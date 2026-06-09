# CInputBitStream::getBit(void)

- ea: `0x18000dca0`
- end: `0x18000dd45`
- name: `?getBit@CInputBitStream@@QEAAKXZ`
- size: `165`
- prototype: `__int64 __fastcall(CInputBitStream *this)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c330`
- `0x18000c5b0`
- `0x18000c9c0`
- `0x18000cd98`
- `0x18000cf1c`
- `0x18000d300`
- `0x18000db00`
- `0x18000db8c`
- `0x18000df50`
- `0x18000e040`
- `0x18000e180`
- `0x18000e350`
- `0x18000e4d0`
- `0x18000e5e0`
- `0x18000e760`

## callees

- `0x18000dca0`
- `0x18001e798`

## pseudocode

```c
__int64 __fastcall CInputBitStream::getBit(CInputBitStream *this)
{
  int v2; // r11d
  int *v3; // r10
  int v4; // ecx
  __int64 result; // rax
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
0x18000dca0  cmp     dword ptr [rcx+14h], 0
0x18000dca4  mov     r9, rcx
0x18000dca7  jnz     loc_18000DD3B
0x18000dcad  mov     r11d, [rcx+8]
0x18000dcb1  lea     r10, [rcx+10h]
0x18000dcb5  test    r11d, r11d
0x18000dcb8  jnz     short loc_18000DCBF
0x18000dcba  cmp     [r10], r11d
0x18000dcbd  jz      short loc_18000DD3B
0x18000dcbf  mov     ecx, [r10]
0x18000dcc2  cmp     ecx, 1
0x18000dcc5  jb      short loc_18000DCD7
0x18000dcc7  mov     eax, [r9+0Ch]
0x18000dccb  dec     ecx
0x18000dccd  shr     eax, cl
0x18000dccf  and     eax, 1
0x18000dcd2  mov     [r10], ecx
0x18000dcd5  jmp     short locret_18000DD44
0x18000dcd7  cmp     r11d, 4
0x18000dcdb  jl      short loc_18000DD2D
0x18000dcdd  mov     r8, [r9]
0x18000dce0  movzx   eax, byte ptr [r8+3]
0x18000dce5  mov     [r9+0Ch], eax
0x18000dce9  movzx   ecx, byte ptr [r8+2]
0x18000dcee  shl     ecx, 8
0x18000dcf1  or      ecx, eax
0x18000dcf3  mov     [r9+0Ch], ecx
0x18000dcf7  movzx   edx, byte ptr [r8+1]
0x18000dcfc  shl     edx, 10h
0x18000dcff  or      edx, ecx
0x18000dd01  lea     rcx, [r8+4]
0x18000dd05  mov     [r9+0Ch], edx
0x18000dd09  movzx   eax, byte ptr [r8]
0x18000dd0d  shl     eax, 18h
0x18000dd10  or      eax, edx
0x18000dd12  mov     [r9], rcx
0x18000dd15  lea     ecx, [r11-4]
0x18000dd19  mov     [r9+0Ch], eax
0x18000dd1d  shr     eax, 1Fh
0x18000dd20  mov     [r9+8], ecx
0x18000dd24  mov     dword ptr [r10], 1Fh
0x18000dd2b  jmp     short locret_18000DD44
0x18000dd2d  xor     edx, edx; unsigned int
0x18000dd2f  mov     rcx, r9; this
0x18000dd32  lea     r8d, [rdx+1]; unsigned int
0x18000dd36  jmp     ?finalLoad@CInputBitStream@@AEAAKKK@Z; CInputBitStream::finalLoad(ulong,ulong)
0x18000dd3b  mov     dword ptr [rcx+14h], 1
0x18000dd42  xor     eax, eax
0x18000dd44  retn
```
