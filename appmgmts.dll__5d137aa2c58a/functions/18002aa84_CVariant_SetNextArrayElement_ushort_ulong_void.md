# CVariant::SetNextArrayElement(ushort,ulong,void *)

- ea: `0x18002aa84`
- end: `0x18002ab1c`
- name: `?SetNextArrayElement@CVariant@@AEAAJGKPEAX@Z`
- size: `152`
- prototype: `HRESULT __fastcall(CVariant *this, VARTYPE, ULONG, void *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18002a054`
- `0x18002a110`
- `0x18002a1cc`

## callees

- `0x18002aa84`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002aace`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002aace`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18002aaf4`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18002aaf4`

## pseudocode

```c
HRESULT __fastcall CVariant::SetNextArrayElement(CVariant *this, VARTYPE a2, ULONG a3, void *a4)
{
  HRESULT result; // eax
  LONG *v9; // rdi
  SAFEARRAY *v10; // rax
  SAFEARRAYBOUND rgsabound; // [rsp+20h] [rbp-48h] BYREF

  if ( !a3 )
    return 1;
  v9 = (LONG *)((char *)this + 24);
  if ( !*((_DWORD *)this + 6) )
  {
    rgsabound.lLbound = 0;
    rgsabound.cElements = a3;
    v10 = SafeArrayCreate(a2, 1u, &rgsabound);
    if ( !v10 )
      return -2147024882;
    *((_QWORD *)this + 1) = v10;
    *(_WORD *)this = a2 | 0x2000;
    *((_DWORD *)this + 7) = a3;
  }
  result = SafeArrayPutElement(*((SAFEARRAY **)this + 1), v9, a4);
  if ( result >= 0 && ++*v9 == *((_DWORD *)this + 7) )
    return 1;
  return result;
}

```

## disassembly

```asm
0x18002aa84  push    rbx
0x18002aa86  push    rbp
0x18002aa87  push    rsi
0x18002aa88  push    rdi
0x18002aa89  push    r14
0x18002aa8b  push    r15
0x18002aa8d  sub     rsp, 38h
0x18002aa91  mov     r15, r9
0x18002aa94  mov     ebp, r8d
0x18002aa97  movzx   r14d, dx
0x18002aa9b  mov     rsi, rcx
0x18002aa9e  test    r8d, r8d
0x18002aaa1  jnz     short loc_18002AAA9
0x18002aaa3  lea     eax, [r8+1]
0x18002aaa7  jmp     short loc_18002AB08
0x18002aaa9  lea     rdi, [rcx+18h]
0x18002aaad  mov     ebx, 1
0x18002aab2  cmp     dword ptr [rdi], 0
0x18002aab5  jnz     short loc_18002AAEA
0x18002aab7  lea     r8, [rsp+68h+rgsabound]; rgsabound
0x18002aabc  mov     [rsp+68h+rgsabound.lLbound], 0
0x18002aac4  mov     edx, ebx; cDims
0x18002aac6  mov     [rsp+68h+rgsabound.cElements], ebp
0x18002aaca  movzx   ecx, r14w; vt
0x18002aace  call    cs:__imp_SafeArrayCreate
0x18002aad4  test    rax, rax
0x18002aad7  jz      short loc_18002AB15
0x18002aad9  or      r14w, 2000h
0x18002aadf  mov     [rsi+8], rax
0x18002aae3  mov     [rsi], r14w
0x18002aae7  mov     [rsi+1Ch], ebp
0x18002aaea  mov     rcx, [rsi+8]; psa
0x18002aaee  mov     r8, r15; pv
0x18002aaf1  mov     rdx, rdi; rgIndices
0x18002aaf4  call    cs:__imp_SafeArrayPutElement
0x18002aafa  test    eax, eax
0x18002aafc  js      short loc_18002AB08
0x18002aafe  add     [rdi], ebx
0x18002ab00  mov     ecx, [rdi]
0x18002ab02  cmp     ecx, [rsi+1Ch]
0x18002ab05  cmovz   eax, ebx
0x18002ab08  add     rsp, 38h
0x18002ab0c  pop     r15
0x18002ab0e  pop     r14
0x18002ab10  pop     rdi
0x18002ab11  pop     rsi
0x18002ab12  pop     rbp
0x18002ab13  pop     rbx
0x18002ab14  retn
0x18002ab15  mov     eax, 8007000Eh
0x18002ab1a  jmp     short loc_18002AB08
```
