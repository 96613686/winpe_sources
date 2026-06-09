# WLIDpExceptionFilter(ulong)

- ea: `0x180007334`
- end: `0x180007358`
- name: `?WLIDpExceptionFilter@@YAHK@Z`
- size: `36`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800066d4`
- `0x180006a78`

## callees

- `0x180007334`

## pseudocode

```c
__int64 __fastcall WLIDpExceptionFilter(int a1)
{
  __int64 v1; // rdx
  unsigned int v2; // r8d

  v1 = 0;
  v2 = 1;
  while ( a1 != *((_DWORD *)qword_180010A60 + v1) )
  {
    v1 = (unsigned int)(v1 + 1);
    if ( (int)v1 >= 14 )
      return v2;
  }
  return 0;
}

```

## disassembly

```asm
0x180007334  xor     edx, edx
0x180007336  lea     r8d, [rdx+1]
0x18000733a  lea     r9, qword_180010A60
0x180007341  cmp     ecx, [r9+rdx*4]
0x180007345  jz      short loc_180007351
0x180007347  add     edx, r8d
0x18000734a  cmp     edx, 0Eh
0x18000734d  jl      short loc_18000733A
0x18000734f  jmp     short loc_180007354
0x180007351  xor     r8d, r8d
0x180007354  mov     eax, r8d
0x180007357  retn
```
