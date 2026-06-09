# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x140006698`
- end: `0x140006841`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140003900`
- `0x140006594`
- `0x1400065c8`

## callees

- `0x140006698`
- `0x140006848`
- `0x140008b18`
- `0x140008c3c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006747`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400067b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400067e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006747`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400067b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400067e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006755`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400067bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400067f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006755`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400067bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400067f2`

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
0x140006698  mov     [rsp+Buf1], rdx
0x14000669d  push    rbx
0x14000669e  push    rbp
0x14000669f  push    rsi
0x1400066a0  push    rdi
0x1400066a1  push    r12
0x1400066a3  push    r13
0x1400066a5  push    r14
0x1400066a7  push    r15
0x1400066a9  sub     rsp, 58h
0x1400066ad  mov     ebp, [rsp+98h+arg_28]
0x1400066b4  mov     r13, r9
0x1400066b7  mov     r12, [rsp+98h+arg_20]
0x1400066bf  mov     r15, r8
0x1400066c2  mov     [rsp+98h+var_70], ebp; unsigned int
0x1400066c6  mov     rsi, rdx
0x1400066c9  mov     [rsp+98h+var_78], r12; unsigned __int64
0x1400066ce  mov     rbx, rcx
0x1400066d1  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1400066d6  test    al, al
0x1400066d8  jz      short loc_1400066E1
0x1400066da  mov     al, 1
0x1400066dc  jmp     loc_140006822
0x1400066e1  lea     rdx, [r12+20h]
0x1400066e6  add     rdx, r15; unsigned __int64
0x1400066e9  lea     r14, [rbx+18h]
0x1400066ed  cmp     qword ptr [r14], 0
0x1400066f1  jnz     loc_1400067FA
0x1400066f7  xorps   xmm0, xmm0
0x1400066fa  lea     rcx, [rsp+98h+var_68]; this
0x1400066ff  xorps   xmm1, xmm1
0x140006702  add     rdx, 0Ah; unsigned __int64
0x140006706  movdqu  [rsp+98h+var_68], xmm0
0x14000670c  movdqu  [rsp+98h+var_58], xmm1
0x140006712  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140006717  test    al, al
0x140006719  jz      loc_1400067DA
0x14000671f  mov     rdi, qword ptr [rsp+98h+var_58]
0x140006724  mov     rsi, qword ptr [rsp+98h+var_68]
0x140006729  sub     rdi, rsi
0x14000672c  cmp     rdi, 0Ah
0x140006730  jb      loc_140006833
0x140006736  mov     rbp, [rbx+30h]
0x14000673a  mov     qword ptr [rbx+30h], 0
0x140006742  test    rbp, rbp
0x140006745  jz      short loc_14000675B
0x140006747  call    cs:__imp_GetProcessHeap
0x14000674d  mov     r8, rbp; lpMem
0x140006750  xor     edx, edx; dwFlags
0x140006752  mov     rcx, rax; hHeap
0x140006755  call    cs:__imp_HeapFree
0x14000675b  mov     [r14], rsi
0x14000675e  lea     rax, [rdi+rsi]
0x140006762  mov     [rbx+28h], rax
0x140006766  xor     edi, edi
0x140006768  xor     eax, eax
0x14000676a  mov     byte ptr [rbx+39h], 0
0x14000676e  mov     [rsi], ax
0x140006771  movzx   eax, word ptr [rbx]
0x140006774  mov     [rsi+2], ax
0x140006778  movzx   eax, word ptr [rbx+2]
0x14000677c  mov     [rsi+4], ax
0x140006780  mov     al, [rbx+4]
0x140006783  mov     [rsi+8], al
0x140006786  movzx   eax, word ptr [rbx+6]
0x14000678a  mov     [rsi+6], ax
0x14000678e  mov     al, [rbx+8]
0x140006791  mov     [rsi+9], al
0x140006794  mov     rax, [r14]
0x140006797  add     rax, 0Ah
0x14000679b  mov     [rbx+20h], rax
0x14000679f  mov     rsi, [rbx+30h]
0x1400067a3  mov     rax, qword ptr [rsp+98h+var_58+8]
0x1400067a8  mov     [rbx+30h], rax
0x1400067ac  test    rsi, rsi
0x1400067af  jz      short loc_1400067C5
0x1400067b1  call    cs:__imp_GetProcessHeap
0x1400067b7  mov     r8, rsi; lpMem
0x1400067ba  xor     edx, edx; dwFlags
0x1400067bc  mov     rcx, rax; hHeap
0x1400067bf  call    cs:__imp_HeapFree
0x1400067c5  mov     rsi, [rsp+98h+Buf1]
0x1400067cd  mov     ebp, [rsp+98h+arg_28]
0x1400067d4  mov     byte ptr [rbx+3Ah], 1
0x1400067d8  jmp     short loc_1400067DF
0x1400067da  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x1400067df  test    rdi, rdi
0x1400067e2  jz      short loc_140006808
0x1400067e4  call    cs:__imp_GetProcessHeap
0x1400067ea  mov     r8, rdi; lpMem
0x1400067ed  xor     edx, edx; dwFlags
0x1400067ef  mov     rcx, rax; hHeap
0x1400067f2  call    cs:__imp_HeapFree
0x1400067f8  jmp     short loc_140006808
0x1400067fa  cmp     byte ptr [rbx+3Ah], 0
0x1400067fe  jz      short loc_140006808
0x140006800  mov     rcx, r14; this
0x140006803  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140006808  mov     [rsp+98h+var_70], ebp; unsigned int
0x14000680c  mov     r9, r13; void *
0x14000680f  mov     r8, r15; Size
0x140006812  mov     [rsp+98h+var_78], r12; unsigned __int64
0x140006817  mov     rdx, rsi; Buf1
0x14000681a  mov     rcx, rbx; this
0x14000681d  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x140006822  add     rsp, 58h
0x140006826  pop     r15
0x140006828  pop     r14
0x14000682a  pop     r13
0x14000682c  pop     r12
0x14000682e  pop     rdi
0x14000682f  pop     rsi
0x140006830  pop     rbp
0x140006831  pop     rbx
0x140006832  retn
0x140006833  mov     rcx, [rsp+98h]; this
0x14000683b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
