# sqlite3MemRealloc

- ea: `0x18009c060`
- end: `0x18009c0b7`
- name: `sqlite3MemRealloc`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18009c060`
- `0x1800c5260`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__msize` at `0x18009c089`
- `api-ms-win-crt-private-l1-1-0!_o__msize` at `0x18009c089`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x18009c078`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x18009c078`

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
0x18009c060  mov     [rsp+arg_0], rbx
0x18009c065  mov     [rsp+arg_8], rsi
0x18009c06a  push    rdi
0x18009c06b  sub     rsp, 20h
0x18009c06f  movsxd  rdi, edx
0x18009c072  mov     rsi, rcx
0x18009c075  mov     rdx, rdi
0x18009c078  call    cs:__imp__o_realloc
0x18009c07e  mov     rbx, rax
0x18009c081  test    rax, rax
0x18009c084  jnz     short loc_18009C0A4
0x18009c086  mov     rcx, rsi
0x18009c089  call    cs:__imp__o__msize
0x18009c08f  mov     r9d, edi
0x18009c092  lea     rdx, aFailedMemoryRe; "failed memory resize %u to %u bytes"
0x18009c099  mov     r8, rax
0x18009c09c  lea     ecx, [rbx+7]
0x18009c09f  call    sqlite3_log
0x18009c0a4  mov     rsi, [rsp+28h+arg_8]
0x18009c0a9  mov     rax, rbx
0x18009c0ac  mov     rbx, [rsp+28h+arg_0]
0x18009c0b1  add     rsp, 20h
0x18009c0b5  pop     rdi
0x18009c0b6  retn
```
