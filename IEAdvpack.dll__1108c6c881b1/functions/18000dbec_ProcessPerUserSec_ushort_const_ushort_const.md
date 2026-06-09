# ProcessPerUserSec(ushort const *,ushort const *)

- ea: `0x18000dbec`
- end: `0x18000de28`
- name: `?ProcessPerUserSec@@YAJPEBG0@Z`
- size: `572`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpAppName)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180004880`

## callees

- `0x180006d24`
- `0x180007454`
- `0x18000c574`
- `0x18000dbec`
- `0x180010d50`
- `0x18001b94e`
- `0x18001b980`

## string_xrefs

- `0x18000dc3a`: `PerUserInstall`
- `0x18000dc75`: `Inf=%1, InstallSec=%2, PerUserInstall=%3\n`
- `0x18000dcbc`: `IsInstalled`
- `0x18000dcdb`: `RollbackUninstall`
- `0x18000dd67`: `StubPath`
- `0x18000ddc5`: `ComponentID`

## pseudocode

```c
__int64 __fastcall ProcessPerUserSec(const unsigned __int16 *a1, LPCWSTR lpAppName)
{
  unsigned int v4; // edi
  unsigned int v6[4]; // [rsp+30h] [rbp-D0h] BYREF
  PERUSERSECTIONW pPerUser; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Section[264]; // [rsp+B40h] [rbp+A40h] BYREF

  v4 = 0;
  memset_0(&pPerUser, 0, sizeof(pPerUser));
  if ( (int)GetTranslatedString(a1, lpAppName, L"PerUserInstall", Section, 0x104u, 0) >= 0 )
  {
    AdvWriteToLog(L"ProcessPerUserSec: \r\n");
    AdvWriteToLog(L"Inf=%1, InstallSec=%2, PerUserInstall=%3\r\n", a1, lpAppName, Section);
    if ( (int)GetTranslatedString(a1, Section, L"GUID", pPerUser.szGUID, 0x3Bu, v6) < 0 )
    {
      AdvWriteToLog(L"Failure: No GUID specified\r\n");
    }
    else
    {
      pPerUser.dwIsInstalled = GetTranslatedInt(a1, Section, L"IsInstalled", 0x3E7u);
      pPerUser.bRollback = GetTranslatedInt(a1, Section, L"RollbackUninstall", 0);
      GetTranslatedString(a1, Section, L"DisplayName", pPerUser.szDispName, 0x80u, v6);
      GetTranslatedString(a1, Section, L"Version", pPerUser.szVersion, 0x20u, v6);
      GetTranslatedString(a1, Section, L"StubPath", pPerUser.szStub, 0x410u, v6);
      GetTranslatedString(a1, Section, L"Locale", pPerUser.szLocale, 0xAu, v6);
      GetTranslatedString(a1, Section, L"ComponentID", pPerUser.szCompID, 0x80u, v6);
      v4 = SetPerUserSecValuesW(&pPerUser);
    }
    AdvWriteToLog(L"ProcessPerUserSec: End hr=0x%1!x!\r\n", v4);
  }
  return v4;
}

```

## disassembly

```asm
0x18000dbec  mov     [rsp-8+arg_10], rbx
0x18000dbf1  push    rbp
0x18000dbf2  push    rsi
0x18000dbf3  push    rdi
0x18000dbf4  lea     rbp, [rsp-0C60h]
0x18000dbfc  sub     rsp, 0D60h
0x18000dc03  mov     rax, cs:__security_cookie
0x18000dc0a  xor     rax, rsp
0x18000dc0d  mov     [rbp+0C70h+var_20], rax
0x18000dc14  mov     rsi, rdx
0x18000dc17  mov     rbx, rcx
0x18000dc1a  xor     edx, edx; Val
0x18000dc1c  lea     rcx, [rsp+0D70h+pPerUser]; void *
0x18000dc21  mov     r8d, 0AF4h; Size
0x18000dc27  xor     edi, edi
0x18000dc29  call    memset_0
0x18000dc2e  lea     r9, [rbp+0C70h+Section]; unsigned __int16 *
0x18000dc35  mov     [rsp+0D70h+var_D48], rdi; unsigned int *
0x18000dc3a  lea     r8, aPeruserinstall; "PerUserInstall"
0x18000dc41  mov     [rsp+0D70h+var_D50], 104h; unsigned int
0x18000dc49  mov     rdx, rsi; lpAppName
0x18000dc4c  mov     rcx, rbx; unsigned __int16 *
0x18000dc4f  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x18000dc54  test    eax, eax
0x18000dc56  js      loc_18000DE04
0x18000dc5c  lea     rcx, aProcessperuser; "ProcessPerUserSec: \r\n"
0x18000dc63  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18000dc68  lea     r9, [rbp+0C70h+Section]
0x18000dc6f  mov     r8, rsi
0x18000dc72  mov     rdx, rbx
0x18000dc75  lea     rcx, aInf1Installsec; "Inf=%1, InstallSec=%2, PerUserInstall=%"...
0x18000dc7c  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18000dc81  lea     rax, [rsp+0D70h+var_D40]
0x18000dc86  mov     rcx, rbx; unsigned __int16 *
0x18000dc89  mov     [rsp+0D70h+var_D48], rax; unsigned int *
0x18000dc8e  lea     r9, [rsp+0D70h+pPerUser]; unsigned __int16 *
0x18000dc93  lea     r8, aGuid; "GUID"
0x18000dc9a  mov     [rsp+0D70h+var_D50], 3Bh ; ';'; unsigned int
0x18000dca2  lea     rdx, [rbp+0C70h+Section]; lpAppName
0x18000dca9  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x18000dcae  test    eax, eax
0x18000dcb0  js      loc_18000DDEA
0x18000dcb6  mov     r9d, 3E7h; nDefault
0x18000dcbc  lea     r8, aIsinstalled; "IsInstalled"
0x18000dcc3  lea     rdx, [rbp+0C70h+Section]; Section
0x18000dcca  mov     rcx, rbx; unsigned __int16 *
0x18000dccd  call    ?GetTranslatedInt@@YAKPEBG00K@Z; GetTranslatedInt(ushort const *,ushort const *,ushort const *,ulong)
0x18000dcd2  xor     r9d, r9d; nDefault
0x18000dcd5  mov     [rbp+0C70h+pPerUser.dwIsInstalled], eax
0x18000dcdb  lea     r8, aRollbackuninst; "RollbackUninstall"
0x18000dce2  mov     rcx, rbx; unsigned __int16 *
0x18000dce5  lea     rdx, [rbp+0C70h+Section]; Section
0x18000dcec  call    ?GetTranslatedInt@@YAKPEBG00K@Z; GetTranslatedInt(ushort const *,ushort const *,ushort const *,ulong)
0x18000dcf1  mov     [rbp+0C70h+pPerUser.bRollback], eax
0x18000dcf7  lea     r9, [rbp+0C70h+pPerUser.szDispName]; unsigned __int16 *
0x18000dcfb  lea     rax, [rsp+0D70h+var_D40]
0x18000dd00  mov     edi, 80h
0x18000dd05  mov     [rsp+0D70h+var_D48], rax; unsigned int *
0x18000dd0a  lea     r8, aDisplayname; "DisplayName"
0x18000dd11  lea     rdx, [rbp+0C70h+Section]; lpAppName
0x18000dd18  mov     [rsp+0D70h+var_D50], edi; unsigned int
0x18000dd1c  mov     rcx, rbx; unsigned __int16 *
0x18000dd1f  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x18000dd24  lea     rax, [rsp+0D70h+var_D40]
0x18000dd29  mov     rcx, rbx; unsigned __int16 *
0x18000dd2c  mov     [rsp+0D70h+var_D48], rax; unsigned int *
0x18000dd31  lea     r9, [rbp+0C70h+pPerUser.szVersion]; unsigned __int16 *
0x18000dd38  lea     r8, aVersion; "Version"
0x18000dd3f  mov     [rsp+0D70h+var_D50], 20h ; ' '; unsigned int
0x18000dd47  lea     rdx, [rbp+0C70h+Section]; lpAppName
0x18000dd4e  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x18000dd53  lea     rax, [rsp+0D70h+var_D40]
0x18000dd58  mov     rcx, rbx; unsigned __int16 *
0x18000dd5b  mov     [rsp+0D70h+var_D48], rax; unsigned int *
0x18000dd60  lea     r9, [rbp+0C70h+pPerUser.szStub]; unsigned __int16 *
0x18000dd67  lea     r8, aStubpath; "StubPath"
0x18000dd6e  mov     [rsp+0D70h+var_D50], 410h; unsigned int
0x18000dd76  lea     rdx, [rbp+0C70h+Section]; lpAppName
0x18000dd7d  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x18000dd82  lea     rax, [rsp+0D70h+var_D40]
0x18000dd87  mov     rcx, rbx; unsigned __int16 *
0x18000dd8a  mov     [rsp+0D70h+var_D48], rax; unsigned int *
0x18000dd8f  lea     r9, [rbp+0C70h+pPerUser.szLocale]; unsigned __int16 *
0x18000dd96  lea     r8, aLocale; "Locale"
0x18000dd9d  mov     [rsp+0D70h+var_D50], 0Ah; unsigned int
0x18000dda5  lea     rdx, [rbp+0C70h+Section]; lpAppName
0x18000ddac  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x18000ddb1  lea     rax, [rsp+0D70h+var_D40]
0x18000ddb6  mov     rcx, rbx; unsigned __int16 *
0x18000ddb9  mov     [rsp+0D70h+var_D48], rax; unsigned int *
0x18000ddbe  lea     r9, [rbp+0C70h+pPerUser.szCompID]; unsigned __int16 *
0x18000ddc5  lea     r8, aComponentid; "ComponentID"
0x18000ddcc  mov     [rsp+0D70h+var_D50], edi; unsigned int
0x18000ddd0  lea     rdx, [rbp+0C70h+Section]; lpAppName
0x18000ddd7  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x18000dddc  lea     rcx, [rsp+0D70h+pPerUser]; pPerUser
0x18000dde1  call    SetPerUserSecValuesW
0x18000dde6  mov     edi, eax
0x18000dde8  jmp     short loc_18000DDF6
0x18000ddea  lea     rcx, aFailureNoGuidS; "Failure: No GUID specified\r\n"
0x18000ddf1  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18000ddf6  mov     edx, edi
0x18000ddf8  lea     rcx, aProcessperuser_0; "ProcessPerUserSec: End hr=0x%1!x!\r\n"
0x18000ddff  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18000de04  mov     eax, edi
0x18000de06  mov     rcx, [rbp+0C70h+var_20]
0x18000de0d  xor     rcx, rsp; StackCookie
0x18000de10  call    __security_check_cookie
0x18000de15  mov     rbx, [rsp+0D70h+arg_10]
0x18000de1d  add     rsp, 0D60h
0x18000de24  pop     rdi
0x18000de25  pop     rsi
0x18000de26  pop     rbp
0x18000de27  retn
```
