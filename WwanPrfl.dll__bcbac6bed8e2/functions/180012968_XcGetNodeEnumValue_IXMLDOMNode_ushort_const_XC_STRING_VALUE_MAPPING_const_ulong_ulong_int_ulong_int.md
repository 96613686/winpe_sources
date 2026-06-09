# XcGetNodeEnumValue(IXMLDOMNode *,ushort const *,_XC_STRING_VALUE_MAPPING const *,ulong,ulong *,int,ulong,int *)

- ea: `0x180012968`
- end: `0x180012a43`
- name: `?XcGetNodeEnumValue@@YAKPEAUIXMLDOMNode@@PEBGPEBU_XC_STRING_VALUE_MAPPING@@KPEAKHKPEAH@Z`
- size: `219`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, const unsigned __int16 *, LPCWSTR *, unsigned int, unsigned int *, int, unsigned int, int *)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000b670`
- `0x18000bd80`
- `0x18000c4a0`
- `0x18000cf80`
- `0x18000f26c`
- `0x180011164`
- `0x180011ba0`

## callees

- `0x180012968`
- `0x180012db0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180012984`
- `OLEAUT32!__imp_VariantInit` at `0x180012984`
- `OLEAUT32!__imp_VariantClear` at `0x180012a30`
- `OLEAUT32!__imp_VariantClear` at `0x180012a30`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800129f5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800129f5`

## pseudocode

```c
__int64 __fastcall XcGetNodeEnumValue(
        struct IXMLDOMNode *a1,
        const unsigned __int16 *a2,
        LPCWSTR *a3,
        unsigned int a4,
        unsigned int *a5,
        int a6,
        unsigned int a7,
        int *a8)
{
  unsigned int NodeTypedValue; // eax
  unsigned int v13; // ebx
  unsigned int v14; // edi
  VARIANTARG pvarg; // [rsp+20h] [rbp-48h] BYREF

  VariantInit(&pvarg);
  NodeTypedValue = XcGetNodeTypedValue(a1, a2, &pvarg);
  v13 = NodeTypedValue;
  if ( NodeTypedValue == 1168 )
  {
    if ( a6 )
    {
      v13 = 0;
      *a5 = a7;
      if ( a8 )
        *a8 = 0;
    }
    else
    {
      v13 = 1206;
    }
  }
  else if ( !NodeTypedValue )
  {
    v14 = 0;
    v13 = 1206;
    if ( a4 )
    {
      while ( lstrcmpW(a3[2 * v14], pvarg.bstrVal) )
      {
        if ( ++v14 >= a4 )
          goto LABEL_13;
      }
      v13 = 0;
      *a5 = (unsigned int)a3[2 * v14 + 1];
      if ( a8 )
        *a8 = 1;
    }
  }
LABEL_13:
  VariantClear(&pvarg);
  return v13;
}

```

## disassembly

```asm
0x180012968  push    rbx
0x18001296a  push    rbp
0x18001296b  push    rsi
0x18001296c  push    rdi
0x18001296d  push    r14
0x18001296f  sub     rsp, 40h
0x180012973  mov     rdi, rcx
0x180012976  mov     ebp, r9d
0x180012979  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18001297e  mov     r14, r8
0x180012981  mov     rbx, rdx
0x180012984  call    cs:__imp_VariantInit
0x18001298a  lea     r8, [rsp+68h+pvarg]; struct tagVARIANT *
0x18001298f  mov     rdx, rbx; unsigned __int16 *
0x180012992  mov     rcx, rdi; struct IXMLDOMNode *
0x180012995  call    ?XcGetNodeTypedValue@@YAKPEAUIXMLDOMNode@@PEBGPEAUtagVARIANT@@@Z; XcGetNodeTypedValue(IXMLDOMNode *,ushort const *,tagVARIANT *)
0x18001299a  mov     ebx, eax
0x18001299c  cmp     eax, 490h
0x1800129a1  jnz     short loc_1800129D8
0x1800129a3  cmp     [rsp+68h+arg_28], 0
0x1800129ab  jz      short loc_1800129D1
0x1800129ad  mov     rax, [rsp+68h+arg_20]
0x1800129b5  xor     ebx, ebx
0x1800129b7  mov     ecx, [rsp+68h+arg_30]
0x1800129be  mov     [rax], ecx
0x1800129c0  mov     rax, [rsp+68h+arg_38]
0x1800129c8  test    rax, rax
0x1800129cb  jz      short loc_180012A2B
0x1800129cd  mov     [rax], ebx
0x1800129cf  jmp     short loc_180012A2B
0x1800129d1  mov     ebx, 4B6h
0x1800129d6  jmp     short loc_180012A2B
0x1800129d8  test    eax, eax
0x1800129da  jnz     short loc_180012A2B
0x1800129dc  xor     edi, edi
0x1800129de  mov     ebx, 4B6h
0x1800129e3  test    ebp, ebp
0x1800129e5  jz      short loc_180012A2B
0x1800129e7  mov     rdx, qword ptr [rsp+68h+pvarg+8]; lpString2
0x1800129ec  mov     esi, edi
0x1800129ee  add     rsi, rsi
0x1800129f1  mov     rcx, [r14+rsi*8]; lpString1
0x1800129f5  call    cs:__imp_lstrcmpW
0x1800129fb  test    eax, eax
0x1800129fd  jz      short loc_180012A07
0x1800129ff  inc     edi
0x180012a01  cmp     edi, ebp
0x180012a03  jb      short loc_1800129E7
0x180012a05  jmp     short loc_180012A2B
0x180012a07  mov     rax, [rsp+68h+arg_20]
0x180012a0f  xor     ebx, ebx
0x180012a11  mov     ecx, [r14+rsi*8+8]
0x180012a16  mov     [rax], ecx
0x180012a18  mov     rax, [rsp+68h+arg_38]
0x180012a20  test    rax, rax
0x180012a23  jz      short loc_180012A2B
0x180012a25  mov     dword ptr [rax], 1
0x180012a2b  lea     rcx, [rsp+68h+pvarg]; pvarg
0x180012a30  call    cs:__imp_VariantClear
0x180012a36  mov     eax, ebx
0x180012a38  add     rsp, 40h
0x180012a3c  pop     r14
0x180012a3e  pop     rdi
0x180012a3f  pop     rsi
0x180012a40  pop     rbp
0x180012a41  pop     rbx
0x180012a42  retn
```
