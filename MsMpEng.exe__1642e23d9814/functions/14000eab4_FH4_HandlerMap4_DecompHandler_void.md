# FH4::HandlerMap4::DecompHandler(void)

- ea: `0x14000eab4`
- end: `0x14000ec3c`
- name: `?DecompHandler@HandlerMap4@FH4@@AEAAXXZ`
- size: `392`
- prototype: `void __fastcall(FH4::HandlerMap4 *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000d260`
- `0x14000da10`
- `0x14000e4b0`

## callees

- `0x14000eab4`

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
    v4 -= *((char *)qword_14002D5E0 + v5);
    *((_DWORD *)this + 7) = *((_DWORD *)v4 - 1) >> *((_BYTE *)&qword_14002D5E0[2] + v5);
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
    v4 -= *((char *)qword_14002D5E0 + v7);
    *((_DWORD *)this + 9) = *((_DWORD *)v4 - 1) >> *((_BYTE *)&qword_14002D5E0[2] + v7);
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
      v14 = (char *)v8 - *((char *)qword_14002D5E0 + v13);
      v15 = (unsigned int)((*((_DWORD *)v14 - 1) >> *((_BYTE *)&qword_14002D5E0[2] + v13)) + *((_DWORD *)this + 18));
      *((_QWORD *)this + 1) = v14;
      *((_QWORD *)this + 6) = v15;
      return;
    }
    if ( v9 == 32 )
    {
      v16 = *((_DWORD *)this + 18);
      v17 = *(_BYTE *)v8 & 0xF;
      v18 = (char *)v8 - *((char *)qword_14002D5E0 + v17);
      v19 = *((_DWORD *)v18 - 1) >> *((_BYTE *)&qword_14002D5E0[2] + v17);
      *((_QWORD *)this + 1) = v18;
      *((_QWORD *)this + 6) = (unsigned int)(v16 + v19);
      v20 = *v18 & 0xF;
      v21 = &v18[-*((char *)qword_14002D5E0 + v20)];
      v22 = *((_DWORD *)v21 - 1) >> *((_BYTE *)&qword_14002D5E0[2] + v20);
      *((_QWORD *)this + 1) = v21;
      v12 = (unsigned int)(v16 + v22);
      goto LABEL_16;
    }
  }
}

```

## disassembly

```asm
0x14000eab4  xor     eax, eax
0x14000eab6  lea     r11, cs:140000000h
0x14000eabd  mov     [rcx+18h], al
0x14000eac0  xorps   xmm0, xmm0
0x14000eac3  mov     [rcx+1Ch], rax
0x14000eac7  mov     r8, rcx
0x14000eaca  mov     [rcx+24h], rax
0x14000eace  movups  xmmword ptr [rcx+30h], xmm0
0x14000ead2  mov     rax, [rcx+8]
0x14000ead6  mov     r10b, [rax]
0x14000ead9  lea     rdx, [rax+1]
0x14000eadd  mov     [rcx+18h], r10b
0x14000eae1  mov     [rcx+8], rdx
0x14000eae5  test    r10b, 1
0x14000eae9  jz      short loc_14000EB12
0x14000eaeb  movzx   ecx, byte ptr [rdx]
0x14000eaee  and     ecx, 0Fh
0x14000eaf1  movsx   rax, byte ptr [rcx+r11+2D5E0h]
0x14000eafa  mov     cl, [rcx+r11+2D5F0h]
0x14000eb02  sub     rdx, rax
0x14000eb05  mov     eax, [rdx-4]
0x14000eb08  shr     eax, cl
0x14000eb0a  mov     [r8+1Ch], eax
0x14000eb0e  mov     [r8+8], rdx
0x14000eb12  test    r10b, 2
0x14000eb16  jz      short loc_14000EB26
0x14000eb18  mov     eax, [rdx]
0x14000eb1a  add     rdx, 4
0x14000eb1e  mov     [r8+8], rdx
0x14000eb22  mov     [r8+20h], eax
0x14000eb26  test    r10b, 4
0x14000eb2a  jz      short loc_14000EB53
0x14000eb2c  movzx   ecx, byte ptr [rdx]
0x14000eb2f  and     ecx, 0Fh
0x14000eb32  movsx   rax, byte ptr [rcx+r11+2D5E0h]
0x14000eb3b  mov     cl, [rcx+r11+2D5F0h]
0x14000eb43  sub     rdx, rax
0x14000eb46  mov     eax, [rdx-4]
0x14000eb49  shr     eax, cl
0x14000eb4b  mov     [r8+24h], eax
0x14000eb4f  mov     [r8+8], rdx
0x14000eb53  mov     eax, [rdx]
0x14000eb55  lea     r9, [rdx+4]
0x14000eb59  mov     [r8+28h], eax
0x14000eb5d  mov     al, r10b
0x14000eb60  and     al, 30h
0x14000eb62  mov     [r8+8], r9
0x14000eb66  test    r10b, 8
0x14000eb6a  jz      short loc_14000EBA7
0x14000eb6c  cmp     al, 10h
0x14000eb6e  jnz     short loc_14000EB80
0x14000eb70  movsxd  rcx, dword ptr [r9]
0x14000eb73  lea     rax, [r9+4]
0x14000eb77  mov     [r8+8], rax
0x14000eb7b  mov     [r8+30h], rcx
0x14000eb7f  retn
0x14000eb80  cmp     al, 20h ; ' '
0x14000eb82  jnz     locret_14000EC3B
0x14000eb88  movsxd  rax, dword ptr [r9]
0x14000eb8b  lea     rdx, [r9+4]
0x14000eb8f  mov     [r8+8], rdx
0x14000eb93  mov     [r8+30h], rax
0x14000eb97  lea     rax, [rdx+4]
0x14000eb9b  movsxd  rcx, dword ptr [rdx]
0x14000eb9e  mov     [r8+8], rax
0x14000eba2  jmp     loc_14000EC37
0x14000eba7  cmp     al, 10h
0x14000eba9  jnz     short loc_14000EBDB
0x14000ebab  movzx   ecx, byte ptr [r9]
0x14000ebaf  and     ecx, 0Fh
0x14000ebb2  movsx   rax, byte ptr [rcx+r11+2D5E0h]
0x14000ebbb  mov     cl, [rcx+r11+2D5F0h]
0x14000ebc3  sub     r9, rax
0x14000ebc6  mov     eax, [r8+48h]
0x14000ebca  mov     edx, [r9-4]
0x14000ebce  shr     edx, cl
0x14000ebd0  add     eax, edx
0x14000ebd2  mov     [r8+8], r9
0x14000ebd6  mov     [r8+30h], rax
0x14000ebda  retn
0x14000ebdb  cmp     al, 20h ; ' '
0x14000ebdd  jnz     short locret_14000EC3B
0x14000ebdf  movzx   ecx, byte ptr [r9]
0x14000ebe3  mov     edx, [r8+48h]
0x14000ebe7  and     ecx, 0Fh
0x14000ebea  movsx   rax, byte ptr [rcx+r11+2D5E0h]
0x14000ebf3  mov     cl, [rcx+r11+2D5F0h]
0x14000ebfb  sub     r9, rax
0x14000ebfe  mov     eax, [r9-4]
0x14000ec02  shr     eax, cl
0x14000ec04  mov     [r8+8], r9
0x14000ec08  lea     ecx, [rdx+rax]
0x14000ec0b  mov     [r8+30h], rcx
0x14000ec0f  movzx   ecx, byte ptr [r9]
0x14000ec13  and     ecx, 0Fh
0x14000ec16  movsx   rax, byte ptr [rcx+r11+2D5E0h]
0x14000ec1f  mov     cl, [rcx+r11+2D5F0h]
0x14000ec27  sub     r9, rax
0x14000ec2a  mov     eax, [r9-4]
0x14000ec2e  shr     eax, cl
0x14000ec30  mov     [r8+8], r9
0x14000ec34  lea     ecx, [rdx+rax]
0x14000ec37  mov     [r8+38h], rcx
0x14000ec3b  retn
```
