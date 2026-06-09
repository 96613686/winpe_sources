# DavpParseUInt16

- ea: `0x180004850`
- end: `0x1800048a0`
- name: `DavpParseUInt16`
- size: `80`
- prototype: `__int64 __fastcall(unsigned __int16 **, _WORD *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180001460`
- `0x180001e80`
- `0x1800027c0`
- `0x180003830`
- `0x180003e10`

## callees

- `0x180004850`

## pseudocode

```c
__int64 __fastcall DavpParseUInt16(unsigned __int16 **a1, _WORD *a2)
{
  unsigned __int16 *v2; // rax
  unsigned int v3; // r9d
  int v4; // r8d
  unsigned int v5; // r8d
  __int64 result; // rax

  v2 = *a1;
  v3 = 0;
  while ( 1 )
  {
    v4 = *v2;
    if ( !(_WORD)v4 )
      break;
    v5 = v4 - 48;
    if ( v5 > 9 )
      break;
    v3 = v5 + 10 * v3;
    if ( v3 > 0xFFFF )
      return 87;
    ++v2;
  }
  if ( v2 == *a1 )
    return 87;
  *a1 = v2;
  result = 0;
  *a2 = v3;
  return result;
}

```

## disassembly

```asm
0x180004850  mov     r10, [rcx]
0x180004853  mov     r11, rcx
0x180004856  mov     rax, r10
0x180004859  xor     r9d, r9d
0x18000485c  nop     dword ptr [rax+00h]
0x180004860  movzx   r8d, word ptr [rax]
0x180004864  test    r8w, r8w
0x180004868  jz      short loc_18000488B
0x18000486a  add     r8d, 0FFFFFFD0h
0x18000486e  cmp     r8d, 9
0x180004872  ja      short loc_18000488B
0x180004874  lea     ecx, [r9+r9*4]
0x180004878  lea     r9d, [r8+rcx*2]
0x18000487c  cmp     r9d, 0FFFFh
0x180004883  ja      short loc_180004890
0x180004885  add     rax, 2
0x180004889  jmp     short loc_180004860
0x18000488b  cmp     rax, r10
0x18000488e  jnz     short loc_180004896
0x180004890  mov     eax, 57h ; 'W'
0x180004895  retn
0x180004896  mov     [r11], rax
0x180004899  xor     eax, eax
0x18000489b  mov     [rdx], r9w
0x18000489f  retn
```
