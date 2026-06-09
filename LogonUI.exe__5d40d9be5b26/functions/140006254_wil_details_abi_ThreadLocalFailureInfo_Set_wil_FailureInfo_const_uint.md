# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140006254`
- end: `0x1400063c4`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `368`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400064b8`

## callees

- `0x140001cdc`
- `0x1400032d0`
- `0x1400039c8`
- `0x1400058d4`
- `0x1400060dc`
- `0x1400060fc`
- `0x140006254`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400062fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400062fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000630a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000630a`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  _QWORD *v3; // rsi
  unsigned __int64 v6; // r15
  const char *v7; // rdx
  unsigned __int64 v8; // r15
  const char *v9; // rdx
  SIZE_T v10; // r15
  SIZE_T *v11; // rdi
  LPVOID v12; // r12
  void *v13; // rbx
  HANDLE ProcessHeap; // rax
  char *v15; // rcx
  char *v16; // rdi
  void *v17; // rax
  const unsigned __int16 *v18; // rdx
  char *v19; // rbx
  wil::details *v20; // rcx
  rsize_t v21; // rax
  const void *v22; // rcx
  rsize_t v23; // r14

  *((_DWORD *)this + 1) = a3;
  v3 = (_QWORD *)((char *)this + 56);
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v6 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const unsigned __int16 *)a2);
  v8 = wil::details::ResultStringSize(*((wil::details **)a2 + 7), v7) + v6;
  v10 = wil::details::ResultStringSize(*((wil::details **)a2 + 16), v9) + v8;
  v11 = (SIZE_T *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v11 < v10 )
  {
    v12 = wil::details::ProcessHeapAlloc(8u, v10);
    if ( v12 )
    {
      v13 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v13);
      *((_QWORD *)this + 8) = v12;
      *v11 = v10;
    }
  }
  v15 = (char *)*((_QWORD *)this + 8);
  if ( v15 )
  {
    v16 = &v15[*v11];
    v17 = (void *)wil::details::WriteResultString<char const *>(v15);
    v19 = (char *)wil::details::WriteResultString<char const *>(v17);
    if ( v19 != v16
      && (v20 = (wil::details *)*((_QWORD *)a2 + 3)) != 0
      && *(_WORD *)v20
      && (v21 = wil::details::ResultStringSize(v20, v18), v23 = v21, v16 - v19 >= v21) )
    {
      memcpy_s(v19, v16 - v19, v22, v21);
      if ( v3 )
        *v3 = v19;
      v19 += v23;
    }
    else if ( v3 )
    {
      *v3 = 0;
    }
    memset_0(v19, 0, v16 - v19);
  }
}

```

## disassembly

```asm
0x140006254  push    rbx
0x140006256  push    rbp
0x140006257  push    rsi
0x140006258  push    rdi
0x140006259  push    r12
0x14000625b  push    r13
0x14000625d  push    r14
0x14000625f  push    r15
0x140006261  sub     rsp, 28h
0x140006265  mov     [rcx+4], r8d
0x140006269  lea     rbx, [rcx+20h]
0x14000626d  mov     eax, [rdx+8]
0x140006270  lea     rsi, [rcx+38h]
0x140006274  mov     [rcx+8], eax
0x140006277  xor     r12d, r12d
0x14000627a  mov     [rcx+10h], r12
0x14000627e  mov     rbp, rcx
0x140006281  movzx   eax, word ptr [rdx+40h]
0x140006285  mov     r14, rdx
0x140006288  mov     [rcx+18h], ax
0x14000628c  mov     al, [rdx]
0x14000628e  mov     [rcx+1Ah], al
0x140006291  mov     [rbx], r12
0x140006294  mov     rax, [rdx+88h]
0x14000629b  mov     [rcx+28h], rax
0x14000629f  mov     rax, [rdx+90h]
0x1400062a6  mov     [rcx+30h], rax
0x1400062aa  mov     [rsi], r12
0x1400062ad  mov     rcx, [rdx+18h]; this
0x1400062b1  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1400062b6  mov     rcx, [r14+38h]; this
0x1400062ba  mov     r15, rax
0x1400062bd  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1400062c2  mov     rcx, [r14+80h]; this
0x1400062c9  add     r15, rax
0x1400062cc  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1400062d1  add     r15, rax
0x1400062d4  lea     rdi, [rbp+48h]
0x1400062d8  cmp     [rbp+40h], r12
0x1400062dc  jz      short loc_1400062E3
0x1400062de  cmp     [rdi], r15
0x1400062e1  jnb     short loc_14000631E
0x1400062e3  mov     rdx, r15; dwBytes
0x1400062e6  mov     ecx, 8; dwFlags
0x1400062eb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400062f0  mov     r12, rax
0x1400062f3  test    rax, rax
0x1400062f6  jz      short loc_14000631B
0x1400062f8  mov     rbx, [rbp+40h]
0x1400062fc  call    cs:__imp_GetProcessHeap
0x140006302  mov     r8, rbx; lpMem
0x140006305  xor     edx, edx; dwFlags
0x140006307  mov     rcx, rax; hHeap
0x14000630a  call    cs:__imp_HeapFree
0x140006310  mov     [rbp+40h], r12
0x140006314  lea     rbx, [rbp+20h]
0x140006318  mov     [rdi], r15
0x14000631b  xor     r12d, r12d
0x14000631e  mov     rcx, [rbp+40h]; Destination
0x140006322  test    rcx, rcx
0x140006325  jz      loc_1400063B3
0x14000632b  mov     rdi, [rdi]
0x14000632e  lea     r9, [rbp+10h]
0x140006332  mov     r8, [r14+38h]
0x140006336  add     rdi, rcx
0x140006339  mov     rdx, rdi
0x14000633c  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140006341  mov     r8, [r14+80h]
0x140006348  mov     r9, rbx
0x14000634b  mov     rdx, rdi
0x14000634e  mov     rcx, rax; Destination
0x140006351  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140006356  mov     rbx, rax
0x140006359  cmp     rax, rdi
0x14000635c  jz      short loc_14000639B
0x14000635e  mov     rcx, [r14+18h]; this
0x140006362  test    rcx, rcx
0x140006365  jz      short loc_14000639B
0x140006367  cmp     [rcx], r12w
0x14000636b  jz      short loc_14000639B
0x14000636d  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x140006372  mov     rdx, rdi
0x140006375  mov     r14, rax
0x140006378  sub     rdx, rbx; DestinationSize
0x14000637b  cmp     rdx, rax
0x14000637e  jb      short loc_14000639B
0x140006380  mov     r8, rcx; Source
0x140006383  mov     r9, rax; SourceSize
0x140006386  mov     rcx, rbx; Destination
0x140006389  call    memcpy_s
0x14000638e  test    rsi, rsi
0x140006391  jz      short loc_140006396
0x140006393  mov     [rsi], rbx
0x140006396  add     rbx, r14
0x140006399  jmp     short loc_1400063A3
0x14000639b  test    rsi, rsi
0x14000639e  jz      short loc_1400063A3
0x1400063a0  mov     [rsi], r12
0x1400063a3  sub     rdi, rbx
0x1400063a6  xor     edx, edx; Val
0x1400063a8  mov     r8, rdi; Size
0x1400063ab  mov     rcx, rbx; void *
0x1400063ae  call    memset_0
0x1400063b3  add     rsp, 28h
0x1400063b7  pop     r15
0x1400063b9  pop     r14
0x1400063bb  pop     r13
0x1400063bd  pop     r12
0x1400063bf  pop     rdi
0x1400063c0  pop     rsi
0x1400063c1  pop     rbp
0x1400063c2  pop     rbx
0x1400063c3  retn
```
