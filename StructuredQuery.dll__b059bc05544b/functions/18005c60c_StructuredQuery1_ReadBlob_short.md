# StructuredQuery1::ReadBlob_short_

- ea: `0x18005c60c`
- end: `0x18005c699`
- name: `StructuredQuery1::ReadBlob_short_`
- size: `141`
- prototype: `__int64 __fastcall(IStream *pstm)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003dc94`

## callees

- `0x18005c60c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005c67a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005c67a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005c646`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005c646`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18005c626`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18005c65d`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18005c626`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18005c65d`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::ReadBlob_short_(IStream *pstm, _DWORD *a2, _QWORD *a3)
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
  v8 = 2LL * (unsigned int)*a2;
  if ( v8 > 0xFFFFFFFF )
  {
    v7 = -2147024362;
    goto LABEL_8;
  }
  v9 = 2 * *a2;
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
0x18005c60c  push    rbx
0x18005c60e  push    rbp
0x18005c60f  push    rsi
0x18005c610  push    rdi
0x18005c611  push    r14
0x18005c613  sub     rsp, 20h
0x18005c617  mov     rsi, r8
0x18005c61a  xor     edi, edi
0x18005c61c  mov     r14, rdx
0x18005c61f  mov     rbp, rcx
0x18005c622  lea     r8d, [rdi+4]; cb
0x18005c626  call    cs:__imp_IStream_Read
0x18005c62c  mov     ebx, eax
0x18005c62e  test    eax, eax
0x18005c630  js      short loc_18005C677
0x18005c632  mov     eax, [r14]
0x18005c635  mov     ecx, 0FFFFFFFFh
0x18005c63a  add     rax, rax
0x18005c63d  cmp     rax, rcx
0x18005c640  ja      short loc_18005C672
0x18005c642  mov     ecx, eax; cb
0x18005c644  mov     ebx, eax
0x18005c646  call    cs:__imp_CoTaskMemAlloc
0x18005c64c  mov     rdi, rax
0x18005c64f  test    rax, rax
0x18005c652  jz      short loc_18005C66B
0x18005c654  mov     r8d, ebx; cb
0x18005c657  mov     rdx, rax; pv
0x18005c65a  mov     rcx, rbp; pstm
0x18005c65d  call    cs:__imp_IStream_Read
0x18005c663  mov     ebx, eax
0x18005c665  test    eax, eax
0x18005c667  jns     short loc_18005C689
0x18005c669  jmp     short loc_18005C677
0x18005c66b  mov     ebx, 8007000Eh
0x18005c670  jmp     short loc_18005C677
0x18005c672  mov     ebx, 80070216h
0x18005c677  mov     rcx, rdi; pv
0x18005c67a  call    cs:__imp_CoTaskMemFree
0x18005c680  xor     edi, edi
0x18005c682  mov     dword ptr [r14], 0
0x18005c689  mov     [rsi], rdi
0x18005c68c  mov     eax, ebx
0x18005c68e  add     rsp, 20h
0x18005c692  pop     r14
0x18005c694  pop     rdi
0x18005c695  pop     rsi
0x18005c696  pop     rbp
0x18005c697  pop     rbx
0x18005c698  retn
```
