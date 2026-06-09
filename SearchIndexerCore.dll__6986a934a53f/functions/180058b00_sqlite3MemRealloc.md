# sqlite3MemRealloc

- ea: `0x180058b00`
- end: `0x180058b5b`
- name: `sqlite3MemRealloc`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x1800257e0`
- `0x180058b00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__msize` at `0x180058b3c`
- `api-ms-win-crt-private-l1-1-0!_o__msize` at `0x180058b3c`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x180058b18`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x180058b18`

## pseudocode

```c
__int64 __fastcall sqlite3MemRealloc(__int64 a1, int a2)
{
  __int64 v4; // rbx
  int v6; // eax

  v4 = _o_realloc(a1, a2);
  if ( !v4 )
  {
    v6 = _o__msize(a1);
    sqlite3_log(7, "failed memory resize %u to %u bytes", v6, a2);
  }
  return v4;
}

```

## disassembly

```asm
0x180058b00  mov     [rsp+arg_0], rbx
0x180058b05  mov     [rsp+arg_8], rsi
0x180058b0a  push    rdi
0x180058b0b  sub     rsp, 20h
0x180058b0f  movsxd  rdi, edx
0x180058b12  mov     rsi, rcx
0x180058b15  mov     rdx, rdi
0x180058b18  call    cs:__imp__o_realloc
0x180058b1e  mov     rbx, rax
0x180058b21  test    rax, rax
0x180058b24  jz      short loc_180058B39
0x180058b26  mov     rsi, [rsp+28h+arg_8]
0x180058b2b  mov     rax, rbx
0x180058b2e  mov     rbx, [rsp+28h+arg_0]
0x180058b33  add     rsp, 20h
0x180058b37  pop     rdi
0x180058b38  retn
0x180058b39  mov     rcx, rsi
0x180058b3c  call    cs:__imp__o__msize
0x180058b42  mov     r9d, edi
0x180058b45  lea     rdx, aFailedMemoryRe; "failed memory resize %u to %u bytes"
0x180058b4c  mov     r8, rax
0x180058b4f  mov     ecx, 7
0x180058b54  call    sqlite3_log
0x180058b59  jmp     short loc_180058B26
```
