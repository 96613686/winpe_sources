# CheckTestCert

- ea: `0x180056678`
- end: `0x180056782`
- name: `CheckTestCert`
- size: `266`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180056bc8`
- `0x180056ef4`
- `0x180057254`

## callees

- `0x1800110fc`
- `0x18005588c`
- `0x180056678`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800566d1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800566d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005675c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005675c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180056715`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180056715`

## string_xrefs

- `0x1800566c3`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x180056721`: `Test certificate found in registry.`

## pseudocode

```c
__int64 __fastcall CheckTestCert(__int64 a1)
{
  unsigned int v2; // ebx
  __int64 v4; // [rsp+30h] [rbp-40h] BYREF
  BYTE *v5; // [rsp+38h] [rbp-38h]
  DWORD cbData; // [rsp+40h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-28h] BYREF
  BYTE Data[24]; // [rsp+50h] [rbp-20h] BYREF

  v2 = -2145078525;
  if ( a1 )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
            0,
            1u,
            &hKey) )
    {
      v5 = Data;
      cbData = 20;
      v4 = 1;
      if ( RegQueryValueExW(hKey, L"TestCert", 0, 0, Data, &cbData) >= 0 )
      {
        WUTrace(0, 0, 32, 4, 0, L"Test certificate found in registry.", v4, v5);
        v2 = VerifyKnownCerts(a1, &v4);
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  return v2;
}

```

## disassembly

```asm
0x180056678  mov     [rsp-8+arg_8], rbx
0x18005667d  mov     [rsp-8+arg_10], rdi
0x180056682  push    rbp
0x180056683  mov     rbp, rsp
0x180056686  sub     rsp, 70h
0x18005668a  mov     rax, cs:__security_cookie
0x180056691  xor     rax, rsp
0x180056694  mov     [rbp+var_8], rax
0x180056698  mov     rdi, rcx
0x18005669b  mov     ebx, 8024B303h
0x1800566a0  test    rcx, rcx
0x1800566a3  jz      loc_180056762
0x1800566a9  lea     rax, [rbp+hKey]
0x1800566ad  mov     [rbp+hKey], 0
0x1800566b5  mov     r9d, 1; samDesired
0x1800566bb  mov     [rsp+70h+phkResult], rax; phkResult
0x1800566c0  xor     r8d, r8d; ulOptions
0x1800566c3  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800566ca  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800566d1  call    cs:__imp_RegOpenKeyExW
0x1800566d7  test    eax, eax
0x1800566d9  jnz     short loc_180056753
0x1800566db  mov     rcx, [rbp+hKey]; hKey
0x1800566df  lea     rax, [rbp+Data]
0x1800566e3  mov     [rbp+var_38], rax
0x1800566e7  lea     rdx, ValueName; "TestCert"
0x1800566ee  lea     rax, [rbp+cbData]
0x1800566f2  mov     [rbp+cbData], 14h
0x1800566f9  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1800566fe  xor     r9d, r9d; lpType
0x180056701  lea     rax, [rbp+Data]
0x180056705  mov     [rbp+var_40], 1
0x18005670d  xor     r8d, r8d; lpReserved
0x180056710  mov     [rsp+70h+phkResult], rax; lpData
0x180056715  call    cs:__imp_RegQueryValueExW
0x18005671b  test    eax, eax
0x18005671d  js      short loc_180056753
0x18005671f  xor     edx, edx
0x180056721  lea     rax, aTestCertificat; "Test certificate found in registry."
0x180056728  mov     [rsp+70h+lpcbData], rax
0x18005672d  xor     ecx, ecx
0x18005672f  mov     [rsp+70h+phkResult], 0
0x180056738  lea     r9d, [rdx+4]
0x18005673c  lea     r8d, [rdx+20h]
0x180056740  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180056745  lea     rdx, [rbp+var_40]
0x180056749  mov     rcx, rdi
0x18005674c  call    VerifyKnownCerts
0x180056751  mov     ebx, eax
0x180056753  mov     rcx, [rbp+hKey]; hKey
0x180056757  test    rcx, rcx
0x18005675a  jz      short loc_180056762
0x18005675c  call    cs:__imp_RegCloseKey
0x180056762  mov     eax, ebx
0x180056764  mov     rcx, [rbp+var_8]
0x180056768  xor     rcx, rsp; StackCookie
0x18005676b  call    __security_check_cookie
0x180056770  lea     r11, [rsp+70h+var_s0]
0x180056775  mov     rbx, [r11+18h]
0x180056779  mov     rdi, [r11+20h]
0x18005677d  mov     rsp, r11
0x180056780  pop     rbp
0x180056781  retn
```
