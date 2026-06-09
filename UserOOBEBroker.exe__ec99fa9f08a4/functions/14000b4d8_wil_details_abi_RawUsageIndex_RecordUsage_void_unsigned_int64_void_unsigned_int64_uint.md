# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x14000b4d8`
- end: `0x14000b681`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140008460`
- `0x14000b3d4`
- `0x14000b408`

## callees

- `0x14000b4d8`
- `0x14000b688`
- `0x14000d46c`
- `0x14000d7d4`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000b595`
- `KERNEL32!HeapFree` at `0x14000b5ff`
- `KERNEL32!HeapFree` at `0x14000b632`
- `KERNEL32!HeapFree` at `0x14000b595`
- `KERNEL32!HeapFree` at `0x14000b5ff`
- `KERNEL32!HeapFree` at `0x14000b632`
- `KERNEL32!GetProcessHeap` at `0x14000b587`
- `KERNEL32!GetProcessHeap` at `0x14000b5f1`
- `KERNEL32!GetProcessHeap` at `0x14000b624`
- `KERNEL32!GetProcessHeap` at `0x14000b587`
- `KERNEL32!GetProcessHeap` at `0x14000b5f1`
- `KERNEL32!GetProcessHeap` at `0x14000b624`

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
0x14000b4d8  mov     [rsp+Buf1], rdx
0x14000b4dd  push    rbx
0x14000b4de  push    rbp
0x14000b4df  push    rsi
0x14000b4e0  push    rdi
0x14000b4e1  push    r12
0x14000b4e3  push    r13
0x14000b4e5  push    r14
0x14000b4e7  push    r15
0x14000b4e9  sub     rsp, 58h
0x14000b4ed  mov     ebp, [rsp+98h+arg_28]
0x14000b4f4  mov     r13, r9
0x14000b4f7  mov     r12, [rsp+98h+arg_20]
0x14000b4ff  mov     r15, r8
0x14000b502  mov     [rsp+98h+var_70], ebp; unsigned int
0x14000b506  mov     rsi, rdx
0x14000b509  mov     [rsp+98h+var_78], r12; unsigned __int64
0x14000b50e  mov     rbx, rcx
0x14000b511  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x14000b516  test    al, al
0x14000b518  jz      short loc_14000B521
0x14000b51a  mov     al, 1
0x14000b51c  jmp     loc_14000B662
0x14000b521  lea     rdx, [r12+20h]
0x14000b526  add     rdx, r15; unsigned __int64
0x14000b529  lea     r14, [rbx+18h]
0x14000b52d  cmp     qword ptr [r14], 0
0x14000b531  jnz     loc_14000B63A
0x14000b537  xorps   xmm0, xmm0
0x14000b53a  lea     rcx, [rsp+98h+var_68]; this
0x14000b53f  xorps   xmm1, xmm1
0x14000b542  add     rdx, 0Ah; unsigned __int64
0x14000b546  movdqu  [rsp+98h+var_68], xmm0
0x14000b54c  movdqu  [rsp+98h+var_58], xmm1
0x14000b552  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000b557  test    al, al
0x14000b559  jz      loc_14000B61A
0x14000b55f  mov     rdi, qword ptr [rsp+98h+var_58]
0x14000b564  mov     rsi, qword ptr [rsp+98h+var_68]
0x14000b569  sub     rdi, rsi
0x14000b56c  cmp     rdi, 0Ah
0x14000b570  jb      loc_14000B673
0x14000b576  mov     rbp, [rbx+30h]
0x14000b57a  mov     qword ptr [rbx+30h], 0
0x14000b582  test    rbp, rbp
0x14000b585  jz      short loc_14000B59B
0x14000b587  call    cs:__imp_GetProcessHeap
0x14000b58d  mov     r8, rbp; lpMem
0x14000b590  xor     edx, edx; dwFlags
0x14000b592  mov     rcx, rax; hHeap
0x14000b595  call    cs:__imp_HeapFree
0x14000b59b  mov     [r14], rsi
0x14000b59e  lea     rax, [rdi+rsi]
0x14000b5a2  mov     [rbx+28h], rax
0x14000b5a6  xor     edi, edi
0x14000b5a8  xor     eax, eax
0x14000b5aa  mov     byte ptr [rbx+39h], 0
0x14000b5ae  mov     [rsi], ax
0x14000b5b1  movzx   eax, word ptr [rbx]
0x14000b5b4  mov     [rsi+2], ax
0x14000b5b8  movzx   eax, word ptr [rbx+2]
0x14000b5bc  mov     [rsi+4], ax
0x14000b5c0  mov     al, [rbx+4]
0x14000b5c3  mov     [rsi+8], al
0x14000b5c6  movzx   eax, word ptr [rbx+6]
0x14000b5ca  mov     [rsi+6], ax
0x14000b5ce  mov     al, [rbx+8]
0x14000b5d1  mov     [rsi+9], al
0x14000b5d4  mov     rax, [r14]
0x14000b5d7  add     rax, 0Ah
0x14000b5db  mov     [rbx+20h], rax
0x14000b5df  mov     rsi, [rbx+30h]
0x14000b5e3  mov     rax, qword ptr [rsp+98h+var_58+8]
0x14000b5e8  mov     [rbx+30h], rax
0x14000b5ec  test    rsi, rsi
0x14000b5ef  jz      short loc_14000B605
0x14000b5f1  call    cs:__imp_GetProcessHeap
0x14000b5f7  mov     r8, rsi; lpMem
0x14000b5fa  xor     edx, edx; dwFlags
0x14000b5fc  mov     rcx, rax; hHeap
0x14000b5ff  call    cs:__imp_HeapFree
0x14000b605  mov     rsi, [rsp+98h+Buf1]
0x14000b60d  mov     ebp, [rsp+98h+arg_28]
0x14000b614  mov     byte ptr [rbx+3Ah], 1
0x14000b618  jmp     short loc_14000B61F
0x14000b61a  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x14000b61f  test    rdi, rdi
0x14000b622  jz      short loc_14000B648
0x14000b624  call    cs:__imp_GetProcessHeap
0x14000b62a  mov     r8, rdi; lpMem
0x14000b62d  xor     edx, edx; dwFlags
0x14000b62f  mov     rcx, rax; hHeap
0x14000b632  call    cs:__imp_HeapFree
0x14000b638  jmp     short loc_14000B648
0x14000b63a  cmp     byte ptr [rbx+3Ah], 0
0x14000b63e  jz      short loc_14000B648
0x14000b640  mov     rcx, r14; this
0x14000b643  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000b648  mov     [rsp+98h+var_70], ebp; unsigned int
0x14000b64c  mov     r9, r13; void *
0x14000b64f  mov     r8, r15; Size
0x14000b652  mov     [rsp+98h+var_78], r12; unsigned __int64
0x14000b657  mov     rdx, rsi; Buf1
0x14000b65a  mov     rcx, rbx; this
0x14000b65d  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x14000b662  add     rsp, 58h
0x14000b666  pop     r15
0x14000b668  pop     r14
0x14000b66a  pop     r13
0x14000b66c  pop     r12
0x14000b66e  pop     rdi
0x14000b66f  pop     rsi
0x14000b670  pop     rbp
0x14000b671  pop     rbx
0x14000b672  retn
0x14000b673  mov     rcx, [rsp+98h]; this
0x14000b67b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
