# ValidateInterfaceId(ulong,ulong)

- ea: `0x180001d9c`
- end: `0x180001dc1`
- name: `?ValidateInterfaceId@@YAHKK@Z`
- size: `37`
- prototype: `__int64 __fastcall(unsigned int, unsigned int)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180001dd0`
- `0x180012f40`
- `0x180013330`
- `0x180013510`
- `0x180013720`
- `0x18001858c`
- `0x180018860`
- `0x180019070`
- `0x1800192a0`
- `0x1800195e0`
- `0x180019770`
- `0x180019e84`

## callees

- `0x180001d9c`

## pseudocode

```c
__int64 __fastcall ValidateInterfaceId(int a1, char a2)
{
  unsigned int v2; // edx
  __int64 result; // rax

  if ( (unsigned int)(a1 - 1) <= 7 || (unsigned int)(a1 - 65537) <= 3 )
    return 1;
  v2 = a2 & 1;
  result = 0;
  if ( !a1 )
    return v2;
  return result;
}

```

## disassembly

```asm
0x180001d9c  lea     eax, [rcx-1]
0x180001d9f  cmp     eax, 7
0x180001da2  jbe     short loc_180001DBB
0x180001da4  lea     eax, [rcx-10001h]
0x180001daa  cmp     eax, 3
0x180001dad  jbe     short loc_180001DBB
0x180001daf  and     edx, 1
0x180001db2  xor     eax, eax
0x180001db4  test    ecx, ecx
0x180001db6  cmovz   eax, edx
0x180001db9  retn
0x180001dbb  mov     eax, 1
0x180001dc0  retn
```
