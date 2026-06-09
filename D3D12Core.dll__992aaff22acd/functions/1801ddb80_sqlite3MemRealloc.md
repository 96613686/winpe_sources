# sqlite3MemRealloc

- ea: `0x1801ddb80`
- end: `0x1801ddbd7`
- name: `sqlite3MemRealloc`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x1801ddb80`
- `0x180205320`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__msize` at `0x1801ddba9`
- `api-ms-win-crt-private-l1-1-0!_o__msize` at `0x1801ddba9`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x1801ddb98`
- `api-ms-win-crt-private-l1-1-0!_o_realloc` at `0x1801ddb98`

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
0x1801ddb80  mov     [rsp+arg_0], rbx
0x1801ddb85  mov     [rsp+arg_8], rsi
0x1801ddb8a  push    rdi
0x1801ddb8b  sub     rsp, 20h
0x1801ddb8f  movsxd  rdi, edx
0x1801ddb92  mov     rsi, rcx
0x1801ddb95  mov     rdx, rdi
0x1801ddb98  call    cs:__imp__o_realloc
0x1801ddb9e  mov     rbx, rax
0x1801ddba1  test    rax, rax
0x1801ddba4  jnz     short loc_1801DDBC4
0x1801ddba6  mov     rcx, rsi
0x1801ddba9  call    cs:__imp__o__msize
0x1801ddbaf  mov     r9d, edi
0x1801ddbb2  lea     rdx, aFailedMemoryRe; "failed memory resize %u to %u bytes"
0x1801ddbb9  mov     r8, rax
0x1801ddbbc  lea     ecx, [rbx+7]
0x1801ddbbf  call    sqlite3_log
0x1801ddbc4  mov     rsi, [rsp+28h+arg_8]
0x1801ddbc9  mov     rax, rbx
0x1801ddbcc  mov     rbx, [rsp+28h+arg_0]
0x1801ddbd1  add     rsp, 20h
0x1801ddbd5  pop     rdi
0x1801ddbd6  retn
```
