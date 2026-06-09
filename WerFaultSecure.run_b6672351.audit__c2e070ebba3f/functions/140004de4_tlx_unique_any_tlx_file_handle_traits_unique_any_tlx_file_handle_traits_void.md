# tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)

- ea: `0x140004de4`
- end: `0x140004e00`
- name: `??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140011434`
- `0x140011446`
- `0x14001148b`
- `0x1400114d3`

## callees

- `0x140004de4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004df5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004df5`

## pseudocode

```c
int __fastcall tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void **a1)
{
  void *v1; // rcx
  int result; // eax

  v1 = *a1;
  result = (_DWORD)v1 + 1;
  if ( (unsigned __int64)v1 + 1 > 1 )
    return CloseHandle(v1);
  return result;
}

```

## disassembly

```asm
0x140004de4  sub     rsp, 28h
0x140004de8  mov     rcx, [rcx]; hObject
0x140004deb  lea     rax, [rcx+1]
0x140004def  cmp     rax, 1
0x140004df3  jbe     short loc_140004DFB
0x140004df5  call    cs:__imp_CloseHandle
0x140004dfb  add     rsp, 28h
0x140004dff  retn
```
