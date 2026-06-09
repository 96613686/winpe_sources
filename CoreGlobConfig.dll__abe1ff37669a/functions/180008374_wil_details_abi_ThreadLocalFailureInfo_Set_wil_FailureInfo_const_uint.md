# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180008374`
- end: `0x1800084aa`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000870c`

## callees

- `0x1800032dc`
- `0x180006360`
- `0x1800063d8`
- `0x180007ee8`
- `0x1800081f8`
- `0x180008218`
- `0x180008374`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008423`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008423`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008431`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008431`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  unsigned __int16 **v3; // r14
  unsigned __int64 v6; // rbp
  const char *v7; // rdx
  unsigned __int64 v8; // rbp
  const char *v9; // rdx
  SIZE_T v10; // rbp
  SIZE_T *v11; // rdi
  LPVOID v12; // r14
  void *v13; // rbx
  HANDLE ProcessHeap; // rax
  char *v15; // rcx
  const char *v16; // rbx
  char *v17; // rax
  unsigned __int16 *v18; // rax
  char *v19; // rax

  *((_DWORD *)this + 1) = a3;
  v3 = (unsigned __int16 **)((char *)this + 56);
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
    v3 = (unsigned __int16 **)((char *)this + 56);
  }
  v15 = (char *)*((_QWORD *)this + 8);
  if ( v15 )
  {
    v16 = &v15[*v11];
    v17 = wil::details::WriteResultString<char const *>(v15, v16, *((wil::details **)a2 + 7), (char **)this + 2);
    v18 = (unsigned __int16 *)wil::details::WriteResultString<char const *>(
                                v17,
                                v16,
                                *((wil::details **)a2 + 16),
                                (char **)this + 4);
    v19 = wil::details::WriteResultString<unsigned short const *>(
            v18,
            (const unsigned __int16 *)v16,
            *((wil::details **)a2 + 3),
            v3);
    memset_0(v19, 0, v16 - v19);
  }
}

```

## disassembly

```asm
0x180008374  push    rbx
0x180008376  push    rbp
0x180008377  push    rsi
0x180008378  push    rdi
0x180008379  push    r12
0x18000837b  push    r13
0x18000837d  push    r14
0x18000837f  push    r15
0x180008381  sub     rsp, 28h
0x180008385  mov     [rcx+4], r8d
0x180008389  lea     r14, [rcx+38h]
0x18000838d  mov     eax, [rdx+8]
0x180008390  mov     rsi, rcx
0x180008393  mov     [rcx+8], eax
0x180008396  mov     r15, rdx
0x180008399  mov     qword ptr [rcx+10h], 0
0x1800083a1  movzx   eax, word ptr [rdx+40h]
0x1800083a5  mov     [rcx+18h], ax
0x1800083a9  mov     al, [rdx]
0x1800083ab  mov     [rcx+1Ah], al
0x1800083ae  mov     qword ptr [rcx+20h], 0
0x1800083b6  mov     rax, [rdx+88h]
0x1800083bd  mov     [rcx+28h], rax
0x1800083c1  mov     rax, [rdx+90h]
0x1800083c8  mov     [rcx+30h], rax
0x1800083cc  mov     qword ptr [r14], 0
0x1800083d3  mov     rcx, [rdx+18h]; this
0x1800083d7  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800083dc  mov     rcx, [r15+38h]; this
0x1800083e0  mov     rbp, rax
0x1800083e3  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800083e8  mov     rcx, [r15+80h]; this
0x1800083ef  add     rbp, rax
0x1800083f2  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800083f7  add     rbp, rax
0x1800083fa  lea     rdi, [rsi+48h]
0x1800083fe  cmp     qword ptr [rsi+40h], 0
0x180008403  jz      short loc_18000840A
0x180008405  cmp     [rdi], rbp
0x180008408  jnb     short loc_180008442
0x18000840a  mov     rdx, rbp; dwBytes
0x18000840d  mov     ecx, 8; dwFlags
0x180008412  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008417  mov     r14, rax
0x18000841a  test    rax, rax
0x18000841d  jz      short loc_18000843E
0x18000841f  mov     rbx, [rsi+40h]
0x180008423  call    cs:__imp_GetProcessHeap
0x180008429  mov     r8, rbx; lpMem
0x18000842c  xor     edx, edx; dwFlags
0x18000842e  mov     rcx, rax; hHeap
0x180008431  call    cs:__imp_HeapFree
0x180008437  mov     [rsi+40h], r14
0x18000843b  mov     [rdi], rbp
0x18000843e  lea     r14, [rsi+38h]
0x180008442  mov     rcx, [rsi+40h]; Destination
0x180008446  test    rcx, rcx
0x180008449  jz      short loc_180008499
0x18000844b  mov     rbx, [rdi]
0x18000844e  lea     r9, [rsi+10h]
0x180008452  mov     r8, [r15+38h]
0x180008456  add     rbx, rcx
0x180008459  mov     rdx, rbx
0x18000845c  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180008461  mov     r8, [r15+80h]
0x180008468  lea     r9, [rsi+20h]
0x18000846c  mov     rdx, rbx
0x18000846f  mov     rcx, rax; Destination
0x180008472  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180008477  mov     r8, [r15+18h]
0x18000847b  mov     r9, r14
0x18000847e  mov     rdx, rbx
0x180008481  mov     rcx, rax; Destination
0x180008484  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180008489  sub     rbx, rax
0x18000848c  xor     edx, edx; Val
0x18000848e  mov     r8, rbx; Size
0x180008491  mov     rcx, rax; void *
0x180008494  call    memset_0
0x180008499  add     rsp, 28h
0x18000849d  pop     r15
0x18000849f  pop     r14
0x1800084a1  pop     r13
0x1800084a3  pop     r12
0x1800084a5  pop     rdi
0x1800084a6  pop     rsi
0x1800084a7  pop     rbp
0x1800084a8  pop     rbx
0x1800084a9  retn
```
