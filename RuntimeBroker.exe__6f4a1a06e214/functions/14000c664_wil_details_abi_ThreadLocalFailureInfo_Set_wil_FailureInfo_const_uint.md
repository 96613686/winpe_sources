# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x14000c664`
- end: `0x14000c7d4`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `368`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14000c824`

## callees

- `0x140006030`
- `0x14000837c`
- `0x140009640`
- `0x14000aa04`
- `0x14000c5b4`
- `0x14000c5d4`
- `0x14000c664`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c71a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c71a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c70c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c70c`

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
0x14000c664  push    rbx
0x14000c666  push    rbp
0x14000c667  push    rsi
0x14000c668  push    rdi
0x14000c669  push    r12
0x14000c66b  push    r13
0x14000c66d  push    r14
0x14000c66f  push    r15
0x14000c671  sub     rsp, 28h
0x14000c675  mov     [rcx+4], r8d
0x14000c679  lea     rbx, [rcx+20h]
0x14000c67d  mov     eax, [rdx+8]
0x14000c680  lea     rsi, [rcx+38h]
0x14000c684  mov     [rcx+8], eax
0x14000c687  xor     r12d, r12d
0x14000c68a  mov     [rcx+10h], r12
0x14000c68e  mov     rbp, rcx
0x14000c691  movzx   eax, word ptr [rdx+40h]
0x14000c695  mov     r14, rdx
0x14000c698  mov     [rcx+18h], ax
0x14000c69c  mov     al, [rdx]
0x14000c69e  mov     [rcx+1Ah], al
0x14000c6a1  mov     [rbx], r12
0x14000c6a4  mov     rax, [rdx+88h]
0x14000c6ab  mov     [rcx+28h], rax
0x14000c6af  mov     rax, [rdx+90h]
0x14000c6b6  mov     [rcx+30h], rax
0x14000c6ba  mov     [rsi], r12
0x14000c6bd  mov     rcx, [rdx+18h]; this
0x14000c6c1  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x14000c6c6  mov     rcx, [r14+38h]; this
0x14000c6ca  mov     r15, rax
0x14000c6cd  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x14000c6d2  mov     rcx, [r14+80h]; this
0x14000c6d9  add     r15, rax
0x14000c6dc  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x14000c6e1  add     r15, rax
0x14000c6e4  lea     rdi, [rbp+48h]
0x14000c6e8  cmp     [rbp+40h], r12
0x14000c6ec  jz      short loc_14000C6F3
0x14000c6ee  cmp     [rdi], r15
0x14000c6f1  jnb     short loc_14000C72E
0x14000c6f3  mov     rdx, r15; dwBytes
0x14000c6f6  mov     ecx, 8; dwFlags
0x14000c6fb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000c700  mov     r12, rax
0x14000c703  test    rax, rax
0x14000c706  jz      short loc_14000C72B
0x14000c708  mov     rbx, [rbp+40h]
0x14000c70c  call    cs:__imp_GetProcessHeap
0x14000c712  mov     r8, rbx; lpMem
0x14000c715  xor     edx, edx; dwFlags
0x14000c717  mov     rcx, rax; hHeap
0x14000c71a  call    cs:__imp_HeapFree
0x14000c720  mov     [rbp+40h], r12
0x14000c724  lea     rbx, [rbp+20h]
0x14000c728  mov     [rdi], r15
0x14000c72b  xor     r12d, r12d
0x14000c72e  mov     rcx, [rbp+40h]; Destination
0x14000c732  test    rcx, rcx
0x14000c735  jz      loc_14000C7C3
0x14000c73b  mov     rdi, [rdi]
0x14000c73e  lea     r9, [rbp+10h]
0x14000c742  mov     r8, [r14+38h]
0x14000c746  add     rdi, rcx
0x14000c749  mov     rdx, rdi
0x14000c74c  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14000c751  mov     r8, [r14+80h]
0x14000c758  mov     r9, rbx
0x14000c75b  mov     rdx, rdi
0x14000c75e  mov     rcx, rax; Destination
0x14000c761  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14000c766  mov     rbx, rax
0x14000c769  cmp     rax, rdi
0x14000c76c  jz      short loc_14000C7AB
0x14000c76e  mov     rcx, [r14+18h]; this
0x14000c772  test    rcx, rcx
0x14000c775  jz      short loc_14000C7AB
0x14000c777  cmp     [rcx], r12w
0x14000c77b  jz      short loc_14000C7AB
0x14000c77d  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x14000c782  mov     rdx, rdi
0x14000c785  mov     r14, rax
0x14000c788  sub     rdx, rbx; DestinationSize
0x14000c78b  cmp     rdx, rax
0x14000c78e  jb      short loc_14000C7AB
0x14000c790  mov     r8, rcx; Source
0x14000c793  mov     r9, rax; SourceSize
0x14000c796  mov     rcx, rbx; Destination
0x14000c799  call    memcpy_s
0x14000c79e  test    rsi, rsi
0x14000c7a1  jz      short loc_14000C7A6
0x14000c7a3  mov     [rsi], rbx
0x14000c7a6  add     rbx, r14
0x14000c7a9  jmp     short loc_14000C7B3
0x14000c7ab  test    rsi, rsi
0x14000c7ae  jz      short loc_14000C7B3
0x14000c7b0  mov     [rsi], r12
0x14000c7b3  sub     rdi, rbx
0x14000c7b6  xor     edx, edx; Val
0x14000c7b8  mov     r8, rdi; Size
0x14000c7bb  mov     rcx, rbx; void *
0x14000c7be  call    memset_0
0x14000c7c3  add     rsp, 28h
0x14000c7c7  pop     r15
0x14000c7c9  pop     r14
0x14000c7cb  pop     r13
0x14000c7cd  pop     r12
0x14000c7cf  pop     rdi
0x14000c7d0  pop     rsi
0x14000c7d1  pop     rbp
0x14000c7d2  pop     rbx
0x14000c7d3  retn
```
