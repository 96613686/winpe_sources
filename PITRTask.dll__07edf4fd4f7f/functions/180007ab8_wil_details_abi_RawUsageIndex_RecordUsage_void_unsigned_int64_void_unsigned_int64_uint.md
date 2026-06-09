# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180007ab8`
- end: `0x180007c7b`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `451`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180003d20`
- `0x180007954`
- `0x1800079a8`

## callees

- `0x180007ab8`
- `0x180007c84`
- `0x18000b874`
- `0x18000bf6c`
- `0x1800107c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b77`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007be1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007c11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b77`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007be1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007c11`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007b85`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007bef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007c1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007b85`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007bef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007c1f`

## pseudocode

```c
bool __fastcall wil::details_abi::RawUsageIndex::RecordUsage(
        wil::details_abi::RawUsageIndex *this,
        void *Buf1,
        size_t Size,
        void *a4,
        unsigned __int64 a5,
        unsigned int a6)
{
  unsigned int v6; // ebp
  void *v7; // rsi
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
  __int128 v26; // [rsp+38h] [rbp-70h] BYREF
  __int128 v27; // [rsp+48h] [rbp-60h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v6 = a6;
  v7 = a4;
  if ( wil::details_abi::RawUsageIndex::RecordUsageInternal(this, Buf1, Size, a4, a5, a6) )
    return 1;
  v12 = Size + a5 + 32;
  v13 = (_QWORD *)((char *)this + 24);
  if ( *((_QWORD *)this + 3) )
  {
    if ( *((_BYTE *)this + 58) )
      wil::details_abi::heap_buffer::ensure((wil::details_abi::RawUsageIndex *)((char *)this + 24), v12);
  }
  else
  {
    v26 = 0;
    v27 = 0;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&v26, v12 + 10) )
    {
      v17 = v26;
      v18 = v27 - v26;
      if ( (_QWORD)v27 - (_QWORD)v26 < 0xAu )
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
      *((_QWORD *)this + 6) = *((_QWORD *)&v27 + 1);
      if ( v22 )
      {
        v23 = GetProcessHeap();
        HeapFree(v23, 0, v22);
      }
      v7 = a4;
      v6 = a6;
      *((_BYTE *)this + 58) = 1;
    }
    else
    {
      v21 = (void *)*((_QWORD *)&v27 + 1);
    }
    if ( v21 )
    {
      v24 = GetProcessHeap();
      HeapFree(v24, 0, v21);
    }
  }
  return wil::details_abi::RawUsageIndex::RecordUsageInternal(this, Buf1, Size, v7, a5, v6);
}

```

## disassembly

```asm
0x180007ab8  push    rbx
0x180007aba  push    rbp
0x180007abb  push    rsi
0x180007abc  push    rdi
0x180007abd  push    r12
0x180007abf  push    r13
0x180007ac1  push    r14
0x180007ac3  push    r15
0x180007ac5  sub     rsp, 68h
0x180007ac9  mov     rax, cs:__security_cookie
0x180007ad0  xor     rax, rsp
0x180007ad3  mov     [rsp+0A8h+var_50], rax
0x180007ad8  mov     ebp, [rsp+0A8h+arg_28]
0x180007adf  mov     rsi, r9
0x180007ae2  mov     r12, [rsp+0A8h+arg_20]
0x180007aea  mov     r15, r8
0x180007aed  mov     [rsp+0A8h+var_80], ebp; unsigned int
0x180007af1  mov     r13, rdx
0x180007af4  mov     [rsp+0A8h+var_88], r12; unsigned __int64
0x180007af9  mov     rbx, rcx
0x180007afc  mov     [rsp+0A8h+var_78], r9
0x180007b01  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180007b06  test    al, al
0x180007b08  jz      short loc_180007B11
0x180007b0a  mov     al, 1
0x180007b0c  jmp     loc_180007C4F
0x180007b11  lea     rdx, [r12+20h]
0x180007b16  add     rdx, r15; unsigned __int64
0x180007b19  lea     r14, [rbx+18h]
0x180007b1d  cmp     qword ptr [r14], 0
0x180007b21  jnz     loc_180007C27
0x180007b27  xorps   xmm0, xmm0
0x180007b2a  lea     rcx, [rsp+0A8h+var_70]; this
0x180007b2f  xorps   xmm1, xmm1
0x180007b32  add     rdx, 0Ah; unsigned __int64
0x180007b36  movdqu  [rsp+0A8h+var_70], xmm0
0x180007b3c  movdqu  [rsp+0A8h+var_60], xmm1
0x180007b42  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180007b47  test    al, al
0x180007b49  jz      loc_180007C07
0x180007b4f  mov     rdi, qword ptr [rsp+0A8h+var_60]
0x180007b54  mov     rsi, qword ptr [rsp+0A8h+var_70]
0x180007b59  sub     rdi, rsi
0x180007b5c  cmp     rdi, 0Ah
0x180007b60  jb      loc_180007C6D
0x180007b66  mov     rbp, [rbx+30h]
0x180007b6a  mov     qword ptr [rbx+30h], 0
0x180007b72  test    rbp, rbp
0x180007b75  jz      short loc_180007B8B
0x180007b77  call    cs:__imp_GetProcessHeap
0x180007b7d  mov     r8, rbp; lpMem
0x180007b80  xor     edx, edx; dwFlags
0x180007b82  mov     rcx, rax; hHeap
0x180007b85  call    cs:__imp_HeapFree
0x180007b8b  mov     [r14], rsi
0x180007b8e  lea     rax, [rdi+rsi]
0x180007b92  mov     [rbx+28h], rax
0x180007b96  xor     edi, edi
0x180007b98  xor     eax, eax
0x180007b9a  mov     byte ptr [rbx+39h], 0
0x180007b9e  mov     [rsi], ax
0x180007ba1  movzx   eax, word ptr [rbx]
0x180007ba4  mov     [rsi+2], ax
0x180007ba8  movzx   eax, word ptr [rbx+2]
0x180007bac  mov     [rsi+4], ax
0x180007bb0  mov     al, [rbx+4]
0x180007bb3  mov     [rsi+8], al
0x180007bb6  movzx   eax, word ptr [rbx+6]
0x180007bba  mov     [rsi+6], ax
0x180007bbe  mov     al, [rbx+8]
0x180007bc1  mov     [rsi+9], al
0x180007bc4  mov     rax, [r14]
0x180007bc7  add     rax, 0Ah
0x180007bcb  mov     [rbx+20h], rax
0x180007bcf  mov     rsi, [rbx+30h]
0x180007bd3  mov     rax, qword ptr [rsp+0A8h+var_60+8]
0x180007bd8  mov     [rbx+30h], rax
0x180007bdc  test    rsi, rsi
0x180007bdf  jz      short loc_180007BF5
0x180007be1  call    cs:__imp_GetProcessHeap
0x180007be7  mov     r8, rsi; lpMem
0x180007bea  xor     edx, edx; dwFlags
0x180007bec  mov     rcx, rax; hHeap
0x180007bef  call    cs:__imp_HeapFree
0x180007bf5  mov     rsi, [rsp+0A8h+var_78]
0x180007bfa  mov     ebp, [rsp+0A8h+arg_28]
0x180007c01  mov     byte ptr [rbx+3Ah], 1
0x180007c05  jmp     short loc_180007C0C
0x180007c07  mov     rdi, qword ptr [rsp+0A8h+var_60+8]
0x180007c0c  test    rdi, rdi
0x180007c0f  jz      short loc_180007C35
0x180007c11  call    cs:__imp_GetProcessHeap
0x180007c17  mov     r8, rdi; lpMem
0x180007c1a  xor     edx, edx; dwFlags
0x180007c1c  mov     rcx, rax; hHeap
0x180007c1f  call    cs:__imp_HeapFree
0x180007c25  jmp     short loc_180007C35
0x180007c27  cmp     byte ptr [rbx+3Ah], 0
0x180007c2b  jz      short loc_180007C35
0x180007c2d  mov     rcx, r14; this
0x180007c30  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180007c35  mov     [rsp+0A8h+var_80], ebp; unsigned int
0x180007c39  mov     r9, rsi; void *
0x180007c3c  mov     r8, r15; Size
0x180007c3f  mov     [rsp+0A8h+var_88], r12; unsigned __int64
0x180007c44  mov     rdx, r13; Buf1
0x180007c47  mov     rcx, rbx; this
0x180007c4a  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180007c4f  mov     rcx, [rsp+0A8h+var_50]
0x180007c54  xor     rcx, rsp; StackCookie
0x180007c57  call    __security_check_cookie
0x180007c5c  add     rsp, 68h
0x180007c60  pop     r15
0x180007c62  pop     r14
0x180007c64  pop     r13
0x180007c66  pop     r12
0x180007c68  pop     rdi
0x180007c69  pop     rsi
0x180007c6a  pop     rbp
0x180007c6b  pop     rbx
0x180007c6c  retn
0x180007c6d  mov     rcx, [rsp+0A8h]; this
0x180007c75  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
