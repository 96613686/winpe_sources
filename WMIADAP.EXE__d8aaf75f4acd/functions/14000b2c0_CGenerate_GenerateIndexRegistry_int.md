# CGenerate::GenerateIndexRegistry(int)

- ea: `0x14000b2c0`
- end: `0x14000b2dc`
- name: `?GenerateIndexRegistry@CGenerate@@AEAAKH@Z`
- size: `28`
- prototype: `__int64 __fastcall(CGenerate *this, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000b2e4`

## callees

- `0x14000b2c0`

## pseudocode

```c
__int64 __fastcall CGenerate::GenerateIndexRegistry(CGenerate *this, int a2)
{
  __int64 result; // rax
  int v3; // ecx

  if ( a2 )
  {
    result = 0;
    v3 = 0;
  }
  else
  {
    result = (unsigned int)(2 * dword_140024FB8);
    v3 = dword_140024FB8 + 1;
  }
  dword_140024FB8 = v3;
  return result;
}

```

## disassembly

```asm
0x14000b2c0  test    edx, edx
0x14000b2c2  jz      short loc_14000B2CA
0x14000b2c4  xor     eax, eax
0x14000b2c6  xor     ecx, ecx
0x14000b2c8  jmp     short loc_14000B2D5
0x14000b2ca  mov     ecx, cs:dword_140024FB8
0x14000b2d0  lea     eax, [rcx+rcx]
0x14000b2d3  inc     ecx
0x14000b2d5  mov     cs:dword_140024FB8, ecx
0x14000b2db  retn
```
