# CMetadataPngHistReaderWriter::SetValue(uint,tagPROPVARIANT const *)

- ea: `0x1801ad060`
- end: `0x1801ad11c`
- name: `?SetValue@CMetadataPngHistReaderWriter@@MEAAJIPEBUtagPROPVARIANT@@@Z`
- size: `188`
- prototype: `__int64 __fastcall(CMetadataPngHistReaderWriter *__hidden this, unsigned int, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180039480`
- `0x1800bd9d4`
- `0x18017e438`
- `0x1801ad060`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801ad0c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801ad0c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ad0b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ad0b7`

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
0x1801ad060  push    rbx
0x1801ad062  push    rbp
0x1801ad063  push    rsi
0x1801ad064  push    rdi
0x1801ad065  sub     rsp, 28h
0x1801ad069  mov     rsi, r8
0x1801ad06c  mov     rdi, rcx
0x1801ad06f  cmp     edx, 1
0x1801ad072  jz      short loc_1801AD07B
0x1801ad074  mov     ebx, 80070057h
0x1801ad079  jmp     short loc_1801AD0E6
0x1801ad07b  mov     ecx, [r8+8]
0x1801ad07f  lea     rdx, [rsp+48h+puResult]; puResult
0x1801ad084  add     rcx, rcx; ullOperand
0x1801ad087  mov     [rsp+48h+puResult], 0
0x1801ad08f  call    ULongLongToUInt
0x1801ad094  mov     ebx, eax
0x1801ad096  test    eax, eax
0x1801ad098  jns     short loc_1801AD0AB
0x1801ad09a  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801ad0a1  jz      short loc_1801AD0A7
0x1801ad0a3  mov     ecx, eax
0x1801ad0a5  jmp     short loc_1801AD0F1
0x1801ad0a7  test    eax, eax
0x1801ad0a9  js      short loc_1801AD110
0x1801ad0ab  mov     rcx, [rdi+0A0h]; pv
0x1801ad0b2  test    rcx, rcx
0x1801ad0b5  jz      short loc_1801AD0C3
0x1801ad0b7  call    cs:__imp_CoTaskMemFree
0x1801ad0be  nop     dword ptr [rax+rax+00h]
0x1801ad0c3  mov     ebp, [rsp+48h+puResult]
0x1801ad0c7  mov     ecx, ebp; cb
0x1801ad0c9  call    cs:__imp_CoTaskMemAlloc
0x1801ad0d0  nop     dword ptr [rax+rax+00h]
0x1801ad0d5  mov     [rdi+0A0h], rax
0x1801ad0dc  test    rax, rax
0x1801ad0df  jnz     short loc_1801AD0F8
0x1801ad0e1  mov     ebx, 8007000Eh
0x1801ad0e6  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801ad0ed  jz      short loc_1801AD110
0x1801ad0ef  mov     ecx, ebx; int
0x1801ad0f1  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801ad0f6  jmp     short loc_1801AD110
0x1801ad0f8  mov     ecx, [rsi+8]
0x1801ad0fb  mov     r8, rbp; Size
0x1801ad0fe  mov     [rdi+98h], ecx
0x1801ad104  mov     rcx, rax; void *
0x1801ad107  mov     rdx, [rsi+10h]; Src
0x1801ad10b  call    memcpy_0
0x1801ad110  mov     eax, ebx
0x1801ad112  add     rsp, 28h
0x1801ad116  pop     rdi
0x1801ad117  pop     rsi
0x1801ad118  pop     rbp
0x1801ad119  pop     rbx
0x1801ad11a  retn
```
