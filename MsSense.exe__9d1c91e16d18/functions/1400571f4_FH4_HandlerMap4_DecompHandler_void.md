# FH4::HandlerMap4::DecompHandler(void)

- ea: `0x1400571f4`
- end: `0x14005737c`
- name: `?DecompHandler@HandlerMap4@FH4@@AEAAXXZ`
- size: `392`
- prototype: `void __fastcall(FH4::HandlerMap4 *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140055a00`
- `0x1400561b0`
- `0x140056c50`

## callees

- `0x1400571f4`

## pseudocode

```c
void __fastcall FH4::HandlerMap4::DecompHandler(FH4::HandlerMap4 *this)
{
  char *v2; // rax
  char v3; // r10
  _BYTE *v4; // rdx
  __int64 v5; // rcx
  int v6; // eax
  __int64 v7; // rcx
  int *v8; // r9
  char v9; // al
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  char *v14; // r9
  __int64 v15; // rax
  int v16; // edx
  __int64 v17; // rcx
  _BYTE *v18; // r9
  int v19; // eax
  __int64 v20; // rcx
  _BYTE *v21; // r9
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
    v4 -= *((char *)qword_14009C050 + v5);
    *((_DWORD *)this + 7) = *((_DWORD *)v4 - 1) >> *((_BYTE *)&qword_14009C050[2] + v5);
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
    v4 -= *((char *)qword_14009C050 + v7);
    *((_DWORD *)this + 9) = *((_DWORD *)v4 - 1) >> *((_BYTE *)&qword_14009C050[2] + v7);
    *((_QWORD *)this + 1) = v4;
  }
  v8 = (int *)(v4 + 4);
  *((_DWORD *)this + 10) = *(_DWORD *)v4;
  v9 = v3 & 0x30;
  *((_QWORD *)this + 1) = v4 + 4;
  if ( (v3 & 8) != 0 )
  {
    if ( v9 == 16 )
    {
      v10 = *v8;
      *((_QWORD *)this + 1) = v4 + 8;
      *((_QWORD *)this + 6) = v10;
      return;
    }
    if ( v9 == 32 )
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
      v14 = (char *)v8 - *((char *)qword_14009C050 + v13);
      v15 = (unsigned int)((*((_DWORD *)v14 - 1) >> *((_BYTE *)&qword_14009C050[2] + v13)) + *((_DWORD *)this + 18));
      *((_QWORD *)this + 1) = v14;
      *((_QWORD *)this + 6) = v15;
      return;
    }
    if ( v9 == 32 )
    {
      v16 = *((_DWORD *)this + 18);
      v17 = *(_BYTE *)v8 & 0xF;
      v18 = (char *)v8 - *((char *)qword_14009C050 + v17);
      v19 = *((_DWORD *)v18 - 1) >> *((_BYTE *)&qword_14009C050[2] + v17);
      *((_QWORD *)this + 1) = v18;
      *((_QWORD *)this + 6) = (unsigned int)(v16 + v19);
      v20 = *v18 & 0xF;
      v21 = &v18[-*((char *)qword_14009C050 + v20)];
      v22 = *((_DWORD *)v21 - 1) >> *((_BYTE *)&qword_14009C050[2] + v20);
      *((_QWORD *)this + 1) = v21;
      v12 = (unsigned int)(v16 + v22);
      goto LABEL_16;
    }
  }
}

```

## disassembly

```asm
0x1400571f4  xor     eax, eax
0x1400571f6  lea     r11, __ImageBase
0x1400571fd  mov     [rcx+18h], al
0x140057200  xorps   xmm0, xmm0
0x140057203  mov     [rcx+1Ch], rax
0x140057207  mov     r8, rcx
0x14005720a  mov     [rcx+24h], rax
0x14005720e  movups  xmmword ptr [rcx+30h], xmm0
0x140057212  mov     rax, [rcx+8]
0x140057216  mov     r10b, [rax]
0x140057219  lea     rdx, [rax+1]
0x14005721d  mov     [rcx+18h], r10b
0x140057221  mov     [rcx+8], rdx
0x140057225  test    r10b, 1
0x140057229  jz      short loc_140057252
0x14005722b  movzx   ecx, byte ptr [rdx]
0x14005722e  and     ecx, 0Fh
0x140057231  movsx   rax, byte ptr [rcx+r11+9C050h]
0x14005723a  mov     cl, [rcx+r11+9C060h]
0x140057242  sub     rdx, rax
0x140057245  mov     eax, [rdx-4]
0x140057248  shr     eax, cl
0x14005724a  mov     [r8+1Ch], eax
0x14005724e  mov     [r8+8], rdx
0x140057252  test    r10b, 2
0x140057256  jz      short loc_140057266
0x140057258  mov     eax, [rdx]
0x14005725a  add     rdx, 4
0x14005725e  mov     [r8+8], rdx
0x140057262  mov     [r8+20h], eax
0x140057266  test    r10b, 4
0x14005726a  jz      short loc_140057293
0x14005726c  movzx   ecx, byte ptr [rdx]
0x14005726f  and     ecx, 0Fh
0x140057272  movsx   rax, byte ptr [rcx+r11+9C050h]
0x14005727b  mov     cl, [rcx+r11+9C060h]
0x140057283  sub     rdx, rax
0x140057286  mov     eax, [rdx-4]
0x140057289  shr     eax, cl
0x14005728b  mov     [r8+24h], eax
0x14005728f  mov     [r8+8], rdx
0x140057293  mov     eax, [rdx]
0x140057295  lea     r9, [rdx+4]
0x140057299  mov     [r8+28h], eax
0x14005729d  mov     al, r10b
0x1400572a0  and     al, 30h
0x1400572a2  mov     [r8+8], r9
0x1400572a6  test    r10b, 8
0x1400572aa  jz      short loc_1400572E7
0x1400572ac  cmp     al, 10h
0x1400572ae  jnz     short loc_1400572C0
0x1400572b0  movsxd  rcx, dword ptr [r9]
0x1400572b3  lea     rax, [r9+4]
0x1400572b7  mov     [r8+8], rax
0x1400572bb  mov     [r8+30h], rcx
0x1400572bf  retn
0x1400572c0  cmp     al, 20h ; ' '
0x1400572c2  jnz     locret_14005737B
0x1400572c8  movsxd  rax, dword ptr [r9]
0x1400572cb  lea     rdx, [r9+4]
0x1400572cf  mov     [r8+8], rdx
0x1400572d3  mov     [r8+30h], rax
0x1400572d7  lea     rax, [rdx+4]
0x1400572db  movsxd  rcx, dword ptr [rdx]
0x1400572de  mov     [r8+8], rax
0x1400572e2  jmp     loc_140057377
0x1400572e7  cmp     al, 10h
0x1400572e9  jnz     short loc_14005731B
0x1400572eb  movzx   ecx, byte ptr [r9]
0x1400572ef  and     ecx, 0Fh
0x1400572f2  movsx   rax, byte ptr [rcx+r11+9C050h]
0x1400572fb  mov     cl, [rcx+r11+9C060h]
0x140057303  sub     r9, rax
0x140057306  mov     eax, [r8+48h]
0x14005730a  mov     edx, [r9-4]
0x14005730e  shr     edx, cl
0x140057310  add     eax, edx
0x140057312  mov     [r8+8], r9
0x140057316  mov     [r8+30h], rax
0x14005731a  retn
0x14005731b  cmp     al, 20h ; ' '
0x14005731d  jnz     short locret_14005737B
0x14005731f  movzx   ecx, byte ptr [r9]
0x140057323  mov     edx, [r8+48h]
0x140057327  and     ecx, 0Fh
0x14005732a  movsx   rax, byte ptr [rcx+r11+9C050h]
0x140057333  mov     cl, [rcx+r11+9C060h]
0x14005733b  sub     r9, rax
0x14005733e  mov     eax, [r9-4]
0x140057342  shr     eax, cl
0x140057344  mov     [r8+8], r9
0x140057348  lea     ecx, [rdx+rax]
0x14005734b  mov     [r8+30h], rcx
0x14005734f  movzx   ecx, byte ptr [r9]
0x140057353  and     ecx, 0Fh
0x140057356  movsx   rax, byte ptr [rcx+r11+9C050h]
0x14005735f  mov     cl, [rcx+r11+9C060h]
0x140057367  sub     r9, rax
0x14005736a  mov     eax, [r9-4]
0x14005736e  shr     eax, cl
0x140057370  mov     [r8+8], r9
0x140057374  lea     ecx, [rdx+rax]
0x140057377  mov     [r8+38h], rcx
0x14005737b  retn
```
