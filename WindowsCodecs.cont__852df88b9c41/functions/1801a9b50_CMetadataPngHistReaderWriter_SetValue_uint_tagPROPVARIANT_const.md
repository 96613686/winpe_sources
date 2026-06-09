# CMetadataPngHistReaderWriter::SetValue(uint,tagPROPVARIANT const *)

- ea: `0x1801a9b50`
- end: `0x1801a9bff`
- name: `?SetValue@CMetadataPngHistReaderWriter@@MEAAJIPEBUtagPROPVARIANT@@@Z`
- size: `175`
- prototype: `__int64 __fastcall(CMetadataPngHistReaderWriter *this, int, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18006ac40`
- `0x1800bb784`
- `0x18017b528`
- `0x1801a9b50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801a9bb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801a9bb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a9ba7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a9ba7`

## pseudocode

```c
__int64 __fastcall CMetadataPngHistReaderWriter::SetValue(
        CMetadataPngHistReaderWriter *this,
        int a2,
        const struct tagPROPVARIANT *a3)
{
  unsigned int v5; // ebx
  ULONGLONG v6; // rcx
  HRESULT v7; // eax
  int v8; // ecx
  void *v9; // rcx
  size_t v10; // rbp
  void *v11; // rax
  UINT puResult; // [rsp+58h] [rbp+10h] BYREF

  if ( a2 == 1 )
  {
    v6 = 2LL * a3->ulVal;
    puResult = 0;
    v7 = ULongLongToUInt(v6, &puResult);
    v5 = v7;
    if ( v7 < 0 )
    {
      if ( !(_DWORD)g_doStackCaptures )
        return v5;
      v8 = v7;
      goto LABEL_13;
    }
    v9 = (void *)*((_QWORD *)this + 20);
    if ( v9 )
      CoTaskMemFree(v9);
    v10 = puResult;
    v11 = CoTaskMemAlloc(puResult);
    *((_QWORD *)this + 20) = v11;
    if ( v11 )
    {
      *((_DWORD *)this + 38) = a3->lVal;
      memcpy_0(v11, a3->bstrblobVal.pData, v10);
      return v5;
    }
    v5 = -2147024882;
  }
  else
  {
    v5 = -2147024809;
  }
  if ( (_DWORD)g_doStackCaptures )
  {
    v8 = v5;
LABEL_13:
    DoStackCapture(v8);
  }
  return v5;
}

```

## disassembly

```asm
0x1801a9b50  push    rbx
0x1801a9b52  push    rbp
0x1801a9b53  push    rsi
0x1801a9b54  push    rdi
0x1801a9b55  sub     rsp, 28h
0x1801a9b59  mov     rsi, r8
0x1801a9b5c  mov     rdi, rcx
0x1801a9b5f  cmp     edx, 1
0x1801a9b62  jz      short loc_1801A9B6B
0x1801a9b64  mov     ebx, 80070057h
0x1801a9b69  jmp     short loc_1801A9BCA
0x1801a9b6b  mov     ecx, [r8+8]
0x1801a9b6f  lea     rdx, [rsp+48h+puResult]; puResult
0x1801a9b74  add     rcx, rcx; ullOperand
0x1801a9b77  mov     [rsp+48h+puResult], 0
0x1801a9b7f  call    ULongLongToUInt
0x1801a9b84  mov     ebx, eax
0x1801a9b86  test    eax, eax
0x1801a9b88  jns     short loc_1801A9B9B
0x1801a9b8a  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801a9b91  jz      short loc_1801A9B97
0x1801a9b93  mov     ecx, eax
0x1801a9b95  jmp     short loc_1801A9BD5
0x1801a9b97  test    eax, eax
0x1801a9b99  js      short loc_1801A9BF4
0x1801a9b9b  mov     rcx, [rdi+0A0h]; pv
0x1801a9ba2  test    rcx, rcx
0x1801a9ba5  jz      short loc_1801A9BAD
0x1801a9ba7  call    cs:__imp_CoTaskMemFree
0x1801a9bad  mov     ebp, [rsp+48h+puResult]
0x1801a9bb1  mov     ecx, ebp; cb
0x1801a9bb3  call    cs:__imp_CoTaskMemAlloc
0x1801a9bb9  mov     [rdi+0A0h], rax
0x1801a9bc0  test    rax, rax
0x1801a9bc3  jnz     short loc_1801A9BDC
0x1801a9bc5  mov     ebx, 8007000Eh
0x1801a9bca  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801a9bd1  jz      short loc_1801A9BF4
0x1801a9bd3  mov     ecx, ebx; int
0x1801a9bd5  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801a9bda  jmp     short loc_1801A9BF4
0x1801a9bdc  mov     ecx, [rsi+8]
0x1801a9bdf  mov     r8, rbp; Size
0x1801a9be2  mov     [rdi+98h], ecx
0x1801a9be8  mov     rcx, rax; void *
0x1801a9beb  mov     rdx, [rsi+10h]; Src
0x1801a9bef  call    memcpy_0
0x1801a9bf4  mov     eax, ebx
0x1801a9bf6  add     rsp, 28h
0x1801a9bfa  pop     rdi
0x1801a9bfb  pop     rsi
0x1801a9bfc  pop     rbp
0x1801a9bfd  pop     rbx
0x1801a9bfe  retn
```
