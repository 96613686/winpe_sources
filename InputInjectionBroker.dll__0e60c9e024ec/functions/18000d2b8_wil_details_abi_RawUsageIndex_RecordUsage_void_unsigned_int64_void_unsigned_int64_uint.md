# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18000d2b8`
- end: `0x18000d461`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180009dc0`
- `0x18000d1b4`
- `0x18000d1e8`

## callees

- `0x18000d2b8`
- `0x18000d468`
- `0x18000e9bc`
- `0x18000ea2c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d367`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d3d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d404`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d367`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d3d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d404`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d375`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d3df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d412`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d375`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d3df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d412`

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
0x18000d2b8  mov     [rsp+Buf1], rdx
0x18000d2bd  push    rbx
0x18000d2be  push    rbp
0x18000d2bf  push    rsi
0x18000d2c0  push    rdi
0x18000d2c1  push    r12
0x18000d2c3  push    r13
0x18000d2c5  push    r14
0x18000d2c7  push    r15
0x18000d2c9  sub     rsp, 58h
0x18000d2cd  mov     ebp, [rsp+98h+arg_28]
0x18000d2d4  mov     r13, r9
0x18000d2d7  mov     r12, [rsp+98h+arg_20]
0x18000d2df  mov     r15, r8
0x18000d2e2  mov     [rsp+98h+var_70], ebp; unsigned int
0x18000d2e6  mov     rsi, rdx
0x18000d2e9  mov     [rsp+98h+var_78], r12; unsigned __int64
0x18000d2ee  mov     rbx, rcx
0x18000d2f1  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000d2f6  test    al, al
0x18000d2f8  jz      short loc_18000D301
0x18000d2fa  mov     al, 1
0x18000d2fc  jmp     loc_18000D442
0x18000d301  lea     rdx, [r12+20h]
0x18000d306  add     rdx, r15; unsigned __int64
0x18000d309  lea     r14, [rbx+18h]
0x18000d30d  cmp     qword ptr [r14], 0
0x18000d311  jnz     loc_18000D41A
0x18000d317  xorps   xmm0, xmm0
0x18000d31a  lea     rcx, [rsp+98h+var_68]; this
0x18000d31f  xorps   xmm1, xmm1
0x18000d322  add     rdx, 0Ah; unsigned __int64
0x18000d326  movdqu  [rsp+98h+var_68], xmm0
0x18000d32c  movdqu  [rsp+98h+var_58], xmm1
0x18000d332  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000d337  test    al, al
0x18000d339  jz      loc_18000D3FA
0x18000d33f  mov     rdi, qword ptr [rsp+98h+var_58]
0x18000d344  mov     rsi, qword ptr [rsp+98h+var_68]
0x18000d349  sub     rdi, rsi
0x18000d34c  cmp     rdi, 0Ah
0x18000d350  jb      loc_18000D453
0x18000d356  mov     rbp, [rbx+30h]
0x18000d35a  mov     qword ptr [rbx+30h], 0
0x18000d362  test    rbp, rbp
0x18000d365  jz      short loc_18000D37B
0x18000d367  call    cs:__imp_GetProcessHeap
0x18000d36d  mov     r8, rbp; lpMem
0x18000d370  xor     edx, edx; dwFlags
0x18000d372  mov     rcx, rax; hHeap
0x18000d375  call    cs:__imp_HeapFree
0x18000d37b  mov     [r14], rsi
0x18000d37e  lea     rax, [rdi+rsi]
0x18000d382  mov     [rbx+28h], rax
0x18000d386  xor     edi, edi
0x18000d388  xor     eax, eax
0x18000d38a  mov     byte ptr [rbx+39h], 0
0x18000d38e  mov     [rsi], ax
0x18000d391  movzx   eax, word ptr [rbx]
0x18000d394  mov     [rsi+2], ax
0x18000d398  movzx   eax, word ptr [rbx+2]
0x18000d39c  mov     [rsi+4], ax
0x18000d3a0  mov     al, [rbx+4]
0x18000d3a3  mov     [rsi+8], al
0x18000d3a6  movzx   eax, word ptr [rbx+6]
0x18000d3aa  mov     [rsi+6], ax
0x18000d3ae  mov     al, [rbx+8]
0x18000d3b1  mov     [rsi+9], al
0x18000d3b4  mov     rax, [r14]
0x18000d3b7  add     rax, 0Ah
0x18000d3bb  mov     [rbx+20h], rax
0x18000d3bf  mov     rsi, [rbx+30h]
0x18000d3c3  mov     rax, qword ptr [rsp+98h+var_58+8]
0x18000d3c8  mov     [rbx+30h], rax
0x18000d3cc  test    rsi, rsi
0x18000d3cf  jz      short loc_18000D3E5
0x18000d3d1  call    cs:__imp_GetProcessHeap
0x18000d3d7  mov     r8, rsi; lpMem
0x18000d3da  xor     edx, edx; dwFlags
0x18000d3dc  mov     rcx, rax; hHeap
0x18000d3df  call    cs:__imp_HeapFree
0x18000d3e5  mov     rsi, [rsp+98h+Buf1]
0x18000d3ed  mov     ebp, [rsp+98h+arg_28]
0x18000d3f4  mov     byte ptr [rbx+3Ah], 1
0x18000d3f8  jmp     short loc_18000D3FF
0x18000d3fa  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x18000d3ff  test    rdi, rdi
0x18000d402  jz      short loc_18000D428
0x18000d404  call    cs:__imp_GetProcessHeap
0x18000d40a  mov     r8, rdi; lpMem
0x18000d40d  xor     edx, edx; dwFlags
0x18000d40f  mov     rcx, rax; hHeap
0x18000d412  call    cs:__imp_HeapFree
0x18000d418  jmp     short loc_18000D428
0x18000d41a  cmp     byte ptr [rbx+3Ah], 0
0x18000d41e  jz      short loc_18000D428
0x18000d420  mov     rcx, r14; this
0x18000d423  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000d428  mov     [rsp+98h+var_70], ebp; unsigned int
0x18000d42c  mov     r9, r13; void *
0x18000d42f  mov     r8, r15; Size
0x18000d432  mov     [rsp+98h+var_78], r12; unsigned __int64
0x18000d437  mov     rdx, rsi; Buf1
0x18000d43a  mov     rcx, rbx; this
0x18000d43d  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000d442  add     rsp, 58h
0x18000d446  pop     r15
0x18000d448  pop     r14
0x18000d44a  pop     r13
0x18000d44c  pop     r12
0x18000d44e  pop     rdi
0x18000d44f  pop     rsi
0x18000d450  pop     rbp
0x18000d451  pop     rbx
0x18000d452  retn
0x18000d453  mov     rcx, [rsp+98h]; this
0x18000d45b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
