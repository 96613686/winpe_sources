# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180008110`
- end: `0x1800082b9`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800058d0`
- `0x180008010`
- `0x180008044`

## callees

- `0x180008110`
- `0x1800082c0`
- `0x180009cc8`
- `0x180009d2c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800081cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008237`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000826a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800081cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008237`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000826a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800081bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008229`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000825c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800081bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008229`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000825c`

## pseudocode

```c
bool __fastcall wil::details_abi::RawUsageIndex::RecordUsage(
        wil::details_abi::RawUsageIndex *this,
        void *a2,
        size_t a3,
        void *a4,
        unsigned __int64 a5,
        unsigned int a6)
{
  unsigned int v6; // ebp
  void *v9; // rsi
  unsigned __int64 v12; // rdx
  _QWORD *v13; // r14
  void *v14; // rdx
  unsigned int v15; // r8d
  const char *v16; // r9
  __int64 v17; // rsi
  __int64 v18; // rdi
  void *v19; // rbp
  HANDLE ProcessHeap; // rax
  void *v21; // rdi
  void *v22; // rsi
  HANDLE v23; // rax
  HANDLE v24; // rax
  __int128 v25; // [rsp+30h] [rbp-68h] BYREF
  __int128 v26; // [rsp+40h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v6 = a6;
  v9 = a2;
  if ( wil::details_abi::RawUsageIndex::RecordUsageInternal(this, a2, a3, a4, a5, a6) )
    return 1;
  v12 = a3 + a5 + 32;
  v13 = (_QWORD *)((char *)this + 24);
  if ( *((_QWORD *)this + 3) )
  {
    if ( *((_BYTE *)this + 58) )
      wil::details_abi::heap_buffer::ensure((wil::details_abi::RawUsageIndex *)((char *)this + 24), v12);
  }
  else
  {
    v25 = 0;
    v26 = 0;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&v25, v12 + 10) )
    {
      v17 = v25;
      v18 = v26 - v25;
      if ( (_QWORD)v26 - (_QWORD)v25 < 0xAu )
        wil::details::in1diag3::_FailFast_Unexpected(retaddr, v14, v15, v16);
      v19 = (void *)*((_QWORD *)this + 6);
      *((_QWORD *)this + 6) = 0;
      if ( v19 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v19);
      }
      *v13 = v17;
      *((_QWORD *)this + 5) = v18 + v17;
      v21 = 0;
      *((_BYTE *)this + 57) = 0;
      *(_WORD *)v17 = 0;
      *(_WORD *)(v17 + 2) = *(_WORD *)this;
      *(_WORD *)(v17 + 4) = *((_WORD *)this + 1);
      *(_BYTE *)(v17 + 8) = *((_BYTE *)this + 4);
      *(_WORD *)(v17 + 6) = *((_WORD *)this + 3);
      *(_BYTE *)(v17 + 9) = *((_BYTE *)this + 8);
      *((_QWORD *)this + 4) = *v13 + 10LL;
      v22 = (void *)*((_QWORD *)this + 6);
      *((_QWORD *)this + 6) = *((_QWORD *)&v26 + 1);
      if ( v22 )
      {
        v23 = GetProcessHeap();
        HeapFree(v23, 0, v22);
      }
      v9 = a2;
      v6 = a6;
      *((_BYTE *)this + 58) = 1;
    }
    else
    {
      v21 = (void *)*((_QWORD *)&v26 + 1);
    }
    if ( v21 )
    {
      v24 = GetProcessHeap();
      HeapFree(v24, 0, v21);
    }
  }
  return wil::details_abi::RawUsageIndex::RecordUsageInternal(this, v9, a3, a4, a5, v6);
}

```

## disassembly

```asm
0x180008110  mov     [rsp+Buf1], rdx
0x180008115  push    rbx
0x180008116  push    rbp
0x180008117  push    rsi
0x180008118  push    rdi
0x180008119  push    r12
0x18000811b  push    r13
0x18000811d  push    r14
0x18000811f  push    r15
0x180008121  sub     rsp, 58h
0x180008125  mov     ebp, [rsp+98h+arg_28]
0x18000812c  mov     r13, r9
0x18000812f  mov     r12, [rsp+98h+arg_20]
0x180008137  mov     r15, r8
0x18000813a  mov     [rsp+98h+var_70], ebp; unsigned int
0x18000813e  mov     rsi, rdx
0x180008141  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180008146  mov     rbx, rcx
0x180008149  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000814e  test    al, al
0x180008150  jz      short loc_180008159
0x180008152  mov     al, 1
0x180008154  jmp     loc_18000829A
0x180008159  lea     rdx, [r12+20h]
0x18000815e  add     rdx, r15; unsigned __int64
0x180008161  lea     r14, [rbx+18h]
0x180008165  cmp     qword ptr [r14], 0
0x180008169  jnz     loc_180008272
0x18000816f  xorps   xmm0, xmm0
0x180008172  lea     rcx, [rsp+98h+var_68]; this
0x180008177  xorps   xmm1, xmm1
0x18000817a  add     rdx, 0Ah; unsigned __int64
0x18000817e  movdqu  [rsp+98h+var_68], xmm0
0x180008184  movdqu  [rsp+98h+var_58], xmm1
0x18000818a  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000818f  test    al, al
0x180008191  jz      loc_180008252
0x180008197  mov     rdi, qword ptr [rsp+98h+var_58]
0x18000819c  mov     rsi, qword ptr [rsp+98h+var_68]
0x1800081a1  sub     rdi, rsi
0x1800081a4  cmp     rdi, 0Ah
0x1800081a8  jb      loc_1800082AB
0x1800081ae  mov     rbp, [rbx+30h]
0x1800081b2  mov     qword ptr [rbx+30h], 0
0x1800081ba  test    rbp, rbp
0x1800081bd  jz      short loc_1800081D3
0x1800081bf  call    cs:__imp_GetProcessHeap
0x1800081c5  mov     r8, rbp; lpMem
0x1800081c8  xor     edx, edx; dwFlags
0x1800081ca  mov     rcx, rax; hHeap
0x1800081cd  call    cs:__imp_HeapFree
0x1800081d3  mov     [r14], rsi
0x1800081d6  lea     rax, [rdi+rsi]
0x1800081da  mov     [rbx+28h], rax
0x1800081de  xor     edi, edi
0x1800081e0  xor     eax, eax
0x1800081e2  mov     byte ptr [rbx+39h], 0
0x1800081e6  mov     [rsi], ax
0x1800081e9  movzx   eax, word ptr [rbx]
0x1800081ec  mov     [rsi+2], ax
0x1800081f0  movzx   eax, word ptr [rbx+2]
0x1800081f4  mov     [rsi+4], ax
0x1800081f8  mov     al, [rbx+4]
0x1800081fb  mov     [rsi+8], al
0x1800081fe  movzx   eax, word ptr [rbx+6]
0x180008202  mov     [rsi+6], ax
0x180008206  mov     al, [rbx+8]
0x180008209  mov     [rsi+9], al
0x18000820c  mov     rax, [r14]
0x18000820f  add     rax, 0Ah
0x180008213  mov     [rbx+20h], rax
0x180008217  mov     rsi, [rbx+30h]
0x18000821b  mov     rax, qword ptr [rsp+98h+var_58+8]
0x180008220  mov     [rbx+30h], rax
0x180008224  test    rsi, rsi
0x180008227  jz      short loc_18000823D
0x180008229  call    cs:__imp_GetProcessHeap
0x18000822f  mov     r8, rsi; lpMem
0x180008232  xor     edx, edx; dwFlags
0x180008234  mov     rcx, rax; hHeap
0x180008237  call    cs:__imp_HeapFree
0x18000823d  mov     rsi, [rsp+98h+Buf1]
0x180008245  mov     ebp, [rsp+98h+arg_28]
0x18000824c  mov     byte ptr [rbx+3Ah], 1
0x180008250  jmp     short loc_180008257
0x180008252  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x180008257  test    rdi, rdi
0x18000825a  jz      short loc_180008280
0x18000825c  call    cs:__imp_GetProcessHeap
0x180008262  mov     r8, rdi; lpMem
0x180008265  xor     edx, edx; dwFlags
0x180008267  mov     rcx, rax; hHeap
0x18000826a  call    cs:__imp_HeapFree
0x180008270  jmp     short loc_180008280
0x180008272  cmp     byte ptr [rbx+3Ah], 0
0x180008276  jz      short loc_180008280
0x180008278  mov     rcx, r14; this
0x18000827b  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180008280  mov     [rsp+98h+var_70], ebp; unsigned int
0x180008284  mov     r9, r13; void *
0x180008287  mov     r8, r15; Size
0x18000828a  mov     [rsp+98h+var_78], r12; unsigned __int64
0x18000828f  mov     rdx, rsi; Buf1
0x180008292  mov     rcx, rbx; this
0x180008295  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000829a  add     rsp, 58h
0x18000829e  pop     r15
0x1800082a0  pop     r14
0x1800082a2  pop     r13
0x1800082a4  pop     r12
0x1800082a6  pop     rdi
0x1800082a7  pop     rsi
0x1800082a8  pop     rbp
0x1800082a9  pop     rbx
0x1800082aa  retn
0x1800082ab  mov     rcx, [rsp+98h]; this
0x1800082b3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
