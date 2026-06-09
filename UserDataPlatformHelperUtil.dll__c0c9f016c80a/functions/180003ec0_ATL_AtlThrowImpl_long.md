# ATL::AtlThrowImpl(long)

- ea: `0x180003ec0`
- end: `0x180003edf`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `31`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180006790`
- `0x1800078b0`
- `0x180007c90`
- `0x1800080d0`
- `0x180008b08`
- `0x180009004`

## callees

- `0x180004874`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl(int a1)
{
  DWORD v1; // eax

  v1 = -1073741795;
  if ( a1 == -2147024882 )
    v1 = -1073741801;
  ATL::_AtlRaiseException(v1);
  JUMPOUT(0x180003EDELL);
}

```

## disassembly

```asm
0x180003ec0  sub     rsp, 28h
0x180003ec4  cmp     ecx, 8007000Eh
0x180003eca  mov     eax, 0C000001Dh
0x180003ecf  mov     edx, 0C0000017h; unsigned int
0x180003ed4  cmovz   eax, edx
0x180003ed7  mov     ecx, eax; unsigned int
0x180003ed9  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
