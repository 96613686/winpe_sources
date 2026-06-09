# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x140014cac`
- end: `0x140014e55`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140013590`
- `0x140014ba8`
- `0x140014bdc`

## callees

- `0x140014cac`
- `0x140014e5c`
- `0x140016244`
- `0x1400162b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140014d69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140014dd3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140014e06`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140014d69`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140014dd3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140014e06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014d5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014dc5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014df8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014d5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014dc5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140014df8`

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
0x140014cac  mov     [rsp+Buf1], rdx
0x140014cb1  push    rbx
0x140014cb2  push    rbp
0x140014cb3  push    rsi
0x140014cb4  push    rdi
0x140014cb5  push    r12
0x140014cb7  push    r13
0x140014cb9  push    r14
0x140014cbb  push    r15
0x140014cbd  sub     rsp, 58h
0x140014cc1  mov     ebp, [rsp+98h+arg_28]
0x140014cc8  mov     r13, r9
0x140014ccb  mov     r12, [rsp+98h+arg_20]
0x140014cd3  mov     r15, r8
0x140014cd6  mov     [rsp+98h+var_70], ebp; unsigned int
0x140014cda  mov     rsi, rdx
0x140014cdd  mov     [rsp+98h+var_78], r12; unsigned __int64
0x140014ce2  mov     rbx, rcx
0x140014ce5  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x140014cea  test    al, al
0x140014cec  jz      short loc_140014CF5
0x140014cee  mov     al, 1
0x140014cf0  jmp     loc_140014E36
0x140014cf5  lea     rdx, [r12+20h]
0x140014cfa  add     rdx, r15; unsigned __int64
0x140014cfd  lea     r14, [rbx+18h]
0x140014d01  cmp     qword ptr [r14], 0
0x140014d05  jnz     loc_140014E0E
0x140014d0b  xorps   xmm0, xmm0
0x140014d0e  lea     rcx, [rsp+98h+var_68]; this
0x140014d13  xorps   xmm1, xmm1
0x140014d16  add     rdx, 0Ah; unsigned __int64
0x140014d1a  movdqu  [rsp+98h+var_68], xmm0
0x140014d20  movdqu  [rsp+98h+var_58], xmm1
0x140014d26  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140014d2b  test    al, al
0x140014d2d  jz      loc_140014DEE
0x140014d33  mov     rdi, qword ptr [rsp+98h+var_58]
0x140014d38  mov     rsi, qword ptr [rsp+98h+var_68]
0x140014d3d  sub     rdi, rsi
0x140014d40  cmp     rdi, 0Ah
0x140014d44  jb      loc_140014E47
0x140014d4a  mov     rbp, [rbx+30h]
0x140014d4e  mov     qword ptr [rbx+30h], 0
0x140014d56  test    rbp, rbp
0x140014d59  jz      short loc_140014D6F
0x140014d5b  call    cs:__imp_GetProcessHeap
0x140014d61  mov     r8, rbp; lpMem
0x140014d64  xor     edx, edx; dwFlags
0x140014d66  mov     rcx, rax; hHeap
0x140014d69  call    cs:__imp_HeapFree
0x140014d6f  mov     [r14], rsi
0x140014d72  lea     rax, [rdi+rsi]
0x140014d76  mov     [rbx+28h], rax
0x140014d7a  xor     edi, edi
0x140014d7c  xor     eax, eax
0x140014d7e  mov     byte ptr [rbx+39h], 0
0x140014d82  mov     [rsi], ax
0x140014d85  movzx   eax, word ptr [rbx]
0x140014d88  mov     [rsi+2], ax
0x140014d8c  movzx   eax, word ptr [rbx+2]
0x140014d90  mov     [rsi+4], ax
0x140014d94  mov     al, [rbx+4]
0x140014d97  mov     [rsi+8], al
0x140014d9a  movzx   eax, word ptr [rbx+6]
0x140014d9e  mov     [rsi+6], ax
0x140014da2  mov     al, [rbx+8]
0x140014da5  mov     [rsi+9], al
0x140014da8  mov     rax, [r14]
0x140014dab  add     rax, 0Ah
0x140014daf  mov     [rbx+20h], rax
0x140014db3  mov     rsi, [rbx+30h]
0x140014db7  mov     rax, qword ptr [rsp+98h+var_58+8]
0x140014dbc  mov     [rbx+30h], rax
0x140014dc0  test    rsi, rsi
0x140014dc3  jz      short loc_140014DD9
0x140014dc5  call    cs:__imp_GetProcessHeap
0x140014dcb  mov     r8, rsi; lpMem
0x140014dce  xor     edx, edx; dwFlags
0x140014dd0  mov     rcx, rax; hHeap
0x140014dd3  call    cs:__imp_HeapFree
0x140014dd9  mov     rsi, [rsp+98h+Buf1]
0x140014de1  mov     ebp, [rsp+98h+arg_28]
0x140014de8  mov     byte ptr [rbx+3Ah], 1
0x140014dec  jmp     short loc_140014DF3
0x140014dee  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x140014df3  test    rdi, rdi
0x140014df6  jz      short loc_140014E1C
0x140014df8  call    cs:__imp_GetProcessHeap
0x140014dfe  mov     r8, rdi; lpMem
0x140014e01  xor     edx, edx; dwFlags
0x140014e03  mov     rcx, rax; hHeap
0x140014e06  call    cs:__imp_HeapFree
0x140014e0c  jmp     short loc_140014E1C
0x140014e0e  cmp     byte ptr [rbx+3Ah], 0
0x140014e12  jz      short loc_140014E1C
0x140014e14  mov     rcx, r14; this
0x140014e17  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140014e1c  mov     [rsp+98h+var_70], ebp; unsigned int
0x140014e20  mov     r9, r13; void *
0x140014e23  mov     r8, r15; Size
0x140014e26  mov     [rsp+98h+var_78], r12; unsigned __int64
0x140014e2b  mov     rdx, rsi; Buf1
0x140014e2e  mov     rcx, rbx; this
0x140014e31  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x140014e36  add     rsp, 58h
0x140014e3a  pop     r15
0x140014e3c  pop     r14
0x140014e3e  pop     r13
0x140014e40  pop     r12
0x140014e42  pop     rdi
0x140014e43  pop     rsi
0x140014e44  pop     rbp
0x140014e45  pop     rbx
0x140014e46  retn
0x140014e47  mov     rcx, [rsp+98h]; this
0x140014e4f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
