# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800088a4`
- end: `0x1800089e7`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `323`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180008d48`

## callees

- `0x180003eec`
- `0x180003f6c`
- `0x180007494`
- `0x1800086f8`
- `0x18000871c`
- `0x1800088a4`
- `0x180028832`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008967`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008967`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008953`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008953`

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
0x1800088a4  push    rbx
0x1800088a6  push    rbp
0x1800088a7  push    rsi
0x1800088a8  push    rdi
0x1800088a9  push    r12
0x1800088ab  push    r13
0x1800088ad  push    r14
0x1800088af  push    r15
0x1800088b1  sub     rsp, 28h
0x1800088b5  mov     [rcx+4], r8d
0x1800088b9  lea     r14, [rcx+38h]
0x1800088bd  mov     eax, [rdx+8]
0x1800088c0  mov     rsi, rcx
0x1800088c3  mov     [rcx+8], eax
0x1800088c6  mov     r15, rdx
0x1800088c9  mov     qword ptr [rcx+10h], 0
0x1800088d1  movzx   eax, word ptr [rdx+40h]
0x1800088d5  mov     [rcx+18h], ax
0x1800088d9  mov     al, [rdx]
0x1800088db  mov     [rcx+1Ah], al
0x1800088de  mov     qword ptr [rcx+20h], 0
0x1800088e6  mov     rax, [rdx+88h]
0x1800088ed  mov     [rcx+28h], rax
0x1800088f1  mov     rax, [rdx+90h]
0x1800088f8  mov     [rcx+30h], rax
0x1800088fc  mov     qword ptr [r14], 0
0x180008903  mov     rcx, [rdx+18h]; this
0x180008907  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000890c  mov     rcx, [r15+38h]; this
0x180008910  mov     rbp, rax
0x180008913  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180008918  mov     rcx, [r15+80h]; this
0x18000891f  add     rbp, rax
0x180008922  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180008927  add     rbp, rax
0x18000892a  lea     rdi, [rsi+48h]
0x18000892e  cmp     qword ptr [rsi+40h], 0
0x180008933  jz      short loc_18000893A
0x180008935  cmp     [rdi], rbp
0x180008938  jnb     short loc_18000897E
0x18000893a  mov     rdx, rbp; dwBytes
0x18000893d  mov     ecx, 8; dwFlags
0x180008942  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008947  mov     r14, rax
0x18000894a  test    rax, rax
0x18000894d  jz      short loc_18000897A
0x18000894f  mov     rbx, [rsi+40h]
0x180008953  call    cs:__imp_GetProcessHeap
0x18000895a  nop     dword ptr [rax+rax+00h]
0x18000895f  mov     r8, rbx; lpMem
0x180008962  xor     edx, edx; dwFlags
0x180008964  mov     rcx, rax; hHeap
0x180008967  call    cs:__imp_HeapFree
0x18000896e  nop     dword ptr [rax+rax+00h]
0x180008973  mov     [rsi+40h], r14
0x180008977  mov     [rdi], rbp
0x18000897a  lea     r14, [rsi+38h]
0x18000897e  mov     rcx, [rsi+40h]; Destination
0x180008982  test    rcx, rcx
0x180008985  jz      short loc_1800089D5
0x180008987  mov     rbx, [rdi]
0x18000898a  lea     r9, [rsi+10h]
0x18000898e  mov     r8, [r15+38h]
0x180008992  add     rbx, rcx
0x180008995  mov     rdx, rbx
0x180008998  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000899d  mov     r8, [r15+80h]
0x1800089a4  lea     r9, [rsi+20h]
0x1800089a8  mov     rdx, rbx
0x1800089ab  mov     rcx, rax; Destination
0x1800089ae  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800089b3  mov     r8, [r15+18h]
0x1800089b7  mov     r9, r14
0x1800089ba  mov     rdx, rbx
0x1800089bd  mov     rcx, rax; Destination
0x1800089c0  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x1800089c5  sub     rbx, rax
0x1800089c8  xor     edx, edx; Val
0x1800089ca  mov     r8, rbx; Size
0x1800089cd  mov     rcx, rax; void *
0x1800089d0  call    memset_0
0x1800089d5  add     rsp, 28h
0x1800089d9  pop     r15
0x1800089db  pop     r14
0x1800089dd  pop     r13
0x1800089df  pop     r12
0x1800089e1  pop     rdi
0x1800089e2  pop     rsi
0x1800089e3  pop     rbp
0x1800089e4  pop     rbx
0x1800089e5  retn
```
