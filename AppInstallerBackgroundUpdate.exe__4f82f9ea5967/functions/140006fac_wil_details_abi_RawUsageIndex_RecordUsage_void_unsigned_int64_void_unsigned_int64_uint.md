# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x140006fac`
- end: `0x140007155`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140005f80`
- `0x140006ea8`
- `0x140006edc`

## callees

- `0x140006fac`
- `0x14000715c`
- `0x140008274`
- `0x1400082dc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000705b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400070c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400070f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000705b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400070c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400070f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007069`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400070d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007106`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007069`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400070d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007106`

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
0x140006fac  mov     [rsp+Buf1], rdx
0x140006fb1  push    rbx
0x140006fb2  push    rbp
0x140006fb3  push    rsi
0x140006fb4  push    rdi
0x140006fb5  push    r12
0x140006fb7  push    r13
0x140006fb9  push    r14
0x140006fbb  push    r15
0x140006fbd  sub     rsp, 58h
0x140006fc1  mov     ebp, [rsp+98h+arg_28]
0x140006fc8  mov     r13, r9
0x140006fcb  mov     r12, [rsp+98h+arg_20]
0x140006fd3  mov     r15, r8
0x140006fd6  mov     [rsp+98h+var_70], ebp; unsigned int
0x140006fda  mov     rsi, rdx
0x140006fdd  mov     [rsp+98h+var_78], r12; unsigned __int64
0x140006fe2  mov     rbx, rcx
0x140006fe5  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x140006fea  test    al, al
0x140006fec  jz      short loc_140006FF5
0x140006fee  mov     al, 1
0x140006ff0  jmp     loc_140007136
0x140006ff5  lea     rdx, [r12+20h]
0x140006ffa  add     rdx, r15; unsigned __int64
0x140006ffd  lea     r14, [rbx+18h]
0x140007001  cmp     qword ptr [r14], 0
0x140007005  jnz     loc_14000710E
0x14000700b  xorps   xmm0, xmm0
0x14000700e  lea     rcx, [rsp+98h+var_68]; this
0x140007013  xorps   xmm1, xmm1
0x140007016  add     rdx, 0Ah; unsigned __int64
0x14000701a  movdqu  [rsp+98h+var_68], xmm0
0x140007020  movdqu  [rsp+98h+var_58], xmm1
0x140007026  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000702b  test    al, al
0x14000702d  jz      loc_1400070EE
0x140007033  mov     rdi, qword ptr [rsp+98h+var_58]
0x140007038  mov     rsi, qword ptr [rsp+98h+var_68]
0x14000703d  sub     rdi, rsi
0x140007040  cmp     rdi, 0Ah
0x140007044  jb      loc_140007147
0x14000704a  mov     rbp, [rbx+30h]
0x14000704e  mov     qword ptr [rbx+30h], 0
0x140007056  test    rbp, rbp
0x140007059  jz      short loc_14000706F
0x14000705b  call    cs:__imp_GetProcessHeap
0x140007061  mov     r8, rbp; lpMem
0x140007064  xor     edx, edx; dwFlags
0x140007066  mov     rcx, rax; hHeap
0x140007069  call    cs:__imp_HeapFree
0x14000706f  mov     [r14], rsi
0x140007072  lea     rax, [rdi+rsi]
0x140007076  mov     [rbx+28h], rax
0x14000707a  xor     edi, edi
0x14000707c  xor     eax, eax
0x14000707e  mov     byte ptr [rbx+39h], 0
0x140007082  mov     [rsi], ax
0x140007085  movzx   eax, word ptr [rbx]
0x140007088  mov     [rsi+2], ax
0x14000708c  movzx   eax, word ptr [rbx+2]
0x140007090  mov     [rsi+4], ax
0x140007094  mov     al, [rbx+4]
0x140007097  mov     [rsi+8], al
0x14000709a  movzx   eax, word ptr [rbx+6]
0x14000709e  mov     [rsi+6], ax
0x1400070a2  mov     al, [rbx+8]
0x1400070a5  mov     [rsi+9], al
0x1400070a8  mov     rax, [r14]
0x1400070ab  add     rax, 0Ah
0x1400070af  mov     [rbx+20h], rax
0x1400070b3  mov     rsi, [rbx+30h]
0x1400070b7  mov     rax, qword ptr [rsp+98h+var_58+8]
0x1400070bc  mov     [rbx+30h], rax
0x1400070c0  test    rsi, rsi
0x1400070c3  jz      short loc_1400070D9
0x1400070c5  call    cs:__imp_GetProcessHeap
0x1400070cb  mov     r8, rsi; lpMem
0x1400070ce  xor     edx, edx; dwFlags
0x1400070d0  mov     rcx, rax; hHeap
0x1400070d3  call    cs:__imp_HeapFree
0x1400070d9  mov     rsi, [rsp+98h+Buf1]
0x1400070e1  mov     ebp, [rsp+98h+arg_28]
0x1400070e8  mov     byte ptr [rbx+3Ah], 1
0x1400070ec  jmp     short loc_1400070F3
0x1400070ee  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x1400070f3  test    rdi, rdi
0x1400070f6  jz      short loc_14000711C
0x1400070f8  call    cs:__imp_GetProcessHeap
0x1400070fe  mov     r8, rdi; lpMem
0x140007101  xor     edx, edx; dwFlags
0x140007103  mov     rcx, rax; hHeap
0x140007106  call    cs:__imp_HeapFree
0x14000710c  jmp     short loc_14000711C
0x14000710e  cmp     byte ptr [rbx+3Ah], 0
0x140007112  jz      short loc_14000711C
0x140007114  mov     rcx, r14; this
0x140007117  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000711c  mov     [rsp+98h+var_70], ebp; unsigned int
0x140007120  mov     r9, r13; void *
0x140007123  mov     r8, r15; Size
0x140007126  mov     [rsp+98h+var_78], r12; unsigned __int64
0x14000712b  mov     rdx, rsi; Buf1
0x14000712e  mov     rcx, rbx; this
0x140007131  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x140007136  add     rsp, 58h
0x14000713a  pop     r15
0x14000713c  pop     r14
0x14000713e  pop     r13
0x140007140  pop     r12
0x140007142  pop     rdi
0x140007143  pop     rsi
0x140007144  pop     rbp
0x140007145  pop     rbx
0x140007146  retn
0x140007147  mov     rcx, [rsp+98h]; this
0x14000714f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
