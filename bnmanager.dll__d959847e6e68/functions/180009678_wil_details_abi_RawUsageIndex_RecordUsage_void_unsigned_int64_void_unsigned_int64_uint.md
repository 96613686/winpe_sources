# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180009678`
- end: `0x180009821`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180005900`
- `0x180009574`
- `0x1800095a8`

## callees

- `0x180009678`
- `0x180009828`
- `0x18000bba8`
- `0x18000bd0c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009735`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000979f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800097d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009735`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000979f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800097d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009727`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009791`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800097c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009727`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009791`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800097c4`

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
0x180009678  mov     [rsp+Buf1], rdx
0x18000967d  push    rbx
0x18000967e  push    rbp
0x18000967f  push    rsi
0x180009680  push    rdi
0x180009681  push    r12
0x180009683  push    r13
0x180009685  push    r14
0x180009687  push    r15
0x180009689  sub     rsp, 58h
0x18000968d  mov     ebp, [rsp+98h+arg_28]
0x180009694  mov     r13, r9
0x180009697  mov     r12, [rsp+98h+arg_20]
0x18000969f  mov     r15, r8
0x1800096a2  mov     [rsp+98h+var_70], ebp; unsigned int
0x1800096a6  mov     rsi, rdx
0x1800096a9  mov     [rsp+98h+var_78], r12; unsigned __int64
0x1800096ae  mov     rbx, rcx
0x1800096b1  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1800096b6  test    al, al
0x1800096b8  jz      short loc_1800096C1
0x1800096ba  mov     al, 1
0x1800096bc  jmp     loc_180009802
0x1800096c1  lea     rdx, [r12+20h]
0x1800096c6  add     rdx, r15; unsigned __int64
0x1800096c9  lea     r14, [rbx+18h]
0x1800096cd  cmp     qword ptr [r14], 0
0x1800096d1  jnz     loc_1800097DA
0x1800096d7  xorps   xmm0, xmm0
0x1800096da  lea     rcx, [rsp+98h+var_68]; this
0x1800096df  xorps   xmm1, xmm1
0x1800096e2  add     rdx, 0Ah; unsigned __int64
0x1800096e6  movdqu  [rsp+98h+var_68], xmm0
0x1800096ec  movdqu  [rsp+98h+var_58], xmm1
0x1800096f2  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800096f7  test    al, al
0x1800096f9  jz      loc_1800097BA
0x1800096ff  mov     rdi, qword ptr [rsp+98h+var_58]
0x180009704  mov     rsi, qword ptr [rsp+98h+var_68]
0x180009709  sub     rdi, rsi
0x18000970c  cmp     rdi, 0Ah
0x180009710  jb      loc_180009813
0x180009716  mov     rbp, [rbx+30h]
0x18000971a  mov     qword ptr [rbx+30h], 0
0x180009722  test    rbp, rbp
0x180009725  jz      short loc_18000973B
0x180009727  call    cs:__imp_GetProcessHeap
0x18000972d  mov     r8, rbp; lpMem
0x180009730  xor     edx, edx; dwFlags
0x180009732  mov     rcx, rax; hHeap
0x180009735  call    cs:__imp_HeapFree
0x18000973b  mov     [r14], rsi
0x18000973e  lea     rax, [rdi+rsi]
0x180009742  mov     [rbx+28h], rax
0x180009746  xor     edi, edi
0x180009748  xor     eax, eax
0x18000974a  mov     byte ptr [rbx+39h], 0
0x18000974e  mov     [rsi], ax
0x180009751  movzx   eax, word ptr [rbx]
0x180009754  mov     [rsi+2], ax
0x180009758  movzx   eax, word ptr [rbx+2]
0x18000975c  mov     [rsi+4], ax
0x180009760  mov     al, [rbx+4]
0x180009763  mov     [rsi+8], al
0x180009766  movzx   eax, word ptr [rbx+6]
0x18000976a  mov     [rsi+6], ax
0x18000976e  mov     al, [rbx+8]
0x180009771  mov     [rsi+9], al
0x180009774  mov     rax, [r14]
0x180009777  add     rax, 0Ah
0x18000977b  mov     [rbx+20h], rax
0x18000977f  mov     rsi, [rbx+30h]
0x180009783  mov     rax, qword ptr [rsp+98h+var_58+8]
0x180009788  mov     [rbx+30h], rax
0x18000978c  test    rsi, rsi
0x18000978f  jz      short loc_1800097A5
0x180009791  call    cs:__imp_GetProcessHeap
0x180009797  mov     r8, rsi; lpMem
0x18000979a  xor     edx, edx; dwFlags
0x18000979c  mov     rcx, rax; hHeap
0x18000979f  call    cs:__imp_HeapFree
0x1800097a5  mov     rsi, [rsp+98h+Buf1]
0x1800097ad  mov     ebp, [rsp+98h+arg_28]
0x1800097b4  mov     byte ptr [rbx+3Ah], 1
0x1800097b8  jmp     short loc_1800097BF
0x1800097ba  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x1800097bf  test    rdi, rdi
0x1800097c2  jz      short loc_1800097E8
0x1800097c4  call    cs:__imp_GetProcessHeap
0x1800097ca  mov     r8, rdi; lpMem
0x1800097cd  xor     edx, edx; dwFlags
0x1800097cf  mov     rcx, rax; hHeap
0x1800097d2  call    cs:__imp_HeapFree
0x1800097d8  jmp     short loc_1800097E8
0x1800097da  cmp     byte ptr [rbx+3Ah], 0
0x1800097de  jz      short loc_1800097E8
0x1800097e0  mov     rcx, r14; this
0x1800097e3  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800097e8  mov     [rsp+98h+var_70], ebp; unsigned int
0x1800097ec  mov     r9, r13; void *
0x1800097ef  mov     r8, r15; Size
0x1800097f2  mov     [rsp+98h+var_78], r12; unsigned __int64
0x1800097f7  mov     rdx, rsi; Buf1
0x1800097fa  mov     rcx, rbx; this
0x1800097fd  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180009802  add     rsp, 58h
0x180009806  pop     r15
0x180009808  pop     r14
0x18000980a  pop     r13
0x18000980c  pop     r12
0x18000980e  pop     rdi
0x18000980f  pop     rsi
0x180009810  pop     rbp
0x180009811  pop     rbx
0x180009812  retn
0x180009813  mov     rcx, [rsp+98h]; this
0x18000981b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
