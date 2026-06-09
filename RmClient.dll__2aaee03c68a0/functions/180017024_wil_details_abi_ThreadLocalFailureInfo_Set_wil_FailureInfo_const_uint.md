# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180017024`
- end: `0x180017195`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `369`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001719c`

## callees

- `0x18000de80`
- `0x180015e38`
- `0x180016f54`
- `0x180016f74`
- `0x180017024`
- `0x18001ae8e`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180017159`
- `msvcrt!memcpy_s` at `0x180017159`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800170da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800170da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800170cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800170cc`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  char **v3; // rbx
  char **v4; // rsi
  unsigned __int64 v7; // r15
  const char *v8; // rdx
  unsigned __int64 v9; // r15
  const char *v10; // rdx
  SIZE_T v11; // r15
  SIZE_T *v12; // rdi
  LPVOID v13; // r12
  void *v14; // rbx
  HANDLE ProcessHeap; // rax
  char *v16; // rcx
  const char *v17; // rdi
  char *v18; // rax
  const unsigned __int16 *v19; // rdx
  char *v20; // rbx
  wil::details *v21; // rcx
  rsize_t v22; // rax
  const void *v23; // rcx
  rsize_t v24; // r14

  *((_DWORD *)this + 1) = a3;
  v3 = (char **)((char *)this + 32);
  v4 = (char **)((char *)this + 56);
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v7 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const unsigned __int16 *)a2);
  v9 = wil::details::ResultStringSize(*((wil::details **)a2 + 7), v8) + v7;
  v11 = wil::details::ResultStringSize(*((wil::details **)a2 + 16), v10) + v9;
  v12 = (SIZE_T *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v12 < v11 )
  {
    v13 = wil::details::ProcessHeapAlloc(8u, v11);
    if ( v13 )
    {
      v14 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v14);
      *((_QWORD *)this + 8) = v13;
      v3 = (char **)((char *)this + 32);
      *v12 = v11;
    }
  }
  v16 = (char *)*((_QWORD *)this + 8);
  if ( v16 )
  {
    v17 = &v16[*v12];
    v18 = wil::details::WriteResultString<char const *>(v16, v17, *((wil::details **)a2 + 7), (char **)this + 2);
    v20 = wil::details::WriteResultString<char const *>(v18, v17, *((wil::details **)a2 + 16), v3);
    if ( v20 != v17
      && (v21 = (wil::details *)*((_QWORD *)a2 + 3)) != 0
      && *(_WORD *)v21
      && (v22 = wil::details::ResultStringSize(v21, v19), v24 = v22, v17 - v20 >= v22) )
    {
      memcpy_s(v20, v17 - v20, v23, v22);
      if ( v4 )
        *v4 = v20;
      v20 += v24;
    }
    else if ( v4 )
    {
      *v4 = 0;
    }
    memset_0(v20, 0, v17 - v20);
  }
}

```

## disassembly

```asm
0x180017024  push    rbx
0x180017026  push    rbp
0x180017027  push    rsi
0x180017028  push    rdi
0x180017029  push    r12
0x18001702b  push    r13
0x18001702d  push    r14
0x18001702f  push    r15
0x180017031  sub     rsp, 28h
0x180017035  mov     [rcx+4], r8d
0x180017039  lea     rbx, [rcx+20h]
0x18001703d  mov     eax, [rdx+8]
0x180017040  lea     rsi, [rcx+38h]
0x180017044  mov     [rcx+8], eax
0x180017047  xor     r12d, r12d
0x18001704a  mov     [rcx+10h], r12
0x18001704e  mov     rbp, rcx
0x180017051  movzx   eax, word ptr [rdx+40h]
0x180017055  mov     r14, rdx
0x180017058  mov     [rcx+18h], ax
0x18001705c  mov     al, [rdx]
0x18001705e  mov     [rcx+1Ah], al
0x180017061  mov     [rbx], r12
0x180017064  mov     rax, [rdx+88h]
0x18001706b  mov     [rcx+28h], rax
0x18001706f  mov     rax, [rdx+90h]
0x180017076  mov     [rcx+30h], rax
0x18001707a  mov     [rsi], r12
0x18001707d  mov     rcx, [rdx+18h]; this
0x180017081  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180017086  mov     rcx, [r14+38h]; this
0x18001708a  mov     r15, rax
0x18001708d  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180017092  mov     rcx, [r14+80h]; this
0x180017099  add     r15, rax
0x18001709c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800170a1  add     r15, rax
0x1800170a4  lea     rdi, [rbp+48h]
0x1800170a8  cmp     [rbp+40h], r12
0x1800170ac  jz      short loc_1800170B3
0x1800170ae  cmp     [rdi], r15
0x1800170b1  jnb     short loc_1800170EE
0x1800170b3  mov     rdx, r15; dwBytes
0x1800170b6  mov     ecx, 8; dwFlags
0x1800170bb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800170c0  mov     r12, rax
0x1800170c3  test    rax, rax
0x1800170c6  jz      short loc_1800170EB
0x1800170c8  mov     rbx, [rbp+40h]
0x1800170cc  call    cs:__imp_GetProcessHeap
0x1800170d2  mov     r8, rbx; lpMem
0x1800170d5  xor     edx, edx; dwFlags
0x1800170d7  mov     rcx, rax; hHeap
0x1800170da  call    cs:__imp_HeapFree
0x1800170e0  mov     [rbp+40h], r12
0x1800170e4  lea     rbx, [rbp+20h]
0x1800170e8  mov     [rdi], r15
0x1800170eb  xor     r12d, r12d
0x1800170ee  mov     rcx, [rbp+40h]; Destination
0x1800170f2  test    rcx, rcx
0x1800170f5  jz      loc_180017184
0x1800170fb  mov     rdi, [rdi]
0x1800170fe  lea     r9, [rbp+10h]
0x180017102  mov     r8, [r14+38h]
0x180017106  add     rdi, rcx
0x180017109  mov     rdx, rdi
0x18001710c  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180017111  mov     r8, [r14+80h]
0x180017118  mov     r9, rbx
0x18001711b  mov     rdx, rdi
0x18001711e  mov     rcx, rax; Destination
0x180017121  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180017126  mov     rbx, rax
0x180017129  cmp     rax, rdi
0x18001712c  jz      short loc_18001716C
0x18001712e  mov     rcx, [r14+18h]; this
0x180017132  test    rcx, rcx
0x180017135  jz      short loc_18001716C
0x180017137  cmp     [rcx], r12w
0x18001713b  jz      short loc_18001716C
0x18001713d  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180017142  mov     rdx, rdi
0x180017145  mov     r14, rax
0x180017148  sub     rdx, rbx; DestinationSize
0x18001714b  cmp     rdx, rax
0x18001714e  jb      short loc_18001716C
0x180017150  mov     r8, rcx; Source
0x180017153  mov     r9, rax; SourceSize
0x180017156  mov     rcx, rbx; Destination
0x180017159  call    cs:__imp_memcpy_s
0x18001715f  test    rsi, rsi
0x180017162  jz      short loc_180017167
0x180017164  mov     [rsi], rbx
0x180017167  add     rbx, r14
0x18001716a  jmp     short loc_180017174
0x18001716c  test    rsi, rsi
0x18001716f  jz      short loc_180017174
0x180017171  mov     [rsi], r12
0x180017174  sub     rdi, rbx
0x180017177  xor     edx, edx; Val
0x180017179  mov     r8, rdi; Size
0x18001717c  mov     rcx, rbx; void *
0x18001717f  call    memset_0
0x180017184  add     rsp, 28h
0x180017188  pop     r15
0x18001718a  pop     r14
0x18001718c  pop     r13
0x18001718e  pop     r12
0x180017190  pop     rdi
0x180017191  pop     rsi
0x180017192  pop     rbp
0x180017193  pop     rbx
0x180017194  retn
```
