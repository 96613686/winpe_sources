# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000f650`
- end: `0x18000f793`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `323`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000f94c`

## callees

- `0x1800026d8`
- `0x180003630`
- `0x1800036a8`
- `0x180004cf8`
- `0x180004d1c`
- `0x18000b8b4`
- `0x18000f650`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f713`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f713`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f6ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f6ff`

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
0x18000f650  push    rbx
0x18000f652  push    rbp
0x18000f653  push    rsi
0x18000f654  push    rdi
0x18000f655  push    r12
0x18000f657  push    r13
0x18000f659  push    r14
0x18000f65b  push    r15
0x18000f65d  sub     rsp, 28h
0x18000f661  mov     [rcx+4], r8d
0x18000f665  lea     r14, [rcx+38h]
0x18000f669  mov     eax, [rdx+8]
0x18000f66c  mov     rsi, rcx
0x18000f66f  mov     [rcx+8], eax
0x18000f672  mov     r15, rdx
0x18000f675  mov     qword ptr [rcx+10h], 0
0x18000f67d  movzx   eax, word ptr [rdx+40h]
0x18000f681  mov     [rcx+18h], ax
0x18000f685  mov     al, [rdx]
0x18000f687  mov     [rcx+1Ah], al
0x18000f68a  mov     qword ptr [rcx+20h], 0
0x18000f692  mov     rax, [rdx+88h]
0x18000f699  mov     [rcx+28h], rax
0x18000f69d  mov     rax, [rdx+90h]
0x18000f6a4  mov     [rcx+30h], rax
0x18000f6a8  mov     qword ptr [r14], 0
0x18000f6af  mov     rcx, [rdx+18h]; this
0x18000f6b3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000f6b8  mov     rcx, [r15+38h]; this
0x18000f6bc  mov     rbp, rax
0x18000f6bf  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000f6c4  mov     rcx, [r15+80h]; this
0x18000f6cb  add     rbp, rax
0x18000f6ce  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000f6d3  add     rbp, rax
0x18000f6d6  lea     rdi, [rsi+48h]
0x18000f6da  cmp     qword ptr [rsi+40h], 0
0x18000f6df  jz      short loc_18000F6E6
0x18000f6e1  cmp     [rdi], rbp
0x18000f6e4  jnb     short loc_18000F72A
0x18000f6e6  mov     rdx, rbp; dwBytes
0x18000f6e9  mov     ecx, 8; dwFlags
0x18000f6ee  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000f6f3  mov     r14, rax
0x18000f6f6  test    rax, rax
0x18000f6f9  jz      short loc_18000F726
0x18000f6fb  mov     rbx, [rsi+40h]
0x18000f6ff  call    cs:__imp_GetProcessHeap
0x18000f706  nop     dword ptr [rax+rax+00h]
0x18000f70b  mov     r8, rbx; lpMem
0x18000f70e  xor     edx, edx; dwFlags
0x18000f710  mov     rcx, rax; hHeap
0x18000f713  call    cs:__imp_HeapFree
0x18000f71a  nop     dword ptr [rax+rax+00h]
0x18000f71f  mov     [rsi+40h], r14
0x18000f723  mov     [rdi], rbp
0x18000f726  lea     r14, [rsi+38h]
0x18000f72a  mov     rcx, [rsi+40h]; Destination
0x18000f72e  test    rcx, rcx
0x18000f731  jz      short loc_18000F781
0x18000f733  mov     rbx, [rdi]
0x18000f736  lea     r9, [rsi+10h]
0x18000f73a  mov     r8, [r15+38h]
0x18000f73e  add     rbx, rcx
0x18000f741  mov     rdx, rbx
0x18000f744  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000f749  mov     r8, [r15+80h]
0x18000f750  lea     r9, [rsi+20h]
0x18000f754  mov     rdx, rbx
0x18000f757  mov     rcx, rax; Destination
0x18000f75a  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000f75f  mov     r8, [r15+18h]
0x18000f763  mov     r9, r14
0x18000f766  mov     rdx, rbx
0x18000f769  mov     rcx, rax; Destination
0x18000f76c  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18000f771  sub     rbx, rax
0x18000f774  xor     edx, edx; Val
0x18000f776  mov     r8, rbx; Size
0x18000f779  mov     rcx, rax; void *
0x18000f77c  call    memset_0
0x18000f781  add     rsp, 28h
0x18000f785  pop     r15
0x18000f787  pop     r14
0x18000f789  pop     r13
0x18000f78b  pop     r12
0x18000f78d  pop     rdi
0x18000f78e  pop     rsi
0x18000f78f  pop     rbp
0x18000f790  pop     rbx
0x18000f791  retn
```
