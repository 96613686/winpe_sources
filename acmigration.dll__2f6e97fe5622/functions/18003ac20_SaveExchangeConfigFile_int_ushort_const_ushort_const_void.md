# SaveExchangeConfigFile(int *,ushort const *,ushort const *,void *)

- ea: `0x18003ac20`
- end: `0x18003ad00`
- name: `?SaveExchangeConfigFile@@YAJPEAHPEBG1PEAX@Z`
- size: `224`
- prototype: `__int64 __fastcall(int *, const unsigned __int16 *, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config, installer_update`

## callees

- `0x180001cf0`
- `0x18003ac20`
- `0x1800543c0`

## import_xrefs

- `KERNEL32!CopyFileW` at `0x18003acb4`
- `KERNEL32!CopyFileW` at `0x18003acb4`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18003ac54`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18003ac85`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18003ac54`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18003ac85`
- `KERNEL32!GetLastError` at `0x18003ac5e`
- `KERNEL32!GetLastError` at `0x18003ac8f`
- `KERNEL32!GetLastError` at `0x18003acbe`
- `KERNEL32!GetLastError` at `0x18003ac5e`
- `KERNEL32!GetLastError` at `0x18003ac8f`
- `KERNEL32!GetLastError` at `0x18003acbe`

## string_xrefs

- `0x18003ac64`: `Failed to expand setup binary path. %d`
- `0x18003ac95`: `Failed to expand setup binary path. %d`
- `0x18003ac47`: `%windir%\System32\Inetsrv\Config\Schema\wsmanconfig_schema.xml`
- `0x18003acd1`: `SaveExchangeConfigFile`
- `0x18003ac7e`: `%windir%\System32\Inetsrv\Config\Schema\wsmanconfig_schema.xml.mig`
- `0x18003acc4`: `Failed to save config file. %d`

## pseudocode

```c
__int64 __fastcall SaveExchangeConfigFile(int *a1, const unsigned __int16 *a2, const unsigned __int16 *a3, void *a4)
{
  DWORD LastError; // eax
  const char *v5; // r9
  __int64 v6; // r8
  DWORD v8; // [rsp+20h] [rbp-448h]
  WCHAR NewFileName[264]; // [rsp+30h] [rbp-438h] BYREF
  WCHAR Dst[264]; // [rsp+240h] [rbp-228h] BYREF

  *a1 = 0;
  if ( !ExpandEnvironmentStringsW(L"%windir%\\System32\\Inetsrv\\Config\\Schema\\wsmanconfig_schema.xml", Dst, 0x103u) )
  {
    LastError = GetLastError();
    v5 = "Failed to expand setup binary path. %d";
    v6 = 81;
LABEL_7:
    v8 = LastError;
    AslLogCallPrintf(1, "SaveExchangeConfigFile", v6, v5, v8);
    return 0;
  }
  if ( !ExpandEnvironmentStringsW(
          L"%windir%\\System32\\Inetsrv\\Config\\Schema\\wsmanconfig_schema.xml.mig",
          NewFileName,
          0x103u) )
  {
    LastError = GetLastError();
    v5 = "Failed to expand setup binary path. %d";
    v6 = 90;
    goto LABEL_7;
  }
  if ( !CopyFileW(Dst, NewFileName, 0) )
  {
    LastError = GetLastError();
    v5 = "Failed to save config file. %d";
    v6 = 97;
    goto LABEL_7;
  }
  return 0;
}

```

## disassembly

```asm
0x18003ac20  sub     rsp, 468h
0x18003ac27  mov     rax, cs:__security_cookie
0x18003ac2e  xor     rax, rsp
0x18003ac31  mov     [rsp+468h+var_18], rax
0x18003ac39  mov     dword ptr [rcx], 0
0x18003ac3f  lea     rdx, [rsp+468h+Dst]; lpDst
0x18003ac47  lea     rcx, aWindirSystem32; "%windir%\\System32\\Inetsrv\\Config\\Sc"...
0x18003ac4e  mov     r8d, 103h; nSize
0x18003ac54  call    cs:__imp_ExpandEnvironmentStringsW
0x18003ac5a  test    eax, eax
0x18003ac5c  jnz     short loc_18003AC73
0x18003ac5e  call    cs:__imp_GetLastError
0x18003ac64  lea     r9, aFailedToExpand_1; "Failed to expand setup binary path. %d"
0x18003ac6b  mov     r8d, 51h ; 'Q'
0x18003ac71  jmp     short loc_18003ACD1
0x18003ac73  mov     r8d, 103h; nSize
0x18003ac79  lea     rdx, [rsp+468h+NewFileName]; lpDst
0x18003ac7e  lea     rcx, aWindirSystem32_2; "%windir%\\System32\\Inetsrv\\Config\\Sc"...
0x18003ac85  call    cs:__imp_ExpandEnvironmentStringsW
0x18003ac8b  test    eax, eax
0x18003ac8d  jnz     short loc_18003ACA4
0x18003ac8f  call    cs:__imp_GetLastError
0x18003ac95  lea     r9, aFailedToExpand_1; "Failed to expand setup binary path. %d"
0x18003ac9c  mov     r8d, 5Ah ; 'Z'
0x18003aca2  jmp     short loc_18003ACD1
0x18003aca4  xor     r8d, r8d; bFailIfExists
0x18003aca7  lea     rdx, [rsp+468h+NewFileName]; lpNewFileName
0x18003acac  lea     rcx, [rsp+468h+Dst]; lpExistingFileName
0x18003acb4  call    cs:__imp_CopyFileW
0x18003acba  test    eax, eax
0x18003acbc  jnz     short loc_18003ACE6
0x18003acbe  call    cs:__imp_GetLastError
0x18003acc4  lea     r9, aFailedToSaveCo; "Failed to save config file. %d"
0x18003accb  mov     r8d, 61h ; 'a'
0x18003acd1  lea     rdx, aSaveexchangeco; "SaveExchangeConfigFile"
0x18003acd8  mov     [rsp+468h+var_448], eax
0x18003acdc  mov     ecx, 1
0x18003ace1  call    AslLogCallPrintf
0x18003ace6  xor     eax, eax
0x18003ace8  mov     rcx, [rsp+468h+var_18]
0x18003acf0  xor     rcx, rsp; StackCookie
0x18003acf3  call    __security_check_cookie
0x18003acf8  add     rsp, 468h
0x18003acff  retn
```
