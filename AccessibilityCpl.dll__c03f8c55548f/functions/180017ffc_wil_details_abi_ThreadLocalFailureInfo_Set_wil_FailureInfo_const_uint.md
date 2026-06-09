# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180017ffc`
- end: `0x18001816d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `369`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001844c`

## callees

- `0x180004258`
- `0x1800148ec`
- `0x180015b70`
- `0x180015b90`
- `0x180017ffc`
- `0x18002d1ee`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180018131`
- `msvcrt!memcpy_s` at `0x180018131`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800180b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800180b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800180a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800180a4`

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
0x180017ffc  push    rbx
0x180017ffe  push    rbp
0x180017fff  push    rsi
0x180018000  push    rdi
0x180018001  push    r12
0x180018003  push    r13
0x180018005  push    r14
0x180018007  push    r15
0x180018009  sub     rsp, 28h
0x18001800d  mov     [rcx+4], r8d
0x180018011  lea     rbx, [rcx+20h]
0x180018015  mov     eax, [rdx+8]
0x180018018  lea     rsi, [rcx+38h]
0x18001801c  mov     [rcx+8], eax
0x18001801f  xor     r12d, r12d
0x180018022  mov     [rcx+10h], r12
0x180018026  mov     rbp, rcx
0x180018029  movzx   eax, word ptr [rdx+40h]
0x18001802d  mov     r14, rdx
0x180018030  mov     [rcx+18h], ax
0x180018034  mov     al, [rdx]
0x180018036  mov     [rcx+1Ah], al
0x180018039  mov     [rbx], r12
0x18001803c  mov     rax, [rdx+88h]
0x180018043  mov     [rcx+28h], rax
0x180018047  mov     rax, [rdx+90h]
0x18001804e  mov     [rcx+30h], rax
0x180018052  mov     [rsi], r12
0x180018055  mov     rcx, [rdx+18h]; this
0x180018059  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18001805e  mov     rcx, [r14+38h]; this
0x180018062  mov     r15, rax
0x180018065  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18001806a  mov     rcx, [r14+80h]; this
0x180018071  add     r15, rax
0x180018074  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180018079  add     r15, rax
0x18001807c  lea     rdi, [rbp+48h]
0x180018080  cmp     [rbp+40h], r12
0x180018084  jz      short loc_18001808B
0x180018086  cmp     [rdi], r15
0x180018089  jnb     short loc_1800180C6
0x18001808b  mov     rdx, r15; dwBytes
0x18001808e  mov     ecx, 8; dwFlags
0x180018093  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180018098  mov     r12, rax
0x18001809b  test    rax, rax
0x18001809e  jz      short loc_1800180C3
0x1800180a0  mov     rbx, [rbp+40h]
0x1800180a4  call    cs:__imp_GetProcessHeap
0x1800180aa  mov     r8, rbx; lpMem
0x1800180ad  xor     edx, edx; dwFlags
0x1800180af  mov     rcx, rax; hHeap
0x1800180b2  call    cs:__imp_HeapFree
0x1800180b8  mov     [rbp+40h], r12
0x1800180bc  lea     rbx, [rbp+20h]
0x1800180c0  mov     [rdi], r15
0x1800180c3  xor     r12d, r12d
0x1800180c6  mov     rcx, [rbp+40h]; Destination
0x1800180ca  test    rcx, rcx
0x1800180cd  jz      loc_18001815C
0x1800180d3  mov     rdi, [rdi]
0x1800180d6  lea     r9, [rbp+10h]
0x1800180da  mov     r8, [r14+38h]
0x1800180de  add     rdi, rcx
0x1800180e1  mov     rdx, rdi
0x1800180e4  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800180e9  mov     r8, [r14+80h]
0x1800180f0  mov     r9, rbx
0x1800180f3  mov     rdx, rdi
0x1800180f6  mov     rcx, rax; Destination
0x1800180f9  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800180fe  mov     rbx, rax
0x180018101  cmp     rax, rdi
0x180018104  jz      short loc_180018144
0x180018106  mov     rcx, [r14+18h]; this
0x18001810a  test    rcx, rcx
0x18001810d  jz      short loc_180018144
0x18001810f  cmp     [rcx], r12w
0x180018113  jz      short loc_180018144
0x180018115  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18001811a  mov     rdx, rdi
0x18001811d  mov     r14, rax
0x180018120  sub     rdx, rbx; DestinationSize
0x180018123  cmp     rdx, rax
0x180018126  jb      short loc_180018144
0x180018128  mov     r8, rcx; Source
0x18001812b  mov     r9, rax; SourceSize
0x18001812e  mov     rcx, rbx; Destination
0x180018131  call    cs:__imp_memcpy_s
0x180018137  test    rsi, rsi
0x18001813a  jz      short loc_18001813F
0x18001813c  mov     [rsi], rbx
0x18001813f  add     rbx, r14
0x180018142  jmp     short loc_18001814C
0x180018144  test    rsi, rsi
0x180018147  jz      short loc_18001814C
0x180018149  mov     [rsi], r12
0x18001814c  sub     rdi, rbx
0x18001814f  xor     edx, edx; Val
0x180018151  mov     r8, rdi; Size
0x180018154  mov     rcx, rbx; void *
0x180018157  call    memset_0
0x18001815c  add     rsp, 28h
0x180018160  pop     r15
0x180018162  pop     r14
0x180018164  pop     r13
0x180018166  pop     r12
0x180018168  pop     rdi
0x180018169  pop     rsi
0x18001816a  pop     rbp
0x18001816b  pop     rbx
0x18001816c  retn
```
