# BampProcessWindowStateUpdate

- ea: `0x140012eec`
- end: `0x14001308b`
- name: `BampProcessWindowStateUpdate`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update`

## callers

- `0x140012ea0`

## callees

- `0x140001430`
- `0x1400026d0`
- `0x14000c18c`
- `0x1400102d4`
- `0x140010684`
- `0x140010760`
- `0x1400107a0`
- `0x1400107f0`
- `0x1400114e4`
- `0x140012eec`
- `0x1400153a0`

## import_xrefs

- `ntoskrnl!PsGetProcessSessionId` at `0x140012f68`
- `ntoskrnl!PsGetProcessSessionId` at `0x140012f68`
- `ntoskrnl!PsGetServerSiloServiceSessionId` at `0x140012f8d`
- `ntoskrnl!PsGetServerSiloServiceSessionId` at `0x140012f8d`
- `ntoskrnl!PsGetProcessServerSilo` at `0x140012f7e`
- `ntoskrnl!PsGetProcessServerSilo` at `0x140012f7e`

## pseudocode

```c
__int64 __fastcall BampProcessWindowStateUpdate(__int64 a1, int a2)
{
  void *ThrottledProcessInformation; // rbx
  unsigned int v5; // edi
  unsigned int ProcessSessionId; // eax
  __int64 ProcessServerSilo; // rax
  unsigned int ServerSiloServiceSessionId; // eax
  int v10; // [rsp+30h] [rbp-29h] BYREF
  int v11; // [rsp+34h] [rbp-25h] BYREF
  int v12; // [rsp+38h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+40h] [rbp-19h] BYREF
  int *v14; // [rsp+60h] [rbp+7h]
  __int64 v15; // [rsp+68h] [rbp+Fh]
  int *v16; // [rsp+70h] [rbp+17h]
  __int64 v17; // [rsp+78h] [rbp+1Fh]
  int *v18; // [rsp+80h] [rbp+27h]
  __int64 v19; // [rsp+88h] [rbp+2Fh]

  BampAcquireThrottlingLockShared();
  ThrottledProcessInformation = (void *)BampFindThrottledProcessInformation(a1);
  BampReleaseThrottlingLockShared();
  if ( !ThrottledProcessInformation )
  {
    v5 = -1073741275;
    goto LABEL_13;
  }
  v10 = 0;
  if ( a2 )
  {
    v10 = 1;
    switch ( a2 )
    {
      case 2:
        v10 = 9;
        break;
      case 3:
        v10 = 5;
        break;
      case 4:
        v10 = 7;
        break;
      case 5:
        ProcessSessionId = PsGetProcessSessionId(a1);
        BampTempBoostCreateOrExtend(ProcessSessionId);
        ProcessServerSilo = PsGetProcessServerSilo(a1);
        ServerSiloServiceSessionId = PsGetServerSiloServiceSessionId(ProcessServerSilo);
        v5 = BampTempBoostCreateOrExtend(ServerSiloServiceSessionId);
        goto LABEL_13;
    }
  }
  BampAcquireThrottledProcessLock(ThrottledProcessInformation);
  BampUpdateThrottledProcessState((__int64)ThrottledProcessInformation, &v10, 0, 0, 0);
  BampReleaseThrottledProcessLock(ThrottledProcessInformation);
  v5 = 0;
LABEL_13:
  if ( (unsigned int)dword_140007010 > 4 )
  {
    v15 = 4;
    v14 = &v10;
    v11 = *(_DWORD *)(a1 + 464);
    v17 = 4;
    v16 = &v11;
    v18 = &v12;
    v19 = 4;
    v10 = v5;
    v12 = a2;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140007010, (unsigned __int8 *)byte_140004AB3, 0, 0, 5u, &v13);
  }
  if ( ThrottledProcessInformation )
    BampDereferenceThrottledProcessInformation(ThrottledProcessInformation);
  return v5;
}

```

## disassembly

```asm
0x140012eec  mov     [rsp-8+arg_8], rbx
0x140012ef1  mov     [rsp-8+arg_10], rsi
0x140012ef6  push    rbp
0x140012ef7  push    rdi
0x140012ef8  push    r14
0x140012efa  lea     rbp, [rsp-47h]
0x140012eff  sub     rsp, 0A0h
0x140012f06  mov     rax, cs:__security_cookie
0x140012f0d  xor     rax, rsp
0x140012f10  mov     [rbp+57h+var_20], rax
0x140012f14  mov     esi, edx
0x140012f16  mov     r14, rcx
0x140012f19  call    BampAcquireThrottlingLockShared
0x140012f1e  mov     rcx, r14
0x140012f21  call    BampFindThrottledProcessInformation
0x140012f26  mov     rbx, rax
0x140012f29  call    BampReleaseThrottlingLockShared
0x140012f2e  test    rbx, rbx
0x140012f31  jnz     short loc_140012F3D
0x140012f33  mov     edi, 0C0000225h
0x140012f38  jmp     loc_140012FEA
0x140012f3d  mov     [rbp+57h+var_80], 0
0x140012f44  test    esi, esi
0x140012f46  jz      short loc_140012FBD
0x140012f48  mov     ecx, esi
0x140012f4a  mov     [rbp+57h+var_80], 1
0x140012f51  sub     ecx, 2
0x140012f54  jz      short loc_140012FB6
0x140012f56  sub     ecx, 1
0x140012f59  jz      short loc_140012FAD
0x140012f5b  sub     ecx, 1
0x140012f5e  jz      short loc_140012FA4
0x140012f60  cmp     ecx, 1
0x140012f63  jnz     short loc_140012FBD
0x140012f65  mov     rcx, r14
0x140012f68  call    cs:__imp_PsGetProcessSessionId
0x140012f6f  nop     dword ptr [rax+rax+00h]
0x140012f74  mov     ecx, eax
0x140012f76  call    BampTempBoostCreateOrExtend
0x140012f7b  mov     rcx, r14
0x140012f7e  call    cs:__imp_PsGetProcessServerSilo
0x140012f85  nop     dword ptr [rax+rax+00h]
0x140012f8a  mov     rcx, rax
0x140012f8d  call    cs:__imp_PsGetServerSiloServiceSessionId
0x140012f94  nop     dword ptr [rax+rax+00h]
0x140012f99  mov     ecx, eax
0x140012f9b  call    BampTempBoostCreateOrExtend
0x140012fa0  mov     edi, eax
0x140012fa2  jmp     short loc_140012FEA
0x140012fa4  mov     [rbp+57h+var_80], 7
0x140012fab  jmp     short loc_140012FBD
0x140012fad  mov     [rbp+57h+var_80], 5
0x140012fb4  jmp     short loc_140012FBD
0x140012fb6  mov     [rbp+57h+var_80], 9
0x140012fbd  mov     rcx, rbx
0x140012fc0  call    BampAcquireThrottledProcessLock
0x140012fc5  xor     r9d, r9d
0x140012fc8  mov     [rsp+0B0h+var_90], 0
0x140012fd1  xor     r8d, r8d
0x140012fd4  lea     rdx, [rbp+57h+var_80]
0x140012fd8  mov     rcx, rbx
0x140012fdb  call    BampUpdateThrottledProcessState
0x140012fe0  mov     rcx, rbx
0x140012fe3  call    BampReleaseThrottledProcessLock
0x140012fe8  xor     edi, edi
0x140012fea  mov     eax, cs:dword_140007010
0x140012ff0  mov     ecx, 4
0x140012ff5  cmp     eax, ecx
0x140012ff7  jbe     short loc_140013057
0x140012ff9  lea     rax, [rbp+57h+var_80]
0x140012ffd  mov     [rbp+57h+var_48], rcx
0x140013001  mov     [rbp+57h+var_50], rax
0x140013005  lea     rdx, byte_140004AB3
0x14001300c  mov     eax, [r14+1D0h]
0x140013013  xor     r9d, r9d
0x140013016  mov     [rbp+57h+var_7C], eax
0x140013019  xor     r8d, r8d
0x14001301c  lea     rax, [rbp+57h+var_7C]
0x140013020  mov     [rbp+57h+var_38], rcx
0x140013024  mov     [rbp+57h+var_40], rax
0x140013028  lea     rax, [rbp+57h+var_78]
0x14001302c  mov     [rbp+57h+var_30], rax
0x140013030  lea     rax, [rbp+57h+var_70]
0x140013034  mov     [rbp+57h+var_28], rcx
0x140013038  lea     rcx, dword_140007010
0x14001303f  mov     [rsp+0B0h+var_88], rax
0x140013044  mov     dword ptr [rsp+0B0h+var_90], 5
0x14001304c  mov     [rbp+57h+var_80], edi
0x14001304f  mov     [rbp+57h+var_78], esi
0x140013052  call    _tlgWriteTransfer_EtwWriteTransfer
0x140013057  test    rbx, rbx
0x14001305a  jz      short loc_140013064
0x14001305c  mov     rcx, rbx; P
0x14001305f  call    BampDereferenceThrottledProcessInformation
0x140013064  mov     eax, edi
0x140013066  mov     rcx, [rbp+57h+var_20]
0x14001306a  xor     rcx, rsp; StackCookie
0x14001306d  call    __security_check_cookie
0x140013072  lea     r11, [rsp+0B0h+var_10]
0x14001307a  mov     rbx, [r11+28h]
0x14001307e  mov     rsi, [r11+30h]
0x140013082  mov     rsp, r11
0x140013085  pop     r14
0x140013087  pop     rdi
0x140013088  pop     rbp
0x140013089  retn
```
