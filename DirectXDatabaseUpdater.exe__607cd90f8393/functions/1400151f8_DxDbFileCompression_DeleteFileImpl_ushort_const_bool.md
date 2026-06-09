# DxDbFileCompression::DeleteFileImpl(ushort const *,bool)

- ea: `0x1400151f8`
- end: `0x140015265`
- name: `?DeleteFileImpl@DxDbFileCompression@@YAXPEBG_N@Z`
- size: `109`
- prototype: `void __fastcall(LPCWSTR lpExistingFileName, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140005d20`
- `0x140007ad8`
- `0x14000fa90`

## callees

- `0x1400151f8`
- `0x14001526c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140015207`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140015207`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015211`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015211`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x140015241`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x140015241`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall DxDbFileCompression::DeleteFileImpl(LPCWSTR lpExistingFileName, const unsigned __int16 *a2)
{
  char v2; // bl
  DWORD LastError; // eax
  unsigned int v5; // r8d
  const char *v6; // r9
  __int64 v7; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (char)a2;
  if ( !DeleteFileW(lpExistingFileName) )
  {
    LastError = GetLastError();
    if ( LastError == 5 || LastError == 32 || LastError == 1224 )
    {
      if ( MoveFileExW(lpExistingFileName, 0, 4u) )
        return;
      v7 = 229;
      goto LABEL_10;
    }
    if ( !v2 || LastError != 2 )
    {
      v7 = 239;
LABEL_10:
      wil::details::in1diag3::Log_GetLastError(retaddr, (void *)v7, v5, v6);
    }
  }
}

```

## disassembly

```asm
0x1400151f8  mov     [rsp+arg_0], rbx
0x1400151fd  push    rdi
0x1400151fe  sub     rsp, 20h
0x140015202  mov     bl, dl
0x140015204  mov     rdi, rcx
0x140015207  call    cs:__imp_DeleteFileW
0x14001520d  test    eax, eax
0x14001520f  jnz     short loc_14001525A
0x140015211  call    cs:__imp_GetLastError
0x140015217  cmp     eax, 5
0x14001521a  jz      short loc_140015238
0x14001521c  cmp     eax, 20h ; ' '
0x14001521f  jz      short loc_140015238
0x140015221  cmp     eax, 4C8h
0x140015226  jz      short loc_140015238
0x140015228  test    bl, bl
0x14001522a  jz      short loc_140015231
0x14001522c  cmp     eax, 2
0x14001522f  jz      short loc_14001525A
0x140015231  mov     edx, 0EFh
0x140015236  jmp     short loc_140015250
0x140015238  xor     edx, edx; lpNewFileName
0x14001523a  mov     rcx, rdi; lpExistingFileName
0x14001523d  lea     r8d, [rdx+4]; dwFlags
0x140015241  call    cs:__imp_MoveFileExW
0x140015247  test    eax, eax
0x140015249  jnz     short loc_14001525A
0x14001524b  mov     edx, 0E5h; void *
0x140015250  mov     rcx, [rsp+28h]; this
0x140015255  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x14001525a  mov     rbx, [rsp+28h+arg_0]
0x14001525f  add     rsp, 20h
0x140015263  pop     rdi
0x140015264  retn
```
