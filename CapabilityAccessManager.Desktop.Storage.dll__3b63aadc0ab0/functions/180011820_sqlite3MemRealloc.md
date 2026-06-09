# sqlite3MemRealloc

- ea: `0x180011820`
- end: `0x180011879`
- name: `sqlite3MemRealloc`
- size: `89`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180011820`
- `0x180016970`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__msize` at `0x180011849`
- `api-ms-win-crt-private-l1-1-0!_o__msize` at `0x180011849`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x180011838`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x180011838`

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
0x180011820  mov     [rsp+arg_0], rbx
0x180011825  mov     [rsp+arg_8], rsi
0x18001182a  push    rdi
0x18001182b  sub     rsp, 20h
0x18001182f  movsxd  rdi, edx
0x180011832  mov     rsi, rcx
0x180011835  mov     rdx, rdi
0x180011838  call    cs:__imp__o_realloc
0x18001183e  mov     rbx, rax
0x180011841  test    rax, rax
0x180011844  jnz     short loc_180011869
0x180011846  mov     rcx, rsi
0x180011849  call    cs:__imp__o__msize
0x18001184f  mov     r9d, edi
0x180011852  lea     rdx, aFailedMemoryRe; "failed memory resize %u to %u bytes"
0x180011859  mov     r8, rax
0x18001185c  mov     ecx, 7
0x180011861  call    sqlite3_log
0x180011866  mov     rax, rbx
0x180011869  mov     rbx, [rsp+28h+arg_0]
0x18001186e  mov     rsi, [rsp+28h+arg_8]
0x180011873  add     rsp, 20h
0x180011877  pop     rdi
0x180011878  retn
```
