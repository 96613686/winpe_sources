# XMLNode_GetTagText

- ea: `0x180011820`
- end: `0x180011929`
- name: `XMLNode_GetTagText`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800117b0`

## callees

- `0x180011820`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800118d1`
- `OLEAUT32!__imp_SysAllocString` at `0x1800118d1`
- `OLEAUT32!__imp_VariantInit` at `0x18001189b`
- `OLEAUT32!__imp_VariantInit` at `0x18001189b`
- `OLEAUT32!__imp_VariantClear` at `0x1800118f1`
- `OLEAUT32!__imp_VariantClear` at `0x1800118f1`

## pseudocode

```c
__int64 __fastcall XMLNode_GetTagText(__int64 *a1, BSTR *a2)
{
  __int64 v4; // rax
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  BSTR v8; // rax
  VARIANTARG pvarg; // [rsp+20h] [rbp-28h] BYREF
  int v11; // [rsp+50h] [rbp+8h] BYREF

  if ( a1 && a2 )
  {
    *a2 = 0;
    v4 = *a1;
    v11 = 3;
    v5 = (*(__int64 (__fastcall **)(__int64 *, int *))(v4 + 80))(a1, &v11);
    v6 = v5;
    if ( v5 == 1 )
      return (unsigned int)-2147467259;
    if ( v5 < 0 )
      return v6;
    if ( v11 != 3 )
      return (*(unsigned int (__fastcall **)(__int64 *, BSTR *))(*a1 + 208))(a1, a2);
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v7 = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *))(*a1 + 64))(a1, &pvarg);
    v6 = v7;
    if ( v7 != 1 )
    {
      if ( v7 < 0 )
      {
LABEL_14:
        VariantClear(&pvarg);
        return v6;
      }
      if ( pvarg.vt == 8 )
      {
        v8 = SysAllocString(pvarg.bstrVal);
        *a2 = v8;
        if ( !v8 )
          v6 = -2147024882;
        goto LABEL_14;
      }
    }
    v6 = -2147467259;
    goto LABEL_14;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180011820  mov     [rsp+arg_8], rbx
0x180011825  mov     [rsp+arg_10], rsi
0x18001182a  push    rdi
0x18001182b  sub     rsp, 40h
0x18001182f  mov     rsi, rdx
0x180011832  mov     rdi, rcx
0x180011835  test    rcx, rcx
0x180011838  jz      loc_180011914
0x18001183e  test    rdx, rdx
0x180011841  jz      loc_180011914
0x180011847  mov     qword ptr [rdx], 0
0x18001184e  lea     rdx, [rsp+48h+arg_0]
0x180011853  mov     rax, [rcx]
0x180011856  mov     [rsp+48h+arg_0], 3
0x18001185e  mov     rax, [rax+50h]
0x180011862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011867  mov     ebx, eax
0x180011869  cmp     eax, 1
0x18001186c  jnz     short loc_180011878
0x18001186e  mov     ebx, 80004005h
0x180011873  jmp     loc_180011910
0x180011878  test    eax, eax
0x18001187a  js      loc_180011910
0x180011880  cmp     [rsp+48h+arg_0], 3
0x180011885  jnz     short loc_1800118F9
0x180011887  xorps   xmm0, xmm0
0x18001188a  lea     rcx, [rsp+48h+pvarg]; pvarg
0x18001188f  xor     eax, eax
0x180011891  movups  xmmword ptr [rsp+48h+pvarg], xmm0
0x180011896  mov     qword ptr [rsp+48h+pvarg+10h], rax
0x18001189b  call    cs:__imp_VariantInit
0x1800118a1  mov     rax, [rdi]
0x1800118a4  lea     rdx, [rsp+48h+pvarg]
0x1800118a9  mov     rcx, rdi
0x1800118ac  mov     rax, [rax+40h]
0x1800118b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118b5  mov     ebx, eax
0x1800118b7  cmp     eax, 1
0x1800118ba  jz      short loc_1800118E7
0x1800118bc  test    eax, eax
0x1800118be  js      short loc_1800118EC
0x1800118c0  mov     eax, 8
0x1800118c5  cmp     ax, word ptr [rsp+48h+pvarg]
0x1800118ca  jnz     short loc_1800118E7
0x1800118cc  mov     rcx, qword ptr [rsp+48h+pvarg+8]; psz
0x1800118d1  call    cs:__imp_SysAllocString
0x1800118d7  test    rax, rax
0x1800118da  mov     [rsi], rax
0x1800118dd  mov     ecx, 8007000Eh
0x1800118e2  cmovz   ebx, ecx
0x1800118e5  jmp     short loc_1800118EC
0x1800118e7  mov     ebx, 80004005h
0x1800118ec  lea     rcx, [rsp+48h+pvarg]; pvarg
0x1800118f1  call    cs:__imp_VariantClear
0x1800118f7  jmp     short loc_180011910
0x1800118f9  mov     rax, [rdi]
0x1800118fc  mov     rdx, rsi
0x1800118ff  mov     rcx, rdi
0x180011902  mov     rax, [rax+0D0h]
0x180011909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001190e  mov     ebx, eax
0x180011910  mov     eax, ebx
0x180011912  jmp     short loc_180011919
0x180011914  mov     eax, 80070057h
0x180011919  mov     rbx, [rsp+48h+arg_8]
0x18001191e  mov     rsi, [rsp+48h+arg_10]
0x180011923  add     rsp, 40h
0x180011927  pop     rdi
0x180011928  retn
```
