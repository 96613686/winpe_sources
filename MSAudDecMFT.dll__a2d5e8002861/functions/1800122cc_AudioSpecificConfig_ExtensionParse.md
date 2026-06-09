# AudioSpecificConfig_ExtensionParse

- ea: `0x1800122cc`
- end: `0x180012577`
- name: `AudioSpecificConfig_ExtensionParse`
- size: `683`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180011da8`

## callees

- `0x18000e9b0`
- `0x1800110c0`
- `0x180012264`
- `0x1800122cc`
- `0x1800125f4`
- `0x180012768`
- `0x1800960c0`

## pseudocode

```c
__int64 __fastcall AudioSpecificConfig_ExtensionParse(__int64 a1, int *a2, __int64 a3)
{
  int v4; // r14d
  __int64 v7; // r8
  int v8; // edi
  int v9; // ebp
  int v10; // eax
  int v12; // edi
  unsigned int v13; // ebp
  __int64 v14; // r8
  __int64 v15; // r8
  unsigned int (__fastcall *v16)(_QWORD, int *, _QWORD, _QWORD, _DWORD, _DWORD, int, int, unsigned int, int, __int64); // rax
  int AOT; // eax
  __int64 v18; // r8
  char v19; // al
  __int64 v20; // r8
  bool v21; // zf
  int SampleRate; // eax
  int v23; // [rsp+48h] [rbp-60h]

  v4 = -1;
  CDKsyncCache_0(a2);
  while ( 2 )
  {
    v8 = a2[2];
    do
    {
      while ( 1 )
      {
        if ( v8 < 11 )
          return 0;
        v9 = v4;
        v10 = CDKreadBits(a2, 11, v7);
        v8 -= 11;
        v4 = v10;
        if ( v10 == 695 )
          break;
        switch ( v10 )
        {
          case 1352:
            if ( v9 == 695 && *(_DWORD *)(a1 + 1216) == 5 && v8 > 0 )
            {
              *(_BYTE *)(a1 + 1230) = CDKreadBits(a2, 1, v7);
              --v8;
            }
            break;
          case 1898:
            if ( *(_DWORD *)(a1 + 1216) != 30 )
            {
LABEL_17:
              if ( (v10 != 1996 || *(_DWORD *)(a1 + 1216) != 44) && v8 >= 1 )
              {
                --v8;
                if ( (unsigned int)CDKreadBits(a2, 1, v7) )
                {
                  v12 = v8 - 8;
                  v13 = CDKreadBits(a2, 8, v7);
                  if ( v13 == 255 )
                  {
                    v12 -= 16;
                    v13 = CDKreadBits(a2, 16, v15) + 255;
                  }
                  v16 = *(unsigned int (__fastcall **)(_QWORD, int *, _QWORD, _QWORD, _DWORD, _DWORD, int, int, unsigned int, int, __int64))(a3 + 64);
                  if ( !v16 )
                    goto LABEL_14;
                  LOBYTE(v23) = *(_BYTE *)(a1 + 1234);
                  if ( v16(
                         *(_QWORD *)(a3 + 72),
                         a2,
                         *(unsigned int *)(a1 + 1200),
                         *(unsigned int *)(a1 + 1204),
                         *(_DWORD *)(a1 + 1208),
                         *(char *)(a1 + 1224),
                         1,
                         -1,
                         v13,
                         v23,
                         a1 + 1237) )
                  {
                    return 1025;
                  }
LABEL_15:
                  v8 = v12 - 8 * v13;
                }
              }
            }
            break;
          case 1995:
            if ( *(_DWORD *)(a1 + 1216) != 43 && (unsigned int)CDKreadBits(a2, 1, v7) )
            {
              v12 = v8 - 8;
              v13 = CDKreadBits(a2, 8, v7);
              if ( v13 == 255 )
              {
                v12 -= 16;
                v13 = CDKreadBits(a2, 16, v14) + 255;
              }
LABEL_14:
              CDKpushFor(a2, v13);
              goto LABEL_15;
            }
            break;
          case 1996:
            goto LABEL_17;
          default:
            return 0;
        }
      }
    }
    while ( *(_DWORD *)(a1 + 1216) == 5 || v8 < 5 );
    AOT = getAOT(a2);
    *(_DWORD *)(a1 + 1216) = AOT;
    if ( AOT != 5 && AOT != 22 )
      goto LABEL_41;
    v19 = CDKreadBits(a2, 1, v18);
    v21 = *(_DWORD *)(a1 + 1200) == 42;
    *(_BYTE *)(a1 + 1229) = v19;
    if ( !v21 || v19 <= 0 || *(_BYTE *)(a1 + 2) )
    {
      if ( v19 != 1
        || (SampleRate = getSampleRate(a2, a1 + 1232, 4),
            *(_DWORD *)(a1 + 1220) = SampleRate,
            (unsigned int)(SampleRate - 1) <= 0x176FF) )
      {
        if ( *(_DWORD *)(a1 + 1216) == 22 )
          *(_BYTE *)(a1 + 1233) = CDKreadBits(a2, 4, v20);
LABEL_41:
        CDKsyncCache_0(a2);
        continue;
      }
    }
    return 1025;
  }
}

```

## disassembly

```asm
0x1800122cc  push    rbx
0x1800122ce  push    rbp
0x1800122cf  push    rsi
0x1800122d0  push    rdi
0x1800122d1  push    r12
0x1800122d3  push    r13
0x1800122d5  push    r14
0x1800122d7  push    r15
0x1800122d9  sub     rsp, 68h
0x1800122dd  mov     rsi, rcx
0x1800122e0  or      r14d, 0FFFFFFFFh
0x1800122e4  mov     rcx, rdx
0x1800122e7  mov     r15, r8
0x1800122ea  mov     rbx, rdx
0x1800122ed  call    CDKsyncCache_0
0x1800122f2  lea     r12d, [r14+2]
0x1800122f6  mov     r13d, 0FFh
0x1800122fc  mov     edi, [rbx+8]
0x1800122ff  cmp     edi, 0Bh
0x180012302  jl      short loc_180012346
0x180012304  mov     edx, 0Bh
0x180012309  mov     rcx, rbx
0x18001230c  mov     ebp, r14d
0x18001230f  call    CDKreadBits
0x180012314  mov     edx, eax
0x180012316  sub     edi, 0Bh
0x180012319  mov     r14d, eax
0x18001231c  sub     edx, 2B7h
0x180012322  jz      loc_1800124CB
0x180012328  sub     edx, 291h
0x18001232e  jz      loc_180012491
0x180012334  sub     edx, 222h
0x18001233a  jz      short loc_1800123B1
0x18001233c  sub     edx, 61h ; 'a'
0x18001233f  jz      short loc_18001235A
0x180012341  cmp     edx, r12d
0x180012344  jz      short loc_1800123BE
0x180012346  xor     eax, eax
0x180012348  add     rsp, 68h
0x18001234c  pop     r15
0x18001234e  pop     r14
0x180012350  pop     r13
0x180012352  pop     r12
0x180012354  pop     rdi
0x180012355  pop     rsi
0x180012356  pop     rbp
0x180012357  pop     rbx
0x180012358  retn
0x18001235a  cmp     dword ptr [rsi+4C0h], 2Bh ; '+'
0x180012361  jz      short loc_1800122FF
0x180012363  mov     edx, r12d
0x180012366  mov     rcx, rbx
0x180012369  call    CDKreadBits
0x18001236e  test    eax, eax
0x180012370  jz      short loc_1800122FF
0x180012372  mov     edx, 8
0x180012377  mov     rcx, rbx
0x18001237a  call    CDKreadBits
0x18001237f  add     edi, 0FFFFFFF8h
0x180012382  mov     ebp, eax
0x180012384  cmp     eax, r13d
0x180012387  jnz     short loc_18001239D
0x180012389  mov     edx, 10h
0x18001238e  mov     rcx, rbx
0x180012391  call    CDKreadBits
0x180012396  add     edi, 0FFFFFFF0h
0x180012399  lea     ebp, [rax+r13]
0x18001239d  mov     edx, ebp
0x18001239f  mov     rcx, rbx
0x1800123a2  call    CDKpushFor
0x1800123a7  neg     ebp
0x1800123a9  lea     edi, [rdi+rbp*8]
0x1800123ac  jmp     loc_1800122FF
0x1800123b1  cmp     dword ptr [rsi+4C0h], 1Eh
0x1800123b8  jz      loc_1800122FF
0x1800123be  cmp     eax, 7CCh
0x1800123c3  jnz     short loc_1800123D2
0x1800123c5  cmp     dword ptr [rsi+4C0h], 2Ch ; ','
0x1800123cc  jz      loc_1800122FF
0x1800123d2  cmp     edi, r12d
0x1800123d5  jl      loc_1800122FF
0x1800123db  mov     edx, r12d
0x1800123de  mov     rcx, rbx
0x1800123e1  dec     edi
0x1800123e3  call    CDKreadBits
0x1800123e8  test    eax, eax
0x1800123ea  jz      loc_1800122FF
0x1800123f0  mov     edx, 8
0x1800123f5  mov     rcx, rbx
0x1800123f8  call    CDKreadBits
0x1800123fd  add     edi, 0FFFFFFF8h
0x180012400  mov     ebp, eax
0x180012402  cmp     eax, r13d
0x180012405  jnz     short loc_18001241B
0x180012407  mov     edx, 10h
0x18001240c  mov     rcx, rbx
0x18001240f  call    CDKreadBits
0x180012414  add     edi, 0FFFFFFF0h
0x180012417  lea     ebp, [rax+r13]
0x18001241b  mov     rax, [r15+40h]
0x18001241f  test    rax, rax
0x180012422  jz      loc_18001239D
0x180012428  movsx   edx, byte ptr [rsi+4C8h]
0x18001242f  lea     rcx, [rsi+4D5h]
0x180012436  mov     r9d, [rsi+4B4h]
0x18001243d  mov     r8d, [rsi+4B0h]
0x180012444  mov     [rsp+0A8h+var_58], rcx
0x180012449  mov     cl, [rsi+4D2h]
0x18001244f  mov     [rsp+0A8h+var_60], cl
0x180012453  mov     ecx, [rsi+4B8h]
0x180012459  mov     [rsp+0A8h+var_68], ebp
0x18001245d  mov     [rsp+0A8h+var_70], 0FFFFFFFFh
0x180012465  mov     [rsp+0A8h+var_78], r12d
0x18001246a  mov     [rsp+0A8h+var_80], edx
0x18001246e  mov     rdx, rbx
0x180012471  mov     [rsp+0A8h+var_88], ecx
0x180012475  mov     rcx, [r15+48h]
0x180012479  call    cs:__guard_dispatch_icall_fptr
0x18001247f  test    eax, eax
0x180012481  jz      loc_1800123A7
0x180012487  mov     eax, 401h
0x18001248c  jmp     loc_180012348
0x180012491  cmp     ebp, 2B7h
0x180012497  jnz     loc_1800122FF
0x18001249d  cmp     dword ptr [rsi+4C0h], 5
0x1800124a4  jnz     loc_1800122FF
0x1800124aa  test    edi, edi
0x1800124ac  jle     loc_1800122FF
0x1800124b2  mov     edx, r12d
0x1800124b5  mov     rcx, rbx
0x1800124b8  call    CDKreadBits
0x1800124bd  mov     [rsi+4CEh], al
0x1800124c3  sub     edi, r12d
0x1800124c6  jmp     loc_1800122FF
0x1800124cb  cmp     dword ptr [rsi+4C0h], 5
0x1800124d2  jz      loc_1800122FF
0x1800124d8  cmp     edi, 5
0x1800124db  jl      loc_1800122FF
0x1800124e1  mov     rcx, rbx
0x1800124e4  call    getAOT
0x1800124e9  mov     [rsi+4C0h], eax
0x1800124ef  cmp     eax, 5
0x1800124f2  jz      short loc_1800124F9
0x1800124f4  cmp     eax, 16h
0x1800124f7  jnz     short loc_18001256A
0x1800124f9  mov     edx, r12d
0x1800124fc  mov     rcx, rbx
0x1800124ff  call    CDKreadBits
0x180012504  cmp     dword ptr [rsi+4B0h], 2Ah ; '*'
0x18001250b  mov     [rsi+4CDh], al
0x180012511  jnz     short loc_180012521
0x180012513  test    al, al
0x180012515  jle     short loc_180012521
0x180012517  cmp     byte ptr [rsi+2], 0
0x18001251b  jz      loc_180012487
0x180012521  cmp     al, r12b
0x180012524  jnz     short loc_18001254E
0x180012526  lea     rdx, [rsi+4D0h]
0x18001252d  mov     r8d, 4
0x180012533  mov     rcx, rbx
0x180012536  call    getSampleRate
0x18001253b  mov     [rsi+4C4h], eax
0x180012541  dec     eax
0x180012543  cmp     eax, 176FFh
0x180012548  ja      loc_180012487
0x18001254e  cmp     dword ptr [rsi+4C0h], 16h
0x180012555  jnz     short loc_18001256A
0x180012557  mov     edx, 4
0x18001255c  mov     rcx, rbx
0x18001255f  call    CDKreadBits
0x180012564  mov     [rsi+4D1h], al
0x18001256a  mov     rcx, rbx
0x18001256d  call    CDKsyncCache_0
0x180012572  jmp     loc_1800122FC
```
