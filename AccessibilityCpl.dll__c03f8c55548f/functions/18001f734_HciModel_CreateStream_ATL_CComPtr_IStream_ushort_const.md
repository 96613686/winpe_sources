# HciModel::CreateStream(ATL::CComPtr<IStream> &,ushort const *)

- ea: `0x18001f734`
- end: `0x18001f817`
- name: `?CreateStream@HciModel@@AEAAJAEAV?$CComPtr@UIStream@@@ATL@@PEBG@Z`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001fa7c`

## callees

- `0x18001f734`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001f801`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18001f801`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18001f7a2`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18001f7a2`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001f78c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001f78c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001f772`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001f7e8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001f772`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001f7e8`
- `KERNEL32!GlobalLock` at `0x18001f7b4`
- `KERNEL32!GlobalLock` at `0x18001f7b4`
- `KERNEL32!GlobalUnlock` at `0x18001f7f2`
- `KERNEL32!GlobalUnlock` at `0x18001f7f2`

## pseudocode

```c
HRESULT __fastcall HciModel::CreateStream(__int64 a1, LPSTREAM *a2, const WCHAR *a3)
{
  int v6; // eax
  SIZE_T cbMultiByte; // rdi
  void *v8; // rcx
  HGLOBAL v9; // rax
  CHAR *lpMultiByteStr; // rax

  v6 = WideCharToMultiByte(0, 0x400u, a3, -1, 0, 0, 0, 0);
  cbMultiByte = v6;
  if ( v6 <= 0 )
    return -2147467259;
  v8 = *(void **)(a1 + 56);
  if ( v8 )
  {
    GlobalFree(v8);
    *(_QWORD *)(a1 + 56) = 0;
  }
  v9 = GlobalAlloc(0x102u, cbMultiByte);
  *(_QWORD *)(a1 + 56) = v9;
  if ( !v9 )
    return -2147467259;
  lpMultiByteStr = (CHAR *)GlobalLock(v9);
  if ( !lpMultiByteStr )
    return -2147467259;
  WideCharToMultiByte(0, 0x400u, a3, -1, lpMultiByteStr, cbMultiByte, 0, 0);
  GlobalUnlock(*(HGLOBAL *)(a1 + 56));
  return CreateStreamOnHGlobal(*(HGLOBAL *)(a1 + 56), 0, a2);
}

```

## disassembly

```asm
0x18001f734  mov     rax, rsp
0x18001f737  push    rbx
0x18001f738  push    rbp
0x18001f739  push    rsi
0x18001f73a  push    rdi
0x18001f73b  sub     rsp, 48h
0x18001f73f  mov     qword ptr [rax-30h], 0
0x18001f747  mov     rbp, rdx
0x18001f74a  mov     qword ptr [rax-38h], 0
0x18001f752  mov     rbx, rcx
0x18001f755  mov     dword ptr [rax-40h], 0
0x18001f75c  or      r9d, 0FFFFFFFFh; cchWideChar
0x18001f760  mov     edx, 400h; dwFlags
0x18001f765  mov     qword ptr [rax-48h], 0
0x18001f76d  xor     ecx, ecx; CodePage
0x18001f76f  mov     rsi, r8
0x18001f772  call    cs:__imp_WideCharToMultiByte
0x18001f778  movsxd  rdi, eax
0x18001f77b  test    eax, eax
0x18001f77d  jle     loc_18001F809
0x18001f783  mov     rcx, [rbx+38h]; hMem
0x18001f787  test    rcx, rcx
0x18001f78a  jz      short loc_18001F79A
0x18001f78c  call    cs:__imp_GlobalFree
0x18001f792  mov     qword ptr [rbx+38h], 0
0x18001f79a  mov     rdx, rdi; dwBytes
0x18001f79d  mov     ecx, 102h; uFlags
0x18001f7a2  call    cs:__imp_GlobalAlloc
0x18001f7a8  mov     [rbx+38h], rax
0x18001f7ac  test    rax, rax
0x18001f7af  jz      short loc_18001F809
0x18001f7b1  mov     rcx, rax; hMem
0x18001f7b4  call    cs:__imp_GlobalLock
0x18001f7ba  test    rax, rax
0x18001f7bd  jz      short loc_18001F809
0x18001f7bf  mov     [rsp+68h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18001f7c8  or      r9d, 0FFFFFFFFh; cchWideChar
0x18001f7cc  mov     [rsp+68h+lpDefaultChar], 0; lpDefaultChar
0x18001f7d5  mov     r8, rsi; lpWideCharStr
0x18001f7d8  mov     [rsp+68h+cbMultiByte], edi; cbMultiByte
0x18001f7dc  mov     edx, 400h; dwFlags
0x18001f7e1  xor     ecx, ecx; CodePage
0x18001f7e3  mov     [rsp+68h+lpMultiByteStr], rax; lpMultiByteStr
0x18001f7e8  call    cs:__imp_WideCharToMultiByte
0x18001f7ee  mov     rcx, [rbx+38h]; hMem
0x18001f7f2  call    cs:__imp_GlobalUnlock
0x18001f7f8  mov     rcx, [rbx+38h]; hGlobal
0x18001f7fc  mov     r8, rbp; ppstm
0x18001f7ff  xor     edx, edx; fDeleteOnRelease
0x18001f801  call    cs:__imp_CreateStreamOnHGlobal
0x18001f807  jmp     short loc_18001F80E
0x18001f809  mov     eax, 80004005h
0x18001f80e  add     rsp, 48h
0x18001f812  pop     rdi
0x18001f813  pop     rsi
0x18001f814  pop     rbp
0x18001f815  pop     rbx
0x18001f816  retn
```
