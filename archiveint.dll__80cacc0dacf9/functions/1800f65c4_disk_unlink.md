# disk_unlink

- ea: `0x1800f65c4`
- end: `0x1800f6614`
- name: `disk_unlink`
- size: `80`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800f4c10`
- `0x1800f5838`
- `0x1800f5e24`
- `0x1800f6098`
- `0x1800f6a50`
- `0x1800f7330`

## callees

- `0x1800ef3f8`
- `0x1800f65c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wunlink` at `0x1800f65d1`
- `api-ms-win-crt-private-l1-1-0!_o__wunlink` at `0x1800f65f6`
- `api-ms-win-crt-private-l1-1-0!_o__wunlink` at `0x1800f65d1`
- `api-ms-win-crt-private-l1-1-0!_o__wunlink` at `0x1800f65f6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f6601`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f6601`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f65dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f65dd`

## pseudocode

```c
__int64 __fastcall disk_unlink(LPCWSTR lpFileName)
{
  unsigned int v2; // edi
  void *v3; // rbx

  v2 = ((__int64 (*)(void))_o__wunlink)();
  if ( v2 && GetLastError() == 123 )
  {
    v3 = (void *)_la_win_permissive_name_w(lpFileName);
    v2 = _o__wunlink(v3);
    free(v3);
  }
  return v2;
}

```

## disassembly

```asm
0x1800f65c4  mov     [rsp+arg_0], rbx
0x1800f65c9  push    rdi
0x1800f65ca  sub     rsp, 20h
0x1800f65ce  mov     rbx, rcx
0x1800f65d1  call    cs:__imp__o__wunlink
0x1800f65d7  mov     edi, eax
0x1800f65d9  test    eax, eax
0x1800f65db  jz      short loc_1800F6607
0x1800f65dd  call    cs:__imp_GetLastError
0x1800f65e3  cmp     eax, 7Bh ; '{'
0x1800f65e6  jnz     short loc_1800F6607
0x1800f65e8  mov     rcx, rbx; lpFileName
0x1800f65eb  call    __la_win_permissive_name_w
0x1800f65f0  mov     rcx, rax
0x1800f65f3  mov     rbx, rax
0x1800f65f6  call    cs:__imp__o__wunlink
0x1800f65fc  mov     rcx, rbx; Block
0x1800f65ff  mov     edi, eax
0x1800f6601  call    cs:__imp_free
0x1800f6607  mov     rbx, [rsp+28h+arg_0]
0x1800f660c  mov     eax, edi
0x1800f660e  add     rsp, 20h
0x1800f6612  pop     rdi
0x1800f6613  retn
```
