# ATL::CComSafeArray<uchar,17>::CComSafeArray<uchar,17>(ulong,long)

- ea: `0x140008b48`
- end: `0x140008ba4`
- name: `??0?$CComSafeArray@E$0BB@@ATL@@QEAA@KJ@Z`
- size: `92`
- prototype: `SAFEARRAY **__fastcall(SAFEARRAY **, ULONG)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400095cc`
- `0x14000d0fc`
- `0x140012bd0`

## callees

- `0x140008b48`
- `0x140009b90`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x140008b71`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x140008b71`
- `OLEAUT32!__imp_SafeArrayLock` at `0x140008b89`
- `OLEAUT32!__imp_SafeArrayLock` at `0x140008b89`

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
LABEL_4:
    ATL::AtlThrowImpl(v4);
  return a1;
}

```

## disassembly

```asm
0x140008b48  push    rbx
0x140008b4a  sub     rsp, 20h
0x140008b4e  mov     rbx, rcx
0x140008b51  mov     qword ptr [rcx], 0
0x140008b58  mov     ecx, 11h; vt
0x140008b5d  mov     [rsp+28h+rgsabound.cElements], edx
0x140008b61  lea     r8, [rsp+28h+rgsabound]; rgsabound
0x140008b66  mov     [rsp+28h+rgsabound.lLbound], 0
0x140008b6e  lea     edx, [rcx-10h]; cDims
0x140008b71  call    cs:__imp_SafeArrayCreate
0x140008b77  mov     [rbx], rax
0x140008b7a  test    rax, rax
0x140008b7d  jnz     short loc_140008B86
0x140008b7f  mov     eax, 8007000Eh
0x140008b84  jmp     short loc_140008B93
0x140008b86  mov     rcx, rax; psa
0x140008b89  call    cs:__imp_SafeArrayLock
0x140008b8f  test    eax, eax
0x140008b91  jns     short loc_140008B9B
0x140008b93  mov     ecx, eax; int
0x140008b95  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140008b9b  mov     rax, rbx
0x140008b9e  add     rsp, 20h
0x140008ba2  pop     rbx
0x140008ba3  retn
```
