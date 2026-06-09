# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x14000b280`
- end: `0x14000b429`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140008df0`
- `0x14000b17c`
- `0x14000b1b0`

## callees

- `0x14000b280`
- `0x14000b430`
- `0x14000db50`
- `0x14000dd18`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b32f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b399`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b3cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b32f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b399`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b3cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b33d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b3a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b3da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b33d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b3a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b3da`

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
0x14000b280  mov     [rsp+Buf1], rdx
0x14000b285  push    rbx
0x14000b286  push    rbp
0x14000b287  push    rsi
0x14000b288  push    rdi
0x14000b289  push    r12
0x14000b28b  push    r13
0x14000b28d  push    r14
0x14000b28f  push    r15
0x14000b291  sub     rsp, 58h
0x14000b295  mov     ebp, [rsp+98h+arg_28]
0x14000b29c  mov     r13, r9
0x14000b29f  mov     r12, [rsp+98h+arg_20]
0x14000b2a7  mov     r15, r8
0x14000b2aa  mov     [rsp+98h+var_70], ebp; unsigned int
0x14000b2ae  mov     rsi, rdx
0x14000b2b1  mov     [rsp+98h+var_78], r12; unsigned __int64
0x14000b2b6  mov     rbx, rcx
0x14000b2b9  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x14000b2be  test    al, al
0x14000b2c0  jz      short loc_14000B2C9
0x14000b2c2  mov     al, 1
0x14000b2c4  jmp     loc_14000B40A
0x14000b2c9  lea     rdx, [r12+20h]
0x14000b2ce  add     rdx, r15; unsigned __int64
0x14000b2d1  lea     r14, [rbx+18h]
0x14000b2d5  cmp     qword ptr [r14], 0
0x14000b2d9  jnz     loc_14000B3E2
0x14000b2df  xorps   xmm0, xmm0
0x14000b2e2  lea     rcx, [rsp+98h+var_68]; this
0x14000b2e7  xorps   xmm1, xmm1
0x14000b2ea  add     rdx, 0Ah; unsigned __int64
0x14000b2ee  movdqu  [rsp+98h+var_68], xmm0
0x14000b2f4  movdqu  [rsp+98h+var_58], xmm1
0x14000b2fa  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000b2ff  test    al, al
0x14000b301  jz      loc_14000B3C2
0x14000b307  mov     rdi, qword ptr [rsp+98h+var_58]
0x14000b30c  mov     rsi, qword ptr [rsp+98h+var_68]
0x14000b311  sub     rdi, rsi
0x14000b314  cmp     rdi, 0Ah
0x14000b318  jb      loc_14000B41B
0x14000b31e  mov     rbp, [rbx+30h]
0x14000b322  mov     qword ptr [rbx+30h], 0
0x14000b32a  test    rbp, rbp
0x14000b32d  jz      short loc_14000B343
0x14000b32f  call    cs:__imp_GetProcessHeap
0x14000b335  mov     r8, rbp; lpMem
0x14000b338  xor     edx, edx; dwFlags
0x14000b33a  mov     rcx, rax; hHeap
0x14000b33d  call    cs:__imp_HeapFree
0x14000b343  mov     [r14], rsi
0x14000b346  lea     rax, [rdi+rsi]
0x14000b34a  mov     [rbx+28h], rax
0x14000b34e  xor     edi, edi
0x14000b350  xor     eax, eax
0x14000b352  mov     byte ptr [rbx+39h], 0
0x14000b356  mov     [rsi], ax
0x14000b359  movzx   eax, word ptr [rbx]
0x14000b35c  mov     [rsi+2], ax
0x14000b360  movzx   eax, word ptr [rbx+2]
0x14000b364  mov     [rsi+4], ax
0x14000b368  mov     al, [rbx+4]
0x14000b36b  mov     [rsi+8], al
0x14000b36e  movzx   eax, word ptr [rbx+6]
0x14000b372  mov     [rsi+6], ax
0x14000b376  mov     al, [rbx+8]
0x14000b379  mov     [rsi+9], al
0x14000b37c  mov     rax, [r14]
0x14000b37f  add     rax, 0Ah
0x14000b383  mov     [rbx+20h], rax
0x14000b387  mov     rsi, [rbx+30h]
0x14000b38b  mov     rax, qword ptr [rsp+98h+var_58+8]
0x14000b390  mov     [rbx+30h], rax
0x14000b394  test    rsi, rsi
0x14000b397  jz      short loc_14000B3AD
0x14000b399  call    cs:__imp_GetProcessHeap
0x14000b39f  mov     r8, rsi; lpMem
0x14000b3a2  xor     edx, edx; dwFlags
0x14000b3a4  mov     rcx, rax; hHeap
0x14000b3a7  call    cs:__imp_HeapFree
0x14000b3ad  mov     rsi, [rsp+98h+Buf1]
0x14000b3b5  mov     ebp, [rsp+98h+arg_28]
0x14000b3bc  mov     byte ptr [rbx+3Ah], 1
0x14000b3c0  jmp     short loc_14000B3C7
0x14000b3c2  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x14000b3c7  test    rdi, rdi
0x14000b3ca  jz      short loc_14000B3F0
0x14000b3cc  call    cs:__imp_GetProcessHeap
0x14000b3d2  mov     r8, rdi; lpMem
0x14000b3d5  xor     edx, edx; dwFlags
0x14000b3d7  mov     rcx, rax; hHeap
0x14000b3da  call    cs:__imp_HeapFree
0x14000b3e0  jmp     short loc_14000B3F0
0x14000b3e2  cmp     byte ptr [rbx+3Ah], 0
0x14000b3e6  jz      short loc_14000B3F0
0x14000b3e8  mov     rcx, r14; this
0x14000b3eb  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000b3f0  mov     [rsp+98h+var_70], ebp; unsigned int
0x14000b3f4  mov     r9, r13; void *
0x14000b3f7  mov     r8, r15; Size
0x14000b3fa  mov     [rsp+98h+var_78], r12; unsigned __int64
0x14000b3ff  mov     rdx, rsi; Buf1
0x14000b402  mov     rcx, rbx; this
0x14000b405  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x14000b40a  add     rsp, 58h
0x14000b40e  pop     r15
0x14000b410  pop     r14
0x14000b412  pop     r13
0x14000b414  pop     r12
0x14000b416  pop     rdi
0x14000b417  pop     rsi
0x14000b418  pop     rbp
0x14000b419  pop     rbx
0x14000b41a  retn
0x14000b41b  mov     rcx, [rsp+98h]; this
0x14000b423  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
