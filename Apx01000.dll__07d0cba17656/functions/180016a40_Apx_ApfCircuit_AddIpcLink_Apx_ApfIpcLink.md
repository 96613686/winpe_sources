# Apx::ApfCircuit::AddIpcLink(Apx::ApfIpcLink *)

- ea: `0x180016a40`
- end: `0x180016b52`
- name: `?AddIpcLink@ApfCircuit@Apx@@QEAAXPEAVApfIpcLink@2@@Z`
- size: `274`
- prototype: `void __fastcall(Apx::ApfCircuit *this, unsigned __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010a84`
- `0x180010c7c`

## callees

- `0x18000a12c`
- `0x18000d3c0`
- `0x180016a40`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016ab0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016ab0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016a87`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016a87`

## pseudocode

```c
void __fastcall Apx::ApfCircuit::AddIpcLink(Apx::ApfCircuit *this, unsigned __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_dec558fb6f7b38a97945fa3380f33db3_Traceguids);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v4 = *((unsigned int *)this + 20);
  *((_DWORD *)this + 11) = 4;
  *((_DWORD *)this + v4 + 12) = 4;
  if ( ++*((_DWORD *)this + 20) >= 8u )
    *((_DWORD *)this + 20) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  imp_ApxObjectReferenceActual(0, (Apx::ApfVerify *)~a2);
  *((_QWORD *)this + 4) = a2;
  v5 = (*(__int64 (__fastcall **)(unsigned __int64))(*(_QWORD *)a2 + 48LL))(a2);
  v6 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 3) = v5;
  (*(void (__fastcall **)(__int64, __int64 (__fastcall *)(Apx::ApfCircuit *, unsigned __int16, struct APF_MESSAGE *, unsigned int, void *, unsigned int, unsigned int *), Apx::ApfCircuit *))(*(_QWORD *)v6 + 16LL))(
    v6,
    Apx::ApfCircuit::_CommandHandler,
    this);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 24LL))(*((_QWORD *)this + 4));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_dec558fb6f7b38a97945fa3380f33db3_Traceguids);
  }
}

```

## disassembly

```asm
0x180016a40  push    rbx
0x180016a42  push    rbp
0x180016a43  push    rsi
0x180016a44  push    rdi
0x180016a45  sub     rsp, 38h
0x180016a49  mov     rsi, rdx
0x180016a4c  mov     rbx, rcx
0x180016a4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a56  lea     rbp, WPP_GLOBAL_Control
0x180016a5d  cmp     rcx, rbp
0x180016a60  jz      short loc_180016A83
0x180016a62  test    byte ptr [rcx+1Ch], 1
0x180016a66  jz      short loc_180016A83
0x180016a68  cmp     byte ptr [rcx+19h], 5
0x180016a6c  jb      short loc_180016A83
0x180016a6e  mov     rcx, [rcx+10h]
0x180016a72  lea     r8, WPP_dec558fb6f7b38a97945fa3380f33db3_Traceguids
0x180016a79  mov     edx, 1Ah
0x180016a7e  call    WPP_SF_
0x180016a83  lea     rcx, [rbx+58h]; lpCriticalSection
0x180016a87  call    cs:__imp_EnterCriticalSection
0x180016a8d  mov     eax, [rbx+50h]
0x180016a90  mov     ecx, 4
0x180016a95  mov     [rbx+2Ch], ecx
0x180016a98  mov     [rbx+rax*4+30h], ecx
0x180016a9c  inc     dword ptr [rbx+50h]
0x180016a9f  cmp     dword ptr [rbx+50h], 8
0x180016aa3  jb      short loc_180016AAC
0x180016aa5  mov     dword ptr [rbx+50h], 0
0x180016aac  lea     rcx, [rbx+58h]; lpCriticalSection
0x180016ab0  call    cs:__imp_LeaveCriticalSection
0x180016ab6  lea     rax, aOnecoreuapDriv_6; "onecoreuap\\drivers\\wdm\\audio\\backpl"...
0x180016abd  mov     rdx, rsi
0x180016ac0  not     rdx; Apx::ApfVerify *
0x180016ac3  mov     [rsp+58h+var_38], rax
0x180016ac8  xor     ecx, ecx; this
0x180016aca  mov     r9d, 1AEh
0x180016ad0  mov     r8d, 44787041h
0x180016ad6  call    imp_ApxObjectReferenceActual
0x180016adb  mov     [rbx+20h], rsi
0x180016adf  mov     rcx, rsi
0x180016ae2  mov     rax, [rsi]
0x180016ae5  mov     rax, [rax+30h]
0x180016ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016aee  mov     rcx, [rbx+20h]
0x180016af2  lea     rdx, ?_CommandHandler@ApfCircuit@Apx@@CAJPEAXGPEAUAPF_MESSAGE@@K0KPEAK@Z; Apx::ApfCircuit::_CommandHandler(void *,ushort,APF_MESSAGE *,ulong,void *,ulong,ulong *)
0x180016af9  mov     [rbx+18h], rax
0x180016afd  mov     r8, rbx
0x180016b00  mov     rax, [rcx]
0x180016b03  mov     rax, [rax+10h]
0x180016b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b0c  mov     rcx, [rbx+20h]
0x180016b10  mov     rax, [rcx]
0x180016b13  mov     rax, [rax+18h]
0x180016b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b23  cmp     rcx, rbp
0x180016b26  jz      short loc_180016B49
0x180016b28  test    byte ptr [rcx+1Ch], 1
0x180016b2c  jz      short loc_180016B49
0x180016b2e  cmp     byte ptr [rcx+19h], 5
0x180016b32  jb      short loc_180016B49
0x180016b34  mov     rcx, [rcx+10h]
0x180016b38  lea     r8, WPP_dec558fb6f7b38a97945fa3380f33db3_Traceguids
0x180016b3f  mov     edx, 1Bh
0x180016b44  call    WPP_SF_
0x180016b49  add     rsp, 38h
0x180016b4d  pop     rdi
0x180016b4e  pop     rsi
0x180016b4f  pop     rbp
0x180016b50  pop     rbx
0x180016b51  retn
```
