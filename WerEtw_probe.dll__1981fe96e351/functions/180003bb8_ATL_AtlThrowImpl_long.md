# ATL::AtlThrowImpl(long)

- ea: `0x180003bb8`
- end: `0x180003bd7`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `31`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `48`
- callee_count: `1`
- tags: ``

## callers

- `0x1800039f4`
- `0x180003be0`
- `0x180003d20`
- `0x1800045d4`
- `0x18000527c`
- `0x1800053a8`
- `0x180006c70`
- `0x180007da8`
- `0x180008270`
- `0x18000cf40`
- `0x18000d294`
- `0x18000d4bc`
- `0x18000d770`
- `0x180011188`
- `0x18001154c`
- `0x180011630`
- `0x180011774`
- `0x180012058`
- `0x180012110`
- `0x1800125f8`
- `0x1800126e4`
- `0x1800127d0`
- `0x180013088`
- `0x180013e40`
- `0x180014000`
- `0x180014234`
- `0x1800143e0`
- `0x180014534`
- `0x1800149ac`
- `0x180014c74`
- `0x180015018`
- `0x18001578c`
- `0x180015b80`
- `0x180015e40`
- `0x1800164e0`
- `0x1800166b4`
- `0x18001753c`
- `0x180018228`
- `0x18001c1f0`
- `0x18001d5e4`
- `0x18001e0b0`
- `0x18001f11c`
- `0x18001f328`
- `0x180021f6c`
- `0x180022ca8`
- `0x180022e08`
- `0x1800239c0`
- `0x1800280cc`

## callees

- `0x1800036b4`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl(int a1)
{
  unsigned int v1; // eax

  v1 = -1073741795;
  if ( a1 == -2147024882 )
    v1 = -1073741801;
  ATL::_AtlRaiseException(v1, 0xC0000017);
  JUMPOUT(0x180003BD6LL);
}

```

## disassembly

```asm
0x180003bb8  sub     rsp, 28h
0x180003bbc  cmp     ecx, 8007000Eh
0x180003bc2  mov     eax, 0C000001Dh
0x180003bc7  mov     edx, 0C0000017h; unsigned int
0x180003bcc  cmovz   eax, edx
0x180003bcf  mov     ecx, eax; unsigned int
0x180003bd1  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
