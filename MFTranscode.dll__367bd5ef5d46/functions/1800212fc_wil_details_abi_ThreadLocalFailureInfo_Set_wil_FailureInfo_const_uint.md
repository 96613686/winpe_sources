# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800212fc`
- end: `0x18002146c`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `368`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180021594`

## callees

- `0x180017de4`
- `0x180017e20`
- `0x18001c970`
- `0x180020ee0`
- `0x180021250`
- `0x180021270`
- `0x1800212fc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800213b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800213b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800213a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800213a4`

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
0x1800212fc  push    rbx
0x1800212fe  push    rbp
0x1800212ff  push    rsi
0x180021300  push    rdi
0x180021301  push    r12
0x180021303  push    r13
0x180021305  push    r14
0x180021307  push    r15
0x180021309  sub     rsp, 28h
0x18002130d  mov     [rcx+4], r8d
0x180021311  lea     rbx, [rcx+20h]
0x180021315  mov     eax, [rdx+8]
0x180021318  lea     rsi, [rcx+38h]
0x18002131c  mov     [rcx+8], eax
0x18002131f  xor     r12d, r12d
0x180021322  mov     [rcx+10h], r12
0x180021326  mov     rbp, rcx
0x180021329  movzx   eax, word ptr [rdx+40h]
0x18002132d  mov     r14, rdx
0x180021330  mov     [rcx+18h], ax
0x180021334  mov     al, [rdx]
0x180021336  mov     [rcx+1Ah], al
0x180021339  mov     [rbx], r12
0x18002133c  mov     rax, [rdx+88h]
0x180021343  mov     [rcx+28h], rax
0x180021347  mov     rax, [rdx+90h]
0x18002134e  mov     [rcx+30h], rax
0x180021352  mov     [rsi], r12
0x180021355  mov     rcx, [rdx+18h]; this
0x180021359  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18002135e  mov     rcx, [r14+38h]; this
0x180021362  mov     r15, rax
0x180021365  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18002136a  mov     rcx, [r14+80h]; this
0x180021371  add     r15, rax
0x180021374  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180021379  add     r15, rax
0x18002137c  lea     rdi, [rbp+48h]
0x180021380  cmp     [rbp+40h], r12
0x180021384  jz      short loc_18002138B
0x180021386  cmp     [rdi], r15
0x180021389  jnb     short loc_1800213C6
0x18002138b  mov     rdx, r15; dwBytes
0x18002138e  mov     ecx, 8; dwFlags
0x180021393  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180021398  mov     r12, rax
0x18002139b  test    rax, rax
0x18002139e  jz      short loc_1800213C3
0x1800213a0  mov     rbx, [rbp+40h]
0x1800213a4  call    cs:__imp_GetProcessHeap
0x1800213aa  mov     r8, rbx; lpMem
0x1800213ad  xor     edx, edx; dwFlags
0x1800213af  mov     rcx, rax; hHeap
0x1800213b2  call    cs:__imp_HeapFree
0x1800213b8  mov     [rbp+40h], r12
0x1800213bc  lea     rbx, [rbp+20h]
0x1800213c0  mov     [rdi], r15
0x1800213c3  xor     r12d, r12d
0x1800213c6  mov     rcx, [rbp+40h]; Destination
0x1800213ca  test    rcx, rcx
0x1800213cd  jz      loc_18002145B
0x1800213d3  mov     rdi, [rdi]
0x1800213d6  lea     r9, [rbp+10h]
0x1800213da  mov     r8, [r14+38h]
0x1800213de  add     rdi, rcx
0x1800213e1  mov     rdx, rdi
0x1800213e4  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800213e9  mov     r8, [r14+80h]
0x1800213f0  mov     r9, rbx
0x1800213f3  mov     rdx, rdi
0x1800213f6  mov     rcx, rax; Destination
0x1800213f9  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800213fe  mov     rbx, rax
0x180021401  cmp     rax, rdi
0x180021404  jz      short loc_180021443
0x180021406  mov     rcx, [r14+18h]; this
0x18002140a  test    rcx, rcx
0x18002140d  jz      short loc_180021443
0x18002140f  cmp     [rcx], r12w
0x180021413  jz      short loc_180021443
0x180021415  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18002141a  mov     rdx, rdi
0x18002141d  mov     r14, rax
0x180021420  sub     rdx, rbx; DestinationSize
0x180021423  cmp     rdx, rax
0x180021426  jb      short loc_180021443
0x180021428  mov     r8, rcx; Source
0x18002142b  mov     r9, rax; SourceSize
0x18002142e  mov     rcx, rbx; Destination
0x180021431  call    memcpy_s
0x180021436  test    rsi, rsi
0x180021439  jz      short loc_18002143E
0x18002143b  mov     [rsi], rbx
0x18002143e  add     rbx, r14
0x180021441  jmp     short loc_18002144B
0x180021443  test    rsi, rsi
0x180021446  jz      short loc_18002144B
0x180021448  mov     [rsi], r12
0x18002144b  sub     rdi, rbx
0x18002144e  xor     edx, edx; Val
0x180021450  mov     r8, rdi; Size
0x180021453  mov     rcx, rbx; void *
0x180021456  call    memset_0
0x18002145b  add     rsp, 28h
0x18002145f  pop     r15
0x180021461  pop     r14
0x180021463  pop     r13
0x180021465  pop     r12
0x180021467  pop     rdi
0x180021468  pop     rsi
0x180021469  pop     rbp
0x18002146a  pop     rbx
0x18002146b  retn
```
