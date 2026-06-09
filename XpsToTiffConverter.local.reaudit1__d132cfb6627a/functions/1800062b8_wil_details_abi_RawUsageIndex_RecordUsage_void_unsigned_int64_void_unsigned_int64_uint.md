# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x1800062b8`
- end: `0x180006461`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180003940`
- `0x1800061b4`
- `0x1800061e8`

## callees

- `0x1800062b8`
- `0x180006468`
- `0x180008738`
- `0x18000885c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006375`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800063df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006412`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006375`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800063df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006412`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006367`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006404`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006367`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006404`

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
0x1800062b8  mov     [rsp+Buf1], rdx
0x1800062bd  push    rbx
0x1800062be  push    rbp
0x1800062bf  push    rsi
0x1800062c0  push    rdi
0x1800062c1  push    r12
0x1800062c3  push    r13
0x1800062c5  push    r14
0x1800062c7  push    r15
0x1800062c9  sub     rsp, 58h
0x1800062cd  mov     ebp, [rsp+98h+arg_28]
0x1800062d4  mov     r13, r9
0x1800062d7  mov     r12, [rsp+98h+arg_20]
0x1800062df  mov     r15, r8
0x1800062e2  mov     [rsp+98h+var_70], ebp; unsigned int
0x1800062e6  mov     rsi, rdx
0x1800062e9  mov     [rsp+98h+var_78], r12; unsigned __int64
0x1800062ee  mov     rbx, rcx
0x1800062f1  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1800062f6  test    al, al
0x1800062f8  jz      short loc_180006301
0x1800062fa  mov     al, 1
0x1800062fc  jmp     loc_180006442
0x180006301  lea     rdx, [r12+20h]
0x180006306  add     rdx, r15; unsigned __int64
0x180006309  lea     r14, [rbx+18h]
0x18000630d  cmp     qword ptr [r14], 0
0x180006311  jnz     loc_18000641A
0x180006317  xorps   xmm0, xmm0
0x18000631a  lea     rcx, [rsp+98h+var_68]; this
0x18000631f  xorps   xmm1, xmm1
0x180006322  add     rdx, 0Ah; unsigned __int64
0x180006326  movdqu  [rsp+98h+var_68], xmm0
0x18000632c  movdqu  [rsp+98h+var_58], xmm1
0x180006332  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180006337  test    al, al
0x180006339  jz      loc_1800063FA
0x18000633f  mov     rdi, qword ptr [rsp+98h+var_58]
0x180006344  mov     rsi, qword ptr [rsp+98h+var_68]
0x180006349  sub     rdi, rsi
0x18000634c  cmp     rdi, 0Ah
0x180006350  jb      loc_180006453
0x180006356  mov     rbp, [rbx+30h]
0x18000635a  mov     qword ptr [rbx+30h], 0
0x180006362  test    rbp, rbp
0x180006365  jz      short loc_18000637B
0x180006367  call    cs:__imp_GetProcessHeap
0x18000636d  mov     r8, rbp; lpMem
0x180006370  xor     edx, edx; dwFlags
0x180006372  mov     rcx, rax; hHeap
0x180006375  call    cs:__imp_HeapFree
0x18000637b  mov     [r14], rsi
0x18000637e  lea     rax, [rdi+rsi]
0x180006382  mov     [rbx+28h], rax
0x180006386  xor     edi, edi
0x180006388  xor     eax, eax
0x18000638a  mov     byte ptr [rbx+39h], 0
0x18000638e  mov     [rsi], ax
0x180006391  movzx   eax, word ptr [rbx]
0x180006394  mov     [rsi+2], ax
0x180006398  movzx   eax, word ptr [rbx+2]
0x18000639c  mov     [rsi+4], ax
0x1800063a0  mov     al, [rbx+4]
0x1800063a3  mov     [rsi+8], al
0x1800063a6  movzx   eax, word ptr [rbx+6]
0x1800063aa  mov     [rsi+6], ax
0x1800063ae  mov     al, [rbx+8]
0x1800063b1  mov     [rsi+9], al
0x1800063b4  mov     rax, [r14]
0x1800063b7  add     rax, 0Ah
0x1800063bb  mov     [rbx+20h], rax
0x1800063bf  mov     rsi, [rbx+30h]
0x1800063c3  mov     rax, qword ptr [rsp+98h+var_58+8]
0x1800063c8  mov     [rbx+30h], rax
0x1800063cc  test    rsi, rsi
0x1800063cf  jz      short loc_1800063E5
0x1800063d1  call    cs:__imp_GetProcessHeap
0x1800063d7  mov     r8, rsi; lpMem
0x1800063da  xor     edx, edx; dwFlags
0x1800063dc  mov     rcx, rax; hHeap
0x1800063df  call    cs:__imp_HeapFree
0x1800063e5  mov     rsi, [rsp+98h+Buf1]
0x1800063ed  mov     ebp, [rsp+98h+arg_28]
0x1800063f4  mov     byte ptr [rbx+3Ah], 1
0x1800063f8  jmp     short loc_1800063FF
0x1800063fa  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x1800063ff  test    rdi, rdi
0x180006402  jz      short loc_180006428
0x180006404  call    cs:__imp_GetProcessHeap
0x18000640a  mov     r8, rdi; lpMem
0x18000640d  xor     edx, edx; dwFlags
0x18000640f  mov     rcx, rax; hHeap
0x180006412  call    cs:__imp_HeapFree
0x180006418  jmp     short loc_180006428
0x18000641a  cmp     byte ptr [rbx+3Ah], 0
0x18000641e  jz      short loc_180006428
0x180006420  mov     rcx, r14; this
0x180006423  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180006428  mov     [rsp+98h+var_70], ebp; unsigned int
0x18000642c  mov     r9, r13; void *
0x18000642f  mov     r8, r15; Size
0x180006432  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180006437  mov     rdx, rsi; Buf1
0x18000643a  mov     rcx, rbx; this
0x18000643d  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180006442  add     rsp, 58h
0x180006446  pop     r15
0x180006448  pop     r14
0x18000644a  pop     r13
0x18000644c  pop     r12
0x18000644e  pop     rdi
0x18000644f  pop     rsi
0x180006450  pop     rbp
0x180006451  pop     rbx
0x180006452  retn
0x180006453  mov     rcx, [rsp+98h]; this
0x18000645b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
