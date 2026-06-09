# CInternetException::GetErrorMessage(ushort *,uint,uint *)

- ea: `0x18006ea20`
- end: `0x18006eb97`
- name: `?GetErrorMessage@CInternetException@@UEAAHPEAGIPEAI@Z`
- size: `375`
- prototype: `int(CInternetException *__hidden this, unsigned __int16 *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18006ea20`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18006eb50`
- `msvcrt!wcsncpy_s` at `0x18006eb50`
- `msvcrt!wcscpy_s` at `0x18006eb6b`
- `msvcrt!wcscpy_s` at `0x18006eb6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006eb15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006eb15`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006ea6d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006ea6d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18006eaa4`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18006ead5`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18006eaa4`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18006ead5`
- `KERNEL32!LocalAlloc` at `0x18006eb29`
- `KERNEL32!LocalAlloc` at `0x18006eb29`
- `KERNEL32!LocalFree` at `0x18006eb59`
- `KERNEL32!LocalFree` at `0x18006eb7a`
- `KERNEL32!LocalFree` at `0x18006eb59`
- `KERNEL32!LocalFree` at `0x18006eb7a`
- `WININET!InternetGetLastResponseInfoW` at `0x18006eb0b`
- `WININET!InternetGetLastResponseInfoW` at `0x18006eb3d`
- `WININET!InternetGetLastResponseInfoW` at `0x18006eb0b`
- `WININET!InternetGetLastResponseInfoW` at `0x18006eb3d`

## string_xrefs

- `0x18006ea66`: `WININET.DLL`

## pseudocode

```c
__int64 __fastcall CInternetException::GetErrorMessage(
        CInternetException *this,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned int *a4)
{
  rsize_t v4; // r14
  HMODULE Library; // rax
  DWORD *v9; // rdi
  DWORD v10; // ebx
  WCHAR *v11; // rbx
  WCHAR Buffer[4]; // [rsp+40h] [rbp-10h] BYREF
  DWORD dwBufferLength; // [rsp+78h] [rbp+28h] BYREF
  DWORD dwError; // [rsp+88h] [rbp+38h] BYREF

  v4 = a3;
  if ( a4 )
    *a4 = 0;
  if ( !a2 )
    return 0;
  *(_QWORD *)Buffer = 0;
  Library = LoadLibraryExW(L"WININET.DLL", 0, 0x800u);
  v9 = (DWORD *)((char *)this + 16);
  if ( Library && FormatMessageW(0x900u, Library, *v9, 0, Buffer, 0, 0)
    || (v10 = FormatMessageW(0x1100u, 0, *v9, 0, Buffer, 0, 0)) != 0 )
  {
    if ( *v9 == 12003 )
    {
      dwBufferLength = 0;
      dwError = 0;
      if ( !InternetGetLastResponseInfoW(&dwError, 0, &dwBufferLength) && GetLastError() == 122 )
      {
        v11 = (WCHAR *)LocalAlloc(0x40u, 2LL * dwBufferLength);
        InternetGetLastResponseInfoW(&dwError, v11, &dwBufferLength);
        wcsncpy_s(a2, v4, v11, dwBufferLength);
        LocalFree(v11);
      }
    }
    else
    {
      wcscpy_s(a2, v4, *(const wchar_t **)Buffer);
    }
    v10 = 1;
    LocalFree(*(HLOCAL *)Buffer);
  }
  else
  {
    *a2 = 0;
  }
  return v10;
}

```

## disassembly

```asm
0x18006ea20  mov     [rsp-18h+arg_0], rbx
0x18006ea25  mov     [rsp-18h+arg_10], rsi
0x18006ea2a  push    rbp
0x18006ea2b  push    rdi
0x18006ea2c  push    r14
0x18006ea2e  mov     rbp, rsp
0x18006ea31  sub     rsp, 50h
0x18006ea35  mov     r14d, r8d
0x18006ea38  mov     rsi, rdx
0x18006ea3b  mov     rdi, rcx
0x18006ea3e  test    r9, r9
0x18006ea41  jz      short loc_18006EA4A
0x18006ea43  mov     dword ptr [r9], 0
0x18006ea4a  test    rsi, rsi
0x18006ea4d  jnz     short loc_18006EA56
0x18006ea4f  xor     eax, eax
0x18006ea51  jmp     loc_18006EB82
0x18006ea56  xor     edx, edx; hFile
0x18006ea58  mov     qword ptr [rbp+Buffer], 0
0x18006ea60  mov     r8d, 800h; dwFlags
0x18006ea66  lea     rcx, aWininetDll_0; "WININET.DLL"
0x18006ea6d  call    cs:__imp_LoadLibraryExW
0x18006ea73  add     rdi, 10h
0x18006ea77  test    rax, rax
0x18006ea7a  jz      short loc_18006EAAE
0x18006ea7c  mov     r8d, [rdi]; dwMessageId
0x18006ea7f  lea     rcx, [rbp+Buffer]
0x18006ea83  mov     [rsp+50h+Arguments], 0; Arguments
0x18006ea8c  xor     r9d, r9d; dwLanguageId
0x18006ea8f  mov     [rsp+50h+nSize], 0; nSize
0x18006ea97  mov     rdx, rax; lpSource
0x18006ea9a  mov     [rsp+50h+lpBuffer], rcx; lpBuffer
0x18006ea9f  mov     ecx, 900h; dwFlags
0x18006eaa4  call    cs:__imp_FormatMessageW
0x18006eaaa  test    eax, eax
0x18006eaac  jnz     short loc_18006EAEB
0x18006eaae  mov     r8d, [rdi]; dwMessageId
0x18006eab1  lea     rax, [rbp+Buffer]
0x18006eab5  mov     [rsp+50h+Arguments], 0; Arguments
0x18006eabe  xor     r9d, r9d; dwLanguageId
0x18006eac1  mov     [rsp+50h+nSize], 0; nSize
0x18006eac9  xor     edx, edx; lpSource
0x18006eacb  mov     ecx, 1100h; dwFlags
0x18006ead0  mov     [rsp+50h+lpBuffer], rax; lpBuffer
0x18006ead5  call    cs:__imp_FormatMessageW
0x18006eadb  mov     ebx, eax
0x18006eadd  test    eax, eax
0x18006eadf  jnz     short loc_18006EAEB
0x18006eae1  xor     ecx, ecx
0x18006eae3  mov     [rsi], cx
0x18006eae6  jmp     loc_18006EB80
0x18006eaeb  cmp     dword ptr [rdi], 2EE3h
0x18006eaf1  jnz     short loc_18006EB61
0x18006eaf3  lea     r8, [rbp+dwBufferLength]; lpdwBufferLength
0x18006eaf7  mov     [rbp+dwBufferLength], 0
0x18006eafe  xor     edx, edx; lpszBuffer
0x18006eb00  mov     [rbp+dwError], 0
0x18006eb07  lea     rcx, [rbp+dwError]; lpdwError
0x18006eb0b  call    cs:__imp_InternetGetLastResponseInfoW
0x18006eb11  test    eax, eax
0x18006eb13  jnz     short loc_18006EB71
0x18006eb15  call    cs:__imp_GetLastError
0x18006eb1b  cmp     eax, 7Ah ; 'z'
0x18006eb1e  jnz     short loc_18006EB71
0x18006eb20  mov     edx, [rbp+dwBufferLength]
0x18006eb23  lea     ecx, [rax-3Ah]; uFlags
0x18006eb26  add     rdx, rdx; uBytes
0x18006eb29  call    cs:__imp_LocalAlloc
0x18006eb2f  mov     rdx, rax; lpszBuffer
0x18006eb32  lea     r8, [rbp+dwBufferLength]; lpdwBufferLength
0x18006eb36  lea     rcx, [rbp+dwError]; lpdwError
0x18006eb3a  mov     rbx, rax
0x18006eb3d  call    cs:__imp_InternetGetLastResponseInfoW
0x18006eb43  mov     r9d, [rbp+dwBufferLength]; MaxCount
0x18006eb47  mov     rdx, r14; SizeInWords
0x18006eb4a  mov     r8, rbx; Source
0x18006eb4d  mov     rcx, rsi; Destination
0x18006eb50  call    cs:__imp_wcsncpy_s
0x18006eb56  mov     rcx, rbx; hMem
0x18006eb59  call    cs:__imp_LocalFree
0x18006eb5f  jmp     short loc_18006EB71
0x18006eb61  mov     r8, qword ptr [rbp+Buffer]; Source
0x18006eb65  mov     rdx, r14; SizeInWords
0x18006eb68  mov     rcx, rsi; Destination
0x18006eb6b  call    cs:__imp_wcscpy_s
0x18006eb71  mov     rcx, qword ptr [rbp+Buffer]; hMem
0x18006eb75  mov     ebx, 1
0x18006eb7a  call    cs:__imp_LocalFree
0x18006eb80  mov     eax, ebx
0x18006eb82  lea     r11, [rsp+50h+var_s0]
0x18006eb87  mov     rbx, [r11+20h]
0x18006eb8b  mov     rsi, [r11+30h]
0x18006eb8f  mov     rsp, r11
0x18006eb92  pop     r14
0x18006eb94  pop     rdi
0x18006eb95  pop     rbp
0x18006eb96  retn
```
