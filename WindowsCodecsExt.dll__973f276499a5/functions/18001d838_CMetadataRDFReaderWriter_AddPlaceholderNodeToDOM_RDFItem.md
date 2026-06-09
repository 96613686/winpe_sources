# CMetadataRDFReaderWriter::AddPlaceholderNodeToDOM(RDFItem *)

- ea: `0x18001d838`
- end: `0x18001d984`
- name: `?AddPlaceholderNodeToDOM@CMetadataRDFReaderWriter@@IEAAJPEAVRDFItem@@@Z`
- size: `332`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, struct RDFItem *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180002aa0`

## callees

- `0x180004500`
- `0x180014334`
- `0x1800171c4`
- `0x18001d838`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001d879`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d879`
- `OLEAUT32!__imp_VariantInit` at `0x18001d86c`
- `OLEAUT32!__imp_VariantInit` at `0x18001d86c`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::AddPlaceholderNodeToDOM(__int64 **this, struct RDFItem *a2)
{
  unsigned __int16 *v4; // rbx
  unsigned int v5; // edi
  int v6; // ecx
  int v7; // eax
  __int64 *v8; // rcx
  __int64 v9; // rax
  __int64 (__fastcall *v10)(__int64 *, __int128 *, unsigned __int16 *, _QWORD, __int64 *); // rax
  VARIANTARG pvarg; // [rsp+30h] [rbp-40h] BYREF
  __int128 v13; // [rsp+50h] [rbp-20h] BYREF
  IRecordInfo *pRecInfo; // [rsp+60h] [rbp-10h]
  __int64 v15; // [rsp+A0h] [rbp+30h] BYREF
  unsigned __int16 *v16; // [rsp+A8h] [rbp+38h] BYREF

  v15 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v16 = SysAllocString(L"Placeholder");
  v4 = v16;
  if ( v16 )
  {
    v7 = CMetadataRDFReaderWriter::EnsureDOM((CMetadataRDFReaderWriter *)this);
    v5 = v7;
    if ( v7 >= 0 )
    {
      v8 = this[23];
      pvarg.vt = 18;
      pvarg.iVal = 1;
      v9 = *v8;
      pRecInfo = pvarg.pRecInfo;
      v10 = *(__int64 (__fastcall **)(__int64 *, __int128 *, unsigned __int16 *, _QWORD, __int64 *))(v9 + 448);
      v13 = *(_OWORD *)&pvarg.vt;
      v7 = v10(v8, &v13, v4, 0, &v15);
      v5 = v7;
      if ( v7 >= 0 )
      {
        v7 = ((__int64 (__fastcall *)(__int64 **, __int64 *, __int64, __int64 *, struct RDFItem *))(*this)[40])(
               this,
               this[23],
               v15,
               this[24],
               a2);
        v5 = v7;
        if ( v7 >= 0 )
          goto LABEL_10;
      }
    }
    if ( !g_doStackCaptures )
      goto LABEL_10;
    v6 = v7;
  }
  else
  {
    v5 = -2147024882;
    if ( !g_doStackCaptures )
      goto LABEL_10;
    v6 = -2147024882;
  }
  DoStackCapture(v6);
LABEL_10:
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  FreeBSTR(&v16);
  return v5;
}

```

## disassembly

```asm
0x18001d838  mov     [rsp-18h+arg_0], rbx
0x18001d83d  mov     [rsp-18h+arg_8], rsi
0x18001d842  push    rbp
0x18001d843  push    rdi
0x18001d844  push    r14
0x18001d846  mov     rbp, rsp
0x18001d849  sub     rsp, 70h
0x18001d84d  mov     rsi, rcx
0x18001d850  mov     [rbp+arg_10], 0
0x18001d858  xorps   xmm0, xmm0
0x18001d85b  lea     rcx, [rbp+pvarg]; pvarg
0x18001d85f  xor     eax, eax
0x18001d861  mov     r14, rdx
0x18001d864  movups  xmmword ptr [rbp+pvarg], xmm0
0x18001d868  mov     qword ptr [rbp+pvarg+10h], rax
0x18001d86c  call    cs:__imp_VariantInit
0x18001d872  lea     rcx, aPlaceholder; "Placeholder"
0x18001d879  call    cs:__imp_SysAllocString
0x18001d87f  mov     [rbp+arg_18], rax
0x18001d883  mov     rbx, rax
0x18001d886  test    rax, rax
0x18001d889  jnz     short loc_18001D8A3
0x18001d88b  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x18001d891  mov     edi, 8007000Eh
0x18001d896  jz      loc_18001D947
0x18001d89c  mov     ecx, edi
0x18001d89e  jmp     loc_18001D942
0x18001d8a3  mov     rcx, rsi; this
0x18001d8a6  call    ?EnsureDOM@CMetadataRDFReaderWriter@@IEAAJXZ; CMetadataRDFReaderWriter::EnsureDOM(void)
0x18001d8ab  mov     edi, eax
0x18001d8ad  test    eax, eax
0x18001d8af  js      loc_18001D937
0x18001d8b5  mov     rcx, [rsi+0B8h]
0x18001d8bc  lea     rdx, [rbp+arg_10]
0x18001d8c0  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18001d8c5  mov     eax, 12h
0x18001d8ca  mov     word ptr [rbp+pvarg], ax
0x18001d8ce  xor     r9d, r9d
0x18001d8d1  mov     eax, 1
0x18001d8d6  mov     [rsp+70h+var_50], rdx
0x18001d8db  mov     word ptr [rbp+pvarg+8], ax
0x18001d8df  lea     rdx, [rbp+var_20]
0x18001d8e3  mov     rax, [rcx]
0x18001d8e6  mov     r8, rbx
0x18001d8e9  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18001d8ed  movsd   [rbp+var_10], xmm1
0x18001d8f2  mov     rax, [rax+1C0h]
0x18001d8f9  movaps  [rbp+var_20], xmm0
0x18001d8fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d902  mov     edi, eax
0x18001d904  test    eax, eax
0x18001d906  js      short loc_18001D937
0x18001d908  mov     rax, [rsi]
0x18001d90b  mov     rcx, rsi
0x18001d90e  mov     r9, [rsi+0C0h]
0x18001d915  mov     r8, [rbp+arg_10]
0x18001d919  mov     rdx, [rsi+0B8h]
0x18001d920  mov     rax, [rax+140h]
0x18001d927  mov     [rsp+70h+var_50], r14
0x18001d92c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d931  mov     edi, eax
0x18001d933  test    eax, eax
0x18001d935  jns     short loc_18001D947
0x18001d937  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18001d93e  jz      short loc_18001D947
0x18001d940  mov     ecx, eax; int
0x18001d942  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001d947  mov     rcx, [rbp+arg_10]
0x18001d94b  test    rcx, rcx
0x18001d94e  jz      short loc_18001D964
0x18001d950  mov     rdx, [rcx]
0x18001d953  mov     rax, [rdx+10h]
0x18001d957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d95c  mov     [rbp+arg_10], 0
0x18001d964  lea     rcx, [rbp+arg_18]; unsigned __int16 **
0x18001d968  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x18001d96d  lea     r11, [rsp+70h+var_s0]
0x18001d972  mov     eax, edi
0x18001d974  mov     rbx, [r11+20h]
0x18001d978  mov     rsi, [r11+28h]
0x18001d97c  mov     rsp, r11
0x18001d97f  pop     r14
0x18001d981  pop     rdi
0x18001d982  pop     rbp
0x18001d983  retn
```
