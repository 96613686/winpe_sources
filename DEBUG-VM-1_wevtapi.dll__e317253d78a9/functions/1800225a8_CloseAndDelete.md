# CloseAndDelete

- ea: `0x1800225a8`
- end: `0x180022653`
- name: `CloseAndDelete`
- size: `171`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800310a8`
- `0x180031754`

## callees

- `0x18001585c`
- `0x1800225a8`
- `0x180022d7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800225d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022614`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800225d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022614`
- `api-ms-win-core-file-l2-1-0!ReOpenFile` at `0x1800225c1`
- `api-ms-win-core-file-l2-1-0!ReOpenFile` at `0x180022600`
- `api-ms-win-core-file-l2-1-0!ReOpenFile` at `0x1800225c1`
- `api-ms-win-core-file-l2-1-0!ReOpenFile` at `0x180022600`

## pseudocode

```c
__int64 __fastcall CloseAndDelete(HANDLE *a1)
{
  char *v2; // rbx
  DWORD LastError; // ebx
  char *v5; // [rsp+30h] [rbp+8h] BYREF
  char *v6; // [rsp+38h] [rbp+10h] BYREF

  v2 = (char *)ReOpenFile(*a1, 0, 7u, 0);
  v6 = v2;
  if ( v2 == (char *)-1LL || v2 + 1 == (char *)1 )
  {
    LastError = GetLastError();
  }
  else
  {
    tlx::unique_any<tlx::file_handle_traits>::reset(a1, 0);
    v5 = (char *)ReOpenFile(v2, 0x10000u, 7u, 0x4000000u);
    if ( v5 == (char *)-1LL || v5 + 1 == (char *)1 )
    {
      LastError = GetLastError();
      tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v5);
    }
    else
    {
      tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v5);
      LastError = 0;
    }
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v6);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(a1);
  return LastError;
}

```

## disassembly

```asm
0x1800225a8  mov     [rsp+arg_10], rbx
0x1800225ad  push    rdi
0x1800225ae  sub     rsp, 20h
0x1800225b2  xor     r9d, r9d; dwFlagsAndAttributes
0x1800225b5  mov     rdi, rcx
0x1800225b8  mov     rcx, [rcx]; hOriginalFile
0x1800225bb  xor     edx, edx; dwDesiredAccess
0x1800225bd  lea     r8d, [r9+7]; dwShareMode
0x1800225c1  call    cs:__imp_ReOpenFile
0x1800225c7  mov     rbx, rax
0x1800225ca  mov     [rsp+28h+arg_8], rax
0x1800225cf  inc     rax
0x1800225d2  cmp     rax, 1
0x1800225d6  ja      short loc_1800225E2
0x1800225d8  call    cs:__imp_GetLastError
0x1800225de  mov     ebx, eax
0x1800225e0  jmp     short loc_180022634
0x1800225e2  xor     edx, edx
0x1800225e4  mov     rcx, rdi
0x1800225e7  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x1800225ec  mov     edx, 10000h; dwDesiredAccess
0x1800225f1  mov     r9d, 4000000h; dwFlagsAndAttributes
0x1800225f7  mov     r8d, 7; dwShareMode
0x1800225fd  mov     rcx, rbx; hOriginalFile
0x180022600  call    cs:__imp_ReOpenFile
0x180022606  mov     [rsp+28h+arg_0], rax
0x18002260b  inc     rax
0x18002260e  cmp     rax, 1
0x180022612  ja      short loc_180022628
0x180022614  call    cs:__imp_GetLastError
0x18002261a  lea     rcx, [rsp+28h+arg_0]
0x18002261f  mov     ebx, eax
0x180022621  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180022626  jmp     short loc_180022634
0x180022628  lea     rcx, [rsp+28h+arg_0]
0x18002262d  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180022632  xor     ebx, ebx
0x180022634  lea     rcx, [rsp+28h+arg_8]
0x180022639  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18002263e  mov     rcx, rdi
0x180022641  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180022646  mov     eax, ebx
0x180022648  mov     rbx, [rsp+28h+arg_10]
0x18002264d  add     rsp, 20h
0x180022651  pop     rdi
0x180022652  retn
```
