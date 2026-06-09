# sqlite3MemRealloc

- ea: `0x18007a8f0`
- end: `0x18007a947`
- name: `sqlite3MemRealloc`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18007a8f0`
- `0x1800a2e30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__msize` at `0x18007a919`
- `api-ms-win-crt-private-l1-1-0!_o__msize` at `0x18007a919`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x18007a908`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x18007a908`

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
0x18007a8f0  mov     [rsp+arg_0], rbx
0x18007a8f5  mov     [rsp+arg_8], rsi
0x18007a8fa  push    rdi
0x18007a8fb  sub     rsp, 20h
0x18007a8ff  movsxd  rdi, edx
0x18007a902  mov     rsi, rcx
0x18007a905  mov     rdx, rdi
0x18007a908  call    cs:__imp__o_realloc
0x18007a90e  mov     rbx, rax
0x18007a911  test    rax, rax
0x18007a914  jnz     short loc_18007A934
0x18007a916  mov     rcx, rsi
0x18007a919  call    cs:__imp__o__msize
0x18007a91f  mov     r9d, edi
0x18007a922  lea     rdx, aFailedMemoryRe; "failed memory resize %u to %u bytes"
0x18007a929  mov     r8, rax
0x18007a92c  lea     ecx, [rbx+7]
0x18007a92f  call    sqlite3_log
0x18007a934  mov     rsi, [rsp+28h+arg_8]
0x18007a939  mov     rax, rbx
0x18007a93c  mov     rbx, [rsp+28h+arg_0]
0x18007a941  add     rsp, 20h
0x18007a945  pop     rdi
0x18007a946  retn
```
