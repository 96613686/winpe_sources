# CInputBitStream::getBits(ulong)

- ea: `0x18000b16c`
- end: `0x18000b24f`
- name: `?getBits@CInputBitStream@@QEAAKK@Z`
- size: `227`
- prototype: `unsigned int __fastcall(CInputBitStream *__hidden this, unsigned int)`
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x180009ef4`
- `0x18000ab10`
- `0x18000adf8`
- `0x18000c330`
- `0x18000c5b0`
- `0x18000c9c0`
- `0x18000cd98`
- `0x18000cf1c`
- `0x18000d300`
- `0x18000da60`
- `0x18000db00`
- `0x18000db8c`
- `0x18000e870`
- `0x18000e9d0`
- `0x1800129f8`
- `0x180012c04`

## callees

- `0x18000b16c`
- `0x18001e798`

## pseudocode

```c
unsigned int __fastcall CInputBitStream::getBits(CInputBitStream *this, unsigned int a2)
{
  int v3; // edi
  _DWORD *v4; // rbx
  __int64 v5; // rcx
  unsigned int v6; // r11d
  int v7; // ecx
  unsigned int result; // eax
  unsigned int v9; // r11d
  unsigned int v10; // r9d
  unsigned __int8 *v11; // rcx
  unsigned int v12; // r8d

  if ( *((_DWORD *)this + 5)
    || (v3 = *((_DWORD *)this + 2), v4 = (_DWORD *)((char *)this + 16), 8 * v3 < a2) && *v4 + 8 * v3 < a2 )
  {
    *((_DWORD *)this + 5) = 1;
    return 0;
  }
  else
  {
    v5 = (unsigned int)*v4;
    v6 = *((_DWORD *)this + 3);
    if ( a2 > (unsigned int)v5 )
    {
      v9 = *((_DWORD *)&getMask + v5) & v6;
      v10 = a2 - v5;
      if ( v3 < 4 )
      {
        return CInputBitStream::finalLoad(this, v9, v10);
      }
      else
      {
        v11 = *(unsigned __int8 **)this;
        v12 = *(unsigned __int8 *)(*(_QWORD *)this + 3LL)
            | ((*(unsigned __int8 *)(*(_QWORD *)this + 2LL)
              | ((*(unsigned __int8 *)(*(_QWORD *)this + 1LL) | (**(unsigned __int8 **)this << 8)) << 8)) << 8);
        *v4 = 32 - v10;
        *((_DWORD *)this + 3) = v12;
        *(_QWORD *)this = v11 + 4;
        *((_DWORD *)this + 2) = v3 - 4;
        return (v12 >> (32 - v10)) | (v9 << v10);
      }
    }
    else
    {
      v7 = v5 - a2;
      result = (v6 >> v7) & *((_DWORD *)&getMask + a2);
      *v4 = v7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000b16c  mov     [rsp+arg_0], rbx
0x18000b171  push    rdi
0x18000b172  sub     rsp, 20h
0x18000b176  cmp     dword ptr [rcx+14h], 0
0x18000b17a  mov     r10, rcx
0x18000b17d  mov     r9d, edx
0x18000b180  jnz     loc_18000B23A
0x18000b186  mov     edi, [rcx+8]
0x18000b189  lea     rbx, [r10+10h]
0x18000b18d  lea     ecx, ds:0[rdi*8]
0x18000b194  cmp     ecx, r9d
0x18000b197  jnb     short loc_18000B1A4
0x18000b199  add     ecx, [rbx]
0x18000b19b  cmp     ecx, r9d
0x18000b19e  jb      loc_18000B23A
0x18000b1a4  mov     ecx, [rbx]
0x18000b1a6  lea     rdx, ?getMask@@3PAKA; ulong near * getMask
0x18000b1ad  mov     r11d, [r10+0Ch]
0x18000b1b1  cmp     r9d, ecx
0x18000b1b4  ja      short loc_18000B1C7
0x18000b1b6  mov     eax, [rdx+r9*4]
0x18000b1ba  sub     ecx, r9d
0x18000b1bd  shr     r11d, cl
0x18000b1c0  and     eax, r11d
0x18000b1c3  mov     [rbx], ecx
0x18000b1c5  jmp     short loc_18000B244
0x18000b1c7  and     r11d, [rdx+rcx*4]
0x18000b1cb  sub     r9d, ecx
0x18000b1ce  cmp     edi, 4
0x18000b1d1  jl      short loc_18000B22A
0x18000b1d3  mov     rcx, [r10]
0x18000b1d6  mov     edx, 20h ; ' '
0x18000b1db  sub     edx, r9d
0x18000b1de  movzx   eax, byte ptr [rcx+1]
0x18000b1e2  movzx   r8d, byte ptr [rcx]
0x18000b1e6  shl     r8d, 8
0x18000b1ea  or      r8d, eax
0x18000b1ed  movzx   eax, byte ptr [rcx+2]
0x18000b1f1  shl     r8d, 8
0x18000b1f5  or      r8d, eax
0x18000b1f8  movzx   eax, byte ptr [rcx+3]
0x18000b1fc  shl     r8d, 8
0x18000b200  or      r8d, eax
0x18000b203  mov     [rbx], edx
0x18000b205  lea     rax, [rcx+4]
0x18000b209  mov     [r10+0Ch], r8d
0x18000b20d  lea     ecx, [rdi-4]
0x18000b210  mov     [r10], rax
0x18000b213  mov     [r10+8], ecx
0x18000b217  mov     ecx, r9d
0x18000b21a  shl     r11d, cl
0x18000b21d  mov     ecx, edx
0x18000b21f  shr     r8d, cl
0x18000b222  or      r11d, r8d
0x18000b225  mov     eax, r11d
0x18000b228  jmp     short loc_18000B244
0x18000b22a  mov     r8d, r9d; unsigned int
0x18000b22d  mov     edx, r11d; unsigned int
0x18000b230  mov     rcx, r10; this
0x18000b233  call    ?finalLoad@CInputBitStream@@AEAAKKK@Z; CInputBitStream::finalLoad(ulong,ulong)
0x18000b238  jmp     short loc_18000B244
0x18000b23a  mov     dword ptr [r10+14h], 1
0x18000b242  xor     eax, eax
0x18000b244  mov     rbx, [rsp+28h+arg_0]
0x18000b249  add     rsp, 20h
0x18000b24d  pop     rdi
0x18000b24e  retn
```
