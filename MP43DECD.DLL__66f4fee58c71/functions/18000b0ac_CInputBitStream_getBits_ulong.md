# CInputBitStream::getBits(ulong)

- ea: `0x18000b0ac`
- end: `0x18000b18f`
- name: `?getBits@CInputBitStream@@QEAAKK@Z`
- size: `227`
- prototype: `unsigned int __fastcall(CInputBitStream *__hidden this, unsigned int)`
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x180009e34`
- `0x18000aa50`
- `0x18000ad38`
- `0x18000c270`
- `0x18000c4f0`
- `0x18000c900`
- `0x18000ccd8`
- `0x18000ce5c`
- `0x18000d240`
- `0x18000d9a0`
- `0x18000da40`
- `0x18000dacc`
- `0x18000e7b0`
- `0x18000e910`
- `0x180012938`
- `0x180012b44`

## callees

- `0x18000b0ac`
- `0x18001e6d8`

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
0x18000b0ac  mov     [rsp+arg_0], rbx
0x18000b0b1  push    rdi
0x18000b0b2  sub     rsp, 20h
0x18000b0b6  cmp     dword ptr [rcx+14h], 0
0x18000b0ba  mov     r10, rcx
0x18000b0bd  mov     r9d, edx
0x18000b0c0  jnz     loc_18000B17A
0x18000b0c6  mov     edi, [rcx+8]
0x18000b0c9  lea     rbx, [r10+10h]
0x18000b0cd  lea     ecx, ds:0[rdi*8]
0x18000b0d4  cmp     ecx, r9d
0x18000b0d7  jnb     short loc_18000B0E4
0x18000b0d9  add     ecx, [rbx]
0x18000b0db  cmp     ecx, r9d
0x18000b0de  jb      loc_18000B17A
0x18000b0e4  mov     ecx, [rbx]
0x18000b0e6  lea     rdx, ?getMask@@3PAKA; ulong near * getMask
0x18000b0ed  mov     r11d, [r10+0Ch]
0x18000b0f1  cmp     r9d, ecx
0x18000b0f4  ja      short loc_18000B107
0x18000b0f6  mov     eax, [rdx+r9*4]
0x18000b0fa  sub     ecx, r9d
0x18000b0fd  shr     r11d, cl
0x18000b100  and     eax, r11d
0x18000b103  mov     [rbx], ecx
0x18000b105  jmp     short loc_18000B184
0x18000b107  and     r11d, [rdx+rcx*4]
0x18000b10b  sub     r9d, ecx
0x18000b10e  cmp     edi, 4
0x18000b111  jl      short loc_18000B16A
0x18000b113  mov     rcx, [r10]
0x18000b116  mov     edx, 20h ; ' '
0x18000b11b  sub     edx, r9d
0x18000b11e  movzx   eax, byte ptr [rcx+1]
0x18000b122  movzx   r8d, byte ptr [rcx]
0x18000b126  shl     r8d, 8
0x18000b12a  or      r8d, eax
0x18000b12d  movzx   eax, byte ptr [rcx+2]
0x18000b131  shl     r8d, 8
0x18000b135  or      r8d, eax
0x18000b138  movzx   eax, byte ptr [rcx+3]
0x18000b13c  shl     r8d, 8
0x18000b140  or      r8d, eax
0x18000b143  mov     [rbx], edx
0x18000b145  lea     rax, [rcx+4]
0x18000b149  mov     [r10+0Ch], r8d
0x18000b14d  lea     ecx, [rdi-4]
0x18000b150  mov     [r10], rax
0x18000b153  mov     [r10+8], ecx
0x18000b157  mov     ecx, r9d
0x18000b15a  shl     r11d, cl
0x18000b15d  mov     ecx, edx
0x18000b15f  shr     r8d, cl
0x18000b162  or      r11d, r8d
0x18000b165  mov     eax, r11d
0x18000b168  jmp     short loc_18000B184
0x18000b16a  mov     r8d, r9d; unsigned int
0x18000b16d  mov     edx, r11d; unsigned int
0x18000b170  mov     rcx, r10; this
0x18000b173  call    ?finalLoad@CInputBitStream@@AEAAKKK@Z; CInputBitStream::finalLoad(ulong,ulong)
0x18000b178  jmp     short loc_18000B184
0x18000b17a  mov     dword ptr [r10+14h], 1
0x18000b182  xor     eax, eax
0x18000b184  mov     rbx, [rsp+28h+arg_0]
0x18000b189  add     rsp, 20h
0x18000b18d  pop     rdi
0x18000b18e  retn
```
