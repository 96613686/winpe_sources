# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000e9b8`
- end: `0x18000eaee`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002c7f0`

## callees

- `0x18000e948`
- `0x18000e9b8`
- `0x18000ed50`
- `0x18000ed74`
- `0x18000f698`
- `0x18001f8d8`
- `0x18002aad0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ea75`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ea75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ea67`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ea67`

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
0x18000e9b8  push    rbx
0x18000e9ba  push    rbp
0x18000e9bb  push    rsi
0x18000e9bc  push    rdi
0x18000e9bd  push    r12
0x18000e9bf  push    r13
0x18000e9c1  push    r14
0x18000e9c3  push    r15
0x18000e9c5  sub     rsp, 28h
0x18000e9c9  mov     [rcx+4], r8d
0x18000e9cd  lea     r14, [rcx+38h]
0x18000e9d1  mov     eax, [rdx+8]
0x18000e9d4  mov     rsi, rcx
0x18000e9d7  mov     [rcx+8], eax
0x18000e9da  mov     r15, rdx
0x18000e9dd  mov     qword ptr [rcx+10h], 0
0x18000e9e5  movzx   eax, word ptr [rdx+40h]
0x18000e9e9  mov     [rcx+18h], ax
0x18000e9ed  mov     al, [rdx]
0x18000e9ef  mov     [rcx+1Ah], al
0x18000e9f2  mov     qword ptr [rcx+20h], 0
0x18000e9fa  mov     rax, [rdx+88h]
0x18000ea01  mov     [rcx+28h], rax
0x18000ea05  mov     rax, [rdx+90h]
0x18000ea0c  mov     [rcx+30h], rax
0x18000ea10  mov     qword ptr [r14], 0
0x18000ea17  mov     rcx, [rdx+18h]; this
0x18000ea1b  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000ea20  mov     rcx, [r15+38h]; this
0x18000ea24  mov     rbp, rax
0x18000ea27  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000ea2c  mov     rcx, [r15+80h]; this
0x18000ea33  add     rbp, rax
0x18000ea36  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000ea3b  add     rbp, rax
0x18000ea3e  lea     rdi, [rsi+48h]
0x18000ea42  cmp     qword ptr [rsi+40h], 0
0x18000ea47  jz      short loc_18000EA4E
0x18000ea49  cmp     [rdi], rbp
0x18000ea4c  jnb     short loc_18000EA86
0x18000ea4e  mov     rdx, rbp; dwBytes
0x18000ea51  mov     ecx, 8; dwFlags
0x18000ea56  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000ea5b  mov     r14, rax
0x18000ea5e  test    rax, rax
0x18000ea61  jz      short loc_18000EA82
0x18000ea63  mov     rbx, [rsi+40h]
0x18000ea67  call    cs:__imp_GetProcessHeap
0x18000ea6d  mov     r8, rbx; lpMem
0x18000ea70  xor     edx, edx; dwFlags
0x18000ea72  mov     rcx, rax; hHeap
0x18000ea75  call    cs:__imp_HeapFree
0x18000ea7b  mov     [rsi+40h], r14
0x18000ea7f  mov     [rdi], rbp
0x18000ea82  lea     r14, [rsi+38h]
0x18000ea86  mov     rcx, [rsi+40h]; Destination
0x18000ea8a  test    rcx, rcx
0x18000ea8d  jz      short loc_18000EADD
0x18000ea8f  mov     rbx, [rdi]
0x18000ea92  lea     r9, [rsi+10h]
0x18000ea96  mov     r8, [r15+38h]
0x18000ea9a  add     rbx, rcx
0x18000ea9d  mov     rdx, rbx
0x18000eaa0  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000eaa5  mov     r8, [r15+80h]
0x18000eaac  lea     r9, [rsi+20h]
0x18000eab0  mov     rdx, rbx
0x18000eab3  mov     rcx, rax; Destination
0x18000eab6  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000eabb  mov     r8, [r15+18h]
0x18000eabf  mov     r9, r14
0x18000eac2  mov     rdx, rbx
0x18000eac5  mov     rcx, rax; Destination
0x18000eac8  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18000eacd  sub     rbx, rax
0x18000ead0  xor     edx, edx; Val
0x18000ead2  mov     r8, rbx; Size
0x18000ead5  mov     rcx, rax; void *
0x18000ead8  call    memset_0
0x18000eadd  add     rsp, 28h
0x18000eae1  pop     r15
0x18000eae3  pop     r14
0x18000eae5  pop     r13
0x18000eae7  pop     r12
0x18000eae9  pop     rdi
0x18000eaea  pop     rsi
0x18000eaeb  pop     rbp
0x18000eaec  pop     rbx
0x18000eaed  retn
```
