# StructuredQuery1::ReadBlob_long_

- ea: `0x18005bf14`
- end: `0x18005bfa2`
- name: `StructuredQuery1::ReadBlob_long_`
- size: `142`
- prototype: `__int64 __fastcall(IStream *pstm)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003dc94`

## callees

- `0x18005bf14`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005bf83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005bf83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005bf4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005bf4f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18005bf2e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18005bf66`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18005bf2e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18005bf66`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::ReadBlob_long_(IStream *pstm, _DWORD *a2, _QWORD *a3)
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
  v8 = 4LL * (unsigned int)*a2;
  if ( v8 > 0xFFFFFFFF )
  {
    v7 = -2147024362;
    goto LABEL_8;
  }
  v9 = 4 * *a2;
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
0x18005bf14  push    rbx
0x18005bf16  push    rbp
0x18005bf17  push    rsi
0x18005bf18  push    rdi
0x18005bf19  push    r14
0x18005bf1b  sub     rsp, 20h
0x18005bf1f  mov     rsi, r8
0x18005bf22  xor     edi, edi
0x18005bf24  mov     r14, rdx
0x18005bf27  mov     rbp, rcx
0x18005bf2a  lea     r8d, [rdi+4]; cb
0x18005bf2e  call    cs:__imp_IStream_Read
0x18005bf34  mov     ebx, eax
0x18005bf36  test    eax, eax
0x18005bf38  js      short loc_18005BF80
0x18005bf3a  mov     eax, [r14]
0x18005bf3d  mov     ecx, 0FFFFFFFFh
0x18005bf42  shl     rax, 2
0x18005bf46  cmp     rax, rcx
0x18005bf49  ja      short loc_18005BF7B
0x18005bf4b  mov     ecx, eax; cb
0x18005bf4d  mov     ebx, eax
0x18005bf4f  call    cs:__imp_CoTaskMemAlloc
0x18005bf55  mov     rdi, rax
0x18005bf58  test    rax, rax
0x18005bf5b  jz      short loc_18005BF74
0x18005bf5d  mov     r8d, ebx; cb
0x18005bf60  mov     rdx, rax; pv
0x18005bf63  mov     rcx, rbp; pstm
0x18005bf66  call    cs:__imp_IStream_Read
0x18005bf6c  mov     ebx, eax
0x18005bf6e  test    eax, eax
0x18005bf70  jns     short loc_18005BF92
0x18005bf72  jmp     short loc_18005BF80
0x18005bf74  mov     ebx, 8007000Eh
0x18005bf79  jmp     short loc_18005BF80
0x18005bf7b  mov     ebx, 80070216h
0x18005bf80  mov     rcx, rdi; pv
0x18005bf83  call    cs:__imp_CoTaskMemFree
0x18005bf89  xor     edi, edi
0x18005bf8b  mov     dword ptr [r14], 0
0x18005bf92  mov     [rsi], rdi
0x18005bf95  mov     eax, ebx
0x18005bf97  add     rsp, 20h
0x18005bf9b  pop     r14
0x18005bf9d  pop     rdi
0x18005bf9e  pop     rsi
0x18005bf9f  pop     rbp
0x18005bfa0  pop     rbx
0x18005bfa1  retn
```
