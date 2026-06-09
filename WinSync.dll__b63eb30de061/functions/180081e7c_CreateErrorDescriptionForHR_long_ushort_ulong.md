# CreateErrorDescriptionForHR(long,ushort *,ulong)

- ea: `0x180081e7c`
- end: `0x180081f62`
- name: `?CreateErrorDescriptionForHR@@YAJJPEAGK@Z`
- size: `230`
- prototype: `__int64 __fastcall(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180081f68`

## callees

- `0x180081e7c`
- `0x180092bc0`
- `0x180093270`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081f16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081f16`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180081f0c`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180081f0c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180081f3c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180081f3c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180081ede`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180081ede`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180081ebf`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180081ebf`

## pseudocode

```c
__int64 __fastcall CreateErrorDescriptionForHR(DWORD dwMessageId, LPWSTR lpBuffer, DWORD nSize)
{
  unsigned int v6; // edi
  HINSTANCE v7; // rbx
  LANGID UserDefaultUILanguage; // ax
  __int64 v9; // r8
  HMODULE LibraryW; // rax
  HMODULE v11; // rbx
  DWORD v12; // eax
  signed int LastError; // eax
  WCHAR LibFileName[264]; // [rsp+40h] [rbp-248h] BYREF

  v6 = 1;
  if ( dwMessageId + 2147217408 <= 0x2A )
  {
    v7 = g_hInstance;
    UserDefaultUILanguage = GetUserDefaultUILanguage();
    if ( (unsigned __int8)GetResourceLibraryPathInternal(v7, UserDefaultUILanguage, v9, LibFileName) )
    {
      LibraryW = LoadLibraryW(LibFileName);
      v11 = LibraryW;
      if ( LibraryW )
      {
        v12 = FormatMessageW(0x800u, LibraryW, dwMessageId, 0, lpBuffer, nSize, 0);
        if ( v12 )
        {
          v6 = 0;
          if ( v12 == nSize )
            v6 = -2147024662;
        }
        else
        {
          LastError = GetLastError();
          v6 = LastError;
          if ( LastError > 0 )
            v6 = (unsigned __int16)LastError | 0x80070000;
        }
        FreeLibrary(v11);
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180081e7c  push    rbx
0x180081e7e  push    rbp
0x180081e7f  push    rsi
0x180081e80  push    rdi
0x180081e81  push    r14
0x180081e83  sub     rsp, 260h
0x180081e8a  mov     rax, cs:__security_cookie
0x180081e91  xor     rax, rsp
0x180081e94  mov     [rsp+288h+var_38], rax
0x180081e9c  lea     eax, [rcx+7FFBF000h]
0x180081ea2  mov     esi, r8d
0x180081ea5  mov     r14, rdx
0x180081ea8  mov     ebp, ecx
0x180081eaa  mov     edi, 1
0x180081eaf  cmp     eax, 2Ah ; '*'
0x180081eb2  ja      loc_180081F42
0x180081eb8  mov     rbx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x180081ebf  call    cs:__imp_GetUserDefaultUILanguage
0x180081ec5  lea     r9, [rsp+288h+LibFileName]
0x180081eca  mov     rcx, rbx
0x180081ecd  movzx   edx, ax
0x180081ed0  call    GetResourceLibraryPathInternal
0x180081ed5  test    al, al
0x180081ed7  jz      short loc_180081F42
0x180081ed9  lea     rcx, [rsp+288h+LibFileName]; lpLibFileName
0x180081ede  call    cs:__imp_LoadLibraryW
0x180081ee4  mov     rbx, rax
0x180081ee7  test    rax, rax
0x180081eea  jz      short loc_180081F42
0x180081eec  mov     [rsp+288h+Arguments], 0; Arguments
0x180081ef5  xor     r9d, r9d; dwLanguageId
0x180081ef8  mov     [rsp+288h+nSize], esi; nSize
0x180081efc  mov     r8d, ebp; dwMessageId
0x180081eff  mov     rdx, rax; lpSource
0x180081f02  mov     [rsp+288h+lpBuffer], r14; lpBuffer
0x180081f07  mov     ecx, 800h; dwFlags
0x180081f0c  call    cs:__imp_FormatMessageW
0x180081f12  test    eax, eax
0x180081f14  jnz     short loc_180081F2D
0x180081f16  call    cs:__imp_GetLastError
0x180081f1c  mov     edi, eax
0x180081f1e  test    eax, eax
0x180081f20  jle     short loc_180081F39
0x180081f22  movzx   edi, ax
0x180081f25  or      edi, 80070000h
0x180081f2b  jmp     short loc_180081F39
0x180081f2d  xor     edi, edi
0x180081f2f  mov     ecx, 800700EAh
0x180081f34  cmp     eax, esi
0x180081f36  cmovz   edi, ecx
0x180081f39  mov     rcx, rbx; hLibModule
0x180081f3c  call    cs:__imp_FreeLibrary
0x180081f42  mov     eax, edi
0x180081f44  mov     rcx, [rsp+288h+var_38]
0x180081f4c  xor     rcx, rsp; StackCookie
0x180081f4f  call    __security_check_cookie
0x180081f54  add     rsp, 260h
0x180081f5b  pop     r14
0x180081f5d  pop     rdi
0x180081f5e  pop     rsi
0x180081f5f  pop     rbp
0x180081f60  pop     rbx
0x180081f61  retn
```
