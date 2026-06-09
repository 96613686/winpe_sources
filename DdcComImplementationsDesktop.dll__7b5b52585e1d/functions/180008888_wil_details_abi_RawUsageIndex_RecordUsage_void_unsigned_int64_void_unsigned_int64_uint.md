# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180008888`
- end: `0x180008a31`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180005f90`
- `0x180008784`
- `0x1800087b8`

## callees

- `0x180008888`
- `0x180008a38`
- `0x18000ab28`
- `0x18000ac4c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008945`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008945`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008937`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800089a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800089d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008937`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800089a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800089d4`

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
0x180008888  mov     [rsp+Buf1], rdx
0x18000888d  push    rbx
0x18000888e  push    rbp
0x18000888f  push    rsi
0x180008890  push    rdi
0x180008891  push    r12
0x180008893  push    r13
0x180008895  push    r14
0x180008897  push    r15
0x180008899  sub     rsp, 58h
0x18000889d  mov     ebp, [rsp+98h+arg_28]
0x1800088a4  mov     r13, r9
0x1800088a7  mov     r12, [rsp+98h+arg_20]
0x1800088af  mov     r15, r8
0x1800088b2  mov     [rsp+98h+var_70], ebp; unsigned int
0x1800088b6  mov     rsi, rdx
0x1800088b9  mov     [rsp+98h+var_78], r12; unsigned __int64
0x1800088be  mov     rbx, rcx
0x1800088c1  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1800088c6  test    al, al
0x1800088c8  jz      short loc_1800088D1
0x1800088ca  mov     al, 1
0x1800088cc  jmp     loc_180008A12
0x1800088d1  lea     rdx, [r12+20h]
0x1800088d6  add     rdx, r15; unsigned __int64
0x1800088d9  lea     r14, [rbx+18h]
0x1800088dd  cmp     qword ptr [r14], 0
0x1800088e1  jnz     loc_1800089EA
0x1800088e7  xorps   xmm0, xmm0
0x1800088ea  lea     rcx, [rsp+98h+var_68]; this
0x1800088ef  xorps   xmm1, xmm1
0x1800088f2  add     rdx, 0Ah; unsigned __int64
0x1800088f6  movdqu  [rsp+98h+var_68], xmm0
0x1800088fc  movdqu  [rsp+98h+var_58], xmm1
0x180008902  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180008907  test    al, al
0x180008909  jz      loc_1800089CA
0x18000890f  mov     rdi, qword ptr [rsp+98h+var_58]
0x180008914  mov     rsi, qword ptr [rsp+98h+var_68]
0x180008919  sub     rdi, rsi
0x18000891c  cmp     rdi, 0Ah
0x180008920  jb      loc_180008A23
0x180008926  mov     rbp, [rbx+30h]
0x18000892a  mov     qword ptr [rbx+30h], 0
0x180008932  test    rbp, rbp
0x180008935  jz      short loc_18000894B
0x180008937  call    cs:__imp_GetProcessHeap
0x18000893d  mov     r8, rbp; lpMem
0x180008940  xor     edx, edx; dwFlags
0x180008942  mov     rcx, rax; hHeap
0x180008945  call    cs:__imp_HeapFree
0x18000894b  mov     [r14], rsi
0x18000894e  lea     rax, [rdi+rsi]
0x180008952  mov     [rbx+28h], rax
0x180008956  xor     edi, edi
0x180008958  xor     eax, eax
0x18000895a  mov     byte ptr [rbx+39h], 0
0x18000895e  mov     [rsi], ax
0x180008961  movzx   eax, word ptr [rbx]
0x180008964  mov     [rsi+2], ax
0x180008968  movzx   eax, word ptr [rbx+2]
0x18000896c  mov     [rsi+4], ax
0x180008970  mov     al, [rbx+4]
0x180008973  mov     [rsi+8], al
0x180008976  movzx   eax, word ptr [rbx+6]
0x18000897a  mov     [rsi+6], ax
0x18000897e  mov     al, [rbx+8]
0x180008981  mov     [rsi+9], al
0x180008984  mov     rax, [r14]
0x180008987  add     rax, 0Ah
0x18000898b  mov     [rbx+20h], rax
0x18000898f  mov     rsi, [rbx+30h]
0x180008993  mov     rax, qword ptr [rsp+98h+var_58+8]
0x180008998  mov     [rbx+30h], rax
0x18000899c  test    rsi, rsi
0x18000899f  jz      short loc_1800089B5
0x1800089a1  call    cs:__imp_GetProcessHeap
0x1800089a7  mov     r8, rsi; lpMem
0x1800089aa  xor     edx, edx; dwFlags
0x1800089ac  mov     rcx, rax; hHeap
0x1800089af  call    cs:__imp_HeapFree
0x1800089b5  mov     rsi, [rsp+98h+Buf1]
0x1800089bd  mov     ebp, [rsp+98h+arg_28]
0x1800089c4  mov     byte ptr [rbx+3Ah], 1
0x1800089c8  jmp     short loc_1800089CF
0x1800089ca  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x1800089cf  test    rdi, rdi
0x1800089d2  jz      short loc_1800089F8
0x1800089d4  call    cs:__imp_GetProcessHeap
0x1800089da  mov     r8, rdi; lpMem
0x1800089dd  xor     edx, edx; dwFlags
0x1800089df  mov     rcx, rax; hHeap
0x1800089e2  call    cs:__imp_HeapFree
0x1800089e8  jmp     short loc_1800089F8
0x1800089ea  cmp     byte ptr [rbx+3Ah], 0
0x1800089ee  jz      short loc_1800089F8
0x1800089f0  mov     rcx, r14; this
0x1800089f3  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800089f8  mov     [rsp+98h+var_70], ebp; unsigned int
0x1800089fc  mov     r9, r13; void *
0x1800089ff  mov     r8, r15; Size
0x180008a02  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180008a07  mov     rdx, rsi; Buf1
0x180008a0a  mov     rcx, rbx; this
0x180008a0d  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180008a12  add     rsp, 58h
0x180008a16  pop     r15
0x180008a18  pop     r14
0x180008a1a  pop     r13
0x180008a1c  pop     r12
0x180008a1e  pop     rdi
0x180008a1f  pop     rsi
0x180008a20  pop     rbp
0x180008a21  pop     rbx
0x180008a22  retn
0x180008a23  mov     rcx, [rsp+98h]; this
0x180008a2b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
