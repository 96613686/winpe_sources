# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18000aa58`
- end: `0x18000ac01`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800065e0`
- `0x18000a954`
- `0x18000a988`

## callees

- `0x18000aa58`
- `0x18000ac08`
- `0x18000e830`
- `0x18000eb4c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ab15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ab7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000abb2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ab15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ab7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000abb2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ab07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ab71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aba4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ab07`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ab71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aba4`

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
0x18000aa58  mov     [rsp+Buf1], rdx
0x18000aa5d  push    rbx
0x18000aa5e  push    rbp
0x18000aa5f  push    rsi
0x18000aa60  push    rdi
0x18000aa61  push    r12
0x18000aa63  push    r13
0x18000aa65  push    r14
0x18000aa67  push    r15
0x18000aa69  sub     rsp, 58h
0x18000aa6d  mov     ebp, [rsp+98h+arg_28]
0x18000aa74  mov     r13, r9
0x18000aa77  mov     r12, [rsp+98h+arg_20]
0x18000aa7f  mov     r15, r8
0x18000aa82  mov     [rsp+98h+var_70], ebp; unsigned int
0x18000aa86  mov     rsi, rdx
0x18000aa89  mov     [rsp+98h+var_78], r12; unsigned __int64
0x18000aa8e  mov     rbx, rcx
0x18000aa91  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000aa96  test    al, al
0x18000aa98  jz      short loc_18000AAA1
0x18000aa9a  mov     al, 1
0x18000aa9c  jmp     loc_18000ABE2
0x18000aaa1  lea     rdx, [r12+20h]
0x18000aaa6  add     rdx, r15; unsigned __int64
0x18000aaa9  lea     r14, [rbx+18h]
0x18000aaad  cmp     qword ptr [r14], 0
0x18000aab1  jnz     loc_18000ABBA
0x18000aab7  xorps   xmm0, xmm0
0x18000aaba  lea     rcx, [rsp+98h+var_68]; this
0x18000aabf  xorps   xmm1, xmm1
0x18000aac2  add     rdx, 0Ah; unsigned __int64
0x18000aac6  movdqu  [rsp+98h+var_68], xmm0
0x18000aacc  movdqu  [rsp+98h+var_58], xmm1
0x18000aad2  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000aad7  test    al, al
0x18000aad9  jz      loc_18000AB9A
0x18000aadf  mov     rdi, qword ptr [rsp+98h+var_58]
0x18000aae4  mov     rsi, qword ptr [rsp+98h+var_68]
0x18000aae9  sub     rdi, rsi
0x18000aaec  cmp     rdi, 0Ah
0x18000aaf0  jb      loc_18000ABF3
0x18000aaf6  mov     rbp, [rbx+30h]
0x18000aafa  mov     qword ptr [rbx+30h], 0
0x18000ab02  test    rbp, rbp
0x18000ab05  jz      short loc_18000AB1B
0x18000ab07  call    cs:__imp_GetProcessHeap
0x18000ab0d  mov     r8, rbp; lpMem
0x18000ab10  xor     edx, edx; dwFlags
0x18000ab12  mov     rcx, rax; hHeap
0x18000ab15  call    cs:__imp_HeapFree
0x18000ab1b  mov     [r14], rsi
0x18000ab1e  lea     rax, [rdi+rsi]
0x18000ab22  mov     [rbx+28h], rax
0x18000ab26  xor     edi, edi
0x18000ab28  xor     eax, eax
0x18000ab2a  mov     byte ptr [rbx+39h], 0
0x18000ab2e  mov     [rsi], ax
0x18000ab31  movzx   eax, word ptr [rbx]
0x18000ab34  mov     [rsi+2], ax
0x18000ab38  movzx   eax, word ptr [rbx+2]
0x18000ab3c  mov     [rsi+4], ax
0x18000ab40  mov     al, [rbx+4]
0x18000ab43  mov     [rsi+8], al
0x18000ab46  movzx   eax, word ptr [rbx+6]
0x18000ab4a  mov     [rsi+6], ax
0x18000ab4e  mov     al, [rbx+8]
0x18000ab51  mov     [rsi+9], al
0x18000ab54  mov     rax, [r14]
0x18000ab57  add     rax, 0Ah
0x18000ab5b  mov     [rbx+20h], rax
0x18000ab5f  mov     rsi, [rbx+30h]
0x18000ab63  mov     rax, qword ptr [rsp+98h+var_58+8]
0x18000ab68  mov     [rbx+30h], rax
0x18000ab6c  test    rsi, rsi
0x18000ab6f  jz      short loc_18000AB85
0x18000ab71  call    cs:__imp_GetProcessHeap
0x18000ab77  mov     r8, rsi; lpMem
0x18000ab7a  xor     edx, edx; dwFlags
0x18000ab7c  mov     rcx, rax; hHeap
0x18000ab7f  call    cs:__imp_HeapFree
0x18000ab85  mov     rsi, [rsp+98h+Buf1]
0x18000ab8d  mov     ebp, [rsp+98h+arg_28]
0x18000ab94  mov     byte ptr [rbx+3Ah], 1
0x18000ab98  jmp     short loc_18000AB9F
0x18000ab9a  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x18000ab9f  test    rdi, rdi
0x18000aba2  jz      short loc_18000ABC8
0x18000aba4  call    cs:__imp_GetProcessHeap
0x18000abaa  mov     r8, rdi; lpMem
0x18000abad  xor     edx, edx; dwFlags
0x18000abaf  mov     rcx, rax; hHeap
0x18000abb2  call    cs:__imp_HeapFree
0x18000abb8  jmp     short loc_18000ABC8
0x18000abba  cmp     byte ptr [rbx+3Ah], 0
0x18000abbe  jz      short loc_18000ABC8
0x18000abc0  mov     rcx, r14; this
0x18000abc3  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000abc8  mov     [rsp+98h+var_70], ebp; unsigned int
0x18000abcc  mov     r9, r13; void *
0x18000abcf  mov     r8, r15; Size
0x18000abd2  mov     [rsp+98h+var_78], r12; unsigned __int64
0x18000abd7  mov     rdx, rsi; Buf1
0x18000abda  mov     rcx, rbx; this
0x18000abdd  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000abe2  add     rsp, 58h
0x18000abe6  pop     r15
0x18000abe8  pop     r14
0x18000abea  pop     r13
0x18000abec  pop     r12
0x18000abee  pop     rdi
0x18000abef  pop     rsi
0x18000abf0  pop     rbp
0x18000abf1  pop     rbx
0x18000abf2  retn
0x18000abf3  mov     rcx, [rsp+98h]; this
0x18000abfb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
