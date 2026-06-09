# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18000acd4`
- end: `0x18000ae89`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `437`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180008730`
- `0x18000abd0`
- `0x18000ac04`

## callees

- `0x18000acd4`
- `0x18000ae90`
- `0x18000ce34`
- `0x18000cef4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ad91`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000adfb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ae2e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ad91`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000adfb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ae2e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ad83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aded`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ae20`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ad83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aded`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ae20`

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
  const char *v14; // r9
  __int64 v15; // rsi
  __int64 v16; // rdi
  void *v17; // rbp
  HANDLE ProcessHeap; // rax
  void *v19; // rdi
  void *v20; // rsi
  HANDLE v21; // rax
  HANDLE v22; // rax
  __int128 v23; // [rsp+30h] [rbp-68h] BYREF
  __int128 v24; // [rsp+40h] [rbp-58h]
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
    v23 = 0;
    v24 = 0;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&v23, v12 + 10) )
    {
      v15 = v23;
      v16 = v24 - v23;
      if ( (_QWORD)v24 - (_QWORD)v23 < 0xAu )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x14C9,
          (int)"onecore\\internal\\sdk\\inc\\wil\\Staging.h",
          v14);
      v17 = (void *)*((_QWORD *)this + 6);
      *((_QWORD *)this + 6) = 0;
      if ( v17 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v17);
      }
      *v13 = v15;
      *((_QWORD *)this + 5) = v16 + v15;
      v19 = 0;
      *((_BYTE *)this + 57) = 0;
      *(_WORD *)v15 = 0;
      *(_WORD *)(v15 + 2) = *(_WORD *)this;
      *(_WORD *)(v15 + 4) = *((_WORD *)this + 1);
      *(_BYTE *)(v15 + 8) = *((_BYTE *)this + 4);
      *(_WORD *)(v15 + 6) = *((_WORD *)this + 3);
      *(_BYTE *)(v15 + 9) = *((_BYTE *)this + 8);
      *((_QWORD *)this + 4) = *v13 + 10LL;
      v20 = (void *)*((_QWORD *)this + 6);
      *((_QWORD *)this + 6) = *((_QWORD *)&v24 + 1);
      if ( v20 )
      {
        v21 = GetProcessHeap();
        HeapFree(v21, 0, v20);
      }
      v9 = a2;
      v6 = a6;
      *((_BYTE *)this + 58) = 1;
    }
    else
    {
      v19 = (void *)*((_QWORD *)&v24 + 1);
    }
    if ( v19 )
    {
      v22 = GetProcessHeap();
      HeapFree(v22, 0, v19);
    }
  }
  return wil::details_abi::RawUsageIndex::RecordUsageInternal(this, v9, a3, a4, a5, v6);
}

```

## disassembly

```asm
0x18000acd4  mov     [rsp+Buf1], rdx
0x18000acd9  push    rbx
0x18000acda  push    rbp
0x18000acdb  push    rsi
0x18000acdc  push    rdi
0x18000acdd  push    r12
0x18000acdf  push    r13
0x18000ace1  push    r14
0x18000ace3  push    r15
0x18000ace5  sub     rsp, 58h
0x18000ace9  mov     ebp, [rsp+98h+arg_28]
0x18000acf0  mov     r13, r9
0x18000acf3  mov     r12, [rsp+98h+arg_20]
0x18000acfb  mov     r15, r8
0x18000acfe  mov     [rsp+98h+var_70], ebp; unsigned int
0x18000ad02  mov     rsi, rdx
0x18000ad05  mov     [rsp+98h+var_78], r12; unsigned __int64
0x18000ad0a  mov     rbx, rcx
0x18000ad0d  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000ad12  test    al, al
0x18000ad14  jz      short loc_18000AD1D
0x18000ad16  mov     al, 1
0x18000ad18  jmp     loc_18000AE5E
0x18000ad1d  lea     rdx, [r12+20h]
0x18000ad22  add     rdx, r15; unsigned __int64
0x18000ad25  lea     r14, [rbx+18h]
0x18000ad29  cmp     qword ptr [r14], 0
0x18000ad2d  jnz     loc_18000AE36
0x18000ad33  xorps   xmm0, xmm0
0x18000ad36  lea     rcx, [rsp+98h+var_68]; this
0x18000ad3b  xorps   xmm1, xmm1
0x18000ad3e  add     rdx, 0Ah; unsigned __int64
0x18000ad42  movdqu  [rsp+98h+var_68], xmm0
0x18000ad48  movdqu  [rsp+98h+var_58], xmm1
0x18000ad4e  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000ad53  test    al, al
0x18000ad55  jz      loc_18000AE16
0x18000ad5b  mov     rdi, qword ptr [rsp+98h+var_58]
0x18000ad60  mov     rsi, qword ptr [rsp+98h+var_68]
0x18000ad65  sub     rdi, rsi
0x18000ad68  cmp     rdi, 0Ah
0x18000ad6c  jb      loc_18000AE6F
0x18000ad72  mov     rbp, [rbx+30h]
0x18000ad76  mov     qword ptr [rbx+30h], 0
0x18000ad7e  test    rbp, rbp
0x18000ad81  jz      short loc_18000AD97
0x18000ad83  call    cs:__imp_GetProcessHeap
0x18000ad89  mov     r8, rbp; lpMem
0x18000ad8c  xor     edx, edx; dwFlags
0x18000ad8e  mov     rcx, rax; hHeap
0x18000ad91  call    cs:__imp_HeapFree
0x18000ad97  mov     [r14], rsi
0x18000ad9a  lea     rax, [rdi+rsi]
0x18000ad9e  mov     [rbx+28h], rax
0x18000ada2  xor     edi, edi
0x18000ada4  xor     eax, eax
0x18000ada6  mov     byte ptr [rbx+39h], 0
0x18000adaa  mov     [rsi], ax
0x18000adad  movzx   eax, word ptr [rbx]
0x18000adb0  mov     [rsi+2], ax
0x18000adb4  movzx   eax, word ptr [rbx+2]
0x18000adb8  mov     [rsi+4], ax
0x18000adbc  mov     al, [rbx+4]
0x18000adbf  mov     [rsi+8], al
0x18000adc2  movzx   eax, word ptr [rbx+6]
0x18000adc6  mov     [rsi+6], ax
0x18000adca  mov     al, [rbx+8]
0x18000adcd  mov     [rsi+9], al
0x18000add0  mov     rax, [r14]
0x18000add3  add     rax, 0Ah
0x18000add7  mov     [rbx+20h], rax
0x18000addb  mov     rsi, [rbx+30h]
0x18000addf  mov     rax, qword ptr [rsp+98h+var_58+8]
0x18000ade4  mov     [rbx+30h], rax
0x18000ade8  test    rsi, rsi
0x18000adeb  jz      short loc_18000AE01
0x18000aded  call    cs:__imp_GetProcessHeap
0x18000adf3  mov     r8, rsi; lpMem
0x18000adf6  xor     edx, edx; dwFlags
0x18000adf8  mov     rcx, rax; hHeap
0x18000adfb  call    cs:__imp_HeapFree
0x18000ae01  mov     rsi, [rsp+98h+Buf1]
0x18000ae09  mov     ebp, [rsp+98h+arg_28]
0x18000ae10  mov     byte ptr [rbx+3Ah], 1
0x18000ae14  jmp     short loc_18000AE1B
0x18000ae16  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x18000ae1b  test    rdi, rdi
0x18000ae1e  jz      short loc_18000AE44
0x18000ae20  call    cs:__imp_GetProcessHeap
0x18000ae26  mov     r8, rdi; lpMem
0x18000ae29  xor     edx, edx; dwFlags
0x18000ae2b  mov     rcx, rax; hHeap
0x18000ae2e  call    cs:__imp_HeapFree
0x18000ae34  jmp     short loc_18000AE44
0x18000ae36  cmp     byte ptr [rbx+3Ah], 0
0x18000ae3a  jz      short loc_18000AE44
0x18000ae3c  mov     rcx, r14; this
0x18000ae3f  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000ae44  mov     [rsp+98h+var_70], ebp; unsigned int
0x18000ae48  mov     r9, r13; void *
0x18000ae4b  mov     r8, r15; Size
0x18000ae4e  mov     [rsp+98h+var_78], r12; unsigned __int64
0x18000ae53  mov     rdx, rsi; Buf1
0x18000ae56  mov     rcx, rbx; this
0x18000ae59  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000ae5e  add     rsp, 58h
0x18000ae62  pop     r15
0x18000ae64  pop     r14
0x18000ae66  pop     r13
0x18000ae68  pop     r12
0x18000ae6a  pop     rdi
0x18000ae6b  pop     rsi
0x18000ae6c  pop     rbp
0x18000ae6d  pop     rbx
0x18000ae6e  retn
0x18000ae6f  mov     rcx, [rsp+98h]; this
0x18000ae77  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Stagi"...
0x18000ae7e  mov     edx, 14C9h; void *
0x18000ae83  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
