# sqlite3MemRealloc

- ea: `0x140063200`
- end: `0x140063257`
- name: `sqlite3MemRealloc`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x140063200`
- `0x14008b740`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__msize` at `0x140063229`
- `api-ms-win-crt-private-l1-1-0!_o__msize` at `0x140063229`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x140063218`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x140063218`

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
0x140063200  mov     [rsp+arg_0], rbx
0x140063205  mov     [rsp+arg_8], rsi
0x14006320a  push    rdi
0x14006320b  sub     rsp, 20h
0x14006320f  movsxd  rdi, edx
0x140063212  mov     rsi, rcx
0x140063215  mov     rdx, rdi
0x140063218  call    cs:__imp__o_realloc
0x14006321e  mov     rbx, rax
0x140063221  test    rax, rax
0x140063224  jnz     short loc_140063244
0x140063226  mov     rcx, rsi
0x140063229  call    cs:__imp__o__msize
0x14006322f  mov     r9d, edi
0x140063232  lea     rdx, aFailedMemoryRe; "failed memory resize %u to %u bytes"
0x140063239  mov     r8, rax
0x14006323c  lea     ecx, [rbx+7]
0x14006323f  call    sqlite3_log
0x140063244  mov     rsi, [rsp+28h+arg_8]
0x140063249  mov     rax, rbx
0x14006324c  mov     rbx, [rsp+28h+arg_0]
0x140063251  add     rsp, 20h
0x140063255  pop     rdi
0x140063256  retn
```
