# IMixerIsValidComponentType(ulong,ulong)

- ea: `0x18000beb0`
- end: `0x18000bed6`
- name: `?IMixerIsValidComponentType@@YAHKK@Z`
- size: `38`
- prototype: `__int64 __fastcall(unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b090`

## callees

- `0x18000beb0`

## pseudocode

```c
_BOOL8 __fastcall IMixerIsValidComponentType(unsigned int a1, int a2)
{
  if ( a2 < 0 )
  {
    if ( a1 < 0x1000 )
      return 0;
    return a1 <= 0x100A;
  }
  else
  {
    return a1 <= 8;
  }
}

```

## disassembly

```asm
0x18000beb0  test    edx, edx
0x18000beb2  js      short loc_18000BEBC
0x18000beb4  cmp     ecx, 8
0x18000beb7  jbe     short loc_18000BED0
0x18000beb9  xor     eax, eax
0x18000bebb  retn
0x18000bebc  cmp     ecx, 1000h
0x18000bec2  jb      short loc_18000BEB9
0x18000bec4  xor     eax, eax
0x18000bec6  cmp     ecx, 100Ah
0x18000becc  setbe   al
0x18000becf  retn
0x18000bed0  mov     eax, 1
0x18000bed5  retn
```
