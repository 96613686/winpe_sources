# CheckTestCert

- ea: `0x14002bb18`
- end: `0x14002bc22`
- name: `CheckTestCert`
- size: `266`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14002c094`
- `0x14002c3c4`
- `0x14002cef0`

## callees

- `0x1400154b4`
- `0x14002ad38`
- `0x14002bb18`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002bbfc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002bbfc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002bb71`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002bb71`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14002bbb5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14002bbb5`

## string_xrefs

- `0x14002bb63`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x14002bbc1`: `Test certificate found in registry.`

## pseudocode

```c
__int64 __fastcall CheckTestCert(__int64 a1)
{
  unsigned int v2; // ebx
  _QWORD v4[2]; // [rsp+30h] [rbp-40h] BYREF
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
      v4[1] = Data;
      cbData = 20;
      v4[0] = 1;
      if ( RegQueryValueExW(hKey, L"TestCert", 0, 0, Data, &cbData) >= 0 )
      {
        WUTrace(0, 0, 32, 4, 0, L"Test certificate found in registry.");
        v2 = VerifyKnownCerts(a1, v4);
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
0x14002bb18  mov     [rsp-8+arg_8], rbx
0x14002bb1d  mov     [rsp-8+arg_10], rdi
0x14002bb22  push    rbp
0x14002bb23  mov     rbp, rsp
0x14002bb26  sub     rsp, 70h
0x14002bb2a  mov     rax, cs:__security_cookie
0x14002bb31  xor     rax, rsp
0x14002bb34  mov     [rbp+var_8], rax
0x14002bb38  mov     rdi, rcx
0x14002bb3b  mov     ebx, 8024B303h
0x14002bb40  test    rcx, rcx
0x14002bb43  jz      loc_14002BC02
0x14002bb49  lea     rax, [rbp+hKey]
0x14002bb4d  mov     [rbp+hKey], 0
0x14002bb55  mov     r9d, 1; samDesired
0x14002bb5b  mov     [rsp+70h+phkResult], rax; phkResult
0x14002bb60  xor     r8d, r8d; ulOptions
0x14002bb63  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14002bb6a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14002bb71  call    cs:__imp_RegOpenKeyExW
0x14002bb77  test    eax, eax
0x14002bb79  jnz     short loc_14002BBF3
0x14002bb7b  mov     rcx, [rbp+hKey]; hKey
0x14002bb7f  lea     rax, [rbp+Data]
0x14002bb83  mov     [rbp+var_38], rax
0x14002bb87  lea     rdx, aTestcert; "TestCert"
0x14002bb8e  lea     rax, [rbp+cbData]
0x14002bb92  mov     [rbp+cbData], 14h
0x14002bb99  mov     [rsp+70h+lpcbData], rax; lpcbData
0x14002bb9e  xor     r9d, r9d; lpType
0x14002bba1  lea     rax, [rbp+Data]
0x14002bba5  mov     [rbp+var_40], 1
0x14002bbad  xor     r8d, r8d; lpReserved
0x14002bbb0  mov     [rsp+70h+phkResult], rax; lpData
0x14002bbb5  call    cs:__imp_RegQueryValueExW
0x14002bbbb  test    eax, eax
0x14002bbbd  js      short loc_14002BBF3
0x14002bbbf  xor     edx, edx
0x14002bbc1  lea     rax, aTestCertificat; "Test certificate found in registry."
0x14002bbc8  mov     [rsp+70h+lpcbData], rax
0x14002bbcd  xor     ecx, ecx
0x14002bbcf  mov     [rsp+70h+phkResult], 0
0x14002bbd8  lea     r9d, [rdx+4]
0x14002bbdc  lea     r8d, [rdx+20h]
0x14002bbe0  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14002bbe5  lea     rdx, [rbp+var_40]
0x14002bbe9  mov     rcx, rdi
0x14002bbec  call    VerifyKnownCerts
0x14002bbf1  mov     ebx, eax
0x14002bbf3  mov     rcx, [rbp+hKey]; hKey
0x14002bbf7  test    rcx, rcx
0x14002bbfa  jz      short loc_14002BC02
0x14002bbfc  call    cs:__imp_RegCloseKey
0x14002bc02  mov     eax, ebx
0x14002bc04  mov     rcx, [rbp+var_8]
0x14002bc08  xor     rcx, rsp; StackCookie
0x14002bc0b  call    __security_check_cookie
0x14002bc10  lea     r11, [rsp+70h+var_s0]
0x14002bc15  mov     rbx, [r11+18h]
0x14002bc19  mov     rdi, [r11+20h]
0x14002bc1d  mov     rsp, r11
0x14002bc20  pop     rbp
0x14002bc21  retn
```
