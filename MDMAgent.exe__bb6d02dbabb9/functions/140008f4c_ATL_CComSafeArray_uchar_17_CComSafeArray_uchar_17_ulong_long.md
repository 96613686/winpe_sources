# ATL::CComSafeArray<uchar,17>::CComSafeArray<uchar,17>(ulong,long)

- ea: `0x140008f4c`
- end: `0x140008fb5`
- name: `??0?$CComSafeArray@E$0BB@@ATL@@QEAA@KJ@Z`
- size: `105`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400099c8`
- `0x14000d780`
- `0x14001351c`

## callees

- `0x140008f4c`
- `0x140009fc4`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x140008f75`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x140008f75`
- `OLEAUT32!__imp_SafeArrayLock` at `0x140008f93`
- `OLEAUT32!__imp_SafeArrayLock` at `0x140008f93`

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
0x140008f4c  push    rbx
0x140008f4e  sub     rsp, 20h
0x140008f52  mov     rbx, rcx
0x140008f55  mov     qword ptr [rcx], 0
0x140008f5c  mov     ecx, 11h; vt
0x140008f61  mov     [rsp+28h+rgsabound.cElements], edx
0x140008f65  lea     r8, [rsp+28h+rgsabound]; rgsabound
0x140008f6a  mov     [rsp+28h+rgsabound.lLbound], 0
0x140008f72  lea     edx, [rcx-10h]; cDims
0x140008f75  call    cs:__imp_SafeArrayCreate
0x140008f7c  nop     dword ptr [rax+rax+00h]
0x140008f81  mov     [rbx], rax
0x140008f84  test    rax, rax
0x140008f87  jnz     short loc_140008F90
0x140008f89  mov     eax, 8007000Eh
0x140008f8e  jmp     short loc_140008FA3
0x140008f90  mov     rcx, rax; psa
0x140008f93  call    cs:__imp_SafeArrayLock
0x140008f9a  nop     dword ptr [rax+rax+00h]
0x140008f9f  test    eax, eax
0x140008fa1  jns     short loc_140008FAB
0x140008fa3  mov     ecx, eax; int
0x140008fa5  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140008faa  int     3; Trap to Debugger
0x140008fab  mov     rax, rbx
0x140008fae  add     rsp, 20h
0x140008fb2  pop     rbx
0x140008fb3  retn
```
