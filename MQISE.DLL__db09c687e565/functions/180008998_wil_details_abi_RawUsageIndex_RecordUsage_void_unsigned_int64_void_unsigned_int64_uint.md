# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180008998`
- end: `0x180008b49`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `433`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800042b0`
- `0x180008894`
- `0x1800088c8`

## callees

- `0x180008998`
- `0x180008b50`
- `0x18000b3e4`
- `0x18000c40c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180008a4f`
- `KERNEL32!GetProcessHeap` at `0x180008abf`
- `KERNEL32!GetProcessHeap` at `0x180008af3`
- `KERNEL32!GetProcessHeap` at `0x180008a4f`
- `KERNEL32!GetProcessHeap` at `0x180008abf`
- `KERNEL32!GetProcessHeap` at `0x180008af3`
- `KERNEL32!HeapFree` at `0x180008a5d`
- `KERNEL32!HeapFree` at `0x180008acd`
- `KERNEL32!HeapFree` at `0x180008b01`
- `KERNEL32!HeapFree` at `0x180008a5d`
- `KERNEL32!HeapFree` at `0x180008acd`
- `KERNEL32!HeapFree` at `0x180008b01`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall wil::details_abi::RawUsageIndex::RecordUsage(
        wil::details_abi::RawUsageIndex *this,
        void *a2,
        size_t a3,
        void *a4,
        unsigned __int64 a5,
        unsigned int a6)
{
  void *v8; // rsi
  unsigned int v10; // ebp
  unsigned __int64 v12; // rdx
  _QWORD *v13; // r14
  void *v14; // rdx
  unsigned int v15; // r8d
  const char *v16; // r9
  __int64 v17; // rsi
  __int64 v18; // rdi
  void *v19; // rbp
  HANDLE ProcessHeap; // rax
  __int64 v21; // rax
  void *v22; // rdi
  void *v23; // rsi
  HANDLE v24; // rax
  HANDLE v25; // rax
  __int128 v26; // [rsp+30h] [rbp-68h] BYREF
  __int128 v27; // [rsp+40h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v8 = a2;
  v10 = a6;
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
      *((_BYTE *)this + 57) = 0;
      *(_WORD *)v17 = 0;
      *(_WORD *)(v17 + 2) = *(_WORD *)this;
      *(_WORD *)(v17 + 4) = *((_WORD *)this + 1);
      *(_BYTE *)(v17 + 8) = *((_BYTE *)this + 4);
      *(_WORD *)(v17 + 6) = *((_WORD *)this + 3);
      *(_BYTE *)(v17 + 9) = *((_BYTE *)this + 8);
      *((_QWORD *)this + 4) = *v13 + 10LL;
      v21 = *((_QWORD *)&v27 + 1);
      v22 = 0;
      *((_QWORD *)&v27 + 1) = 0;
      v23 = (void *)*((_QWORD *)this + 6);
      *((_QWORD *)this + 6) = v21;
      if ( v23 )
      {
        v24 = GetProcessHeap();
        HeapFree(v24, 0, v23);
      }
      *((_BYTE *)this + 58) = 1;
      v8 = a2;
      v10 = a6;
    }
    else
    {
      v22 = (void *)*((_QWORD *)&v27 + 1);
    }
    if ( v22 )
    {
      v25 = GetProcessHeap();
      HeapFree(v25, 0, v22);
    }
  }
  return wil::details_abi::RawUsageIndex::RecordUsageInternal(this, v8, a3, a4, a5, v10);
}

```

## disassembly

```asm
0x180008998  mov     [rsp+Buf1], rdx
0x18000899d  push    rbx
0x18000899e  push    rbp
0x18000899f  push    rsi
0x1800089a0  push    rdi
0x1800089a1  push    r12
0x1800089a3  push    r13
0x1800089a5  push    r14
0x1800089a7  push    r15
0x1800089a9  sub     rsp, 58h
0x1800089ad  mov     r13, r9
0x1800089b0  mov     r15, r8
0x1800089b3  mov     rsi, rdx
0x1800089b6  mov     rbx, rcx
0x1800089b9  mov     ebp, [rsp+98h+arg_28]
0x1800089c0  mov     [rsp+98h+var_70], ebp; unsigned int
0x1800089c4  mov     r12, [rsp+98h+arg_20]
0x1800089cc  mov     [rsp+98h+var_78], r12; unsigned __int64
0x1800089d1  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1800089d6  test    al, al
0x1800089d8  jz      short loc_1800089E1
0x1800089da  mov     al, 1
0x1800089dc  jmp     loc_180008B32
0x1800089e1  lea     rdx, [r12+20h]
0x1800089e6  add     rdx, r15; unsigned __int64
0x1800089e9  lea     r14, [rbx+18h]
0x1800089ed  cmp     qword ptr [r14], 0
0x1800089f1  jnz     loc_180008B0A
0x1800089f7  xorps   xmm0, xmm0
0x1800089fa  movdqu  [rsp+98h+var_68], xmm0
0x180008a00  xorps   xmm1, xmm1
0x180008a03  movdqu  [rsp+98h+var_58], xmm1
0x180008a09  add     rdx, 0Ah; unsigned __int64
0x180008a0d  lea     rcx, [rsp+98h+var_68]; this
0x180008a12  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180008a17  test    al, al
0x180008a19  jz      loc_180008AE9
0x180008a1f  mov     rdi, qword ptr [rsp+98h+var_58]
0x180008a24  mov     rsi, qword ptr [rsp+98h+var_68]
0x180008a29  sub     rdi, rsi
0x180008a2c  mov     rcx, [rsp+98h]; this
0x180008a34  cmp     rdi, 0Ah
0x180008a38  jb      loc_180008B43
0x180008a3e  mov     rbp, [rbx+30h]
0x180008a42  mov     qword ptr [rbx+30h], 0
0x180008a4a  test    rbp, rbp
0x180008a4d  jz      short loc_180008A64
0x180008a4f  call    cs:__imp_GetProcessHeap
0x180008a55  mov     rcx, rax; hHeap
0x180008a58  mov     r8, rbp; lpMem
0x180008a5b  xor     edx, edx; dwFlags
0x180008a5d  call    cs:__imp_HeapFree
0x180008a63  nop
0x180008a64  mov     [r14], rsi
0x180008a67  lea     rax, [rdi+rsi]
0x180008a6b  mov     [rbx+28h], rax
0x180008a6f  mov     byte ptr [rbx+39h], 0
0x180008a73  xor     eax, eax
0x180008a75  mov     [rsi], ax
0x180008a78  movzx   eax, word ptr [rbx]
0x180008a7b  mov     [rsi+2], ax
0x180008a7f  movzx   eax, word ptr [rbx+2]
0x180008a83  mov     [rsi+4], ax
0x180008a87  mov     al, [rbx+4]
0x180008a8a  mov     [rsi+8], al
0x180008a8d  movzx   eax, word ptr [rbx+6]
0x180008a91  mov     [rsi+6], ax
0x180008a95  mov     al, [rbx+8]
0x180008a98  mov     [rsi+9], al
0x180008a9b  mov     rax, [r14]
0x180008a9e  add     rax, 0Ah
0x180008aa2  mov     [rbx+20h], rax
0x180008aa6  mov     rax, qword ptr [rsp+98h+var_58+8]
0x180008aab  xor     edi, edi
0x180008aad  mov     qword ptr [rsp+98h+var_58+8], rdi
0x180008ab2  mov     rsi, [rbx+30h]
0x180008ab6  mov     [rbx+30h], rax
0x180008aba  test    rsi, rsi
0x180008abd  jz      short loc_180008AD4
0x180008abf  call    cs:__imp_GetProcessHeap
0x180008ac5  mov     rcx, rax; hHeap
0x180008ac8  mov     r8, rsi; lpMem
0x180008acb  xor     edx, edx; dwFlags
0x180008acd  call    cs:__imp_HeapFree
0x180008ad3  nop
0x180008ad4  mov     byte ptr [rbx+3Ah], 1
0x180008ad8  mov     rsi, [rsp+98h+Buf1]
0x180008ae0  mov     ebp, [rsp+98h+arg_28]
0x180008ae7  jmp     short loc_180008AEE
0x180008ae9  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x180008aee  test    rdi, rdi
0x180008af1  jz      short loc_180008B08
0x180008af3  call    cs:__imp_GetProcessHeap
0x180008af9  mov     rcx, rax; hHeap
0x180008afc  mov     r8, rdi; lpMem
0x180008aff  xor     edx, edx; dwFlags
0x180008b01  call    cs:__imp_HeapFree
0x180008b07  nop
0x180008b08  jmp     short loc_180008B18
0x180008b0a  cmp     byte ptr [rbx+3Ah], 0
0x180008b0e  jz      short loc_180008B18
0x180008b10  mov     rcx, r14; this
0x180008b13  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180008b18  mov     [rsp+98h+var_70], ebp; unsigned int
0x180008b1c  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180008b21  mov     r9, r13; void *
0x180008b24  mov     r8, r15; Size
0x180008b27  mov     rdx, rsi; Buf1
0x180008b2a  mov     rcx, rbx; this
0x180008b2d  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180008b32  add     rsp, 58h
0x180008b36  pop     r15
0x180008b38  pop     r14
0x180008b3a  pop     r13
0x180008b3c  pop     r12
0x180008b3e  pop     rdi
0x180008b3f  pop     rsi
0x180008b40  pop     rbp
0x180008b41  pop     rbx
0x180008b42  retn
0x180008b43  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
