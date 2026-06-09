# GetSLSExpireSecsInADay(void)

- ea: `0x140037020`
- end: `0x1400370f3`
- name: `?GetSLSExpireSecsInADay@@YAKXZ`
- size: `211`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14003401c`

## callees

- `0x140003de4`
- `0x1400154b4`
- `0x1400178a4`
- `0x140037020`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400370a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400370a9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003706e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003706e`

## string_xrefs

- `0x140037060`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`

## pseudocode

```c
__int64 GetSLSExpireSecsInADay(void)
{
  unsigned int v1; // [rsp+40h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-20h] BYREF

  v1 = 86400;
  if ( (unsigned int)AreTestKeysAllowed() )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
            0,
            1u,
            &hKey) )
    {
      if ( !hKey )
        goto LABEL_8;
      if ( RegQueryDwordValue(hKey, L"SLSExpireSecsInADay", &v1) < 0 )
        v1 = 86400;
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
LABEL_8:
  WUTrace(0, 0, 4, 5, 0, L"GetSLSExpireSecsInADay SecsInADay = %d.");
  return v1;
}

```

## disassembly

```asm
0x140037020  sub     rsp, 68h
0x140037024  mov     rax, cs:__security_cookie
0x14003702b  xor     rax, rsp
0x14003702e  mov     [rsp+68h+var_18], rax
0x140037033  mov     [rsp+68h+var_28], 15180h
0x14003703b  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x140037040  test    eax, eax
0x140037042  jz      short loc_1400370AF
0x140037044  lea     rax, [rsp+68h+hKey]
0x140037049  mov     [rsp+68h+hKey], 0
0x140037052  mov     r9d, 1; samDesired
0x140037058  mov     [rsp+68h+phkResult], rax; phkResult
0x14003705d  xor     r8d, r8d; ulOptions
0x140037060  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140037067  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14003706e  call    cs:__imp_RegOpenKeyExW
0x140037074  test    eax, eax
0x140037076  jnz     short loc_14003709F
0x140037078  mov     rcx, [rsp+68h+hKey]; HKEY
0x14003707d  test    rcx, rcx
0x140037080  jz      short loc_1400370AF
0x140037082  lea     r8, [rsp+68h+var_28]; unsigned int *
0x140037087  lea     rdx, aSlsexpiresecsi; "SLSExpireSecsInADay"
0x14003708e  call    ?RegQueryDwordValue@@YAJPEAUHKEY__@@PEB_WPEAK@Z; RegQueryDwordValue(HKEY__ *,wchar_t const *,ulong *)
0x140037093  test    eax, eax
0x140037095  jns     short loc_14003709F
0x140037097  mov     [rsp+68h+var_28], 15180h
0x14003709f  mov     rcx, [rsp+68h+hKey]; hKey
0x1400370a4  test    rcx, rcx
0x1400370a7  jz      short loc_1400370AF
0x1400370a9  call    cs:__imp_RegCloseKey
0x1400370af  mov     eax, [rsp+68h+var_28]
0x1400370b3  xor     edx, edx
0x1400370b5  mov     [rsp+68h+var_38], eax
0x1400370b9  xor     ecx, ecx
0x1400370bb  lea     rax, aGetslsexpirese; "GetSLSExpireSecsInADay SecsInADay = %d."
0x1400370c2  mov     [rsp+68h+var_40], rax
0x1400370c7  lea     r9d, [rdx+5]
0x1400370cb  mov     [rsp+68h+phkResult], 0
0x1400370d4  lea     r8d, [rdx+4]
0x1400370d8  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1400370dd  mov     eax, [rsp+68h+var_28]
0x1400370e1  mov     rcx, [rsp+68h+var_18]
0x1400370e6  xor     rcx, rsp; StackCookie
0x1400370e9  call    __security_check_cookie
0x1400370ee  add     rsp, 68h
0x1400370f2  retn
```
