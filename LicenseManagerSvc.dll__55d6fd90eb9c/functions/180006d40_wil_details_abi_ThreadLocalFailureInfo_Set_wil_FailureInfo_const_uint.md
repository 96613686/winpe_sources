# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180006d40`
- end: `0x180006e76`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800070d8`

## callees

- `0x180004184`
- `0x180004d60`
- `0x180004dd8`
- `0x1800067cc`
- `0x180006c08`
- `0x180006c28`
- `0x180006d40`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006def`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006def`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006dfd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006dfd`

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
0x180006d40  push    rbx
0x180006d42  push    rbp
0x180006d43  push    rsi
0x180006d44  push    rdi
0x180006d45  push    r12
0x180006d47  push    r13
0x180006d49  push    r14
0x180006d4b  push    r15
0x180006d4d  sub     rsp, 28h
0x180006d51  mov     [rcx+4], r8d
0x180006d55  lea     r14, [rcx+38h]
0x180006d59  mov     eax, [rdx+8]
0x180006d5c  mov     rsi, rcx
0x180006d5f  mov     [rcx+8], eax
0x180006d62  mov     r15, rdx
0x180006d65  mov     qword ptr [rcx+10h], 0
0x180006d6d  movzx   eax, word ptr [rdx+40h]
0x180006d71  mov     [rcx+18h], ax
0x180006d75  mov     al, [rdx]
0x180006d77  mov     [rcx+1Ah], al
0x180006d7a  mov     qword ptr [rcx+20h], 0
0x180006d82  mov     rax, [rdx+88h]
0x180006d89  mov     [rcx+28h], rax
0x180006d8d  mov     rax, [rdx+90h]
0x180006d94  mov     [rcx+30h], rax
0x180006d98  mov     qword ptr [r14], 0
0x180006d9f  mov     rcx, [rdx+18h]; this
0x180006da3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180006da8  mov     rcx, [r15+38h]; this
0x180006dac  mov     rbp, rax
0x180006daf  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180006db4  mov     rcx, [r15+80h]; this
0x180006dbb  add     rbp, rax
0x180006dbe  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180006dc3  add     rbp, rax
0x180006dc6  lea     rdi, [rsi+48h]
0x180006dca  cmp     qword ptr [rsi+40h], 0
0x180006dcf  jz      short loc_180006DD6
0x180006dd1  cmp     [rdi], rbp
0x180006dd4  jnb     short loc_180006E0E
0x180006dd6  mov     rdx, rbp; dwBytes
0x180006dd9  mov     ecx, 8; dwFlags
0x180006dde  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006de3  mov     r14, rax
0x180006de6  test    rax, rax
0x180006de9  jz      short loc_180006E0A
0x180006deb  mov     rbx, [rsi+40h]
0x180006def  call    cs:__imp_GetProcessHeap
0x180006df5  mov     r8, rbx; lpMem
0x180006df8  xor     edx, edx; dwFlags
0x180006dfa  mov     rcx, rax; hHeap
0x180006dfd  call    cs:__imp_HeapFree
0x180006e03  mov     [rsi+40h], r14
0x180006e07  mov     [rdi], rbp
0x180006e0a  lea     r14, [rsi+38h]
0x180006e0e  mov     rcx, [rsi+40h]; Destination
0x180006e12  test    rcx, rcx
0x180006e15  jz      short loc_180006E65
0x180006e17  mov     rbx, [rdi]
0x180006e1a  lea     r9, [rsi+10h]
0x180006e1e  mov     r8, [r15+38h]
0x180006e22  add     rbx, rcx
0x180006e25  mov     rdx, rbx
0x180006e28  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180006e2d  mov     r8, [r15+80h]
0x180006e34  lea     r9, [rsi+20h]
0x180006e38  mov     rdx, rbx
0x180006e3b  mov     rcx, rax; Destination
0x180006e3e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180006e43  mov     r8, [r15+18h]
0x180006e47  mov     r9, r14
0x180006e4a  mov     rdx, rbx
0x180006e4d  mov     rcx, rax; Destination
0x180006e50  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180006e55  sub     rbx, rax
0x180006e58  xor     edx, edx; Val
0x180006e5a  mov     r8, rbx; Size
0x180006e5d  mov     rcx, rax; void *
0x180006e60  call    memset_0
0x180006e65  add     rsp, 28h
0x180006e69  pop     r15
0x180006e6b  pop     r14
0x180006e6d  pop     r13
0x180006e6f  pop     r12
0x180006e71  pop     rdi
0x180006e72  pop     rsi
0x180006e73  pop     rbp
0x180006e74  pop     rbx
0x180006e75  retn
```
