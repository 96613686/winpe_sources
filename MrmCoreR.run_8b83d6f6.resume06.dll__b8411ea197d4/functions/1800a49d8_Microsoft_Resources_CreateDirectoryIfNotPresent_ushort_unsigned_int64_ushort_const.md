# Microsoft::Resources::CreateDirectoryIfNotPresent(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800a49d8`
- end: `0x1800a4a4c`
- name: `?CreateDirectoryIfNotPresent@Resources@Microsoft@@YAJPEAG_KPEBG@Z`
- size: `116`
- prototype: `__int64 __fastcall(Microsoft::Resources *__hidden this, unsigned __int16 *, unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800a5e24`

## callees

- `0x180052344`
- `0x1800a49d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a4a1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a4a2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a4a1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a4a2c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800a4a15`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800a4a15`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::CreateDirectoryIfNotPresent(
        Microsoft::Resources *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  int v7; // ebx
  signed int LastError; // eax

  v7 = StringCchCatW((unsigned __int16 *)this, (unsigned __int64)a2, L"\\");
  if ( v7 >= 0 )
  {
    v7 = StringCchCatW((unsigned __int16 *)this, (unsigned __int64)a2, a3);
    if ( v7 >= 0 && !CreateDirectoryW((LPCWSTR)this, 0) && GetLastError() != 183 )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800a49d8  push    rbx
0x1800a49da  push    rbp
0x1800a49db  push    rsi
0x1800a49dc  push    rdi
0x1800a49dd  sub     rsp, 28h
0x1800a49e1  mov     rbp, r8
0x1800a49e4  mov     rsi, rdx
0x1800a49e7  lea     r8, asc_1800E1F10; "\\"
0x1800a49ee  mov     rdi, rcx
0x1800a49f1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a49f6  mov     ebx, eax
0x1800a49f8  test    eax, eax
0x1800a49fa  js      short loc_1800A4A41
0x1800a49fc  mov     r8, rbp; unsigned __int16 *
0x1800a49ff  mov     rdx, rsi; unsigned __int64
0x1800a4a02  mov     rcx, rdi; unsigned __int16 *
0x1800a4a05  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a4a0a  mov     ebx, eax
0x1800a4a0c  test    eax, eax
0x1800a4a0e  js      short loc_1800A4A41
0x1800a4a10  xor     edx, edx; lpSecurityAttributes
0x1800a4a12  mov     rcx, rdi; lpPathName
0x1800a4a15  call    cs:__imp_CreateDirectoryW
0x1800a4a1b  test    eax, eax
0x1800a4a1d  jnz     short loc_1800A4A41
0x1800a4a1f  call    cs:__imp_GetLastError
0x1800a4a25  cmp     eax, 0B7h
0x1800a4a2a  jz      short loc_1800A4A41
0x1800a4a2c  call    cs:__imp_GetLastError
0x1800a4a32  mov     ebx, eax
0x1800a4a34  test    eax, eax
0x1800a4a36  jle     short loc_1800A4A41
0x1800a4a38  movzx   ebx, ax
0x1800a4a3b  or      ebx, 80070000h
0x1800a4a41  mov     eax, ebx
0x1800a4a43  add     rsp, 28h
0x1800a4a47  pop     rdi
0x1800a4a48  pop     rsi
0x1800a4a49  pop     rbp
0x1800a4a4a  pop     rbx
0x1800a4a4b  retn
```
