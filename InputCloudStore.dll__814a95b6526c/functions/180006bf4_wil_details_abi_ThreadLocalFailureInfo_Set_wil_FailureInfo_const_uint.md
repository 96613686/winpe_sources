# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180006bf4`
- end: `0x180006d2a`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180006f8c`

## callees

- `0x180003fd4`
- `0x180004b60`
- `0x180004bd8`
- `0x180006778`
- `0x180006a78`
- `0x180006a98`
- `0x180006bf4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006ca3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006ca3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006cb1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006cb1`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  wchar_t **v3; // r14
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
  char *v18; // rax
  char *v19; // rax

  *((_DWORD *)this + 1) = a3;
  v3 = (wchar_t **)((char *)this + 56);
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v6 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const wchar_t *)a2);
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
    v3 = (wchar_t **)((char *)this + 56);
  }
  v15 = (char *)*((_QWORD *)this + 8);
  if ( v15 )
  {
    v16 = &v15[*v11];
    v17 = wil::details::WriteResultString<char const *>(v15, v16, *((wil::details **)a2 + 7), (char **)this + 2);
    v18 = wil::details::WriteResultString<char const *>(v17, v16, *((wil::details **)a2 + 16), (char **)this + 4);
    v19 = wil::details::WriteResultString<wchar_t const *>(
            (wchar_t *)v18,
            (const wchar_t *)v16,
            *((wil::details **)a2 + 3),
            v3);
    memset_0(v19, 0, v16 - v19);
  }
}

```

## disassembly

```asm
0x180006bf4  push    rbx
0x180006bf6  push    rbp
0x180006bf7  push    rsi
0x180006bf8  push    rdi
0x180006bf9  push    r12
0x180006bfb  push    r13
0x180006bfd  push    r14
0x180006bff  push    r15
0x180006c01  sub     rsp, 28h
0x180006c05  mov     [rcx+4], r8d
0x180006c09  lea     r14, [rcx+38h]
0x180006c0d  mov     eax, [rdx+8]
0x180006c10  mov     rsi, rcx
0x180006c13  mov     [rcx+8], eax
0x180006c16  mov     r15, rdx
0x180006c19  mov     qword ptr [rcx+10h], 0
0x180006c21  movzx   eax, word ptr [rdx+40h]
0x180006c25  mov     [rcx+18h], ax
0x180006c29  mov     al, [rdx]
0x180006c2b  mov     [rcx+1Ah], al
0x180006c2e  mov     qword ptr [rcx+20h], 0
0x180006c36  mov     rax, [rdx+88h]
0x180006c3d  mov     [rcx+28h], rax
0x180006c41  mov     rax, [rdx+90h]
0x180006c48  mov     [rcx+30h], rax
0x180006c4c  mov     qword ptr [r14], 0
0x180006c53  mov     rcx, [rdx+18h]; this
0x180006c57  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x180006c5c  mov     rcx, [r15+38h]; this
0x180006c60  mov     rbp, rax
0x180006c63  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180006c68  mov     rcx, [r15+80h]; this
0x180006c6f  add     rbp, rax
0x180006c72  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180006c77  add     rbp, rax
0x180006c7a  lea     rdi, [rsi+48h]
0x180006c7e  cmp     qword ptr [rsi+40h], 0
0x180006c83  jz      short loc_180006C8A
0x180006c85  cmp     [rdi], rbp
0x180006c88  jnb     short loc_180006CC2
0x180006c8a  mov     rdx, rbp; dwBytes
0x180006c8d  mov     ecx, 8; dwFlags
0x180006c92  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006c97  mov     r14, rax
0x180006c9a  test    rax, rax
0x180006c9d  jz      short loc_180006CBE
0x180006c9f  mov     rbx, [rsi+40h]
0x180006ca3  call    cs:__imp_GetProcessHeap
0x180006ca9  mov     r8, rbx; lpMem
0x180006cac  xor     edx, edx; dwFlags
0x180006cae  mov     rcx, rax; hHeap
0x180006cb1  call    cs:__imp_HeapFree
0x180006cb7  mov     [rsi+40h], r14
0x180006cbb  mov     [rdi], rbp
0x180006cbe  lea     r14, [rsi+38h]
0x180006cc2  mov     rcx, [rsi+40h]; Destination
0x180006cc6  test    rcx, rcx
0x180006cc9  jz      short loc_180006D19
0x180006ccb  mov     rbx, [rdi]
0x180006cce  lea     r9, [rsi+10h]
0x180006cd2  mov     r8, [r15+38h]
0x180006cd6  add     rbx, rcx
0x180006cd9  mov     rdx, rbx
0x180006cdc  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180006ce1  mov     r8, [r15+80h]
0x180006ce8  lea     r9, [rsi+20h]
0x180006cec  mov     rdx, rbx
0x180006cef  mov     rcx, rax; Destination
0x180006cf2  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180006cf7  mov     r8, [r15+18h]
0x180006cfb  mov     r9, r14
0x180006cfe  mov     rdx, rbx
0x180006d01  mov     rcx, rax; Destination
0x180006d04  call    ??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z; wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)
0x180006d09  sub     rbx, rax
0x180006d0c  xor     edx, edx; Val
0x180006d0e  mov     r8, rbx; Size
0x180006d11  mov     rcx, rax; void *
0x180006d14  call    memset_0
0x180006d19  add     rsp, 28h
0x180006d1d  pop     r15
0x180006d1f  pop     r14
0x180006d21  pop     r13
0x180006d23  pop     r12
0x180006d25  pop     rdi
0x180006d26  pop     rsi
0x180006d27  pop     rbp
0x180006d28  pop     rbx
0x180006d29  retn
```
