# CMetadataXMPAltReaderWriter::HrGetValueByIndex(uint,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *)

- ea: `0x180001140`
- end: `0x1800011d6`
- name: `?HrGetValueByIndex@CMetadataXMPAltReaderWriter@@UEAAJIPEAUtagPROPVARIANT@@00@Z`
- size: `150`
- prototype: `__int64 __fastcall(CMetadataXMPAltReaderWriter *__hidden this, unsigned int, struct tagPROPVARIANT *, struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001140`
- `0x1800021c0`
- `0x1800171c4`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CMetadataXMPAltReaderWriter::HrGetValueByIndex(
        CMetadataXMPAltReaderWriter *this,
        int a2,
        struct tagPROPVARIANT *a3,
        struct tagPROPVARIANT *a4,
        PROPVARIANT *a5)
{
  int ValueByIndex; // eax
  unsigned int v10; // ebx

  if ( (*(unsigned int (__fastcall **)(CMetadataXMPAltReaderWriter *))(*(_QWORD *)this + 272LL))(this) )
  {
    ValueByIndex = CMetadataRDFReaderWriter::HrGetValueByIndex(this, a2, 0, 0, a5);
    v10 = ValueByIndex;
    if ( ValueByIndex < 0 )
    {
      if ( !g_doStackCaptures )
        return v10;
LABEL_5:
      DoStackCapture(ValueByIndex);
      return v10;
    }
    if ( a4 )
    {
      a4->vt = 19;
      a4->lVal = a2;
    }
  }
  else
  {
    ValueByIndex = CMetadataRDFReaderWriter::HrGetValueByIndex(this, a2, a3, a4, a5);
    v10 = ValueByIndex;
    if ( ValueByIndex < 0 && g_doStackCaptures )
      goto LABEL_5;
  }
  return v10;
}

```

## disassembly

```asm
0x180001140  push    rbx
0x180001142  push    rbp
0x180001143  push    rsi
0x180001144  push    rdi
0x180001145  sub     rsp, 38h
0x180001149  mov     rax, [rcx]
0x18000114c  mov     rdi, r9
0x18000114f  mov     rbp, r8
0x180001152  mov     esi, edx
0x180001154  mov     rbx, rcx
0x180001157  mov     rax, [rax+110h]
0x18000115e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001163  test    eax, eax
0x180001165  mov     edx, esi; unsigned int
0x180001167  mov     rax, [rsp+58h+arg_20]
0x18000116f  mov     rcx, rbx; this
0x180001172  mov     [rsp+58h+var_38], rax; struct tagPROPVARIANT *
0x180001177  jz      short loc_1800011AB
0x180001179  xor     r9d, r9d; struct tagPROPVARIANT *
0x18000117c  xor     r8d, r8d; struct tagPROPVARIANT *
0x18000117f  call    ?HrGetValueByIndex@CMetadataRDFReaderWriter@@MEAAJIPEAUtagPROPVARIANT@@00@Z; CMetadataRDFReaderWriter::HrGetValueByIndex(uint,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *)
0x180001184  mov     ebx, eax
0x180001186  test    eax, eax
0x180001188  jns     short loc_1800011C7
0x18000118a  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180001191  jnz     short loc_1800011A2
0x180001193  test    eax, eax
0x180001195  jns     short loc_1800011C7
0x180001197  mov     eax, ebx
0x180001199  add     rsp, 38h
0x18000119d  pop     rdi
0x18000119e  pop     rsi
0x18000119f  pop     rbp
0x1800011a0  pop     rbx
0x1800011a1  retn
0x1800011a2  mov     ecx, eax; int
0x1800011a4  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800011a9  jmp     short loc_180001197
0x1800011ab  mov     r9, rdi; struct tagPROPVARIANT *
0x1800011ae  mov     r8, rbp; struct tagPROPVARIANT *
0x1800011b1  call    ?HrGetValueByIndex@CMetadataRDFReaderWriter@@MEAAJIPEAUtagPROPVARIANT@@00@Z; CMetadataRDFReaderWriter::HrGetValueByIndex(uint,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *)
0x1800011b6  mov     ebx, eax
0x1800011b8  test    eax, eax
0x1800011ba  jns     short loc_180001197
0x1800011bc  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800011c3  jz      short loc_180001197
0x1800011c5  jmp     short loc_1800011A2
0x1800011c7  test    rdi, rdi
0x1800011ca  jz      short loc_180001197
0x1800011cc  mov     word ptr [rdi], 13h
0x1800011d1  mov     [rdi+8], esi
0x1800011d4  jmp     short loc_180001197
```
