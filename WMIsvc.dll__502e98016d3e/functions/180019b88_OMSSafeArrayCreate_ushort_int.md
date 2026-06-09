# OMSSafeArrayCreate(ushort,int)

- ea: `0x180019b88`
- end: `0x180019bb6`
- name: `?OMSSafeArrayCreate@@YAPEAUtagSAFEARRAY@@GH@Z`
- size: `46`
- prototype: `struct tagSAFEARRAY *__fastcall(unsigned __int16, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001c450`

## callees

- `0x180019b88`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x180019bab`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180019bab`

## pseudocode

```c
struct tagSAFEARRAY *__fastcall OMSSafeArrayCreate(VARTYPE a1, signed int a2)
{
  SAFEARRAYBOUND rgsabound; // [rsp+40h] [rbp+18h] BYREF

  if ( a2 < 1 )
    return 0;
  rgsabound.cElements = a2;
  rgsabound.lLbound = 0;
  return SafeArrayCreate(a1, 1u, &rgsabound);
}

```

## disassembly

```asm
0x180019b88  sub     rsp, 28h
0x180019b8c  cmp     edx, 1
0x180019b8f  jge     short loc_180019B95
0x180019b91  xor     eax, eax
0x180019b93  jmp     short loc_180019BB1
0x180019b95  mov     [rsp+28h+rgsabound.cElements], edx
0x180019b99  lea     r8, [rsp+28h+rgsabound]; rgsabound
0x180019b9e  mov     edx, 1; cDims
0x180019ba3  mov     [rsp+28h+rgsabound.lLbound], 0
0x180019bab  call    cs:__imp_SafeArrayCreate
0x180019bb1  add     rsp, 28h
0x180019bb5  retn
```
