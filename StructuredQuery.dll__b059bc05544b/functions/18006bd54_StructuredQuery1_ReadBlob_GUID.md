# StructuredQuery1::ReadBlob__GUID_

- ea: `0x18006bd54`
- end: `0x18006bde2`
- name: `StructuredQuery1::ReadBlob__GUID_`
- size: `142`
- prototype: `__int64 __fastcall(IStream *pstm)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003dc94`

## callees

- `0x18006bd54`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bdc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bdc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006bd8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006bd8f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18006bd6e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18006bda6`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18006bd6e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18006bda6`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::ReadBlob__GUID_(IStream *pstm, _DWORD *a2, _QWORD *a3)
{
  void *v4; // rdi
  HRESULT v7; // ebx
  unsigned __int64 v8; // rax
  ULONG v9; // ebx
  void *v10; // rax

  v4 = 0;
  v7 = IStream_Read(pstm, a2, 4u);
  if ( v7 >= 0 )
  {
    v8 = 16LL * (unsigned int)*a2;
    if ( v8 > 0xFFFFFFFF )
    {
      v7 = -2147024362;
    }
    else
    {
      v9 = 16 * *a2;
      v10 = CoTaskMemAlloc((unsigned int)v8);
      v4 = v10;
      if ( v10 )
      {
        v7 = IStream_Read(pstm, v10, v9);
        if ( v7 >= 0 )
          goto LABEL_9;
      }
      else
      {
        v7 = -2147024882;
      }
    }
  }
  CoTaskMemFree(v4);
  v4 = 0;
  *a2 = 0;
LABEL_9:
  *a3 = v4;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18006bd54  push    rbx
0x18006bd56  push    rbp
0x18006bd57  push    rsi
0x18006bd58  push    rdi
0x18006bd59  push    r14
0x18006bd5b  sub     rsp, 20h
0x18006bd5f  mov     rsi, r8
0x18006bd62  xor     edi, edi
0x18006bd64  mov     r14, rdx
0x18006bd67  mov     rbp, rcx
0x18006bd6a  lea     r8d, [rdi+4]; cb
0x18006bd6e  call    cs:__imp_IStream_Read
0x18006bd74  mov     ebx, eax
0x18006bd76  test    eax, eax
0x18006bd78  js      short loc_18006BDC0
0x18006bd7a  mov     eax, [r14]
0x18006bd7d  mov     ecx, 0FFFFFFFFh
0x18006bd82  shl     rax, 4
0x18006bd86  cmp     rax, rcx
0x18006bd89  ja      short loc_18006BDBB
0x18006bd8b  mov     ecx, eax; cb
0x18006bd8d  mov     ebx, eax
0x18006bd8f  call    cs:__imp_CoTaskMemAlloc
0x18006bd95  mov     rdi, rax
0x18006bd98  test    rax, rax
0x18006bd9b  jz      short loc_18006BDB4
0x18006bd9d  mov     r8d, ebx; cb
0x18006bda0  mov     rdx, rax; pv
0x18006bda3  mov     rcx, rbp; pstm
0x18006bda6  call    cs:__imp_IStream_Read
0x18006bdac  mov     ebx, eax
0x18006bdae  test    eax, eax
0x18006bdb0  js      short loc_18006BDC0
0x18006bdb2  jmp     short loc_18006BDD2
0x18006bdb4  mov     ebx, 8007000Eh
0x18006bdb9  jmp     short loc_18006BDC0
0x18006bdbb  mov     ebx, 80070216h
0x18006bdc0  mov     rcx, rdi; pv
0x18006bdc3  call    cs:__imp_CoTaskMemFree
0x18006bdc9  xor     edi, edi
0x18006bdcb  mov     dword ptr [r14], 0
0x18006bdd2  mov     [rsi], rdi
0x18006bdd5  mov     eax, ebx
0x18006bdd7  add     rsp, 20h
0x18006bddb  pop     r14
0x18006bddd  pop     rdi
0x18006bdde  pop     rsi
0x18006bddf  pop     rbp
0x18006bde0  pop     rbx
0x18006bde1  retn
```
