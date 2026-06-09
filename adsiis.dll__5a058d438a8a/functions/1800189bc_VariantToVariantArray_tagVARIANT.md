# VariantToVariantArray(tagVARIANT *)

- ea: `0x1800189bc`
- end: `0x180018a3b`
- name: `?VariantToVariantArray@@YAJPEAUtagVARIANT@@@Z`
- size: `127`
- prototype: `__int64 __fastcall(struct tagVARIANT *pv)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180012574`
- `0x180018518`

## callees

- `0x1800189bc`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800189fa`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800189fa`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180018a1a`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180018a1a`

## pseudocode

```c
HRESULT __fastcall VariantToVariantArray(struct tagVARIANT *pv)
{
  HRESULT result; // eax
  SAFEARRAY *v3; // rax
  LONGLONG v4; // rdi
  LONG rgIndices; // [rsp+30h] [rbp+8h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+38h] [rbp+10h] BYREF

  if ( pv->vt == 8204 )
    return 0;
  rgIndices = 0;
  rgsabound = (SAFEARRAYBOUND)1LL;
  v3 = SafeArrayCreate(0xCu, 1u, &rgsabound);
  v4 = (LONGLONG)v3;
  if ( !v3 )
    return -2147024882;
  result = SafeArrayPutElement(v3, &rgIndices, pv);
  if ( result >= 0 )
  {
    pv->vt = 8204;
    pv->llVal = v4;
  }
  return result;
}

```

## disassembly

```asm
0x1800189bc  mov     [rsp+arg_10], rbx
0x1800189c1  mov     [rsp+arg_18], rsi
0x1800189c6  push    rdi
0x1800189c7  sub     rsp, 20h
0x1800189cb  mov     esi, 200Ch
0x1800189d0  mov     rbx, rcx
0x1800189d3  cmp     si, [rcx]
0x1800189d6  jnz     short loc_1800189DC
0x1800189d8  xor     eax, eax
0x1800189da  jmp     short loc_180018A2B
0x1800189dc  mov     edx, 1; cDims
0x1800189e1  mov     [rsp+28h+rgIndices], 0
0x1800189e9  lea     r8, [rsp+28h+rgsabound]; rgsabound
0x1800189ee  mov     qword ptr [rsp+28h+rgsabound.cElements], 1
0x1800189f7  lea     ecx, [rdx+0Bh]; vt
0x1800189fa  call    cs:__imp_SafeArrayCreate
0x180018a00  mov     rdi, rax
0x180018a03  test    rax, rax
0x180018a06  jnz     short loc_180018A0F
0x180018a08  mov     eax, 8007000Eh
0x180018a0d  jmp     short loc_180018A2B
0x180018a0f  mov     r8, rbx; pv
0x180018a12  lea     rdx, [rsp+28h+rgIndices]; rgIndices
0x180018a17  mov     rcx, rdi; psa
0x180018a1a  call    cs:__imp_SafeArrayPutElement
0x180018a20  test    eax, eax
0x180018a22  js      short loc_180018A2B
0x180018a24  mov     [rbx], si
0x180018a27  mov     [rbx+8], rdi
0x180018a2b  mov     rbx, [rsp+28h+arg_10]
0x180018a30  mov     rsi, [rsp+28h+arg_18]
0x180018a35  add     rsp, 20h
0x180018a39  pop     rdi
0x180018a3a  retn
```
