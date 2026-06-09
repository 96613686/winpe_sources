# _anonymous_namespace_::Remover::Delete

- ea: `0x180041260`
- end: `0x180041322`
- name: `_anonymous_namespace_::Remover::Delete`
- size: `194`
- prototype: `int __fastcall(const wchar_t *pathName, const _WIN32_FIND_DATAW *findData, const _WIN32_FIND_DATAW *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180041530`

## callees

- `0x1800223bc`
- `0x180025cfb`
- `0x1800266d0`
- `0x180041260`
- `0x1800414f4`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800412a7`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800412e2`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800412a7`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800412e2`

## pseudocode

```c
int __fastcall anonymous_namespace_::Remover::Delete(
        const wchar_t *pathName,
        const _WIN32_FIND_DATAW *findData,
        const _WIN32_FIND_DATAW *a3)
{
  int v4; // ebx
  unsigned int dwFileAttributes; // edx

  v4 = 0;
  dwFileAttributes = a3->dwFileAttributes;
  if ( (a3->dwFileAttributes & 0x10) != 0 )
  {
    if ( !RemoveDirectoryW_0((LPCWSTR)findData)
      && GetLastError_0() == 5
      && (a3->dwFileAttributes & 1) != 0
      && (!SetFileAttributesW((LPCWSTR)findData, a3->dwFileAttributes & 0xFFFFFFFE)
       || !RemoveDirectoryW_0((LPCWSTR)findData)) )
    {
      GetLastError_0();
    }
    v4 = Common::IsDirectoryReparsePointOpaque(a3) + 1;
  }
  else if ( (dwFileAttributes & 1) != 0 && !SetFileAttributesW((LPCWSTR)findData, dwFileAttributes & 0xFFFFFFFE)
         || !(*(unsigned int (__fastcall **)(const _WIN32_FIND_DATAW *))pathName)(findData) )
  {
    GetLastError_0();
  }
  return anonymous_namespace_::Remover::Report(pathName, (const ActionType)findData, v4);
}

```

## disassembly

```asm
0x180041260  push    rbx
0x180041262  push    rsi
0x180041263  push    rdi
0x180041264  push    r14
0x180041266  push    r15
0x180041268  sub     rsp, 20h
0x18004126c  mov     rsi, pathName
0x18004126f  xor     ebx, ebx
0x180041271  mov     edx, [findData]
0x180041274  mov     r14, findData
0x180041277  mov     r15, this
0x18004127a  test    dl, 10h
0x18004127d  jz      short loc_1800412D7
0x18004127f  mov     this, rsi; lpPathName
0x180041282  mov     edi, ebx
0x180041284  call    RemoveDirectoryW_0
0x180041289  test    eax, eax
0x18004128b  jnz     short loc_1800412C8
0x18004128d  call    GetLastError_0
0x180041292  mov     edi, eax
0x180041294  cmp     eax, 5
0x180041297  jnz     short loc_1800412C8
0x180041299  mov     edx, [r14]
0x18004129c  test    dl, 1
0x18004129f  jz      short loc_1800412C8
0x1800412a1  and     edx, 0FFFFFFFEh; dwFileAttributes
0x1800412a4  mov     this, rsi; lpFileName
0x1800412a7  call    cs:__imp_SetFileAttributesW
0x1800412ad  test    eax, eax
0x1800412af  jz      short loc_1800412C1
0x1800412b1  mov     this, rsi; lpPathName
0x1800412b4  call    RemoveDirectoryW_0
0x1800412b9  test    eax, eax
0x1800412bb  jz      short loc_1800412C1
0x1800412bd  mov     edi, ebx
0x1800412bf  jmp     short loc_1800412C8
0x1800412c1  call    GetLastError_0
0x1800412c6  mov     edi, eax
0x1800412c8  mov     this, r14; findData
0x1800412cb  call    ?IsDirectoryReparsePointOpaque@Common@@YA_NAEBU_WIN32_FIND_DATAW@@@Z; Common::IsDirectoryReparsePointOpaque(_WIN32_FIND_DATAW const &)
0x1800412d0  movzx   ebx, al
0x1800412d3  inc     ebx
0x1800412d5  jmp     short loc_180041306
0x1800412d7  test    dl, 1
0x1800412da  jz      short loc_1800412F5
0x1800412dc  and     edx, 0FFFFFFFEh; dwFileAttributes
0x1800412df  mov     this, rsi; lpFileName
0x1800412e2  call    cs:__imp_SetFileAttributesW
0x1800412e8  test    eax, eax
0x1800412ea  jnz     short loc_1800412F5
0x1800412ec  call    GetLastError_0
0x1800412f1  mov     edi, eax
0x1800412f3  jmp     short loc_180041306
0x1800412f5  mov     rax, [r15]
0x1800412f8  mov     this, rsi
0x1800412fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041300  test    eax, eax
0x180041302  jz      short loc_1800412EC
0x180041304  mov     edi, ebx
0x180041306  mov     r9d, edi
0x180041309  mov     r8d, ebx
0x18004130c  mov     pathName, rsi
0x18004130f  mov     this, r15
0x180041312  add     rsp, 20h
0x180041316  pop     r15
0x180041318  pop     r14
0x18004131a  pop     rdi
0x18004131b  pop     rsi
0x18004131c  pop     rbx
0x18004131d  jmp     _anonymous_namespace___Remover__Report
```
