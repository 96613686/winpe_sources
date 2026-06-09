# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x14000b350`
- end: `0x14000b4f9`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140008bc0`
- `0x14000b250`
- `0x14000b284`

## callees

- `0x140006524`
- `0x14000b350`
- `0x14000b500`
- `0x14000cdd8`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000b40d`
- `KERNEL32!HeapFree` at `0x14000b477`
- `KERNEL32!HeapFree` at `0x14000b4aa`
- `KERNEL32!HeapFree` at `0x14000b40d`
- `KERNEL32!HeapFree` at `0x14000b477`
- `KERNEL32!HeapFree` at `0x14000b4aa`
- `KERNEL32!GetProcessHeap` at `0x14000b3ff`
- `KERNEL32!GetProcessHeap` at `0x14000b469`
- `KERNEL32!GetProcessHeap` at `0x14000b49c`
- `KERNEL32!GetProcessHeap` at `0x14000b3ff`
- `KERNEL32!GetProcessHeap` at `0x14000b469`
- `KERNEL32!GetProcessHeap` at `0x14000b49c`

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
0x14000b350  mov     [rsp+Buf1], rdx
0x14000b355  push    rbx
0x14000b356  push    rbp
0x14000b357  push    rsi
0x14000b358  push    rdi
0x14000b359  push    r12
0x14000b35b  push    r13
0x14000b35d  push    r14
0x14000b35f  push    r15
0x14000b361  sub     rsp, 58h
0x14000b365  mov     ebp, [rsp+98h+arg_28]
0x14000b36c  mov     r13, r9
0x14000b36f  mov     r12, [rsp+98h+arg_20]
0x14000b377  mov     r15, r8
0x14000b37a  mov     [rsp+98h+var_70], ebp; unsigned int
0x14000b37e  mov     rsi, rdx
0x14000b381  mov     [rsp+98h+var_78], r12; unsigned __int64
0x14000b386  mov     rbx, rcx
0x14000b389  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x14000b38e  test    al, al
0x14000b390  jz      short loc_14000B399
0x14000b392  mov     al, 1
0x14000b394  jmp     loc_14000B4DA
0x14000b399  lea     rdx, [r12+20h]
0x14000b39e  add     rdx, r15; unsigned __int64
0x14000b3a1  lea     r14, [rbx+18h]
0x14000b3a5  cmp     qword ptr [r14], 0
0x14000b3a9  jnz     loc_14000B4B2
0x14000b3af  xorps   xmm0, xmm0
0x14000b3b2  lea     rcx, [rsp+98h+var_68]; this
0x14000b3b7  xorps   xmm1, xmm1
0x14000b3ba  add     rdx, 0Ah; unsigned __int64
0x14000b3be  movdqu  [rsp+98h+var_68], xmm0
0x14000b3c4  movdqu  [rsp+98h+var_58], xmm1
0x14000b3ca  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000b3cf  test    al, al
0x14000b3d1  jz      loc_14000B492
0x14000b3d7  mov     rdi, qword ptr [rsp+98h+var_58]
0x14000b3dc  mov     rsi, qword ptr [rsp+98h+var_68]
0x14000b3e1  sub     rdi, rsi
0x14000b3e4  cmp     rdi, 0Ah
0x14000b3e8  jb      loc_14000B4EB
0x14000b3ee  mov     rbp, [rbx+30h]
0x14000b3f2  mov     qword ptr [rbx+30h], 0
0x14000b3fa  test    rbp, rbp
0x14000b3fd  jz      short loc_14000B413
0x14000b3ff  call    cs:__imp_GetProcessHeap
0x14000b405  mov     r8, rbp; lpMem
0x14000b408  xor     edx, edx; dwFlags
0x14000b40a  mov     rcx, rax; hHeap
0x14000b40d  call    cs:__imp_HeapFree
0x14000b413  mov     [r14], rsi
0x14000b416  lea     rax, [rdi+rsi]
0x14000b41a  mov     [rbx+28h], rax
0x14000b41e  xor     edi, edi
0x14000b420  xor     eax, eax
0x14000b422  mov     byte ptr [rbx+39h], 0
0x14000b426  mov     [rsi], ax
0x14000b429  movzx   eax, word ptr [rbx]
0x14000b42c  mov     [rsi+2], ax
0x14000b430  movzx   eax, word ptr [rbx+2]
0x14000b434  mov     [rsi+4], ax
0x14000b438  mov     al, [rbx+4]
0x14000b43b  mov     [rsi+8], al
0x14000b43e  movzx   eax, word ptr [rbx+6]
0x14000b442  mov     [rsi+6], ax
0x14000b446  mov     al, [rbx+8]
0x14000b449  mov     [rsi+9], al
0x14000b44c  mov     rax, [r14]
0x14000b44f  add     rax, 0Ah
0x14000b453  mov     [rbx+20h], rax
0x14000b457  mov     rsi, [rbx+30h]
0x14000b45b  mov     rax, qword ptr [rsp+98h+var_58+8]
0x14000b460  mov     [rbx+30h], rax
0x14000b464  test    rsi, rsi
0x14000b467  jz      short loc_14000B47D
0x14000b469  call    cs:__imp_GetProcessHeap
0x14000b46f  mov     r8, rsi; lpMem
0x14000b472  xor     edx, edx; dwFlags
0x14000b474  mov     rcx, rax; hHeap
0x14000b477  call    cs:__imp_HeapFree
0x14000b47d  mov     rsi, [rsp+98h+Buf1]
0x14000b485  mov     ebp, [rsp+98h+arg_28]
0x14000b48c  mov     byte ptr [rbx+3Ah], 1
0x14000b490  jmp     short loc_14000B497
0x14000b492  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x14000b497  test    rdi, rdi
0x14000b49a  jz      short loc_14000B4C0
0x14000b49c  call    cs:__imp_GetProcessHeap
0x14000b4a2  mov     r8, rdi; lpMem
0x14000b4a5  xor     edx, edx; dwFlags
0x14000b4a7  mov     rcx, rax; hHeap
0x14000b4aa  call    cs:__imp_HeapFree
0x14000b4b0  jmp     short loc_14000B4C0
0x14000b4b2  cmp     byte ptr [rbx+3Ah], 0
0x14000b4b6  jz      short loc_14000B4C0
0x14000b4b8  mov     rcx, r14; this
0x14000b4bb  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000b4c0  mov     [rsp+98h+var_70], ebp; unsigned int
0x14000b4c4  mov     r9, r13; void *
0x14000b4c7  mov     r8, r15; Size
0x14000b4ca  mov     [rsp+98h+var_78], r12; unsigned __int64
0x14000b4cf  mov     rdx, rsi; Buf1
0x14000b4d2  mov     rcx, rbx; this
0x14000b4d5  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x14000b4da  add     rsp, 58h
0x14000b4de  pop     r15
0x14000b4e0  pop     r14
0x14000b4e2  pop     r13
0x14000b4e4  pop     r12
0x14000b4e6  pop     rdi
0x14000b4e7  pop     rsi
0x14000b4e8  pop     rbp
0x14000b4e9  pop     rbx
0x14000b4ea  retn
0x14000b4eb  mov     rcx, [rsp+98h]; this
0x14000b4f3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
