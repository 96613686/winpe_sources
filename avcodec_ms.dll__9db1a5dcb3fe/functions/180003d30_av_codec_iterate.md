# av_codec_iterate

- ea: `0x180003d30`
- end: `0x180003daf`
- name: `av_codec_iterate`
- size: `127`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003e0c`
- `0x180003e84`
- `0x18000e6e0`

## callees

- `0x180003c28`
- `0x180003d30`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180003d68`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180003d68`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180003d86`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180003d86`

## pseudocode

```c
char **__fastcall av_codec_iterate(__int64 *a1)
{
  __int64 v1; // rsi
  char **v3; // rbx
  char **result; // rax
  BOOL v5; // [rsp+30h] [rbp+8h] BYREF

  v1 = *a1;
  v5 = 0;
  v3 = off_180025D00[v1];
  InitOnceBeginInitialize(&InitOnce, 0, &v5, 0);
  if ( v5 )
    sub_180003C28();
  InitOnceComplete(&InitOnce, 0, 0);
  if ( !v3 )
    return 0;
  result = v3;
  *a1 = v1 + 1;
  return result;
}

```

## disassembly

```asm
0x180003d30  mov     rax, rsp
0x180003d33  mov     [rax+10h], rbx
0x180003d37  mov     [rax+18h], rsi
0x180003d3b  push    rdi
0x180003d3c  sub     rsp, 20h
0x180003d40  mov     rsi, [rcx]
0x180003d43  lea     rbx, off_180025D00
0x180003d4a  mov     rdi, rcx
0x180003d4d  mov     dword ptr [rax+8], 0
0x180003d54  xor     r9d, r9d; lpContext
0x180003d57  lea     r8, [rax+8]; fPending
0x180003d5b  xor     edx, edx; dwFlags
0x180003d5d  lea     rcx, InitOnce; lpInitOnce
0x180003d64  mov     rbx, [rbx+rsi*8]
0x180003d68  call    cs:InitOnceBeginInitialize
0x180003d6e  cmp     [rsp+28h+arg_0], 0
0x180003d73  jz      short loc_180003D7A
0x180003d75  call    sub_180003C28
0x180003d7a  xor     r8d, r8d; lpContext
0x180003d7d  lea     rcx, InitOnce; lpInitOnce
0x180003d84  xor     edx, edx; dwFlags
0x180003d86  call    cs:InitOnceComplete
0x180003d8c  test    rbx, rbx
0x180003d8f  jz      short loc_180003D9D
0x180003d91  lea     rcx, [rsi+1]
0x180003d95  mov     rax, rbx
0x180003d98  mov     [rdi], rcx
0x180003d9b  jmp     short loc_180003D9F
0x180003d9d  xor     eax, eax
0x180003d9f  mov     rbx, [rsp+28h+arg_8]
0x180003da4  mov     rsi, [rsp+28h+arg_10]
0x180003da9  add     rsp, 20h
0x180003dad  pop     rdi
0x180003dae  retn
```
