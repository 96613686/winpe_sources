# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180005df4`
- end: `0x180005f9d`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180003180`
- `0x180005cf4`
- `0x180005d28`

## callees

- `0x180005df4`
- `0x180005fa4`
- `0x180007c78`
- `0x180007cdc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005eb1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f4e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005eb1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ea3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f40`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005ea3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f40`

## pseudocode

```c
char __fastcall wil::details_abi::RawUsageIndex::RecordUsage(
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
0x180005df4  mov     [rsp+Buf1], rdx
0x180005df9  push    rbx
0x180005dfa  push    rbp
0x180005dfb  push    rsi
0x180005dfc  push    rdi
0x180005dfd  push    r12
0x180005dff  push    r13
0x180005e01  push    r14
0x180005e03  push    r15
0x180005e05  sub     rsp, 58h
0x180005e09  mov     ebp, [rsp+98h+arg_28]
0x180005e10  mov     r13, r9
0x180005e13  mov     r12, [rsp+98h+arg_20]
0x180005e1b  mov     r15, r8
0x180005e1e  mov     [rsp+98h+var_70], ebp; unsigned int
0x180005e22  mov     rsi, rdx
0x180005e25  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180005e2a  mov     rbx, rcx
0x180005e2d  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180005e32  test    al, al
0x180005e34  jz      short loc_180005E3D
0x180005e36  mov     al, 1
0x180005e38  jmp     loc_180005F7E
0x180005e3d  lea     rdx, [r12+20h]
0x180005e42  add     rdx, r15; unsigned __int64
0x180005e45  lea     r14, [rbx+18h]
0x180005e49  cmp     qword ptr [r14], 0
0x180005e4d  jnz     loc_180005F56
0x180005e53  xorps   xmm0, xmm0
0x180005e56  lea     rcx, [rsp+98h+var_68]; this
0x180005e5b  xorps   xmm1, xmm1
0x180005e5e  add     rdx, 0Ah; unsigned __int64
0x180005e62  movdqu  [rsp+98h+var_68], xmm0
0x180005e68  movdqu  [rsp+98h+var_58], xmm1
0x180005e6e  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180005e73  test    al, al
0x180005e75  jz      loc_180005F36
0x180005e7b  mov     rdi, qword ptr [rsp+98h+var_58]
0x180005e80  mov     rsi, qword ptr [rsp+98h+var_68]
0x180005e85  sub     rdi, rsi
0x180005e88  cmp     rdi, 0Ah
0x180005e8c  jb      loc_180005F8F
0x180005e92  mov     rbp, [rbx+30h]
0x180005e96  mov     qword ptr [rbx+30h], 0
0x180005e9e  test    rbp, rbp
0x180005ea1  jz      short loc_180005EB7
0x180005ea3  call    cs:__imp_GetProcessHeap
0x180005ea9  mov     r8, rbp; lpMem
0x180005eac  xor     edx, edx; dwFlags
0x180005eae  mov     rcx, rax; hHeap
0x180005eb1  call    cs:__imp_HeapFree
0x180005eb7  mov     [r14], rsi
0x180005eba  lea     rax, [rdi+rsi]
0x180005ebe  mov     [rbx+28h], rax
0x180005ec2  xor     edi, edi
0x180005ec4  xor     eax, eax
0x180005ec6  mov     byte ptr [rbx+39h], 0
0x180005eca  mov     [rsi], ax
0x180005ecd  movzx   eax, word ptr [rbx]
0x180005ed0  mov     [rsi+2], ax
0x180005ed4  movzx   eax, word ptr [rbx+2]
0x180005ed8  mov     [rsi+4], ax
0x180005edc  mov     al, [rbx+4]
0x180005edf  mov     [rsi+8], al
0x180005ee2  movzx   eax, word ptr [rbx+6]
0x180005ee6  mov     [rsi+6], ax
0x180005eea  mov     al, [rbx+8]
0x180005eed  mov     [rsi+9], al
0x180005ef0  mov     rax, [r14]
0x180005ef3  add     rax, 0Ah
0x180005ef7  mov     [rbx+20h], rax
0x180005efb  mov     rsi, [rbx+30h]
0x180005eff  mov     rax, qword ptr [rsp+98h+var_58+8]
0x180005f04  mov     [rbx+30h], rax
0x180005f08  test    rsi, rsi
0x180005f0b  jz      short loc_180005F21
0x180005f0d  call    cs:__imp_GetProcessHeap
0x180005f13  mov     r8, rsi; lpMem
0x180005f16  xor     edx, edx; dwFlags
0x180005f18  mov     rcx, rax; hHeap
0x180005f1b  call    cs:__imp_HeapFree
0x180005f21  mov     rsi, [rsp+98h+Buf1]
0x180005f29  mov     ebp, [rsp+98h+arg_28]
0x180005f30  mov     byte ptr [rbx+3Ah], 1
0x180005f34  jmp     short loc_180005F3B
0x180005f36  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x180005f3b  test    rdi, rdi
0x180005f3e  jz      short loc_180005F64
0x180005f40  call    cs:__imp_GetProcessHeap
0x180005f46  mov     r8, rdi; lpMem
0x180005f49  xor     edx, edx; dwFlags
0x180005f4b  mov     rcx, rax; hHeap
0x180005f4e  call    cs:__imp_HeapFree
0x180005f54  jmp     short loc_180005F64
0x180005f56  cmp     byte ptr [rbx+3Ah], 0
0x180005f5a  jz      short loc_180005F64
0x180005f5c  mov     rcx, r14; this
0x180005f5f  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180005f64  mov     [rsp+98h+var_70], ebp; unsigned int
0x180005f68  mov     r9, r13; void *
0x180005f6b  mov     r8, r15; Size
0x180005f6e  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180005f73  mov     rdx, rsi; Buf1
0x180005f76  mov     rcx, rbx; this
0x180005f79  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180005f7e  add     rsp, 58h
0x180005f82  pop     r15
0x180005f84  pop     r14
0x180005f86  pop     r13
0x180005f88  pop     r12
0x180005f8a  pop     rdi
0x180005f8b  pop     rsi
0x180005f8c  pop     rbp
0x180005f8d  pop     rbx
0x180005f8e  retn
0x180005f8f  mov     rcx, [rsp+98h]; this
0x180005f97  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
