# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x14000a590`
- end: `0x14000a6c6`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14000aa14`

## callees

- `0x140003ab8`
- `0x140004c68`
- `0x140004ce0`
- `0x140009340`
- `0x14000a3b8`
- `0x14000a3d8`
- `0x14000a590`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a63f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a63f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a64d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a64d`

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
0x14000a590  push    rbx
0x14000a592  push    rbp
0x14000a593  push    rsi
0x14000a594  push    rdi
0x14000a595  push    r12
0x14000a597  push    r13
0x14000a599  push    r14
0x14000a59b  push    r15
0x14000a59d  sub     rsp, 28h
0x14000a5a1  mov     [rcx+4], r8d
0x14000a5a5  lea     r14, [rcx+38h]
0x14000a5a9  mov     eax, [rdx+8]
0x14000a5ac  mov     rsi, rcx
0x14000a5af  mov     [rcx+8], eax
0x14000a5b2  mov     r15, rdx
0x14000a5b5  mov     qword ptr [rcx+10h], 0
0x14000a5bd  movzx   eax, word ptr [rdx+40h]
0x14000a5c1  mov     [rcx+18h], ax
0x14000a5c5  mov     al, [rdx]
0x14000a5c7  mov     [rcx+1Ah], al
0x14000a5ca  mov     qword ptr [rcx+20h], 0
0x14000a5d2  mov     rax, [rdx+88h]
0x14000a5d9  mov     [rcx+28h], rax
0x14000a5dd  mov     rax, [rdx+90h]
0x14000a5e4  mov     [rcx+30h], rax
0x14000a5e8  mov     qword ptr [r14], 0
0x14000a5ef  mov     rcx, [rdx+18h]; this
0x14000a5f3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x14000a5f8  mov     rcx, [r15+38h]; this
0x14000a5fc  mov     rbp, rax
0x14000a5ff  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x14000a604  mov     rcx, [r15+80h]; this
0x14000a60b  add     rbp, rax
0x14000a60e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x14000a613  add     rbp, rax
0x14000a616  lea     rdi, [rsi+48h]
0x14000a61a  cmp     qword ptr [rsi+40h], 0
0x14000a61f  jz      short loc_14000A626
0x14000a621  cmp     [rdi], rbp
0x14000a624  jnb     short loc_14000A65E
0x14000a626  mov     rdx, rbp; dwBytes
0x14000a629  mov     ecx, 8; dwFlags
0x14000a62e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000a633  mov     r14, rax
0x14000a636  test    rax, rax
0x14000a639  jz      short loc_14000A65A
0x14000a63b  mov     rbx, [rsi+40h]
0x14000a63f  call    cs:__imp_GetProcessHeap
0x14000a645  mov     r8, rbx; lpMem
0x14000a648  xor     edx, edx; dwFlags
0x14000a64a  mov     rcx, rax; hHeap
0x14000a64d  call    cs:__imp_HeapFree
0x14000a653  mov     [rsi+40h], r14
0x14000a657  mov     [rdi], rbp
0x14000a65a  lea     r14, [rsi+38h]
0x14000a65e  mov     rcx, [rsi+40h]; Destination
0x14000a662  test    rcx, rcx
0x14000a665  jz      short loc_14000A6B5
0x14000a667  mov     rbx, [rdi]
0x14000a66a  lea     r9, [rsi+10h]
0x14000a66e  mov     r8, [r15+38h]
0x14000a672  add     rbx, rcx
0x14000a675  mov     rdx, rbx
0x14000a678  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14000a67d  mov     r8, [r15+80h]
0x14000a684  lea     r9, [rsi+20h]
0x14000a688  mov     rdx, rbx
0x14000a68b  mov     rcx, rax; Destination
0x14000a68e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14000a693  mov     r8, [r15+18h]
0x14000a697  mov     r9, r14
0x14000a69a  mov     rdx, rbx
0x14000a69d  mov     rcx, rax; Destination
0x14000a6a0  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x14000a6a5  sub     rbx, rax
0x14000a6a8  xor     edx, edx; Val
0x14000a6aa  mov     r8, rbx; Size
0x14000a6ad  mov     rcx, rax; void *
0x14000a6b0  call    memset_0
0x14000a6b5  add     rsp, 28h
0x14000a6b9  pop     r15
0x14000a6bb  pop     r14
0x14000a6bd  pop     r13
0x14000a6bf  pop     r12
0x14000a6c1  pop     rdi
0x14000a6c2  pop     rsi
0x14000a6c3  pop     rbp
0x14000a6c4  pop     rbx
0x14000a6c5  retn
```
