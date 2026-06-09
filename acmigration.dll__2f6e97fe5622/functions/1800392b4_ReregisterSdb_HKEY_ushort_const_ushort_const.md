# ReregisterSdb(HKEY__ *,ushort const *,ushort const *)

- ea: `0x1800392b4`
- end: `0x180039501`
- name: `?ReregisterSdb@@YAJPEAUHKEY__@@PEBG1@Z`
- size: `589`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180037c64`
- `0x180038b90`
- `0x1800390fc`

## callees

- `0x180001cf0`
- `0x1800392b4`
- `0x1800543c0`
- `0x180054594`
- `0x180061528`
- `0x180061b4c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800393ff`
- `KERNEL32!GetLastError` at `0x18003944b`
- `KERNEL32!GetLastError` at `0x1800393ff`
- `KERNEL32!GetLastError` at `0x18003944b`
- `ADVAPI32!RegQueryValueExW` at `0x180039353`
- `ADVAPI32!RegQueryValueExW` at `0x180039396`
- `ADVAPI32!RegQueryValueExW` at `0x180039353`
- `ADVAPI32!RegQueryValueExW` at `0x180039396`
- `ADVAPI32!RegCloseKey` at `0x1800393df`
- `ADVAPI32!RegCloseKey` at `0x1800394e5`
- `ADVAPI32!RegCloseKey` at `0x1800393df`
- `ADVAPI32!RegCloseKey` at `0x1800394e5`
- `ADVAPI32!RegOpenKeyExW` at `0x180039311`
- `ADVAPI32!RegOpenKeyExW` at `0x180039311`

## string_xrefs

- `0x1800394ae`: `Failed to open installed sdb subkey: 0x%x`
- `0x18003947c`: `Failed to query installed sdb value: 0x%x`
- `0x180039495`: `Failed to query installed sdb value: 0x%x`
- `0x18003938f`: `DatabaseInstallTimeStamp`

## pseudocode

```c
__int64 __fastcall ReregisterSdb(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  int v4; // eax
  int v5; // ebx
  int v6; // ebx
  signed int LastError; // eax
  bool v8; // sf
  bool v9; // sf
  const char *v10; // r9
  __int64 v11; // r8
  PHKEY phkResult; // [rsp+20h] [rbp-50h]
  DWORD cbData; // [rsp+30h] [rbp-40h] BYREF
  DWORD Type; // [rsp+34h] [rbp-3Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-38h] BYREF
  BYTE Data[4]; // [rsp+40h] [rbp-30h] BYREF
  BYTE v18[8]; // [rsp+48h] [rbp-28h] BYREF
  GUID Guid; // [rsp+50h] [rbp-20h] BYREF

  hKey = 0;
  cbData = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  Guid = 0;
  *(_QWORD *)v18 = 0;
  v4 = RegOpenKeyExW(a1, a2, 0, 0x20119u, &hKey);
  if ( v4 )
  {
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    goto LABEL_31;
  }
  if ( !hKey )
  {
LABEL_31:
    v10 = "Failed to open installed sdb subkey: 0x%x";
    v11 = 906;
    goto LABEL_32;
  }
  cbData = 4;
  v4 = RegQueryValueExW(hKey, L"DatabaseType", 0, &Type, Data, &cbData);
  if ( v4 )
  {
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    goto LABEL_28;
  }
  if ( Type != 4 )
  {
LABEL_28:
    v10 = "Failed to query installed sdb value: 0x%x";
    v11 = 920;
    goto LABEL_32;
  }
  cbData = 8;
  v4 = RegQueryValueExW(hKey, L"DatabaseInstallTimeStamp", 0, &Type, v18, &cbData);
  if ( v4 )
  {
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    goto LABEL_25;
  }
  if ( Type != 11 )
  {
LABEL_25:
    v10 = "Failed to query installed sdb value: 0x%x";
    v11 = 934;
LABEL_32:
    v9 = v4 < 0;
    goto LABEL_33;
  }
  v5 = AslGuidFromString(&Guid);
  if ( v5 )
  {
    v6 = v5 | 0x10000000;
    if ( v6 >= 0 )
      v6 = -2147467259;
    goto LABEL_36;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( !(unsigned int)SdbUnregisterDatabase((__int64)&Guid) )
  {
    LastError = GetLastError();
    v8 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v8 = LastError < 0;
    }
    if ( !v8 )
      LastError = -2147467259;
    AslLogCallPrintf(1, "ReregisterSdb", 960, "Failed to unregister sdb: 0x%x", LastError);
  }
  if ( (unsigned int)SdbRegisterDatabaseEx(a3, *(ULONG *)Data, (struct _FILETIME *)v18) )
  {
    v6 = 0;
    goto LABEL_36;
  }
  v4 = GetLastError();
  v9 = v4 < 0;
  if ( v4 > 0 )
  {
    v4 = (unsigned __int16)v4 | 0x80070000;
    v9 = v4 < 0;
  }
  v10 = "Failed to unregister sdb: 0x%x";
  v11 = 971;
LABEL_33:
  if ( !v9 )
    v4 = -2147467259;
  LODWORD(phkResult) = v4;
  v6 = v4;
  AslLogCallPrintf(1, "ReregisterSdb", v11, v10, phkResult);
LABEL_36:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800392b4  push    rbp
0x1800392b6  push    rbx
0x1800392b7  push    rdi
0x1800392b8  mov     rbp, rsp
0x1800392bb  sub     rsp, 70h
0x1800392bf  mov     rax, cs:__security_cookie
0x1800392c6  xor     rax, rsp
0x1800392c9  mov     [rbp+var_10], rax
0x1800392cd  mov     rdi, r8
0x1800392d0  mov     [rbp+hKey], 0
0x1800392d8  xorps   xmm0, xmm0
0x1800392db  mov     [rbp+cbData], 0
0x1800392e2  lea     rax, [rbp+hKey]
0x1800392e6  mov     [rbp+Type], 0
0x1800392ed  xor     r8d, r8d; ulOptions
0x1800392f0  mov     [rsp+70h+phkResult], rax; phkResult
0x1800392f5  mov     r9d, 20119h; samDesired
0x1800392fb  mov     dword ptr [rbp+Data], 0
0x180039302  movups  xmmword ptr [rbp+Guid.Data1], xmm0
0x180039306  mov     rbx, rdx
0x180039309  mov     qword ptr [rbp+var_28], 0
0x180039311  call    cs:__imp_RegOpenKeyExW
0x180039317  test    eax, eax
0x180039319  jnz     loc_1800394A4
0x18003931f  mov     rcx, [rbp+hKey]; hKey
0x180039323  test    rcx, rcx
0x180039326  jz      loc_1800394AE
0x18003932c  lea     rax, [rbp+cbData]
0x180039330  mov     [rbp+cbData], 4
0x180039337  mov     [rsp+70h+lpcbData], rax; lpcbData
0x18003933c  lea     r9, [rbp+Type]; lpType
0x180039340  lea     rax, [rbp+Data]
0x180039344  xor     r8d, r8d; lpReserved
0x180039347  lea     rdx, aDatabasetype; "DatabaseType"
0x18003934e  mov     [rsp+70h+phkResult], rax; lpData
0x180039353  call    cs:__imp_RegQueryValueExW
0x180039359  test    eax, eax
0x18003935b  jnz     loc_18003948B
0x180039361  cmp     [rbp+Type], 4
0x180039365  jnz     loc_180039495
0x18003936b  mov     rcx, [rbp+hKey]; hKey
0x18003936f  lea     rax, [rbp+cbData]
0x180039373  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180039378  lea     r9, [rbp+Type]; lpType
0x18003937c  lea     rax, [rbp+var_28]
0x180039380  mov     [rbp+cbData], 8
0x180039387  xor     r8d, r8d; lpReserved
0x18003938a  mov     [rsp+70h+phkResult], rax; lpData
0x18003938f  lea     rdx, aDatabaseinstal; "DatabaseInstallTimeStamp"
0x180039396  call    cs:__imp_RegQueryValueExW
0x18003939c  test    eax, eax
0x18003939e  jnz     loc_180039472
0x1800393a4  cmp     [rbp+Type], 0Bh
0x1800393a8  jnz     loc_18003947C
0x1800393ae  mov     rdx, rbx
0x1800393b1  lea     rcx, [rbp+Guid]; Guid
0x1800393b5  call    AslGuidFromString
0x1800393ba  mov     ebx, eax
0x1800393bc  test    eax, eax
0x1800393be  jz      short loc_1800393D6
0x1800393c0  or      ebx, 10000000h
0x1800393c6  jl      loc_1800394DC
0x1800393cc  mov     ebx, 80004005h
0x1800393d1  jmp     loc_1800394DC
0x1800393d6  mov     rcx, [rbp+hKey]; hKey
0x1800393da  test    rcx, rcx
0x1800393dd  jz      short loc_1800393ED
0x1800393df  call    cs:__imp_RegCloseKey
0x1800393e5  mov     [rbp+hKey], 0
0x1800393ed  lea     rcx, [rbp+Guid]
0x1800393f1  call    SdbUnregisterDatabase
0x1800393f6  mov     ebx, 80004005h
0x1800393fb  test    eax, eax
0x1800393fd  jnz     short loc_180039438
0x1800393ff  call    cs:__imp_GetLastError
0x180039405  test    eax, eax
0x180039407  jle     short loc_180039413
0x180039409  movzx   eax, ax
0x18003940c  or      eax, 80070000h
0x180039411  test    eax, eax
0x180039413  cmovns  eax, ebx
0x180039416  lea     r9, aFailedToUnregi; "Failed to unregister sdb: 0x%x"
0x18003941d  mov     r8d, 3C0h
0x180039423  mov     dword ptr [rsp+70h+phkResult], eax
0x180039427  lea     rdx, aReregistersdb; "ReregisterSdb"
0x18003942e  mov     ecx, 1
0x180039433  call    AslLogCallPrintf
0x180039438  mov     edx, dword ptr [rbp+Data]
0x18003943b  lea     r8, [rbp+var_28]
0x18003943f  mov     rcx, rdi; SourceString
0x180039442  call    SdbRegisterDatabaseEx
0x180039447  test    eax, eax
0x180039449  jnz     short loc_18003946E
0x18003944b  call    cs:__imp_GetLastError
0x180039451  test    eax, eax
0x180039453  jle     short loc_18003945F
0x180039455  movzx   eax, ax
0x180039458  or      eax, 80070000h
0x18003945d  test    eax, eax
0x18003945f  lea     r9, aFailedToUnregi; "Failed to unregister sdb: 0x%x"
0x180039466  mov     r8d, 3CBh
0x18003946c  jmp     short loc_1800394C2
0x18003946e  xor     ebx, ebx
0x180039470  jmp     short loc_1800394DC
0x180039472  jle     short loc_18003947C
0x180039474  movzx   eax, ax
0x180039477  or      eax, 80070000h
0x18003947c  lea     r9, aFailedToQueryI; "Failed to query installed sdb value: 0x"...
0x180039483  mov     r8d, 3A6h
0x180039489  jmp     short loc_1800394BB
0x18003948b  jle     short loc_180039495
0x18003948d  movzx   eax, ax
0x180039490  or      eax, 80070000h
0x180039495  lea     r9, aFailedToQueryI; "Failed to query installed sdb value: 0x"...
0x18003949c  mov     r8d, 398h
0x1800394a2  jmp     short loc_1800394BB
0x1800394a4  jle     short loc_1800394AE
0x1800394a6  movzx   eax, ax
0x1800394a9  or      eax, 80070000h
0x1800394ae  lea     r9, aFailedToOpenIn; "Failed to open installed sdb subkey: 0x"...
0x1800394b5  mov     r8d, 38Ah
0x1800394bb  mov     ebx, 80004005h
0x1800394c0  test    eax, eax
0x1800394c2  cmovns  eax, ebx
0x1800394c5  lea     rdx, aReregistersdb; "ReregisterSdb"
0x1800394cc  mov     ecx, 1
0x1800394d1  mov     dword ptr [rsp+70h+phkResult], eax
0x1800394d5  mov     ebx, eax
0x1800394d7  call    AslLogCallPrintf
0x1800394dc  mov     rcx, [rbp+hKey]; hKey
0x1800394e0  test    rcx, rcx
0x1800394e3  jz      short loc_1800394EB
0x1800394e5  call    cs:__imp_RegCloseKey
0x1800394eb  mov     eax, ebx
0x1800394ed  mov     rcx, [rbp+var_10]
0x1800394f1  xor     rcx, rsp; StackCookie
0x1800394f4  call    __security_check_cookie
0x1800394f9  add     rsp, 70h
0x1800394fd  pop     rdi
0x1800394fe  pop     rbx
0x1800394ff  pop     rbp
0x180039500  retn
```
