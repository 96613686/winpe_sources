# __std_fs_get_final_path_name_by_handle

- ea: `0x1800bab98`
- end: `0x1800babc8`
- name: `__std_fs_get_final_path_name_by_handle`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x1800cb300`

## callees

- `0x1800bab98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800babaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800babaa`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800bab9c`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800bab9c`

## pseudocode

```c
__int64 __fastcall _std_fs_get_final_path_name_by_handle(void *a1, WCHAR *a2, DWORD a3, DWORD a4)
{
  __int64 v5; // [rsp+20h] [rbp-18h]

  LODWORD(v5) = GetFinalPathNameByHandleW(a1, a2, a3, a4);
  if ( (_DWORD)v5 )
    HIDWORD(v5) = 0;
  else
    HIDWORD(v5) = GetLastError();
  return v5;
}

```

## disassembly

```asm
0x1800bab98  sub     rsp, 38h
0x1800bab9c  call    cs:__imp_GetFinalPathNameByHandleW
0x1800baba2  mov     dword ptr [rsp+38h+var_18], eax
0x1800baba6  test    eax, eax
0x1800baba8  jnz     short loc_1800BABB6
0x1800babaa  call    cs:__imp_GetLastError
0x1800babb0  mov     dword ptr [rsp+38h+var_18+4], eax
0x1800babb4  jmp     short loc_1800BABBE
0x1800babb6  mov     dword ptr [rsp+38h+var_18+4], 0
0x1800babbe  mov     rax, [rsp+38h+var_18]
0x1800babc3  add     rsp, 38h
0x1800babc7  retn
```
