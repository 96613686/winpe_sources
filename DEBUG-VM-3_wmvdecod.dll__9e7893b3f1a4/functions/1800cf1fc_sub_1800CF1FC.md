# sub_1800CF1FC

- ea: `0x1800cf1fc`
- end: `0x1800cf25a`
- name: `sub_1800CF1FC`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18007c210`

## callees

- `0x1800cecb0`
- `0x1800cf1fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800cf212`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800cf212`

## pseudocode

```c
void sub_1800CF1FC()
{
  char *v0; // rbx
  char *v1; // rcx

  if ( dword_18028FB98 )
  {
    DeleteCriticalSection(&stru_1802834F0);
    dword_18028FB98 = 0;
  }
  v0 = (char *)lpAddress;
  while ( v0 )
  {
    v1 = v0;
    v0 = (char *)*((_QWORD *)v0 + 8058);
    sub_1800CECB0(v1);
    --qword_1802834D0;
  }
  lpAddress = 0;
}

```

## disassembly

```asm
0x1800cf1fc  push    rbx
0x1800cf1fe  sub     rsp, 20h
0x1800cf202  cmp     cs:dword_18028FB98, 0
0x1800cf209  jz      short loc_1800CF228
0x1800cf20b  lea     rcx, stru_1802834F0; lpCriticalSection
0x1800cf212  call    cs:DeleteCriticalSection
0x1800cf219  nop     dword ptr [rax+rax+00h]
0x1800cf21e  mov     cs:dword_18028FB98, 0
0x1800cf228  mov     rbx, cs:lpAddress
0x1800cf22f  jmp     short loc_1800CF247
0x1800cf231  mov     rcx, rbx; lpAddress
0x1800cf234  mov     rbx, [rbx+0FBD0h]
0x1800cf23b  call    sub_1800CECB0
0x1800cf240  dec     cs:qword_1802834D0
0x1800cf247  test    rbx, rbx
0x1800cf24a  jnz     short loc_1800CF231
0x1800cf24c  mov     cs:lpAddress, rbx
0x1800cf253  add     rsp, 20h
0x1800cf257  pop     rbx
0x1800cf258  retn
```
