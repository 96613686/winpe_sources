# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180009a58`
- end: `0x180009c01`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180007ce0`
- `0x180009954`
- `0x180009988`

## callees

- `0x180009a58`
- `0x180009c08`
- `0x18000af74`
- `0x18000afc4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009ba4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009ba4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009bb2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009bb2`

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
0x180009a58  mov     [rsp+Buf1], rdx
0x180009a5d  push    rbx
0x180009a5e  push    rbp
0x180009a5f  push    rsi
0x180009a60  push    rdi
0x180009a61  push    r12
0x180009a63  push    r13
0x180009a65  push    r14
0x180009a67  push    r15
0x180009a69  sub     rsp, 58h
0x180009a6d  mov     ebp, [rsp+98h+arg_28]
0x180009a74  mov     r13, r9
0x180009a77  mov     r12, [rsp+98h+arg_20]
0x180009a7f  mov     r15, r8
0x180009a82  mov     [rsp+98h+var_70], ebp; unsigned int
0x180009a86  mov     rsi, rdx
0x180009a89  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180009a8e  mov     rbx, rcx
0x180009a91  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180009a96  test    al, al
0x180009a98  jz      short loc_180009AA1
0x180009a9a  mov     al, 1
0x180009a9c  jmp     loc_180009BE2
0x180009aa1  lea     rdx, [r12+20h]
0x180009aa6  add     rdx, r15; unsigned __int64
0x180009aa9  lea     r14, [rbx+18h]
0x180009aad  cmp     qword ptr [r14], 0
0x180009ab1  jnz     loc_180009BBA
0x180009ab7  xorps   xmm0, xmm0
0x180009aba  lea     rcx, [rsp+98h+var_68]; this
0x180009abf  xorps   xmm1, xmm1
0x180009ac2  add     rdx, 0Ah; unsigned __int64
0x180009ac6  movdqu  [rsp+98h+var_68], xmm0
0x180009acc  movdqu  [rsp+98h+var_58], xmm1
0x180009ad2  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180009ad7  test    al, al
0x180009ad9  jz      loc_180009B9A
0x180009adf  mov     rdi, qword ptr [rsp+98h+var_58]
0x180009ae4  mov     rsi, qword ptr [rsp+98h+var_68]
0x180009ae9  sub     rdi, rsi
0x180009aec  cmp     rdi, 0Ah
0x180009af0  jb      loc_180009BF3
0x180009af6  mov     rbp, [rbx+30h]
0x180009afa  mov     qword ptr [rbx+30h], 0
0x180009b02  test    rbp, rbp
0x180009b05  jz      short loc_180009B1B
0x180009b07  call    cs:__imp_GetProcessHeap
0x180009b0d  mov     r8, rbp; lpMem
0x180009b10  xor     edx, edx; dwFlags
0x180009b12  mov     rcx, rax; hHeap
0x180009b15  call    cs:__imp_HeapFree
0x180009b1b  mov     [r14], rsi
0x180009b1e  lea     rax, [rdi+rsi]
0x180009b22  mov     [rbx+28h], rax
0x180009b26  xor     edi, edi
0x180009b28  xor     eax, eax
0x180009b2a  mov     byte ptr [rbx+39h], 0
0x180009b2e  mov     [rsi], ax
0x180009b31  movzx   eax, word ptr [rbx]
0x180009b34  mov     [rsi+2], ax
0x180009b38  movzx   eax, word ptr [rbx+2]
0x180009b3c  mov     [rsi+4], ax
0x180009b40  mov     al, [rbx+4]
0x180009b43  mov     [rsi+8], al
0x180009b46  movzx   eax, word ptr [rbx+6]
0x180009b4a  mov     [rsi+6], ax
0x180009b4e  mov     al, [rbx+8]
0x180009b51  mov     [rsi+9], al
0x180009b54  mov     rax, [r14]
0x180009b57  add     rax, 0Ah
0x180009b5b  mov     [rbx+20h], rax
0x180009b5f  mov     rsi, [rbx+30h]
0x180009b63  mov     rax, qword ptr [rsp+98h+var_58+8]
0x180009b68  mov     [rbx+30h], rax
0x180009b6c  test    rsi, rsi
0x180009b6f  jz      short loc_180009B85
0x180009b71  call    cs:__imp_GetProcessHeap
0x180009b77  mov     r8, rsi; lpMem
0x180009b7a  xor     edx, edx; dwFlags
0x180009b7c  mov     rcx, rax; hHeap
0x180009b7f  call    cs:__imp_HeapFree
0x180009b85  mov     rsi, [rsp+98h+Buf1]
0x180009b8d  mov     ebp, [rsp+98h+arg_28]
0x180009b94  mov     byte ptr [rbx+3Ah], 1
0x180009b98  jmp     short loc_180009B9F
0x180009b9a  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x180009b9f  test    rdi, rdi
0x180009ba2  jz      short loc_180009BC8
0x180009ba4  call    cs:__imp_GetProcessHeap
0x180009baa  mov     r8, rdi; lpMem
0x180009bad  xor     edx, edx; dwFlags
0x180009baf  mov     rcx, rax; hHeap
0x180009bb2  call    cs:__imp_HeapFree
0x180009bb8  jmp     short loc_180009BC8
0x180009bba  cmp     byte ptr [rbx+3Ah], 0
0x180009bbe  jz      short loc_180009BC8
0x180009bc0  mov     rcx, r14; this
0x180009bc3  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180009bc8  mov     [rsp+98h+var_70], ebp; unsigned int
0x180009bcc  mov     r9, r13; void *
0x180009bcf  mov     r8, r15; Size
0x180009bd2  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180009bd7  mov     rdx, rsi; Buf1
0x180009bda  mov     rcx, rbx; this
0x180009bdd  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180009be2  add     rsp, 58h
0x180009be6  pop     r15
0x180009be8  pop     r14
0x180009bea  pop     r13
0x180009bec  pop     r12
0x180009bee  pop     rdi
0x180009bef  pop     rsi
0x180009bf0  pop     rbp
0x180009bf1  pop     rbx
0x180009bf2  retn
0x180009bf3  mov     rcx, [rsp+98h]; this
0x180009bfb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
