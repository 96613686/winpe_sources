# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x14000d740`
- end: `0x14000d8e9`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x14000c080`
- `0x14000d634`
- `0x14000d668`

## callees

- `0x14000d740`
- `0x14000d8f0`
- `0x14000e994`
- `0x14000ea94`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d7fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d867`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d89a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d7fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d867`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d89a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d7ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d859`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d88c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d7ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d859`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d88c`

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
0x14000d740  mov     [rsp+Buf1], rdx
0x14000d745  push    rbx
0x14000d746  push    rbp
0x14000d747  push    rsi
0x14000d748  push    rdi
0x14000d749  push    r12
0x14000d74b  push    r13
0x14000d74d  push    r14
0x14000d74f  push    r15
0x14000d751  sub     rsp, 58h
0x14000d755  mov     ebp, [rsp+98h+arg_28]
0x14000d75c  mov     r13, r9
0x14000d75f  mov     r12, [rsp+98h+arg_20]
0x14000d767  mov     r15, r8
0x14000d76a  mov     [rsp+98h+var_70], ebp; unsigned int
0x14000d76e  mov     rsi, rdx
0x14000d771  mov     [rsp+98h+var_78], r12; unsigned __int64
0x14000d776  mov     rbx, rcx
0x14000d779  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x14000d77e  test    al, al
0x14000d780  jz      short loc_14000D789
0x14000d782  mov     al, 1
0x14000d784  jmp     loc_14000D8CA
0x14000d789  lea     rdx, [r12+20h]
0x14000d78e  add     rdx, r15; unsigned __int64
0x14000d791  lea     r14, [rbx+18h]
0x14000d795  cmp     qword ptr [r14], 0
0x14000d799  jnz     loc_14000D8A2
0x14000d79f  xorps   xmm0, xmm0
0x14000d7a2  lea     rcx, [rsp+98h+var_68]; this
0x14000d7a7  xorps   xmm1, xmm1
0x14000d7aa  add     rdx, 0Ah; unsigned __int64
0x14000d7ae  movdqu  [rsp+98h+var_68], xmm0
0x14000d7b4  movdqu  [rsp+98h+var_58], xmm1
0x14000d7ba  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000d7bf  test    al, al
0x14000d7c1  jz      loc_14000D882
0x14000d7c7  mov     rdi, qword ptr [rsp+98h+var_58]
0x14000d7cc  mov     rsi, qword ptr [rsp+98h+var_68]
0x14000d7d1  sub     rdi, rsi
0x14000d7d4  cmp     rdi, 0Ah
0x14000d7d8  jb      loc_14000D8DB
0x14000d7de  mov     rbp, [rbx+30h]
0x14000d7e2  mov     qword ptr [rbx+30h], 0
0x14000d7ea  test    rbp, rbp
0x14000d7ed  jz      short loc_14000D803
0x14000d7ef  call    cs:__imp_GetProcessHeap
0x14000d7f5  mov     r8, rbp; lpMem
0x14000d7f8  xor     edx, edx; dwFlags
0x14000d7fa  mov     rcx, rax; hHeap
0x14000d7fd  call    cs:__imp_HeapFree
0x14000d803  mov     [r14], rsi
0x14000d806  lea     rax, [rdi+rsi]
0x14000d80a  mov     [rbx+28h], rax
0x14000d80e  xor     edi, edi
0x14000d810  xor     eax, eax
0x14000d812  mov     byte ptr [rbx+39h], 0
0x14000d816  mov     [rsi], ax
0x14000d819  movzx   eax, word ptr [rbx]
0x14000d81c  mov     [rsi+2], ax
0x14000d820  movzx   eax, word ptr [rbx+2]
0x14000d824  mov     [rsi+4], ax
0x14000d828  mov     al, [rbx+4]
0x14000d82b  mov     [rsi+8], al
0x14000d82e  movzx   eax, word ptr [rbx+6]
0x14000d832  mov     [rsi+6], ax
0x14000d836  mov     al, [rbx+8]
0x14000d839  mov     [rsi+9], al
0x14000d83c  mov     rax, [r14]
0x14000d83f  add     rax, 0Ah
0x14000d843  mov     [rbx+20h], rax
0x14000d847  mov     rsi, [rbx+30h]
0x14000d84b  mov     rax, qword ptr [rsp+98h+var_58+8]
0x14000d850  mov     [rbx+30h], rax
0x14000d854  test    rsi, rsi
0x14000d857  jz      short loc_14000D86D
0x14000d859  call    cs:__imp_GetProcessHeap
0x14000d85f  mov     r8, rsi; lpMem
0x14000d862  xor     edx, edx; dwFlags
0x14000d864  mov     rcx, rax; hHeap
0x14000d867  call    cs:__imp_HeapFree
0x14000d86d  mov     rsi, [rsp+98h+Buf1]
0x14000d875  mov     ebp, [rsp+98h+arg_28]
0x14000d87c  mov     byte ptr [rbx+3Ah], 1
0x14000d880  jmp     short loc_14000D887
0x14000d882  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x14000d887  test    rdi, rdi
0x14000d88a  jz      short loc_14000D8B0
0x14000d88c  call    cs:__imp_GetProcessHeap
0x14000d892  mov     r8, rdi; lpMem
0x14000d895  xor     edx, edx; dwFlags
0x14000d897  mov     rcx, rax; hHeap
0x14000d89a  call    cs:__imp_HeapFree
0x14000d8a0  jmp     short loc_14000D8B0
0x14000d8a2  cmp     byte ptr [rbx+3Ah], 0
0x14000d8a6  jz      short loc_14000D8B0
0x14000d8a8  mov     rcx, r14; this
0x14000d8ab  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000d8b0  mov     [rsp+98h+var_70], ebp; unsigned int
0x14000d8b4  mov     r9, r13; void *
0x14000d8b7  mov     r8, r15; Size
0x14000d8ba  mov     [rsp+98h+var_78], r12; unsigned __int64
0x14000d8bf  mov     rdx, rsi; Buf1
0x14000d8c2  mov     rcx, rbx; this
0x14000d8c5  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x14000d8ca  add     rsp, 58h
0x14000d8ce  pop     r15
0x14000d8d0  pop     r14
0x14000d8d2  pop     r13
0x14000d8d4  pop     r12
0x14000d8d6  pop     rdi
0x14000d8d7  pop     rsi
0x14000d8d8  pop     rbp
0x14000d8d9  pop     rbx
0x14000d8da  retn
0x14000d8db  mov     rcx, [rsp+98h]; this
0x14000d8e3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
