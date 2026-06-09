# StructuredQuery1::ReadBlob_unsigned_char_

- ea: `0x18006bcd4`
- end: `0x18006bd4b`
- name: `StructuredQuery1::ReadBlob_unsigned_char_`
- size: `119`
- prototype: `__int64 __fastcall(IStream *pstm)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003dc94`

## callees

- `0x18006bcd4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bd2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bd2c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006bcff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006bcff`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18006bcee`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18006bd16`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18006bcee`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18006bd16`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::ReadBlob_unsigned_char_(IStream *pstm, ULONG *a2, _QWORD *a3)
{
  void *v4; // rbx
  HRESULT v7; // edi
  ULONG v8; // edi
  void *v9; // rax

  v4 = 0;
  v7 = IStream_Read(pstm, a2, 4u);
  if ( v7 >= 0 )
  {
    v8 = *a2;
    v9 = CoTaskMemAlloc(*a2);
    v4 = v9;
    if ( v9 )
    {
      v7 = IStream_Read(pstm, v9, v8);
      if ( v7 >= 0 )
        goto LABEL_7;
    }
    else
    {
      v7 = -2147024882;
    }
  }
  CoTaskMemFree(v4);
  v4 = 0;
  *a2 = 0;
LABEL_7:
  *a3 = v4;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18006bcd4  push    rbx
0x18006bcd6  push    rbp
0x18006bcd7  push    rsi
0x18006bcd8  push    rdi
0x18006bcd9  push    r14
0x18006bcdb  sub     rsp, 20h
0x18006bcdf  mov     rsi, r8
0x18006bce2  xor     ebx, ebx
0x18006bce4  mov     r14, rdx
0x18006bce7  mov     rbp, rcx
0x18006bcea  lea     r8d, [rbx+4]; cb
0x18006bcee  call    cs:__imp_IStream_Read
0x18006bcf4  mov     edi, eax
0x18006bcf6  test    eax, eax
0x18006bcf8  js      short loc_18006BD29
0x18006bcfa  mov     edi, [r14]
0x18006bcfd  mov     ecx, edi; cb
0x18006bcff  call    cs:__imp_CoTaskMemAlloc
0x18006bd05  mov     rbx, rax
0x18006bd08  test    rax, rax
0x18006bd0b  jz      short loc_18006BD24
0x18006bd0d  mov     r8d, edi; cb
0x18006bd10  mov     rdx, rax; pv
0x18006bd13  mov     rcx, rbp; pstm
0x18006bd16  call    cs:__imp_IStream_Read
0x18006bd1c  mov     edi, eax
0x18006bd1e  test    eax, eax
0x18006bd20  js      short loc_18006BD29
0x18006bd22  jmp     short loc_18006BD3B
0x18006bd24  mov     edi, 8007000Eh
0x18006bd29  mov     rcx, rbx; pv
0x18006bd2c  call    cs:__imp_CoTaskMemFree
0x18006bd32  xor     ebx, ebx
0x18006bd34  mov     dword ptr [r14], 0
0x18006bd3b  mov     [rsi], rbx
0x18006bd3e  mov     eax, edi
0x18006bd40  add     rsp, 20h
0x18006bd44  pop     r14
0x18006bd46  pop     rdi
0x18006bd47  pop     rsi
0x18006bd48  pop     rbp
0x18006bd49  pop     rbx
0x18006bd4a  retn
```
