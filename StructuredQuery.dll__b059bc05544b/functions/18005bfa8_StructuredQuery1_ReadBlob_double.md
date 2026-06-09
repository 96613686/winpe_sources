# StructuredQuery1::ReadBlob_double_

- ea: `0x18005bfa8`
- end: `0x18005c036`
- name: `StructuredQuery1::ReadBlob_double_`
- size: `142`
- prototype: `__int64 __fastcall(IStream *pstm)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003dc94`

## callees

- `0x18005bfa8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005c017`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005c017`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005bfe3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005bfe3`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18005bfc2`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18005bffa`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18005bfc2`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18005bffa`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::ReadBlob_double_(IStream *pstm, _DWORD *a2, _QWORD *a3)
{
  void *v4; // rdi
  HRESULT v7; // ebx
  unsigned __int64 v8; // rax
  ULONG v9; // ebx
  void *v10; // rax

  v4 = 0;
  v7 = IStream_Read(pstm, a2, 4u);
  if ( v7 < 0 )
    goto LABEL_8;
  v8 = 8LL * (unsigned int)*a2;
  if ( v8 > 0xFFFFFFFF )
  {
    v7 = -2147024362;
    goto LABEL_8;
  }
  v9 = 8 * *a2;
  v10 = CoTaskMemAlloc((unsigned int)v8);
  v4 = v10;
  if ( !v10 )
  {
    v7 = -2147024882;
LABEL_8:
    CoTaskMemFree(v4);
    v4 = 0;
    *a2 = 0;
    goto LABEL_9;
  }
  v7 = IStream_Read(pstm, v10, v9);
  if ( v7 < 0 )
    goto LABEL_8;
LABEL_9:
  *a3 = v4;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18005bfa8  push    rbx
0x18005bfaa  push    rbp
0x18005bfab  push    rsi
0x18005bfac  push    rdi
0x18005bfad  push    r14
0x18005bfaf  sub     rsp, 20h
0x18005bfb3  mov     rsi, r8
0x18005bfb6  xor     edi, edi
0x18005bfb8  mov     r14, rdx
0x18005bfbb  mov     rbp, rcx
0x18005bfbe  lea     r8d, [rdi+4]; cb
0x18005bfc2  call    cs:__imp_IStream_Read
0x18005bfc8  mov     ebx, eax
0x18005bfca  test    eax, eax
0x18005bfcc  js      short loc_18005C014
0x18005bfce  mov     eax, [r14]
0x18005bfd1  mov     ecx, 0FFFFFFFFh
0x18005bfd6  shl     rax, 3
0x18005bfda  cmp     rax, rcx
0x18005bfdd  ja      short loc_18005C00F
0x18005bfdf  mov     ecx, eax; cb
0x18005bfe1  mov     ebx, eax
0x18005bfe3  call    cs:__imp_CoTaskMemAlloc
0x18005bfe9  mov     rdi, rax
0x18005bfec  test    rax, rax
0x18005bfef  jz      short loc_18005C008
0x18005bff1  mov     r8d, ebx; cb
0x18005bff4  mov     rdx, rax; pv
0x18005bff7  mov     rcx, rbp; pstm
0x18005bffa  call    cs:__imp_IStream_Read
0x18005c000  mov     ebx, eax
0x18005c002  test    eax, eax
0x18005c004  jns     short loc_18005C026
0x18005c006  jmp     short loc_18005C014
0x18005c008  mov     ebx, 8007000Eh
0x18005c00d  jmp     short loc_18005C014
0x18005c00f  mov     ebx, 80070216h
0x18005c014  mov     rcx, rdi; pv
0x18005c017  call    cs:__imp_CoTaskMemFree
0x18005c01d  xor     edi, edi
0x18005c01f  mov     dword ptr [r14], 0
0x18005c026  mov     [rsi], rdi
0x18005c029  mov     eax, ebx
0x18005c02b  add     rsp, 20h
0x18005c02f  pop     r14
0x18005c031  pop     rdi
0x18005c032  pop     rsi
0x18005c033  pop     rbp
0x18005c034  pop     rbx
0x18005c035  retn
```
