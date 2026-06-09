# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800069bc`
- end: `0x180006af2`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180006d54`

## callees

- `0x180003f7c`
- `0x180004b14`
- `0x180004b8c`
- `0x180006538`
- `0x1800068d8`
- `0x1800068f8`
- `0x1800069bc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006a6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006a6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006a79`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006a79`

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
0x1800069bc  push    rbx
0x1800069be  push    rbp
0x1800069bf  push    rsi
0x1800069c0  push    rdi
0x1800069c1  push    r12
0x1800069c3  push    r13
0x1800069c5  push    r14
0x1800069c7  push    r15
0x1800069c9  sub     rsp, 28h
0x1800069cd  mov     [rcx+4], r8d
0x1800069d1  lea     r14, [rcx+38h]
0x1800069d5  mov     eax, [rdx+8]
0x1800069d8  mov     rsi, rcx
0x1800069db  mov     [rcx+8], eax
0x1800069de  mov     r15, rdx
0x1800069e1  mov     qword ptr [rcx+10h], 0
0x1800069e9  movzx   eax, word ptr [rdx+40h]
0x1800069ed  mov     [rcx+18h], ax
0x1800069f1  mov     al, [rdx]
0x1800069f3  mov     [rcx+1Ah], al
0x1800069f6  mov     qword ptr [rcx+20h], 0
0x1800069fe  mov     rax, [rdx+88h]
0x180006a05  mov     [rcx+28h], rax
0x180006a09  mov     rax, [rdx+90h]
0x180006a10  mov     [rcx+30h], rax
0x180006a14  mov     qword ptr [r14], 0
0x180006a1b  mov     rcx, [rdx+18h]; this
0x180006a1f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180006a24  mov     rcx, [r15+38h]; this
0x180006a28  mov     rbp, rax
0x180006a2b  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180006a30  mov     rcx, [r15+80h]; this
0x180006a37  add     rbp, rax
0x180006a3a  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180006a3f  add     rbp, rax
0x180006a42  lea     rdi, [rsi+48h]
0x180006a46  cmp     qword ptr [rsi+40h], 0
0x180006a4b  jz      short loc_180006A52
0x180006a4d  cmp     [rdi], rbp
0x180006a50  jnb     short loc_180006A8A
0x180006a52  mov     rdx, rbp; dwBytes
0x180006a55  mov     ecx, 8; dwFlags
0x180006a5a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006a5f  mov     r14, rax
0x180006a62  test    rax, rax
0x180006a65  jz      short loc_180006A86
0x180006a67  mov     rbx, [rsi+40h]
0x180006a6b  call    cs:__imp_GetProcessHeap
0x180006a71  mov     r8, rbx; lpMem
0x180006a74  xor     edx, edx; dwFlags
0x180006a76  mov     rcx, rax; hHeap
0x180006a79  call    cs:__imp_HeapFree
0x180006a7f  mov     [rsi+40h], r14
0x180006a83  mov     [rdi], rbp
0x180006a86  lea     r14, [rsi+38h]
0x180006a8a  mov     rcx, [rsi+40h]; Destination
0x180006a8e  test    rcx, rcx
0x180006a91  jz      short loc_180006AE1
0x180006a93  mov     rbx, [rdi]
0x180006a96  lea     r9, [rsi+10h]
0x180006a9a  mov     r8, [r15+38h]
0x180006a9e  add     rbx, rcx
0x180006aa1  mov     rdx, rbx
0x180006aa4  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180006aa9  mov     r8, [r15+80h]
0x180006ab0  lea     r9, [rsi+20h]
0x180006ab4  mov     rdx, rbx
0x180006ab7  mov     rcx, rax; Destination
0x180006aba  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180006abf  mov     r8, [r15+18h]
0x180006ac3  mov     r9, r14
0x180006ac6  mov     rdx, rbx
0x180006ac9  mov     rcx, rax; Destination
0x180006acc  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180006ad1  sub     rbx, rax
0x180006ad4  xor     edx, edx; Val
0x180006ad6  mov     r8, rbx; Size
0x180006ad9  mov     rcx, rax; void *
0x180006adc  call    memset_0
0x180006ae1  add     rsp, 28h
0x180006ae5  pop     r15
0x180006ae7  pop     r14
0x180006ae9  pop     r13
0x180006aeb  pop     r12
0x180006aed  pop     rdi
0x180006aee  pop     rsi
0x180006aef  pop     rbp
0x180006af0  pop     rbx
0x180006af1  retn
```
