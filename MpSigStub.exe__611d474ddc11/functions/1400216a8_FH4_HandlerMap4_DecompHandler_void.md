# FH4::HandlerMap4::DecompHandler(void)

- ea: `0x1400216a8`
- end: `0x14002183c`
- name: `?DecompHandler@HandlerMap4@FH4@@AEAAXXZ`
- size: `404`
- prototype: `void __fastcall(FH4::HandlerMap4 *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001fea4`
- `0x1400205bc`
- `0x140021060`

## callees

- `0x1400216a8`

## pseudocode

```c
void __fastcall FH4::HandlerMap4::DecompHandler(FH4::HandlerMap4 *this)
{
  char *v2; // rax
  char v3; // r9
  _BYTE *v4; // rdx
  __int64 v5; // rcx
  int v6; // eax
  __int64 v7; // rcx
  int *v8; // r10
  char v9; // al
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  char *v14; // r10
  __int64 v15; // rax
  int v16; // edx
  __int64 v17; // rcx
  _BYTE *v18; // r10
  int v19; // eax
  __int64 v20; // rcx
  _BYTE *v21; // r10
  int v22; // eax

  *((_BYTE *)this + 24) = 0;
  *(_QWORD *)((char *)this + 28) = 0;
  *(_QWORD *)((char *)this + 36) = 0;
  *((_OWORD *)this + 3) = 0;
  v2 = (char *)*((_QWORD *)this + 1);
  v3 = *v2;
  v4 = v2 + 1;
  *((_BYTE *)this + 24) = *v2;
  *((_QWORD *)this + 1) = v2 + 1;
  if ( (v3 & 1) != 0 )
  {
    v5 = *v4 & 0xF;
    v4 -= *((char *)qword_1400BBEB0 + v5);
    *((_DWORD *)this + 7) = *((_DWORD *)v4 - 1) >> *((_BYTE *)&qword_1400BBEB0[2] + v5);
    *((_QWORD *)this + 1) = v4;
  }
  if ( (v3 & 2) != 0 )
  {
    v6 = *(_DWORD *)v4;
    v4 += 4;
    *((_QWORD *)this + 1) = v4;
    *((_DWORD *)this + 8) = v6;
  }
  if ( (v3 & 4) != 0 )
  {
    v7 = *v4 & 0xF;
    v4 -= *((char *)qword_1400BBEB0 + v7);
    *((_DWORD *)this + 9) = *((_DWORD *)v4 - 1) >> *((_BYTE *)&qword_1400BBEB0[2] + v7);
    *((_QWORD *)this + 1) = v4;
  }
  v8 = (int *)(v4 + 4);
  *((_DWORD *)this + 10) = *(_DWORD *)v4;
  *((_QWORD *)this + 1) = v4 + 4;
  v9 = v3 & 0x30;
  if ( (v3 & 8) != 0 )
  {
    if ( v9 == 16 )
    {
      v10 = *v8;
      *((_QWORD *)this + 1) = v4 + 8;
      *((_QWORD *)this + 6) = v10;
      return;
    }
    if ( (v3 & 0x30) == 0x20 )
    {
      v11 = *v8;
      *((_QWORD *)this + 1) = v4 + 8;
      *((_QWORD *)this + 6) = v11;
      v12 = *((int *)v4 + 2);
      *((_QWORD *)this + 1) = v4 + 12;
LABEL_16:
      *((_QWORD *)this + 7) = v12;
    }
  }
  else
  {
    if ( v9 == 16 )
    {
      v13 = *(_BYTE *)v8 & 0xF;
      v14 = (char *)v8 - *((char *)qword_1400BBEB0 + v13);
      v15 = (unsigned int)((*((_DWORD *)v14 - 1) >> *((_BYTE *)&qword_1400BBEB0[2] + v13)) + *((_DWORD *)this + 18));
      *((_QWORD *)this + 1) = v14;
      *((_QWORD *)this + 6) = v15;
      return;
    }
    if ( (v3 & 0x30) == 0x20 )
    {
      v16 = *((_DWORD *)this + 18);
      v17 = *(_BYTE *)v8 & 0xF;
      v18 = (char *)v8 - *((char *)qword_1400BBEB0 + v17);
      v19 = *((_DWORD *)v18 - 1) >> *((_BYTE *)&qword_1400BBEB0[2] + v17);
      *((_QWORD *)this + 1) = v18;
      *((_QWORD *)this + 6) = (unsigned int)(v16 + v19);
      v20 = *v18 & 0xF;
      v21 = &v18[-*((char *)qword_1400BBEB0 + v20)];
      v22 = *((_DWORD *)v21 - 1) >> *((_BYTE *)&qword_1400BBEB0[2] + v20);
      *((_QWORD *)this + 1) = v21;
      v12 = (unsigned int)(v16 + v22);
      goto LABEL_16;
    }
  }
}

```

## disassembly

```asm
0x1400216a8  xor     eax, eax
0x1400216aa  lea     r11, cs:140000000h
0x1400216b1  mov     [rcx+18h], al
0x1400216b4  xorps   xmm0, xmm0
0x1400216b7  mov     [rcx+1Ch], rax
0x1400216bb  mov     r8, rcx
0x1400216be  mov     [rcx+24h], rax
0x1400216c2  movups  xmmword ptr [rcx+30h], xmm0
0x1400216c6  mov     rax, [rcx+8]
0x1400216ca  mov     r9b, [rax]
0x1400216cd  lea     rdx, [rax+1]
0x1400216d1  mov     [rcx+18h], r9b
0x1400216d5  mov     [rcx+8], rdx
0x1400216d9  test    r9b, 1
0x1400216dd  jz      short loc_140021706
0x1400216df  movzx   ecx, byte ptr [rdx]
0x1400216e2  and     ecx, 0Fh
0x1400216e5  movsx   rax, byte ptr [rcx+r11+0BBEB0h]
0x1400216ee  mov     cl, [rcx+r11+0BBEC0h]
0x1400216f6  sub     rdx, rax
0x1400216f9  mov     eax, [rdx-4]
0x1400216fc  shr     eax, cl
0x1400216fe  mov     [r8+1Ch], eax
0x140021702  mov     [r8+8], rdx
0x140021706  test    r9b, 2
0x14002170a  jz      short loc_14002171A
0x14002170c  mov     eax, [rdx]
0x14002170e  add     rdx, 4
0x140021712  mov     [r8+8], rdx
0x140021716  mov     [r8+20h], eax
0x14002171a  test    r9b, 4
0x14002171e  jz      short loc_140021747
0x140021720  movzx   ecx, byte ptr [rdx]
0x140021723  and     ecx, 0Fh
0x140021726  movsx   rax, byte ptr [rcx+r11+0BBEB0h]
0x14002172f  mov     cl, [rcx+r11+0BBEC0h]
0x140021737  sub     rdx, rax
0x14002173a  mov     eax, [rdx-4]
0x14002173d  shr     eax, cl
0x14002173f  mov     [r8+24h], eax
0x140021743  mov     [r8+8], rdx
0x140021747  mov     eax, [rdx]
0x140021749  lea     r10, [rdx+4]
0x14002174d  mov     [r8+28h], eax
0x140021751  mov     cl, 30h ; '0'
0x140021753  mov     al, r9b
0x140021756  mov     [r8+8], r10
0x14002175a  and     al, cl
0x14002175c  test    r9b, 8
0x140021760  jz      short loc_1400217A2
0x140021762  cmp     al, 10h
0x140021764  jnz     short loc_140021776
0x140021766  movsxd  rcx, dword ptr [r10]
0x140021769  lea     rax, [r10+4]
0x14002176d  mov     [r8+8], rax
0x140021771  mov     [r8+30h], rcx
0x140021775  retn
0x140021776  and     r9b, cl
0x140021779  cmp     r9b, 20h ; ' '
0x14002177d  jnz     locret_14002183B
0x140021783  movsxd  rax, dword ptr [r10]
0x140021786  lea     rdx, [r10+4]
0x14002178a  mov     [r8+8], rdx
0x14002178e  mov     [r8+30h], rax
0x140021792  lea     rax, [rdx+4]
0x140021796  movsxd  rcx, dword ptr [rdx]
0x140021799  mov     [r8+8], rax
0x14002179d  jmp     loc_140021837
0x1400217a2  cmp     al, 10h
0x1400217a4  jnz     short loc_1400217D6
0x1400217a6  movzx   ecx, byte ptr [r10]
0x1400217aa  and     ecx, 0Fh
0x1400217ad  movsx   rax, byte ptr [rcx+r11+0BBEB0h]
0x1400217b6  mov     cl, [rcx+r11+0BBEC0h]
0x1400217be  sub     r10, rax
0x1400217c1  mov     eax, [r8+48h]
0x1400217c5  mov     edx, [r10-4]
0x1400217c9  shr     edx, cl
0x1400217cb  add     eax, edx
0x1400217cd  mov     [r8+8], r10
0x1400217d1  mov     [r8+30h], rax
0x1400217d5  retn
0x1400217d6  and     r9b, cl
0x1400217d9  cmp     r9b, 20h ; ' '
0x1400217dd  jnz     short locret_14002183B
0x1400217df  movzx   ecx, byte ptr [r10]
0x1400217e3  mov     edx, [r8+48h]
0x1400217e7  and     ecx, 0Fh
0x1400217ea  movsx   rax, byte ptr [rcx+r11+0BBEB0h]
0x1400217f3  mov     cl, [rcx+r11+0BBEC0h]
0x1400217fb  sub     r10, rax
0x1400217fe  mov     eax, [r10-4]
0x140021802  shr     eax, cl
0x140021804  mov     [r8+8], r10
0x140021808  lea     ecx, [rdx+rax]
0x14002180b  mov     [r8+30h], rcx
0x14002180f  movzx   ecx, byte ptr [r10]
0x140021813  and     ecx, 0Fh
0x140021816  movsx   rax, byte ptr [rcx+r11+0BBEB0h]
0x14002181f  mov     cl, [rcx+r11+0BBEC0h]
0x140021827  sub     r10, rax
0x14002182a  mov     eax, [r10-4]
0x14002182e  shr     eax, cl
0x140021830  mov     [r8+8], r10
0x140021834  lea     ecx, [rdx+rax]
0x140021837  mov     [r8+38h], rcx
0x14002183b  retn
```
