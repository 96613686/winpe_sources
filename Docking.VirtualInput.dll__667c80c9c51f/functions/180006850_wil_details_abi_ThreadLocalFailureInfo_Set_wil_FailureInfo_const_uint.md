# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180006850`
- end: `0x180006986`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180006be8`

## callees

- `0x180004054`
- `0x180004ab8`
- `0x180004b30`
- `0x1800065c0`
- `0x180006728`
- `0x180006748`
- `0x180006850`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000690d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000690d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800068ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800068ff`

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
0x180006850  push    rbx
0x180006852  push    rbp
0x180006853  push    rsi
0x180006854  push    rdi
0x180006855  push    r12
0x180006857  push    r13
0x180006859  push    r14
0x18000685b  push    r15
0x18000685d  sub     rsp, 28h
0x180006861  mov     [rcx+4], r8d
0x180006865  lea     r14, [rcx+38h]
0x180006869  mov     eax, [rdx+8]
0x18000686c  mov     rsi, rcx
0x18000686f  mov     [rcx+8], eax
0x180006872  mov     r15, rdx
0x180006875  mov     qword ptr [rcx+10h], 0
0x18000687d  movzx   eax, word ptr [rdx+40h]
0x180006881  mov     [rcx+18h], ax
0x180006885  mov     al, [rdx]
0x180006887  mov     [rcx+1Ah], al
0x18000688a  mov     qword ptr [rcx+20h], 0
0x180006892  mov     rax, [rdx+88h]
0x180006899  mov     [rcx+28h], rax
0x18000689d  mov     rax, [rdx+90h]
0x1800068a4  mov     [rcx+30h], rax
0x1800068a8  mov     qword ptr [r14], 0
0x1800068af  mov     rcx, [rdx+18h]; this
0x1800068b3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800068b8  mov     rcx, [r15+38h]; this
0x1800068bc  mov     rbp, rax
0x1800068bf  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800068c4  mov     rcx, [r15+80h]; this
0x1800068cb  add     rbp, rax
0x1800068ce  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800068d3  add     rbp, rax
0x1800068d6  lea     rdi, [rsi+48h]
0x1800068da  cmp     qword ptr [rsi+40h], 0
0x1800068df  jz      short loc_1800068E6
0x1800068e1  cmp     [rdi], rbp
0x1800068e4  jnb     short loc_18000691E
0x1800068e6  mov     rdx, rbp; dwBytes
0x1800068e9  mov     ecx, 8; dwFlags
0x1800068ee  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800068f3  mov     r14, rax
0x1800068f6  test    rax, rax
0x1800068f9  jz      short loc_18000691A
0x1800068fb  mov     rbx, [rsi+40h]
0x1800068ff  call    cs:__imp_GetProcessHeap
0x180006905  mov     r8, rbx; lpMem
0x180006908  xor     edx, edx; dwFlags
0x18000690a  mov     rcx, rax; hHeap
0x18000690d  call    cs:__imp_HeapFree
0x180006913  mov     [rsi+40h], r14
0x180006917  mov     [rdi], rbp
0x18000691a  lea     r14, [rsi+38h]
0x18000691e  mov     rcx, [rsi+40h]; Destination
0x180006922  test    rcx, rcx
0x180006925  jz      short loc_180006975
0x180006927  mov     rbx, [rdi]
0x18000692a  lea     r9, [rsi+10h]
0x18000692e  mov     r8, [r15+38h]
0x180006932  add     rbx, rcx
0x180006935  mov     rdx, rbx
0x180006938  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000693d  mov     r8, [r15+80h]
0x180006944  lea     r9, [rsi+20h]
0x180006948  mov     rdx, rbx
0x18000694b  mov     rcx, rax; Destination
0x18000694e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180006953  mov     r8, [r15+18h]
0x180006957  mov     r9, r14
0x18000695a  mov     rdx, rbx
0x18000695d  mov     rcx, rax; Destination
0x180006960  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180006965  sub     rbx, rax
0x180006968  xor     edx, edx; Val
0x18000696a  mov     r8, rbx; Size
0x18000696d  mov     rcx, rax; void *
0x180006970  call    memset_0
0x180006975  add     rsp, 28h
0x180006979  pop     r15
0x18000697b  pop     r14
0x18000697d  pop     r13
0x18000697f  pop     r12
0x180006981  pop     rdi
0x180006982  pop     rsi
0x180006983  pop     rbp
0x180006984  pop     rbx
0x180006985  retn
```
