# AllowUrlForBrokeredReadInternal(ushort const *)

- ea: `0x180024a08`
- end: `0x180024b27`
- name: `?AllowUrlForBrokeredReadInternal@@YAJPEBG@Z`
- size: `287`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x18001c950`
- `0x18001c9b0`

## callees

- `0x180002ce0`
- `0x180024a08`

## import_xrefs

- `iertutil!__imp_SetExtValue` at `0x180024a5c`
- `iertutil!__imp_SetExtValue` at `0x180024af5`
- `iertutil!__imp_SetExtValue` at `0x180024a5c`
- `iertutil!__imp_SetExtValue` at `0x180024af5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024ab8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024ab8`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180024aad`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180024aad`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024a8d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180024a8d`

## pseudocode

```c
__int64 __fastcall AllowUrlForBrokeredReadInternal(LPCWSTR lpFileName)
{
  __int64 result; // rax
  HANDLE FileW; // rax
  void *v4; // rdi
  DWORD FinalPathNameByHandleW; // ebx
  _DWORD v6[4]; // [rsp+40h] [rbp-238h] BYREF
  WCHAR szFilePath[264]; // [rsp+50h] [rbp-228h] BYREF

  v6[0] = 1;
  result = SetExtValue((__int64 *)SettingStore::IEVALUE_BrokeredRead_DesktopUrlId, 2, 8, v6, 4, 1, lpFileName);
  if ( !(_DWORD)result )
  {
    FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0, 0);
    v4 = FileW;
    if ( FileW == (HANDLE)-1LL )
      return 2147500037LL;
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, szFilePath, 0x104u, 0);
    CloseHandle(v4);
    if ( FinalPathNameByHandleW - 1 > 0x102 )
    {
      return 2147500037LL;
    }
    else
    {
      v6[0] = 1;
      return SetExtValue((__int64 *)SettingStore::IEVALUE_BrokeredRead_DesktopUrlId, 2, 8, v6, 4, 1, szFilePath);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180024a08  mov     [rsp+arg_8], rbx
0x180024a0d  mov     [rsp+arg_10], rsi
0x180024a12  push    rdi
0x180024a13  sub     rsp, 270h
0x180024a1a  mov     rax, cs:__security_cookie
0x180024a21  xor     rax, rsp
0x180024a24  mov     [rsp+278h+var_18], rax
0x180024a2c  mov     esi, 1
0x180024a31  mov     [rsp+278h+hTemplateFile], rcx
0x180024a36  mov     rbx, rcx
0x180024a39  mov     [rsp+278h+dwFlagsAndAttributes], esi
0x180024a3d  mov     rcx, cs:?IEVALUE_BrokeredRead_DesktopUrlId@SettingStore@@3U?$EXTVALUE1ID@K@1@B; SettingStore::EXTVALUE1ID<ulong> const SettingStore::IEVALUE_BrokeredRead_DesktopUrlId
0x180024a44  lea     r9, [rsp+278h+var_238]
0x180024a49  mov     [rsp+278h+var_238], esi
0x180024a4d  lea     edx, [rsi+1]
0x180024a50  mov     [rsp+278h+dwCreationDisposition], 4
0x180024a58  lea     r8d, [rsi+7]
0x180024a5c  call    cs:__imp_SetExtValue
0x180024a62  test    eax, eax
0x180024a64  jnz     loc_180024B02
0x180024a6a  mov     [rsp+278h+hTemplateFile], 0; hTemplateFile
0x180024a73  xor     r9d, r9d; lpSecurityAttributes
0x180024a76  mov     [rsp+278h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180024a7a  mov     r8d, esi; dwShareMode
0x180024a7d  mov     edx, 80000000h; dwDesiredAccess
0x180024a82  mov     [rsp+278h+dwCreationDisposition], 3; dwCreationDisposition
0x180024a8a  mov     rcx, rbx; lpFileName
0x180024a8d  call    cs:__imp_CreateFileW
0x180024a93  mov     rdi, rax
0x180024a96  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180024a9a  jz      short loc_180024AFD
0x180024a9c  xor     r9d, r9d; dwFlags
0x180024a9f  lea     rdx, [rsp+278h+szFilePath]; lpszFilePath
0x180024aa4  mov     r8d, 104h; cchFilePath
0x180024aaa  mov     rcx, rax; hFile
0x180024aad  call    cs:__imp_GetFinalPathNameByHandleW
0x180024ab3  mov     rcx, rdi; hObject
0x180024ab6  mov     ebx, eax
0x180024ab8  call    cs:__imp_CloseHandle
0x180024abe  lea     eax, [rbx-1]
0x180024ac1  cmp     eax, 102h
0x180024ac6  ja      short loc_180024AFD
0x180024ac8  mov     rcx, cs:?IEVALUE_BrokeredRead_DesktopUrlId@SettingStore@@3U?$EXTVALUE1ID@K@1@B; SettingStore::EXTVALUE1ID<ulong> const SettingStore::IEVALUE_BrokeredRead_DesktopUrlId
0x180024acf  lea     rax, [rsp+278h+szFilePath]
0x180024ad4  mov     [rsp+278h+hTemplateFile], rax
0x180024ad9  lea     r9, [rsp+278h+var_238]
0x180024ade  mov     [rsp+278h+dwFlagsAndAttributes], esi
0x180024ae2  lea     edx, [rsi+1]
0x180024ae5  lea     r8d, [rsi+7]
0x180024ae9  mov     [rsp+278h+dwCreationDisposition], 4
0x180024af1  mov     [rsp+278h+var_238], esi
0x180024af5  call    cs:__imp_SetExtValue
0x180024afb  jmp     short loc_180024B02
0x180024afd  mov     eax, 80004005h
0x180024b02  mov     rcx, [rsp+278h+var_18]
0x180024b0a  xor     rcx, rsp; StackCookie
0x180024b0d  call    __security_check_cookie
0x180024b12  lea     r11, [rsp+278h+var_8]
0x180024b1a  mov     rbx, [r11+18h]
0x180024b1e  mov     rsi, [r11+20h]
0x180024b22  mov     rsp, r11
0x180024b25  pop     rdi
0x180024b26  retn
```
