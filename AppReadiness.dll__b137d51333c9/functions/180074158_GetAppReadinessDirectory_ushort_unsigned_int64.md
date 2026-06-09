# GetAppReadinessDirectory(ushort *,unsigned __int64)

- ea: `0x180074158`
- end: `0x18007425e`
- name: `?GetAppReadinessDirectory@@YAJPEAG_K@Z`
- size: `262`
- prototype: `__int64 __fastcall(WCHAR *lpPathName, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, loader_planting`

## callers

- `0x180019620`
- `0x18001abb0`

## callees

- `0x1800232cc`
- `0x180074158`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800741ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074231`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800741ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074231`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800741df`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800741df`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800741b3`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800741b3`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180074227`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180074227`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180074216`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180074216`

## string_xrefs

- `0x180074207`: `AppReadiness`
- `0x18007419a`: `AppReadinessDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetAppReadinessDirectory(WCHAR *lpPathName, __int64 a2)
{
  __int64 result; // rax
  int v4; // ebx
  signed int LastError; // eax
  signed int v6; // eax
  unsigned int v7; // [rsp+58h] [rbp+10h] BYREF
  int v8; // [rsp+5Ch] [rbp+14h]
  UINT uSize; // [rsp+60h] [rbp+18h] BYREF

  v8 = HIDWORD(a2);
  v7 = 0;
  result = ULongLongToULong(0x208u, &v7);
  v4 = result;
  if ( (int)result >= 0 )
  {
    if ( (int)RtlGetPersistedStateLocation(L"AppReadinessDirectory", 0, 0, 1, lpPathName, v7, &v7) >= 0 )
      goto LABEL_17;
    uSize = 0;
    result = ULongLongToULong(0x104u, &uSize);
    if ( (int)result < 0 )
      return result;
    if ( GetWindowsDirectoryW(lpPathName, uSize) - 1 <= 0x102 )
      goto LABEL_18;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
    {
LABEL_18:
      v4 = PathCchAppend(lpPathName, 0x104u, L"AppReadiness");
      if ( v4 >= 0 )
      {
LABEL_17:
        if ( !CreateDirectoryW(lpPathName, 0) )
        {
          v6 = GetLastError();
          v4 = v6;
          if ( v6 > 0 )
            v4 = (unsigned __int16)v6 | 0x80070000;
          if ( v4 == -2147024713 )
            return 0;
        }
      }
    }
    return (unsigned int)v4;
  }
  return result;
}

```

## disassembly

```asm
0x180074158  mov     rax, rsp
0x18007415b  mov     [rax+8], rbx
0x18007415f  mov     [rax+10h], rdx
0x180074163  push    rdi
0x180074164  sub     rsp, 40h
0x180074168  mov     rdi, rcx
0x18007416b  mov     dword ptr [rax+10h], 0
0x180074172  mov     ecx, 208h; unsigned __int64
0x180074177  lea     rdx, [rax+10h]; unsigned int *
0x18007417b  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180074180  mov     ebx, eax
0x180074182  test    eax, eax
0x180074184  js      loc_180074253
0x18007418a  lea     rax, [rsp+48h+arg_8]
0x18007418f  mov     r9d, 1
0x180074195  mov     [rsp+48h+var_18], rax
0x18007419a  lea     rcx, aAppreadinessdi; "AppReadinessDirectory"
0x1800741a1  mov     eax, [rsp+48h+arg_8]
0x1800741a5  xor     r8d, r8d
0x1800741a8  mov     [rsp+48h+var_20], eax
0x1800741ac  xor     edx, edx
0x1800741ae  mov     [rsp+48h+var_28], rdi
0x1800741b3  call    cs:__imp_RtlGetPersistedStateLocation
0x1800741b9  test    eax, eax
0x1800741bb  jns     short loc_180074222
0x1800741bd  lea     rdx, [rsp+48h+uSize]; unsigned int *
0x1800741c2  mov     [rsp+48h+uSize], 0
0x1800741ca  mov     ecx, 104h; unsigned __int64
0x1800741cf  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800741d4  test    eax, eax
0x1800741d6  js      short loc_180074253
0x1800741d8  mov     edx, [rsp+48h+uSize]; uSize
0x1800741dc  mov     rcx, rdi; lpBuffer
0x1800741df  call    cs:__imp_GetWindowsDirectoryW
0x1800741e5  dec     eax
0x1800741e7  cmp     eax, 102h
0x1800741ec  jbe     short loc_180074207
0x1800741ee  call    cs:__imp_GetLastError
0x1800741f4  mov     ebx, eax
0x1800741f6  test    eax, eax
0x1800741f8  jle     short loc_180074203
0x1800741fa  movzx   ebx, ax
0x1800741fd  or      ebx, 80070000h
0x180074203  test    ebx, ebx
0x180074205  js      short loc_180074251
0x180074207  lea     r8, aAppreadiness; "AppReadiness"
0x18007420e  mov     edx, 104h; cchPath
0x180074213  mov     rcx, rdi; pszPath
0x180074216  call    cs:__imp_PathCchAppend
0x18007421c  mov     ebx, eax
0x18007421e  test    eax, eax
0x180074220  js      short loc_180074251
0x180074222  xor     edx, edx; lpSecurityAttributes
0x180074224  mov     rcx, rdi; lpPathName
0x180074227  call    cs:__imp_CreateDirectoryW
0x18007422d  test    eax, eax
0x18007422f  jnz     short loc_180074251
0x180074231  call    cs:__imp_GetLastError
0x180074237  mov     ebx, eax
0x180074239  test    eax, eax
0x18007423b  jle     short loc_180074246
0x18007423d  movzx   ebx, ax
0x180074240  or      ebx, 80070000h
0x180074246  xor     eax, eax
0x180074248  cmp     ebx, 800700B7h
0x18007424e  cmovz   ebx, eax
0x180074251  mov     eax, ebx
0x180074253  mov     rbx, [rsp+48h+arg_0]
0x180074258  add     rsp, 40h
0x18007425c  pop     rdi
0x18007425d  retn
```
