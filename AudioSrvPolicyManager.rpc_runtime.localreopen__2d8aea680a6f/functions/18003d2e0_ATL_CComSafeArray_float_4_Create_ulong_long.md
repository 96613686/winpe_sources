# ATL::CComSafeArray<float,4>::Create(ulong,long)

- ea: `0x18003d2e0`
- end: `0x18003d333`
- name: `?Create@?$CComSafeArray@M$03@ATL@@QEAAJKJ@Z`
- size: `83`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800137b0`

## callees

- `0x18003d2e0`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x18003d30f`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18003d30f`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18003d327`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18003d327`

## pseudocode

```c
HRESULT __fastcall ATL::CComSafeArray<float,4>::Create(SAFEARRAY **a1, ULONG a2)
{
  bool v2; // zf
  SAFEARRAY *v5; // rax
  SAFEARRAYBOUND rgsabound; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1 == 0;
  rgsabound.cElements = a2;
  rgsabound.lLbound = 0;
  if ( !v2 )
    return -2147467259;
  v5 = SafeArrayCreate(4u, 1u, &rgsabound);
  *a1 = v5;
  if ( v5 )
    return SafeArrayLock(v5);
  else
    return -2147024882;
}

```

## disassembly

```asm
0x18003d2e0  push    rbx
0x18003d2e2  sub     rsp, 20h
0x18003d2e6  cmp     qword ptr [rcx], 0
0x18003d2ea  mov     rbx, rcx
0x18003d2ed  mov     [rsp+28h+rgsabound.cElements], edx
0x18003d2f1  mov     [rsp+28h+rgsabound.lLbound], 0
0x18003d2f9  jz      short loc_18003D302
0x18003d2fb  mov     eax, 80004005h
0x18003d300  jmp     short loc_18003D32D
0x18003d302  mov     ecx, 4; vt
0x18003d307  lea     r8, [rsp+28h+rgsabound]; rgsabound
0x18003d30c  lea     edx, [rcx-3]; cDims
0x18003d30f  call    cs:__imp_SafeArrayCreate
0x18003d315  mov     [rbx], rax
0x18003d318  test    rax, rax
0x18003d31b  jnz     short loc_18003D324
0x18003d31d  mov     eax, 8007000Eh
0x18003d322  jmp     short loc_18003D32D
0x18003d324  mov     rcx, rax; psa
0x18003d327  call    cs:__imp_SafeArrayLock
0x18003d32d  add     rsp, 20h
0x18003d331  pop     rbx
0x18003d332  retn
```
