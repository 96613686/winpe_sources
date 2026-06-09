# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180005be0`
- end: `0x180005dae`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `462`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800032b0`
- `0x180005ad0`
- `0x180005b08`

## callees

- `0x180005be0`
- `0x180005db4`
- `0x180007898`
- `0x180008360`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180005c8f`
- `KERNEL32!GetProcessHeap` at `0x180005d05`
- `KERNEL32!GetProcessHeap` at `0x180005d44`
- `KERNEL32!GetProcessHeap` at `0x180005c8f`
- `KERNEL32!GetProcessHeap` at `0x180005d05`
- `KERNEL32!GetProcessHeap` at `0x180005d44`
- `KERNEL32!HeapFree` at `0x180005ca3`
- `KERNEL32!HeapFree` at `0x180005d19`
- `KERNEL32!HeapFree` at `0x180005d58`
- `KERNEL32!HeapFree` at `0x180005ca3`
- `KERNEL32!HeapFree` at `0x180005d19`
- `KERNEL32!HeapFree` at `0x180005d58`

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
0x180005be0  mov     [rsp+Buf1], rdx
0x180005be5  push    rbx
0x180005be6  push    rbp
0x180005be7  push    rsi
0x180005be8  push    rdi
0x180005be9  push    r12
0x180005beb  push    r13
0x180005bed  push    r14
0x180005bef  push    r15
0x180005bf1  sub     rsp, 58h
0x180005bf5  mov     ebp, [rsp+98h+arg_28]
0x180005bfc  mov     r13, r9
0x180005bff  mov     r12, [rsp+98h+arg_20]
0x180005c07  mov     r15, r8
0x180005c0a  mov     [rsp+98h+var_70], ebp; unsigned int
0x180005c0e  mov     rsi, rdx
0x180005c11  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180005c16  mov     rbx, rcx
0x180005c19  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180005c1e  test    al, al
0x180005c20  jz      short loc_180005C29
0x180005c22  mov     al, 1
0x180005c24  jmp     loc_180005D8E
0x180005c29  lea     rdx, [r12+20h]
0x180005c2e  add     rdx, r15; unsigned __int64
0x180005c31  lea     r14, [rbx+18h]
0x180005c35  cmp     qword ptr [r14], 0
0x180005c39  jnz     loc_180005D66
0x180005c3f  xorps   xmm0, xmm0
0x180005c42  lea     rcx, [rsp+98h+var_68]; this
0x180005c47  xorps   xmm1, xmm1
0x180005c4a  add     rdx, 0Ah; unsigned __int64
0x180005c4e  movdqu  [rsp+98h+var_68], xmm0
0x180005c54  movdqu  [rsp+98h+var_58], xmm1
0x180005c5a  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180005c5f  test    al, al
0x180005c61  jz      loc_180005D3A
0x180005c67  mov     rdi, qword ptr [rsp+98h+var_58]
0x180005c6c  mov     rsi, qword ptr [rsp+98h+var_68]
0x180005c71  sub     rdi, rsi
0x180005c74  cmp     rdi, 0Ah
0x180005c78  jb      loc_180005DA0
0x180005c7e  mov     rbp, [rbx+30h]
0x180005c82  mov     qword ptr [rbx+30h], 0
0x180005c8a  test    rbp, rbp
0x180005c8d  jz      short loc_180005CAF
0x180005c8f  call    cs:__imp_GetProcessHeap
0x180005c96  nop     dword ptr [rax+rax+00h]
0x180005c9b  mov     r8, rbp; lpMem
0x180005c9e  xor     edx, edx; dwFlags
0x180005ca0  mov     rcx, rax; hHeap
0x180005ca3  call    cs:__imp_HeapFree
0x180005caa  nop     dword ptr [rax+rax+00h]
0x180005caf  mov     [r14], rsi
0x180005cb2  lea     rax, [rdi+rsi]
0x180005cb6  mov     [rbx+28h], rax
0x180005cba  xor     edi, edi
0x180005cbc  xor     eax, eax
0x180005cbe  mov     byte ptr [rbx+39h], 0
0x180005cc2  mov     [rsi], ax
0x180005cc5  movzx   eax, word ptr [rbx]
0x180005cc8  mov     [rsi+2], ax
0x180005ccc  movzx   eax, word ptr [rbx+2]
0x180005cd0  mov     [rsi+4], ax
0x180005cd4  mov     al, [rbx+4]
0x180005cd7  mov     [rsi+8], al
0x180005cda  movzx   eax, word ptr [rbx+6]
0x180005cde  mov     [rsi+6], ax
0x180005ce2  mov     al, [rbx+8]
0x180005ce5  mov     [rsi+9], al
0x180005ce8  mov     rax, [r14]
0x180005ceb  add     rax, 0Ah
0x180005cef  mov     [rbx+20h], rax
0x180005cf3  mov     rsi, [rbx+30h]
0x180005cf7  mov     rax, qword ptr [rsp+98h+var_58+8]
0x180005cfc  mov     [rbx+30h], rax
0x180005d00  test    rsi, rsi
0x180005d03  jz      short loc_180005D25
0x180005d05  call    cs:__imp_GetProcessHeap
0x180005d0c  nop     dword ptr [rax+rax+00h]
0x180005d11  mov     r8, rsi; lpMem
0x180005d14  xor     edx, edx; dwFlags
0x180005d16  mov     rcx, rax; hHeap
0x180005d19  call    cs:__imp_HeapFree
0x180005d20  nop     dword ptr [rax+rax+00h]
0x180005d25  mov     rsi, [rsp+98h+Buf1]
0x180005d2d  mov     ebp, [rsp+98h+arg_28]
0x180005d34  mov     byte ptr [rbx+3Ah], 1
0x180005d38  jmp     short loc_180005D3F
0x180005d3a  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x180005d3f  test    rdi, rdi
0x180005d42  jz      short loc_180005D74
0x180005d44  call    cs:__imp_GetProcessHeap
0x180005d4b  nop     dword ptr [rax+rax+00h]
0x180005d50  mov     r8, rdi; lpMem
0x180005d53  xor     edx, edx; dwFlags
0x180005d55  mov     rcx, rax; hHeap
0x180005d58  call    cs:__imp_HeapFree
0x180005d5f  nop     dword ptr [rax+rax+00h]
0x180005d64  jmp     short loc_180005D74
0x180005d66  cmp     byte ptr [rbx+3Ah], 0
0x180005d6a  jz      short loc_180005D74
0x180005d6c  mov     rcx, r14; this
0x180005d6f  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180005d74  mov     [rsp+98h+var_70], ebp; unsigned int
0x180005d78  mov     r9, r13; void *
0x180005d7b  mov     r8, r15; Size
0x180005d7e  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180005d83  mov     rdx, rsi; Buf1
0x180005d86  mov     rcx, rbx; this
0x180005d89  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180005d8e  add     rsp, 58h
0x180005d92  pop     r15
0x180005d94  pop     r14
0x180005d96  pop     r13
0x180005d98  pop     r12
0x180005d9a  pop     rdi
0x180005d9b  pop     rsi
0x180005d9c  pop     rbp
0x180005d9d  pop     rbx
0x180005d9e  retn
0x180005da0  mov     rcx, [rsp+98h]; this
0x180005da8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
