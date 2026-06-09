# sqlite3MemRealloc

- ea: `0x1800862b0`
- end: `0x180086307`
- name: `sqlite3MemRealloc`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18003af40`
- `0x1800862b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__msize` at `0x1800862d9`
- `api-ms-win-crt-private-l1-1-0!_o__msize` at `0x1800862d9`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x1800862c8`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x1800862c8`

## pseudocode

```c
__int64 __fastcall sqlite3MemRealloc(__int64 a1, int a2)
{
  __int64 v4; // rbx
  int v5; // eax

  v4 = _o_realloc(a1, a2);
  if ( !v4 )
  {
    v5 = _o__msize(a1);
    sqlite3_log(7, "failed memory resize %u to %u bytes", v5, a2);
  }
  return v4;
}

```

## disassembly

```asm
0x1800862b0  mov     [rsp+arg_0], rbx
0x1800862b5  mov     [rsp+arg_8], rsi
0x1800862ba  push    rdi
0x1800862bb  sub     rsp, 20h
0x1800862bf  movsxd  rdi, edx
0x1800862c2  mov     rsi, rcx
0x1800862c5  mov     rdx, rdi
0x1800862c8  call    cs:__imp__o_realloc
0x1800862ce  mov     rbx, rax
0x1800862d1  test    rax, rax
0x1800862d4  jnz     short loc_1800862F4
0x1800862d6  mov     rcx, rsi
0x1800862d9  call    cs:__imp__o__msize
0x1800862df  mov     r9d, edi
0x1800862e2  lea     rdx, aFailedMemoryRe; "failed memory resize %u to %u bytes"
0x1800862e9  mov     r8, rax
0x1800862ec  lea     ecx, [rbx+7]
0x1800862ef  call    sqlite3_log
0x1800862f4  mov     rsi, [rsp+28h+arg_8]
0x1800862f9  mov     rax, rbx
0x1800862fc  mov     rbx, [rsp+28h+arg_0]
0x180086301  add     rsp, 20h
0x180086305  pop     rdi
0x180086306  retn
```
