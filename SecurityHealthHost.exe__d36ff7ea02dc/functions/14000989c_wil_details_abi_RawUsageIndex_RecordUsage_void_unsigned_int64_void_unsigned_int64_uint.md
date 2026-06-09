# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x14000989c`
- end: `0x140009a45`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1400077c0`
- `0x140009798`
- `0x1400097cc`

## callees

- `0x14000989c`
- `0x140009a4c`
- `0x14000ba6c`
- `0x14000bb9c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000994b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400099b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400099e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000994b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400099b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400099e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140009959`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400099c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400099f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140009959`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400099c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400099f6`

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
0x14000989c  mov     [rsp+Buf1], rdx
0x1400098a1  push    rbx
0x1400098a2  push    rbp
0x1400098a3  push    rsi
0x1400098a4  push    rdi
0x1400098a5  push    r12
0x1400098a7  push    r13
0x1400098a9  push    r14
0x1400098ab  push    r15
0x1400098ad  sub     rsp, 58h
0x1400098b1  mov     ebp, [rsp+98h+arg_28]
0x1400098b8  mov     r13, r9
0x1400098bb  mov     r12, [rsp+98h+arg_20]
0x1400098c3  mov     r15, r8
0x1400098c6  mov     [rsp+98h+var_70], ebp; unsigned int
0x1400098ca  mov     rsi, rdx
0x1400098cd  mov     [rsp+98h+var_78], r12; unsigned __int64
0x1400098d2  mov     rbx, rcx
0x1400098d5  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1400098da  test    al, al
0x1400098dc  jz      short loc_1400098E5
0x1400098de  mov     al, 1
0x1400098e0  jmp     loc_140009A26
0x1400098e5  lea     rdx, [r12+20h]
0x1400098ea  add     rdx, r15; unsigned __int64
0x1400098ed  lea     r14, [rbx+18h]
0x1400098f1  cmp     qword ptr [r14], 0
0x1400098f5  jnz     loc_1400099FE
0x1400098fb  xorps   xmm0, xmm0
0x1400098fe  lea     rcx, [rsp+98h+var_68]; this
0x140009903  xorps   xmm1, xmm1
0x140009906  add     rdx, 0Ah; unsigned __int64
0x14000990a  movdqu  [rsp+98h+var_68], xmm0
0x140009910  movdqu  [rsp+98h+var_58], xmm1
0x140009916  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000991b  test    al, al
0x14000991d  jz      loc_1400099DE
0x140009923  mov     rdi, qword ptr [rsp+98h+var_58]
0x140009928  mov     rsi, qword ptr [rsp+98h+var_68]
0x14000992d  sub     rdi, rsi
0x140009930  cmp     rdi, 0Ah
0x140009934  jb      loc_140009A37
0x14000993a  mov     rbp, [rbx+30h]
0x14000993e  mov     qword ptr [rbx+30h], 0
0x140009946  test    rbp, rbp
0x140009949  jz      short loc_14000995F
0x14000994b  call    cs:__imp_GetProcessHeap
0x140009951  mov     r8, rbp; lpMem
0x140009954  xor     edx, edx; dwFlags
0x140009956  mov     rcx, rax; hHeap
0x140009959  call    cs:__imp_HeapFree
0x14000995f  mov     [r14], rsi
0x140009962  lea     rax, [rdi+rsi]
0x140009966  mov     [rbx+28h], rax
0x14000996a  xor     edi, edi
0x14000996c  xor     eax, eax
0x14000996e  mov     byte ptr [rbx+39h], 0
0x140009972  mov     [rsi], ax
0x140009975  movzx   eax, word ptr [rbx]
0x140009978  mov     [rsi+2], ax
0x14000997c  movzx   eax, word ptr [rbx+2]
0x140009980  mov     [rsi+4], ax
0x140009984  mov     al, [rbx+4]
0x140009987  mov     [rsi+8], al
0x14000998a  movzx   eax, word ptr [rbx+6]
0x14000998e  mov     [rsi+6], ax
0x140009992  mov     al, [rbx+8]
0x140009995  mov     [rsi+9], al
0x140009998  mov     rax, [r14]
0x14000999b  add     rax, 0Ah
0x14000999f  mov     [rbx+20h], rax
0x1400099a3  mov     rsi, [rbx+30h]
0x1400099a7  mov     rax, qword ptr [rsp+98h+var_58+8]
0x1400099ac  mov     [rbx+30h], rax
0x1400099b0  test    rsi, rsi
0x1400099b3  jz      short loc_1400099C9
0x1400099b5  call    cs:__imp_GetProcessHeap
0x1400099bb  mov     r8, rsi; lpMem
0x1400099be  xor     edx, edx; dwFlags
0x1400099c0  mov     rcx, rax; hHeap
0x1400099c3  call    cs:__imp_HeapFree
0x1400099c9  mov     rsi, [rsp+98h+Buf1]
0x1400099d1  mov     ebp, [rsp+98h+arg_28]
0x1400099d8  mov     byte ptr [rbx+3Ah], 1
0x1400099dc  jmp     short loc_1400099E3
0x1400099de  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x1400099e3  test    rdi, rdi
0x1400099e6  jz      short loc_140009A0C
0x1400099e8  call    cs:__imp_GetProcessHeap
0x1400099ee  mov     r8, rdi; lpMem
0x1400099f1  xor     edx, edx; dwFlags
0x1400099f3  mov     rcx, rax; hHeap
0x1400099f6  call    cs:__imp_HeapFree
0x1400099fc  jmp     short loc_140009A0C
0x1400099fe  cmp     byte ptr [rbx+3Ah], 0
0x140009a02  jz      short loc_140009A0C
0x140009a04  mov     rcx, r14; this
0x140009a07  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140009a0c  mov     [rsp+98h+var_70], ebp; unsigned int
0x140009a10  mov     r9, r13; void *
0x140009a13  mov     r8, r15; Size
0x140009a16  mov     [rsp+98h+var_78], r12; unsigned __int64
0x140009a1b  mov     rdx, rsi; Buf1
0x140009a1e  mov     rcx, rbx; this
0x140009a21  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x140009a26  add     rsp, 58h
0x140009a2a  pop     r15
0x140009a2c  pop     r14
0x140009a2e  pop     r13
0x140009a30  pop     r12
0x140009a32  pop     rdi
0x140009a33  pop     rsi
0x140009a34  pop     rbp
0x140009a35  pop     rbx
0x140009a36  retn
0x140009a37  mov     rcx, [rsp+98h]; this
0x140009a3f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
