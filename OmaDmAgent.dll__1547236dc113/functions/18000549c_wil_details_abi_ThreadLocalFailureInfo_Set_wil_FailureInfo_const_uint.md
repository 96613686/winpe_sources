# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000549c`
- end: `0x1800055df`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `323`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180005850`

## callees

- `0x180002914`
- `0x180002994`
- `0x180004f80`
- `0x1800053a8`
- `0x1800053cc`
- `0x18000549c`
- `0x18001f3da`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000554b`
- `KERNEL32!GetProcessHeap` at `0x18000554b`
- `KERNEL32!HeapFree` at `0x18000555f`
- `KERNEL32!HeapFree` at `0x18000555f`

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
0x18000549c  push    rbx
0x18000549e  push    rbp
0x18000549f  push    rsi
0x1800054a0  push    rdi
0x1800054a1  push    r12
0x1800054a3  push    r13
0x1800054a5  push    r14
0x1800054a7  push    r15
0x1800054a9  sub     rsp, 28h
0x1800054ad  mov     [rcx+4], r8d
0x1800054b1  lea     r14, [rcx+38h]
0x1800054b5  mov     eax, [rdx+8]
0x1800054b8  mov     rsi, rcx
0x1800054bb  mov     [rcx+8], eax
0x1800054be  mov     r15, rdx
0x1800054c1  mov     qword ptr [rcx+10h], 0
0x1800054c9  movzx   eax, word ptr [rdx+40h]
0x1800054cd  mov     [rcx+18h], ax
0x1800054d1  mov     al, [rdx]
0x1800054d3  mov     [rcx+1Ah], al
0x1800054d6  mov     qword ptr [rcx+20h], 0
0x1800054de  mov     rax, [rdx+88h]
0x1800054e5  mov     [rcx+28h], rax
0x1800054e9  mov     rax, [rdx+90h]
0x1800054f0  mov     [rcx+30h], rax
0x1800054f4  mov     qword ptr [r14], 0
0x1800054fb  mov     rcx, [rdx+18h]; this
0x1800054ff  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180005504  mov     rcx, [r15+38h]; this
0x180005508  mov     rbp, rax
0x18000550b  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180005510  mov     rcx, [r15+80h]; this
0x180005517  add     rbp, rax
0x18000551a  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000551f  add     rbp, rax
0x180005522  lea     rdi, [rsi+48h]
0x180005526  cmp     qword ptr [rsi+40h], 0
0x18000552b  jz      short loc_180005532
0x18000552d  cmp     [rdi], rbp
0x180005530  jnb     short loc_180005576
0x180005532  mov     rdx, rbp; dwBytes
0x180005535  mov     ecx, 8; dwFlags
0x18000553a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000553f  mov     r14, rax
0x180005542  test    rax, rax
0x180005545  jz      short loc_180005572
0x180005547  mov     rbx, [rsi+40h]
0x18000554b  call    cs:__imp_GetProcessHeap
0x180005552  nop     dword ptr [rax+rax+00h]
0x180005557  mov     r8, rbx; lpMem
0x18000555a  xor     edx, edx; dwFlags
0x18000555c  mov     rcx, rax; hHeap
0x18000555f  call    cs:__imp_HeapFree
0x180005566  nop     dword ptr [rax+rax+00h]
0x18000556b  mov     [rsi+40h], r14
0x18000556f  mov     [rdi], rbp
0x180005572  lea     r14, [rsi+38h]
0x180005576  mov     rcx, [rsi+40h]; Destination
0x18000557a  test    rcx, rcx
0x18000557d  jz      short loc_1800055CD
0x18000557f  mov     rbx, [rdi]
0x180005582  lea     r9, [rsi+10h]
0x180005586  mov     r8, [r15+38h]
0x18000558a  add     rbx, rcx
0x18000558d  mov     rdx, rbx
0x180005590  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180005595  mov     r8, [r15+80h]
0x18000559c  lea     r9, [rsi+20h]
0x1800055a0  mov     rdx, rbx
0x1800055a3  mov     rcx, rax; Destination
0x1800055a6  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800055ab  mov     r8, [r15+18h]
0x1800055af  mov     r9, r14
0x1800055b2  mov     rdx, rbx
0x1800055b5  mov     rcx, rax; Destination
0x1800055b8  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x1800055bd  sub     rbx, rax
0x1800055c0  xor     edx, edx; Val
0x1800055c2  mov     r8, rbx; Size
0x1800055c5  mov     rcx, rax; void *
0x1800055c8  call    memset_0
0x1800055cd  add     rsp, 28h
0x1800055d1  pop     r15
0x1800055d3  pop     r14
0x1800055d5  pop     r13
0x1800055d7  pop     r12
0x1800055d9  pop     rdi
0x1800055da  pop     rsi
0x1800055db  pop     rbp
0x1800055dc  pop     rbx
0x1800055dd  retn
```
