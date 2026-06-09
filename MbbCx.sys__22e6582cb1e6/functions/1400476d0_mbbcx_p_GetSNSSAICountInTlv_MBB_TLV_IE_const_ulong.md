# mbbcx_p::GetSNSSAICountInTlv(_MBB_TLV_IE * const,ulong &)

- ea: `0x1400476d0`
- end: `0x140047732`
- name: `?GetSNSSAICountInTlv@mbbcx_p@@YA?AW4MbbTlvError@1@QEAU_MBB_TLV_IE@@AEAK@Z`
- size: `98`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14003bf28`
- `0x14003c670`
- `0x14003cdf8`
- `0x14004041c`
- `0x140047458`

## callees

- `0x1400476d0`

## pseudocode

```c
__int64 __fastcall mbbcx_p::GetSNSSAICountInTlv(__int64 a1, _DWORD *a2)
{
  unsigned int v2; // r9d
  unsigned __int8 *v3; // r10
  unsigned int v4; // r8d
  unsigned int v5; // ecx
  int v6; // r11d
  unsigned int v7; // ecx

  v2 = *(_DWORD *)(a1 + 4);
  v3 = (unsigned __int8 *)(a1 + 8);
  v4 = 0;
  *a2 = 0;
  if ( v2 )
  {
    while ( !v4 )
    {
      v5 = *v3;
      if ( (unsigned __int8)v5 <= 8u && (v6 = 310, _bittest(&v6, v5)) )
      {
        v7 = v5 + 1;
        if ( v2 >= v7 )
        {
          v2 -= v7;
          v3 += v7;
          ++*a2;
        }
        else
        {
          v4 = 14;
        }
      }
      else
      {
        v4 = 13;
      }
      if ( !v2 )
      {
        if ( !v4 )
          return v4;
        break;
      }
    }
    *a2 = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x1400476d0  mov     r9d, [rcx+4]
0x1400476d4  lea     r10, [rcx+8]
0x1400476d8  xor     r8d, r8d
0x1400476db  mov     [rdx], r8d
0x1400476de  test    r9d, r9d
0x1400476e1  jz      short loc_14004772E
0x1400476e3  test    r8d, r8d
0x1400476e6  jnz     short loc_140047728
0x1400476e8  movzx   ecx, byte ptr [r10]
0x1400476ec  cmp     cl, 8
0x1400476ef  ja      short loc_140047718
0x1400476f1  mov     r11d, 136h
0x1400476f7  bt      r11d, ecx
0x1400476fb  jnb     short loc_140047718
0x1400476fd  inc     ecx
0x1400476ff  cmp     r9d, ecx
0x140047702  jnb     short loc_14004770C
0x140047704  mov     r8d, 0Eh
0x14004770a  jmp     short loc_14004771E
0x14004770c  mov     eax, ecx
0x14004770e  sub     r9d, ecx
0x140047711  add     r10, rax
0x140047714  inc     dword ptr [rdx]
0x140047716  jmp     short loc_14004771E
0x140047718  mov     r8d, 0Dh
0x14004771e  test    r9d, r9d
0x140047721  jnz     short loc_1400476E3
0x140047723  test    r8d, r8d
0x140047726  jz      short loc_14004772E
0x140047728  mov     dword ptr [rdx], 0
0x14004772e  mov     eax, r8d
0x140047731  retn
```
