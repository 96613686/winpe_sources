# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000c310`
- end: `0x18000c446`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000c6a8`

## callees

- `0x1800093c4`
- `0x18000a650`
- `0x18000a6c8`
- `0x18000c078`
- `0x18000c1e8`
- `0x18000c208`
- `0x18000c310`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000c3bf`
- `KERNEL32!GetProcessHeap` at `0x18000c3bf`
- `KERNEL32!HeapFree` at `0x18000c3cd`
- `KERNEL32!HeapFree` at `0x18000c3cd`

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
  v5 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const wchar_t *)a2);
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
    v18 = (void *)wil::details::WriteResultString<wchar_t const *>(v17);
    memset_0(v18, 0, v15 - (_BYTE *)v18);
  }
}

```

## disassembly

```asm
0x18000c310  push    rbx
0x18000c312  push    rbp
0x18000c313  push    rsi
0x18000c314  push    rdi
0x18000c315  push    r12
0x18000c317  push    r13
0x18000c319  push    r14
0x18000c31b  push    r15
0x18000c31d  sub     rsp, 28h
0x18000c321  mov     [rcx+4], r8d
0x18000c325  lea     r14, [rcx+38h]
0x18000c329  mov     eax, [rdx+8]
0x18000c32c  mov     rsi, rcx
0x18000c32f  mov     [rcx+8], eax
0x18000c332  mov     r15, rdx
0x18000c335  mov     qword ptr [rcx+10h], 0
0x18000c33d  movzx   eax, word ptr [rdx+40h]
0x18000c341  mov     [rcx+18h], ax
0x18000c345  mov     al, [rdx]
0x18000c347  mov     [rcx+1Ah], al
0x18000c34a  mov     qword ptr [rcx+20h], 0
0x18000c352  mov     rax, [rdx+88h]
0x18000c359  mov     [rcx+28h], rax
0x18000c35d  mov     rax, [rdx+90h]
0x18000c364  mov     [rcx+30h], rax
0x18000c368  mov     qword ptr [r14], 0
0x18000c36f  mov     rcx, [rdx+18h]; this
0x18000c373  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x18000c378  mov     rcx, [r15+38h]; this
0x18000c37c  mov     rbp, rax
0x18000c37f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000c384  mov     rcx, [r15+80h]; this
0x18000c38b  add     rbp, rax
0x18000c38e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000c393  add     rbp, rax
0x18000c396  lea     rdi, [rsi+48h]
0x18000c39a  cmp     qword ptr [rsi+40h], 0
0x18000c39f  jz      short loc_18000C3A6
0x18000c3a1  cmp     [rdi], rbp
0x18000c3a4  jnb     short loc_18000C3DE
0x18000c3a6  mov     rdx, rbp; dwBytes
0x18000c3a9  mov     ecx, 8; dwFlags
0x18000c3ae  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000c3b3  mov     r14, rax
0x18000c3b6  test    rax, rax
0x18000c3b9  jz      short loc_18000C3DA
0x18000c3bb  mov     rbx, [rsi+40h]
0x18000c3bf  call    cs:__imp_GetProcessHeap
0x18000c3c5  mov     r8, rbx; lpMem
0x18000c3c8  xor     edx, edx; dwFlags
0x18000c3ca  mov     rcx, rax; hHeap
0x18000c3cd  call    cs:__imp_HeapFree
0x18000c3d3  mov     [rsi+40h], r14
0x18000c3d7  mov     [rdi], rbp
0x18000c3da  lea     r14, [rsi+38h]
0x18000c3de  mov     rcx, [rsi+40h]; Destination
0x18000c3e2  test    rcx, rcx
0x18000c3e5  jz      short loc_18000C435
0x18000c3e7  mov     rbx, [rdi]
0x18000c3ea  lea     r9, [rsi+10h]
0x18000c3ee  mov     r8, [r15+38h]
0x18000c3f2  add     rbx, rcx
0x18000c3f5  mov     rdx, rbx
0x18000c3f8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000c3fd  mov     r8, [r15+80h]
0x18000c404  lea     r9, [rsi+20h]
0x18000c408  mov     rdx, rbx
0x18000c40b  mov     rcx, rax; Destination
0x18000c40e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000c413  mov     r8, [r15+18h]
0x18000c417  mov     r9, r14
0x18000c41a  mov     rdx, rbx
0x18000c41d  mov     rcx, rax; Destination
0x18000c420  call    ??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z; wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)
0x18000c425  sub     rbx, rax
0x18000c428  xor     edx, edx; Val
0x18000c42a  mov     r8, rbx; Size
0x18000c42d  mov     rcx, rax; void *
0x18000c430  call    memset_0
0x18000c435  add     rsp, 28h
0x18000c439  pop     r15
0x18000c43b  pop     r14
0x18000c43d  pop     r13
0x18000c43f  pop     r12
0x18000c441  pop     rdi
0x18000c442  pop     rsi
0x18000c443  pop     rbp
0x18000c444  pop     rbx
0x18000c445  retn
```
