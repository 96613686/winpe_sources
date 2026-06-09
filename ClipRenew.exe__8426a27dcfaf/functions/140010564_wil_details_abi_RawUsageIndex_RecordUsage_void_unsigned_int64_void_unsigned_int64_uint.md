# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x140010564`
- end: `0x14001070d`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140006310`
- `0x140010464`
- `0x140010498`

## callees

- `0x140010564`
- `0x140010714`
- `0x140011d1c`
- `0x140011fcc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010613`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001067d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400106b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010613`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001067d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400106b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010621`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001068b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400106be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010621`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001068b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400106be`

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
0x140010564  mov     [rsp+Buf1], rdx
0x140010569  push    rbx
0x14001056a  push    rbp
0x14001056b  push    rsi
0x14001056c  push    rdi
0x14001056d  push    r12
0x14001056f  push    r13
0x140010571  push    r14
0x140010573  push    r15
0x140010575  sub     rsp, 58h
0x140010579  mov     ebp, [rsp+98h+arg_28]
0x140010580  mov     r13, r9
0x140010583  mov     r12, [rsp+98h+arg_20]
0x14001058b  mov     r15, r8
0x14001058e  mov     [rsp+98h+var_70], ebp; unsigned int
0x140010592  mov     rsi, rdx
0x140010595  mov     [rsp+98h+var_78], r12; unsigned __int64
0x14001059a  mov     rbx, rcx
0x14001059d  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1400105a2  test    al, al
0x1400105a4  jz      short loc_1400105AD
0x1400105a6  mov     al, 1
0x1400105a8  jmp     loc_1400106EE
0x1400105ad  lea     rdx, [r12+20h]
0x1400105b2  add     rdx, r15; unsigned __int64
0x1400105b5  lea     r14, [rbx+18h]
0x1400105b9  cmp     qword ptr [r14], 0
0x1400105bd  jnz     loc_1400106C6
0x1400105c3  xorps   xmm0, xmm0
0x1400105c6  lea     rcx, [rsp+98h+var_68]; this
0x1400105cb  xorps   xmm1, xmm1
0x1400105ce  add     rdx, 0Ah; unsigned __int64
0x1400105d2  movdqu  [rsp+98h+var_68], xmm0
0x1400105d8  movdqu  [rsp+98h+var_58], xmm1
0x1400105de  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1400105e3  test    al, al
0x1400105e5  jz      loc_1400106A6
0x1400105eb  mov     rdi, qword ptr [rsp+98h+var_58]
0x1400105f0  mov     rsi, qword ptr [rsp+98h+var_68]
0x1400105f5  sub     rdi, rsi
0x1400105f8  cmp     rdi, 0Ah
0x1400105fc  jb      loc_1400106FF
0x140010602  mov     rbp, [rbx+30h]
0x140010606  mov     qword ptr [rbx+30h], 0
0x14001060e  test    rbp, rbp
0x140010611  jz      short loc_140010627
0x140010613  call    cs:__imp_GetProcessHeap
0x140010619  mov     r8, rbp; lpMem
0x14001061c  xor     edx, edx; dwFlags
0x14001061e  mov     rcx, rax; hHeap
0x140010621  call    cs:__imp_HeapFree
0x140010627  mov     [r14], rsi
0x14001062a  lea     rax, [rdi+rsi]
0x14001062e  mov     [rbx+28h], rax
0x140010632  xor     edi, edi
0x140010634  xor     eax, eax
0x140010636  mov     byte ptr [rbx+39h], 0
0x14001063a  mov     [rsi], ax
0x14001063d  movzx   eax, word ptr [rbx]
0x140010640  mov     [rsi+2], ax
0x140010644  movzx   eax, word ptr [rbx+2]
0x140010648  mov     [rsi+4], ax
0x14001064c  mov     al, [rbx+4]
0x14001064f  mov     [rsi+8], al
0x140010652  movzx   eax, word ptr [rbx+6]
0x140010656  mov     [rsi+6], ax
0x14001065a  mov     al, [rbx+8]
0x14001065d  mov     [rsi+9], al
0x140010660  mov     rax, [r14]
0x140010663  add     rax, 0Ah
0x140010667  mov     [rbx+20h], rax
0x14001066b  mov     rsi, [rbx+30h]
0x14001066f  mov     rax, qword ptr [rsp+98h+var_58+8]
0x140010674  mov     [rbx+30h], rax
0x140010678  test    rsi, rsi
0x14001067b  jz      short loc_140010691
0x14001067d  call    cs:__imp_GetProcessHeap
0x140010683  mov     r8, rsi; lpMem
0x140010686  xor     edx, edx; dwFlags
0x140010688  mov     rcx, rax; hHeap
0x14001068b  call    cs:__imp_HeapFree
0x140010691  mov     rsi, [rsp+98h+Buf1]
0x140010699  mov     ebp, [rsp+98h+arg_28]
0x1400106a0  mov     byte ptr [rbx+3Ah], 1
0x1400106a4  jmp     short loc_1400106AB
0x1400106a6  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x1400106ab  test    rdi, rdi
0x1400106ae  jz      short loc_1400106D4
0x1400106b0  call    cs:__imp_GetProcessHeap
0x1400106b6  mov     r8, rdi; lpMem
0x1400106b9  xor     edx, edx; dwFlags
0x1400106bb  mov     rcx, rax; hHeap
0x1400106be  call    cs:__imp_HeapFree
0x1400106c4  jmp     short loc_1400106D4
0x1400106c6  cmp     byte ptr [rbx+3Ah], 0
0x1400106ca  jz      short loc_1400106D4
0x1400106cc  mov     rcx, r14; this
0x1400106cf  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1400106d4  mov     [rsp+98h+var_70], ebp; unsigned int
0x1400106d8  mov     r9, r13; void *
0x1400106db  mov     r8, r15; Size
0x1400106de  mov     [rsp+98h+var_78], r12; unsigned __int64
0x1400106e3  mov     rdx, rsi; Buf1
0x1400106e6  mov     rcx, rbx; this
0x1400106e9  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1400106ee  add     rsp, 58h
0x1400106f2  pop     r15
0x1400106f4  pop     r14
0x1400106f6  pop     r13
0x1400106f8  pop     r12
0x1400106fa  pop     rdi
0x1400106fb  pop     rsi
0x1400106fc  pop     rbp
0x1400106fd  pop     rbx
0x1400106fe  retn
0x1400106ff  mov     rcx, [rsp+98h]; this
0x140010707  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
