# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800094b0`
- end: `0x1800095e6`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180009940`

## callees

- `0x180002878`
- `0x18000366c`
- `0x1800036e4`
- `0x180007b48`
- `0x180009328`
- `0x180009348`
- `0x1800094b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000956d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000956d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000955f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000955f`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  unsigned __int64 v5; // rbp
  const char *v6; // rdx
  unsigned __int64 v7; // rbp
  const char *v8; // rdx
  SIZE_T v9; // rbp
  SIZE_T *v10; // rdi
  LPVOID v11; // r14
  void *v12; // rbx
  HANDLE ProcessHeap; // rax
  char *v14; // rcx
  char *v15; // rbx
  void *v16; // rax
  void *v17; // rax
  void *v18; // rax

  *((_DWORD *)this + 1) = a3;
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v5 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const unsigned __int16 *)a2);
  v7 = wil::details::ResultStringSize(*((wil::details **)a2 + 7), v6) + v5;
  v9 = wil::details::ResultStringSize(*((wil::details **)a2 + 16), v8) + v7;
  v10 = (SIZE_T *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v10 < v9 )
  {
    v11 = wil::details::ProcessHeapAlloc(8u, v9);
    if ( v11 )
    {
      v12 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v12);
      *((_QWORD *)this + 8) = v11;
      *v10 = v9;
    }
  }
  v14 = (char *)*((_QWORD *)this + 8);
  if ( v14 )
  {
    v15 = &v14[*v10];
    v16 = (void *)wil::details::WriteResultString<char const *>(v14);
    v17 = (void *)wil::details::WriteResultString<char const *>(v16);
    v18 = (void *)wil::details::WriteResultString<unsigned short const *>(v17);
    memset_0(v18, 0, v15 - (_BYTE *)v18);
  }
}

```

## disassembly

```asm
0x1800094b0  push    rbx
0x1800094b2  push    rbp
0x1800094b3  push    rsi
0x1800094b4  push    rdi
0x1800094b5  push    r12
0x1800094b7  push    r13
0x1800094b9  push    r14
0x1800094bb  push    r15
0x1800094bd  sub     rsp, 28h
0x1800094c1  mov     [rcx+4], r8d
0x1800094c5  lea     r14, [rcx+38h]
0x1800094c9  mov     eax, [rdx+8]
0x1800094cc  mov     rsi, rcx
0x1800094cf  mov     [rcx+8], eax
0x1800094d2  mov     r15, rdx
0x1800094d5  mov     qword ptr [rcx+10h], 0
0x1800094dd  movzx   eax, word ptr [rdx+40h]
0x1800094e1  mov     [rcx+18h], ax
0x1800094e5  mov     al, [rdx]
0x1800094e7  mov     [rcx+1Ah], al
0x1800094ea  mov     qword ptr [rcx+20h], 0
0x1800094f2  mov     rax, [rdx+88h]
0x1800094f9  mov     [rcx+28h], rax
0x1800094fd  mov     rax, [rdx+90h]
0x180009504  mov     [rcx+30h], rax
0x180009508  mov     qword ptr [r14], 0
0x18000950f  mov     rcx, [rdx+18h]; this
0x180009513  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180009518  mov     rcx, [r15+38h]; this
0x18000951c  mov     rbp, rax
0x18000951f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180009524  mov     rcx, [r15+80h]; this
0x18000952b  add     rbp, rax
0x18000952e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180009533  add     rbp, rax
0x180009536  lea     rdi, [rsi+48h]
0x18000953a  cmp     qword ptr [rsi+40h], 0
0x18000953f  jz      short loc_180009546
0x180009541  cmp     [rdi], rbp
0x180009544  jnb     short loc_18000957E
0x180009546  mov     rdx, rbp; dwBytes
0x180009549  mov     ecx, 8; dwFlags
0x18000954e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009553  mov     r14, rax
0x180009556  test    rax, rax
0x180009559  jz      short loc_18000957A
0x18000955b  mov     rbx, [rsi+40h]
0x18000955f  call    cs:__imp_GetProcessHeap
0x180009565  mov     r8, rbx; lpMem
0x180009568  xor     edx, edx; dwFlags
0x18000956a  mov     rcx, rax; hHeap
0x18000956d  call    cs:__imp_HeapFree
0x180009573  mov     [rsi+40h], r14
0x180009577  mov     [rdi], rbp
0x18000957a  lea     r14, [rsi+38h]
0x18000957e  mov     rcx, [rsi+40h]; Destination
0x180009582  test    rcx, rcx
0x180009585  jz      short loc_1800095D5
0x180009587  mov     rbx, [rdi]
0x18000958a  lea     r9, [rsi+10h]
0x18000958e  mov     r8, [r15+38h]
0x180009592  add     rbx, rcx
0x180009595  mov     rdx, rbx
0x180009598  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000959d  mov     r8, [r15+80h]
0x1800095a4  lea     r9, [rsi+20h]
0x1800095a8  mov     rdx, rbx
0x1800095ab  mov     rcx, rax; Destination
0x1800095ae  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800095b3  mov     r8, [r15+18h]
0x1800095b7  mov     r9, r14
0x1800095ba  mov     rdx, rbx
0x1800095bd  mov     rcx, rax; Destination
0x1800095c0  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x1800095c5  sub     rbx, rax
0x1800095c8  xor     edx, edx; Val
0x1800095ca  mov     r8, rbx; Size
0x1800095cd  mov     rcx, rax; void *
0x1800095d0  call    memset_0
0x1800095d5  add     rsp, 28h
0x1800095d9  pop     r15
0x1800095db  pop     r14
0x1800095dd  pop     r13
0x1800095df  pop     r12
0x1800095e1  pop     rdi
0x1800095e2  pop     rsi
0x1800095e3  pop     rbp
0x1800095e4  pop     rbx
0x1800095e5  retn
```
