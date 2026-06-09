# Broker::BrokerBase::DecodeBrokeredEvent(std::vector<uchar,std::allocator<uchar>> &,_BR_EVENT_PARAMETERS * *)

- ea: `0x180019660`
- end: `0x180019760`
- name: `?DecodeBrokeredEvent@BrokerBase@Broker@@QEAAXAEAV?$vector@EV?$allocator@E@std@@@std@@PEAPEAU_BR_EVENT_PARAMETERS@@@Z`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800188c0`

## callees

- `0x18000e9f4`
- `0x18000f794`
- `0x1800165da`
- `0x180019660`
- `0x180019768`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001971d`
- `ntdll!RtlNtStatusToDosError` at `0x18001971d`

## pseudocode

```c
__int64 __fastcall Broker::BrokerBase::DecodeBrokeredEvent(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v3; // r15
  __int16 v4; // si
  void *v5; // rbx
  unsigned __int16 v6; // si
  __int64 result; // rax
  NTSTATUS v9; // edi
  void **pExceptionObject; // [rsp+30h] [rbp-38h] BYREF
  __int128 v11; // [rsp+38h] [rbp-30h]
  int v12; // [rsp+48h] [rbp-20h]
  ULONG v13; // [rsp+50h] [rbp-18h]
  __int64 v14; // [rsp+A0h] [rbp+38h] BYREF

  v14 = a1;
  v3 = *(_QWORD *)a2;
  v4 = *(_WORD *)(a2 + 8);
  v5 = 0;
  LOWORD(v14) = 0;
  v6 = v4 - v3;
  result = BrpDecodeBrokeredEvent_V1(v3, v6, 0, 0, (USHORT *)&v14);
  v9 = result;
  if ( (_DWORD)result == -1073741789 )
  {
    v5 = BciHeapAlloc((unsigned __int16)v14);
    if ( !v5 )
    {
      *((_QWORD *)&v11 + 1) = 0;
      *(_QWORD *)&v11 = "bad allocation";
      pExceptionObject = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)&pExceptionObject;
    }
    result = BrpDecodeBrokeredEvent_V1(v3, v6, v14, (__int64)v5, (USHORT *)&v14);
    v9 = result;
  }
  if ( v9 < 0 )
  {
    if ( v5 )
      BciHeapFree(v5);
    v12 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v13 = RtlNtStatusToDosError(v9);
    v11 = 0;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  *a3 = v5;
  return result;
}

```

## disassembly

```asm
0x180019660  mov     [rsp-30h+arg_0], rcx
0x180019665  push    rbp
0x180019666  push    rbx
0x180019667  push    rsi
0x180019668  push    rdi
0x180019669  push    r14
0x18001966b  push    r15
0x18001966d  mov     rbp, rsp
0x180019670  sub     rsp, 68h
0x180019674  mov     r15, [rdx]
0x180019677  xor     eax, eax
0x180019679  movzx   esi, word ptr [rdx+8]
0x18001967d  xor     ebx, ebx
0x18001967f  mov     word ptr [rbp+arg_0], ax
0x180019683  sub     si, r15w
0x180019687  mov     r14, r8
0x18001968a  lea     rax, [rbp+arg_0]
0x18001968e  xor     r8d, r8d
0x180019691  xor     r9d, r9d
0x180019694  mov     [rsp+68h+var_48], rax
0x180019699  movzx   edx, si
0x18001969c  mov     rcx, r15
0x18001969f  call    BrpDecodeBrokeredEvent_V1
0x1800196a4  mov     edi, eax
0x1800196a6  cmp     eax, 0C0000023h
0x1800196ab  jnz     short loc_18001970A
0x1800196ad  movzx   ecx, word ptr [rbp+arg_0]; unsigned __int64
0x1800196b1  call    ?BciHeapAlloc@@YAPEAX_K@Z; BciHeapAlloc(unsigned __int64)
0x1800196b6  mov     rbx, rax
0x1800196b9  test    rax, rax
0x1800196bc  jnz     short loc_1800196EC
0x1800196be  xorps   xmm0, xmm0
0x1800196c1  lea     rax, aBadAllocation; "bad allocation"
0x1800196c8  movups  [rbp+var_30], xmm0
0x1800196cc  mov     qword ptr [rbp+var_30], rax
0x1800196d0  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800196d7  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x1800196de  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800196e2  mov     [rbp+pExceptionObject], rax
0x1800196e6  call    _CxxThrowException_0
0x1800196ec  movzx   r8d, word ptr [rbp+arg_0]
0x1800196f1  lea     rax, [rbp+arg_0]
0x1800196f5  mov     r9, rbx
0x1800196f8  mov     [rsp+68h+var_48], rax
0x1800196fd  movzx   edx, si
0x180019700  mov     rcx, r15
0x180019703  call    BrpDecodeBrokeredEvent_V1
0x180019708  mov     edi, eax
0x18001970a  test    edi, edi
0x18001970c  jns     short loc_180019750
0x18001970e  test    rbx, rbx
0x180019711  jz      short loc_18001971B
0x180019713  mov     rcx, rbx; void *
0x180019716  call    ?BciHeapFree@@YAHPEAX@Z; BciHeapFree(void *)
0x18001971b  mov     ecx, edi; Status
0x18001971d  call    cs:__imp_RtlNtStatusToDosError
0x180019723  lea     rcx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18001972a  mov     [rbp+var_20], 1
0x180019731  mov     [rbp+pExceptionObject], rcx
0x180019735  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18001973c  xorps   xmm0, xmm0
0x18001973f  mov     [rbp+var_18], eax
0x180019742  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180019746  movups  [rbp+var_30], xmm0
0x18001974a  call    _CxxThrowException_0
0x180019750  mov     [r14], rbx
0x180019753  add     rsp, 68h
0x180019757  pop     r15
0x180019759  pop     r14
0x18001975b  pop     rdi
0x18001975c  pop     rsi
0x18001975d  pop     rbx
0x18001975e  pop     rbp
0x18001975f  retn
```
