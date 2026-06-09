# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1400083f0`
- end: `0x140008526`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140008864`

## callees

- `0x140003de8`
- `0x1400049a0`
- `0x140004a18`
- `0x140007370`
- `0x14000829c`
- `0x1400082bc`
- `0x1400083f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400084ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400084ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000849f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000849f`

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
0x1400083f0  push    rbx
0x1400083f2  push    rbp
0x1400083f3  push    rsi
0x1400083f4  push    rdi
0x1400083f5  push    r12
0x1400083f7  push    r13
0x1400083f9  push    r14
0x1400083fb  push    r15
0x1400083fd  sub     rsp, 28h
0x140008401  mov     [rcx+4], r8d
0x140008405  lea     r14, [rcx+38h]
0x140008409  mov     eax, [rdx+8]
0x14000840c  mov     rsi, rcx
0x14000840f  mov     [rcx+8], eax
0x140008412  mov     r15, rdx
0x140008415  mov     qword ptr [rcx+10h], 0
0x14000841d  movzx   eax, word ptr [rdx+40h]
0x140008421  mov     [rcx+18h], ax
0x140008425  mov     al, [rdx]
0x140008427  mov     [rcx+1Ah], al
0x14000842a  mov     qword ptr [rcx+20h], 0
0x140008432  mov     rax, [rdx+88h]
0x140008439  mov     [rcx+28h], rax
0x14000843d  mov     rax, [rdx+90h]
0x140008444  mov     [rcx+30h], rax
0x140008448  mov     qword ptr [r14], 0
0x14000844f  mov     rcx, [rdx+18h]; this
0x140008453  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x140008458  mov     rcx, [r15+38h]; this
0x14000845c  mov     rbp, rax
0x14000845f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140008464  mov     rcx, [r15+80h]; this
0x14000846b  add     rbp, rax
0x14000846e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140008473  add     rbp, rax
0x140008476  lea     rdi, [rsi+48h]
0x14000847a  cmp     qword ptr [rsi+40h], 0
0x14000847f  jz      short loc_140008486
0x140008481  cmp     [rdi], rbp
0x140008484  jnb     short loc_1400084BE
0x140008486  mov     rdx, rbp; dwBytes
0x140008489  mov     ecx, 8; dwFlags
0x14000848e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140008493  mov     r14, rax
0x140008496  test    rax, rax
0x140008499  jz      short loc_1400084BA
0x14000849b  mov     rbx, [rsi+40h]
0x14000849f  call    cs:__imp_GetProcessHeap
0x1400084a5  mov     r8, rbx; lpMem
0x1400084a8  xor     edx, edx; dwFlags
0x1400084aa  mov     rcx, rax; hHeap
0x1400084ad  call    cs:__imp_HeapFree
0x1400084b3  mov     [rsi+40h], r14
0x1400084b7  mov     [rdi], rbp
0x1400084ba  lea     r14, [rsi+38h]
0x1400084be  mov     rcx, [rsi+40h]; Destination
0x1400084c2  test    rcx, rcx
0x1400084c5  jz      short loc_140008515
0x1400084c7  mov     rbx, [rdi]
0x1400084ca  lea     r9, [rsi+10h]
0x1400084ce  mov     r8, [r15+38h]
0x1400084d2  add     rbx, rcx
0x1400084d5  mov     rdx, rbx
0x1400084d8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1400084dd  mov     r8, [r15+80h]
0x1400084e4  lea     r9, [rsi+20h]
0x1400084e8  mov     rdx, rbx
0x1400084eb  mov     rcx, rax; Destination
0x1400084ee  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1400084f3  mov     r8, [r15+18h]
0x1400084f7  mov     r9, r14
0x1400084fa  mov     rdx, rbx
0x1400084fd  mov     rcx, rax; Destination
0x140008500  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x140008505  sub     rbx, rax
0x140008508  xor     edx, edx; Val
0x14000850a  mov     r8, rbx; Size
0x14000850d  mov     rcx, rax; void *
0x140008510  call    memset_0
0x140008515  add     rsp, 28h
0x140008519  pop     r15
0x14000851b  pop     r14
0x14000851d  pop     r13
0x14000851f  pop     r12
0x140008521  pop     rdi
0x140008522  pop     rsi
0x140008523  pop     rbp
0x140008524  pop     rbx
0x140008525  retn
```
