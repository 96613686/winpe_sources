# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800131a4`
- end: `0x180013314`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `368`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180013408`

## callees

- `0x18000dbd8`
- `0x18000f4dc`
- `0x1800101a4`
- `0x1800127a0`
- `0x180013028`
- `0x180013048`
- `0x1800131a4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001324c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001324c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001325a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001325a`

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
0x1800131a4  push    rbx
0x1800131a6  push    rbp
0x1800131a7  push    rsi
0x1800131a8  push    rdi
0x1800131a9  push    r12
0x1800131ab  push    r13
0x1800131ad  push    r14
0x1800131af  push    r15
0x1800131b1  sub     rsp, 28h
0x1800131b5  mov     [rcx+4], r8d
0x1800131b9  lea     rbx, [rcx+20h]
0x1800131bd  mov     eax, [rdx+8]
0x1800131c0  lea     rsi, [rcx+38h]
0x1800131c4  mov     [rcx+8], eax
0x1800131c7  xor     r12d, r12d
0x1800131ca  mov     [rcx+10h], r12
0x1800131ce  mov     rbp, rcx
0x1800131d1  movzx   eax, word ptr [rdx+40h]
0x1800131d5  mov     r14, rdx
0x1800131d8  mov     [rcx+18h], ax
0x1800131dc  mov     al, [rdx]
0x1800131de  mov     [rcx+1Ah], al
0x1800131e1  mov     [rbx], r12
0x1800131e4  mov     rax, [rdx+88h]
0x1800131eb  mov     [rcx+28h], rax
0x1800131ef  mov     rax, [rdx+90h]
0x1800131f6  mov     [rcx+30h], rax
0x1800131fa  mov     [rsi], r12
0x1800131fd  mov     rcx, [rdx+18h]; this
0x180013201  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180013206  mov     rcx, [r14+38h]; this
0x18001320a  mov     r15, rax
0x18001320d  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180013212  mov     rcx, [r14+80h]; this
0x180013219  add     r15, rax
0x18001321c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180013221  add     r15, rax
0x180013224  lea     rdi, [rbp+48h]
0x180013228  cmp     [rbp+40h], r12
0x18001322c  jz      short loc_180013233
0x18001322e  cmp     [rdi], r15
0x180013231  jnb     short loc_18001326E
0x180013233  mov     rdx, r15; dwBytes
0x180013236  mov     ecx, 8; dwFlags
0x18001323b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180013240  mov     r12, rax
0x180013243  test    rax, rax
0x180013246  jz      short loc_18001326B
0x180013248  mov     rbx, [rbp+40h]
0x18001324c  call    cs:__imp_GetProcessHeap
0x180013252  mov     r8, rbx; lpMem
0x180013255  xor     edx, edx; dwFlags
0x180013257  mov     rcx, rax; hHeap
0x18001325a  call    cs:__imp_HeapFree
0x180013260  mov     [rbp+40h], r12
0x180013264  lea     rbx, [rbp+20h]
0x180013268  mov     [rdi], r15
0x18001326b  xor     r12d, r12d
0x18001326e  mov     rcx, [rbp+40h]; Destination
0x180013272  test    rcx, rcx
0x180013275  jz      loc_180013303
0x18001327b  mov     rdi, [rdi]
0x18001327e  lea     r9, [rbp+10h]
0x180013282  mov     r8, [r14+38h]
0x180013286  add     rdi, rcx
0x180013289  mov     rdx, rdi
0x18001328c  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180013291  mov     r8, [r14+80h]
0x180013298  mov     r9, rbx
0x18001329b  mov     rdx, rdi
0x18001329e  mov     rcx, rax; Destination
0x1800132a1  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800132a6  mov     rbx, rax
0x1800132a9  cmp     rax, rdi
0x1800132ac  jz      short loc_1800132EB
0x1800132ae  mov     rcx, [r14+18h]; this
0x1800132b2  test    rcx, rcx
0x1800132b5  jz      short loc_1800132EB
0x1800132b7  cmp     [rcx], r12w
0x1800132bb  jz      short loc_1800132EB
0x1800132bd  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800132c2  mov     rdx, rdi
0x1800132c5  mov     r14, rax
0x1800132c8  sub     rdx, rbx; DestinationSize
0x1800132cb  cmp     rdx, rax
0x1800132ce  jb      short loc_1800132EB
0x1800132d0  mov     r8, rcx; Source
0x1800132d3  mov     r9, rax; SourceSize
0x1800132d6  mov     rcx, rbx; Destination
0x1800132d9  call    memcpy_s
0x1800132de  test    rsi, rsi
0x1800132e1  jz      short loc_1800132E6
0x1800132e3  mov     [rsi], rbx
0x1800132e6  add     rbx, r14
0x1800132e9  jmp     short loc_1800132F3
0x1800132eb  test    rsi, rsi
0x1800132ee  jz      short loc_1800132F3
0x1800132f0  mov     [rsi], r12
0x1800132f3  sub     rdi, rbx
0x1800132f6  xor     edx, edx; Val
0x1800132f8  mov     r8, rdi; Size
0x1800132fb  mov     rcx, rbx; void *
0x1800132fe  call    memset_0
0x180013303  add     rsp, 28h
0x180013307  pop     r15
0x180013309  pop     r14
0x18001330b  pop     r13
0x18001330d  pop     r12
0x18001330f  pop     rdi
0x180013310  pop     rsi
0x180013311  pop     rbp
0x180013312  pop     rbx
0x180013313  retn
```
