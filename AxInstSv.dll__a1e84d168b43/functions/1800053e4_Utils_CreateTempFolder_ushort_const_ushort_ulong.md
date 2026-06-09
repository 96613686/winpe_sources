# Utils::CreateTempFolder(ushort const *,ushort *,ulong)

- ea: `0x1800053e4`
- end: `0x1800054c4`
- name: `?CreateTempFolder@Utils@@SAJPEBGPEAGK@Z`
- size: `224`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180006aec`

## callees

- `0x180001720`
- `0x180005060`
- `0x1800053e4`
- `0x180005b78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005483`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005483`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180005465`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180005465`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180005479`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180005479`

## pseudocode

```c
__int64 __fastcall Utils::CreateTempFolder(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  int appended; // ebx
  int v5; // edi
  unsigned int v6; // r9d
  signed int LastError; // eax
  unsigned __int16 v9[264]; // [rsp+20h] [rbp-238h] BYREF

  if ( a1 && *a1 && (appended = 0, v5 = 1, a2) )
  {
    while ( v5 <= 9999 )
    {
      appended = StringCchPrintfW(v9, 0x104u, L"AXS%05d", (unsigned int)v5);
      if ( appended < 0 )
        return (unsigned int)appended;
      appended = Utils::AppendPath(a1, v9, a2, v6);
      if ( appended < 0 )
        return (unsigned int)appended;
      if ( GetFileAttributesW(a2) == -1 )
        break;
      ++v5;
    }
    if ( !CreateDirectoryW(a2, 0) )
    {
      LastError = GetLastError();
      appended = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1800053e4  mov     [rsp+arg_10], rbx
0x1800053e9  push    rbp
0x1800053ea  push    rsi
0x1800053eb  push    rdi
0x1800053ec  sub     rsp, 240h
0x1800053f3  mov     rax, cs:__security_cookie
0x1800053fa  xor     rax, rsp
0x1800053fd  mov     [rsp+258h+var_28], rax
0x180005405  mov     rsi, rdx
0x180005408  mov     rbp, rcx
0x18000540b  test    rcx, rcx
0x18000540e  jz      loc_18000549A
0x180005414  xor     eax, eax
0x180005416  cmp     ax, [rcx]
0x180005419  jz      short loc_18000549A
0x18000541b  xor     ebx, ebx
0x18000541d  lea     edi, [rax+1]
0x180005420  test    rdx, rdx
0x180005423  jz      short loc_18000549A
0x180005425  cmp     edi, 270Fh
0x18000542b  jg      short loc_180005474
0x18000542d  mov     r9d, edi
0x180005430  lea     r8, aAxs05d; "AXS%05d"
0x180005437  mov     edx, 104h; unsigned __int64
0x18000543c  lea     rcx, [rsp+258h+var_238]; unsigned __int16 *
0x180005441  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005446  mov     ebx, eax
0x180005448  test    eax, eax
0x18000544a  js      short loc_18000549F
0x18000544c  mov     r8, rsi; unsigned __int16 *
0x18000544f  lea     rdx, [rsp+258h+var_238]; unsigned __int16 *
0x180005454  mov     rcx, rbp; unsigned __int16 *
0x180005457  call    ?AppendPath@Utils@@SAJPEBG0PEAGK@Z; Utils::AppendPath(ushort const *,ushort const *,ushort *,ulong)
0x18000545c  mov     ebx, eax
0x18000545e  test    eax, eax
0x180005460  js      short loc_18000549F
0x180005462  mov     rcx, rsi; lpFileName
0x180005465  call    cs:__imp_GetFileAttributesW
0x18000546b  cmp     eax, 0FFFFFFFFh
0x18000546e  jz      short loc_180005474
0x180005470  inc     edi
0x180005472  jmp     short loc_180005425
0x180005474  xor     edx, edx; lpSecurityAttributes
0x180005476  mov     rcx, rsi; lpPathName
0x180005479  call    cs:__imp_CreateDirectoryW
0x18000547f  test    eax, eax
0x180005481  jnz     short loc_18000549F
0x180005483  call    cs:__imp_GetLastError
0x180005489  mov     ebx, eax
0x18000548b  test    eax, eax
0x18000548d  jle     short loc_18000549F
0x18000548f  movzx   ebx, ax
0x180005492  or      ebx, 80070000h
0x180005498  jmp     short loc_18000549F
0x18000549a  mov     ebx, 80070057h
0x18000549f  mov     eax, ebx
0x1800054a1  mov     rcx, [rsp+258h+var_28]
0x1800054a9  xor     rcx, rsp; StackCookie
0x1800054ac  call    __security_check_cookie
0x1800054b1  mov     rbx, [rsp+258h+arg_10]
0x1800054b9  add     rsp, 240h
0x1800054c0  pop     rdi
0x1800054c1  pop     rsi
0x1800054c2  pop     rbp
0x1800054c3  retn
```
