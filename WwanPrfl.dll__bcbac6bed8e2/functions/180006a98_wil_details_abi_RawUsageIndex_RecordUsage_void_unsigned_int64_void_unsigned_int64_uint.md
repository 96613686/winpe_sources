# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180006a98`
- end: `0x180006c41`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180003990`
- `0x180006994`
- `0x1800069c8`

## callees

- `0x180006a98`
- `0x180006c48`
- `0x180009198`
- `0x18000d5fc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006b55`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006bbf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006bf2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006b55`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006bbf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006bf2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006b47`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006bb1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006be4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006b47`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006bb1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006be4`

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
0x180006a98  mov     [rsp+Buf1], rdx
0x180006a9d  push    rbx
0x180006a9e  push    rbp
0x180006a9f  push    rsi
0x180006aa0  push    rdi
0x180006aa1  push    r12
0x180006aa3  push    r13
0x180006aa5  push    r14
0x180006aa7  push    r15
0x180006aa9  sub     rsp, 58h
0x180006aad  mov     ebp, [rsp+98h+arg_28]
0x180006ab4  mov     r13, r9
0x180006ab7  mov     r12, [rsp+98h+arg_20]
0x180006abf  mov     r15, r8
0x180006ac2  mov     [rsp+98h+var_70], ebp; unsigned int
0x180006ac6  mov     rsi, rdx
0x180006ac9  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180006ace  mov     rbx, rcx
0x180006ad1  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180006ad6  test    al, al
0x180006ad8  jz      short loc_180006AE1
0x180006ada  mov     al, 1
0x180006adc  jmp     loc_180006C22
0x180006ae1  lea     rdx, [r12+20h]
0x180006ae6  add     rdx, r15; unsigned __int64
0x180006ae9  lea     r14, [rbx+18h]
0x180006aed  cmp     qword ptr [r14], 0
0x180006af1  jnz     loc_180006BFA
0x180006af7  xorps   xmm0, xmm0
0x180006afa  lea     rcx, [rsp+98h+var_68]; this
0x180006aff  xorps   xmm1, xmm1
0x180006b02  add     rdx, 0Ah; unsigned __int64
0x180006b06  movdqu  [rsp+98h+var_68], xmm0
0x180006b0c  movdqu  [rsp+98h+var_58], xmm1
0x180006b12  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180006b17  test    al, al
0x180006b19  jz      loc_180006BDA
0x180006b1f  mov     rdi, qword ptr [rsp+98h+var_58]
0x180006b24  mov     rsi, qword ptr [rsp+98h+var_68]
0x180006b29  sub     rdi, rsi
0x180006b2c  cmp     rdi, 0Ah
0x180006b30  jb      loc_180006C33
0x180006b36  mov     rbp, [rbx+30h]
0x180006b3a  mov     qword ptr [rbx+30h], 0
0x180006b42  test    rbp, rbp
0x180006b45  jz      short loc_180006B5B
0x180006b47  call    cs:__imp_GetProcessHeap
0x180006b4d  mov     r8, rbp; lpMem
0x180006b50  xor     edx, edx; dwFlags
0x180006b52  mov     rcx, rax; hHeap
0x180006b55  call    cs:__imp_HeapFree
0x180006b5b  mov     [r14], rsi
0x180006b5e  lea     rax, [rdi+rsi]
0x180006b62  mov     [rbx+28h], rax
0x180006b66  xor     edi, edi
0x180006b68  xor     eax, eax
0x180006b6a  mov     byte ptr [rbx+39h], 0
0x180006b6e  mov     [rsi], ax
0x180006b71  movzx   eax, word ptr [rbx]
0x180006b74  mov     [rsi+2], ax
0x180006b78  movzx   eax, word ptr [rbx+2]
0x180006b7c  mov     [rsi+4], ax
0x180006b80  mov     al, [rbx+4]
0x180006b83  mov     [rsi+8], al
0x180006b86  movzx   eax, word ptr [rbx+6]
0x180006b8a  mov     [rsi+6], ax
0x180006b8e  mov     al, [rbx+8]
0x180006b91  mov     [rsi+9], al
0x180006b94  mov     rax, [r14]
0x180006b97  add     rax, 0Ah
0x180006b9b  mov     [rbx+20h], rax
0x180006b9f  mov     rsi, [rbx+30h]
0x180006ba3  mov     rax, qword ptr [rsp+98h+var_58+8]
0x180006ba8  mov     [rbx+30h], rax
0x180006bac  test    rsi, rsi
0x180006baf  jz      short loc_180006BC5
0x180006bb1  call    cs:__imp_GetProcessHeap
0x180006bb7  mov     r8, rsi; lpMem
0x180006bba  xor     edx, edx; dwFlags
0x180006bbc  mov     rcx, rax; hHeap
0x180006bbf  call    cs:__imp_HeapFree
0x180006bc5  mov     rsi, [rsp+98h+Buf1]
0x180006bcd  mov     ebp, [rsp+98h+arg_28]
0x180006bd4  mov     byte ptr [rbx+3Ah], 1
0x180006bd8  jmp     short loc_180006BDF
0x180006bda  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x180006bdf  test    rdi, rdi
0x180006be2  jz      short loc_180006C08
0x180006be4  call    cs:__imp_GetProcessHeap
0x180006bea  mov     r8, rdi; lpMem
0x180006bed  xor     edx, edx; dwFlags
0x180006bef  mov     rcx, rax; hHeap
0x180006bf2  call    cs:__imp_HeapFree
0x180006bf8  jmp     short loc_180006C08
0x180006bfa  cmp     byte ptr [rbx+3Ah], 0
0x180006bfe  jz      short loc_180006C08
0x180006c00  mov     rcx, r14; this
0x180006c03  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180006c08  mov     [rsp+98h+var_70], ebp; unsigned int
0x180006c0c  mov     r9, r13; void *
0x180006c0f  mov     r8, r15; Size
0x180006c12  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180006c17  mov     rdx, rsi; Buf1
0x180006c1a  mov     rcx, rbx; this
0x180006c1d  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180006c22  add     rsp, 58h
0x180006c26  pop     r15
0x180006c28  pop     r14
0x180006c2a  pop     r13
0x180006c2c  pop     r12
0x180006c2e  pop     rdi
0x180006c2f  pop     rsi
0x180006c30  pop     rbp
0x180006c31  pop     rbx
0x180006c32  retn
0x180006c33  mov     rcx, [rsp+98h]; this
0x180006c3b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
