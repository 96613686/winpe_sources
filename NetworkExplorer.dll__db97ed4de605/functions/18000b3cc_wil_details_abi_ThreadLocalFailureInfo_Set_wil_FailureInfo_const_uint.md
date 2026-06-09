# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000b3cc`
- end: `0x18000b502`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000b78c`

## callees

- `0x180008688`
- `0x180008700`
- `0x18000abec`
- `0x18000b2e0`
- `0x18000b300`
- `0x18000b3cc`
- `0x18000f076`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b489`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b489`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b47b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b47b`

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
0x18000b3cc  push    rbx
0x18000b3ce  push    rbp
0x18000b3cf  push    rsi
0x18000b3d0  push    rdi
0x18000b3d1  push    r12
0x18000b3d3  push    r13
0x18000b3d5  push    r14
0x18000b3d7  push    r15
0x18000b3d9  sub     rsp, 28h
0x18000b3dd  mov     [rcx+4], r8d
0x18000b3e1  lea     r14, [rcx+38h]
0x18000b3e5  mov     eax, [rdx+8]
0x18000b3e8  mov     rsi, rcx
0x18000b3eb  mov     [rcx+8], eax
0x18000b3ee  mov     r15, rdx
0x18000b3f1  mov     qword ptr [rcx+10h], 0
0x18000b3f9  movzx   eax, word ptr [rdx+40h]
0x18000b3fd  mov     [rcx+18h], ax
0x18000b401  mov     al, [rdx]
0x18000b403  mov     [rcx+1Ah], al
0x18000b406  mov     qword ptr [rcx+20h], 0
0x18000b40e  mov     rax, [rdx+88h]
0x18000b415  mov     [rcx+28h], rax
0x18000b419  mov     rax, [rdx+90h]
0x18000b420  mov     [rcx+30h], rax
0x18000b424  mov     qword ptr [r14], 0
0x18000b42b  mov     rcx, [rdx+18h]; this
0x18000b42f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000b434  mov     rcx, [r15+38h]; this
0x18000b438  mov     rbp, rax
0x18000b43b  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000b440  mov     rcx, [r15+80h]; this
0x18000b447  add     rbp, rax
0x18000b44a  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000b44f  add     rbp, rax
0x18000b452  lea     rdi, [rsi+48h]
0x18000b456  cmp     qword ptr [rsi+40h], 0
0x18000b45b  jz      short loc_18000B462
0x18000b45d  cmp     [rdi], rbp
0x18000b460  jnb     short loc_18000B49A
0x18000b462  mov     rdx, rbp; dwBytes
0x18000b465  mov     ecx, 8; dwFlags
0x18000b46a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000b46f  mov     r14, rax
0x18000b472  test    rax, rax
0x18000b475  jz      short loc_18000B496
0x18000b477  mov     rbx, [rsi+40h]
0x18000b47b  call    cs:__imp_GetProcessHeap
0x18000b481  mov     r8, rbx; lpMem
0x18000b484  xor     edx, edx; dwFlags
0x18000b486  mov     rcx, rax; hHeap
0x18000b489  call    cs:__imp_HeapFree
0x18000b48f  mov     [rsi+40h], r14
0x18000b493  mov     [rdi], rbp
0x18000b496  lea     r14, [rsi+38h]
0x18000b49a  mov     rcx, [rsi+40h]; Destination
0x18000b49e  test    rcx, rcx
0x18000b4a1  jz      short loc_18000B4F1
0x18000b4a3  mov     rbx, [rdi]
0x18000b4a6  lea     r9, [rsi+10h]
0x18000b4aa  mov     r8, [r15+38h]
0x18000b4ae  add     rbx, rcx
0x18000b4b1  mov     rdx, rbx
0x18000b4b4  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000b4b9  mov     r8, [r15+80h]
0x18000b4c0  lea     r9, [rsi+20h]
0x18000b4c4  mov     rdx, rbx
0x18000b4c7  mov     rcx, rax; Destination
0x18000b4ca  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000b4cf  mov     r8, [r15+18h]
0x18000b4d3  mov     r9, r14
0x18000b4d6  mov     rdx, rbx
0x18000b4d9  mov     rcx, rax; Destination
0x18000b4dc  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18000b4e1  sub     rbx, rax
0x18000b4e4  xor     edx, edx; Val
0x18000b4e6  mov     r8, rbx; Size
0x18000b4e9  mov     rcx, rax; void *
0x18000b4ec  call    memset_0
0x18000b4f1  add     rsp, 28h
0x18000b4f5  pop     r15
0x18000b4f7  pop     r14
0x18000b4f9  pop     r13
0x18000b4fb  pop     r12
0x18000b4fd  pop     rdi
0x18000b4fe  pop     rsi
0x18000b4ff  pop     rbp
0x18000b500  pop     rbx
0x18000b501  retn
```
