# CInputBitStream::getBit(void)

- ea: `0x18000dbe0`
- end: `0x18000dc85`
- name: `?getBit@CInputBitStream@@QEAAKXZ`
- size: `165`
- prototype: `unsigned int __fastcall(CInputBitStream *__hidden this)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c270`
- `0x18000c4f0`
- `0x18000c900`
- `0x18000ccd8`
- `0x18000ce5c`
- `0x18000d240`
- `0x18000da40`
- `0x18000dacc`
- `0x18000de90`
- `0x18000df80`
- `0x18000e0c0`
- `0x18000e290`
- `0x18000e410`
- `0x18000e520`
- `0x18000e6a0`

## callees

- `0x18000dbe0`
- `0x18001e6d8`

## pseudocode

```c
int __fastcall CInputBitStream::getBit(CInputBitStream *this)
{
  int v2; // r11d
  int *v3; // r10
  int v4; // ecx
  int result; // eax
  unsigned __int8 *v6; // r8
  int v7; // eax
  int v8; // ecx
  int v9; // edx
  unsigned int v10; // eax

  if ( !*((_DWORD *)this + 5) && ((v2 = *((_DWORD *)this + 2), v3 = (int *)((char *)this + 16), v2) || *v3) )
  {
    if ( *v3 )
    {
      v4 = *v3 - 1;
      result = (*((_DWORD *)this + 3) >> v4) & 1;
      *v3 = v4;
    }
    else if ( v2 < 4 )
    {
      return CInputBitStream::finalLoad(this, 0, 1u);
    }
    else
    {
      v6 = *(unsigned __int8 **)this;
      v7 = *(unsigned __int8 *)(*(_QWORD *)this + 3LL);
      *((_DWORD *)this + 3) = v7;
      v8 = v7 | (v6[2] << 8);
      *((_DWORD *)this + 3) = v8;
      v9 = v8 | (v6[1] << 16);
      *((_DWORD *)this + 3) = v9;
      v10 = v9 | (*v6 << 24);
      *(_QWORD *)this = v6 + 4;
      *((_DWORD *)this + 3) = v10;
      result = v10 >> 31;
      *((_DWORD *)this + 2) = v2 - 4;
      *v3 = 31;
    }
  }
  else
  {
    *((_DWORD *)this + 5) = 1;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000dbe0  cmp     dword ptr [rcx+14h], 0
0x18000dbe4  mov     r9, rcx
0x18000dbe7  jnz     loc_18000DC7B
0x18000dbed  mov     r11d, [rcx+8]
0x18000dbf1  lea     r10, [rcx+10h]
0x18000dbf5  test    r11d, r11d
0x18000dbf8  jnz     short loc_18000DBFF
0x18000dbfa  cmp     [r10], r11d
0x18000dbfd  jz      short loc_18000DC7B
0x18000dbff  mov     ecx, [r10]
0x18000dc02  cmp     ecx, 1
0x18000dc05  jb      short loc_18000DC17
0x18000dc07  mov     eax, [r9+0Ch]
0x18000dc0b  dec     ecx
0x18000dc0d  shr     eax, cl
0x18000dc0f  and     eax, 1
0x18000dc12  mov     [r10], ecx
0x18000dc15  jmp     short locret_18000DC84
0x18000dc17  cmp     r11d, 4
0x18000dc1b  jl      short loc_18000DC6D
0x18000dc1d  mov     r8, [r9]
0x18000dc20  movzx   eax, byte ptr [r8+3]
0x18000dc25  mov     [r9+0Ch], eax
0x18000dc29  movzx   ecx, byte ptr [r8+2]
0x18000dc2e  shl     ecx, 8
0x18000dc31  or      ecx, eax
0x18000dc33  mov     [r9+0Ch], ecx
0x18000dc37  movzx   edx, byte ptr [r8+1]
0x18000dc3c  shl     edx, 10h
0x18000dc3f  or      edx, ecx
0x18000dc41  lea     rcx, [r8+4]
0x18000dc45  mov     [r9+0Ch], edx
0x18000dc49  movzx   eax, byte ptr [r8]
0x18000dc4d  shl     eax, 18h
0x18000dc50  or      eax, edx
0x18000dc52  mov     [r9], rcx
0x18000dc55  lea     ecx, [r11-4]
0x18000dc59  mov     [r9+0Ch], eax
0x18000dc5d  shr     eax, 1Fh
0x18000dc60  mov     [r9+8], ecx
0x18000dc64  mov     dword ptr [r10], 1Fh
0x18000dc6b  jmp     short locret_18000DC84
0x18000dc6d  xor     edx, edx; unsigned int
0x18000dc6f  mov     rcx, r9; this
0x18000dc72  lea     r8d, [rdx+1]; unsigned int
0x18000dc76  jmp     ?finalLoad@CInputBitStream@@AEAAKKK@Z; CInputBitStream::finalLoad(ulong,ulong)
0x18000dc7b  mov     dword ptr [rcx+14h], 1
0x18000dc82  xor     eax, eax
0x18000dc84  retn
```
