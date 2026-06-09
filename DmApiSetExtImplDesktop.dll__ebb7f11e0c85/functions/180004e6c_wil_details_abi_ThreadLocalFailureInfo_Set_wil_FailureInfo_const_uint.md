# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180004e6c`
- end: `0x180004faf`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `323`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180005220`

## callees

- `0x180002b40`
- `0x180002bc0`
- `0x180004978`
- `0x180004d58`
- `0x180004d7c`
- `0x180004e6c`
- `0x180009efe`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004f2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004f2f`

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
0x180004e6c  push    rbx
0x180004e6e  push    rbp
0x180004e6f  push    rsi
0x180004e70  push    rdi
0x180004e71  push    r12
0x180004e73  push    r13
0x180004e75  push    r14
0x180004e77  push    r15
0x180004e79  sub     rsp, 28h
0x180004e7d  mov     [rcx+4], r8d
0x180004e81  lea     r14, [rcx+38h]
0x180004e85  mov     eax, [rdx+8]
0x180004e88  mov     rsi, rcx
0x180004e8b  mov     [rcx+8], eax
0x180004e8e  mov     r15, rdx
0x180004e91  mov     qword ptr [rcx+10h], 0
0x180004e99  movzx   eax, word ptr [rdx+40h]
0x180004e9d  mov     [rcx+18h], ax
0x180004ea1  mov     al, [rdx]
0x180004ea3  mov     [rcx+1Ah], al
0x180004ea6  mov     qword ptr [rcx+20h], 0
0x180004eae  mov     rax, [rdx+88h]
0x180004eb5  mov     [rcx+28h], rax
0x180004eb9  mov     rax, [rdx+90h]
0x180004ec0  mov     [rcx+30h], rax
0x180004ec4  mov     qword ptr [r14], 0
0x180004ecb  mov     rcx, [rdx+18h]; this
0x180004ecf  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180004ed4  mov     rcx, [r15+38h]; this
0x180004ed8  mov     rbp, rax
0x180004edb  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180004ee0  mov     rcx, [r15+80h]; this
0x180004ee7  add     rbp, rax
0x180004eea  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180004eef  add     rbp, rax
0x180004ef2  lea     rdi, [rsi+48h]
0x180004ef6  cmp     qword ptr [rsi+40h], 0
0x180004efb  jz      short loc_180004F02
0x180004efd  cmp     [rdi], rbp
0x180004f00  jnb     short loc_180004F46
0x180004f02  mov     rdx, rbp; dwBytes
0x180004f05  mov     ecx, 8; dwFlags
0x180004f0a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004f0f  mov     r14, rax
0x180004f12  test    rax, rax
0x180004f15  jz      short loc_180004F42
0x180004f17  mov     rbx, [rsi+40h]
0x180004f1b  call    cs:__imp_GetProcessHeap
0x180004f22  nop     dword ptr [rax+rax+00h]
0x180004f27  mov     r8, rbx; lpMem
0x180004f2a  xor     edx, edx; dwFlags
0x180004f2c  mov     rcx, rax; hHeap
0x180004f2f  call    cs:__imp_HeapFree
0x180004f36  nop     dword ptr [rax+rax+00h]
0x180004f3b  mov     [rsi+40h], r14
0x180004f3f  mov     [rdi], rbp
0x180004f42  lea     r14, [rsi+38h]
0x180004f46  mov     rcx, [rsi+40h]; Destination
0x180004f4a  test    rcx, rcx
0x180004f4d  jz      short loc_180004F9D
0x180004f4f  mov     rbx, [rdi]
0x180004f52  lea     r9, [rsi+10h]
0x180004f56  mov     r8, [r15+38h]
0x180004f5a  add     rbx, rcx
0x180004f5d  mov     rdx, rbx
0x180004f60  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180004f65  mov     r8, [r15+80h]
0x180004f6c  lea     r9, [rsi+20h]
0x180004f70  mov     rdx, rbx
0x180004f73  mov     rcx, rax; Destination
0x180004f76  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180004f7b  mov     r8, [r15+18h]
0x180004f7f  mov     r9, r14
0x180004f82  mov     rdx, rbx
0x180004f85  mov     rcx, rax; Destination
0x180004f88  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180004f8d  sub     rbx, rax
0x180004f90  xor     edx, edx; Val
0x180004f92  mov     r8, rbx; Size
0x180004f95  mov     rcx, rax; void *
0x180004f98  call    memset_0
0x180004f9d  add     rsp, 28h
0x180004fa1  pop     r15
0x180004fa3  pop     r14
0x180004fa5  pop     r13
0x180004fa7  pop     r12
0x180004fa9  pop     rdi
0x180004faa  pop     rsi
0x180004fab  pop     rbp
0x180004fac  pop     rbx
0x180004fad  retn
```
