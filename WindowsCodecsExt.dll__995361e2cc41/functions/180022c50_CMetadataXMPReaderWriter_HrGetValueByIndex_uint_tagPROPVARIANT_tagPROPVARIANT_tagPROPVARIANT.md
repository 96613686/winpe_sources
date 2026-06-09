# CMetadataXMPReaderWriter::HrGetValueByIndex(uint,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *)

- ea: `0x180022c50`
- end: `0x180022d25`
- name: `?HrGetValueByIndex@CMetadataXMPReaderWriter@@UEAAJIPEAUtagPROPVARIANT@@00@Z`
- size: `213`
- prototype: `int(CMetadataXMPReaderWriter *__hidden this, unsigned int, struct tagPROPVARIANT *, struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800021c0`
- `0x180002608`
- `0x1800171c4`
- `0x180022c50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180022cc2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180022cc2`

## pseudocode

```c
__int64 __fastcall CMetadataXMPReaderWriter::HrGetValueByIndex(
        CMetadataXMPReaderWriter *this,
        int a2,
        struct tagPROPVARIANT *a3,
        struct tagPROPVARIANT *a4,
        PROPVARIANT *a5)
{
  int v8; // ebx
  int ValueByIndex; // eax
  int v10; // ecx

  if ( a2 == *((_DWORD *)this + 43) && *((_DWORD *)this + 65) )
  {
    v8 = 0;
    if ( a3 )
    {
      ValueByIndex = PropVariantString(L"PaddingSchema", a3);
      v8 = ValueByIndex;
      if ( ValueByIndex < 0 )
      {
        if ( !g_doStackCaptures )
          return (unsigned int)v8;
        goto LABEL_17;
      }
    }
    if ( a4 && (v8 = PropVariantString(L"padding", a4), v8 < 0) )
    {
      if ( a3 )
        PropVariantClear((PROPVARIANT *)a3);
      if ( g_doStackCaptures )
      {
        v10 = v8;
LABEL_18:
        DoStackCapture(v10);
      }
    }
    else if ( a5 )
    {
      *(_WORD *)a5 = 19;
      *((_DWORD *)a5 + 2) = *((_DWORD *)this + 64);
    }
  }
  else
  {
    ValueByIndex = CMetadataRDFReaderWriter::HrGetValueByIndex(this, a2, a3, a4, a5);
    v8 = ValueByIndex;
    if ( ValueByIndex < 0 && g_doStackCaptures )
    {
LABEL_17:
      v10 = ValueByIndex;
      goto LABEL_18;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180022c50  push    rbx
0x180022c52  push    rbp
0x180022c53  push    rsi
0x180022c54  push    rdi
0x180022c55  sub     rsp, 38h
0x180022c59  mov     rbp, r9
0x180022c5c  mov     rdi, r8
0x180022c5f  mov     rsi, rcx
0x180022c62  cmp     edx, [rcx+0ACh]
0x180022c68  jnz     loc_180022CF2
0x180022c6e  cmp     dword ptr [rcx+104h], 0
0x180022c75  jz      short loc_180022CF2
0x180022c77  xor     ebx, ebx
0x180022c79  test    r8, r8
0x180022c7c  jz      short loc_180022CA0
0x180022c7e  mov     rdx, r8; struct tagPROPVARIANT *
0x180022c81  lea     rcx, aPaddingschema; "PaddingSchema"
0x180022c88  call    ?PropVariantString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; PropVariantString(ushort const *,tagPROPVARIANT *)
0x180022c8d  mov     ebx, eax
0x180022c8f  test    eax, eax
0x180022c91  jns     short loc_180022CA0
0x180022c93  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180022c9a  jnz     short loc_180022D13
0x180022c9c  test    eax, eax
0x180022c9e  js      short loc_180022D1A
0x180022ca0  test    rbp, rbp
0x180022ca3  jz      short loc_180022CD5
0x180022ca5  mov     rdx, rbp; struct tagPROPVARIANT *
0x180022ca8  lea     rcx, aPadding; "padding"
0x180022caf  call    ?PropVariantString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; PropVariantString(ushort const *,tagPROPVARIANT *)
0x180022cb4  mov     ebx, eax
0x180022cb6  test    eax, eax
0x180022cb8  jns     short loc_180022CD5
0x180022cba  test    rdi, rdi
0x180022cbd  jz      short loc_180022CC8
0x180022cbf  mov     rcx, rdi; pvar
0x180022cc2  call    cs:__imp_PropVariantClear
0x180022cc8  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180022ccf  jz      short loc_180022D1A
0x180022cd1  mov     ecx, ebx
0x180022cd3  jmp     short loc_180022D15
0x180022cd5  mov     rcx, [rsp+58h+arg_20]; this
0x180022cdd  test    rcx, rcx
0x180022ce0  jz      short loc_180022D1A
0x180022ce2  mov     word ptr [rcx], 13h
0x180022ce7  mov     eax, [rsi+100h]
0x180022ced  mov     [rcx+8], eax
0x180022cf0  jmp     short loc_180022D1A
0x180022cf2  mov     rax, [rsp+58h+arg_20]
0x180022cfa  mov     [rsp+58h+var_38], rax; struct tagPROPVARIANT *
0x180022cff  call    ?HrGetValueByIndex@CMetadataRDFReaderWriter@@MEAAJIPEAUtagPROPVARIANT@@00@Z; CMetadataRDFReaderWriter::HrGetValueByIndex(uint,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *)
0x180022d04  mov     ebx, eax
0x180022d06  test    eax, eax
0x180022d08  jns     short loc_180022D1A
0x180022d0a  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180022d11  jz      short loc_180022D1A
0x180022d13  mov     ecx, eax; int
0x180022d15  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180022d1a  mov     eax, ebx
0x180022d1c  add     rsp, 38h
0x180022d20  pop     rdi
0x180022d21  pop     rsi
0x180022d22  pop     rbp
0x180022d23  pop     rbx
0x180022d24  retn
```
