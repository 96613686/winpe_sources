# ReadVariantFromStreamEx(tagVARIANT *,ISequentialStream *,ulong)

- ea: `0x180002d30`
- end: `0x180002f3f`
- name: `?ReadVariantFromStreamEx@@YAJPEAUtagVARIANT@@PEAUISequentialStream@@K@Z`
- size: `527`
- prototype: `__int64 __fastcall(VARIANTARG *pvargDest, struct ISequentialStream *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180002d20`

## callees

- `0x1800028b0`
- `0x1800029c8`
- `0x180002d30`
- `0x180004010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180002d71`
- `OLEAUT32!__imp_VariantInit` at `0x180002d71`
- `OLEAUT32!__imp_VariantClear` at `0x180002d8e`
- `OLEAUT32!__imp_VariantClear` at `0x180002f1e`
- `OLEAUT32!__imp_VariantClear` at `0x180002d8e`
- `OLEAUT32!__imp_VariantClear` at `0x180002f1e`
- `OLEAUT32!__imp_VariantChangeType` at `0x180002ece`
- `OLEAUT32!__imp_VariantChangeType` at `0x180002ece`

## pseudocode

```c
__int64 __fastcall ReadVariantFromStreamEx(VARIANTARG *pvargDest, struct ISequentialStream *a2, unsigned int a3)
{
  int SafeArrayFromStream; // ebx
  unsigned int v7; // edi
  UINT v8; // r15d
  int v9; // ecx
  VARIANTARG pvarg; // [rsp+30h] [rbp-20h] BYREF
  VARTYPE v12; // [rsp+80h] [rbp+30h] BYREF
  int v13; // [rsp+98h] [rbp+48h] BYREF

  v13 = 0;
  v12 = 1;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( !pvargDest || !a2 )
  {
    SafeArrayFromStream = -2147467261;
    goto LABEL_39;
  }
  VariantClear(pvargDest);
  v7 = 2;
  if ( a3 < 2 )
  {
LABEL_38:
    SafeArrayFromStream = -2147024362;
    goto LABEL_39;
  }
  SafeArrayFromStream = ((__int64 (__fastcall *)(struct ISequentialStream *, VARTYPE *, __int64, int *))a2->lpVtbl->Read)(
                          a2,
                          &v12,
                          2,
                          &v13);
  if ( SafeArrayFromStream < 0 )
    goto LABEL_39;
  if ( v13 != 2 )
  {
LABEL_7:
    SafeArrayFromStream = -2147467259;
    goto LABEL_39;
  }
  v8 = a3 - 2;
  if ( v12 > 0xBu )
  {
    if ( v12 == 13 )
      goto LABEL_17;
    if ( v12 != 16 && v12 != 17 )
    {
      if ( v12 == 18 )
        goto LABEL_34;
      if ( v12 == 19 )
        goto LABEL_32;
      v9 = v12 - 22;
      if ( v12 == 22 )
        goto LABEL_32;
      goto LABEL_25;
    }
    v7 = 1;
LABEL_34:
    if ( v8 >= v7 )
    {
      SafeArrayFromStream = ((__int64 (__fastcall *)(struct ISequentialStream *, ULONG *, _QWORD, int *))a2->lpVtbl->Read)(
                              a2,
                              &pvargDest->decVal.Lo32,
                              v7,
                              &v13);
      if ( SafeArrayFromStream < 0 )
        goto LABEL_39;
      if ( v7 != v13 )
        goto LABEL_7;
LABEL_28:
      pvargDest->vt = v12;
      goto LABEL_39;
    }
    goto LABEL_38;
  }
  switch ( v12 )
  {
    case 0xBu:
    case 2u:
      goto LABEL_34;
    case 3u:
    case 4u:
      goto LABEL_32;
    case 5u:
    case 6u:
    case 7u:
      v7 = 8;
      goto LABEL_34;
  }
  v9 = v12 - 9;
  if ( v12 == 9 )
  {
LABEL_17:
    SafeArrayFromStream = -2147418113;
    goto LABEL_39;
  }
LABEL_25:
  if ( v9 == 1 )
  {
LABEL_32:
    v7 = 4;
    goto LABEL_34;
  }
  if ( (v12 & 0x2000) != 0 )
  {
    SafeArrayFromStream = ReadSafeArrayFromStream(&pvargDest->parray, v12 & 0xDFFF, a2);
    if ( SafeArrayFromStream < 0 )
      goto LABEL_39;
    goto LABEL_28;
  }
  if ( v12 != 1 )
  {
    pvarg.llVal = 0;
    pvarg.vt = 8;
    SafeArrayFromStream = ReadBSTRFromStreamEx(&pvarg.bstrVal, a2, v8);
    if ( SafeArrayFromStream >= 0 )
      SafeArrayFromStream = VariantChangeType(pvargDest, &pvarg, 1u, v12);
  }
LABEL_39:
  VariantClear(&pvarg);
  return (unsigned int)SafeArrayFromStream;
}

```

## disassembly

```asm
0x180002d30  mov     [rsp-28h+arg_8], rbx
0x180002d35  mov     [rsp-28h+arg_10], rsi
0x180002d3a  push    rbp
0x180002d3b  push    rdi
0x180002d3c  push    r12
0x180002d3e  push    r14
0x180002d40  push    r15
0x180002d42  mov     rbp, rsp
0x180002d45  sub     rsp, 50h
0x180002d49  xor     eax, eax
0x180002d4b  mov     rsi, rcx
0x180002d4e  xorps   xmm0, xmm0
0x180002d51  mov     qword ptr [rbp+pvarg+10h], rax
0x180002d55  mov     r12d, 1
0x180002d5b  mov     [rbp+arg_18], eax
0x180002d5e  lea     rcx, [rbp+pvarg]; pvarg
0x180002d62  mov     [rbp+arg_0], r12w
0x180002d67  movups  xmmword ptr [rbp+pvarg], xmm0
0x180002d6b  mov     r15d, r8d
0x180002d6e  mov     r14, rdx
0x180002d71  call    cs:__imp_VariantInit
0x180002d77  test    rsi, rsi
0x180002d7a  jnz     short loc_180002D86
0x180002d7c  mov     ebx, 80004003h
0x180002d81  jmp     loc_180002F1A
0x180002d86  test    r14, r14
0x180002d89  jz      short loc_180002D7C
0x180002d8b  mov     rcx, rsi; pvarg
0x180002d8e  call    cs:__imp_VariantClear
0x180002d94  mov     edi, 2
0x180002d99  cmp     r15d, edi
0x180002d9c  jb      loc_180002F15
0x180002da2  mov     rax, [r14]
0x180002da5  lea     r9, [rbp+arg_18]
0x180002da9  mov     r8d, edi
0x180002dac  lea     rdx, [rbp+arg_0]
0x180002db0  mov     rcx, r14
0x180002db3  mov     rax, [rax+18h]
0x180002db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dbc  mov     ebx, eax
0x180002dbe  test    eax, eax
0x180002dc0  js      loc_180002F1A
0x180002dc6  cmp     [rbp+arg_18], edi
0x180002dc9  jz      short loc_180002DD5
0x180002dcb  mov     ebx, 80004005h
0x180002dd0  jmp     loc_180002F1A
0x180002dd5  movzx   edx, [rbp+arg_0]
0x180002dd9  add     r15d, 0FFFFFFFEh
0x180002ddd  mov     ecx, edx
0x180002ddf  cmp     edx, 0Bh
0x180002de2  ja      short loc_180002E2B
0x180002de4  jz      loc_180002EE2
0x180002dea  sub     ecx, edi
0x180002dec  jz      loc_180002EE2
0x180002df2  sub     ecx, r12d
0x180002df5  jz      loc_180002ED8
0x180002dfb  sub     ecx, r12d
0x180002dfe  jz      loc_180002ED8
0x180002e04  sub     ecx, r12d
0x180002e07  jz      short loc_180002E21
0x180002e09  sub     ecx, r12d
0x180002e0c  jz      short loc_180002E21
0x180002e0e  sub     ecx, r12d
0x180002e11  jz      short loc_180002E21
0x180002e13  sub     ecx, edi
0x180002e15  jnz     short loc_180002E59
0x180002e17  mov     ebx, 8000FFFFh
0x180002e1c  jmp     loc_180002F1A
0x180002e21  mov     edi, 8
0x180002e26  jmp     loc_180002EE2
0x180002e2b  sub     ecx, 0Dh
0x180002e2e  jz      short loc_180002E17
0x180002e30  sub     ecx, 3
0x180002e33  jz      loc_180002EDF
0x180002e39  sub     ecx, r12d
0x180002e3c  jz      loc_180002EDF
0x180002e42  sub     ecx, r12d
0x180002e45  jz      loc_180002EE2
0x180002e4b  sub     ecx, r12d
0x180002e4e  jz      loc_180002ED8
0x180002e54  sub     ecx, 3
0x180002e57  jz      short loc_180002ED8
0x180002e59  cmp     ecx, r12d
0x180002e5c  jz      short loc_180002ED8
0x180002e5e  bt      dx, 0Dh
0x180002e63  jnb     short loc_180002E8F
0x180002e65  mov     eax, 0DFFFh
0x180002e6a  lea     rcx, [rsi+8]; struct tagSAFEARRAY **
0x180002e6e  and     dx, ax; unsigned __int16
0x180002e71  mov     r8, r14; struct ISequentialStream *
0x180002e74  call    ?ReadSafeArrayFromStream@@YAJPEAPEAUtagSAFEARRAY@@GPEAUISequentialStream@@@Z; ReadSafeArrayFromStream(tagSAFEARRAY * *,ushort,ISequentialStream *)
0x180002e79  mov     ebx, eax
0x180002e7b  test    eax, eax
0x180002e7d  js      loc_180002F1A
0x180002e83  movzx   eax, [rbp+arg_0]
0x180002e87  mov     [rsi], ax
0x180002e8a  jmp     loc_180002F1A
0x180002e8f  cmp     dx, r12w
0x180002e93  jz      loc_180002F1A
0x180002e99  mov     edi, 8
0x180002e9e  mov     qword ptr [rbp+pvarg+8], 0
0x180002ea6  mov     r8d, r15d; unsigned int
0x180002ea9  mov     word ptr [rbp+pvarg], di
0x180002ead  mov     rdx, r14; struct ISequentialStream *
0x180002eb0  lea     rcx, [rbp+pvarg+8]; unsigned __int16 **
0x180002eb4  call    ?ReadBSTRFromStreamEx@@YAJPEAPEAGPEAUISequentialStream@@K@Z; ReadBSTRFromStreamEx(ushort * *,ISequentialStream *,ulong)
0x180002eb9  mov     ebx, eax
0x180002ebb  test    eax, eax
0x180002ebd  js      short loc_180002F1A
0x180002ebf  movzx   r9d, [rbp+arg_0]; vt
0x180002ec4  lea     rdx, [rbp+pvarg]; pvarSrc
0x180002ec8  mov     r8d, r12d; wFlags
0x180002ecb  mov     rcx, rsi; pvargDest
0x180002ece  call    cs:__imp_VariantChangeType
0x180002ed4  mov     ebx, eax
0x180002ed6  jmp     short loc_180002F1A
0x180002ed8  mov     edi, 4
0x180002edd  jmp     short loc_180002EE2
0x180002edf  mov     edi, r12d
0x180002ee2  cmp     r15d, edi
0x180002ee5  jb      short loc_180002F15
0x180002ee7  mov     rax, [r14]
0x180002eea  lea     rdx, [rsi+8]
0x180002eee  lea     r9, [rbp+arg_18]
0x180002ef2  mov     r8d, edi
0x180002ef5  mov     rcx, r14
0x180002ef8  mov     rax, [rax+18h]
0x180002efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f01  mov     ebx, eax
0x180002f03  test    eax, eax
0x180002f05  js      short loc_180002F1A
0x180002f07  cmp     edi, [rbp+arg_18]
0x180002f0a  jz      loc_180002E83
0x180002f10  jmp     loc_180002DCB
0x180002f15  mov     ebx, 80070216h
0x180002f1a  lea     rcx, [rbp+pvarg]; pvarg
0x180002f1e  call    cs:__imp_VariantClear
0x180002f24  lea     r11, [rsp+50h+var_s0]
0x180002f29  mov     eax, ebx
0x180002f2b  mov     rbx, [r11+38h]
0x180002f2f  mov     rsi, [r11+40h]
0x180002f33  mov     rsp, r11
0x180002f36  pop     r15
0x180002f38  pop     r14
0x180002f3a  pop     r12
0x180002f3c  pop     rdi
0x180002f3d  pop     rbp
0x180002f3e  retn
```
