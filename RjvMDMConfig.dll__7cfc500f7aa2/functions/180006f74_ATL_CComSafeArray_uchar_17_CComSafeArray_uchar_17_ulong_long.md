# ATL::CComSafeArray<uchar,17>::CComSafeArray<uchar,17>(ulong,long)

- ea: `0x180006f74`
- end: `0x180006fdd`
- name: `??0?$CComSafeArray@E$0BB@@ATL@@QEAA@KJ@Z`
- size: `105`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007e2c`
- `0x18000c980`

## callees

- `0x180006f74`
- `0x180008484`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x180006f9d`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180006f9d`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180006fbb`
- `OLEAUT32!__imp_SafeArrayLock` at `0x180006fbb`

## pseudocode

```c
SAFEARRAY **__fastcall ATL::CComSafeArray<unsigned char,17>::CComSafeArray<unsigned char,17>(SAFEARRAY **a1, ULONG a2)
{
  SAFEARRAY *v3; // rax
  HRESULT v4; // eax
  SAFEARRAYBOUND rgsabound; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  rgsabound.cElements = a2;
  rgsabound.lLbound = 0;
  v3 = SafeArrayCreate(0x11u, 1u, &rgsabound);
  *a1 = v3;
  if ( !v3 )
  {
    v4 = -2147024882;
    goto LABEL_4;
  }
  v4 = SafeArrayLock(v3);
  if ( v4 < 0 )
  {
LABEL_4:
    ATL::AtlThrowImpl(v4);
    __debugbreak();
  }
  return a1;
}

```

## disassembly

```asm
0x180006f74  push    rbx
0x180006f76  sub     rsp, 20h
0x180006f7a  mov     rbx, rcx
0x180006f7d  mov     qword ptr [rcx], 0
0x180006f84  mov     ecx, 11h; vt
0x180006f89  mov     [rsp+28h+rgsabound.cElements], edx
0x180006f8d  lea     r8, [rsp+28h+rgsabound]; rgsabound
0x180006f92  mov     [rsp+28h+rgsabound.lLbound], 0
0x180006f9a  lea     edx, [rcx-10h]; cDims
0x180006f9d  call    cs:__imp_SafeArrayCreate
0x180006fa4  nop     dword ptr [rax+rax+00h]
0x180006fa9  mov     [rbx], rax
0x180006fac  test    rax, rax
0x180006faf  jnz     short loc_180006FB8
0x180006fb1  mov     eax, 8007000Eh
0x180006fb6  jmp     short loc_180006FCB
0x180006fb8  mov     rcx, rax; psa
0x180006fbb  call    cs:__imp_SafeArrayLock
0x180006fc2  nop     dword ptr [rax+rax+00h]
0x180006fc7  test    eax, eax
0x180006fc9  jns     short loc_180006FD3
0x180006fcb  mov     ecx, eax; int
0x180006fcd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180006fd2  int     3; Trap to Debugger
0x180006fd3  mov     rax, rbx
0x180006fd6  add     rsp, 20h
0x180006fda  pop     rbx
0x180006fdb  retn
```
