# DiagCreatePath(ushort *)

- ea: `0x180025be4`
- end: `0x180025c67`
- name: `?DiagCreatePath@@YAJPEAG@Z`
- size: `131`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180025770`

## callees

- `0x180025be4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180025c04`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180025c04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025c26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025c30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025c26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025c30`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180025c1c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180025c1c`

## pseudocode

```c
__int64 __fastcall DiagCreatePath(LPCWSTR lpPathName)
{
  WCHAR *v2; // rbx
  wchar_t *v3; // rax
  unsigned int v4; // ecx
  signed int LastError; // eax

  v2 = (WCHAR *)(lpPathName + 3);
  while ( 1 )
  {
    v3 = wcschr(v2 + 1, 0x5Cu);
    v4 = 0;
    v2 = v3;
    if ( !v3 )
      break;
    *v3 = 0;
    if ( CreateDirectoryW(lpPathName, 0) || !GetLastError() )
    {
      *v2 = 92;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      *v2 = 92;
      if ( ((v4 + 0x80000000) & 0x80000000) == 0 && v4 != -2147024713 )
        return v4;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180025be4  push    rbx
0x180025be6  push    rbp
0x180025be7  push    rsi
0x180025be8  push    rdi
0x180025be9  sub     rsp, 28h
0x180025bed  mov     rdi, rcx
0x180025bf0  lea     rbx, [rcx+6]
0x180025bf4  mov     esi, 5Ch ; '\'
0x180025bf9  mov     ebp, 80000000h
0x180025bfe  mov     edx, esi; Ch
0x180025c00  lea     rcx, [rbx+2]; Str
0x180025c04  call    cs:__imp_wcschr
0x180025c0a  xor     ecx, ecx
0x180025c0c  mov     rbx, rax
0x180025c0f  test    rax, rax
0x180025c12  jz      short loc_180025C57
0x180025c14  mov     [rax], cx
0x180025c17  xor     edx, edx; lpSecurityAttributes
0x180025c19  mov     rcx, rdi; lpPathName
0x180025c1c  call    cs:__imp_CreateDirectoryW
0x180025c22  test    eax, eax
0x180025c24  jnz     short loc_180025C62
0x180025c26  call    cs:__imp_GetLastError
0x180025c2c  test    eax, eax
0x180025c2e  jz      short loc_180025C62
0x180025c30  call    cs:__imp_GetLastError
0x180025c36  mov     ecx, eax
0x180025c38  test    eax, eax
0x180025c3a  jle     short loc_180025C45
0x180025c3c  movzx   ecx, ax
0x180025c3f  or      ecx, 80070000h
0x180025c45  lea     eax, [rcx+rbp]
0x180025c48  mov     [rbx], si
0x180025c4b  test    ebp, eax
0x180025c4d  jnz     short loc_180025BFE
0x180025c4f  cmp     ecx, 800700B7h
0x180025c55  jz      short loc_180025BFE
0x180025c57  mov     eax, ecx
0x180025c59  add     rsp, 28h
0x180025c5d  pop     rdi
0x180025c5e  pop     rsi
0x180025c5f  pop     rbp
0x180025c60  pop     rbx
0x180025c61  retn
0x180025c62  mov     [rbx], si
0x180025c65  jmp     short loc_180025BFE
```
