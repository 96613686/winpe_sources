# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180006660`
- end: `0x180006809`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `425`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180003980`
- `0x180006560`
- `0x180006594`

## callees

- `0x180006660`
- `0x180006810`
- `0x1800094a0`
- `0x18000a0e4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000671d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006787`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800067ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000671d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006787`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800067ba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000670f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006779`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800067ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000670f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006779`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800067ac`

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
0x180006660  mov     [rsp+Buf1], rdx
0x180006665  push    rbx
0x180006666  push    rbp
0x180006667  push    rsi
0x180006668  push    rdi
0x180006669  push    r12
0x18000666b  push    r13
0x18000666d  push    r14
0x18000666f  push    r15
0x180006671  sub     rsp, 58h
0x180006675  mov     ebp, [rsp+98h+arg_28]
0x18000667c  mov     r13, r9
0x18000667f  mov     r12, [rsp+98h+arg_20]
0x180006687  mov     r15, r8
0x18000668a  mov     [rsp+98h+var_70], ebp; unsigned int
0x18000668e  mov     rsi, rdx
0x180006691  mov     [rsp+98h+var_78], r12; unsigned __int64
0x180006696  mov     rbx, rcx
0x180006699  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000669e  test    al, al
0x1800066a0  jz      short loc_1800066A9
0x1800066a2  mov     al, 1
0x1800066a4  jmp     loc_1800067EA
0x1800066a9  lea     rdx, [r12+20h]
0x1800066ae  add     rdx, r15; unsigned __int64
0x1800066b1  lea     r14, [rbx+18h]
0x1800066b5  cmp     qword ptr [r14], 0
0x1800066b9  jnz     loc_1800067C2
0x1800066bf  xorps   xmm0, xmm0
0x1800066c2  lea     rcx, [rsp+98h+var_68]; this
0x1800066c7  xorps   xmm1, xmm1
0x1800066ca  add     rdx, 0Ah; unsigned __int64
0x1800066ce  movdqu  [rsp+98h+var_68], xmm0
0x1800066d4  movdqu  [rsp+98h+var_58], xmm1
0x1800066da  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800066df  test    al, al
0x1800066e1  jz      loc_1800067A2
0x1800066e7  mov     rdi, qword ptr [rsp+98h+var_58]
0x1800066ec  mov     rsi, qword ptr [rsp+98h+var_68]
0x1800066f1  sub     rdi, rsi
0x1800066f4  cmp     rdi, 0Ah
0x1800066f8  jb      loc_1800067FB
0x1800066fe  mov     rbp, [rbx+30h]
0x180006702  mov     qword ptr [rbx+30h], 0
0x18000670a  test    rbp, rbp
0x18000670d  jz      short loc_180006723
0x18000670f  call    cs:__imp_GetProcessHeap
0x180006715  mov     r8, rbp; lpMem
0x180006718  xor     edx, edx; dwFlags
0x18000671a  mov     rcx, rax; hHeap
0x18000671d  call    cs:__imp_HeapFree
0x180006723  mov     [r14], rsi
0x180006726  lea     rax, [rdi+rsi]
0x18000672a  mov     [rbx+28h], rax
0x18000672e  xor     edi, edi
0x180006730  xor     eax, eax
0x180006732  mov     byte ptr [rbx+39h], 0
0x180006736  mov     [rsi], ax
0x180006739  movzx   eax, word ptr [rbx]
0x18000673c  mov     [rsi+2], ax
0x180006740  movzx   eax, word ptr [rbx+2]
0x180006744  mov     [rsi+4], ax
0x180006748  mov     al, [rbx+4]
0x18000674b  mov     [rsi+8], al
0x18000674e  movzx   eax, word ptr [rbx+6]
0x180006752  mov     [rsi+6], ax
0x180006756  mov     al, [rbx+8]
0x180006759  mov     [rsi+9], al
0x18000675c  mov     rax, [r14]
0x18000675f  add     rax, 0Ah
0x180006763  mov     [rbx+20h], rax
0x180006767  mov     rsi, [rbx+30h]
0x18000676b  mov     rax, qword ptr [rsp+98h+var_58+8]
0x180006770  mov     [rbx+30h], rax
0x180006774  test    rsi, rsi
0x180006777  jz      short loc_18000678D
0x180006779  call    cs:__imp_GetProcessHeap
0x18000677f  mov     r8, rsi; lpMem
0x180006782  xor     edx, edx; dwFlags
0x180006784  mov     rcx, rax; hHeap
0x180006787  call    cs:__imp_HeapFree
0x18000678d  mov     rsi, [rsp+98h+Buf1]
0x180006795  mov     ebp, [rsp+98h+arg_28]
0x18000679c  mov     byte ptr [rbx+3Ah], 1
0x1800067a0  jmp     short loc_1800067A7
0x1800067a2  mov     rdi, qword ptr [rsp+98h+var_58+8]
0x1800067a7  test    rdi, rdi
0x1800067aa  jz      short loc_1800067D0
0x1800067ac  call    cs:__imp_GetProcessHeap
0x1800067b2  mov     r8, rdi; lpMem
0x1800067b5  xor     edx, edx; dwFlags
0x1800067b7  mov     rcx, rax; hHeap
0x1800067ba  call    cs:__imp_HeapFree
0x1800067c0  jmp     short loc_1800067D0
0x1800067c2  cmp     byte ptr [rbx+3Ah], 0
0x1800067c6  jz      short loc_1800067D0
0x1800067c8  mov     rcx, r14; this
0x1800067cb  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800067d0  mov     [rsp+98h+var_70], ebp; unsigned int
0x1800067d4  mov     r9, r13; void *
0x1800067d7  mov     r8, r15; Size
0x1800067da  mov     [rsp+98h+var_78], r12; unsigned __int64
0x1800067df  mov     rdx, rsi; Buf1
0x1800067e2  mov     rcx, rbx; this
0x1800067e5  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1800067ea  add     rsp, 58h
0x1800067ee  pop     r15
0x1800067f0  pop     r14
0x1800067f2  pop     r13
0x1800067f4  pop     r12
0x1800067f6  pop     rdi
0x1800067f7  pop     rsi
0x1800067f8  pop     rbp
0x1800067f9  pop     rbx
0x1800067fa  retn
0x1800067fb  mov     rcx, [rsp+98h]; this
0x180006803  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
