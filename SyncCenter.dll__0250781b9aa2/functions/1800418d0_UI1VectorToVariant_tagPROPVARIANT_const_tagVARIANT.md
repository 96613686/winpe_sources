# UI1VectorToVariant(tagPROPVARIANT const *,tagVARIANT *)

- ea: `0x1800418d0`
- end: `0x180041971`
- name: `?UI1VectorToVariant@@YAJPEBUtagPROPVARIANT@@PEAUtagVARIANT@@@Z`
- size: `161`
- prototype: `__int64 __fastcall(const struct tagPROPVARIANT *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800416b0`

## callees

- `0x1800418d0`
- `0x180052912`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800418ff`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800418ff`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004195b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18004195b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180041925`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180041925`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180041950`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180041950`

## pseudocode

```c
__int64 __fastcall UI1VectorToVariant(const struct tagPROPVARIANT *a1, struct tagVARIANT *a2)
{
  LONG lVal; // eax
  SAFEARRAY *v5; // rax
  SAFEARRAY *v6; // rdi
  HRESULT v7; // ebx
  SAFEARRAYBOUND rgsabound; // [rsp+40h] [rbp+8h] BYREF
  void *ppvData; // [rsp+50h] [rbp+18h] BYREF

  lVal = a1->lVal;
  rgsabound.lLbound = 0;
  rgsabound.cElements = lVal;
  v5 = SafeArrayCreate(0x11u, 1u, &rgsabound);
  v6 = v5;
  if ( v5 )
  {
    ppvData = 0;
    v7 = SafeArrayAccessData(v5, &ppvData);
    if ( v7 < 0 )
    {
      SafeArrayDestroy(v6);
    }
    else
    {
      memcpy_0(ppvData, a1->bstrblobVal.pData, a1->ulVal);
      a2->vt = 8209;
      a2->llVal = (LONGLONG)v6;
      SafeArrayUnaccessData(v6);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800418d0  mov     [rsp+arg_8], rbx
0x1800418d5  push    rsi
0x1800418d6  push    rdi
0x1800418d7  push    r14
0x1800418d9  sub     rsp, 20h
0x1800418dd  mov     eax, [rcx+8]
0x1800418e0  lea     r8, [rsp+38h+rgsabound]; rgsabound
0x1800418e5  mov     rsi, rcx
0x1800418e8  mov     [rsp+38h+rgsabound.lLbound], 0
0x1800418f0  mov     ecx, 11h; vt
0x1800418f5  mov     [rsp+38h+rgsabound.cElements], eax
0x1800418f9  mov     r14, rdx
0x1800418fc  lea     edx, [rcx-10h]; cDims
0x1800418ff  call    cs:__imp_SafeArrayCreate
0x180041905  mov     rdi, rax
0x180041908  test    rax, rax
0x18004190b  jnz     short loc_180041914
0x18004190d  mov     ebx, 8007000Eh
0x180041912  jmp     short loc_180041961
0x180041914  lea     rdx, [rsp+38h+ppvData]; ppvData
0x180041919  mov     [rsp+38h+ppvData], 0
0x180041922  mov     rcx, rdi; psa
0x180041925  call    cs:__imp_SafeArrayAccessData
0x18004192b  mov     ebx, eax
0x18004192d  test    eax, eax
0x18004192f  js      short loc_180041958
0x180041931  mov     r8d, [rsi+8]; Size
0x180041935  mov     rdx, [rsi+10h]; Src
0x180041939  mov     rcx, [rsp+38h+ppvData]; void *
0x18004193e  call    memcpy_0
0x180041943  mov     rcx, rdi; psa
0x180041946  mov     word ptr [r14], 2011h
0x18004194c  mov     [r14+8], rdi
0x180041950  call    cs:__imp_SafeArrayUnaccessData
0x180041956  jmp     short loc_180041961
0x180041958  mov     rcx, rdi; psa
0x18004195b  call    cs:__imp_SafeArrayDestroy
0x180041961  mov     eax, ebx
0x180041963  mov     rbx, [rsp+38h+arg_8]
0x180041968  add     rsp, 20h
0x18004196c  pop     r14
0x18004196e  pop     rdi
0x18004196f  pop     rsi
0x180041970  retn
```
