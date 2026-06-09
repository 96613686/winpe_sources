# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18000d068`
- end: `0x18000d211`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180006030`
- `0x18000cf64`
- `0x18000cf98`

## callees

- `0x18000d068`
- `0x18000d218`
- `0x1800113b8`
- `0x180011eec`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000d117`
- `KERNEL32!GetProcessHeap` at `0x18000d181`
- `KERNEL32!GetProcessHeap` at `0x18000d1b4`
- `KERNEL32!GetProcessHeap` at `0x18000d117`
- `KERNEL32!GetProcessHeap` at `0x18000d181`
- `KERNEL32!GetProcessHeap` at `0x18000d1b4`
- `KERNEL32!HeapFree` at `0x18000d125`
- `KERNEL32!HeapFree` at `0x18000d18f`
- `KERNEL32!HeapFree` at `0x18000d1c2`
- `KERNEL32!HeapFree` at `0x18000d125`
- `KERNEL32!HeapFree` at `0x18000d18f`
- `KERNEL32!HeapFree` at `0x18000d1c2`

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
0x18000d068  mov     [rsp+Buf1], rdx
0x18000d06d  push    rbx
0x18000d06e  push    rbp
0x18000d06f  push    rsi
0x18000d070  push    rdi
0x18000d071  push    r12
0x18000d073  push    r13
0x18000d075  push    r14
0x18000d077  push    r15
0x18000d079  sub     rsp, 58h
0x18000d07d  mov     ebp, [rsp+98h+arg_28]
0x18000d084  mov     r13, r9
0x18000d087  mov     r12, [rsp+98h+arg_20]
0x18000d08f  mov     r15, r8
0x18000d092  mov     [rsp+98h+var_70], ebp; unsigned int
0x18000d096  mov     rsi, rdx
0x18000d099  mov     [rsp+98h+var_78], r12; unsigned __int64
0x18000d09e  mov     rbx, rcx
0x18000d0a1  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000d0a6  test    al, al
0x18000d0a8  jz      short loc_18000D0B1
0x18000d0aa  mov     al, 1
0x18000d0ac  jmp     loc_18000D1F2
0x18000d0b1  lea     rdx, [r12+20h]
0x18000d0b6  add     rdx, r15; unsigned __int64
0x18000d0b9  lea     r14, [rbx+18h]
0x18000d0bd  cmp     qword ptr [r14], 0
0x18000d0c1  jnz     loc_18000D1CA
0x18000d0c7  xorps   xmm0, xmm0
0x18000d0ca  lea     rcx, [rsp+98h+var_68]; this
0x18000d0cf  xorps   xmm1, xmm1
0x18000d0d2  add     rdx, 0Ah; unsigned __int64
0x18000d0d6  movdqu  [rsp+98h+var_68], xmm0
0x18000d0dc  movdqu  [rsp+98h+var_58], xmm1
0x18000d0e2  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000d0e7  test    al, al
0x18000d0e9  jz      loc_18000D1AA
0x18000d0ef  mov     rdi, qword ptr [rsp+98h+var_58]
0x18000d0f4  mov     rsi, qword ptr [rsp+98h+var_68]
0x18000d0f9  sub     rdi, rsi
0x18000d0fc  cmp     rdi, 0Ah
0x18000d100  jb      loc_18000D203
0x18000d106  mov     rbp, [rbx+30h]
0x18000d10a  mov     qword ptr [rbx+30h], 0
0x18000d112  test    rbp, rbp
0x18000d115  jz      short loc_18000D12B
0x18000d117  call    cs:__imp_GetProcessHeap
0x18000d11d  mov     r8, rbp; lpMem
0x18000d120  xor     edx, edx; dwFlags
0x18000d122  mov     rcx, rax; hHeap
0x18000d125  call    cs:__imp_HeapFree
0x18000d12b  mov     [r14], rsi
0x18000d12e  lea     rax, [rdi+rsi]
0x18000d132  mov     [rbx+28h], rax
0x18000d136  xor     edi, edi
0x18000d138  xor     eax, eax
0x18000d13a  mov     byte ptr [rbx+39h], 0
0x18000d13e  mov     [rsi], ax
0x18000d141  movzx   eax, word ptr [rbx]
0x18000d144  mov     [rsi+2], ax
0x18000d148  movzx   eax, word ptr [rbx+2]
0x18000d14c  mov     [rsi+4], ax
0x18000d150  mov     al, [rbx+4]
0x18000d153  mov     [rsi+8], al
0x18000d156  movzx   eax, word ptr [rbx+6]
0x18000d15a  mov     [rsi+6], ax
0x18000d15e  mov     al, [rbx+8]
0x18000d161  mov     [rsi+9], al
0x18000d164  mov     rax, [r14]
0x18000d167  add     rax, 0Ah
0x18000d16b  mov     [rbx+20h], rax
0x18000d16f  mov     rsi, [rbx+30h]
0x18000d173  mov     rax, qword ptr [rsp+98h+var_58+8]
0x18000d178  mov     [rbx+30h], rax
0x18000d17c  test    rsi, rsi
0x18000d17f  jz      short loc_18000D195
0x18000d181  call    cs:__imp_GetProcessHeap
0x18000d187  mov     r8, rsi; lpMem
0x18000d18a  xor     edx, edx; dwFlags
0x18000d18c  mov     rcx, rax; hHeap
0x18000d18f  call    cs:__imp_HeapFree
0x18000d195  mov     rsi, [rsp+98h+Buf1]
0x18000d19d  mov     ebp, [rsp+98h+arg_28]
0x18000d1a4  mov     byte ptr [rbx+3Ah], 1
0x18000d1a8  jmp     short loc_18000D1AF
0x18000d1aa  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x18000d1af  test    rdi, rdi
0x18000d1b2  jz      short loc_18000D1D8
0x18000d1b4  call    cs:__imp_GetProcessHeap
0x18000d1ba  mov     r8, rdi; lpMem
0x18000d1bd  xor     edx, edx; dwFlags
0x18000d1bf  mov     rcx, rax; hHeap
0x18000d1c2  call    cs:__imp_HeapFree
0x18000d1c8  jmp     short loc_18000D1D8
0x18000d1ca  cmp     byte ptr [rbx+3Ah], 0
0x18000d1ce  jz      short loc_18000D1D8
0x18000d1d0  mov     rcx, r14; this
0x18000d1d3  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000d1d8  mov     [rsp+98h+var_70], ebp; unsigned int
0x18000d1dc  mov     r9, r13; void *
0x18000d1df  mov     r8, r15; Size
0x18000d1e2  mov     [rsp+98h+var_78], r12; unsigned __int64
0x18000d1e7  mov     rdx, rsi; Buf1
0x18000d1ea  mov     rcx, rbx; this
0x18000d1ed  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000d1f2  add     rsp, 58h
0x18000d1f6  pop     r15
0x18000d1f8  pop     r14
0x18000d1fa  pop     r13
0x18000d1fc  pop     r12
0x18000d1fe  pop     rdi
0x18000d1ff  pop     rsi
0x18000d200  pop     rbp
0x18000d201  pop     rbx
0x18000d202  retn
0x18000d203  mov     rcx, [rsp+98h]; this
0x18000d20b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
