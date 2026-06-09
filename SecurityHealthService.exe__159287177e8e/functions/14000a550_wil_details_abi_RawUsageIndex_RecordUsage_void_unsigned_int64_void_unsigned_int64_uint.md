# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x14000a550`
- end: `0x14000a71f`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `463`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1400085a0`
- `0x14000a44c`
- `0x14000a480`

## callees

- `0x140006f10`
- `0x14000a550`
- `0x14000a728`
- `0x14000c63c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a60d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a67d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a6b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a60d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a67d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a6b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a5ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a66f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a6a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a5ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a66f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a6a2`

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
  unsigned __int64 v12; // rcx
  __int64 *v13; // rdi
  void *v14; // rdx
  unsigned int v15; // r8d
  const char *v16; // r9
  __int64 v17; // r14
  __int64 v18; // rsi
  void *v19; // rbp
  HANDLE ProcessHeap; // rax
  __int64 v21; // rax
  void *v22; // rdi
  void *v23; // rsi
  HANDLE v24; // rax
  HANDLE v25; // rax
  unsigned __int64 v26; // rdx
  unsigned __int64 v27; // rdx
  __int128 v28; // [rsp+30h] [rbp-68h] BYREF
  __int128 v29; // [rsp+40h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v6 = a6;
  v9 = a2;
  if ( wil::details_abi::RawUsageIndex::RecordUsageInternal(this, a2, a3, a4, a5, a6) )
    return 1;
  v12 = a3 + a5 + 32;
  v13 = (__int64 *)((char *)this + 24);
  if ( *((_QWORD *)this + 3) )
  {
    if ( *((_BYTE *)this + 58) )
    {
      v26 = *((_QWORD *)this + 5) - *((_QWORD *)this + 3);
      if ( v12 + *((_QWORD *)this + 4) - *((_QWORD *)this + 3) >= v26 )
      {
        v27 = 2 * v26;
        if ( v12 >= v27 )
          v27 = a3 + a5 + 32;
        wil::details_abi::heap_buffer::reserve((wil::details_abi::RawUsageIndex *)((char *)this + 24), v27);
      }
    }
  }
  else
  {
    v28 = 0;
    v29 = 0;
    if ( wil::details_abi::heap_buffer::reserve((wil::details_abi::heap_buffer *)&v28, v12 + 10) )
    {
      v17 = v28;
      v18 = v29 - v28;
      if ( (_QWORD)v29 - (_QWORD)v28 < 0xAu )
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
      *((_BYTE *)this + 57) = 0;
      *(_WORD *)v17 = 0;
      *(_WORD *)(v17 + 2) = *(_WORD *)this;
      *(_WORD *)(v17 + 4) = *((_WORD *)this + 1);
      *(_BYTE *)(v17 + 8) = *((_BYTE *)this + 4);
      *(_WORD *)(v17 + 6) = *((_WORD *)this + 3);
      *(_BYTE *)(v17 + 9) = *((_BYTE *)this + 8);
      v21 = *v13;
      v22 = 0;
      *((_QWORD *)this + 4) = v21 + 10;
      v23 = (void *)*((_QWORD *)this + 6);
      *((_QWORD *)this + 6) = *((_QWORD *)&v29 + 1);
      if ( v23 )
      {
        v24 = GetProcessHeap();
        HeapFree(v24, 0, v23);
      }
      v9 = a2;
      v6 = a6;
      *((_BYTE *)this + 58) = 1;
    }
    else
    {
      v22 = (void *)*((_QWORD *)&v29 + 1);
    }
    if ( v22 )
    {
      v25 = GetProcessHeap();
      HeapFree(v25, 0, v22);
    }
  }
  return wil::details_abi::RawUsageIndex::RecordUsageInternal(this, v9, a3, a4, a5, v6);
}

```

## disassembly

```asm
0x14000a550  mov     [rsp+Buf1], rdx
0x14000a555  push    rbx
0x14000a556  push    rbp
0x14000a557  push    rsi
0x14000a558  push    rdi
0x14000a559  push    r12
0x14000a55b  push    r13
0x14000a55d  push    r14
0x14000a55f  push    r15
0x14000a561  sub     rsp, 58h
0x14000a565  mov     ebp, [rsp+98h+arg_28]
0x14000a56c  mov     r13, r9
0x14000a56f  mov     r12, [rsp+98h+arg_20]
0x14000a577  mov     r15, r8
0x14000a57a  mov     [rsp+98h+var_70], ebp; unsigned int
0x14000a57e  mov     rsi, rdx
0x14000a581  mov     [rsp+98h+var_78], r12; unsigned __int64
0x14000a586  mov     rbx, rcx
0x14000a589  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x14000a58e  test    al, al
0x14000a590  jz      short loc_14000A599
0x14000a592  mov     al, 1
0x14000a594  jmp     loc_14000A700
0x14000a599  lea     rcx, [r12+20h]
0x14000a59e  add     rcx, r15
0x14000a5a1  lea     rdi, [rbx+18h]
0x14000a5a5  cmp     qword ptr [rdi], 0
0x14000a5a9  jnz     loc_14000A6B8
0x14000a5af  xorps   xmm0, xmm0
0x14000a5b2  lea     rdx, [rcx+0Ah]; unsigned __int64
0x14000a5b6  xorps   xmm1, xmm1
0x14000a5b9  lea     rcx, [rsp+98h+var_68]; this
0x14000a5be  movdqu  [rsp+98h+var_68], xmm0
0x14000a5c4  movdqu  [rsp+98h+var_58], xmm1
0x14000a5ca  call    ?reserve@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::reserve(unsigned __int64)
0x14000a5cf  test    al, al
0x14000a5d1  jz      loc_14000A698
0x14000a5d7  mov     rsi, qword ptr [rsp+98h+var_58]
0x14000a5dc  mov     r14, qword ptr [rsp+98h+var_68]
0x14000a5e1  sub     rsi, r14
0x14000a5e4  cmp     rsi, 0Ah
0x14000a5e8  jb      loc_14000A711
0x14000a5ee  mov     rbp, [rbx+30h]
0x14000a5f2  mov     qword ptr [rbx+30h], 0
0x14000a5fa  test    rbp, rbp
0x14000a5fd  jz      short loc_14000A613
0x14000a5ff  call    cs:__imp_GetProcessHeap
0x14000a605  mov     r8, rbp; lpMem
0x14000a608  xor     edx, edx; dwFlags
0x14000a60a  mov     rcx, rax; hHeap
0x14000a60d  call    cs:__imp_HeapFree
0x14000a613  mov     [rdi], r14
0x14000a616  lea     rax, [rsi+r14]
0x14000a61a  mov     [rbx+28h], rax
0x14000a61e  xor     eax, eax
0x14000a620  mov     byte ptr [rbx+39h], 0
0x14000a624  mov     [r14], ax
0x14000a628  movzx   eax, word ptr [rbx]
0x14000a62b  mov     [r14+2], ax
0x14000a630  movzx   eax, word ptr [rbx+2]
0x14000a634  mov     [r14+4], ax
0x14000a639  mov     al, [rbx+4]
0x14000a63c  mov     [r14+8], al
0x14000a640  movzx   eax, word ptr [rbx+6]
0x14000a644  mov     [r14+6], ax
0x14000a649  mov     al, [rbx+8]
0x14000a64c  mov     [r14+9], al
0x14000a650  mov     rax, [rdi]
0x14000a653  xor     edi, edi
0x14000a655  add     rax, 0Ah
0x14000a659  mov     [rbx+20h], rax
0x14000a65d  mov     rsi, [rbx+30h]
0x14000a661  mov     rax, qword ptr [rsp+98h+var_58+8]
0x14000a666  mov     [rbx+30h], rax
0x14000a66a  test    rsi, rsi
0x14000a66d  jz      short loc_14000A683
0x14000a66f  call    cs:__imp_GetProcessHeap
0x14000a675  mov     r8, rsi; lpMem
0x14000a678  xor     edx, edx; dwFlags
0x14000a67a  mov     rcx, rax; hHeap
0x14000a67d  call    cs:__imp_HeapFree
0x14000a683  mov     rsi, [rsp+98h+Buf1]
0x14000a68b  mov     ebp, [rsp+98h+arg_28]
0x14000a692  mov     byte ptr [rbx+3Ah], 1
0x14000a696  jmp     short loc_14000A69D
0x14000a698  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x14000a69d  test    rdi, rdi
0x14000a6a0  jz      short loc_14000A6E6
0x14000a6a2  call    cs:__imp_GetProcessHeap
0x14000a6a8  mov     r8, rdi; lpMem
0x14000a6ab  xor     edx, edx; dwFlags
0x14000a6ad  mov     rcx, rax; hHeap
0x14000a6b0  call    cs:__imp_HeapFree
0x14000a6b6  jmp     short loc_14000A6E6
0x14000a6b8  cmp     byte ptr [rbx+3Ah], 0
0x14000a6bc  jz      short loc_14000A6E6
0x14000a6be  mov     rax, [rdi+8]
0x14000a6c2  sub     rax, [rdi]
0x14000a6c5  mov     rdx, [rdi+10h]
0x14000a6c9  add     rax, rcx
0x14000a6cc  sub     rdx, [rdi]
0x14000a6cf  cmp     rax, rdx
0x14000a6d2  jb      short loc_14000A6E6
0x14000a6d4  add     rdx, rdx
0x14000a6d7  cmp     rcx, rdx
0x14000a6da  cmovnb  rdx, rcx; unsigned __int64
0x14000a6de  mov     rcx, rdi; this
0x14000a6e1  call    ?reserve@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::reserve(unsigned __int64)
0x14000a6e6  mov     [rsp+98h+var_70], ebp; unsigned int
0x14000a6ea  mov     r9, r13; void *
0x14000a6ed  mov     r8, r15; Size
0x14000a6f0  mov     [rsp+98h+var_78], r12; unsigned __int64
0x14000a6f5  mov     rdx, rsi; Buf1
0x14000a6f8  mov     rcx, rbx; this
0x14000a6fb  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x14000a700  add     rsp, 58h
0x14000a704  pop     r15
0x14000a706  pop     r14
0x14000a708  pop     r13
0x14000a70a  pop     r12
0x14000a70c  pop     rdi
0x14000a70d  pop     rsi
0x14000a70e  pop     rbp
0x14000a70f  pop     rbx
0x14000a710  retn
0x14000a711  mov     rcx, [rsp+98h]; this
0x14000a719  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
