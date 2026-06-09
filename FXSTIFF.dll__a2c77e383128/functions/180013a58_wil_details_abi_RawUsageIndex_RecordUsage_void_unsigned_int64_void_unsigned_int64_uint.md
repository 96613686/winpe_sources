# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180013a58`
- end: `0x180013c01`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180010e80`
- `0x180013954`
- `0x180013988`

## callees

- `0x180013a58`
- `0x180013c08`
- `0x180015b88`
- `0x180015cac`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180013b15`
- `KERNEL32!HeapFree` at `0x180013b7f`
- `KERNEL32!HeapFree` at `0x180013bb2`
- `KERNEL32!HeapFree` at `0x180013b15`
- `KERNEL32!HeapFree` at `0x180013b7f`
- `KERNEL32!HeapFree` at `0x180013bb2`
- `KERNEL32!GetProcessHeap` at `0x180013b07`
- `KERNEL32!GetProcessHeap` at `0x180013b71`
- `KERNEL32!GetProcessHeap` at `0x180013ba4`
- `KERNEL32!GetProcessHeap` at `0x180013b07`
- `KERNEL32!GetProcessHeap` at `0x180013b71`
- `KERNEL32!GetProcessHeap` at `0x180013ba4`

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
0x180013a58  mov     [rsp+Buf1], rdx
0x180013a5d  push    rbx
0x180013a5e  push    rbp
0x180013a5f  push    rsi
0x180013a60  push    rdi
0x180013a61  push    r12
0x180013a63  push    r13
0x180013a65  push    r14
0x180013a67  push    r15
0x180013a69  sub     rsp, 58h
0x180013a6d  mov     ebp, [rsp+98h+arg_28]
0x180013a74  mov     r13, r9
0x180013a77  mov     r12, [rsp+98h+arg_20]
0x180013a7f  mov     r15, r8
0x180013a82  mov     [rsp+98h+var_70], ebp; unsigned int
0x180013a86  mov     rsi, rdx
0x180013a89  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180013a8e  mov     rbx, rcx
0x180013a91  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180013a96  test    al, al
0x180013a98  jz      short loc_180013AA1
0x180013a9a  mov     al, 1
0x180013a9c  jmp     loc_180013BE2
0x180013aa1  lea     rdx, [r12+20h]
0x180013aa6  add     rdx, r15; unsigned __int64
0x180013aa9  lea     r14, [rbx+18h]
0x180013aad  cmp     qword ptr [r14], 0
0x180013ab1  jnz     loc_180013BBA
0x180013ab7  xorps   xmm0, xmm0
0x180013aba  lea     rcx, [rsp+98h+var_68]; this
0x180013abf  xorps   xmm1, xmm1
0x180013ac2  add     rdx, 0Ah; unsigned __int64
0x180013ac6  movdqu  [rsp+98h+var_68], xmm0
0x180013acc  movdqu  [rsp+98h+var_58], xmm1
0x180013ad2  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180013ad7  test    al, al
0x180013ad9  jz      loc_180013B9A
0x180013adf  mov     rdi, qword ptr [rsp+98h+var_58]
0x180013ae4  mov     rsi, qword ptr [rsp+98h+var_68]
0x180013ae9  sub     rdi, rsi
0x180013aec  cmp     rdi, 0Ah
0x180013af0  jb      loc_180013BF3
0x180013af6  mov     rbp, [rbx+30h]
0x180013afa  mov     qword ptr [rbx+30h], 0
0x180013b02  test    rbp, rbp
0x180013b05  jz      short loc_180013B1B
0x180013b07  call    cs:__imp_GetProcessHeap
0x180013b0d  mov     r8, rbp; lpMem
0x180013b10  xor     edx, edx; dwFlags
0x180013b12  mov     rcx, rax; hHeap
0x180013b15  call    cs:__imp_HeapFree
0x180013b1b  mov     [r14], rsi
0x180013b1e  lea     rax, [rdi+rsi]
0x180013b22  mov     [rbx+28h], rax
0x180013b26  xor     edi, edi
0x180013b28  xor     eax, eax
0x180013b2a  mov     byte ptr [rbx+39h], 0
0x180013b2e  mov     [rsi], ax
0x180013b31  movzx   eax, word ptr [rbx]
0x180013b34  mov     [rsi+2], ax
0x180013b38  movzx   eax, word ptr [rbx+2]
0x180013b3c  mov     [rsi+4], ax
0x180013b40  mov     al, [rbx+4]
0x180013b43  mov     [rsi+8], al
0x180013b46  movzx   eax, word ptr [rbx+6]
0x180013b4a  mov     [rsi+6], ax
0x180013b4e  mov     al, [rbx+8]
0x180013b51  mov     [rsi+9], al
0x180013b54  mov     rax, [r14]
0x180013b57  add     rax, 0Ah
0x180013b5b  mov     [rbx+20h], rax
0x180013b5f  mov     rsi, [rbx+30h]
0x180013b63  mov     rax, qword ptr [rsp+98h+var_58+8]
0x180013b68  mov     [rbx+30h], rax
0x180013b6c  test    rsi, rsi
0x180013b6f  jz      short loc_180013B85
0x180013b71  call    cs:__imp_GetProcessHeap
0x180013b77  mov     r8, rsi; lpMem
0x180013b7a  xor     edx, edx; dwFlags
0x180013b7c  mov     rcx, rax; hHeap
0x180013b7f  call    cs:__imp_HeapFree
0x180013b85  mov     rsi, [rsp+98h+Buf1]
0x180013b8d  mov     ebp, [rsp+98h+arg_28]
0x180013b94  mov     byte ptr [rbx+3Ah], 1
0x180013b98  jmp     short loc_180013B9F
0x180013b9a  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x180013b9f  test    rdi, rdi
0x180013ba2  jz      short loc_180013BC8
0x180013ba4  call    cs:__imp_GetProcessHeap
0x180013baa  mov     r8, rdi; lpMem
0x180013bad  xor     edx, edx; dwFlags
0x180013baf  mov     rcx, rax; hHeap
0x180013bb2  call    cs:__imp_HeapFree
0x180013bb8  jmp     short loc_180013BC8
0x180013bba  cmp     byte ptr [rbx+3Ah], 0
0x180013bbe  jz      short loc_180013BC8
0x180013bc0  mov     rcx, r14; this
0x180013bc3  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180013bc8  mov     [rsp+98h+var_70], ebp; unsigned int
0x180013bcc  mov     r9, r13; void *
0x180013bcf  mov     r8, r15; Size
0x180013bd2  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180013bd7  mov     rdx, rsi; Buf1
0x180013bda  mov     rcx, rbx; this
0x180013bdd  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180013be2  add     rsp, 58h
0x180013be6  pop     r15
0x180013be8  pop     r14
0x180013bea  pop     r13
0x180013bec  pop     r12
0x180013bee  pop     rdi
0x180013bef  pop     rsi
0x180013bf0  pop     rbp
0x180013bf1  pop     rbx
0x180013bf2  retn
0x180013bf3  mov     rcx, [rsp+98h]; this
0x180013bfb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
