# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180014850`
- end: `0x180014986`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180014cd8`

## callees

- `0x180011148`
- `0x1800111c0`
- `0x1800139e8`
- `0x1800146c8`
- `0x1800146e8`
- `0x180014850`
- `0x180020c02`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800148ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800148ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001490d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001490d`

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
0x180014850  push    rbx
0x180014852  push    rbp
0x180014853  push    rsi
0x180014854  push    rdi
0x180014855  push    r12
0x180014857  push    r13
0x180014859  push    r14
0x18001485b  push    r15
0x18001485d  sub     rsp, 28h
0x180014861  mov     [rcx+4], r8d
0x180014865  lea     r14, [rcx+38h]
0x180014869  mov     eax, [rdx+8]
0x18001486c  mov     rsi, rcx
0x18001486f  mov     [rcx+8], eax
0x180014872  mov     r15, rdx
0x180014875  mov     qword ptr [rcx+10h], 0
0x18001487d  movzx   eax, word ptr [rdx+40h]
0x180014881  mov     [rcx+18h], ax
0x180014885  mov     al, [rdx]
0x180014887  mov     [rcx+1Ah], al
0x18001488a  mov     qword ptr [rcx+20h], 0
0x180014892  mov     rax, [rdx+88h]
0x180014899  mov     [rcx+28h], rax
0x18001489d  mov     rax, [rdx+90h]
0x1800148a4  mov     [rcx+30h], rax
0x1800148a8  mov     qword ptr [r14], 0
0x1800148af  mov     rcx, [rdx+18h]; this
0x1800148b3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800148b8  mov     rcx, [r15+38h]; this
0x1800148bc  mov     rbp, rax
0x1800148bf  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800148c4  mov     rcx, [r15+80h]; this
0x1800148cb  add     rbp, rax
0x1800148ce  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800148d3  add     rbp, rax
0x1800148d6  lea     rdi, [rsi+48h]
0x1800148da  cmp     qword ptr [rsi+40h], 0
0x1800148df  jz      short loc_1800148E6
0x1800148e1  cmp     [rdi], rbp
0x1800148e4  jnb     short loc_18001491E
0x1800148e6  mov     rdx, rbp; dwBytes
0x1800148e9  mov     ecx, 8; dwFlags
0x1800148ee  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800148f3  mov     r14, rax
0x1800148f6  test    rax, rax
0x1800148f9  jz      short loc_18001491A
0x1800148fb  mov     rbx, [rsi+40h]
0x1800148ff  call    cs:__imp_GetProcessHeap
0x180014905  mov     r8, rbx; lpMem
0x180014908  xor     edx, edx; dwFlags
0x18001490a  mov     rcx, rax; hHeap
0x18001490d  call    cs:__imp_HeapFree
0x180014913  mov     [rsi+40h], r14
0x180014917  mov     [rdi], rbp
0x18001491a  lea     r14, [rsi+38h]
0x18001491e  mov     rcx, [rsi+40h]; Destination
0x180014922  test    rcx, rcx
0x180014925  jz      short loc_180014975
0x180014927  mov     rbx, [rdi]
0x18001492a  lea     r9, [rsi+10h]
0x18001492e  mov     r8, [r15+38h]
0x180014932  add     rbx, rcx
0x180014935  mov     rdx, rbx
0x180014938  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18001493d  mov     r8, [r15+80h]
0x180014944  lea     r9, [rsi+20h]
0x180014948  mov     rdx, rbx
0x18001494b  mov     rcx, rax; Destination
0x18001494e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180014953  mov     r8, [r15+18h]
0x180014957  mov     r9, r14
0x18001495a  mov     rdx, rbx
0x18001495d  mov     rcx, rax; Destination
0x180014960  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180014965  sub     rbx, rax
0x180014968  xor     edx, edx; Val
0x18001496a  mov     r8, rbx; Size
0x18001496d  mov     rcx, rax; void *
0x180014970  call    memset_0
0x180014975  add     rsp, 28h
0x180014979  pop     r15
0x18001497b  pop     r14
0x18001497d  pop     r13
0x18001497f  pop     r12
0x180014981  pop     rdi
0x180014982  pop     rsi
0x180014983  pop     rbp
0x180014984  pop     rbx
0x180014985  retn
```
