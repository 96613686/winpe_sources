# ATL::CComSafeArray<float,4>::Create(ulong,long)

- ea: `0x18006286c`
- end: `0x1800628bf`
- name: `?Create@?$CComSafeArray@M$03@ATL@@QEAAJKJ@Z`
- size: `83`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800628c8`

## callees

- `0x18006286c`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x18006289b`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18006289b`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1800628b3`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1800628b3`

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
0x18006286c  push    rbx
0x18006286e  sub     rsp, 20h
0x180062872  cmp     qword ptr [rcx], 0
0x180062876  mov     rbx, rcx
0x180062879  mov     [rsp+28h+rgsabound.cElements], edx
0x18006287d  mov     [rsp+28h+rgsabound.lLbound], 0
0x180062885  jz      short loc_18006288E
0x180062887  mov     eax, 80004005h
0x18006288c  jmp     short loc_1800628B9
0x18006288e  mov     ecx, 4; vt
0x180062893  lea     r8, [rsp+28h+rgsabound]; rgsabound
0x180062898  lea     edx, [rcx-3]; cDims
0x18006289b  call    cs:__imp_SafeArrayCreate
0x1800628a1  mov     [rbx], rax
0x1800628a4  test    rax, rax
0x1800628a7  jnz     short loc_1800628B0
0x1800628a9  mov     eax, 8007000Eh
0x1800628ae  jmp     short loc_1800628B9
0x1800628b0  mov     rcx, rax; psa
0x1800628b3  call    cs:__imp_SafeArrayLock
0x1800628b9  add     rsp, 20h
0x1800628bd  pop     rbx
0x1800628be  retn
```
