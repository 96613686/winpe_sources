# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x1400088c8`
- end: `0x140008a71`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140003d00`
- `0x1400087c4`
- `0x1400087f8`

## callees

- `0x1400088c8`
- `0x140008a78`
- `0x14000b548`
- `0x14000b92c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008985`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400089ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008a22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008985`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400089ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008a22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008977`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400089e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008a14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008977`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400089e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008a14`

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
0x1400088c8  mov     [rsp+Buf1], rdx
0x1400088cd  push    rbx
0x1400088ce  push    rbp
0x1400088cf  push    rsi
0x1400088d0  push    rdi
0x1400088d1  push    r12
0x1400088d3  push    r13
0x1400088d5  push    r14
0x1400088d7  push    r15
0x1400088d9  sub     rsp, 58h
0x1400088dd  mov     ebp, [rsp+98h+arg_28]
0x1400088e4  mov     r13, r9
0x1400088e7  mov     r12, [rsp+98h+arg_20]
0x1400088ef  mov     r15, r8
0x1400088f2  mov     [rsp+98h+var_70], ebp; unsigned int
0x1400088f6  mov     rsi, rdx
0x1400088f9  mov     [rsp+98h+var_78], r12; unsigned __int64
0x1400088fe  mov     rbx, rcx
0x140008901  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x140008906  test    al, al
0x140008908  jz      short loc_140008911
0x14000890a  mov     al, 1
0x14000890c  jmp     loc_140008A52
0x140008911  lea     rdx, [r12+20h]
0x140008916  add     rdx, r15; unsigned __int64
0x140008919  lea     r14, [rbx+18h]
0x14000891d  cmp     qword ptr [r14], 0
0x140008921  jnz     loc_140008A2A
0x140008927  xorps   xmm0, xmm0
0x14000892a  lea     rcx, [rsp+98h+var_68]; this
0x14000892f  xorps   xmm1, xmm1
0x140008932  add     rdx, 0Ah; unsigned __int64
0x140008936  movdqu  [rsp+98h+var_68], xmm0
0x14000893c  movdqu  [rsp+98h+var_58], xmm1
0x140008942  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140008947  test    al, al
0x140008949  jz      loc_140008A0A
0x14000894f  mov     rdi, qword ptr [rsp+98h+var_58]
0x140008954  mov     rsi, qword ptr [rsp+98h+var_68]
0x140008959  sub     rdi, rsi
0x14000895c  cmp     rdi, 0Ah
0x140008960  jb      loc_140008A63
0x140008966  mov     rbp, [rbx+30h]
0x14000896a  mov     qword ptr [rbx+30h], 0
0x140008972  test    rbp, rbp
0x140008975  jz      short loc_14000898B
0x140008977  call    cs:__imp_GetProcessHeap
0x14000897d  mov     r8, rbp; lpMem
0x140008980  xor     edx, edx; dwFlags
0x140008982  mov     rcx, rax; hHeap
0x140008985  call    cs:__imp_HeapFree
0x14000898b  mov     [r14], rsi
0x14000898e  lea     rax, [rdi+rsi]
0x140008992  mov     [rbx+28h], rax
0x140008996  xor     edi, edi
0x140008998  xor     eax, eax
0x14000899a  mov     byte ptr [rbx+39h], 0
0x14000899e  mov     [rsi], ax
0x1400089a1  movzx   eax, word ptr [rbx]
0x1400089a4  mov     [rsi+2], ax
0x1400089a8  movzx   eax, word ptr [rbx+2]
0x1400089ac  mov     [rsi+4], ax
0x1400089b0  mov     al, [rbx+4]
0x1400089b3  mov     [rsi+8], al
0x1400089b6  movzx   eax, word ptr [rbx+6]
0x1400089ba  mov     [rsi+6], ax
0x1400089be  mov     al, [rbx+8]
0x1400089c1  mov     [rsi+9], al
0x1400089c4  mov     rax, [r14]
0x1400089c7  add     rax, 0Ah
0x1400089cb  mov     [rbx+20h], rax
0x1400089cf  mov     rsi, [rbx+30h]
0x1400089d3  mov     rax, qword ptr [rsp+98h+var_58+8]
0x1400089d8  mov     [rbx+30h], rax
0x1400089dc  test    rsi, rsi
0x1400089df  jz      short loc_1400089F5
0x1400089e1  call    cs:__imp_GetProcessHeap
0x1400089e7  mov     r8, rsi; lpMem
0x1400089ea  xor     edx, edx; dwFlags
0x1400089ec  mov     rcx, rax; hHeap
0x1400089ef  call    cs:__imp_HeapFree
0x1400089f5  mov     rsi, [rsp+98h+Buf1]
0x1400089fd  mov     ebp, [rsp+98h+arg_28]
0x140008a04  mov     byte ptr [rbx+3Ah], 1
0x140008a08  jmp     short loc_140008A0F
0x140008a0a  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x140008a0f  test    rdi, rdi
0x140008a12  jz      short loc_140008A38
0x140008a14  call    cs:__imp_GetProcessHeap
0x140008a1a  mov     r8, rdi; lpMem
0x140008a1d  xor     edx, edx; dwFlags
0x140008a1f  mov     rcx, rax; hHeap
0x140008a22  call    cs:__imp_HeapFree
0x140008a28  jmp     short loc_140008A38
0x140008a2a  cmp     byte ptr [rbx+3Ah], 0
0x140008a2e  jz      short loc_140008A38
0x140008a30  mov     rcx, r14; this
0x140008a33  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140008a38  mov     [rsp+98h+var_70], ebp; unsigned int
0x140008a3c  mov     r9, r13; void *
0x140008a3f  mov     r8, r15; Size
0x140008a42  mov     [rsp+98h+var_78], r12; unsigned __int64
0x140008a47  mov     rdx, rsi; Buf1
0x140008a4a  mov     rcx, rbx; this
0x140008a4d  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x140008a52  add     rsp, 58h
0x140008a56  pop     r15
0x140008a58  pop     r14
0x140008a5a  pop     r13
0x140008a5c  pop     r12
0x140008a5e  pop     rdi
0x140008a5f  pop     rsi
0x140008a60  pop     rbp
0x140008a61  pop     rbx
0x140008a62  retn
0x140008a63  mov     rcx, [rsp+98h]; this
0x140008a6b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
