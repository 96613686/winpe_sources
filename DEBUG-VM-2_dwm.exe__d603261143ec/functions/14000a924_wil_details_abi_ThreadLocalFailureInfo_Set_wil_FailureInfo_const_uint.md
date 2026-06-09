# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x14000a924`
- end: `0x14000aa94`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `368`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14000ab88`

## callees

- `0x1400061b8`
- `0x1400072fc`
- `0x140009b40`
- `0x14000a7c8`
- `0x14000a7e8`
- `0x14000a924`
- `0x14000bebc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a9cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a9cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a9da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a9da`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  _QWORD *v3; // rsi
  unsigned __int64 v6; // r15
  const char *v7; // rdx
  unsigned __int64 v8; // r15
  const char *v9; // rdx
  SIZE_T v10; // r15
  SIZE_T *v11; // rdi
  LPVOID v12; // r12
  void *v13; // rbx
  HANDLE ProcessHeap; // rax
  char *v15; // rcx
  char *v16; // rdi
  void *v17; // rax
  const unsigned __int16 *v18; // rdx
  char *v19; // rbx
  wil::details *v20; // rcx
  rsize_t v21; // rax
  const void *v22; // rcx
  rsize_t v23; // r14

  *((_DWORD *)this + 1) = a3;
  v3 = (_QWORD *)((char *)this + 56);
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
  }
  v15 = (char *)*((_QWORD *)this + 8);
  if ( v15 )
  {
    v16 = &v15[*v11];
    v17 = (void *)wil::details::WriteResultString<char const *>(v15);
    v19 = (char *)wil::details::WriteResultString<char const *>(v17);
    if ( v19 != v16
      && (v20 = (wil::details *)*((_QWORD *)a2 + 3)) != 0
      && *(_WORD *)v20
      && (v21 = wil::details::ResultStringSize(v20, v18), v23 = v21, v16 - v19 >= v21) )
    {
      memcpy_s(v19, v16 - v19, v22, v21);
      if ( v3 )
        *v3 = v19;
      v19 += v23;
    }
    else if ( v3 )
    {
      *v3 = 0;
    }
    memset_0(v19, 0, v16 - v19);
  }
}

```

## disassembly

```asm
0x14000a924  push    rbx
0x14000a926  push    rbp
0x14000a927  push    rsi
0x14000a928  push    rdi
0x14000a929  push    r12
0x14000a92b  push    r13
0x14000a92d  push    r14
0x14000a92f  push    r15
0x14000a931  sub     rsp, 28h
0x14000a935  mov     [rcx+4], r8d
0x14000a939  lea     rbx, [rcx+20h]
0x14000a93d  mov     eax, [rdx+8]
0x14000a940  lea     rsi, [rcx+38h]
0x14000a944  mov     [rcx+8], eax
0x14000a947  xor     r12d, r12d
0x14000a94a  mov     [rcx+10h], r12
0x14000a94e  mov     rbp, rcx
0x14000a951  movzx   eax, word ptr [rdx+40h]
0x14000a955  mov     r14, rdx
0x14000a958  mov     [rcx+18h], ax
0x14000a95c  mov     al, [rdx]
0x14000a95e  mov     [rcx+1Ah], al
0x14000a961  mov     [rbx], r12
0x14000a964  mov     rax, [rdx+88h]
0x14000a96b  mov     [rcx+28h], rax
0x14000a96f  mov     rax, [rdx+90h]
0x14000a976  mov     [rcx+30h], rax
0x14000a97a  mov     [rsi], r12
0x14000a97d  mov     rcx, [rdx+18h]; this
0x14000a981  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x14000a986  mov     rcx, [r14+38h]; this
0x14000a98a  mov     r15, rax
0x14000a98d  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x14000a992  mov     rcx, [r14+80h]; this
0x14000a999  add     r15, rax
0x14000a99c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x14000a9a1  add     r15, rax
0x14000a9a4  lea     rdi, [rbp+48h]
0x14000a9a8  cmp     [rbp+40h], r12
0x14000a9ac  jz      short loc_14000A9B3
0x14000a9ae  cmp     [rdi], r15
0x14000a9b1  jnb     short loc_14000A9EE
0x14000a9b3  mov     rdx, r15; dwBytes
0x14000a9b6  mov     ecx, 8; dwFlags
0x14000a9bb  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000a9c0  mov     r12, rax
0x14000a9c3  test    rax, rax
0x14000a9c6  jz      short loc_14000A9EB
0x14000a9c8  mov     rbx, [rbp+40h]
0x14000a9cc  call    cs:__imp_GetProcessHeap
0x14000a9d2  mov     r8, rbx; lpMem
0x14000a9d5  xor     edx, edx; dwFlags
0x14000a9d7  mov     rcx, rax; hHeap
0x14000a9da  call    cs:__imp_HeapFree
0x14000a9e0  mov     [rbp+40h], r12
0x14000a9e4  lea     rbx, [rbp+20h]
0x14000a9e8  mov     [rdi], r15
0x14000a9eb  xor     r12d, r12d
0x14000a9ee  mov     rcx, [rbp+40h]; Destination
0x14000a9f2  test    rcx, rcx
0x14000a9f5  jz      loc_14000AA83
0x14000a9fb  mov     rdi, [rdi]
0x14000a9fe  lea     r9, [rbp+10h]
0x14000aa02  mov     r8, [r14+38h]
0x14000aa06  add     rdi, rcx
0x14000aa09  mov     rdx, rdi
0x14000aa0c  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14000aa11  mov     r8, [r14+80h]
0x14000aa18  mov     r9, rbx
0x14000aa1b  mov     rdx, rdi
0x14000aa1e  mov     rcx, rax; Destination
0x14000aa21  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14000aa26  mov     rbx, rax
0x14000aa29  cmp     rax, rdi
0x14000aa2c  jz      short loc_14000AA6B
0x14000aa2e  mov     rcx, [r14+18h]; this
0x14000aa32  test    rcx, rcx
0x14000aa35  jz      short loc_14000AA6B
0x14000aa37  cmp     [rcx], r12w
0x14000aa3b  jz      short loc_14000AA6B
0x14000aa3d  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x14000aa42  mov     rdx, rdi
0x14000aa45  mov     r14, rax
0x14000aa48  sub     rdx, rbx; DestinationSize
0x14000aa4b  cmp     rdx, rax
0x14000aa4e  jb      short loc_14000AA6B
0x14000aa50  mov     r8, rcx; Source
0x14000aa53  mov     r9, rax; SourceSize
0x14000aa56  mov     rcx, rbx; Destination
0x14000aa59  call    memcpy_s
0x14000aa5e  test    rsi, rsi
0x14000aa61  jz      short loc_14000AA66
0x14000aa63  mov     [rsi], rbx
0x14000aa66  add     rbx, r14
0x14000aa69  jmp     short loc_14000AA73
0x14000aa6b  test    rsi, rsi
0x14000aa6e  jz      short loc_14000AA73
0x14000aa70  mov     [rsi], r12
0x14000aa73  sub     rdi, rbx
0x14000aa76  xor     edx, edx; Val
0x14000aa78  mov     r8, rdi; Size
0x14000aa7b  mov     rcx, rbx; void *
0x14000aa7e  call    memset_0
0x14000aa83  add     rsp, 28h
0x14000aa87  pop     r15
0x14000aa89  pop     r14
0x14000aa8b  pop     r13
0x14000aa8d  pop     r12
0x14000aa8f  pop     rdi
0x14000aa90  pop     rsi
0x14000aa91  pop     rbp
0x14000aa92  pop     rbx
0x14000aa93  retn
```
