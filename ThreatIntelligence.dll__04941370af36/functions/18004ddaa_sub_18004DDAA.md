# sub_18004DDAA

- ea: `0x18004ddaa`
- end: `0x18004de03`
- name: `sub_18004DDAA`
- size: `89`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800251f4`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18004ddc8`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18004ddc8`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18004ddd2`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18004ddd2`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18004ddea`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18004ddea`

## pseudocode

```c
__int64 __fastcall sub_18004DDAA(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx

  v3 = *(_QWORD *)(a2 + 32);
  *(_OWORD *)(a2 + 48) = 0;
  __ExceptionPtrCreate((void *)(a2 + 48));
  __ExceptionPtrCurrentException((void *)(a2 + 48));
  sub_1800251F4(v3, (const void *)(a2 + 48));
  __ExceptionPtrDestroy((void *)(a2 + 48));
  return 0;
}

```

## disassembly

```asm
0x18004ddaa  mov     [rsp+arg_8], rdx
0x18004ddaf  push    rbx
0x18004ddb0  push    rbp
0x18004ddb1  sub     rsp, 28h
0x18004ddb5  mov     rbp, rdx
0x18004ddb8  mov     rbx, [rbp+20h]
0x18004ddbc  xorps   xmm0, xmm0
0x18004ddbf  movdqu  xmmword ptr [rbp+30h], xmm0
0x18004ddc4  lea     rcx, [rbp+30h]
0x18004ddc8  call    cs:?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18004ddce  lea     rcx, [rbp+30h]
0x18004ddd2  call    cs:?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18004ddd8  nop
0x18004ddd9  lea     rdx, [rbp+30h]
0x18004dddd  mov     rcx, rbx
0x18004dde0  call    sub_1800251F4
0x18004dde5  nop
0x18004dde6  lea     rcx, [rbp+30h]
0x18004ddea  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18004ddf0  nop
0x18004ddf1  mov     rax, 0
0x18004ddfb  add     rsp, 28h
0x18004ddff  pop     rbp
0x18004de00  pop     rbx
0x18004de01  retn
```
