# CDlpHelpersT<CEmptyType>::FlushRegistryKey(HKEY__ *,ushort const *)

- ea: `0x14000e2a0`
- end: `0x14000e407`
- name: `?FlushRegistryKey@?$CDlpHelpersT@VCEmptyType@@@@SAJPEAUHKEY__@@PEBG@Z`
- size: `359`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140006e64`
- `0x140007494`
- `0x140013894`
- `0x140018ccc`
- `0x140019830`
- `0x14001a000`
- `0x14001a670`

## callees

- `0x1400076c8`
- `0x14000a68c`
- `0x14000e2a0`
- `0x1400135b8`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14000e2df`
- `ADVAPI32!RegOpenKeyExW` at `0x14000e2df`
- `ADVAPI32!RegFlushKey` at `0x14000e3b0`
- `ADVAPI32!RegFlushKey` at `0x14000e3b0`
- `ADVAPI32!RegCloseKey` at `0x14000e322`
- `ADVAPI32!RegCloseKey` at `0x14000e368`
- `ADVAPI32!RegCloseKey` at `0x14000e3e5`
- `ADVAPI32!RegCloseKey` at `0x14000e322`
- `ADVAPI32!RegCloseKey` at `0x14000e368`
- `ADVAPI32!RegCloseKey` at `0x14000e3e5`

## pseudocode

```c
__int64 __fastcall CDlpHelpersT<CEmptyType>::FlushRegistryKey(__int64 a1, const WCHAR *a2)
{
  HKEY v2; // rsi
  HKEY v3; // rbx
  int v5; // ebp
  int v6; // edi
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  int v10; // ecx
  int v11; // eax
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF
  HKEY v14; // [rsp+60h] [rbp+18h] BYREF

  v2 = 0;
  v3 = 0;
  v14 = 0;
  hKey = 0;
  v5 = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 1u, &hKey);
  if ( v6 )
  {
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
  }
  else
  {
    v3 = hKey;
    hKey = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( !(_WORD)v6 )
  {
    v5 = 1;
    goto LABEL_14;
  }
  if ( (unsigned __int16)v6 == 2 )
  {
LABEL_14:
    v6 = 0;
    goto LABEL_15;
  }
  if ( v6 >= 0 )
    v6 = -2147467259;
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
LABEL_15:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
  if ( v3 )
    RegCloseKey(v3);
  if ( v6 < 0 )
    goto LABEL_25;
  if ( !v5 )
  {
    v6 = 0;
    v10 = 0;
LABEL_26:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v10);
    goto LABEL_27;
  }
  v11 = CRegUtilT<CEmptyType,CRegType,0,1>::CreateOrOpenKey(v7, a2, v8, v9, &v14);
  v6 = v11;
  if ( v11 < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v11);
    v2 = v14;
    goto LABEL_27;
  }
  v2 = v14;
  v6 = RegFlushKey(v14);
  if ( v6 )
  {
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
LABEL_25:
    v10 = v6;
    goto LABEL_26;
  }
LABEL_27:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
  if ( v2 )
    RegCloseKey(v2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000e2a0  mov     rax, rsp
0x14000e2a3  mov     [rax+10h], rbx
0x14000e2a7  mov     [rax+20h], rbp
0x14000e2ab  mov     [rax+8], rcx
0x14000e2af  push    rsi
0x14000e2b0  push    rdi
0x14000e2b1  push    r14
0x14000e2b3  sub     rsp, 30h
0x14000e2b7  xor     esi, esi
0x14000e2b9  xor     ebx, ebx
0x14000e2bb  mov     [rax+18h], rsi
0x14000e2bf  xor     r8d, r8d; ulOptions
0x14000e2c2  mov     [rax+8], rbx
0x14000e2c6  lea     rax, [rax+8]
0x14000e2ca  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000e2d1  mov     [rsp+48h+phkResult], rax; phkResult
0x14000e2d6  lea     r9d, [rsi+1]; samDesired
0x14000e2da  mov     r14, rdx
0x14000e2dd  xor     ebp, ebp
0x14000e2df  call    cs:__imp_RegOpenKeyExW
0x14000e2e6  nop     dword ptr [rax+rax+00h]
0x14000e2eb  mov     edi, eax
0x14000e2ed  test    eax, eax
0x14000e2ef  jnz     short loc_14000E2FD
0x14000e2f1  mov     rbx, [rsp+48h+hKey]
0x14000e2f6  mov     [rsp+48h+hKey], rsi
0x14000e2fb  jmp     short loc_14000E311
0x14000e2fd  test    edi, edi
0x14000e2ff  jle     short loc_14000E30A
0x14000e301  movzx   edi, di
0x14000e304  or      edi, 80070000h
0x14000e30a  mov     ecx, edi
0x14000e30c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000e311  mov     ecx, edi
0x14000e313  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000e318  mov     rcx, [rsp+48h+hKey]; hKey
0x14000e31d  test    rcx, rcx
0x14000e320  jz      short loc_14000E333
0x14000e322  call    cs:__imp_RegCloseKey
0x14000e329  nop     dword ptr [rax+rax+00h]
0x14000e32e  mov     [rsp+48h+hKey], rsi
0x14000e333  movzx   eax, di
0x14000e336  test    eax, eax
0x14000e338  jz      short loc_14000E352
0x14000e33a  cmp     eax, 2
0x14000e33d  jz      short loc_14000E357
0x14000e33f  test    edi, edi
0x14000e341  mov     eax, 80004005h
0x14000e346  cmovns  edi, eax
0x14000e349  mov     ecx, edi
0x14000e34b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000e350  jmp     short loc_14000E359
0x14000e352  mov     ebp, 1
0x14000e357  xor     edi, edi
0x14000e359  mov     ecx, edi
0x14000e35b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000e360  test    rbx, rbx
0x14000e363  jz      short loc_14000E374
0x14000e365  mov     rcx, rbx; hKey
0x14000e368  call    cs:__imp_RegCloseKey
0x14000e36f  nop     dword ptr [rax+rax+00h]
0x14000e374  test    edi, edi
0x14000e376  js      short loc_14000E3CF
0x14000e378  test    ebp, ebp
0x14000e37a  jnz     short loc_14000E382
0x14000e37c  xor     edi, edi
0x14000e37e  xor     ecx, ecx
0x14000e380  jmp     short loc_14000E3D1
0x14000e382  lea     rax, [rsp+48h+arg_10]
0x14000e387  mov     rdx, r14
0x14000e38a  mov     [rsp+48h+phkResult], rax
0x14000e38f  call    ?CreateOrOpenKey@?$CRegUtilT@VCEmptyType@@UCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBGK1PEAPEAU2@K@Z; CRegUtilT<CEmptyType,CRegType,0,1>::CreateOrOpenKey(HKEY__ *,ushort const *,ulong,ushort const *,HKEY__ * *,ulong)
0x14000e394  mov     edi, eax
0x14000e396  test    eax, eax
0x14000e398  jns     short loc_14000E3A8
0x14000e39a  mov     ecx, eax
0x14000e39c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000e3a1  mov     rsi, [rsp+48h+arg_10]
0x14000e3a6  jmp     short loc_14000E3D6
0x14000e3a8  mov     rsi, [rsp+48h+arg_10]
0x14000e3ad  mov     rcx, rsi; hKey
0x14000e3b0  call    cs:__imp_RegFlushKey
0x14000e3b7  nop     dword ptr [rax+rax+00h]
0x14000e3bc  mov     edi, eax
0x14000e3be  test    eax, eax
0x14000e3c0  jz      short loc_14000E3D6
0x14000e3c2  test    edi, edi
0x14000e3c4  jle     short loc_14000E3CF
0x14000e3c6  movzx   edi, di
0x14000e3c9  or      edi, 80070000h
0x14000e3cf  mov     ecx, edi
0x14000e3d1  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000e3d6  mov     ecx, edi
0x14000e3d8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000e3dd  test    rsi, rsi
0x14000e3e0  jz      short loc_14000E3F1
0x14000e3e2  mov     rcx, rsi; hKey
0x14000e3e5  call    cs:__imp_RegCloseKey
0x14000e3ec  nop     dword ptr [rax+rax+00h]
0x14000e3f1  mov     rbx, [rsp+48h+arg_8]
0x14000e3f6  mov     eax, edi
0x14000e3f8  mov     rbp, [rsp+48h+arg_18]
0x14000e3fd  add     rsp, 30h
0x14000e401  pop     r14
0x14000e403  pop     rdi
0x14000e404  pop     rsi
0x14000e405  retn
```
