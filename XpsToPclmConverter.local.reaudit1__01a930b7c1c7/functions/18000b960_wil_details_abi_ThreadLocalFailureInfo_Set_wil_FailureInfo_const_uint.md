# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000b960`
- end: `0x18000ba96`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000bde8`

## callees

- `0x180002148`
- `0x180008048`
- `0x1800080c0`
- `0x18000a9b0`
- `0x18000b7d8`
- `0x18000b7f8`
- `0x18000b960`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ba1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ba1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ba0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ba0f`

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
0x18000b960  push    rbx
0x18000b962  push    rbp
0x18000b963  push    rsi
0x18000b964  push    rdi
0x18000b965  push    r12
0x18000b967  push    r13
0x18000b969  push    r14
0x18000b96b  push    r15
0x18000b96d  sub     rsp, 28h
0x18000b971  mov     [rcx+4], r8d
0x18000b975  lea     r14, [rcx+38h]
0x18000b979  mov     eax, [rdx+8]
0x18000b97c  mov     rsi, rcx
0x18000b97f  mov     [rcx+8], eax
0x18000b982  mov     r15, rdx
0x18000b985  mov     qword ptr [rcx+10h], 0
0x18000b98d  movzx   eax, word ptr [rdx+40h]
0x18000b991  mov     [rcx+18h], ax
0x18000b995  mov     al, [rdx]
0x18000b997  mov     [rcx+1Ah], al
0x18000b99a  mov     qword ptr [rcx+20h], 0
0x18000b9a2  mov     rax, [rdx+88h]
0x18000b9a9  mov     [rcx+28h], rax
0x18000b9ad  mov     rax, [rdx+90h]
0x18000b9b4  mov     [rcx+30h], rax
0x18000b9b8  mov     qword ptr [r14], 0
0x18000b9bf  mov     rcx, [rdx+18h]; this
0x18000b9c3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000b9c8  mov     rcx, [r15+38h]; this
0x18000b9cc  mov     rbp, rax
0x18000b9cf  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000b9d4  mov     rcx, [r15+80h]; this
0x18000b9db  add     rbp, rax
0x18000b9de  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000b9e3  add     rbp, rax
0x18000b9e6  lea     rdi, [rsi+48h]
0x18000b9ea  cmp     qword ptr [rsi+40h], 0
0x18000b9ef  jz      short loc_18000B9F6
0x18000b9f1  cmp     [rdi], rbp
0x18000b9f4  jnb     short loc_18000BA2E
0x18000b9f6  mov     rdx, rbp; dwBytes
0x18000b9f9  mov     ecx, 8; dwFlags
0x18000b9fe  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000ba03  mov     r14, rax
0x18000ba06  test    rax, rax
0x18000ba09  jz      short loc_18000BA2A
0x18000ba0b  mov     rbx, [rsi+40h]
0x18000ba0f  call    cs:__imp_GetProcessHeap
0x18000ba15  mov     r8, rbx; lpMem
0x18000ba18  xor     edx, edx; dwFlags
0x18000ba1a  mov     rcx, rax; hHeap
0x18000ba1d  call    cs:__imp_HeapFree
0x18000ba23  mov     [rsi+40h], r14
0x18000ba27  mov     [rdi], rbp
0x18000ba2a  lea     r14, [rsi+38h]
0x18000ba2e  mov     rcx, [rsi+40h]; Destination
0x18000ba32  test    rcx, rcx
0x18000ba35  jz      short loc_18000BA85
0x18000ba37  mov     rbx, [rdi]
0x18000ba3a  lea     r9, [rsi+10h]
0x18000ba3e  mov     r8, [r15+38h]
0x18000ba42  add     rbx, rcx
0x18000ba45  mov     rdx, rbx
0x18000ba48  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000ba4d  mov     r8, [r15+80h]
0x18000ba54  lea     r9, [rsi+20h]
0x18000ba58  mov     rdx, rbx
0x18000ba5b  mov     rcx, rax; Destination
0x18000ba5e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000ba63  mov     r8, [r15+18h]
0x18000ba67  mov     r9, r14
0x18000ba6a  mov     rdx, rbx
0x18000ba6d  mov     rcx, rax; Destination
0x18000ba70  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18000ba75  sub     rbx, rax
0x18000ba78  xor     edx, edx; Val
0x18000ba7a  mov     r8, rbx; Size
0x18000ba7d  mov     rcx, rax; void *
0x18000ba80  call    memset_0
0x18000ba85  add     rsp, 28h
0x18000ba89  pop     r15
0x18000ba8b  pop     r14
0x18000ba8d  pop     r13
0x18000ba8f  pop     r12
0x18000ba91  pop     rdi
0x18000ba92  pop     rsi
0x18000ba93  pop     rbp
0x18000ba94  pop     rbx
0x18000ba95  retn
```
