# initialise_decoder_bitbuf

- ea: `0x1800081c8`
- end: `0x180008209`
- name: `initialise_decoder_bitbuf`
- size: `65`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004a9c`
- `0x180007c94`

## callees

- `0x1800081c8`

## pseudocode

```c
__int64 __fastcall initialise_decoder_bitbuf(__int64 a1)
{
  unsigned __int16 *v1; // r8
  __int64 result; // rax
  int v3; // edx

  if ( *(_DWORD *)(a1 + 88) != 3 )
  {
    v1 = *(unsigned __int16 **)(a1 + 8);
    if ( (unsigned __int64)(v1 + 2) <= *(_QWORD *)(a1 + 16) )
    {
      result = *((unsigned __int8 *)v1 + 2);
      v3 = result | ((*((unsigned __int8 *)v1 + 3) | (*v1 << 8)) << 8);
      *(_BYTE *)(a1 + 4) = 16;
      *(_DWORD *)a1 = v3;
      *(_QWORD *)(a1 + 8) = v1 + 2;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800081c8  cmp     dword ptr [rcx+58h], 3
0x1800081cc  jz      short locret_180008208
0x1800081ce  mov     r8, [rcx+8]
0x1800081d2  lea     r9, [r8+4]
0x1800081d6  cmp     r9, [rcx+10h]
0x1800081da  ja      short locret_180008208
0x1800081dc  movzx   eax, byte ptr [r8]
0x1800081e0  movzx   edx, byte ptr [r8+1]
0x1800081e5  shl     edx, 8
0x1800081e8  or      edx, eax
0x1800081ea  movzx   eax, byte ptr [r8+3]
0x1800081ef  shl     edx, 8
0x1800081f2  or      edx, eax
0x1800081f4  movzx   eax, byte ptr [r8+2]
0x1800081f9  shl     edx, 8
0x1800081fc  or      edx, eax
0x1800081fe  mov     byte ptr [rcx+4], 10h
0x180008202  mov     [rcx], edx
0x180008204  mov     [rcx+8], r9
0x180008208  retn
```
