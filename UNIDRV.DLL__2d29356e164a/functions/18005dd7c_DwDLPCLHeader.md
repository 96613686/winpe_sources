# DwDLPCLHeader

- ea: `0x18005dd7c`
- end: `0x18005e0ce`
- name: `DwDLPCLHeader`
- size: `850`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18005b300`

## callees

- `0x180012590`
- `0x180032728`
- `0x1800487e0`
- `0x1800491dc`
- `0x18005dd7c`

## string_xrefs

- `0x18005df38`: `Cache %d`

## pseudocode

```c
__int64 __fastcall DwDLPCLHeader(__int64 a1, __int64 a2, int a3)
{
  int v6; // esi
  __int64 v7; // rcx
  int v8; // eax
  __int16 v9; // dx
  char v10; // al
  int v11; // r11d
  int v12; // edx
  int v13; // r10d
  int v14; // ecx
  __int16 v15; // r8
  int v16; // eax
  int v17; // ecx
  __int16 v18; // dx
  int v19; // ecx
  bool v20; // zf
  int v21; // eax
  int v22; // eax
  unsigned int v23; // edx
  unsigned __int16 v25; // [rsp+20h] [rbp-49h] BYREF
  char v26; // [rsp+22h] [rbp-47h]
  char v27; // [rsp+23h] [rbp-46h]
  unsigned __int16 v28; // [rsp+26h] [rbp-43h]
  unsigned __int16 v29; // [rsp+28h] [rbp-41h]
  unsigned __int16 v30; // [rsp+2Ah] [rbp-3Fh]
  char v31; // [rsp+2Ch] [rbp-3Dh]
  bool v32; // [rsp+2Dh] [rbp-3Ch]
  unsigned __int16 v33; // [rsp+2Eh] [rbp-3Bh]
  unsigned __int16 v34; // [rsp+30h] [rbp-39h]
  unsigned __int16 v35; // [rsp+32h] [rbp-37h]
  unsigned __int16 v36; // [rsp+34h] [rbp-35h]
  char v37; // [rsp+36h] [rbp-33h]
  bool v38; // [rsp+37h] [rbp-32h]
  __int16 v39; // [rsp+38h] [rbp-31h]
  char v40; // [rsp+3Bh] [rbp-2Eh]
  __int16 v41; // [rsp+3Eh] [rbp-2Bh]
  unsigned __int16 v42; // [rsp+40h] [rbp-29h]
  unsigned __int16 v43; // [rsp+42h] [rbp-27h]
  __int16 v44; // [rsp+48h] [rbp-21h]
  _BYTE v45[16]; // [rsp+50h] [rbp-19h] BYREF
  unsigned __int16 v46; // [rsp+60h] [rbp-9h]
  unsigned __int16 v47; // [rsp+62h] [rbp-7h]
  __int128 v48; // [rsp+70h] [rbp+7h] BYREF
  int v49; // [rsp+80h] [rbp+17h]

  v6 = 68;
  memset_0(&v25, 0, 0x44u);
  v7 = *(_QWORD *)(a1 + 2936);
  if ( *(_DWORD *)(v7 + 320) )
  {
    v46 = *(_WORD *)(a1 + 3944);
    v47 = *(_WORD *)(a1 + 3948);
    v25 = 68;
    v26 = 20;
  }
  else
  {
    v6 = 64;
    v25 = 64;
    v26 = 0;
  }
  v8 = *(_DWORD *)(v7 + 308);
  if ( v8 == -1 )
  {
    v9 = (*(_DWORD *)(*(_QWORD *)(a1 + 4136) + 16LL) & 1) != 0 ? 341 : 277;
    v10 = ((*(_DWORD *)(*(_QWORD *)(a1 + 4136) + 16LL) & 1) != 0) + 1;
  }
  else if ( v8 == 1 )
  {
    v10 = 1;
    v9 = 277;
  }
  else
  {
    v10 = 2;
    v9 = 341;
  }
  v11 = *(__int16 *)(a2 + 60);
  v33 = v9;
  v12 = *(_DWORD *)(a2 + 148);
  v27 = v10;
  v28 = v12;
  if ( v12 <= v11 )
    v28 = v11;
  v13 = *(__int16 *)(a2 + 76);
  v14 = *(_DWORD *)(a2 + 152) - *(_DWORD *)(a2 + 144) + 1;
  v29 = *(_WORD *)(a2 + 152) - *(_WORD *)(a2 + 144) + 1;
  if ( v14 <= v13 )
    v29 = v13;
  v15 = *(_WORD *)(a2 + 62);
  v16 = *(_DWORD *)(a2 + 156);
  v17 = -v15;
  v31 = 0;
  v37 = 0;
  v39 = 0;
  if ( v17 >= v16 )
    LOWORD(v17) = v16;
  v40 = 0;
  v41 = 1023;
  v44 = 0;
  if ( v12 <= v11 )
    LOWORD(v12) = v11;
  v18 = v12 - v17;
  v19 = *(_DWORD *)(a2 + 48) >> 12;
  v30 = v18 + 1;
  v35 = 4 * (v18 + 1);
  v32 = (v19 & 1) == 0;
  v20 = *(_DWORD *)(a2 + 136) == 0;
  v34 = 4 * v13;
  v38 = v20;
  v43 = 4 * v13;
  v36 = 4 * (v11 / 2);
  v42 = 4 * (v11 + v15);
  if ( (int)iDrvPrintfSafeA(v45, 16, "Cache %d", a3) < 0 )
    return 0;
  v25 = (v25 << 8) | HIBYTE(v25);
  v28 = (v28 << 8) | HIBYTE(v28);
  v29 = (v29 << 8) | HIBYTE(v29);
  v30 = (v30 << 8) | HIBYTE(v30);
  v33 = (v33 << 8) | HIBYTE(v33);
  v34 = (v34 << 8) | HIBYTE(v34);
  v35 = (v35 << 8) | HIBYTE(v35);
  v36 = (v36 << 8) | HIBYTE(v36);
  v42 = (v42 << 8) | HIBYTE(v42);
  v43 = (v43 << 8) | HIBYTE(v43);
  v46 = (v46 << 8) | HIBYTE(v46);
  v47 = (v47 << 8) | HIBYTE(v47);
  v48 = 0;
  v49 = 0;
  v21 = iDrvPrintfSafeA(&v48, 20, "\x1B)s%dW", v6);
  if ( v21 < 0 || (unsigned int)WriteSpoolBuf(a1, &v48, v21) != v21 )
    return 0;
  v22 = WriteSpoolBuf(a1, &v25, v6);
  v23 = 2048;
  if ( v22 != v6 )
    return 0;
  return v23;
}

```

## disassembly

```asm
0x18005dd7c  push    rbp
0x18005dd7e  push    rbx
0x18005dd7f  push    rsi
0x18005dd80  push    rdi
0x18005dd81  push    r13
0x18005dd83  push    r14
0x18005dd85  push    r15
0x18005dd87  lea     rbp, [rsp-27h]
0x18005dd8c  sub     rsp, 90h
0x18005dd93  mov     rax, cs:__security_cookie
0x18005dd9a  xor     rax, rsp
0x18005dd9d  mov     [rbp+57h+var_38], rax
0x18005dda1  mov     r15d, r8d
0x18005dda4  mov     rbx, rdx
0x18005dda7  mov     rdi, rcx
0x18005ddaa  mov     esi, 44h ; 'D'
0x18005ddaf  mov     r8d, esi; Size
0x18005ddb2  lea     rcx, [rbp+57h+var_A0]; void *
0x18005ddb6  xor     edx, edx; Val
0x18005ddb8  call    memset_0
0x18005ddbd  mov     rcx, [rdi+0B78h]
0x18005ddc4  lea     r8d, [rsi-4]
0x18005ddc8  cmp     dword ptr [rcx+140h], 0
0x18005ddcf  jnz     short loc_18005DDDF
0x18005ddd1  mov     esi, r8d
0x18005ddd4  mov     [rbp+57h+var_A0], r8w
0x18005ddd9  mov     [rbp+57h+var_9E], 0
0x18005dddd  jmp     short loc_18005DDFD
0x18005dddf  movzx   eax, word ptr [rdi+0F68h]
0x18005dde6  mov     [rbp+57h+var_60], ax
0x18005ddea  movzx   eax, word ptr [rdi+0F6Ch]
0x18005ddf1  mov     [rbp+57h+var_5E], ax
0x18005ddf5  mov     [rbp+57h+var_A0], si
0x18005ddf9  mov     [rbp+57h+var_9E], 14h
0x18005ddfd  mov     eax, [rcx+134h]
0x18005de03  mov     r13d, 2
0x18005de09  lea     r9d, [r13-1]
0x18005de0d  cmp     eax, 0FFFFFFFFh
0x18005de10  jnz     short loc_18005DE3E
0x18005de12  mov     rax, [rdi+1028h]
0x18005de19  mov     ecx, [rax+10h]
0x18005de1c  and     ecx, r9d
0x18005de1f  mov     eax, ecx
0x18005de21  neg     eax
0x18005de23  sbb     dx, dx
0x18005de26  and     dx, r8w
0x18005de2a  mov     r8d, 115h
0x18005de30  add     dx, r8w
0x18005de34  test    ecx, ecx
0x18005de36  setnz   al
0x18005de39  add     al, r9b
0x18005de3c  jmp     short loc_18005DE55
0x18005de3e  cmp     eax, r9d
0x18005de41  jnz     short loc_18005DE4D
0x18005de43  mov     al, r9b
0x18005de46  mov     edx, 115h
0x18005de4b  jmp     short loc_18005DE55
0x18005de4d  mov     al, r13b
0x18005de50  mov     edx, 155h
0x18005de55  movsx   r11d, word ptr [rbx+3Ch]
0x18005de5a  mov     [rbp+57h+var_92], dx
0x18005de5e  mov     edx, [rbx+94h]
0x18005de64  mov     [rbp+57h+var_9D], al
0x18005de67  mov     [rbp+57h+var_9A], dx
0x18005de6b  cmp     edx, r11d
0x18005de6e  jg      short loc_18005DE75
0x18005de70  mov     [rbp+57h+var_9A], r11w
0x18005de75  mov     ecx, [rbx+98h]
0x18005de7b  sub     ecx, [rbx+90h]
0x18005de81  movsx   r10d, word ptr [rbx+4Ch]
0x18005de86  inc     ecx
0x18005de88  mov     [rbp+57h+var_98], cx
0x18005de8c  cmp     ecx, r10d
0x18005de8f  jg      short loc_18005DE96
0x18005de91  mov     [rbp+57h+var_98], r10w
0x18005de96  movsx   r8d, word ptr [rbx+3Eh]
0x18005de9b  mov     eax, [rbx+9Ch]
0x18005dea1  mov     ecx, r8d
0x18005dea4  neg     ecx
0x18005dea6  mov     [rbp+57h+var_94], 0
0x18005deaa  cmp     ecx, eax
0x18005deac  mov     [rbp+57h+var_8A], 0
0x18005deb0  mov     [rbp+57h+var_88], 0
0x18005deb6  cmovge  cx, ax
0x18005deba  mov     [rbp+57h+var_85], 0
0x18005debe  cmp     edx, r11d
0x18005dec1  mov     [rbp+57h+var_82], 3FFh
0x18005dec7  mov     eax, r11d
0x18005deca  mov     [rbp+57h+var_78], 0
0x18005ded0  cmovle  dx, r11w
0x18005ded5  shl     r10w, 2
0x18005deda  sub     dx, cx
0x18005dedd  mov     ecx, [rbx+30h]
0x18005dee0  add     dx, r9w
0x18005dee4  shr     ecx, 0Ch
0x18005dee7  mov     [rbp+57h+var_96], dx
0x18005deeb  not     cl
0x18005deed  shl     dx, 2
0x18005def1  and     cl, r9b
0x18005def4  mov     [rbp+57h+var_8E], dx
0x18005def8  mov     r9d, r15d
0x18005defb  cdq
0x18005defc  mov     [rbp+57h+var_93], cl
0x18005deff  idiv    r13d
0x18005df02  movzx   ecx, r10w
0x18005df06  mov     edx, 10h
0x18005df0b  shl     ax, 2
0x18005df0f  cmp     dword ptr [rbx+88h], 0
0x18005df16  mov     [rbp+57h+var_90], cx
0x18005df1a  setz    [rbp+57h+var_89]
0x18005df1e  mov     [rbp+57h+var_7E], cx
0x18005df22  add     r8w, r11w
0x18005df26  mov     [rbp+57h+var_8C], ax
0x18005df2a  shl     r8w, 2
0x18005df2f  lea     rcx, [rbp+57h+var_70]
0x18005df33  mov     [rbp+57h+var_80], r8w
0x18005df38  lea     r8, aCacheD; "Cache %d"
0x18005df3f  call    iDrvPrintfSafeA
0x18005df44  test    eax, eax
0x18005df46  js      loc_18005E0AE
0x18005df4c  movzx   eax, [rbp+57h+var_A0]
0x18005df50  lea     r8, aSDw_0; "\x1B)s%dW"
0x18005df57  movzx   ecx, ax
0x18005df5a  xorps   xmm0, xmm0
0x18005df5d  shr     cx, 8
0x18005df61  mov     r9d, esi
0x18005df64  shl     ax, 8
0x18005df68  or      cx, ax
0x18005df6b  movzx   eax, [rbp+57h+var_9A]
0x18005df6f  mov     [rbp+57h+var_A0], cx
0x18005df73  movzx   ecx, ax
0x18005df76  shr     cx, 8
0x18005df7a  shl     ax, 8
0x18005df7e  or      cx, ax
0x18005df81  movzx   eax, [rbp+57h+var_98]
0x18005df85  mov     [rbp+57h+var_9A], cx
0x18005df89  movzx   ecx, ax
0x18005df8c  shr     cx, 8
0x18005df90  shl     ax, 8
0x18005df94  or      cx, ax
0x18005df97  movzx   eax, [rbp+57h+var_96]
0x18005df9b  mov     [rbp+57h+var_98], cx
0x18005df9f  movzx   ecx, ax
0x18005dfa2  shr     cx, 8
0x18005dfa6  shl     ax, 8
0x18005dfaa  or      cx, ax
0x18005dfad  movzx   eax, [rbp+57h+var_92]
0x18005dfb1  mov     [rbp+57h+var_96], cx
0x18005dfb5  movzx   ecx, ax
0x18005dfb8  shr     cx, 8
0x18005dfbc  shl     ax, 8
0x18005dfc0  or      cx, ax
0x18005dfc3  movzx   eax, [rbp+57h+var_90]
0x18005dfc7  mov     [rbp+57h+var_92], cx
0x18005dfcb  movzx   ecx, ax
0x18005dfce  shr     cx, 8
0x18005dfd2  shl     ax, 8
0x18005dfd6  or      cx, ax
0x18005dfd9  movzx   eax, [rbp+57h+var_8E]
0x18005dfdd  mov     [rbp+57h+var_90], cx
0x18005dfe1  movzx   ecx, ax
0x18005dfe4  shr     cx, 8
0x18005dfe8  shl     ax, 8
0x18005dfec  or      cx, ax
0x18005dfef  movzx   eax, [rbp+57h+var_8C]
0x18005dff3  mov     [rbp+57h+var_8E], cx
0x18005dff7  movzx   ecx, ax
0x18005dffa  shr     cx, 8
0x18005dffe  shl     ax, 8
0x18005e002  or      cx, ax
0x18005e005  movzx   eax, [rbp+57h+var_80]
0x18005e009  mov     [rbp+57h+var_8C], cx
0x18005e00d  movzx   ecx, ax
0x18005e010  shr     cx, 8
0x18005e014  shl     ax, 8
0x18005e018  or      cx, ax
0x18005e01b  movzx   eax, [rbp+57h+var_7E]
0x18005e01f  mov     [rbp+57h+var_80], cx
0x18005e023  movzx   ecx, ax
0x18005e026  shr     cx, 8
0x18005e02a  shl     ax, 8
0x18005e02e  or      cx, ax
0x18005e031  movzx   eax, [rbp+57h+var_60]
0x18005e035  mov     [rbp+57h+var_7E], cx
0x18005e039  movzx   ecx, ax
0x18005e03c  shr     cx, 8
0x18005e040  shl     ax, 8
0x18005e044  or      cx, ax
0x18005e047  movzx   eax, [rbp+57h+var_5E]
0x18005e04b  mov     [rbp+57h+var_60], cx
0x18005e04f  movzx   ecx, ax
0x18005e052  shr     cx, 8
0x18005e056  shl     ax, 8
0x18005e05a  or      cx, ax
0x18005e05d  xor     eax, eax
0x18005e05f  mov     [rbp+57h+var_5E], cx
0x18005e063  lea     rcx, [rbp+57h+var_50]
0x18005e067  movups  [rbp+57h+var_50], xmm0
0x18005e06b  mov     [rbp+57h+var_40], eax
0x18005e06e  lea     edx, [rax+14h]
0x18005e071  call    iDrvPrintfSafeA
0x18005e076  mov     ebx, eax
0x18005e078  test    eax, eax
0x18005e07a  js      short loc_18005E0AE
0x18005e07c  mov     r8d, eax
0x18005e07f  lea     rdx, [rbp+57h+var_50]
0x18005e083  mov     rcx, rdi
0x18005e086  call    WriteSpoolBuf
0x18005e08b  cmp     eax, ebx
0x18005e08d  jnz     short loc_18005E0AE
0x18005e08f  mov     r8d, esi
0x18005e092  lea     rdx, [rbp+57h+var_A0]
0x18005e096  mov     rcx, rdi
0x18005e099  call    WriteSpoolBuf
0x18005e09e  xor     ecx, ecx
0x18005e0a0  mov     edx, 800h
0x18005e0a5  cmp     eax, esi
0x18005e0a7  cmovnz  edx, ecx
0x18005e0aa  mov     eax, edx
0x18005e0ac  jmp     short loc_18005E0B0
0x18005e0ae  xor     eax, eax
0x18005e0b0  mov     rcx, [rbp+57h+var_38]
0x18005e0b4  xor     rcx, rsp; StackCookie
0x18005e0b7  call    __security_check_cookie
0x18005e0bc  add     rsp, 90h
0x18005e0c3  pop     r15
0x18005e0c5  pop     r14
0x18005e0c7  pop     r13
0x18005e0c9  pop     rdi
0x18005e0ca  pop     rsi
0x18005e0cb  pop     rbx
0x18005e0cc  pop     rbp
0x18005e0cd  retn
```
