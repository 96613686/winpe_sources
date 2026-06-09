# sqlite3MemRealloc

- ea: `0x18004c7e0`
- end: `0x18004c83b`
- name: `sqlite3MemRealloc`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x1800275f0`
- `0x18004c7e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__msize` at `0x18004c819`
- `api-ms-win-crt-private-l1-1-0!_o__msize` at `0x18004c819`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x18004c7f8`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x18004c7f8`

## pseudocode

```c
__int64 __fastcall sqlite3MemRealloc(__int64 a1, int a2)
{
  __int64 result; // rax
  int v5; // eax

  result = _o_realloc(a1, a2);
  if ( !result )
  {
    v5 = _o__msize(a1);
    sqlite3_log(7, "failed memory resize %u to %u bytes", v5, a2);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18004c7e0  mov     [rsp+arg_0], rbx
0x18004c7e5  mov     [rsp+arg_8], rsi
0x18004c7ea  push    rdi
0x18004c7eb  sub     rsp, 20h
0x18004c7ef  movsxd  rdi, edx
0x18004c7f2  mov     rsi, rcx
0x18004c7f5  mov     rdx, rdi
0x18004c7f8  call    cs:__imp__o_realloc
0x18004c7fe  mov     rbx, rax
0x18004c801  test    rax, rax
0x18004c804  jz      short loc_18004C816
0x18004c806  mov     rbx, [rsp+28h+arg_0]
0x18004c80b  mov     rsi, [rsp+28h+arg_8]
0x18004c810  add     rsp, 20h
0x18004c814  pop     rdi
0x18004c815  retn
0x18004c816  mov     rcx, rsi
0x18004c819  call    cs:__imp__o__msize
0x18004c81f  mov     r9d, edi
0x18004c822  lea     rdx, aFailedMemoryRe; "failed memory resize %u to %u bytes"
0x18004c829  mov     r8, rax
0x18004c82c  mov     ecx, 7
0x18004c831  call    sqlite3_log
0x18004c836  mov     rax, rbx
0x18004c839  jmp     short loc_18004C806
```
