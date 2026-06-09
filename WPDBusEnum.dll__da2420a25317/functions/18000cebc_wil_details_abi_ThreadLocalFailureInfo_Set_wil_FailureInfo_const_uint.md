# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000cebc`
- end: `0x18000cff2`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000d254`

## callees

- `0x18000a192`
- `0x18000b518`
- `0x18000b590`
- `0x18000cb5c`
- `0x18000cdd8`
- `0x18000cdf8`
- `0x18000cebc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cf79`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cf79`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cf6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cf6b`

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
0x18000cebc  push    rbx
0x18000cebe  push    rbp
0x18000cebf  push    rsi
0x18000cec0  push    rdi
0x18000cec1  push    r12
0x18000cec3  push    r13
0x18000cec5  push    r14
0x18000cec7  push    r15
0x18000cec9  sub     rsp, 28h
0x18000cecd  mov     [rcx+4], r8d
0x18000ced1  lea     r14, [rcx+38h]
0x18000ced5  mov     eax, [rdx+8]
0x18000ced8  mov     rsi, rcx
0x18000cedb  mov     [rcx+8], eax
0x18000cede  mov     r15, rdx
0x18000cee1  mov     qword ptr [rcx+10h], 0
0x18000cee9  movzx   eax, word ptr [rdx+40h]
0x18000ceed  mov     [rcx+18h], ax
0x18000cef1  mov     al, [rdx]
0x18000cef3  mov     [rcx+1Ah], al
0x18000cef6  mov     qword ptr [rcx+20h], 0
0x18000cefe  mov     rax, [rdx+88h]
0x18000cf05  mov     [rcx+28h], rax
0x18000cf09  mov     rax, [rdx+90h]
0x18000cf10  mov     [rcx+30h], rax
0x18000cf14  mov     qword ptr [r14], 0
0x18000cf1b  mov     rcx, [rdx+18h]; this
0x18000cf1f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000cf24  mov     rcx, [r15+38h]; this
0x18000cf28  mov     rbp, rax
0x18000cf2b  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000cf30  mov     rcx, [r15+80h]; this
0x18000cf37  add     rbp, rax
0x18000cf3a  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000cf3f  add     rbp, rax
0x18000cf42  lea     rdi, [rsi+48h]
0x18000cf46  cmp     qword ptr [rsi+40h], 0
0x18000cf4b  jz      short loc_18000CF52
0x18000cf4d  cmp     [rdi], rbp
0x18000cf50  jnb     short loc_18000CF8A
0x18000cf52  mov     rdx, rbp; dwBytes
0x18000cf55  mov     ecx, 8; dwFlags
0x18000cf5a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000cf5f  mov     r14, rax
0x18000cf62  test    rax, rax
0x18000cf65  jz      short loc_18000CF86
0x18000cf67  mov     rbx, [rsi+40h]
0x18000cf6b  call    cs:__imp_GetProcessHeap
0x18000cf71  mov     r8, rbx; lpMem
0x18000cf74  xor     edx, edx; dwFlags
0x18000cf76  mov     rcx, rax; hHeap
0x18000cf79  call    cs:__imp_HeapFree
0x18000cf7f  mov     [rsi+40h], r14
0x18000cf83  mov     [rdi], rbp
0x18000cf86  lea     r14, [rsi+38h]
0x18000cf8a  mov     rcx, [rsi+40h]; Destination
0x18000cf8e  test    rcx, rcx
0x18000cf91  jz      short loc_18000CFE1
0x18000cf93  mov     rbx, [rdi]
0x18000cf96  lea     r9, [rsi+10h]
0x18000cf9a  mov     r8, [r15+38h]
0x18000cf9e  add     rbx, rcx
0x18000cfa1  mov     rdx, rbx
0x18000cfa4  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000cfa9  mov     r8, [r15+80h]
0x18000cfb0  lea     r9, [rsi+20h]
0x18000cfb4  mov     rdx, rbx
0x18000cfb7  mov     rcx, rax; Destination
0x18000cfba  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000cfbf  mov     r8, [r15+18h]
0x18000cfc3  mov     r9, r14
0x18000cfc6  mov     rdx, rbx
0x18000cfc9  mov     rcx, rax; Destination
0x18000cfcc  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18000cfd1  sub     rbx, rax
0x18000cfd4  xor     edx, edx; Val
0x18000cfd6  mov     r8, rbx; Size
0x18000cfd9  mov     rcx, rax; void *
0x18000cfdc  call    memset_0
0x18000cfe1  add     rsp, 28h
0x18000cfe5  pop     r15
0x18000cfe7  pop     r14
0x18000cfe9  pop     r13
0x18000cfeb  pop     r12
0x18000cfed  pop     rdi
0x18000cfee  pop     rsi
0x18000cfef  pop     rbp
0x18000cff0  pop     rbx
0x18000cff1  retn
```
