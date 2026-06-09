# Concurrency::streams::details::streambuf_state_manager<uchar>::streambuf_state_manager<uchar>(int)

- ea: `0x18002416c`
- end: `0x1800241d1`
- name: `??0?$streambuf_state_manager@E@details@streams@Concurrency@@IEAA@H@Z`
- size: `101`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18002403c`
- `0x180033298`
- `0x180033368`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800241a8`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800241a8`

## pseudocode

```c
__int64 __fastcall Concurrency::streams::details::streambuf_state_manager<unsigned char>::streambuf_state_manager<unsigned char>(
        __int64 a1,
        char a2)
{
  _QWORD *v4; // rcx

  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)a1 = &Concurrency::streams::details::streambuf_state_manager<unsigned char>::`vftable';
  v4 = (_QWORD *)(a1 + 24);
  v4[1] = 0;
  *v4 = 0;
  __ExceptionPtrCreate(v4);
  *(_WORD *)(a1 + 42) = 0;
  *(_BYTE *)(a1 + 40) = a2 & 1;
  *(_BYTE *)(a1 + 41) = (a2 & 2) != 0;
  return a1;
}

```

## disassembly

```asm
0x18002416c  mov     [rsp+arg_0], rbx
0x180024171  push    rdi
0x180024172  sub     rsp, 20h
0x180024176  mov     qword ptr [rcx+8], 0
0x18002417e  lea     rax, ??_7?$streambuf_state_manager@E@details@streams@Concurrency@@6B@; const Concurrency::streams::details::streambuf_state_manager<uchar>::`vftable'
0x180024185  mov     qword ptr [rcx+10h], 0
0x18002418d  mov     rdi, rcx
0x180024190  mov     [rcx], rax
0x180024193  mov     ebx, edx
0x180024195  add     rcx, 18h
0x180024199  mov     qword ptr [rcx+8], 0
0x1800241a1  mov     qword ptr [rcx], 0
0x1800241a8  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800241ae  mov     eax, ebx
0x1800241b0  mov     word ptr [rdi+2Ah], 0
0x1800241b6  and     al, 1
0x1800241b8  shr     ebx, 1
0x1800241ba  and     bl, 1
0x1800241bd  mov     [rdi+28h], al
0x1800241c0  mov     [rdi+29h], bl
0x1800241c3  mov     rax, rdi
0x1800241c6  mov     rbx, [rsp+28h+arg_0]
0x1800241cb  add     rsp, 20h
0x1800241cf  pop     rdi
0x1800241d0  retn
```
