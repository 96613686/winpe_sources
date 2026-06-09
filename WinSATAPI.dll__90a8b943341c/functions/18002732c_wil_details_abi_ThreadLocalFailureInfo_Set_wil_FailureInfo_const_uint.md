# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18002732c`
- end: `0x18002747d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `337`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180027800`

## callees

- `0x180013e69`
- `0x180022818`
- `0x180022894`
- `0x1800263fc`
- `0x180027118`
- `0x180027144`
- `0x18002732c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800273f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800273f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800273dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800273dd`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  int v3; // eax
  __int64 v6; // rax
  unsigned __int64 v7; // rbp
  const char *v8; // rdx
  unsigned __int64 v9; // rbp
  const char *v10; // rdx
  SIZE_T v11; // rbp
  SIZE_T *v12; // rdi
  LPVOID v13; // r14
  void *v14; // rbx
  HANDLE ProcessHeap; // rax
  char *v16; // rcx
  char *v17; // rbx
  void *v18; // rax
  void *v19; // rax
  void *v20; // rax

  *((_DWORD *)this + 1) = a3;
  v3 = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 2) = v3;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  LOBYTE(v3) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_BYTE *)this + 26) = v3;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  v6 = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 6) = v6;
  v7 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const unsigned __int16 *)a2);
  v9 = wil::details::ResultStringSize(*((wil::details **)a2 + 7), v8) + v7;
  v11 = wil::details::ResultStringSize(*((wil::details **)a2 + 16), v10) + v9;
  v12 = (SIZE_T *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v12 < v11 )
  {
    v13 = wil::details::ProcessHeapAlloc(8u, v11);
    if ( v13 )
    {
      v14 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v14);
      *((_QWORD *)this + 8) = v13;
      *v12 = v11;
    }
  }
  v16 = (char *)*((_QWORD *)this + 8);
  if ( v16 )
  {
    v17 = &v16[*v12];
    v18 = (void *)wil::details::WriteResultString<char const *>(v16);
    v19 = (void *)wil::details::WriteResultString<char const *>(v18);
    v20 = (void *)wil::details::WriteResultString<unsigned short const *>(v19);
    memset_0(v20, 0, v17 - (_BYTE *)v20);
  }
}

```

## disassembly

```asm
0x18002732c  mov     [rsp+arg_0], rbx
0x180027331  mov     [rsp+arg_8], rbp
0x180027336  mov     [rsp+arg_10], rsi
0x18002733b  push    rdi
0x18002733c  push    r12
0x18002733e  push    r13
0x180027340  push    r14
0x180027342  push    r15
0x180027344  sub     rsp, 20h
0x180027348  mov     [rcx+4], r8d
0x18002734c  lea     r14, [rcx+38h]
0x180027350  mov     eax, [rdx+8]
0x180027353  mov     rsi, rcx
0x180027356  and     qword ptr [rcx+10h], 0
0x18002735b  mov     r15, rdx
0x18002735e  mov     [rcx+8], eax
0x180027361  movzx   eax, word ptr [rdx+40h]
0x180027365  mov     [rcx+18h], ax
0x180027369  mov     al, [rdx]
0x18002736b  and     qword ptr [rcx+20h], 0
0x180027370  mov     [rcx+1Ah], al
0x180027373  mov     rax, [rdx+88h]
0x18002737a  mov     [rcx+28h], rax
0x18002737e  mov     rax, [rdx+90h]
0x180027385  and     qword ptr [r14], 0
0x180027389  mov     [rcx+30h], rax
0x18002738d  mov     rcx, [rdx+18h]; this
0x180027391  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180027396  mov     rcx, [r15+38h]; this
0x18002739a  mov     rbp, rax
0x18002739d  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800273a2  mov     rcx, [r15+80h]; this
0x1800273a9  add     rbp, rax
0x1800273ac  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800273b1  add     rbp, rax
0x1800273b4  lea     rdi, [rsi+48h]
0x1800273b8  cmp     qword ptr [rsi+40h], 0
0x1800273bd  jz      short loc_1800273C4
0x1800273bf  cmp     [rdi], rbp
0x1800273c2  jnb     short loc_180027408
0x1800273c4  mov     rdx, rbp; dwBytes
0x1800273c7  mov     ecx, 8; dwFlags
0x1800273cc  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800273d1  mov     r14, rax
0x1800273d4  test    rax, rax
0x1800273d7  jz      short loc_180027404
0x1800273d9  mov     rbx, [rsi+40h]
0x1800273dd  call    cs:__imp_GetProcessHeap
0x1800273e4  nop     dword ptr [rax+rax+00h]
0x1800273e9  mov     r8, rbx; lpMem
0x1800273ec  xor     edx, edx; dwFlags
0x1800273ee  mov     rcx, rax; hHeap
0x1800273f1  call    cs:__imp_HeapFree
0x1800273f8  nop     dword ptr [rax+rax+00h]
0x1800273fd  mov     [rsi+40h], r14
0x180027401  mov     [rdi], rbp
0x180027404  lea     r14, [rsi+38h]
0x180027408  mov     rcx, [rsi+40h]; Destination
0x18002740c  test    rcx, rcx
0x18002740f  jz      short loc_18002745F
0x180027411  mov     rbx, [rdi]
0x180027414  lea     r9, [rsi+10h]
0x180027418  mov     r8, [r15+38h]
0x18002741c  add     rbx, rcx
0x18002741f  mov     rdx, rbx
0x180027422  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180027427  mov     r8, [r15+80h]
0x18002742e  lea     r9, [rsi+20h]
0x180027432  mov     rdx, rbx
0x180027435  mov     rcx, rax; Destination
0x180027438  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18002743d  mov     r8, [r15+18h]
0x180027441  mov     r9, r14
0x180027444  mov     rdx, rbx
0x180027447  mov     rcx, rax; Destination
0x18002744a  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18002744f  sub     rbx, rax
0x180027452  xor     edx, edx; Val
0x180027454  mov     r8, rbx; Size
0x180027457  mov     rcx, rax; void *
0x18002745a  call    memset_0
0x18002745f  mov     rbx, [rsp+48h+arg_0]
0x180027464  mov     rbp, [rsp+48h+arg_8]
0x180027469  mov     rsi, [rsp+48h+arg_10]
0x18002746e  add     rsp, 20h
0x180027472  pop     r15
0x180027474  pop     r14
0x180027476  pop     r13
0x180027478  pop     r12
0x18002747a  pop     rdi
0x18002747b  retn
```
