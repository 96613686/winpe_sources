# StructuredQuery1::ReadPSTR

- ea: `0x18006bf70`
- end: `0x18006bffa`
- name: `StructuredQuery1::ReadPSTR`
- size: `138`
- prototype: `__int64 __fastcall(IStream *pstm)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003dc94`

## callees

- `0x18006bf70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bfdc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006bfdc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006bfa5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006bfa5`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18006bf8f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18006bfc1`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18006bf8f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18006bfc1`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::ReadPSTR(IStream *pstm, _QWORD *a2)
{
  void *v2; // rbx
  HRESULT v5; // edi
  void *v6; // rax
  unsigned int pv; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  pv = 0;
  v5 = IStream_Read(pstm, &pv, 4u);
  if ( v5 >= 0 && pv )
  {
    v6 = CoTaskMemAlloc(pv);
    v2 = v6;
    if ( v6 )
    {
      v5 = IStream_Read(pstm, v6, pv - 1);
      if ( v5 < 0 )
      {
        CoTaskMemFree(v2);
        v2 = 0;
      }
      else
      {
        *((_BYTE *)v2 + pv - 1) = 0;
      }
    }
    else
    {
      v5 = -2147024882;
    }
  }
  *a2 = v2;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18006bf70  push    rbx
0x18006bf72  push    rsi
0x18006bf73  push    rdi
0x18006bf74  push    r14
0x18006bf76  sub     rsp, 28h
0x18006bf7a  xor     ebx, ebx
0x18006bf7c  mov     r14, rdx
0x18006bf7f  lea     rdx, [rsp+48h+pv]; pv
0x18006bf84  mov     [rsp+48h+pv], ebx
0x18006bf88  mov     rsi, rcx
0x18006bf8b  lea     r8d, [rbx+4]; cb
0x18006bf8f  call    cs:__imp_IStream_Read
0x18006bf95  mov     edi, eax
0x18006bf97  test    eax, eax
0x18006bf99  js      short loc_18006BFEB
0x18006bf9b  mov     eax, [rsp+48h+pv]
0x18006bf9f  test    eax, eax
0x18006bfa1  jz      short loc_18006BFEB
0x18006bfa3  mov     ecx, eax; cb
0x18006bfa5  call    cs:__imp_CoTaskMemAlloc
0x18006bfab  mov     rbx, rax
0x18006bfae  test    rax, rax
0x18006bfb1  jz      short loc_18006BFE6
0x18006bfb3  mov     r8d, [rsp+48h+pv]
0x18006bfb8  mov     rdx, rax; pv
0x18006bfbb  dec     r8d; cb
0x18006bfbe  mov     rcx, rsi; pstm
0x18006bfc1  call    cs:__imp_IStream_Read
0x18006bfc7  mov     edi, eax
0x18006bfc9  test    eax, eax
0x18006bfcb  js      short loc_18006BFD9
0x18006bfcd  mov     ecx, [rsp+48h+pv]
0x18006bfd1  dec     ecx
0x18006bfd3  mov     byte ptr [rcx+rbx], 0
0x18006bfd7  jmp     short loc_18006BFEB
0x18006bfd9  mov     rcx, rbx; pv
0x18006bfdc  call    cs:__imp_CoTaskMemFree
0x18006bfe2  xor     ebx, ebx
0x18006bfe4  jmp     short loc_18006BFEB
0x18006bfe6  mov     edi, 8007000Eh
0x18006bfeb  mov     [r14], rbx
0x18006bfee  mov     eax, edi
0x18006bff0  add     rsp, 28h
0x18006bff4  pop     r14
0x18006bff6  pop     rdi
0x18006bff7  pop     rsi
0x18006bff8  pop     rbx
0x18006bff9  retn
```
