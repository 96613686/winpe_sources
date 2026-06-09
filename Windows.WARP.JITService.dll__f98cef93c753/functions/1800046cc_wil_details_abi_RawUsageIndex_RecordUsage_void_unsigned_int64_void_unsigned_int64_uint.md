# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x1800046cc`
- end: `0x180004881`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `437`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180007510`
- `0x180007544`
- `0x180007b10`

## callees

- `0x180002e70`
- `0x180004224`
- `0x1800046cc`
- `0x180004888`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004789`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800047f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004826`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004789`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800047f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004826`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000477b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800047e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004818`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000477b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800047e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004818`

## pseudocode

```c
bool __fastcall wil::details_abi::RawUsageIndex::RecordUsage(
        wil::details_abi::RawUsageIndex *this,
        void *a2,
        unsigned __int64 a3,
        void *a4,
        unsigned __int64 a5,
        unsigned int a6)
{
  unsigned int v6; // ebp
  void *v9; // rsi
  unsigned __int64 v12; // rdx
  _QWORD *v13; // r14
  const char *v14; // r9
  __int64 v15; // rsi
  __int64 v16; // rdi
  void *v17; // rbp
  HANDLE ProcessHeap; // rax
  void *v19; // rdi
  void *v20; // rsi
  HANDLE v21; // rax
  HANDLE v22; // rax
  __int128 v23; // [rsp+30h] [rbp-68h] BYREF
  __int128 v24; // [rsp+40h] [rbp-58h]
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
    v23 = 0;
    v24 = 0;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&v23, v12 + 10) )
    {
      v15 = v23;
      v16 = v24 - v23;
      if ( (_QWORD)v24 - (_QWORD)v23 < 0xAu )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          5321,
          (__int64)"onecore\\internal\\sdk\\inc\\wil\\Staging.h",
          v14);
      v17 = (void *)*((_QWORD *)this + 6);
      *((_QWORD *)this + 6) = 0;
      if ( v17 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v17);
      }
      *v13 = v15;
      *((_QWORD *)this + 5) = v16 + v15;
      v19 = 0;
      *((_BYTE *)this + 57) = 0;
      *(_WORD *)v15 = 0;
      *(_WORD *)(v15 + 2) = *(_WORD *)this;
      *(_WORD *)(v15 + 4) = *((_WORD *)this + 1);
      *(_BYTE *)(v15 + 8) = *((_BYTE *)this + 4);
      *(_WORD *)(v15 + 6) = *((_WORD *)this + 3);
      *(_BYTE *)(v15 + 9) = *((_BYTE *)this + 8);
      *((_QWORD *)this + 4) = *v13 + 10LL;
      v20 = (void *)*((_QWORD *)this + 6);
      *((_QWORD *)this + 6) = *((_QWORD *)&v24 + 1);
      if ( v20 )
      {
        v21 = GetProcessHeap();
        HeapFree(v21, 0, v20);
      }
      v9 = a2;
      v6 = a6;
      *((_BYTE *)this + 58) = 1;
    }
    else
    {
      v19 = (void *)*((_QWORD *)&v24 + 1);
    }
    if ( v19 )
    {
      v22 = GetProcessHeap();
      HeapFree(v22, 0, v19);
    }
  }
  return wil::details_abi::RawUsageIndex::RecordUsageInternal(this, v9, a3, a4, a5, v6);
}

```

## disassembly

```asm
0x1800046cc  mov     [rsp+arg_8], rdx
0x1800046d1  push    rbx
0x1800046d2  push    rbp
0x1800046d3  push    rsi
0x1800046d4  push    rdi
0x1800046d5  push    r12
0x1800046d7  push    r13
0x1800046d9  push    r14
0x1800046db  push    r15
0x1800046dd  sub     rsp, 58h
0x1800046e1  mov     ebp, [rsp+98h+arg_28]
0x1800046e8  mov     r13, r9
0x1800046eb  mov     r12, [rsp+98h+arg_20]
0x1800046f3  mov     r15, r8
0x1800046f6  mov     [rsp+98h+var_70], ebp; unsigned int
0x1800046fa  mov     rsi, rdx
0x1800046fd  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180004702  mov     rbx, rcx
0x180004705  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000470a  test    al, al
0x18000470c  jz      short loc_180004715
0x18000470e  mov     al, 1
0x180004710  jmp     loc_180004856
0x180004715  lea     rdx, [r12+20h]
0x18000471a  add     rdx, r15; unsigned __int64
0x18000471d  lea     r14, [rbx+18h]
0x180004721  cmp     qword ptr [r14], 0
0x180004725  jnz     loc_18000482E
0x18000472b  xorps   xmm0, xmm0
0x18000472e  lea     rcx, [rsp+98h+var_68]; this
0x180004733  xorps   xmm1, xmm1
0x180004736  add     rdx, 0Ah; unsigned __int64
0x18000473a  movdqu  [rsp+98h+var_68], xmm0
0x180004740  movdqu  [rsp+98h+var_58], xmm1
0x180004746  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000474b  test    al, al
0x18000474d  jz      loc_18000480E
0x180004753  mov     rdi, qword ptr [rsp+98h+var_58]
0x180004758  mov     rsi, qword ptr [rsp+98h+var_68]
0x18000475d  sub     rdi, rsi
0x180004760  cmp     rdi, 0Ah
0x180004764  jb      loc_180004867
0x18000476a  mov     rbp, [rbx+30h]
0x18000476e  mov     qword ptr [rbx+30h], 0
0x180004776  test    rbp, rbp
0x180004779  jz      short loc_18000478F
0x18000477b  call    cs:__imp_GetProcessHeap
0x180004781  mov     r8, rbp; lpMem
0x180004784  xor     edx, edx; dwFlags
0x180004786  mov     rcx, rax; hHeap
0x180004789  call    cs:__imp_HeapFree
0x18000478f  mov     [r14], rsi
0x180004792  lea     rax, [rdi+rsi]
0x180004796  mov     [rbx+28h], rax
0x18000479a  xor     edi, edi
0x18000479c  xor     eax, eax
0x18000479e  mov     byte ptr [rbx+39h], 0
0x1800047a2  mov     [rsi], ax
0x1800047a5  movzx   eax, word ptr [rbx]
0x1800047a8  mov     [rsi+2], ax
0x1800047ac  movzx   eax, word ptr [rbx+2]
0x1800047b0  mov     [rsi+4], ax
0x1800047b4  mov     al, [rbx+4]
0x1800047b7  mov     [rsi+8], al
0x1800047ba  movzx   eax, word ptr [rbx+6]
0x1800047be  mov     [rsi+6], ax
0x1800047c2  mov     al, [rbx+8]
0x1800047c5  mov     [rsi+9], al
0x1800047c8  mov     rax, [r14]
0x1800047cb  add     rax, 0Ah
0x1800047cf  mov     [rbx+20h], rax
0x1800047d3  mov     rsi, [rbx+30h]
0x1800047d7  mov     rax, qword ptr [rsp+98h+var_58+8]
0x1800047dc  mov     [rbx+30h], rax
0x1800047e0  test    rsi, rsi
0x1800047e3  jz      short loc_1800047F9
0x1800047e5  call    cs:__imp_GetProcessHeap
0x1800047eb  mov     r8, rsi; lpMem
0x1800047ee  xor     edx, edx; dwFlags
0x1800047f0  mov     rcx, rax; hHeap
0x1800047f3  call    cs:__imp_HeapFree
0x1800047f9  mov     rsi, [rsp+98h+arg_8]
0x180004801  mov     ebp, [rsp+98h+arg_28]
0x180004808  mov     byte ptr [rbx+3Ah], 1
0x18000480c  jmp     short loc_180004813
0x18000480e  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x180004813  test    rdi, rdi
0x180004816  jz      short loc_18000483C
0x180004818  call    cs:__imp_GetProcessHeap
0x18000481e  mov     r8, rdi; lpMem
0x180004821  xor     edx, edx; dwFlags
0x180004823  mov     rcx, rax; hHeap
0x180004826  call    cs:__imp_HeapFree
0x18000482c  jmp     short loc_18000483C
0x18000482e  cmp     byte ptr [rbx+3Ah], 0
0x180004832  jz      short loc_18000483C
0x180004834  mov     rcx, r14; this
0x180004837  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000483c  mov     [rsp+98h+var_70], ebp; unsigned int
0x180004840  mov     r9, r13; void *
0x180004843  mov     r8, r15; unsigned __int64
0x180004846  mov     [rsp+98h+var_78], r12; unsigned __int64
0x18000484b  mov     rdx, rsi; void *
0x18000484e  mov     rcx, rbx; this
0x180004851  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180004856  add     rsp, 58h
0x18000485a  pop     r15
0x18000485c  pop     r14
0x18000485e  pop     r13
0x180004860  pop     r12
0x180004862  pop     rdi
0x180004863  pop     rsi
0x180004864  pop     rbp
0x180004865  pop     rbx
0x180004866  retn
0x180004867  mov     rcx, [rsp+98h]; this
0x18000486f  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Stagi"...
0x180004876  mov     edx, 14C9h; void *
0x18000487b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
