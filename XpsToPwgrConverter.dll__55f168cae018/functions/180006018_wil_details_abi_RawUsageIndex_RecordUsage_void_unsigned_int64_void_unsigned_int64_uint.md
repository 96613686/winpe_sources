# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180006018`
- end: `0x1800061c1`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800036a0`
- `0x180005f14`
- `0x180005f48`

## callees

- `0x180006018`
- `0x1800061c8`
- `0x180008428`
- `0x18000854c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800060d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000613f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006172`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800060d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000613f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006172`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800060c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006131`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006164`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800060c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006131`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006164`

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
0x180006018  mov     [rsp+Buf1], rdx
0x18000601d  push    rbx
0x18000601e  push    rbp
0x18000601f  push    rsi
0x180006020  push    rdi
0x180006021  push    r12
0x180006023  push    r13
0x180006025  push    r14
0x180006027  push    r15
0x180006029  sub     rsp, 58h
0x18000602d  mov     ebp, [rsp+98h+arg_28]
0x180006034  mov     r13, r9
0x180006037  mov     r12, [rsp+98h+arg_20]
0x18000603f  mov     r15, r8
0x180006042  mov     [rsp+98h+var_70], ebp; unsigned int
0x180006046  mov     rsi, rdx
0x180006049  mov     [rsp+98h+var_78], r12; unsigned __int64
0x18000604e  mov     rbx, rcx
0x180006051  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180006056  test    al, al
0x180006058  jz      short loc_180006061
0x18000605a  mov     al, 1
0x18000605c  jmp     loc_1800061A2
0x180006061  lea     rdx, [r12+20h]
0x180006066  add     rdx, r15; unsigned __int64
0x180006069  lea     r14, [rbx+18h]
0x18000606d  cmp     qword ptr [r14], 0
0x180006071  jnz     loc_18000617A
0x180006077  xorps   xmm0, xmm0
0x18000607a  lea     rcx, [rsp+98h+var_68]; this
0x18000607f  xorps   xmm1, xmm1
0x180006082  add     rdx, 0Ah; unsigned __int64
0x180006086  movdqu  [rsp+98h+var_68], xmm0
0x18000608c  movdqu  [rsp+98h+var_58], xmm1
0x180006092  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180006097  test    al, al
0x180006099  jz      loc_18000615A
0x18000609f  mov     rdi, qword ptr [rsp+98h+var_58]
0x1800060a4  mov     rsi, qword ptr [rsp+98h+var_68]
0x1800060a9  sub     rdi, rsi
0x1800060ac  cmp     rdi, 0Ah
0x1800060b0  jb      loc_1800061B3
0x1800060b6  mov     rbp, [rbx+30h]
0x1800060ba  mov     qword ptr [rbx+30h], 0
0x1800060c2  test    rbp, rbp
0x1800060c5  jz      short loc_1800060DB
0x1800060c7  call    cs:__imp_GetProcessHeap
0x1800060cd  mov     r8, rbp; lpMem
0x1800060d0  xor     edx, edx; dwFlags
0x1800060d2  mov     rcx, rax; hHeap
0x1800060d5  call    cs:__imp_HeapFree
0x1800060db  mov     [r14], rsi
0x1800060de  lea     rax, [rdi+rsi]
0x1800060e2  mov     [rbx+28h], rax
0x1800060e6  xor     edi, edi
0x1800060e8  xor     eax, eax
0x1800060ea  mov     byte ptr [rbx+39h], 0
0x1800060ee  mov     [rsi], ax
0x1800060f1  movzx   eax, word ptr [rbx]
0x1800060f4  mov     [rsi+2], ax
0x1800060f8  movzx   eax, word ptr [rbx+2]
0x1800060fc  mov     [rsi+4], ax
0x180006100  mov     al, [rbx+4]
0x180006103  mov     [rsi+8], al
0x180006106  movzx   eax, word ptr [rbx+6]
0x18000610a  mov     [rsi+6], ax
0x18000610e  mov     al, [rbx+8]
0x180006111  mov     [rsi+9], al
0x180006114  mov     rax, [r14]
0x180006117  add     rax, 0Ah
0x18000611b  mov     [rbx+20h], rax
0x18000611f  mov     rsi, [rbx+30h]
0x180006123  mov     rax, qword ptr [rsp+98h+var_58+8]
0x180006128  mov     [rbx+30h], rax
0x18000612c  test    rsi, rsi
0x18000612f  jz      short loc_180006145
0x180006131  call    cs:__imp_GetProcessHeap
0x180006137  mov     r8, rsi; lpMem
0x18000613a  xor     edx, edx; dwFlags
0x18000613c  mov     rcx, rax; hHeap
0x18000613f  call    cs:__imp_HeapFree
0x180006145  mov     rsi, [rsp+98h+Buf1]
0x18000614d  mov     ebp, [rsp+98h+arg_28]
0x180006154  mov     byte ptr [rbx+3Ah], 1
0x180006158  jmp     short loc_18000615F
0x18000615a  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x18000615f  test    rdi, rdi
0x180006162  jz      short loc_180006188
0x180006164  call    cs:__imp_GetProcessHeap
0x18000616a  mov     r8, rdi; lpMem
0x18000616d  xor     edx, edx; dwFlags
0x18000616f  mov     rcx, rax; hHeap
0x180006172  call    cs:__imp_HeapFree
0x180006178  jmp     short loc_180006188
0x18000617a  cmp     byte ptr [rbx+3Ah], 0
0x18000617e  jz      short loc_180006188
0x180006180  mov     rcx, r14; this
0x180006183  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180006188  mov     [rsp+98h+var_70], ebp; unsigned int
0x18000618c  mov     r9, r13; void *
0x18000618f  mov     r8, r15; Size
0x180006192  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180006197  mov     rdx, rsi; Buf1
0x18000619a  mov     rcx, rbx; this
0x18000619d  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1800061a2  add     rsp, 58h
0x1800061a6  pop     r15
0x1800061a8  pop     r14
0x1800061aa  pop     r13
0x1800061ac  pop     r12
0x1800061ae  pop     rdi
0x1800061af  pop     rsi
0x1800061b0  pop     rbp
0x1800061b1  pop     rbx
0x1800061b2  retn
0x1800061b3  mov     rcx, [rsp+98h]; this
0x1800061bb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
