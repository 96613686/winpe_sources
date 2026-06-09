# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180004c3c`
- end: `0x180004d72`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180004d78`

## callees

- `0x180002346`
- `0x180002ea8`
- `0x180002f20`
- `0x18000484c`
- `0x180004b68`
- `0x180004b88`
- `0x180004c3c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004cf9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004cf9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ceb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ceb`

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
0x180004c3c  push    rbx
0x180004c3e  push    rbp
0x180004c3f  push    rsi
0x180004c40  push    rdi
0x180004c41  push    r12
0x180004c43  push    r13
0x180004c45  push    r14
0x180004c47  push    r15
0x180004c49  sub     rsp, 28h
0x180004c4d  mov     [rcx+4], r8d
0x180004c51  lea     r14, [rcx+38h]
0x180004c55  mov     eax, [rdx+8]
0x180004c58  mov     rsi, rcx
0x180004c5b  mov     [rcx+8], eax
0x180004c5e  mov     r15, rdx
0x180004c61  mov     qword ptr [rcx+10h], 0
0x180004c69  movzx   eax, word ptr [rdx+40h]
0x180004c6d  mov     [rcx+18h], ax
0x180004c71  mov     al, [rdx]
0x180004c73  mov     [rcx+1Ah], al
0x180004c76  mov     qword ptr [rcx+20h], 0
0x180004c7e  mov     rax, [rdx+88h]
0x180004c85  mov     [rcx+28h], rax
0x180004c89  mov     rax, [rdx+90h]
0x180004c90  mov     [rcx+30h], rax
0x180004c94  mov     qword ptr [r14], 0
0x180004c9b  mov     rcx, [rdx+18h]; this
0x180004c9f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180004ca4  mov     rcx, [r15+38h]; this
0x180004ca8  mov     rbp, rax
0x180004cab  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180004cb0  mov     rcx, [r15+80h]; this
0x180004cb7  add     rbp, rax
0x180004cba  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180004cbf  add     rbp, rax
0x180004cc2  lea     rdi, [rsi+48h]
0x180004cc6  cmp     qword ptr [rsi+40h], 0
0x180004ccb  jz      short loc_180004CD2
0x180004ccd  cmp     [rdi], rbp
0x180004cd0  jnb     short loc_180004D0A
0x180004cd2  mov     rdx, rbp; dwBytes
0x180004cd5  mov     ecx, 8; dwFlags
0x180004cda  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004cdf  mov     r14, rax
0x180004ce2  test    rax, rax
0x180004ce5  jz      short loc_180004D06
0x180004ce7  mov     rbx, [rsi+40h]
0x180004ceb  call    cs:__imp_GetProcessHeap
0x180004cf1  mov     r8, rbx; lpMem
0x180004cf4  xor     edx, edx; dwFlags
0x180004cf6  mov     rcx, rax; hHeap
0x180004cf9  call    cs:__imp_HeapFree
0x180004cff  mov     [rsi+40h], r14
0x180004d03  mov     [rdi], rbp
0x180004d06  lea     r14, [rsi+38h]
0x180004d0a  mov     rcx, [rsi+40h]; Destination
0x180004d0e  test    rcx, rcx
0x180004d11  jz      short loc_180004D61
0x180004d13  mov     rbx, [rdi]
0x180004d16  lea     r9, [rsi+10h]
0x180004d1a  mov     r8, [r15+38h]
0x180004d1e  add     rbx, rcx
0x180004d21  mov     rdx, rbx
0x180004d24  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180004d29  mov     r8, [r15+80h]
0x180004d30  lea     r9, [rsi+20h]
0x180004d34  mov     rdx, rbx
0x180004d37  mov     rcx, rax; Destination
0x180004d3a  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180004d3f  mov     r8, [r15+18h]
0x180004d43  mov     r9, r14
0x180004d46  mov     rdx, rbx
0x180004d49  mov     rcx, rax; Destination
0x180004d4c  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180004d51  sub     rbx, rax
0x180004d54  xor     edx, edx; Val
0x180004d56  mov     r8, rbx; Size
0x180004d59  mov     rcx, rax; void *
0x180004d5c  call    memset_0
0x180004d61  add     rsp, 28h
0x180004d65  pop     r15
0x180004d67  pop     r14
0x180004d69  pop     r13
0x180004d6b  pop     r12
0x180004d6d  pop     rdi
0x180004d6e  pop     rsi
0x180004d6f  pop     rbp
0x180004d70  pop     rbx
0x180004d71  retn
```
