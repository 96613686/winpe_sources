# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18000920c`
- end: `0x1800093b5`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180007ae0`
- `0x180009108`
- `0x18000913c`

## callees

- `0x18000920c`
- `0x1800093bc`
- `0x18000aa14`
- `0x18000aa84`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800092bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009325`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009358`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800092bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009325`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009358`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800092c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009333`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009366`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800092c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009333`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009366`

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
0x18000920c  mov     [rsp+Buf1], rdx
0x180009211  push    rbx
0x180009212  push    rbp
0x180009213  push    rsi
0x180009214  push    rdi
0x180009215  push    r12
0x180009217  push    r13
0x180009219  push    r14
0x18000921b  push    r15
0x18000921d  sub     rsp, 58h
0x180009221  mov     ebp, [rsp+98h+arg_28]
0x180009228  mov     r13, r9
0x18000922b  mov     r12, [rsp+98h+arg_20]
0x180009233  mov     r15, r8
0x180009236  mov     [rsp+98h+var_70], ebp; unsigned int
0x18000923a  mov     rsi, rdx
0x18000923d  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180009242  mov     rbx, rcx
0x180009245  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000924a  test    al, al
0x18000924c  jz      short loc_180009255
0x18000924e  mov     al, 1
0x180009250  jmp     loc_180009396
0x180009255  lea     rdx, [r12+20h]
0x18000925a  add     rdx, r15; unsigned __int64
0x18000925d  lea     r14, [rbx+18h]
0x180009261  cmp     qword ptr [r14], 0
0x180009265  jnz     loc_18000936E
0x18000926b  xorps   xmm0, xmm0
0x18000926e  lea     rcx, [rsp+98h+var_68]; this
0x180009273  xorps   xmm1, xmm1
0x180009276  add     rdx, 0Ah; unsigned __int64
0x18000927a  movdqu  [rsp+98h+var_68], xmm0
0x180009280  movdqu  [rsp+98h+var_58], xmm1
0x180009286  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000928b  test    al, al
0x18000928d  jz      loc_18000934E
0x180009293  mov     rdi, qword ptr [rsp+98h+var_58]
0x180009298  mov     rsi, qword ptr [rsp+98h+var_68]
0x18000929d  sub     rdi, rsi
0x1800092a0  cmp     rdi, 0Ah
0x1800092a4  jb      loc_1800093A7
0x1800092aa  mov     rbp, [rbx+30h]
0x1800092ae  mov     qword ptr [rbx+30h], 0
0x1800092b6  test    rbp, rbp
0x1800092b9  jz      short loc_1800092CF
0x1800092bb  call    cs:__imp_GetProcessHeap
0x1800092c1  mov     r8, rbp; lpMem
0x1800092c4  xor     edx, edx; dwFlags
0x1800092c6  mov     rcx, rax; hHeap
0x1800092c9  call    cs:__imp_HeapFree
0x1800092cf  mov     [r14], rsi
0x1800092d2  lea     rax, [rdi+rsi]
0x1800092d6  mov     [rbx+28h], rax
0x1800092da  xor     edi, edi
0x1800092dc  xor     eax, eax
0x1800092de  mov     byte ptr [rbx+39h], 0
0x1800092e2  mov     [rsi], ax
0x1800092e5  movzx   eax, word ptr [rbx]
0x1800092e8  mov     [rsi+2], ax
0x1800092ec  movzx   eax, word ptr [rbx+2]
0x1800092f0  mov     [rsi+4], ax
0x1800092f4  mov     al, [rbx+4]
0x1800092f7  mov     [rsi+8], al
0x1800092fa  movzx   eax, word ptr [rbx+6]
0x1800092fe  mov     [rsi+6], ax
0x180009302  mov     al, [rbx+8]
0x180009305  mov     [rsi+9], al
0x180009308  mov     rax, [r14]
0x18000930b  add     rax, 0Ah
0x18000930f  mov     [rbx+20h], rax
0x180009313  mov     rsi, [rbx+30h]
0x180009317  mov     rax, qword ptr [rsp+98h+var_58+8]
0x18000931c  mov     [rbx+30h], rax
0x180009320  test    rsi, rsi
0x180009323  jz      short loc_180009339
0x180009325  call    cs:__imp_GetProcessHeap
0x18000932b  mov     r8, rsi; lpMem
0x18000932e  xor     edx, edx; dwFlags
0x180009330  mov     rcx, rax; hHeap
0x180009333  call    cs:__imp_HeapFree
0x180009339  mov     rsi, [rsp+98h+Buf1]
0x180009341  mov     ebp, [rsp+98h+arg_28]
0x180009348  mov     byte ptr [rbx+3Ah], 1
0x18000934c  jmp     short loc_180009353
0x18000934e  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x180009353  test    rdi, rdi
0x180009356  jz      short loc_18000937C
0x180009358  call    cs:__imp_GetProcessHeap
0x18000935e  mov     r8, rdi; lpMem
0x180009361  xor     edx, edx; dwFlags
0x180009363  mov     rcx, rax; hHeap
0x180009366  call    cs:__imp_HeapFree
0x18000936c  jmp     short loc_18000937C
0x18000936e  cmp     byte ptr [rbx+3Ah], 0
0x180009372  jz      short loc_18000937C
0x180009374  mov     rcx, r14; this
0x180009377  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000937c  mov     [rsp+98h+var_70], ebp; unsigned int
0x180009380  mov     r9, r13; void *
0x180009383  mov     r8, r15; Size
0x180009386  mov     [rsp+98h+var_78], r12; unsigned __int64
0x18000938b  mov     rdx, rsi; Buf1
0x18000938e  mov     rcx, rbx; this
0x180009391  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180009396  add     rsp, 58h
0x18000939a  pop     r15
0x18000939c  pop     r14
0x18000939e  pop     r13
0x1800093a0  pop     r12
0x1800093a2  pop     rdi
0x1800093a3  pop     rsi
0x1800093a4  pop     rbp
0x1800093a5  pop     rbx
0x1800093a6  retn
0x1800093a7  mov     rcx, [rsp+98h]; this
0x1800093af  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
