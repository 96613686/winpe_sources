# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180008750`
- end: `0x180008905`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `437`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180007740`
- `0x18000864c`
- `0x180008680`

## callees

- `0x1800037e4`
- `0x180008750`
- `0x18000890c`
- `0x180009a7c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800087ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008869`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000889c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800087ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008869`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000889c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000880d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008877`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800088aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000880d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008877`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800088aa`

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
          (int)"onecore\\internal\\sdk\\inc\\wil/Staging.h",
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
0x180008750  mov     [rsp+Buf1], rdx
0x180008755  push    rbx
0x180008756  push    rbp
0x180008757  push    rsi
0x180008758  push    rdi
0x180008759  push    r12
0x18000875b  push    r13
0x18000875d  push    r14
0x18000875f  push    r15
0x180008761  sub     rsp, 58h
0x180008765  mov     ebp, [rsp+98h+arg_28]
0x18000876c  mov     r13, r9
0x18000876f  mov     r12, [rsp+98h+arg_20]
0x180008777  mov     r15, r8
0x18000877a  mov     [rsp+98h+var_70], ebp; unsigned int
0x18000877e  mov     rsi, rdx
0x180008781  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180008786  mov     rbx, rcx
0x180008789  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000878e  test    al, al
0x180008790  jz      short loc_180008799
0x180008792  mov     al, 1
0x180008794  jmp     loc_1800088DA
0x180008799  lea     rdx, [r12+20h]
0x18000879e  add     rdx, r15; unsigned __int64
0x1800087a1  lea     r14, [rbx+18h]
0x1800087a5  cmp     qword ptr [r14], 0
0x1800087a9  jnz     loc_1800088B2
0x1800087af  xorps   xmm0, xmm0
0x1800087b2  lea     rcx, [rsp+98h+var_68]; this
0x1800087b7  xorps   xmm1, xmm1
0x1800087ba  add     rdx, 0Ah; unsigned __int64
0x1800087be  movdqu  [rsp+98h+var_68], xmm0
0x1800087c4  movdqu  [rsp+98h+var_58], xmm1
0x1800087ca  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800087cf  test    al, al
0x1800087d1  jz      loc_180008892
0x1800087d7  mov     rdi, qword ptr [rsp+98h+var_58]
0x1800087dc  mov     rsi, qword ptr [rsp+98h+var_68]
0x1800087e1  sub     rdi, rsi
0x1800087e4  cmp     rdi, 0Ah
0x1800087e8  jb      loc_1800088EB
0x1800087ee  mov     rbp, [rbx+30h]
0x1800087f2  mov     qword ptr [rbx+30h], 0
0x1800087fa  test    rbp, rbp
0x1800087fd  jz      short loc_180008813
0x1800087ff  call    cs:__imp_GetProcessHeap
0x180008805  mov     r8, rbp; lpMem
0x180008808  xor     edx, edx; dwFlags
0x18000880a  mov     rcx, rax; hHeap
0x18000880d  call    cs:__imp_HeapFree
0x180008813  mov     [r14], rsi
0x180008816  lea     rax, [rdi+rsi]
0x18000881a  mov     [rbx+28h], rax
0x18000881e  xor     edi, edi
0x180008820  xor     eax, eax
0x180008822  mov     byte ptr [rbx+39h], 0
0x180008826  mov     [rsi], ax
0x180008829  movzx   eax, word ptr [rbx]
0x18000882c  mov     [rsi+2], ax
0x180008830  movzx   eax, word ptr [rbx+2]
0x180008834  mov     [rsi+4], ax
0x180008838  mov     al, [rbx+4]
0x18000883b  mov     [rsi+8], al
0x18000883e  movzx   eax, word ptr [rbx+6]
0x180008842  mov     [rsi+6], ax
0x180008846  mov     al, [rbx+8]
0x180008849  mov     [rsi+9], al
0x18000884c  mov     rax, [r14]
0x18000884f  add     rax, 0Ah
0x180008853  mov     [rbx+20h], rax
0x180008857  mov     rsi, [rbx+30h]
0x18000885b  mov     rax, qword ptr [rsp+98h+var_58+8]
0x180008860  mov     [rbx+30h], rax
0x180008864  test    rsi, rsi
0x180008867  jz      short loc_18000887D
0x180008869  call    cs:__imp_GetProcessHeap
0x18000886f  mov     r8, rsi; lpMem
0x180008872  xor     edx, edx; dwFlags
0x180008874  mov     rcx, rax; hHeap
0x180008877  call    cs:__imp_HeapFree
0x18000887d  mov     rsi, [rsp+98h+Buf1]
0x180008885  mov     ebp, [rsp+98h+arg_28]
0x18000888c  mov     byte ptr [rbx+3Ah], 1
0x180008890  jmp     short loc_180008897
0x180008892  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x180008897  test    rdi, rdi
0x18000889a  jz      short loc_1800088C0
0x18000889c  call    cs:__imp_GetProcessHeap
0x1800088a2  mov     r8, rdi; lpMem
0x1800088a5  xor     edx, edx; dwFlags
0x1800088a7  mov     rcx, rax; hHeap
0x1800088aa  call    cs:__imp_HeapFree
0x1800088b0  jmp     short loc_1800088C0
0x1800088b2  cmp     byte ptr [rbx+3Ah], 0
0x1800088b6  jz      short loc_1800088C0
0x1800088b8  mov     rcx, r14; this
0x1800088bb  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800088c0  mov     [rsp+98h+var_70], ebp; unsigned int
0x1800088c4  mov     r9, r13; void *
0x1800088c7  mov     r8, r15; Size
0x1800088ca  mov     [rsp+98h+var_78], r12; unsigned __int64
0x1800088cf  mov     rdx, rsi; Buf1
0x1800088d2  mov     rcx, rbx; this
0x1800088d5  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1800088da  add     rsp, 58h
0x1800088de  pop     r15
0x1800088e0  pop     r14
0x1800088e2  pop     r13
0x1800088e4  pop     r12
0x1800088e6  pop     rdi
0x1800088e7  pop     rsi
0x1800088e8  pop     rbp
0x1800088e9  pop     rbx
0x1800088ea  retn
0x1800088eb  mov     rcx, [rsp+98h]; this
0x1800088f3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil/Stagin"...
0x1800088fa  mov     edx, 14C9h; void *
0x1800088ff  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
