# CDKreadBits

- ea: `0x1800110c0`
- end: `0x180011123`
- name: `CDKreadBits`
- size: `99`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `102`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a1a0`
- `0x1800103a0`
- `0x180010838`
- `0x1800113bc`
- `0x180011da8`
- `0x1800122cc`
- `0x1800125f4`
- `0x18001262c`
- `0x180012768`
- `0x1800127d8`
- `0x180012d90`
- `0x1800131b4`
- `0x1800133e8`
- `0x180014280`
- `0x180014ae0`
- `0x1800176d0`
- `0x180017e54`
- `0x180018c84`
- `0x180018e64`
- `0x1800190c4`
- `0x180019168`
- `0x1800195c0`
- `0x180019b98`
- `0x180019d84`
- `0x180019ec4`
- `0x18001a9d0`
- `0x18001aeac`
- `0x18002b66c`
- `0x18002bb4c`
- `0x18003b360`
- `0x18003c1f0`
- `0x180044774`
- `0x1800471fc`
- `0x18004afa0`
- `0x18004b134`
- `0x18004b3f8`
- `0x180072810`
- `0x180073f98`
- `0x1800755fc`
- `0x180075680`
- `0x180075728`
- `0x180075a24`
- `0x180075a78`
- `0x180075ba4`
- `0x180075c30`
- `0x180075cac`
- `0x180075de0`
- `0x180075e7c`
- `0x180075fec`
- `0x1800760e4`

## callees

- `0x1800110c0`
- `0x1800175b0`

## pseudocode

```c
__int64 __fastcall CDKreadBits(_DWORD *a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rsi
  int v5; // ecx
  int v6; // eax
  int v7; // edi
  int v8; // eax
  int v9; // ecx
  int v10; // eax

  v4 = (unsigned int)a2;
  v5 = a1[1];
  v6 = a2 - v5;
  v7 = 0;
  if ( (int)a2 - v5 > 0 )
  {
    if ( v6 != 32 )
      v7 = *a1 << v6;
    v8 = CDK_get32(a1 + 2, a2, a3);
    v5 = a1[1] + 32;
    *a1 = v8;
  }
  v9 = v5 - v4;
  v10 = v7 | (*a1 >> v9);
  a1[1] = v9;
  return BitMask[v4] & (unsigned int)v10;
}

```

## disassembly

```asm
0x1800110c0  mov     [rsp+arg_0], rbx
0x1800110c5  mov     [rsp+arg_8], rsi
0x1800110ca  push    rdi
0x1800110cb  sub     rsp, 20h
0x1800110cf  mov     rbx, rcx
0x1800110d2  mov     esi, edx
0x1800110d4  mov     ecx, [rcx+4]
0x1800110d7  mov     eax, edx
0x1800110d9  sub     eax, ecx
0x1800110db  xor     edi, edi
0x1800110dd  test    eax, eax
0x1800110df  jle     short loc_1800110FD
0x1800110e1  cmp     eax, 20h ; ' '
0x1800110e4  jz      short loc_1800110EC
0x1800110e6  mov     edi, [rbx]
0x1800110e8  mov     ecx, eax
0x1800110ea  shl     edi, cl
0x1800110ec  lea     rcx, [rbx+8]
0x1800110f0  call    CDK_get32
0x1800110f5  mov     ecx, [rbx+4]
0x1800110f8  add     ecx, 20h ; ' '
0x1800110fb  mov     [rbx], eax
0x1800110fd  mov     eax, [rbx]
0x1800110ff  lea     rdx, BitMask
0x180011106  sub     ecx, esi
0x180011108  shr     eax, cl
0x18001110a  or      eax, edi
0x18001110c  mov     [rbx+4], ecx
0x18001110f  and     eax, [rdx+rsi*4]
0x180011112  mov     rsi, [rsp+28h+arg_8]
0x180011117  mov     rbx, [rsp+28h+arg_0]
0x18001111c  add     rsp, 20h
0x180011120  pop     rdi
0x180011121  retn
```
