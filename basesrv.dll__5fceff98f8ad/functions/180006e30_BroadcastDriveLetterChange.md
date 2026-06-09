# BroadcastDriveLetterChange

- ea: `0x180006e30`
- end: `0x180006ff2`
- name: `BroadcastDriveLetterChange`
- size: `450`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180006d30`

## callees

- `0x180006e30`
- `0x180007ba0`
- `0x18000db40`
- `0x18000e010`

## import_xrefs

- `ntdll!RtlCopyLuid` at `0x180006ea6`
- `ntdll!RtlCopyLuid` at `0x180006ea6`
- `ntdll!LdrGetDllHandle` at `0x180006f1c`
- `ntdll!LdrGetDllHandle` at `0x180006f1c`
- `ntdll!LdrGetProcedureAddress` at `0x180006f48`
- `ntdll!LdrGetProcedureAddress` at `0x180006f48`

## pseudocode

```c
__int64 __fastcall BroadcastDriveLetterChange(char a1, char a2, struct _LUID *a3)
{
  unsigned int v6; // edi
  PVOID v7; // rax
  int v8; // ebx
  NTSTATUS v9; // eax
  int v10; // r8d
  NTSTATUS ProcedureAddress; // edx
  __int64 v12; // r9
  int v13; // [rsp+40h] [rbp-19h] BYREF
  PVOID DllHandle; // [rsp+48h] [rbp-11h] BYREF
  _DWORD v15[2]; // [rsp+50h] [rbp-9h] BYREF
  __int128 v16; // [rsp+58h] [rbp-1h]
  struct _LUID DestinationLuid; // [rsp+68h] [rbp+Fh] BYREF
  __int128 v18; // [rsp+70h] [rbp+17h] BYREF
  int v19; // [rsp+80h] [rbp+27h]

  v15[1] = 0;
  DestinationLuid.LowPart = 0;
  v19 = 0;
  v13 = 0;
  DllHandle = 0;
  v18 = 0;
  if ( !a3 )
    return 3221225485LL;
  v15[0] = 32;
  v16 = 0;
  RtlCopyLuid(&DestinationLuid, a3);
  LODWORD(v18) = 20;
  *(_QWORD *)((char *)&v18 + 4) = 2;
  LOWORD(v19) = 2;
  HIDWORD(v18) = 1 << a1;
  if ( DestinationLuid.LowPart != 999 || (v6 = 104, DestinationLuid.HighPart) )
    v6 = 1128;
  v7 = PBROADCASTSYSTEMMESSAGEEXW;
  v8 = 32772;
  v13 = 24;
  DllHandle = 0;
  if ( PBROADCASTSYSTEMMESSAGEEXW )
    goto LABEL_12;
  v9 = LdrGetDllHandle(0, 0, (PUNICODE_STRING)&DllName, &DllHandle);
  ProcedureAddress = v9;
  if ( !DllHandle
    || v9 < 0
    || (ProcedureAddress = LdrGetProcedureAddress(
                             DllHandle,
                             (PANSI_STRING)&stru_18000F8D0,
                             0,
                             &PBROADCASTSYSTEMMESSAGEEXW),
        ProcedureAddress >= 0) )
  {
    v7 = PBROADCASTSYSTEMMESSAGEEXW;
    if ( !PBROADCASTSYSTEMMESSAGEEXW )
      goto LABEL_15;
LABEL_12:
    v12 = 32772;
    if ( a2 != 1 )
      v12 = 0x8000;
    ProcedureAddress = ((__int64 (__fastcall *)(_QWORD, int *, __int64, __int64, __int128 *, _DWORD *))v7)(
                         v6,
                         &v13,
                         537,
                         v12,
                         &v18,
                         v15);
    goto LABEL_15;
  }
  PBROADCASTSYSTEMMESSAGEEXW = 0;
LABEL_15:
  if ( (v6 & 0x400) == 0 )
  {
    if ( a2 != 1 )
      v8 = 0x8000;
    return (unsigned int)SendWinStationBSM(v6, (unsigned int)&v13, v10, v8, (__int64)&v18);
  }
  return (unsigned int)ProcedureAddress;
}

```

## disassembly

```asm
0x180006e30  push    rbp
0x180006e32  push    rbx
0x180006e33  push    rsi
0x180006e34  push    r14
0x180006e36  lea     rbp, [rsp-3Fh]
0x180006e3b  sub     rsp, 98h
0x180006e42  mov     rax, cs:__security_cookie
0x180006e49  xor     rax, rsp
0x180006e4c  mov     [rbp+57h+var_28], rax
0x180006e50  xor     r14d, r14d
0x180006e53  xor     eax, eax
0x180006e55  mov     [rbp+57h+var_5C], r14d
0x180006e59  xorps   xmm0, xmm0
0x180006e5c  mov     [rbp+57h+DestinationLuid.LowPart], r14d
0x180006e60  movzx   esi, dl
0x180006e63  mov     [rbp+57h+var_30], eax
0x180006e66  mov     ebx, ecx
0x180006e68  mov     [rbp+57h+var_70], r14d
0x180006e6c  mov     [rbp+57h+DllHandle], r14
0x180006e70  movups  [rbp+57h+var_40], xmm0
0x180006e74  test    r8, r8
0x180006e77  jnz     short loc_180006E83
0x180006e79  mov     eax, 0C000000Dh
0x180006e7e  jmp     loc_180006FD8
0x180006e83  mov     [rsp+0B0h+arg_8], rdi
0x180006e8b  lea     rcx, [rbp+57h+DestinationLuid]; DestinationLuid
0x180006e8f  mov     rdx, r8; SourceLuid
0x180006e92  mov     [rsp+0B0h+var_20], r15
0x180006e9a  mov     [rbp+57h+var_60], 20h ; ' '
0x180006ea1  movdqu  [rbp+57h+var_58], xmm0
0x180006ea6  call    cs:__imp_RtlCopyLuid
0x180006ead  nop     dword ptr [rax+rax+00h]
0x180006eb2  mov     edx, 2
0x180006eb7  mov     dword ptr [rbp+57h+var_40], 14h
0x180006ebe  mov     ecx, ebx
0x180006ec0  mov     qword ptr [rbp+57h+var_40+4], rdx
0x180006ec4  mov     eax, 1
0x180006ec9  mov     word ptr [rbp+57h+var_30], dx
0x180006ecd  shl     eax, cl
0x180006ecf  cmp     [rbp+57h+DestinationLuid.LowPart], 3E7h
0x180006ed6  mov     dword ptr [rbp+57h+var_40+0Ch], eax
0x180006ed9  jnz     short loc_180006EE6
0x180006edb  mov     edi, 68h ; 'h'
0x180006ee0  cmp     [rbp+57h+DestinationLuid.HighPart], r14d
0x180006ee4  jz      short loc_180006EEB
0x180006ee6  mov     edi, 468h
0x180006eeb  mov     rax, cs:PBROADCASTSYSTEMMESSAGEEXW
0x180006ef2  mov     ebx, 8004h
0x180006ef7  mov     [rbp+57h+var_70], 18h
0x180006efe  mov     r15d, 8000h
0x180006f04  mov     [rbp+57h+DllHandle], r14
0x180006f08  test    rax, rax
0x180006f0b  jnz     short loc_180006F6F
0x180006f0d  lea     r9, [rbp+57h+DllHandle]; DllHandle
0x180006f11  xor     edx, edx; DllCharacteristics
0x180006f13  lea     r8, DllName; DllName
0x180006f1a  xor     ecx, ecx; DllPath
0x180006f1c  call    cs:__imp_LdrGetDllHandle
0x180006f23  nop     dword ptr [rax+rax+00h]
0x180006f28  mov     rcx, [rbp+57h+DllHandle]; BaseAddress
0x180006f2c  mov     edx, eax
0x180006f2e  test    rcx, rcx
0x180006f31  jz      short loc_180006F63
0x180006f33  test    eax, eax
0x180006f35  js      short loc_180006F63
0x180006f37  lea     r9, PBROADCASTSYSTEMMESSAGEEXW; ProcedureAddress
0x180006f3e  xor     r8d, r8d; Ordinal
0x180006f41  lea     rdx, stru_18000F8D0; Name
0x180006f48  call    cs:__imp_LdrGetProcedureAddress
0x180006f4f  nop     dword ptr [rax+rax+00h]
0x180006f54  mov     edx, eax
0x180006f56  test    eax, eax
0x180006f58  jns     short loc_180006F63
0x180006f5a  mov     cs:PBROADCASTSYSTEMMESSAGEEXW, r14
0x180006f61  jmp     short loc_180006F9F
0x180006f63  mov     rax, cs:PBROADCASTSYSTEMMESSAGEEXW
0x180006f6a  test    rax, rax
0x180006f6d  jz      short loc_180006F9F
0x180006f6f  lea     rcx, [rbp+57h+var_60]
0x180006f73  cmp     sil, 1
0x180006f77  mov     [rsp+0B0h+var_88], rcx
0x180006f7c  lea     rdx, [rbp+57h+var_70]
0x180006f80  lea     rcx, [rbp+57h+var_40]
0x180006f84  mov     r9, rbx
0x180006f87  mov     [rsp+0B0h+var_90], rcx
0x180006f8c  cmovnz  r9, r15
0x180006f90  mov     ecx, edi
0x180006f92  mov     r8d, 219h
0x180006f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f9d  mov     edx, eax
0x180006f9f  bt      edi, 0Ah
0x180006fa3  jb      short loc_180006FC6
0x180006fa5  cmp     sil, 1
0x180006fa9  lea     rax, [rbp+57h+var_40]
0x180006fad  lea     rdx, [rbp+57h+var_70]
0x180006fb1  mov     [rsp+0B0h+var_90], rax
0x180006fb6  cmovnz  rbx, r15
0x180006fba  mov     ecx, edi
0x180006fbc  mov     r9, rbx
0x180006fbf  call    SendWinStationBSM
0x180006fc4  mov     edx, eax
0x180006fc6  mov     r15, [rsp+0B0h+var_20]
0x180006fce  mov     eax, edx
0x180006fd0  mov     rdi, [rsp+0B0h+arg_8]
0x180006fd8  mov     rcx, [rbp+57h+var_28]
0x180006fdc  xor     rcx, rsp; StackCookie
0x180006fdf  call    __security_check_cookie
0x180006fe4  add     rsp, 98h
0x180006feb  pop     r14
0x180006fed  pop     rsi
0x180006fee  pop     rbx
0x180006fef  pop     rbp
0x180006ff0  retn
```
