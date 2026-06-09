# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180021340`
- end: `0x180021476`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800217c4`

## callees

- `0x18001c7a8`
- `0x18001d2bc`
- `0x18001d334`
- `0x180020244`
- `0x180020f1c`
- `0x180020f3c`
- `0x180021340`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800213ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800213ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800213fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800213fd`

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
0x180021340  push    rbx
0x180021342  push    rbp
0x180021343  push    rsi
0x180021344  push    rdi
0x180021345  push    r12
0x180021347  push    r13
0x180021349  push    r14
0x18002134b  push    r15
0x18002134d  sub     rsp, 28h
0x180021351  mov     [rcx+4], r8d
0x180021355  lea     r14, [rcx+38h]
0x180021359  mov     eax, [rdx+8]
0x18002135c  mov     rsi, rcx
0x18002135f  mov     [rcx+8], eax
0x180021362  mov     r15, rdx
0x180021365  mov     qword ptr [rcx+10h], 0
0x18002136d  movzx   eax, word ptr [rdx+40h]
0x180021371  mov     [rcx+18h], ax
0x180021375  mov     al, [rdx]
0x180021377  mov     [rcx+1Ah], al
0x18002137a  mov     qword ptr [rcx+20h], 0
0x180021382  mov     rax, [rdx+88h]
0x180021389  mov     [rcx+28h], rax
0x18002138d  mov     rax, [rdx+90h]
0x180021394  mov     [rcx+30h], rax
0x180021398  mov     qword ptr [r14], 0
0x18002139f  mov     rcx, [rdx+18h]; this
0x1800213a3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800213a8  mov     rcx, [r15+38h]; this
0x1800213ac  mov     rbp, rax
0x1800213af  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800213b4  mov     rcx, [r15+80h]; this
0x1800213bb  add     rbp, rax
0x1800213be  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800213c3  add     rbp, rax
0x1800213c6  lea     rdi, [rsi+48h]
0x1800213ca  cmp     qword ptr [rsi+40h], 0
0x1800213cf  jz      short loc_1800213D6
0x1800213d1  cmp     [rdi], rbp
0x1800213d4  jnb     short loc_18002140E
0x1800213d6  mov     rdx, rbp; dwBytes
0x1800213d9  mov     ecx, 8; dwFlags
0x1800213de  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800213e3  mov     r14, rax
0x1800213e6  test    rax, rax
0x1800213e9  jz      short loc_18002140A
0x1800213eb  mov     rbx, [rsi+40h]
0x1800213ef  call    cs:__imp_GetProcessHeap
0x1800213f5  mov     r8, rbx; lpMem
0x1800213f8  xor     edx, edx; dwFlags
0x1800213fa  mov     rcx, rax; hHeap
0x1800213fd  call    cs:__imp_HeapFree
0x180021403  mov     [rsi+40h], r14
0x180021407  mov     [rdi], rbp
0x18002140a  lea     r14, [rsi+38h]
0x18002140e  mov     rcx, [rsi+40h]; Destination
0x180021412  test    rcx, rcx
0x180021415  jz      short loc_180021465
0x180021417  mov     rbx, [rdi]
0x18002141a  lea     r9, [rsi+10h]
0x18002141e  mov     r8, [r15+38h]
0x180021422  add     rbx, rcx
0x180021425  mov     rdx, rbx
0x180021428  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18002142d  mov     r8, [r15+80h]
0x180021434  lea     r9, [rsi+20h]
0x180021438  mov     rdx, rbx
0x18002143b  mov     rcx, rax; Destination
0x18002143e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180021443  mov     r8, [r15+18h]
0x180021447  mov     r9, r14
0x18002144a  mov     rdx, rbx
0x18002144d  mov     rcx, rax; Destination
0x180021450  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180021455  sub     rbx, rax
0x180021458  xor     edx, edx; Val
0x18002145a  mov     r8, rbx; Size
0x18002145d  mov     rcx, rax; void *
0x180021460  call    memset_0
0x180021465  add     rsp, 28h
0x180021469  pop     r15
0x18002146b  pop     r14
0x18002146d  pop     r13
0x18002146f  pop     r12
0x180021471  pop     rdi
0x180021472  pop     rsi
0x180021473  pop     rbp
0x180021474  pop     rbx
0x180021475  retn
```
