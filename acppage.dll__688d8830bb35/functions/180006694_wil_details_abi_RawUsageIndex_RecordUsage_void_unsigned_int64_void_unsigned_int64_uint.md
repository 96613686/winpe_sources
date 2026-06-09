# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180006694`
- end: `0x18000683d`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180003790`
- `0x180006594`
- `0x1800065c8`

## callees

- `0x180006694`
- `0x180006844`
- `0x1800082f0`
- `0x18000835c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180006751`
- `KERNEL32!HeapFree` at `0x1800067bb`
- `KERNEL32!HeapFree` at `0x1800067ee`
- `KERNEL32!HeapFree` at `0x180006751`
- `KERNEL32!HeapFree` at `0x1800067bb`
- `KERNEL32!HeapFree` at `0x1800067ee`
- `KERNEL32!GetProcessHeap` at `0x180006743`
- `KERNEL32!GetProcessHeap` at `0x1800067ad`
- `KERNEL32!GetProcessHeap` at `0x1800067e0`
- `KERNEL32!GetProcessHeap` at `0x180006743`
- `KERNEL32!GetProcessHeap` at `0x1800067ad`
- `KERNEL32!GetProcessHeap` at `0x1800067e0`

## pseudocode

```c
char __fastcall wil::details_abi::RawUsageIndex::RecordUsage(
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
0x180006694  mov     [rsp+Buf1], rdx
0x180006699  push    rbx
0x18000669a  push    rbp
0x18000669b  push    rsi
0x18000669c  push    rdi
0x18000669d  push    r12
0x18000669f  push    r13
0x1800066a1  push    r14
0x1800066a3  push    r15
0x1800066a5  sub     rsp, 58h
0x1800066a9  mov     ebp, [rsp+98h+arg_28]
0x1800066b0  mov     r13, r9
0x1800066b3  mov     r12, [rsp+98h+arg_20]
0x1800066bb  mov     r15, r8
0x1800066be  mov     [rsp+98h+var_70], ebp; unsigned int
0x1800066c2  mov     rsi, rdx
0x1800066c5  mov     [rsp+98h+var_78], r12; unsigned __int64
0x1800066ca  mov     rbx, rcx
0x1800066cd  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1800066d2  test    al, al
0x1800066d4  jz      short loc_1800066DD
0x1800066d6  mov     al, 1
0x1800066d8  jmp     loc_18000681E
0x1800066dd  lea     rdx, [r12+20h]
0x1800066e2  add     rdx, r15; unsigned __int64
0x1800066e5  lea     r14, [rbx+18h]
0x1800066e9  cmp     qword ptr [r14], 0
0x1800066ed  jnz     loc_1800067F6
0x1800066f3  xorps   xmm0, xmm0
0x1800066f6  lea     rcx, [rsp+98h+var_68]; this
0x1800066fb  xorps   xmm1, xmm1
0x1800066fe  add     rdx, 0Ah; unsigned __int64
0x180006702  movdqu  [rsp+98h+var_68], xmm0
0x180006708  movdqu  [rsp+98h+var_58], xmm1
0x18000670e  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180006713  test    al, al
0x180006715  jz      loc_1800067D6
0x18000671b  mov     rdi, qword ptr [rsp+98h+var_58]
0x180006720  mov     rsi, qword ptr [rsp+98h+var_68]
0x180006725  sub     rdi, rsi
0x180006728  cmp     rdi, 0Ah
0x18000672c  jb      loc_18000682F
0x180006732  mov     rbp, [rbx+30h]
0x180006736  mov     qword ptr [rbx+30h], 0
0x18000673e  test    rbp, rbp
0x180006741  jz      short loc_180006757
0x180006743  call    cs:__imp_GetProcessHeap
0x180006749  mov     r8, rbp; lpMem
0x18000674c  xor     edx, edx; dwFlags
0x18000674e  mov     rcx, rax; hHeap
0x180006751  call    cs:__imp_HeapFree
0x180006757  mov     [r14], rsi
0x18000675a  lea     rax, [rdi+rsi]
0x18000675e  mov     [rbx+28h], rax
0x180006762  xor     edi, edi
0x180006764  xor     eax, eax
0x180006766  mov     byte ptr [rbx+39h], 0
0x18000676a  mov     [rsi], ax
0x18000676d  movzx   eax, word ptr [rbx]
0x180006770  mov     [rsi+2], ax
0x180006774  movzx   eax, word ptr [rbx+2]
0x180006778  mov     [rsi+4], ax
0x18000677c  mov     al, [rbx+4]
0x18000677f  mov     [rsi+8], al
0x180006782  movzx   eax, word ptr [rbx+6]
0x180006786  mov     [rsi+6], ax
0x18000678a  mov     al, [rbx+8]
0x18000678d  mov     [rsi+9], al
0x180006790  mov     rax, [r14]
0x180006793  add     rax, 0Ah
0x180006797  mov     [rbx+20h], rax
0x18000679b  mov     rsi, [rbx+30h]
0x18000679f  mov     rax, qword ptr [rsp+98h+var_58+8]
0x1800067a4  mov     [rbx+30h], rax
0x1800067a8  test    rsi, rsi
0x1800067ab  jz      short loc_1800067C1
0x1800067ad  call    cs:__imp_GetProcessHeap
0x1800067b3  mov     r8, rsi; lpMem
0x1800067b6  xor     edx, edx; dwFlags
0x1800067b8  mov     rcx, rax; hHeap
0x1800067bb  call    cs:__imp_HeapFree
0x1800067c1  mov     rsi, [rsp+98h+Buf1]
0x1800067c9  mov     ebp, [rsp+98h+arg_28]
0x1800067d0  mov     byte ptr [rbx+3Ah], 1
0x1800067d4  jmp     short loc_1800067DB
0x1800067d6  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x1800067db  test    rdi, rdi
0x1800067de  jz      short loc_180006804
0x1800067e0  call    cs:__imp_GetProcessHeap
0x1800067e6  mov     r8, rdi; lpMem
0x1800067e9  xor     edx, edx; dwFlags
0x1800067eb  mov     rcx, rax; hHeap
0x1800067ee  call    cs:__imp_HeapFree
0x1800067f4  jmp     short loc_180006804
0x1800067f6  cmp     byte ptr [rbx+3Ah], 0
0x1800067fa  jz      short loc_180006804
0x1800067fc  mov     rcx, r14; this
0x1800067ff  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180006804  mov     [rsp+98h+var_70], ebp; unsigned int
0x180006808  mov     r9, r13; void *
0x18000680b  mov     r8, r15; Size
0x18000680e  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180006813  mov     rdx, rsi; Buf1
0x180006816  mov     rcx, rbx; this
0x180006819  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000681e  add     rsp, 58h
0x180006822  pop     r15
0x180006824  pop     r14
0x180006826  pop     r13
0x180006828  pop     r12
0x18000682a  pop     rdi
0x18000682b  pop     rsi
0x18000682c  pop     rbp
0x18000682d  pop     rbx
0x18000682e  retn
0x18000682f  mov     rcx, [rsp+98h]; this
0x180006837  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
