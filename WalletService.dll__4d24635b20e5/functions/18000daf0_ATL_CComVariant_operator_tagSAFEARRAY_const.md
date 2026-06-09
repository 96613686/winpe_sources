# ATL::CComVariant::operator=(tagSAFEARRAY const *)

- ea: `0x18000daf0`
- end: `0x18000db6b`
- name: `??4CComVariant@ATL@@QEAAAEAV01@PEBUtagSAFEARRAY@@@Z`
- size: `123`
- prototype: `VARIANTARG *__fastcall(VARIANTARG *, struct tagSAFEARRAY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f240`

## callees

- `0x18000daf0`
- `0x18000dd60`
- `0x18000ddb4`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18000db00`
- `OLEAUT32!__imp_VariantClear` at `0x18000db00`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18000db1c`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18000db1c`

## pseudocode

```c
VARIANTARG *__fastcall ATL::CComVariant::operator=(VARIANTARG *a1, struct tagSAFEARRAY *a2)
{
  HRESULT v4; // eax
  SAFEARRAY *ppsaOut; // [rsp+38h] [rbp+10h] BYREF

  VariantClear(a1);
  ppsaOut = 0;
  if ( a2 )
  {
    v4 = SafeArrayCopy(a2, &ppsaOut);
    if ( v4 < 0 || !ppsaOut )
    {
      a1->vt = 10;
      a1->lVal = v4;
      ATL::AtlThrowImpl(-2147024882);
    }
    ATL::AtlSafeArrayGetActualVartype(a2, &a1->vt);
    a1->vt |= 0x2000u;
    a1->llVal = (LONGLONG)ppsaOut;
  }
  return a1;
}

```

## disassembly

```asm
0x18000daf0  mov     [rsp+arg_0], rbx
0x18000daf5  push    rdi
0x18000daf6  sub     rsp, 20h
0x18000dafa  mov     rdi, rdx
0x18000dafd  mov     rbx, rcx
0x18000db00  call    cs:__imp_VariantClear
0x18000db06  mov     [rsp+28h+ppsaOut], 0
0x18000db0f  test    rdi, rdi
0x18000db12  jz      short loc_18000DB4A
0x18000db14  lea     rdx, [rsp+28h+ppsaOut]; ppsaOut
0x18000db19  mov     rcx, rdi; psa
0x18000db1c  call    cs:__imp_SafeArrayCopy
0x18000db22  test    eax, eax
0x18000db24  js      short loc_18000DB58
0x18000db26  cmp     [rsp+28h+ppsaOut], 0
0x18000db2c  jz      short loc_18000DB58
0x18000db2e  mov     rdx, rbx; unsigned __int16 *
0x18000db31  mov     rcx, rdi; struct tagSAFEARRAY *
0x18000db34  call    ?AtlSafeArrayGetActualVartype@ATL@@YAJPEAUtagSAFEARRAY@@PEAG@Z; ATL::AtlSafeArrayGetActualVartype(tagSAFEARRAY *,ushort *)
0x18000db39  mov     eax, 2000h
0x18000db3e  or      [rbx], ax
0x18000db41  mov     rax, [rsp+28h+ppsaOut]
0x18000db46  mov     [rbx+8], rax
0x18000db4a  mov     rax, rbx
0x18000db4d  mov     rbx, [rsp+28h+arg_0]
0x18000db52  add     rsp, 20h
0x18000db56  pop     rdi
0x18000db57  retn
0x18000db58  mov     ecx, 8007000Eh; int
0x18000db5d  mov     word ptr [rbx], 0Ah
0x18000db62  mov     [rbx+8], eax
0x18000db65  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
