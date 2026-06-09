# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180027edc`
- end: `0x180028012`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180028274`

## callees

- `0x18000a074`
- `0x180026b68`
- `0x180026be0`
- `0x180027c58`
- `0x180027df4`
- `0x180027e14`
- `0x180027edc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027f8b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027f8b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027f99`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027f99`

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
0x180027edc  push    rbx
0x180027ede  push    rbp
0x180027edf  push    rsi
0x180027ee0  push    rdi
0x180027ee1  push    r12
0x180027ee3  push    r13
0x180027ee5  push    r14
0x180027ee7  push    r15
0x180027ee9  sub     rsp, 28h
0x180027eed  mov     [rcx+4], r8d
0x180027ef1  lea     r14, [rcx+38h]
0x180027ef5  mov     eax, [rdx+8]
0x180027ef8  mov     rsi, rcx
0x180027efb  mov     [rcx+8], eax
0x180027efe  mov     r15, rdx
0x180027f01  mov     qword ptr [rcx+10h], 0
0x180027f09  movzx   eax, word ptr [rdx+40h]
0x180027f0d  mov     [rcx+18h], ax
0x180027f11  mov     al, [rdx]
0x180027f13  mov     [rcx+1Ah], al
0x180027f16  mov     qword ptr [rcx+20h], 0
0x180027f1e  mov     rax, [rdx+88h]
0x180027f25  mov     [rcx+28h], rax
0x180027f29  mov     rax, [rdx+90h]
0x180027f30  mov     [rcx+30h], rax
0x180027f34  mov     qword ptr [r14], 0
0x180027f3b  mov     rcx, [rdx+18h]; this
0x180027f3f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180027f44  mov     rcx, [r15+38h]; this
0x180027f48  mov     rbp, rax
0x180027f4b  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180027f50  mov     rcx, [r15+80h]; this
0x180027f57  add     rbp, rax
0x180027f5a  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180027f5f  add     rbp, rax
0x180027f62  lea     rdi, [rsi+48h]
0x180027f66  cmp     qword ptr [rsi+40h], 0
0x180027f6b  jz      short loc_180027F72
0x180027f6d  cmp     [rdi], rbp
0x180027f70  jnb     short loc_180027FAA
0x180027f72  mov     rdx, rbp; dwBytes
0x180027f75  mov     ecx, 8; dwFlags
0x180027f7a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180027f7f  mov     r14, rax
0x180027f82  test    rax, rax
0x180027f85  jz      short loc_180027FA6
0x180027f87  mov     rbx, [rsi+40h]
0x180027f8b  call    cs:__imp_GetProcessHeap
0x180027f91  mov     r8, rbx; lpMem
0x180027f94  xor     edx, edx; dwFlags
0x180027f96  mov     rcx, rax; hHeap
0x180027f99  call    cs:__imp_HeapFree
0x180027f9f  mov     [rsi+40h], r14
0x180027fa3  mov     [rdi], rbp
0x180027fa6  lea     r14, [rsi+38h]
0x180027faa  mov     rcx, [rsi+40h]; Destination
0x180027fae  test    rcx, rcx
0x180027fb1  jz      short loc_180028001
0x180027fb3  mov     rbx, [rdi]
0x180027fb6  lea     r9, [rsi+10h]
0x180027fba  mov     r8, [r15+38h]
0x180027fbe  add     rbx, rcx
0x180027fc1  mov     rdx, rbx
0x180027fc4  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180027fc9  mov     r8, [r15+80h]
0x180027fd0  lea     r9, [rsi+20h]
0x180027fd4  mov     rdx, rbx
0x180027fd7  mov     rcx, rax; Destination
0x180027fda  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180027fdf  mov     r8, [r15+18h]
0x180027fe3  mov     r9, r14
0x180027fe6  mov     rdx, rbx
0x180027fe9  mov     rcx, rax; Destination
0x180027fec  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180027ff1  sub     rbx, rax
0x180027ff4  xor     edx, edx; Val
0x180027ff6  mov     r8, rbx; Size
0x180027ff9  mov     rcx, rax; void *
0x180027ffc  call    memset_0
0x180028001  add     rsp, 28h
0x180028005  pop     r15
0x180028007  pop     r14
0x180028009  pop     r13
0x18002800b  pop     r12
0x18002800d  pop     rdi
0x18002800e  pop     rsi
0x18002800f  pop     rbp
0x180028010  pop     rbx
0x180028011  retn
```
