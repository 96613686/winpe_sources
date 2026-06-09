# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x14000c5f8`
- end: `0x14000c7a1`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140008f40`
- `0x14000c4f4`
- `0x14000c528`

## callees

- `0x14000c5f8`
- `0x14000c7a8`
- `0x14000ed00`
- `0x14000f454`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c6b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c71f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c752`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c6b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c71f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c752`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c6a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c711`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c744`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c6a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c711`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c744`

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
0x14000c5f8  mov     [rsp+Buf1], rdx
0x14000c5fd  push    rbx
0x14000c5fe  push    rbp
0x14000c5ff  push    rsi
0x14000c600  push    rdi
0x14000c601  push    r12
0x14000c603  push    r13
0x14000c605  push    r14
0x14000c607  push    r15
0x14000c609  sub     rsp, 58h
0x14000c60d  mov     ebp, [rsp+98h+arg_28]
0x14000c614  mov     r13, r9
0x14000c617  mov     r12, [rsp+98h+arg_20]
0x14000c61f  mov     r15, r8
0x14000c622  mov     [rsp+98h+var_70], ebp; unsigned int
0x14000c626  mov     rsi, rdx
0x14000c629  mov     [rsp+98h+var_78], r12; unsigned __int64
0x14000c62e  mov     rbx, rcx
0x14000c631  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x14000c636  test    al, al
0x14000c638  jz      short loc_14000C641
0x14000c63a  mov     al, 1
0x14000c63c  jmp     loc_14000C782
0x14000c641  lea     rdx, [r12+20h]
0x14000c646  add     rdx, r15; unsigned __int64
0x14000c649  lea     r14, [rbx+18h]
0x14000c64d  cmp     qword ptr [r14], 0
0x14000c651  jnz     loc_14000C75A
0x14000c657  xorps   xmm0, xmm0
0x14000c65a  lea     rcx, [rsp+98h+var_68]; this
0x14000c65f  xorps   xmm1, xmm1
0x14000c662  add     rdx, 0Ah; unsigned __int64
0x14000c666  movdqu  [rsp+98h+var_68], xmm0
0x14000c66c  movdqu  [rsp+98h+var_58], xmm1
0x14000c672  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000c677  test    al, al
0x14000c679  jz      loc_14000C73A
0x14000c67f  mov     rdi, qword ptr [rsp+98h+var_58]
0x14000c684  mov     rsi, qword ptr [rsp+98h+var_68]
0x14000c689  sub     rdi, rsi
0x14000c68c  cmp     rdi, 0Ah
0x14000c690  jb      loc_14000C793
0x14000c696  mov     rbp, [rbx+30h]
0x14000c69a  mov     qword ptr [rbx+30h], 0
0x14000c6a2  test    rbp, rbp
0x14000c6a5  jz      short loc_14000C6BB
0x14000c6a7  call    cs:__imp_GetProcessHeap
0x14000c6ad  mov     r8, rbp; lpMem
0x14000c6b0  xor     edx, edx; dwFlags
0x14000c6b2  mov     rcx, rax; hHeap
0x14000c6b5  call    cs:__imp_HeapFree
0x14000c6bb  mov     [r14], rsi
0x14000c6be  lea     rax, [rdi+rsi]
0x14000c6c2  mov     [rbx+28h], rax
0x14000c6c6  xor     edi, edi
0x14000c6c8  xor     eax, eax
0x14000c6ca  mov     byte ptr [rbx+39h], 0
0x14000c6ce  mov     [rsi], ax
0x14000c6d1  movzx   eax, word ptr [rbx]
0x14000c6d4  mov     [rsi+2], ax
0x14000c6d8  movzx   eax, word ptr [rbx+2]
0x14000c6dc  mov     [rsi+4], ax
0x14000c6e0  mov     al, [rbx+4]
0x14000c6e3  mov     [rsi+8], al
0x14000c6e6  movzx   eax, word ptr [rbx+6]
0x14000c6ea  mov     [rsi+6], ax
0x14000c6ee  mov     al, [rbx+8]
0x14000c6f1  mov     [rsi+9], al
0x14000c6f4  mov     rax, [r14]
0x14000c6f7  add     rax, 0Ah
0x14000c6fb  mov     [rbx+20h], rax
0x14000c6ff  mov     rsi, [rbx+30h]
0x14000c703  mov     rax, qword ptr [rsp+98h+var_58+8]
0x14000c708  mov     [rbx+30h], rax
0x14000c70c  test    rsi, rsi
0x14000c70f  jz      short loc_14000C725
0x14000c711  call    cs:__imp_GetProcessHeap
0x14000c717  mov     r8, rsi; lpMem
0x14000c71a  xor     edx, edx; dwFlags
0x14000c71c  mov     rcx, rax; hHeap
0x14000c71f  call    cs:__imp_HeapFree
0x14000c725  mov     rsi, [rsp+98h+Buf1]
0x14000c72d  mov     ebp, [rsp+98h+arg_28]
0x14000c734  mov     byte ptr [rbx+3Ah], 1
0x14000c738  jmp     short loc_14000C73F
0x14000c73a  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x14000c73f  test    rdi, rdi
0x14000c742  jz      short loc_14000C768
0x14000c744  call    cs:__imp_GetProcessHeap
0x14000c74a  mov     r8, rdi; lpMem
0x14000c74d  xor     edx, edx; dwFlags
0x14000c74f  mov     rcx, rax; hHeap
0x14000c752  call    cs:__imp_HeapFree
0x14000c758  jmp     short loc_14000C768
0x14000c75a  cmp     byte ptr [rbx+3Ah], 0
0x14000c75e  jz      short loc_14000C768
0x14000c760  mov     rcx, r14; this
0x14000c763  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000c768  mov     [rsp+98h+var_70], ebp; unsigned int
0x14000c76c  mov     r9, r13; void *
0x14000c76f  mov     r8, r15; Size
0x14000c772  mov     [rsp+98h+var_78], r12; unsigned __int64
0x14000c777  mov     rdx, rsi; Buf1
0x14000c77a  mov     rcx, rbx; this
0x14000c77d  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x14000c782  add     rsp, 58h
0x14000c786  pop     r15
0x14000c788  pop     r14
0x14000c78a  pop     r13
0x14000c78c  pop     r12
0x14000c78e  pop     rdi
0x14000c78f  pop     rsi
0x14000c790  pop     rbp
0x14000c791  pop     rbx
0x14000c792  retn
0x14000c793  mov     rcx, [rsp+98h]; this
0x14000c79b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
