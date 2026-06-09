# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x1800142ac`
- end: `0x18001447a`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `462`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180011570`
- `0x180014198`
- `0x1800141d0`

## callees

- `0x1800142ac`
- `0x180014480`
- `0x180016660`
- `0x18001685c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001436f`
- `KERNEL32!HeapFree` at `0x1800143e5`
- `KERNEL32!HeapFree` at `0x180014424`
- `KERNEL32!HeapFree` at `0x18001436f`
- `KERNEL32!HeapFree` at `0x1800143e5`
- `KERNEL32!HeapFree` at `0x180014424`
- `KERNEL32!GetProcessHeap` at `0x18001435b`
- `KERNEL32!GetProcessHeap` at `0x1800143d1`
- `KERNEL32!GetProcessHeap` at `0x180014410`
- `KERNEL32!GetProcessHeap` at `0x18001435b`
- `KERNEL32!GetProcessHeap` at `0x1800143d1`
- `KERNEL32!GetProcessHeap` at `0x180014410`

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
0x1800142ac  mov     [rsp+Buf1], rdx
0x1800142b1  push    rbx
0x1800142b2  push    rbp
0x1800142b3  push    rsi
0x1800142b4  push    rdi
0x1800142b5  push    r12
0x1800142b7  push    r13
0x1800142b9  push    r14
0x1800142bb  push    r15
0x1800142bd  sub     rsp, 58h
0x1800142c1  mov     ebp, [rsp+98h+arg_28]
0x1800142c8  mov     r13, r9
0x1800142cb  mov     r12, [rsp+98h+arg_20]
0x1800142d3  mov     r15, r8
0x1800142d6  mov     [rsp+98h+var_70], ebp; unsigned int
0x1800142da  mov     rsi, rdx
0x1800142dd  mov     [rsp+98h+var_78], r12; unsigned __int64
0x1800142e2  mov     rbx, rcx
0x1800142e5  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1800142ea  test    al, al
0x1800142ec  jz      short loc_1800142F5
0x1800142ee  mov     al, 1
0x1800142f0  jmp     loc_18001445A
0x1800142f5  lea     rdx, [r12+20h]
0x1800142fa  add     rdx, r15; unsigned __int64
0x1800142fd  lea     r14, [rbx+18h]
0x180014301  cmp     qword ptr [r14], 0
0x180014305  jnz     loc_180014432
0x18001430b  xorps   xmm0, xmm0
0x18001430e  lea     rcx, [rsp+98h+var_68]; this
0x180014313  xorps   xmm1, xmm1
0x180014316  add     rdx, 0Ah; unsigned __int64
0x18001431a  movdqu  [rsp+98h+var_68], xmm0
0x180014320  movdqu  [rsp+98h+var_58], xmm1
0x180014326  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18001432b  test    al, al
0x18001432d  jz      loc_180014406
0x180014333  mov     rdi, qword ptr [rsp+98h+var_58]
0x180014338  mov     rsi, qword ptr [rsp+98h+var_68]
0x18001433d  sub     rdi, rsi
0x180014340  cmp     rdi, 0Ah
0x180014344  jb      loc_18001446C
0x18001434a  mov     rbp, [rbx+30h]
0x18001434e  mov     qword ptr [rbx+30h], 0
0x180014356  test    rbp, rbp
0x180014359  jz      short loc_18001437B
0x18001435b  call    cs:__imp_GetProcessHeap
0x180014362  nop     dword ptr [rax+rax+00h]
0x180014367  mov     r8, rbp; lpMem
0x18001436a  xor     edx, edx; dwFlags
0x18001436c  mov     rcx, rax; hHeap
0x18001436f  call    cs:__imp_HeapFree
0x180014376  nop     dword ptr [rax+rax+00h]
0x18001437b  mov     [r14], rsi
0x18001437e  lea     rax, [rdi+rsi]
0x180014382  mov     [rbx+28h], rax
0x180014386  xor     edi, edi
0x180014388  xor     eax, eax
0x18001438a  mov     byte ptr [rbx+39h], 0
0x18001438e  mov     [rsi], ax
0x180014391  movzx   eax, word ptr [rbx]
0x180014394  mov     [rsi+2], ax
0x180014398  movzx   eax, word ptr [rbx+2]
0x18001439c  mov     [rsi+4], ax
0x1800143a0  mov     al, [rbx+4]
0x1800143a3  mov     [rsi+8], al
0x1800143a6  movzx   eax, word ptr [rbx+6]
0x1800143aa  mov     [rsi+6], ax
0x1800143ae  mov     al, [rbx+8]
0x1800143b1  mov     [rsi+9], al
0x1800143b4  mov     rax, [r14]
0x1800143b7  add     rax, 0Ah
0x1800143bb  mov     [rbx+20h], rax
0x1800143bf  mov     rsi, [rbx+30h]
0x1800143c3  mov     rax, qword ptr [rsp+98h+var_58+8]
0x1800143c8  mov     [rbx+30h], rax
0x1800143cc  test    rsi, rsi
0x1800143cf  jz      short loc_1800143F1
0x1800143d1  call    cs:__imp_GetProcessHeap
0x1800143d8  nop     dword ptr [rax+rax+00h]
0x1800143dd  mov     r8, rsi; lpMem
0x1800143e0  xor     edx, edx; dwFlags
0x1800143e2  mov     rcx, rax; hHeap
0x1800143e5  call    cs:__imp_HeapFree
0x1800143ec  nop     dword ptr [rax+rax+00h]
0x1800143f1  mov     rsi, [rsp+98h+Buf1]
0x1800143f9  mov     ebp, [rsp+98h+arg_28]
0x180014400  mov     byte ptr [rbx+3Ah], 1
0x180014404  jmp     short loc_18001440B
0x180014406  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x18001440b  test    rdi, rdi
0x18001440e  jz      short loc_180014440
0x180014410  call    cs:__imp_GetProcessHeap
0x180014417  nop     dword ptr [rax+rax+00h]
0x18001441c  mov     r8, rdi; lpMem
0x18001441f  xor     edx, edx; dwFlags
0x180014421  mov     rcx, rax; hHeap
0x180014424  call    cs:__imp_HeapFree
0x18001442b  nop     dword ptr [rax+rax+00h]
0x180014430  jmp     short loc_180014440
0x180014432  cmp     byte ptr [rbx+3Ah], 0
0x180014436  jz      short loc_180014440
0x180014438  mov     rcx, r14; this
0x18001443b  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180014440  mov     [rsp+98h+var_70], ebp; unsigned int
0x180014444  mov     r9, r13; void *
0x180014447  mov     r8, r15; Size
0x18001444a  mov     [rsp+98h+var_78], r12; unsigned __int64
0x18001444f  mov     rdx, rsi; Buf1
0x180014452  mov     rcx, rbx; this
0x180014455  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18001445a  add     rsp, 58h
0x18001445e  pop     r15
0x180014460  pop     r14
0x180014462  pop     r13
0x180014464  pop     r12
0x180014466  pop     rdi
0x180014467  pop     rsi
0x180014468  pop     rbp
0x180014469  pop     rbx
0x18001446a  retn
0x18001446c  mov     rcx, [rsp+98h]; this
0x180014474  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
