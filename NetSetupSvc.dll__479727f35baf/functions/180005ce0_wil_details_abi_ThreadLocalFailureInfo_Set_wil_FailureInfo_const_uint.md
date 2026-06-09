# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180005ce0`
- end: `0x180005e16`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180006078`

## callees

- `0x1800032d8`
- `0x180003d4c`
- `0x180003dc4`
- `0x1800058b0`
- `0x180005bb8`
- `0x180005bd8`
- `0x180005ce0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005d8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005d8f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005d9d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005d9d`

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
0x180005ce0  push    rbx
0x180005ce2  push    rbp
0x180005ce3  push    rsi
0x180005ce4  push    rdi
0x180005ce5  push    r12
0x180005ce7  push    r13
0x180005ce9  push    r14
0x180005ceb  push    r15
0x180005ced  sub     rsp, 28h
0x180005cf1  mov     [rcx+4], r8d
0x180005cf5  lea     r14, [rcx+38h]
0x180005cf9  mov     eax, [rdx+8]
0x180005cfc  mov     rsi, rcx
0x180005cff  mov     [rcx+8], eax
0x180005d02  mov     r15, rdx
0x180005d05  mov     qword ptr [rcx+10h], 0
0x180005d0d  movzx   eax, word ptr [rdx+40h]
0x180005d11  mov     [rcx+18h], ax
0x180005d15  mov     al, [rdx]
0x180005d17  mov     [rcx+1Ah], al
0x180005d1a  mov     qword ptr [rcx+20h], 0
0x180005d22  mov     rax, [rdx+88h]
0x180005d29  mov     [rcx+28h], rax
0x180005d2d  mov     rax, [rdx+90h]
0x180005d34  mov     [rcx+30h], rax
0x180005d38  mov     qword ptr [r14], 0
0x180005d3f  mov     rcx, [rdx+18h]; this
0x180005d43  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x180005d48  mov     rcx, [r15+38h]; this
0x180005d4c  mov     rbp, rax
0x180005d4f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180005d54  mov     rcx, [r15+80h]; this
0x180005d5b  add     rbp, rax
0x180005d5e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180005d63  add     rbp, rax
0x180005d66  lea     rdi, [rsi+48h]
0x180005d6a  cmp     qword ptr [rsi+40h], 0
0x180005d6f  jz      short loc_180005D76
0x180005d71  cmp     [rdi], rbp
0x180005d74  jnb     short loc_180005DAE
0x180005d76  mov     rdx, rbp; dwBytes
0x180005d79  mov     ecx, 8; dwFlags
0x180005d7e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005d83  mov     r14, rax
0x180005d86  test    rax, rax
0x180005d89  jz      short loc_180005DAA
0x180005d8b  mov     rbx, [rsi+40h]
0x180005d8f  call    cs:__imp_GetProcessHeap
0x180005d95  mov     r8, rbx; lpMem
0x180005d98  xor     edx, edx; dwFlags
0x180005d9a  mov     rcx, rax; hHeap
0x180005d9d  call    cs:__imp_HeapFree
0x180005da3  mov     [rsi+40h], r14
0x180005da7  mov     [rdi], rbp
0x180005daa  lea     r14, [rsi+38h]
0x180005dae  mov     rcx, [rsi+40h]; Destination
0x180005db2  test    rcx, rcx
0x180005db5  jz      short loc_180005E05
0x180005db7  mov     rbx, [rdi]
0x180005dba  lea     r9, [rsi+10h]
0x180005dbe  mov     r8, [r15+38h]
0x180005dc2  add     rbx, rcx
0x180005dc5  mov     rdx, rbx
0x180005dc8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180005dcd  mov     r8, [r15+80h]
0x180005dd4  lea     r9, [rsi+20h]
0x180005dd8  mov     rdx, rbx
0x180005ddb  mov     rcx, rax; Destination
0x180005dde  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180005de3  mov     r8, [r15+18h]
0x180005de7  mov     r9, r14
0x180005dea  mov     rdx, rbx
0x180005ded  mov     rcx, rax; Destination
0x180005df0  call    ??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z; wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)
0x180005df5  sub     rbx, rax
0x180005df8  xor     edx, edx; Val
0x180005dfa  mov     r8, rbx; Size
0x180005dfd  mov     rcx, rax; void *
0x180005e00  call    memset_0
0x180005e05  add     rsp, 28h
0x180005e09  pop     r15
0x180005e0b  pop     r14
0x180005e0d  pop     r13
0x180005e0f  pop     r12
0x180005e11  pop     rdi
0x180005e12  pop     rsi
0x180005e13  pop     rbp
0x180005e14  pop     rbx
0x180005e15  retn
```
