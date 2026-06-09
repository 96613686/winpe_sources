# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180005eb0`
- end: `0x180006059`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180003610`
- `0x180005db0`
- `0x180005de4`

## callees

- `0x180005eb0`
- `0x180006060`
- `0x180007b58`
- `0x180007bbc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005fc9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ffc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005fc9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ffc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005fd7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000600a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005fd7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000600a`

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
0x180005eb0  mov     [rsp+Buf1], rdx
0x180005eb5  push    rbx
0x180005eb6  push    rbp
0x180005eb7  push    rsi
0x180005eb8  push    rdi
0x180005eb9  push    r12
0x180005ebb  push    r13
0x180005ebd  push    r14
0x180005ebf  push    r15
0x180005ec1  sub     rsp, 58h
0x180005ec5  mov     ebp, [rsp+98h+arg_28]
0x180005ecc  mov     r13, r9
0x180005ecf  mov     r12, [rsp+98h+arg_20]
0x180005ed7  mov     r15, r8
0x180005eda  mov     [rsp+98h+var_70], ebp; unsigned int
0x180005ede  mov     rsi, rdx
0x180005ee1  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180005ee6  mov     rbx, rcx
0x180005ee9  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180005eee  test    al, al
0x180005ef0  jz      short loc_180005EF9
0x180005ef2  mov     al, 1
0x180005ef4  jmp     loc_18000603A
0x180005ef9  lea     rdx, [r12+20h]
0x180005efe  add     rdx, r15; unsigned __int64
0x180005f01  lea     r14, [rbx+18h]
0x180005f05  cmp     qword ptr [r14], 0
0x180005f09  jnz     loc_180006012
0x180005f0f  xorps   xmm0, xmm0
0x180005f12  lea     rcx, [rsp+98h+var_68]; this
0x180005f17  xorps   xmm1, xmm1
0x180005f1a  add     rdx, 0Ah; unsigned __int64
0x180005f1e  movdqu  [rsp+98h+var_68], xmm0
0x180005f24  movdqu  [rsp+98h+var_58], xmm1
0x180005f2a  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180005f2f  test    al, al
0x180005f31  jz      loc_180005FF2
0x180005f37  mov     rdi, qword ptr [rsp+98h+var_58]
0x180005f3c  mov     rsi, qword ptr [rsp+98h+var_68]
0x180005f41  sub     rdi, rsi
0x180005f44  cmp     rdi, 0Ah
0x180005f48  jb      loc_18000604B
0x180005f4e  mov     rbp, [rbx+30h]
0x180005f52  mov     qword ptr [rbx+30h], 0
0x180005f5a  test    rbp, rbp
0x180005f5d  jz      short loc_180005F73
0x180005f5f  call    cs:__imp_GetProcessHeap
0x180005f65  mov     r8, rbp; lpMem
0x180005f68  xor     edx, edx; dwFlags
0x180005f6a  mov     rcx, rax; hHeap
0x180005f6d  call    cs:__imp_HeapFree
0x180005f73  mov     [r14], rsi
0x180005f76  lea     rax, [rdi+rsi]
0x180005f7a  mov     [rbx+28h], rax
0x180005f7e  xor     edi, edi
0x180005f80  xor     eax, eax
0x180005f82  mov     byte ptr [rbx+39h], 0
0x180005f86  mov     [rsi], ax
0x180005f89  movzx   eax, word ptr [rbx]
0x180005f8c  mov     [rsi+2], ax
0x180005f90  movzx   eax, word ptr [rbx+2]
0x180005f94  mov     [rsi+4], ax
0x180005f98  mov     al, [rbx+4]
0x180005f9b  mov     [rsi+8], al
0x180005f9e  movzx   eax, word ptr [rbx+6]
0x180005fa2  mov     [rsi+6], ax
0x180005fa6  mov     al, [rbx+8]
0x180005fa9  mov     [rsi+9], al
0x180005fac  mov     rax, [r14]
0x180005faf  add     rax, 0Ah
0x180005fb3  mov     [rbx+20h], rax
0x180005fb7  mov     rsi, [rbx+30h]
0x180005fbb  mov     rax, qword ptr [rsp+98h+var_58+8]
0x180005fc0  mov     [rbx+30h], rax
0x180005fc4  test    rsi, rsi
0x180005fc7  jz      short loc_180005FDD
0x180005fc9  call    cs:__imp_GetProcessHeap
0x180005fcf  mov     r8, rsi; lpMem
0x180005fd2  xor     edx, edx; dwFlags
0x180005fd4  mov     rcx, rax; hHeap
0x180005fd7  call    cs:__imp_HeapFree
0x180005fdd  mov     rsi, [rsp+98h+Buf1]
0x180005fe5  mov     ebp, [rsp+98h+arg_28]
0x180005fec  mov     byte ptr [rbx+3Ah], 1
0x180005ff0  jmp     short loc_180005FF7
0x180005ff2  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x180005ff7  test    rdi, rdi
0x180005ffa  jz      short loc_180006020
0x180005ffc  call    cs:__imp_GetProcessHeap
0x180006002  mov     r8, rdi; lpMem
0x180006005  xor     edx, edx; dwFlags
0x180006007  mov     rcx, rax; hHeap
0x18000600a  call    cs:__imp_HeapFree
0x180006010  jmp     short loc_180006020
0x180006012  cmp     byte ptr [rbx+3Ah], 0
0x180006016  jz      short loc_180006020
0x180006018  mov     rcx, r14; this
0x18000601b  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180006020  mov     [rsp+98h+var_70], ebp; unsigned int
0x180006024  mov     r9, r13; void *
0x180006027  mov     r8, r15; Size
0x18000602a  mov     [rsp+98h+var_78], r12; unsigned __int64
0x18000602f  mov     rdx, rsi; Buf1
0x180006032  mov     rcx, rbx; this
0x180006035  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000603a  add     rsp, 58h
0x18000603e  pop     r15
0x180006040  pop     r14
0x180006042  pop     r13
0x180006044  pop     r12
0x180006046  pop     rdi
0x180006047  pop     rsi
0x180006048  pop     rbp
0x180006049  pop     rbx
0x18000604a  retn
0x18000604b  mov     rcx, [rsp+98h]; this
0x180006053  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
