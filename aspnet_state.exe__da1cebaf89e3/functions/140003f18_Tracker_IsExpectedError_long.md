# Tracker::IsExpectedError(long)

- ea: `0x140003f18`
- end: `0x140003f4c`
- name: `?IsExpectedError@Tracker@@AEAAHJ@Z`
- size: `52`
- prototype: `__int64 __fastcall(Tracker *__hidden this, int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140004108`
- `0x140004410`
- `0x140004638`

## callees

- `0x140003f18`

## pseudocode

```c
__int64 __fastcall Tracker::IsExpectedError(Tracker *this, int a2)
{
  unsigned int v2; // ecx

  v2 = 1;
  if ( a2 != -2147023670 && a2 != -2147023901 && a2 != -2147024832 && (unsigned int)(a2 + 2147014843) > 1 )
    return a2 == -2147014803;
  return v2;
}

```

## disassembly

```asm
0x140003f18  mov     ecx, 1
0x140003f1d  cmp     edx, 800704CAh
0x140003f23  jz      short loc_140003F49
0x140003f25  cmp     edx, 800703E3h
0x140003f2b  jz      short loc_140003F49
0x140003f2d  cmp     edx, 80070040h
0x140003f33  jz      short loc_140003F49
0x140003f35  lea     eax, [rdx+7FF8D8BBh]
0x140003f3b  cmp     eax, ecx
0x140003f3d  jbe     short loc_140003F49
0x140003f3f  cmp     edx, 8007276Dh
0x140003f45  jz      short loc_140003F49
0x140003f47  xor     ecx, ecx
0x140003f49  mov     eax, ecx
0x140003f4b  retn
```
