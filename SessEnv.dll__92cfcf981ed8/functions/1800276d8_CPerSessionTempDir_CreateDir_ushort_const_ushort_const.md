# CPerSessionTempDir::CreateDir(ushort const *,ushort const *)

- ea: `0x1800276d8`
- end: `0x180027777`
- name: `?CreateDir@CPerSessionTempDir@@AEAAJPEBG0@Z`
- size: `159`
- prototype: `__int64 __fastcall(CPerSessionTempDir *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002832c`

## callees

- `0x180003f30`
- `0x1800276d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800276f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002772a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800276f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002772a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800276ec`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180027720`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800276ec`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180027720`

## string_xrefs

- `0x18002774f`: `CPerSessionTempDir::CreateDir`
- `0x180027759`: `CreateDirectory failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CPerSessionTempDir::CreateDir(
        CPerSessionTempDir *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  signed int v4; // ebx
  signed int LastError; // eax
  signed int v6; // eax

  v4 = 0;
  if ( !CreateDirectoryW(a2, 0) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 == -2147024713 )
    {
      v4 = 0;
    }
    else if ( v4 < 0 )
    {
      goto LABEL_13;
    }
  }
  if ( CreateDirectoryW(a3, 0) )
    goto LABEL_12;
  v6 = GetLastError();
  v4 = v6;
  if ( v6 > 0 )
    v4 = (unsigned __int16)v6 | 0x80070000;
  if ( v4 != -2147024713 )
  {
LABEL_12:
    if ( v4 >= 0 )
      return (unsigned int)v4;
LABEL_13:
    _DbgPrintMessage(8, "CreateDirectory failed: 0x%x in %s", v4, "CPerSessionTempDir::CreateDir");
    return (unsigned int)v4;
  }
  return 0;
}

```

## disassembly

```asm
0x1800276d8  mov     [rsp+arg_0], rbx
0x1800276dd  push    rdi
0x1800276de  sub     rsp, 20h
0x1800276e2  mov     rcx, rdx; lpPathName
0x1800276e5  mov     rdi, r8
0x1800276e8  xor     edx, edx; lpSecurityAttributes
0x1800276ea  xor     ebx, ebx
0x1800276ec  call    cs:__imp_CreateDirectoryW
0x1800276f2  test    eax, eax
0x1800276f4  jnz     short loc_18002771B
0x1800276f6  call    cs:__imp_GetLastError
0x1800276fc  mov     ebx, eax
0x1800276fe  test    eax, eax
0x180027700  jle     short loc_18002770B
0x180027702  movzx   ebx, ax
0x180027705  or      ebx, 80070000h
0x18002770b  cmp     ebx, 800700B7h
0x180027711  jnz     short loc_180027717
0x180027713  xor     ebx, ebx
0x180027715  jmp     short loc_18002771B
0x180027717  test    ebx, ebx
0x180027719  js      short loc_18002774F
0x18002771b  xor     edx, edx; lpSecurityAttributes
0x18002771d  mov     rcx, rdi; lpPathName
0x180027720  call    cs:__imp_CreateDirectoryW
0x180027726  test    eax, eax
0x180027728  jnz     short loc_18002774B
0x18002772a  call    cs:__imp_GetLastError
0x180027730  mov     ebx, eax
0x180027732  test    eax, eax
0x180027734  jle     short loc_18002773F
0x180027736  movzx   ebx, ax
0x180027739  or      ebx, 80070000h
0x18002773f  cmp     ebx, 800700B7h
0x180027745  jnz     short loc_18002774B
0x180027747  xor     ebx, ebx
0x180027749  jmp     short loc_18002776A
0x18002774b  test    ebx, ebx
0x18002774d  jns     short loc_18002776A
0x18002774f  lea     r9, aCpersessiontem; "CPerSessionTempDir::CreateDir"
0x180027756  mov     r8d, ebx
0x180027759  lea     rdx, aCreatedirector_0; "CreateDirectory failed: 0x%x in %s"
0x180027760  mov     ecx, 8; int
0x180027765  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002776a  mov     eax, ebx
0x18002776c  mov     rbx, [rsp+28h+arg_0]
0x180027771  add     rsp, 20h
0x180027775  pop     rdi
0x180027776  retn
```
