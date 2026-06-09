# sqlite3MemRealloc

- ea: `0x180080900`
- end: `0x180080957`
- name: `sqlite3MemRealloc`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180080900`
- `0x1800a70c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__msize` at `0x180080929`
- `api-ms-win-crt-private-l1-1-0!_o__msize` at `0x180080929`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x180080918`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x180080918`

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
0x180080900  mov     [rsp+arg_0], rbx
0x180080905  mov     [rsp+arg_8], rsi
0x18008090a  push    rdi
0x18008090b  sub     rsp, 20h
0x18008090f  movsxd  rdi, edx
0x180080912  mov     rsi, rcx
0x180080915  mov     rdx, rdi
0x180080918  call    cs:__imp__o_realloc
0x18008091e  mov     rbx, rax
0x180080921  test    rax, rax
0x180080924  jnz     short loc_180080944
0x180080926  mov     rcx, rsi
0x180080929  call    cs:__imp__o__msize
0x18008092f  mov     r9d, edi
0x180080932  lea     rdx, aFailedMemoryRe; "failed memory resize %u to %u bytes"
0x180080939  mov     r8, rax
0x18008093c  lea     ecx, [rbx+7]
0x18008093f  call    sqlite3_log
0x180080944  mov     rsi, [rsp+28h+arg_8]
0x180080949  mov     rax, rbx
0x18008094c  mov     rbx, [rsp+28h+arg_0]
0x180080951  add     rsp, 20h
0x180080955  pop     rdi
0x180080956  retn
```
