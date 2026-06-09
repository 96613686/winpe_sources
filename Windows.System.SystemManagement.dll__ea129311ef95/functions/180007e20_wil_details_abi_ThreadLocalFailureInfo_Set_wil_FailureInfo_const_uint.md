# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180007e20`
- end: `0x180007f56`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800081b8`

## callees

- `0x18000399c`
- `0x180004920`
- `0x180004998`
- `0x1800078f8`
- `0x180007cec`
- `0x180007d0c`
- `0x180007e20`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007ecf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007ecf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007edd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007edd`

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
0x180007e20  push    rbx
0x180007e22  push    rbp
0x180007e23  push    rsi
0x180007e24  push    rdi
0x180007e25  push    r12
0x180007e27  push    r13
0x180007e29  push    r14
0x180007e2b  push    r15
0x180007e2d  sub     rsp, 28h
0x180007e31  mov     [rcx+4], r8d
0x180007e35  lea     r14, [rcx+38h]
0x180007e39  mov     eax, [rdx+8]
0x180007e3c  mov     rsi, rcx
0x180007e3f  mov     [rcx+8], eax
0x180007e42  mov     r15, rdx
0x180007e45  mov     qword ptr [rcx+10h], 0
0x180007e4d  movzx   eax, word ptr [rdx+40h]
0x180007e51  mov     [rcx+18h], ax
0x180007e55  mov     al, [rdx]
0x180007e57  mov     [rcx+1Ah], al
0x180007e5a  mov     qword ptr [rcx+20h], 0
0x180007e62  mov     rax, [rdx+88h]
0x180007e69  mov     [rcx+28h], rax
0x180007e6d  mov     rax, [rdx+90h]
0x180007e74  mov     [rcx+30h], rax
0x180007e78  mov     qword ptr [r14], 0
0x180007e7f  mov     rcx, [rdx+18h]; this
0x180007e83  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180007e88  mov     rcx, [r15+38h]; this
0x180007e8c  mov     rbp, rax
0x180007e8f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180007e94  mov     rcx, [r15+80h]; this
0x180007e9b  add     rbp, rax
0x180007e9e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180007ea3  add     rbp, rax
0x180007ea6  lea     rdi, [rsi+48h]
0x180007eaa  cmp     qword ptr [rsi+40h], 0
0x180007eaf  jz      short loc_180007EB6
0x180007eb1  cmp     [rdi], rbp
0x180007eb4  jnb     short loc_180007EEE
0x180007eb6  mov     rdx, rbp; dwBytes
0x180007eb9  mov     ecx, 8; dwFlags
0x180007ebe  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007ec3  mov     r14, rax
0x180007ec6  test    rax, rax
0x180007ec9  jz      short loc_180007EEA
0x180007ecb  mov     rbx, [rsi+40h]
0x180007ecf  call    cs:__imp_GetProcessHeap
0x180007ed5  mov     r8, rbx; lpMem
0x180007ed8  xor     edx, edx; dwFlags
0x180007eda  mov     rcx, rax; hHeap
0x180007edd  call    cs:__imp_HeapFree
0x180007ee3  mov     [rsi+40h], r14
0x180007ee7  mov     [rdi], rbp
0x180007eea  lea     r14, [rsi+38h]
0x180007eee  mov     rcx, [rsi+40h]; Destination
0x180007ef2  test    rcx, rcx
0x180007ef5  jz      short loc_180007F45
0x180007ef7  mov     rbx, [rdi]
0x180007efa  lea     r9, [rsi+10h]
0x180007efe  mov     r8, [r15+38h]
0x180007f02  add     rbx, rcx
0x180007f05  mov     rdx, rbx
0x180007f08  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180007f0d  mov     r8, [r15+80h]
0x180007f14  lea     r9, [rsi+20h]
0x180007f18  mov     rdx, rbx
0x180007f1b  mov     rcx, rax; Destination
0x180007f1e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180007f23  mov     r8, [r15+18h]
0x180007f27  mov     r9, r14
0x180007f2a  mov     rdx, rbx
0x180007f2d  mov     rcx, rax; Destination
0x180007f30  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180007f35  sub     rbx, rax
0x180007f38  xor     edx, edx; Val
0x180007f3a  mov     r8, rbx; Size
0x180007f3d  mov     rcx, rax; void *
0x180007f40  call    memset_0
0x180007f45  add     rsp, 28h
0x180007f49  pop     r15
0x180007f4b  pop     r14
0x180007f4d  pop     r13
0x180007f4f  pop     r12
0x180007f51  pop     rdi
0x180007f52  pop     rsi
0x180007f53  pop     rbp
0x180007f54  pop     rbx
0x180007f55  retn
```
