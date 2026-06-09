# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18005c430`
- end: `0x18005c573`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `323`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18005c57c`

## callees

- `0x18004dd14`
- `0x180056960`
- `0x1800569d8`
- `0x180057d74`
- `0x180057d98`
- `0x18005bc90`
- `0x18005c430`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005c4df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005c4df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005c4f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005c4f3`

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
0x18005c430  push    rbx
0x18005c432  push    rbp
0x18005c433  push    rsi
0x18005c434  push    rdi
0x18005c435  push    r12
0x18005c437  push    r13
0x18005c439  push    r14
0x18005c43b  push    r15
0x18005c43d  sub     rsp, 28h
0x18005c441  mov     [rcx+4], r8d
0x18005c445  lea     r14, [rcx+38h]
0x18005c449  mov     eax, [rdx+8]
0x18005c44c  mov     rsi, rcx
0x18005c44f  mov     [rcx+8], eax
0x18005c452  mov     r15, rdx
0x18005c455  mov     qword ptr [rcx+10h], 0
0x18005c45d  movzx   eax, word ptr [rdx+40h]
0x18005c461  mov     [rcx+18h], ax
0x18005c465  mov     al, [rdx]
0x18005c467  mov     [rcx+1Ah], al
0x18005c46a  mov     qword ptr [rcx+20h], 0
0x18005c472  mov     rax, [rdx+88h]
0x18005c479  mov     [rcx+28h], rax
0x18005c47d  mov     rax, [rdx+90h]
0x18005c484  mov     [rcx+30h], rax
0x18005c488  mov     qword ptr [r14], 0
0x18005c48f  mov     rcx, [rdx+18h]; this
0x18005c493  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18005c498  mov     rcx, [r15+38h]; this
0x18005c49c  mov     rbp, rax
0x18005c49f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18005c4a4  mov     rcx, [r15+80h]; this
0x18005c4ab  add     rbp, rax
0x18005c4ae  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18005c4b3  add     rbp, rax
0x18005c4b6  lea     rdi, [rsi+48h]
0x18005c4ba  cmp     qword ptr [rsi+40h], 0
0x18005c4bf  jz      short loc_18005C4C6
0x18005c4c1  cmp     [rdi], rbp
0x18005c4c4  jnb     short loc_18005C50A
0x18005c4c6  mov     rdx, rbp; dwBytes
0x18005c4c9  mov     ecx, 8; dwFlags
0x18005c4ce  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18005c4d3  mov     r14, rax
0x18005c4d6  test    rax, rax
0x18005c4d9  jz      short loc_18005C506
0x18005c4db  mov     rbx, [rsi+40h]
0x18005c4df  call    cs:__imp_GetProcessHeap
0x18005c4e6  nop     dword ptr [rax+rax+00h]
0x18005c4eb  mov     r8, rbx; lpMem
0x18005c4ee  xor     edx, edx; dwFlags
0x18005c4f0  mov     rcx, rax; hHeap
0x18005c4f3  call    cs:__imp_HeapFree
0x18005c4fa  nop     dword ptr [rax+rax+00h]
0x18005c4ff  mov     [rsi+40h], r14
0x18005c503  mov     [rdi], rbp
0x18005c506  lea     r14, [rsi+38h]
0x18005c50a  mov     rcx, [rsi+40h]; Destination
0x18005c50e  test    rcx, rcx
0x18005c511  jz      short loc_18005C561
0x18005c513  mov     rbx, [rdi]
0x18005c516  lea     r9, [rsi+10h]
0x18005c51a  mov     r8, [r15+38h]
0x18005c51e  add     rbx, rcx
0x18005c521  mov     rdx, rbx
0x18005c524  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18005c529  mov     r8, [r15+80h]
0x18005c530  lea     r9, [rsi+20h]
0x18005c534  mov     rdx, rbx
0x18005c537  mov     rcx, rax; Destination
0x18005c53a  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18005c53f  mov     r8, [r15+18h]
0x18005c543  mov     r9, r14
0x18005c546  mov     rdx, rbx
0x18005c549  mov     rcx, rax; Destination
0x18005c54c  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18005c551  sub     rbx, rax
0x18005c554  xor     edx, edx; Val
0x18005c556  mov     r8, rbx; Size
0x18005c559  mov     rcx, rax; void *
0x18005c55c  call    memset_0
0x18005c561  add     rsp, 28h
0x18005c565  pop     r15
0x18005c567  pop     r14
0x18005c569  pop     r13
0x18005c56b  pop     r12
0x18005c56d  pop     rdi
0x18005c56e  pop     rsi
0x18005c56f  pop     rbp
0x18005c570  pop     rbx
0x18005c571  retn
```
