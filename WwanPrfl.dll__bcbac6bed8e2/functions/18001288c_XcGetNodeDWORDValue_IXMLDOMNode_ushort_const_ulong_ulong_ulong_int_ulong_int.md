# XcGetNodeDWORDValue(IXMLDOMNode *,ushort const *,ulong *,ulong,ulong,int,ulong,int *)

- ea: `0x18001288c`
- end: `0x180012962`
- name: `?XcGetNodeDWORDValue@@YAKPEAUIXMLDOMNode@@PEBGPEAKKKHKPEAH@Z`
- size: `214`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, const unsigned __int16 *, unsigned int *, __int64, unsigned int, int, unsigned int, int *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000c4a0`
- `0x180010c60`
- `0x180011164`
- `0x1800117b8`

## callees

- `0x18001288c`
- `0x180012db0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800128a9`
- `OLEAUT32!__imp_VariantInit` at `0x1800128a9`
- `OLEAUT32!__imp_VariantClear` at `0x18001292f`
- `OLEAUT32!__imp_VariantClear` at `0x18001292f`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800128ff`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800128ff`

## pseudocode

```c
__int64 __fastcall XcGetNodeDWORDValue(
        struct IXMLDOMNode *a1,
        const unsigned __int16 *a2,
        unsigned int *a3,
        __int64 a4,
        unsigned int a5,
        int a6,
        unsigned int a7,
        int *a8)
{
  unsigned int NodeTypedValue; // edi
  unsigned int v12; // ebx
  HRESULT v13; // eax
  VARIANTARG pvarg; // [rsp+20h] [rbp-28h] BYREF

  VariantInit(&pvarg);
  NodeTypedValue = XcGetNodeTypedValue(a1, a2, &pvarg);
  if ( NodeTypedValue == 1168 )
  {
    v12 = 0;
    if ( a6 )
    {
      *a3 = a7;
      if ( a8 )
        *a8 = 0;
      goto LABEL_11;
    }
LABEL_12:
    v12 = 1206;
    goto LABEL_11;
  }
  if ( NodeTypedValue )
  {
LABEL_10:
    v12 = NodeTypedValue;
    goto LABEL_11;
  }
  v13 = VariantChangeType(&pvarg, &pvarg, 0, 0x13u);
  if ( !v13 )
  {
    if ( pvarg.lVal > a5 )
      goto LABEL_12;
    *a3 = pvarg.cyVal.Lo;
    if ( a8 )
      *a8 = 1;
    goto LABEL_10;
  }
  v12 = 1206;
  if ( v13 == -2147024882 )
    v12 = 14;
LABEL_11:
  VariantClear(&pvarg);
  return v12;
}

```

## disassembly

```asm
0x18001288c  mov     [rsp+arg_0], rbx
0x180012891  mov     [rsp+arg_8], rsi
0x180012896  push    rdi
0x180012897  sub     rsp, 40h
0x18001289b  mov     rdi, rcx
0x18001289e  mov     rsi, r8
0x1800128a1  lea     rcx, [rsp+48h+pvarg]; pvarg
0x1800128a6  mov     rbx, rdx
0x1800128a9  call    cs:__imp_VariantInit
0x1800128af  lea     r8, [rsp+48h+pvarg]; struct tagVARIANT *
0x1800128b4  mov     rdx, rbx; unsigned __int16 *
0x1800128b7  mov     rcx, rdi; struct IXMLDOMNode *
0x1800128ba  call    ?XcGetNodeTypedValue@@YAKPEAUIXMLDOMNode@@PEBGPEAUtagVARIANT@@@Z; XcGetNodeTypedValue(IXMLDOMNode *,ushort const *,tagVARIANT *)
0x1800128bf  mov     edi, eax
0x1800128c1  cmp     eax, 490h
0x1800128c6  jnz     short loc_1800128EA
0x1800128c8  xor     ebx, ebx
0x1800128ca  cmp     [rsp+48h+arg_28], ebx
0x1800128ce  jz      short loc_180012947
0x1800128d0  mov     eax, [rsp+48h+arg_30]
0x1800128d7  mov     [rsi], eax
0x1800128d9  mov     rax, [rsp+48h+arg_38]
0x1800128e1  test    rax, rax
0x1800128e4  jz      short loc_18001292A
0x1800128e6  mov     [rax], ebx
0x1800128e8  jmp     short loc_18001292A
0x1800128ea  test    edi, edi
0x1800128ec  jnz     short loc_180012928
0x1800128ee  lea     r9d, [rdi+13h]; vt
0x1800128f2  xor     r8d, r8d; wFlags
0x1800128f5  lea     rdx, [rsp+48h+pvarg]; pvarSrc
0x1800128fa  lea     rcx, [rsp+48h+pvarg]; pvargDest
0x1800128ff  call    cs:__imp_VariantChangeType
0x180012905  test    eax, eax
0x180012907  jnz     short loc_18001294E
0x180012909  mov     eax, dword ptr [rsp+48h+pvarg+8]
0x18001290d  cmp     eax, [rsp+48h+arg_20]
0x180012911  ja      short loc_180012947
0x180012913  mov     [rsi], eax
0x180012915  mov     rax, [rsp+48h+arg_38]
0x18001291d  test    rax, rax
0x180012920  jz      short loc_180012928
0x180012922  mov     dword ptr [rax], 1
0x180012928  mov     ebx, edi
0x18001292a  lea     rcx, [rsp+48h+pvarg]; pvarg
0x18001292f  call    cs:__imp_VariantClear
0x180012935  mov     rsi, [rsp+48h+arg_8]
0x18001293a  mov     eax, ebx
0x18001293c  mov     rbx, [rsp+48h+arg_0]
0x180012941  add     rsp, 40h
0x180012945  pop     rdi
0x180012946  retn
0x180012947  mov     ebx, 4B6h
0x18001294c  jmp     short loc_18001292A
0x18001294e  cmp     eax, 8007000Eh
0x180012953  mov     ebx, 4B6h
0x180012958  mov     ecx, 0Eh
0x18001295d  cmovz   ebx, ecx
0x180012960  jmp     short loc_18001292A
```
