# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800247f0`
- end: `0x180024926`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180024a18`

## callees

- `0x1800187f8`
- `0x18001ee30`
- `0x18001f018`
- `0x180021cec`
- `0x180022960`
- `0x1800229d8`
- `0x1800247f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002489f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002489f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800248ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800248ad`

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
0x1800247f0  push    rbx
0x1800247f2  push    rbp
0x1800247f3  push    rsi
0x1800247f4  push    rdi
0x1800247f5  push    r12
0x1800247f7  push    r13
0x1800247f9  push    r14
0x1800247fb  push    r15
0x1800247fd  sub     rsp, 28h
0x180024801  mov     [rcx+4], r8d
0x180024805  lea     r14, [rcx+38h]
0x180024809  mov     eax, [rdx+8]
0x18002480c  mov     rsi, rcx
0x18002480f  mov     [rcx+8], eax
0x180024812  mov     r15, rdx
0x180024815  mov     qword ptr [rcx+10h], 0
0x18002481d  movzx   eax, word ptr [rdx+40h]
0x180024821  mov     [rcx+18h], ax
0x180024825  mov     al, [rdx]
0x180024827  mov     [rcx+1Ah], al
0x18002482a  mov     qword ptr [rcx+20h], 0
0x180024832  mov     rax, [rdx+88h]
0x180024839  mov     [rcx+28h], rax
0x18002483d  mov     rax, [rdx+90h]
0x180024844  mov     [rcx+30h], rax
0x180024848  mov     qword ptr [r14], 0
0x18002484f  mov     rcx, [rdx+18h]; this
0x180024853  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180024858  mov     rcx, [r15+38h]; this
0x18002485c  mov     rbp, rax
0x18002485f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180024864  mov     rcx, [r15+80h]; this
0x18002486b  add     rbp, rax
0x18002486e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180024873  add     rbp, rax
0x180024876  lea     rdi, [rsi+48h]
0x18002487a  cmp     qword ptr [rsi+40h], 0
0x18002487f  jz      short loc_180024886
0x180024881  cmp     [rdi], rbp
0x180024884  jnb     short loc_1800248BE
0x180024886  mov     rdx, rbp; dwBytes
0x180024889  mov     ecx, 8; dwFlags
0x18002488e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180024893  mov     r14, rax
0x180024896  test    rax, rax
0x180024899  jz      short loc_1800248BA
0x18002489b  mov     rbx, [rsi+40h]
0x18002489f  call    cs:__imp_GetProcessHeap
0x1800248a5  mov     r8, rbx; lpMem
0x1800248a8  xor     edx, edx; dwFlags
0x1800248aa  mov     rcx, rax; hHeap
0x1800248ad  call    cs:__imp_HeapFree
0x1800248b3  mov     [rsi+40h], r14
0x1800248b7  mov     [rdi], rbp
0x1800248ba  lea     r14, [rsi+38h]
0x1800248be  mov     rcx, [rsi+40h]; Destination
0x1800248c2  test    rcx, rcx
0x1800248c5  jz      short loc_180024915
0x1800248c7  mov     rbx, [rdi]
0x1800248ca  lea     r9, [rsi+10h]
0x1800248ce  mov     r8, [r15+38h]
0x1800248d2  add     rbx, rcx
0x1800248d5  mov     rdx, rbx
0x1800248d8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800248dd  mov     r8, [r15+80h]
0x1800248e4  lea     r9, [rsi+20h]
0x1800248e8  mov     rdx, rbx
0x1800248eb  mov     rcx, rax; Destination
0x1800248ee  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800248f3  mov     r8, [r15+18h]
0x1800248f7  mov     r9, r14
0x1800248fa  mov     rdx, rbx
0x1800248fd  mov     rcx, rax; Destination
0x180024900  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180024905  sub     rbx, rax
0x180024908  xor     edx, edx; Val
0x18002490a  mov     r8, rbx; Size
0x18002490d  mov     rcx, rax; void *
0x180024910  call    memset_0
0x180024915  add     rsp, 28h
0x180024919  pop     r15
0x18002491b  pop     r14
0x18002491d  pop     r13
0x18002491f  pop     r12
0x180024921  pop     rdi
0x180024922  pop     rsi
0x180024923  pop     rbp
0x180024924  pop     rbx
0x180024925  retn
```
