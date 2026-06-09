# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x1800079c8`
- end: `0x180007b8b`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `451`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *Buf1, size_t Size, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800037b0`
- `0x180007864`
- `0x1800078b8`

## callees

- `0x1800079c8`
- `0x180007b94`
- `0x18000ab38`
- `0x18000af9c`
- `0x18000c610`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a95`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007aff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007b2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a95`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007aff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007b2f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a87`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007af1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a87`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007af1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b21`

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
0x1800079c8  push    rbx
0x1800079ca  push    rbp
0x1800079cb  push    rsi
0x1800079cc  push    rdi
0x1800079cd  push    r12
0x1800079cf  push    r13
0x1800079d1  push    r14
0x1800079d3  push    r15
0x1800079d5  sub     rsp, 68h
0x1800079d9  mov     rax, cs:__security_cookie
0x1800079e0  xor     rax, rsp
0x1800079e3  mov     [rsp+0A8h+var_50], rax
0x1800079e8  mov     ebp, [rsp+0A8h+arg_28]
0x1800079ef  mov     rsi, r9
0x1800079f2  mov     r12, [rsp+0A8h+arg_20]
0x1800079fa  mov     r15, r8
0x1800079fd  mov     [rsp+0A8h+var_80], ebp; unsigned int
0x180007a01  mov     r13, rdx
0x180007a04  mov     [rsp+0A8h+var_88], r12; unsigned __int64
0x180007a09  mov     rbx, rcx
0x180007a0c  mov     [rsp+0A8h+var_78], r9
0x180007a11  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180007a16  test    al, al
0x180007a18  jz      short loc_180007A21
0x180007a1a  mov     al, 1
0x180007a1c  jmp     loc_180007B5F
0x180007a21  lea     rdx, [r12+20h]
0x180007a26  add     rdx, r15; unsigned __int64
0x180007a29  lea     r14, [rbx+18h]
0x180007a2d  cmp     qword ptr [r14], 0
0x180007a31  jnz     loc_180007B37
0x180007a37  xorps   xmm0, xmm0
0x180007a3a  lea     rcx, [rsp+0A8h+var_70]; this
0x180007a3f  xorps   xmm1, xmm1
0x180007a42  add     rdx, 0Ah; unsigned __int64
0x180007a46  movdqu  [rsp+0A8h+var_70], xmm0
0x180007a4c  movdqu  [rsp+0A8h+var_60], xmm1
0x180007a52  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180007a57  test    al, al
0x180007a59  jz      loc_180007B17
0x180007a5f  mov     rdi, qword ptr [rsp+0A8h+var_60]
0x180007a64  mov     rsi, qword ptr [rsp+0A8h+var_70]
0x180007a69  sub     rdi, rsi
0x180007a6c  cmp     rdi, 0Ah
0x180007a70  jb      loc_180007B7D
0x180007a76  mov     rbp, [rbx+30h]
0x180007a7a  mov     qword ptr [rbx+30h], 0
0x180007a82  test    rbp, rbp
0x180007a85  jz      short loc_180007A9B
0x180007a87  call    cs:__imp_GetProcessHeap
0x180007a8d  mov     r8, rbp; lpMem
0x180007a90  xor     edx, edx; dwFlags
0x180007a92  mov     rcx, rax; hHeap
0x180007a95  call    cs:__imp_HeapFree
0x180007a9b  mov     [r14], rsi
0x180007a9e  lea     rax, [rdi+rsi]
0x180007aa2  mov     [rbx+28h], rax
0x180007aa6  xor     edi, edi
0x180007aa8  xor     eax, eax
0x180007aaa  mov     byte ptr [rbx+39h], 0
0x180007aae  mov     [rsi], ax
0x180007ab1  movzx   eax, word ptr [rbx]
0x180007ab4  mov     [rsi+2], ax
0x180007ab8  movzx   eax, word ptr [rbx+2]
0x180007abc  mov     [rsi+4], ax
0x180007ac0  mov     al, [rbx+4]
0x180007ac3  mov     [rsi+8], al
0x180007ac6  movzx   eax, word ptr [rbx+6]
0x180007aca  mov     [rsi+6], ax
0x180007ace  mov     al, [rbx+8]
0x180007ad1  mov     [rsi+9], al
0x180007ad4  mov     rax, [r14]
0x180007ad7  add     rax, 0Ah
0x180007adb  mov     [rbx+20h], rax
0x180007adf  mov     rsi, [rbx+30h]
0x180007ae3  mov     rax, qword ptr [rsp+0A8h+var_60+8]
0x180007ae8  mov     [rbx+30h], rax
0x180007aec  test    rsi, rsi
0x180007aef  jz      short loc_180007B05
0x180007af1  call    cs:__imp_GetProcessHeap
0x180007af7  mov     r8, rsi; lpMem
0x180007afa  xor     edx, edx; dwFlags
0x180007afc  mov     rcx, rax; hHeap
0x180007aff  call    cs:__imp_HeapFree
0x180007b05  mov     rsi, [rsp+0A8h+var_78]
0x180007b0a  mov     ebp, [rsp+0A8h+arg_28]
0x180007b11  mov     byte ptr [rbx+3Ah], 1
0x180007b15  jmp     short loc_180007B1C
0x180007b17  mov     rdi, qword ptr [rsp+0A8h+var_60+8]
0x180007b1c  test    rdi, rdi
0x180007b1f  jz      short loc_180007B45
0x180007b21  call    cs:__imp_GetProcessHeap
0x180007b27  mov     r8, rdi; lpMem
0x180007b2a  xor     edx, edx; dwFlags
0x180007b2c  mov     rcx, rax; hHeap
0x180007b2f  call    cs:__imp_HeapFree
0x180007b35  jmp     short loc_180007B45
0x180007b37  cmp     byte ptr [rbx+3Ah], 0
0x180007b3b  jz      short loc_180007B45
0x180007b3d  mov     rcx, r14; this
0x180007b40  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180007b45  mov     [rsp+0A8h+var_80], ebp; unsigned int
0x180007b49  mov     r9, rsi; void *
0x180007b4c  mov     r8, r15; Size
0x180007b4f  mov     [rsp+0A8h+var_88], r12; unsigned __int64
0x180007b54  mov     rdx, r13; Buf1
0x180007b57  mov     rcx, rbx; this
0x180007b5a  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180007b5f  mov     rcx, [rsp+0A8h+var_50]
0x180007b64  xor     rcx, rsp; StackCookie
0x180007b67  call    __security_check_cookie
0x180007b6c  add     rsp, 68h
0x180007b70  pop     r15
0x180007b72  pop     r14
0x180007b74  pop     r13
0x180007b76  pop     r12
0x180007b78  pop     rdi
0x180007b79  pop     rsi
0x180007b7a  pop     rbp
0x180007b7b  pop     rbx
0x180007b7c  retn
0x180007b7d  mov     rcx, [rsp+0A8h]; this
0x180007b85  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
