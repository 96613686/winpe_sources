# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000f4b8`
- end: `0x18000f5ee`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000f9dc`

## callees

- `0x1800021b8`
- `0x180007df8`
- `0x180007e70`
- `0x18000d618`
- `0x18000efe0`
- `0x18000f000`
- `0x18000f4b8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f575`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f575`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f567`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f567`

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
0x18000f4b8  push    rbx
0x18000f4ba  push    rbp
0x18000f4bb  push    rsi
0x18000f4bc  push    rdi
0x18000f4bd  push    r12
0x18000f4bf  push    r13
0x18000f4c1  push    r14
0x18000f4c3  push    r15
0x18000f4c5  sub     rsp, 28h
0x18000f4c9  mov     [rcx+4], r8d
0x18000f4cd  lea     r14, [rcx+38h]
0x18000f4d1  mov     eax, [rdx+8]
0x18000f4d4  mov     rsi, rcx
0x18000f4d7  mov     [rcx+8], eax
0x18000f4da  mov     r15, rdx
0x18000f4dd  mov     qword ptr [rcx+10h], 0
0x18000f4e5  movzx   eax, word ptr [rdx+40h]
0x18000f4e9  mov     [rcx+18h], ax
0x18000f4ed  mov     al, [rdx]
0x18000f4ef  mov     [rcx+1Ah], al
0x18000f4f2  mov     qword ptr [rcx+20h], 0
0x18000f4fa  mov     rax, [rdx+88h]
0x18000f501  mov     [rcx+28h], rax
0x18000f505  mov     rax, [rdx+90h]
0x18000f50c  mov     [rcx+30h], rax
0x18000f510  mov     qword ptr [r14], 0
0x18000f517  mov     rcx, [rdx+18h]; this
0x18000f51b  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000f520  mov     rcx, [r15+38h]; this
0x18000f524  mov     rbp, rax
0x18000f527  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000f52c  mov     rcx, [r15+80h]; this
0x18000f533  add     rbp, rax
0x18000f536  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000f53b  add     rbp, rax
0x18000f53e  lea     rdi, [rsi+48h]
0x18000f542  cmp     qword ptr [rsi+40h], 0
0x18000f547  jz      short loc_18000F54E
0x18000f549  cmp     [rdi], rbp
0x18000f54c  jnb     short loc_18000F586
0x18000f54e  mov     rdx, rbp; dwBytes
0x18000f551  mov     ecx, 8; dwFlags
0x18000f556  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000f55b  mov     r14, rax
0x18000f55e  test    rax, rax
0x18000f561  jz      short loc_18000F582
0x18000f563  mov     rbx, [rsi+40h]
0x18000f567  call    cs:__imp_GetProcessHeap
0x18000f56d  mov     r8, rbx; lpMem
0x18000f570  xor     edx, edx; dwFlags
0x18000f572  mov     rcx, rax; hHeap
0x18000f575  call    cs:__imp_HeapFree
0x18000f57b  mov     [rsi+40h], r14
0x18000f57f  mov     [rdi], rbp
0x18000f582  lea     r14, [rsi+38h]
0x18000f586  mov     rcx, [rsi+40h]; Destination
0x18000f58a  test    rcx, rcx
0x18000f58d  jz      short loc_18000F5DD
0x18000f58f  mov     rbx, [rdi]
0x18000f592  lea     r9, [rsi+10h]
0x18000f596  mov     r8, [r15+38h]
0x18000f59a  add     rbx, rcx
0x18000f59d  mov     rdx, rbx
0x18000f5a0  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000f5a5  mov     r8, [r15+80h]
0x18000f5ac  lea     r9, [rsi+20h]
0x18000f5b0  mov     rdx, rbx
0x18000f5b3  mov     rcx, rax; Destination
0x18000f5b6  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000f5bb  mov     r8, [r15+18h]
0x18000f5bf  mov     r9, r14
0x18000f5c2  mov     rdx, rbx
0x18000f5c5  mov     rcx, rax; Destination
0x18000f5c8  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18000f5cd  sub     rbx, rax
0x18000f5d0  xor     edx, edx; Val
0x18000f5d2  mov     r8, rbx; Size
0x18000f5d5  mov     rcx, rax; void *
0x18000f5d8  call    memset_0
0x18000f5dd  add     rsp, 28h
0x18000f5e1  pop     r15
0x18000f5e3  pop     r14
0x18000f5e5  pop     r13
0x18000f5e7  pop     r12
0x18000f5e9  pop     rdi
0x18000f5ea  pop     rsi
0x18000f5eb  pop     rbp
0x18000f5ec  pop     rbx
0x18000f5ed  retn
```
