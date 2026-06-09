# CVideoObject::computePars(void)

- ea: `0x1800195c8`
- end: `0x180019788`
- name: `?computePars@CVideoObject@@IEAAXXZ`
- size: `448`
- prototype: `void __fastcall(CVideoObject *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180018f04`

## callees

- `0x1800195c8`

## pseudocode

```c
void __fastcall CVideoObject::computePars(CVideoObject *this)
{
  int v2; // r9d
  unsigned int v3; // r11d
  int v4; // r10d
  int v5; // ebx
  bool v6; // zf
  int v7; // esi
  int v8; // ecx
  int v9; // ebp
  int v10; // eax
  int v11; // eax
  BOOL v12; // eax

  v2 = *((_DWORD *)this + 5) - *((_DWORD *)this + 3);
  *((_DWORD *)this + 321) = v2;
  v3 = ((v2 >> 1) + 15) & 0xFFFFFFF0;
  *((_DWORD *)this + 324) = v3;
  v4 = *((_DWORD *)this + 6) - *((_DWORD *)this + 4);
  *((_DWORD *)this + 323) = v4;
  v5 = v4 >> 1;
  v6 = *((_DWORD *)this + 2) == 0;
  *((_DWORD *)this + 326) = v4 >> 1;
  if ( v6 )
  {
    v7 = *((_DWORD *)this + 315);
    v8 = *((_DWORD *)this + 314);
    v9 = *((_DWORD *)this + 315) / 2;
    v10 = v8;
  }
  else
  {
    v7 = v4;
    v8 = v2;
    v9 = v4 / 2;
    v10 = v2;
  }
  *((_DWORD *)this + 316) = v8;
  v11 = v10 / 2;
  *((_DWORD *)this + 317) = v11;
  *((_DWORD *)this + 318) = v7;
  *((_DWORD *)this + 319) = v9;
  *((_DWORD *)this + 322) = v8 + 32;
  *((_DWORD *)this + 325) = v11 + 16;
  *((_DWORD *)this + 327) = v4 * v2;
  v12 = v2 == *((_DWORD *)this + 314) && v4 == *((_DWORD *)this + 315);
  *((_DWORD *)this + 320) = v12;
  *((_DWORD *)this + 223) = v4 >> 4;
  *((_DWORD *)this + 222) = v2 >> 4;
  *((_DWORD *)this + 335) = v4;
  *((_DWORD *)this + 336) = v5;
  *((_DWORD *)this + 337) = -64;
  *((_DWORD *)this + 224) = (v2 >> 4) * (v4 >> 4);
  *((_DWORD *)this + 225) = (v2 >> 4) - 1;
  *((_DWORD *)this + 333) = v2 + 64;
  *((_DWORD *)this + 334) = v3 + 32;
  *((_DWORD *)this + 338) = 2 * v2 + 32;
  *((_DWORD *)this + 340) = 2 * v4 + 24;
  *((_DWORD *)this + 342) = 2 * v3 + 16;
  *((_DWORD *)this + 344) = 2 * v5 + 8;
  *((_DWORD *)this + 345) = 32 * (v2 + 65);
  *((_DWORD *)this + 346) = 16 * (v3 + 33);
  *((_DWORD *)this + 339) = -56;
  *((_DWORD *)this + 341) = -32;
  *((_DWORD *)this + 343) = -24;
  *((_DWORD *)this + 331) = v2 >> 4;
}

```

## disassembly

```asm
0x1800195c8  push    rbx
0x1800195ca  push    rbp
0x1800195cb  push    rsi
0x1800195cc  push    rdi
0x1800195cd  mov     r9d, [rcx+14h]
0x1800195d1  mov     r8, rcx
0x1800195d4  sub     r9d, [rcx+0Ch]
0x1800195d8  mov     edi, 2
0x1800195dd  mov     [rcx+504h], r9d
0x1800195e4  mov     r11d, r9d
0x1800195e7  sar     r11d, 1
0x1800195ea  add     r11d, 0Fh
0x1800195ee  and     r11d, 0FFFFFFF0h
0x1800195f2  mov     [rcx+510h], r11d
0x1800195f9  mov     r10d, [rcx+18h]
0x1800195fd  sub     r10d, [rcx+10h]
0x180019601  mov     ebx, r10d
0x180019604  mov     [rcx+50Ch], r10d
0x18001960b  sar     ebx, 1
0x18001960d  cmp     dword ptr [rcx+8], 0
0x180019611  mov     [rcx+518h], ebx
0x180019617  jz      short loc_18001962C
0x180019619  mov     eax, r10d
0x18001961c  mov     esi, r10d
0x18001961f  cdq
0x180019620  mov     ecx, r9d
0x180019623  idiv    edi
0x180019625  mov     ebp, eax
0x180019627  mov     eax, r9d
0x18001962a  jmp     short loc_180019642
0x18001962c  mov     esi, [r8+4ECh]
0x180019633  mov     eax, esi
0x180019635  mov     ecx, [rcx+4E8h]
0x18001963b  cdq
0x18001963c  idiv    edi
0x18001963e  mov     ebp, eax
0x180019640  mov     eax, ecx
0x180019642  mov     [r8+4F0h], ecx
0x180019649  cdq
0x18001964a  idiv    edi
0x18001964c  mov     [r8+4F4h], eax
0x180019653  mov     edx, eax
0x180019655  mov     [r8+4F8h], esi
0x18001965c  lea     eax, [rcx+20h]
0x18001965f  mov     [r8+4FCh], ebp
0x180019666  mov     [r8+508h], eax
0x18001966d  lea     eax, [rdx+10h]
0x180019670  mov     [r8+514h], eax
0x180019677  mov     eax, r9d
0x18001967a  imul    eax, r10d
0x18001967e  mov     [r8+51Ch], eax
0x180019685  cmp     r9d, [r8+4E8h]
0x18001968c  jnz     short loc_18001969E
0x18001968e  cmp     r10d, [r8+4ECh]
0x180019695  jnz     short loc_18001969E
0x180019697  mov     eax, 1
0x18001969c  jmp     short loc_1800196A0
0x18001969e  xor     eax, eax
0x1800196a0  mov     [r8+500h], eax
0x1800196a7  mov     ecx, r9d
0x1800196aa  sar     ecx, 4
0x1800196ad  mov     eax, r10d
0x1800196b0  sar     eax, 4
0x1800196b3  mov     [r8+37Ch], eax
0x1800196ba  imul    eax, ecx
0x1800196bd  mov     [r8+378h], ecx
0x1800196c4  mov     [r8+53Ch], r10d
0x1800196cb  mov     [r8+540h], ebx
0x1800196d2  mov     dword ptr [r8+544h], 0FFFFFFC0h
0x1800196dd  mov     [r8+380h], eax
0x1800196e4  lea     eax, [rcx-1]
0x1800196e7  mov     [r8+384h], eax
0x1800196ee  lea     eax, [r9+40h]
0x1800196f2  mov     [r8+534h], eax
0x1800196f9  lea     eax, [r11+20h]
0x1800196fd  mov     [r8+538h], eax
0x180019704  lea     eax, ds:20h[r9*2]
0x18001970c  mov     [r8+548h], eax
0x180019713  lea     eax, ds:18h[r10*2]
0x18001971b  mov     [r8+550h], eax
0x180019722  lea     eax, ds:10h[r11*2]
0x18001972a  mov     [r8+558h], eax
0x180019731  lea     eax, ds:8[rbx*2]
0x180019738  mov     [r8+560h], eax
0x18001973f  lea     eax, [r9+41h]
0x180019743  shl     eax, 5
0x180019746  mov     [r8+564h], eax
0x18001974d  lea     eax, [r11+21h]
0x180019751  shl     eax, 4
0x180019754  mov     [r8+568h], eax
0x18001975b  mov     dword ptr [r8+54Ch], 0FFFFFFC8h
0x180019766  mov     dword ptr [r8+554h], 0FFFFFFE0h
0x180019771  mov     dword ptr [r8+55Ch], 0FFFFFFE8h
0x18001977c  mov     [r8+52Ch], ecx
0x180019783  pop     rdi
0x180019784  pop     rsi
0x180019785  pop     rbp
0x180019786  pop     rbx
0x180019787  retn
```
