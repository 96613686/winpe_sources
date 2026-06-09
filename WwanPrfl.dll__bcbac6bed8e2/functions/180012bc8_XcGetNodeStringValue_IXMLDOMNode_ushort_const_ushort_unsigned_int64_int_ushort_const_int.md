# XcGetNodeStringValue(IXMLDOMNode *,ushort const *,ushort *,unsigned __int64,int,ushort const *,int *)

- ea: `0x180012bc8`
- end: `0x180012da7`
- name: `?XcGetNodeStringValue@@YAKPEAUIXMLDOMNode@@PEBGPEAG_KH1PEAH@Z`
- size: `479`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, const unsigned __int16 *, unsigned __int16 *, unsigned __int64, int, const unsigned __int16 *, int *)`
- caller_count: `14`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000b4b0`
- `0x18000ba90`
- `0x18000bd80`
- `0x18000bf80`
- `0x18000c050`
- `0x18000c280`
- `0x18000c4a0`
- `0x18000cf80`
- `0x18000f26c`
- `0x18000f510`
- `0x180010820`
- `0x180010a24`
- `0x180010c60`
- `0x180011ba0`

## callees

- `0x180012bc8`
- `0x180012db0`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180012be3`
- `OLEAUT32!__imp_VariantInit` at `0x180012be3`
- `OLEAUT32!__imp_VariantClear` at `0x180012d95`
- `OLEAUT32!__imp_VariantClear` at `0x180012d95`

## pseudocode

```c
__int64 __fastcall XcGetNodeStringValue(
        struct IXMLDOMNode *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int64 a4,
        int a5,
        const unsigned __int16 *a6,
        int *a7)
{
  unsigned int NodeTypedValue; // eax
  unsigned int v12; // ebx
  const unsigned __int16 *v13; // rdx
  __int64 v14; // rax
  unsigned __int16 *v15; // rax
  BSTR bstrVal; // rdx
  unsigned __int64 v17; // rax
  __int64 v18; // rax
  unsigned __int16 *v19; // rax
  VARIANTARG pvarg; // [rsp+20h] [rbp-48h] BYREF

  VariantInit(&pvarg);
  NodeTypedValue = XcGetNodeTypedValue(a1, a2, &pvarg);
  v12 = NodeTypedValue;
  if ( NodeTypedValue == 1168 )
  {
    if ( a5 )
    {
      v13 = a6;
      if ( !a6 )
      {
        *a3 = 0;
LABEL_5:
        v12 = 0;
LABEL_19:
        if ( a7 )
          *a7 = 0;
        goto LABEL_42;
      }
      if ( a4 )
      {
        if ( a4 <= 0x7FFFFFFF )
        {
          v14 = 2147483646;
          do
          {
            if ( !v14 )
              break;
            if ( !*v13 )
              break;
            *a3++ = *v13++;
            --v14;
            --a4;
          }
          while ( a4 );
          v15 = a3 - 1;
          v12 = a4 == 0 ? 0x8007007A : 0;
          if ( a4 )
            v15 = a3;
          *v15 = 0;
          if ( a4 )
            goto LABEL_5;
        }
        else
        {
          LOWORD(v12) = 87;
          *a3 = 0;
        }
      }
      else
      {
        LOWORD(v12) = 87;
      }
      v12 = (unsigned __int16)v12;
      if ( (_WORD)v12 )
        goto LABEL_42;
      goto LABEL_19;
    }
LABEL_41:
    v12 = 1206;
    goto LABEL_42;
  }
  if ( NodeTypedValue )
    goto LABEL_42;
  bstrVal = pvarg.bstrVal;
  v17 = -1;
  do
    ++v17;
  while ( *(_WORD *)(pvarg.llVal + 2 * v17) );
  if ( v17 >= a4 )
    goto LABEL_41;
  if ( !a4 )
  {
    LOWORD(v12) = 87;
    goto LABEL_38;
  }
  if ( a4 > 0x7FFFFFFF )
  {
    LOWORD(v12) = 87;
    *a3 = 0;
    goto LABEL_38;
  }
  v18 = 2147483646;
  do
  {
    if ( !v18 )
      break;
    if ( !*bstrVal )
      break;
    *a3++ = *bstrVal++;
    --v18;
    --a4;
  }
  while ( a4 );
  v19 = a3 - 1;
  v12 = a4 == 0 ? 0x8007007A : 0;
  if ( a4 )
    v19 = a3;
  *v19 = 0;
  if ( !a4 )
  {
LABEL_38:
    v12 = (unsigned __int16)v12;
    if ( (_WORD)v12 )
      goto LABEL_42;
    goto LABEL_39;
  }
  v12 = 0;
LABEL_39:
  if ( a7 )
    *a7 = 1;
LABEL_42:
  VariantClear(&pvarg);
  return v12;
}

```

## disassembly

```asm
0x180012bc8  push    rbx
0x180012bca  push    rsi
0x180012bcb  push    rdi
0x180012bcc  push    r14
0x180012bce  sub     rsp, 48h
0x180012bd2  mov     rdi, rcx
0x180012bd5  mov     rsi, r9
0x180012bd8  lea     rcx, [rsp+68h+pvarg]; pvarg
0x180012bdd  mov     r14, r8
0x180012be0  mov     rbx, rdx
0x180012be3  call    cs:__imp_VariantInit
0x180012be9  lea     r8, [rsp+68h+pvarg]; struct tagVARIANT *
0x180012bee  mov     rdx, rbx; unsigned __int16 *
0x180012bf1  mov     rcx, rdi; struct IXMLDOMNode *
0x180012bf4  call    ?XcGetNodeTypedValue@@YAKPEAUIXMLDOMNode@@PEBGPEAUtagVARIANT@@@Z; XcGetNodeTypedValue(IXMLDOMNode *,ushort const *,tagVARIANT *)
0x180012bf9  xor     ecx, ecx
0x180012bfb  mov     ebx, eax
0x180012bfd  cmp     eax, 490h
0x180012c02  jnz     loc_180012CCC
0x180012c08  cmp     [rsp+68h+arg_20], ecx
0x180012c0f  jz      loc_180012D8B
0x180012c15  mov     rdx, [rsp+68h+arg_28]
0x180012c1d  test    rdx, rdx
0x180012c20  jnz     short loc_180012C2D
0x180012c22  mov     [r14], cx
0x180012c26  mov     ebx, ecx
0x180012c28  jmp     loc_180012CB4
0x180012c2d  test    rsi, rsi
0x180012c30  jz      short loc_180012C9B
0x180012c32  cmp     rsi, 7FFFFFFFh
0x180012c39  jbe     short loc_180012C42
0x180012c3b  mov     ebx, 80070057h
0x180012c40  jmp     short loc_180012CA5
0x180012c42  mov     eax, 7FFFFFFEh
0x180012c47  test    rax, rax
0x180012c4a  jz      short loc_180012C6B
0x180012c4c  movzx   r8d, word ptr [rdx]
0x180012c50  test    r8w, r8w
0x180012c54  jz      short loc_180012C6B
0x180012c56  mov     [r14], r8w
0x180012c5a  add     rdx, 2
0x180012c5e  add     r14, 2
0x180012c62  dec     rax
0x180012c65  sub     rsi, 1
0x180012c69  jnz     short loc_180012C47
0x180012c6b  mov     rax, rsi
0x180012c6e  neg     rax
0x180012c71  lea     rax, [r14-2]
0x180012c75  sbb     ebx, ebx
0x180012c77  not     ebx
0x180012c79  and     ebx, 8007007Ah
0x180012c7f  test    rsi, rsi
0x180012c82  cmovnz  rax, r14
0x180012c86  mov     [rax], cx
0x180012c89  jnz     short loc_180012C26
0x180012c8b  mov     eax, ebx
0x180012c8d  and     eax, 1FFF0000h
0x180012c92  cmp     eax, 70000h
0x180012c97  jz      short loc_180012CA9
0x180012c99  jmp     short loc_180012CAC
0x180012c9b  mov     ebx, 80070057h
0x180012ca0  test    rsi, rsi
0x180012ca3  jz      short loc_180012CA9
0x180012ca5  mov     [r14], cx
0x180012ca9  movzx   ebx, bx
0x180012cac  test    ebx, ebx
0x180012cae  jnz     loc_180012D90
0x180012cb4  mov     rax, [rsp+68h+arg_30]
0x180012cbc  test    rax, rax
0x180012cbf  jz      loc_180012D90
0x180012cc5  mov     [rax], ecx
0x180012cc7  jmp     loc_180012D90
0x180012ccc  test    eax, eax
0x180012cce  jnz     loc_180012D90
0x180012cd4  mov     rdx, qword ptr [rsp+68h+pvarg+8]
0x180012cd9  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012cdd  inc     rax
0x180012ce0  cmp     [rdx+rax*2], cx
0x180012ce4  jnz     short loc_180012CDD
0x180012ce6  cmp     rax, rsi
0x180012ce9  jnb     loc_180012D8B
0x180012cef  test    rsi, rsi
0x180012cf2  jz      short loc_180012D61
0x180012cf4  cmp     rsi, 7FFFFFFFh
0x180012cfb  jbe     short loc_180012D04
0x180012cfd  mov     ebx, 80070057h
0x180012d02  jmp     short loc_180012D6B
0x180012d04  mov     eax, 7FFFFFFEh
0x180012d09  test    rax, rax
0x180012d0c  jz      short loc_180012D2D
0x180012d0e  movzx   r8d, word ptr [rdx]
0x180012d12  test    r8w, r8w
0x180012d16  jz      short loc_180012D2D
0x180012d18  mov     [r14], r8w
0x180012d1c  add     rdx, 2
0x180012d20  add     r14, 2
0x180012d24  dec     rax
0x180012d27  sub     rsi, 1
0x180012d2b  jnz     short loc_180012D09
0x180012d2d  mov     rax, rsi
0x180012d30  neg     rax
0x180012d33  lea     rax, [r14-2]
0x180012d37  sbb     ebx, ebx
0x180012d39  not     ebx
0x180012d3b  and     ebx, 8007007Ah
0x180012d41  test    rsi, rsi
0x180012d44  cmovnz  rax, r14
0x180012d48  mov     [rax], cx
0x180012d4b  jz      short loc_180012D51
0x180012d4d  mov     ebx, ecx
0x180012d4f  jmp     short loc_180012D76
0x180012d51  mov     eax, ebx
0x180012d53  and     eax, 1FFF0000h
0x180012d58  cmp     eax, 70000h
0x180012d5d  jnz     short loc_180012D72
0x180012d5f  jmp     short loc_180012D6F
0x180012d61  mov     ebx, 80070057h
0x180012d66  test    rsi, rsi
0x180012d69  jz      short loc_180012D6F
0x180012d6b  mov     [r14], cx
0x180012d6f  movzx   ebx, bx
0x180012d72  test    ebx, ebx
0x180012d74  jnz     short loc_180012D90
0x180012d76  mov     rax, [rsp+68h+arg_30]
0x180012d7e  test    rax, rax
0x180012d81  jz      short loc_180012D90
0x180012d83  mov     dword ptr [rax], 1
0x180012d89  jmp     short loc_180012D90
0x180012d8b  mov     ebx, 4B6h
0x180012d90  lea     rcx, [rsp+68h+pvarg]; pvarg
0x180012d95  call    cs:__imp_VariantClear
0x180012d9b  mov     eax, ebx
0x180012d9d  add     rsp, 48h
0x180012da1  pop     r14
0x180012da3  pop     rdi
0x180012da4  pop     rsi
0x180012da5  pop     rbx
0x180012da6  retn
```
