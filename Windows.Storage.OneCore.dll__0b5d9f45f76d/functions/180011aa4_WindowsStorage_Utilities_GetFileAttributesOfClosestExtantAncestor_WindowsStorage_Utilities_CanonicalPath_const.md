# WindowsStorage::Utilities::GetFileAttributesOfClosestExtantAncestor(WindowsStorage::Utilities::CanonicalPath const &,WindowsStorage::Utilities::CanonicalPath *,bool *)

- ea: `0x180011aa4`
- end: `0x180011b90`
- name: `?GetFileAttributesOfClosestExtantAncestor@Utilities@WindowsStorage@@YAKAEBVCanonicalPath@12@PEAV312@PEA_N@Z`
- size: `236`
- prototype: `__int64 __fastcall(LPCWSTR *this, const struct WindowsStorage::Utilities::CanonicalPath *, struct WindowsStorage::Utilities::CanonicalPath *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path`

## callers

- `0x180015b24`

## callees

- `0x180010654`
- `0x1800119d4`
- `0x180011a4c`
- `0x180011aa4`
- `0x180011b98`
- `0x180011dc4`
- `0x180011f20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011aef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011aef`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180011ad4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180011b34`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180011ad4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180011b34`
- `api-ms-win-core-path-l1-1-0!PathCchIsRoot` at `0x180011aff`
- `api-ms-win-core-path-l1-1-0!PathCchIsRoot` at `0x180011aff`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WindowsStorage::Utilities::GetFileAttributesOfClosestExtantAncestor(
        LPCWSTR *this,
        const struct WindowsStorage::Utilities::CanonicalPath *a2,
        struct WindowsStorage::Utilities::CanonicalPath *a3,
        bool *a4)
{
  DWORD FileAttributesW; // eax
  const char *v8; // r9
  DWORD v9; // ebx
  __int64 v10; // rax
  char v11; // al
  PCWSTR ppszExt[2]; // [rsp+20h] [rbp-78h] BYREF
  PCWSTR pszPath[3]; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v15[16]; // [rsp+48h] [rbp-50h] BYREF
  _BYTE v16[64]; // [rsp+58h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  std::vector<unsigned short>::vector<unsigned short>(pszPath);
  WindowsStorage::Utilities::CanonicalPath::_Canonicalize((LPWSTR *)ppszExt, this[2]);
  FileAttributesW = GetFileAttributesW(this[2]);
  v9 = FileAttributesW;
  if ( a3 )
    *(_BYTE *)a3 = FileAttributesW != -1;
  if ( FileAttributesW == -1 )
  {
    while ( GetLastError() == 2 )
    {
      if ( !PathCchIsRoot(pszPath[0]) )
      {
        v10 = WindowsStorage::Utilities::CanonicalPath::Parent(ppszExt, v15);
        WindowsStorage::Utilities::CanonicalPath::operator=(ppszExt, v10);
        std::vector<unsigned short>::_Tidy(v16);
        v9 = GetFileAttributesW(pszPath[0]);
        if ( v9 == -1 )
          continue;
      }
      if ( v9 != -1 )
        goto LABEL_9;
      break;
    }
    v11 = 1;
  }
  else
  {
LABEL_9:
    v11 = 0;
  }
  if ( v11 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x65,
      (unsigned int)"onecore\\base\\windows.storage\\src\\filesystem.cpp",
      v8);
  if ( a2 )
    WindowsStorage::Utilities::CanonicalPath::operator=(a2, ppszExt);
  std::vector<unsigned short>::_Tidy(pszPath);
  return v9;
}

```

## disassembly

```asm
0x180011aa4  push    rbx
0x180011aa6  push    rbp
0x180011aa7  push    rsi
0x180011aa8  push    rdi
0x180011aa9  sub     rsp, 78h
0x180011aad  mov     rsi, r8
0x180011ab0  mov     rdi, rdx
0x180011ab3  mov     rbx, rcx
0x180011ab6  lea     rcx, [rsp+98h+pszPath]
0x180011abb  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::vector<ushort>(void)
0x180011ac0  nop
0x180011ac1  mov     rdx, [rbx+10h]; lpFileName
0x180011ac5  lea     rcx, [rsp+98h+ppszExt]; ppszExt
0x180011aca  call    ?_Canonicalize@CanonicalPath@Utilities@WindowsStorage@@AEAAXPEBG@Z; WindowsStorage::Utilities::CanonicalPath::_Canonicalize(ushort const *)
0x180011acf  nop
0x180011ad0  mov     rcx, [rbx+10h]; lpFileName
0x180011ad4  call    cs:__imp_GetFileAttributesW
0x180011ada  mov     ebx, eax
0x180011adc  or      ebp, 0FFFFFFFFh
0x180011adf  test    rsi, rsi
0x180011ae2  jz      short loc_180011AEB
0x180011ae4  cmp     eax, ebp
0x180011ae6  setnz   cl
0x180011ae9  mov     [rsi], cl
0x180011aeb  cmp     eax, ebp
0x180011aed  jnz     short loc_180011B48
0x180011aef  call    cs:__imp_GetLastError
0x180011af5  cmp     eax, 2
0x180011af8  jnz     short loc_180011B44
0x180011afa  mov     rcx, [rsp+98h+pszPath]; pszPath
0x180011aff  call    cs:__imp_PathCchIsRoot
0x180011b05  test    eax, eax
0x180011b07  jnz     short loc_180011B40
0x180011b09  lea     rdx, [rsp+98h+var_50]
0x180011b0e  lea     rcx, [rsp+98h+ppszExt]
0x180011b13  call    ?Parent@CanonicalPath@Utilities@WindowsStorage@@QEBA?AV123@XZ; WindowsStorage::Utilities::CanonicalPath::Parent(void)
0x180011b18  mov     rdx, rax
0x180011b1b  lea     rcx, [rsp+98h+ppszExt]
0x180011b20  call    ??4CanonicalPath@Utilities@WindowsStorage@@QEAAAEAV012@$$QEAV012@@Z; WindowsStorage::Utilities::CanonicalPath::operator=(WindowsStorage::Utilities::CanonicalPath &&)
0x180011b25  lea     rcx, [rsp+98h+var_40]
0x180011b2a  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180011b2f  mov     rcx, [rsp+98h+pszPath]; lpFileName
0x180011b34  call    cs:__imp_GetFileAttributesW
0x180011b3a  mov     ebx, eax
0x180011b3c  cmp     eax, ebp
0x180011b3e  jz      short loc_180011AEF
0x180011b40  cmp     ebx, ebp
0x180011b42  jnz     short loc_180011B48
0x180011b44  mov     al, 1
0x180011b46  jmp     short loc_180011B4A
0x180011b48  xor     al, al
0x180011b4a  mov     rcx, [rsp+98h]; this
0x180011b52  test    al, al
0x180011b54  jz      short loc_180011B68
0x180011b56  lea     r8, aOnecoreBaseWin_9; "onecore\\base\\windows.storage\\src\\fi"...
0x180011b5d  mov     edx, 65h ; 'e'; void *
0x180011b62  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180011b68  test    rdi, rdi
0x180011b6b  jz      short loc_180011B7B
0x180011b6d  lea     rdx, [rsp+98h+ppszExt]
0x180011b72  mov     rcx, rdi
0x180011b75  call    ??4CanonicalPath@Utilities@WindowsStorage@@QEAAAEAV012@$$QEAV012@@Z; WindowsStorage::Utilities::CanonicalPath::operator=(WindowsStorage::Utilities::CanonicalPath &&)
0x180011b7a  nop
0x180011b7b  lea     rcx, [rsp+98h+pszPath]
0x180011b80  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x180011b85  mov     eax, ebx
0x180011b87  add     rsp, 78h
0x180011b8b  pop     rdi
0x180011b8c  pop     rsi
0x180011b8d  pop     rbp
0x180011b8e  pop     rbx
0x180011b8f  retn
```
