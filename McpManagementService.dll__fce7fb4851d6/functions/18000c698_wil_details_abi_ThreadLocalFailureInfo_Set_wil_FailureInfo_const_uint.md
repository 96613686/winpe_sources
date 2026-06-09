# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000c698`
- end: `0x18000c7ce`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000cb28`

## callees

- `0x1800045d8`
- `0x1800065ec`
- `0x180006664`
- `0x18000b030`
- `0x18000c3e8`
- `0x18000c408`
- `0x18000c698`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c755`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c755`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c747`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c747`

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
0x18000c698  push    rbx
0x18000c69a  push    rbp
0x18000c69b  push    rsi
0x18000c69c  push    rdi
0x18000c69d  push    r12
0x18000c69f  push    r13
0x18000c6a1  push    r14
0x18000c6a3  push    r15
0x18000c6a5  sub     rsp, 28h
0x18000c6a9  mov     [rcx+4], r8d
0x18000c6ad  lea     r14, [rcx+38h]
0x18000c6b1  mov     eax, [rdx+8]
0x18000c6b4  mov     rsi, rcx
0x18000c6b7  mov     [rcx+8], eax
0x18000c6ba  mov     r15, rdx
0x18000c6bd  mov     qword ptr [rcx+10h], 0
0x18000c6c5  movzx   eax, word ptr [rdx+40h]
0x18000c6c9  mov     [rcx+18h], ax
0x18000c6cd  mov     al, [rdx]
0x18000c6cf  mov     [rcx+1Ah], al
0x18000c6d2  mov     qword ptr [rcx+20h], 0
0x18000c6da  mov     rax, [rdx+88h]
0x18000c6e1  mov     [rcx+28h], rax
0x18000c6e5  mov     rax, [rdx+90h]
0x18000c6ec  mov     [rcx+30h], rax
0x18000c6f0  mov     qword ptr [r14], 0
0x18000c6f7  mov     rcx, [rdx+18h]; this
0x18000c6fb  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000c700  mov     rcx, [r15+38h]; this
0x18000c704  mov     rbp, rax
0x18000c707  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000c70c  mov     rcx, [r15+80h]; this
0x18000c713  add     rbp, rax
0x18000c716  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000c71b  add     rbp, rax
0x18000c71e  lea     rdi, [rsi+48h]
0x18000c722  cmp     qword ptr [rsi+40h], 0
0x18000c727  jz      short loc_18000C72E
0x18000c729  cmp     [rdi], rbp
0x18000c72c  jnb     short loc_18000C766
0x18000c72e  mov     rdx, rbp; dwBytes
0x18000c731  mov     ecx, 8; dwFlags
0x18000c736  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000c73b  mov     r14, rax
0x18000c73e  test    rax, rax
0x18000c741  jz      short loc_18000C762
0x18000c743  mov     rbx, [rsi+40h]
0x18000c747  call    cs:__imp_GetProcessHeap
0x18000c74d  mov     r8, rbx; lpMem
0x18000c750  xor     edx, edx; dwFlags
0x18000c752  mov     rcx, rax; hHeap
0x18000c755  call    cs:__imp_HeapFree
0x18000c75b  mov     [rsi+40h], r14
0x18000c75f  mov     [rdi], rbp
0x18000c762  lea     r14, [rsi+38h]
0x18000c766  mov     rcx, [rsi+40h]; Destination
0x18000c76a  test    rcx, rcx
0x18000c76d  jz      short loc_18000C7BD
0x18000c76f  mov     rbx, [rdi]
0x18000c772  lea     r9, [rsi+10h]
0x18000c776  mov     r8, [r15+38h]
0x18000c77a  add     rbx, rcx
0x18000c77d  mov     rdx, rbx
0x18000c780  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000c785  mov     r8, [r15+80h]
0x18000c78c  lea     r9, [rsi+20h]
0x18000c790  mov     rdx, rbx
0x18000c793  mov     rcx, rax; Destination
0x18000c796  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000c79b  mov     r8, [r15+18h]
0x18000c79f  mov     r9, r14
0x18000c7a2  mov     rdx, rbx
0x18000c7a5  mov     rcx, rax; Destination
0x18000c7a8  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18000c7ad  sub     rbx, rax
0x18000c7b0  xor     edx, edx; Val
0x18000c7b2  mov     r8, rbx; Size
0x18000c7b5  mov     rcx, rax; void *
0x18000c7b8  call    memset_0
0x18000c7bd  add     rsp, 28h
0x18000c7c1  pop     r15
0x18000c7c3  pop     r14
0x18000c7c5  pop     r13
0x18000c7c7  pop     r12
0x18000c7c9  pop     rdi
0x18000c7ca  pop     rsi
0x18000c7cb  pop     rbp
0x18000c7cc  pop     rbx
0x18000c7cd  retn
```
