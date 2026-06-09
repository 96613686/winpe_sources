# Utf8Decoder::ProcessCodeUnit(char,char32_t &)

- ea: `0x1800046f0`
- end: `0x18000479f`
- name: `?ProcessCodeUnit@Utf8Decoder@@QEAAKDAEA_U@Z`
- size: `175`
- prototype: `__int64 __fastcall(Utf8Decoder *this, unsigned __int8, char32_t *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004160`
- `0x1800044c0`

## callees

- `0x1800046f0`

## pseudocode

```c
__int64 __fastcall Utf8Decoder::ProcessCodeUnit(Utf8Decoder *this, unsigned __int8 a2, char32_t *a3)
{
  char v4; // cl
  __int64 v6; // r8
  unsigned int v7; // edx
  char v8; // cl

  v4 = *((_BYTE *)this + 5);
  if ( v4 )
  {
    if ( (a2 & 0xC0) == 0x80 )
    {
      v7 = (*(_DWORD *)this << 6) | a2 & 0x3F;
      v8 = v4 - 1;
      *(_DWORD *)this = v7;
      *((_BYTE *)this + 5) = v8;
      if ( v8 )
        return 997;
      if ( v7 >= dword_1800076F0[*((unsigned __int8 *)this + 4)] && (v7 <= 0xD7FF || v7 - 57344 <= 0x101FFF) )
      {
        *a3 = v7;
        return 0;
      }
    }
  }
  else
  {
    if ( a2 < 0x80u )
    {
      *a3 = (char)a2;
      return 0;
    }
    v6 = *((unsigned __int8 *)qword_1800074E8 + ((unsigned __int64)a2 >> 3));
    if ( (_BYTE)v6 )
    {
      *((_BYTE *)this + 4) = v6;
      *(_DWORD *)this = a2 & ~(unsigned __int8)byte_1800076E1[2 * v6];
      *((_BYTE *)this + 5) = v6 - 1;
      return 997;
    }
  }
  return 582;
}

```

## disassembly

```asm
0x1800046f0  mov     r9, rcx
0x1800046f3  movzx   ecx, byte ptr [rcx+5]
0x1800046f7  test    cl, cl
0x1800046f9  jnz     short loc_180004749
0x1800046fb  cmp     dl, 80h
0x1800046fe  jnb     short loc_180004709
0x180004700  movsx   eax, dl
0x180004703  mov     [r8], eax
0x180004706  xor     eax, eax
0x180004708  retn
0x180004709  movzx   eax, dl
0x18000470c  lea     rcx, __ImageBase
0x180004713  shr     rax, 3
0x180004717  movzx   r8d, byte ptr [rax+rcx+74E8h]
0x180004720  test    r8b, r8b
0x180004723  jz      short loc_180004799
0x180004725  mov     [r9+4], r8b
0x180004729  movzx   ecx, ds:rva byte_1800076E1[rcx+r8*2]
0x180004732  not     ecx
0x180004734  movzx   eax, dl
0x180004737  and     ecx, eax
0x180004739  dec     r8b
0x18000473c  mov     [r9], ecx
0x18000473f  mov     [r9+5], r8b
0x180004743  mov     eax, 3E5h
0x180004748  retn
0x180004749  movzx   eax, dl
0x18000474c  and     al, 0C0h
0x18000474e  cmp     al, 80h
0x180004750  jnz     short loc_180004799
0x180004752  mov     eax, [r9]
0x180004755  and     edx, 3Fh
0x180004758  shl     eax, 6
0x18000475b  or      edx, eax
0x18000475d  sub     cl, 1
0x180004760  mov     [r9], edx
0x180004763  mov     [r9+5], cl
0x180004767  jnz     short loc_180004743
0x180004769  movzx   eax, byte ptr [r9+4]
0x18000476e  lea     rcx, __ImageBase
0x180004775  cmp     edx, ds:rva dword_1800076F0[rcx+rax*4]
0x18000477c  jb      short loc_180004799
0x18000477e  cmp     edx, 0D7FFh
0x180004784  jbe     short loc_180004793
0x180004786  lea     eax, [rdx-0E000h]
0x18000478c  cmp     eax, 101FFFh
0x180004791  ja      short loc_180004799
0x180004793  mov     [r8], edx
0x180004796  xor     eax, eax
0x180004798  retn
0x180004799  mov     eax, 246h
0x18000479e  retn
```
