# sqlite3MemRealloc

- ea: `0x18009da70`
- end: `0x18009dac7`
- name: `sqlite3MemRealloc`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18009da70`
- `0x1800c5fb0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__msize` at `0x18009da99`
- `api-ms-win-crt-private-l1-1-0!_o__msize` at `0x18009da99`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x18009da88`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x18009da88`

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
0x18009da70  mov     [rsp+arg_0], rbx
0x18009da75  mov     [rsp+arg_8], rsi
0x18009da7a  push    rdi
0x18009da7b  sub     rsp, 20h
0x18009da7f  movsxd  rdi, edx
0x18009da82  mov     rsi, rcx
0x18009da85  mov     rdx, rdi
0x18009da88  call    cs:__imp__o_realloc
0x18009da8e  mov     rbx, rax
0x18009da91  test    rax, rax
0x18009da94  jnz     short loc_18009DAB4
0x18009da96  mov     rcx, rsi
0x18009da99  call    cs:__imp__o__msize
0x18009da9f  mov     r9d, edi
0x18009daa2  lea     rdx, aFailedMemoryRe; "failed memory resize %u to %u bytes"
0x18009daa9  mov     r8, rax
0x18009daac  lea     ecx, [rbx+7]
0x18009daaf  call    sqlite3_log
0x18009dab4  mov     rsi, [rsp+28h+arg_8]
0x18009dab9  mov     rax, rbx
0x18009dabc  mov     rbx, [rsp+28h+arg_0]
0x18009dac1  add     rsp, 20h
0x18009dac5  pop     rdi
0x18009dac6  retn
```
