# BroadcastDriveLetterChange

- ea: `0x180006ba0`
- end: `0x180006d67`
- name: `BroadcastDriveLetterChange`
- size: `455`
- prototype: `__int64 __fastcall(char, char, struct _LUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180006aa0`

## callees

- `0x180006ba0`
- `0x18000789c`
- `0x18000d730`
- `0x18000e010`

## import_xrefs

- `ntdll!RtlCopyLuid` at `0x180006c0c`
- `ntdll!RtlCopyLuid` at `0x180006c0c`
- `ntdll!LdrGetDllHandle` at `0x180006c89`
- `ntdll!LdrGetDllHandle` at `0x180006c89`
- `ntdll!LdrGetProcedureAddress` at `0x180006cb6`
- `ntdll!LdrGetProcedureAddress` at `0x180006cb6`

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
  int v13; // [rsp+40h] [rbp-68h] BYREF
  PVOID DllHandle; // [rsp+48h] [rbp-60h] BYREF
  _DWORD v15[2]; // [rsp+50h] [rbp-58h] BYREF
  __int128 v16; // [rsp+58h] [rbp-50h]
  struct _LUID DestinationLuid; // [rsp+68h] [rbp-40h] BYREF
  int v18; // [rsp+70h] [rbp-38h] BYREF
  __int64 v19; // [rsp+74h] [rbp-34h]
  int v20; // [rsp+7Ch] [rbp-2Ch]
  __int16 v21; // [rsp+80h] [rbp-28h]
  __int16 v22; // [rsp+82h] [rbp-26h]

  v15[1] = 0;
  DestinationLuid.LowPart = 0;
  v22 = 0;
  if ( !a3 )
    return 3221225485LL;
  v15[0] = 32;
  v16 = 0;
  RtlCopyLuid(&DestinationLuid, a3);
  v18 = 20;
  v19 = 2;
  v21 = 2;
  v6 = 104;
  v20 = 1 << a1;
  if ( DestinationLuid.LowPart != 999 || DestinationLuid.HighPart )
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
    ProcedureAddress = ((__int64 (__fastcall *)(_QWORD, int *, __int64, __int64, int *, _DWORD *))v7)(
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
0x180006ba0  push    rbx
0x180006ba2  push    rbp
0x180006ba3  push    rsi
0x180006ba4  sub     rsp, 90h
0x180006bab  mov     rax, cs:__security_cookie
0x180006bb2  xor     rax, rsp
0x180006bb5  mov     [rsp+0A8h+var_20], rax
0x180006bbd  xor     ebp, ebp
0x180006bbf  movzx   esi, dl
0x180006bc2  mov     [rsp+0A8h+var_54], ebp
0x180006bc6  mov     ebx, ecx
0x180006bc8  mov     [rsp+0A8h+DestinationLuid.LowPart], ebp
0x180006bcc  mov     [rsp+0A8h+var_26], bp
0x180006bd4  test    r8, r8
0x180006bd7  jnz     short loc_180006BE3
0x180006bd9  mov     eax, 0C000000Dh
0x180006bde  jmp     loc_180006D4B
0x180006be3  xorps   xmm0, xmm0
0x180006be6  mov     [rsp+0A8h+arg_8], rdi
0x180006bee  mov     rdx, r8; SourceLuid
0x180006bf1  mov     [rsp+0A8h+arg_18], r14
0x180006bf9  lea     rcx, [rsp+0A8h+DestinationLuid]; DestinationLuid
0x180006bfe  mov     [rsp+0A8h+var_58], 20h ; ' '
0x180006c06  movdqu  [rsp+0A8h+var_50], xmm0
0x180006c0c  call    cs:__imp_RtlCopyLuid
0x180006c13  nop     dword ptr [rax+rax+00h]
0x180006c18  mov     edx, 2
0x180006c1d  mov     [rsp+0A8h+var_38], 14h
0x180006c25  mov     ecx, ebx
0x180006c27  mov     [rsp+0A8h+var_34], rdx
0x180006c2c  mov     eax, 1
0x180006c31  mov     [rsp+0A8h+var_28], dx
0x180006c39  shl     eax, cl
0x180006c3b  cmp     [rsp+0A8h+DestinationLuid.LowPart], 3E7h
0x180006c43  lea     edi, [rdx+66h]
0x180006c46  mov     [rsp+0A8h+var_2C], eax
0x180006c4a  jnz     short loc_180006C52
0x180006c4c  cmp     [rsp+0A8h+DestinationLuid.HighPart], ebp
0x180006c50  jz      short loc_180006C57
0x180006c52  mov     edi, 468h
0x180006c57  mov     rax, cs:PBROADCASTSYSTEMMESSAGEEXW
0x180006c5e  mov     ebx, 8004h
0x180006c63  mov     [rsp+0A8h+var_68], 18h
0x180006c6b  mov     [rsp+0A8h+DllHandle], rbp
0x180006c70  lea     r14d, [rbx-4]
0x180006c74  test    rax, rax
0x180006c77  jnz     short loc_180006CDD
0x180006c79  lea     r9, [rsp+0A8h+DllHandle]; DllHandle
0x180006c7e  xor     edx, edx; DllCharacteristics
0x180006c80  lea     r8, DllName; DllName
0x180006c87  xor     ecx, ecx; DllPath
0x180006c89  call    cs:__imp_LdrGetDllHandle
0x180006c90  nop     dword ptr [rax+rax+00h]
0x180006c95  mov     rcx, [rsp+0A8h+DllHandle]; BaseAddress
0x180006c9a  mov     edx, eax
0x180006c9c  test    rcx, rcx
0x180006c9f  jz      short loc_180006CD1
0x180006ca1  test    eax, eax
0x180006ca3  js      short loc_180006CD1
0x180006ca5  lea     r9, PBROADCASTSYSTEMMESSAGEEXW; ProcedureAddress
0x180006cac  xor     r8d, r8d; Ordinal
0x180006caf  lea     rdx, stru_18000F8D0; Name
0x180006cb6  call    cs:__imp_LdrGetProcedureAddress
0x180006cbd  nop     dword ptr [rax+rax+00h]
0x180006cc2  mov     edx, eax
0x180006cc4  test    eax, eax
0x180006cc6  jns     short loc_180006CD1
0x180006cc8  mov     cs:PBROADCASTSYSTEMMESSAGEEXW, rbp
0x180006ccf  jmp     short loc_180006D10
0x180006cd1  mov     rax, cs:PBROADCASTSYSTEMMESSAGEEXW
0x180006cd8  test    rax, rax
0x180006cdb  jz      short loc_180006D10
0x180006cdd  lea     rcx, [rsp+0A8h+var_58]
0x180006ce2  cmp     sil, 1
0x180006ce6  mov     [rsp+0A8h+var_80], rcx
0x180006ceb  lea     rdx, [rsp+0A8h+var_68]
0x180006cf0  lea     rcx, [rsp+0A8h+var_38]
0x180006cf5  mov     r9, rbx
0x180006cf8  mov     [rsp+0A8h+var_88], rcx
0x180006cfd  cmovnz  r9, r14
0x180006d01  mov     ecx, edi
0x180006d03  mov     r8d, 219h
0x180006d09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d0e  mov     edx, eax
0x180006d10  bt      edi, 0Ah
0x180006d14  jb      short loc_180006D39
0x180006d16  cmp     sil, 1
0x180006d1a  lea     rax, [rsp+0A8h+var_38]
0x180006d1f  lea     rdx, [rsp+0A8h+var_68]
0x180006d24  mov     [rsp+0A8h+var_88], rax
0x180006d29  cmovnz  rbx, r14
0x180006d2d  mov     ecx, edi
0x180006d2f  mov     r9, rbx
0x180006d32  call    SendWinStationBSM
0x180006d37  mov     edx, eax
0x180006d39  mov     r14, [rsp+0A8h+arg_18]
0x180006d41  mov     eax, edx
0x180006d43  mov     rdi, [rsp+0A8h+arg_8]
0x180006d4b  mov     rcx, [rsp+0A8h+var_20]
0x180006d53  xor     rcx, rsp; StackCookie
0x180006d56  call    __security_check_cookie
0x180006d5b  add     rsp, 90h
0x180006d62  pop     rsi
0x180006d63  pop     rbp
0x180006d64  pop     rbx
0x180006d65  retn
```
