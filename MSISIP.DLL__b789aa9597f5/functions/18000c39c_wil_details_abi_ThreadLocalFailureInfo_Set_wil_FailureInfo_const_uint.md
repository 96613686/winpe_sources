# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000c39c`
- end: `0x18000c4d2`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000c734`

## callees

- `0x1800056d0`
- `0x1800059f0`
- `0x18000ab50`
- `0x18000abc8`
- `0x18000bd24`
- `0x18000c39c`
- `0x18000d2ce`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c44b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c44b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c459`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c459`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  __int64 v4; // rdx
  unsigned __int64 v5; // rbp
  __int64 v6; // rdx
  unsigned __int64 v7; // rbp
  SIZE_T v8; // rbp
  SIZE_T *v9; // rdi
  LPVOID v10; // r14
  void *v11; // rbx
  HANDLE ProcessHeap; // rax
  char *v13; // rcx
  char *v14; // rbx
  void *v15; // rax
  void *v16; // rax
  void *v17; // rax

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
  v7 = wil::details::ResultStringSize(*(wil::details **)(v4 + 56), (const char *)v4) + v5;
  v8 = wil::details::ResultStringSize(*(wil::details **)(v6 + 128), (const char *)v6) + v7;
  v9 = (SIZE_T *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v9 < v8 )
  {
    v10 = wil::details::ProcessHeapAlloc(8u, v8);
    if ( v10 )
    {
      v11 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v11);
      *((_QWORD *)this + 8) = v10;
      *v9 = v8;
    }
  }
  v13 = (char *)*((_QWORD *)this + 8);
  if ( v13 )
  {
    v14 = &v13[*v9];
    v15 = (void *)wil::details::WriteResultString<char const *>(v13);
    v16 = (void *)wil::details::WriteResultString<char const *>(v15);
    v17 = (void *)wil::details::WriteResultString<unsigned short const *>(v16);
    memset_0(v17, 0, v14 - (_BYTE *)v17);
  }
}

```

## disassembly

```asm
0x18000c39c  push    rbx
0x18000c39e  push    rbp
0x18000c39f  push    rsi
0x18000c3a0  push    rdi
0x18000c3a1  push    r12
0x18000c3a3  push    r13
0x18000c3a5  push    r14
0x18000c3a7  push    r15
0x18000c3a9  sub     rsp, 28h
0x18000c3ad  mov     [rcx+4], r8d
0x18000c3b1  lea     r14, [rcx+38h]
0x18000c3b5  mov     eax, [rdx+8]
0x18000c3b8  mov     rsi, rcx
0x18000c3bb  mov     [rcx+8], eax
0x18000c3be  mov     r15, rdx
0x18000c3c1  mov     qword ptr [rcx+10h], 0
0x18000c3c9  movzx   eax, word ptr [rdx+40h]
0x18000c3cd  mov     [rcx+18h], ax
0x18000c3d1  mov     al, [rdx]
0x18000c3d3  mov     [rcx+1Ah], al
0x18000c3d6  mov     qword ptr [rcx+20h], 0
0x18000c3de  mov     rax, [rdx+88h]
0x18000c3e5  mov     [rcx+28h], rax
0x18000c3e9  mov     rax, [rdx+90h]
0x18000c3f0  mov     [rcx+30h], rax
0x18000c3f4  mov     qword ptr [r14], 0
0x18000c3fb  mov     rcx, [rdx+18h]; this
0x18000c3ff  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000c404  mov     rcx, [rdx+38h]; this
0x18000c408  mov     rbp, rax
0x18000c40b  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000c410  mov     rcx, [rdx+80h]; this
0x18000c417  add     rbp, rax
0x18000c41a  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000c41f  add     rbp, rax
0x18000c422  lea     rdi, [rsi+48h]
0x18000c426  cmp     qword ptr [rsi+40h], 0
0x18000c42b  jz      short loc_18000C432
0x18000c42d  cmp     [rdi], rbp
0x18000c430  jnb     short loc_18000C46A
0x18000c432  mov     rdx, rbp; dwBytes
0x18000c435  mov     ecx, 8; dwFlags
0x18000c43a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000c43f  mov     r14, rax
0x18000c442  test    rax, rax
0x18000c445  jz      short loc_18000C466
0x18000c447  mov     rbx, [rsi+40h]
0x18000c44b  call    cs:__imp_GetProcessHeap
0x18000c451  mov     r8, rbx; lpMem
0x18000c454  xor     edx, edx; dwFlags
0x18000c456  mov     rcx, rax; hHeap
0x18000c459  call    cs:__imp_HeapFree
0x18000c45f  mov     [rsi+40h], r14
0x18000c463  mov     [rdi], rbp
0x18000c466  lea     r14, [rsi+38h]
0x18000c46a  mov     rcx, [rsi+40h]; Destination
0x18000c46e  test    rcx, rcx
0x18000c471  jz      short loc_18000C4C1
0x18000c473  mov     rbx, [rdi]
0x18000c476  lea     r9, [rsi+10h]
0x18000c47a  mov     r8, [r15+38h]
0x18000c47e  add     rbx, rcx
0x18000c481  mov     rdx, rbx
0x18000c484  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000c489  mov     r8, [r15+80h]
0x18000c490  lea     r9, [rsi+20h]
0x18000c494  mov     rdx, rbx
0x18000c497  mov     rcx, rax; Destination
0x18000c49a  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000c49f  mov     r8, [r15+18h]
0x18000c4a3  mov     r9, r14
0x18000c4a6  mov     rdx, rbx
0x18000c4a9  mov     rcx, rax; Destination
0x18000c4ac  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18000c4b1  sub     rbx, rax
0x18000c4b4  xor     edx, edx; Val
0x18000c4b6  mov     r8, rbx; Size
0x18000c4b9  mov     rcx, rax; void *
0x18000c4bc  call    memset_0
0x18000c4c1  add     rsp, 28h
0x18000c4c5  pop     r15
0x18000c4c7  pop     r14
0x18000c4c9  pop     r13
0x18000c4cb  pop     r12
0x18000c4cd  pop     rdi
0x18000c4ce  pop     rsi
0x18000c4cf  pop     rbp
0x18000c4d0  pop     rbx
0x18000c4d1  retn
```
