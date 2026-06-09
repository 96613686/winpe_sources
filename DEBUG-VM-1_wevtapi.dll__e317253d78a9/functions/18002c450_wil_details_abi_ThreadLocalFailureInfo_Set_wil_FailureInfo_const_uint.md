# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18002c450`
- end: `0x18002c5c0`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `368`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002c6b4`

## callees

- `0x1800209cc`
- `0x1800254b4`
- `0x1800298a8`
- `0x18002bac0`
- `0x18002c2dc`
- `0x18002c2fc`
- `0x18002c450`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c4f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c4f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c506`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c506`

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
  const wchar_t *v18; // rdx
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
  v6 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const wchar_t *)a2);
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
0x18002c450  push    rbx
0x18002c452  push    rbp
0x18002c453  push    rsi
0x18002c454  push    rdi
0x18002c455  push    r12
0x18002c457  push    r13
0x18002c459  push    r14
0x18002c45b  push    r15
0x18002c45d  sub     rsp, 28h
0x18002c461  mov     [rcx+4], r8d
0x18002c465  lea     rbx, [rcx+20h]
0x18002c469  mov     eax, [rdx+8]
0x18002c46c  lea     rsi, [rcx+38h]
0x18002c470  mov     [rcx+8], eax
0x18002c473  xor     r12d, r12d
0x18002c476  mov     [rcx+10h], r12
0x18002c47a  mov     rbp, rcx
0x18002c47d  movzx   eax, word ptr [rdx+40h]
0x18002c481  mov     r14, rdx
0x18002c484  mov     [rcx+18h], ax
0x18002c488  mov     al, [rdx]
0x18002c48a  mov     [rcx+1Ah], al
0x18002c48d  mov     [rbx], r12
0x18002c490  mov     rax, [rdx+88h]
0x18002c497  mov     [rcx+28h], rax
0x18002c49b  mov     rax, [rdx+90h]
0x18002c4a2  mov     [rcx+30h], rax
0x18002c4a6  mov     [rsi], r12
0x18002c4a9  mov     rcx, [rdx+18h]; this
0x18002c4ad  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x18002c4b2  mov     rcx, [r14+38h]; this
0x18002c4b6  mov     r15, rax
0x18002c4b9  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18002c4be  mov     rcx, [r14+80h]; this
0x18002c4c5  add     r15, rax
0x18002c4c8  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18002c4cd  add     r15, rax
0x18002c4d0  lea     rdi, [rbp+48h]
0x18002c4d4  cmp     [rbp+40h], r12
0x18002c4d8  jz      short loc_18002C4DF
0x18002c4da  cmp     [rdi], r15
0x18002c4dd  jnb     short loc_18002C51A
0x18002c4df  mov     rdx, r15; dwBytes
0x18002c4e2  mov     ecx, 8; dwFlags
0x18002c4e7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18002c4ec  mov     r12, rax
0x18002c4ef  test    rax, rax
0x18002c4f2  jz      short loc_18002C517
0x18002c4f4  mov     rbx, [rbp+40h]
0x18002c4f8  call    cs:__imp_GetProcessHeap
0x18002c4fe  mov     r8, rbx; lpMem
0x18002c501  xor     edx, edx; dwFlags
0x18002c503  mov     rcx, rax; hHeap
0x18002c506  call    cs:__imp_HeapFree
0x18002c50c  mov     [rbp+40h], r12
0x18002c510  lea     rbx, [rbp+20h]
0x18002c514  mov     [rdi], r15
0x18002c517  xor     r12d, r12d
0x18002c51a  mov     rcx, [rbp+40h]; Destination
0x18002c51e  test    rcx, rcx
0x18002c521  jz      loc_18002C5AF
0x18002c527  mov     rdi, [rdi]
0x18002c52a  lea     r9, [rbp+10h]
0x18002c52e  mov     r8, [r14+38h]
0x18002c532  add     rdi, rcx
0x18002c535  mov     rdx, rdi
0x18002c538  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18002c53d  mov     r8, [r14+80h]
0x18002c544  mov     r9, rbx
0x18002c547  mov     rdx, rdi
0x18002c54a  mov     rcx, rax; Destination
0x18002c54d  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18002c552  mov     rbx, rax
0x18002c555  cmp     rax, rdi
0x18002c558  jz      short loc_18002C597
0x18002c55a  mov     rcx, [r14+18h]; this
0x18002c55e  test    rcx, rcx
0x18002c561  jz      short loc_18002C597
0x18002c563  cmp     [rcx], r12w
0x18002c567  jz      short loc_18002C597
0x18002c569  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x18002c56e  mov     rdx, rdi
0x18002c571  mov     r14, rax
0x18002c574  sub     rdx, rbx; DestinationSize
0x18002c577  cmp     rdx, rax
0x18002c57a  jb      short loc_18002C597
0x18002c57c  mov     r8, rcx; Source
0x18002c57f  mov     r9, rax; SourceSize
0x18002c582  mov     rcx, rbx; Destination
0x18002c585  call    memcpy_s
0x18002c58a  test    rsi, rsi
0x18002c58d  jz      short loc_18002C592
0x18002c58f  mov     [rsi], rbx
0x18002c592  add     rbx, r14
0x18002c595  jmp     short loc_18002C59F
0x18002c597  test    rsi, rsi
0x18002c59a  jz      short loc_18002C59F
0x18002c59c  mov     [rsi], r12
0x18002c59f  sub     rdi, rbx
0x18002c5a2  xor     edx, edx; Val
0x18002c5a4  mov     r8, rdi; Size
0x18002c5a7  mov     rcx, rbx; void *
0x18002c5aa  call    memset_0
0x18002c5af  add     rsp, 28h
0x18002c5b3  pop     r15
0x18002c5b5  pop     r14
0x18002c5b7  pop     r13
0x18002c5b9  pop     r12
0x18002c5bb  pop     rdi
0x18002c5bc  pop     rsi
0x18002c5bd  pop     rbp
0x18002c5be  pop     rbx
0x18002c5bf  retn
```
