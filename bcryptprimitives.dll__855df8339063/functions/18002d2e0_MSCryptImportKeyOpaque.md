# MSCryptImportKeyOpaque

- ea: `0x18002d2e0`
- end: `0x18002d7f5`
- name: `MSCryptImportKeyOpaque`
- size: `1301`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, void *Src, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002cd40`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x18002d2e0`
- `0x18002d800`
- `0x18002e680`
- `0x1800495b0`
- `0x180063170`
- `0x180063180`

## string_xrefs

- `0x18002d577`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\opaqueblob.c`
- `0x18002d5bf`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\opaqueblob.c`
- `0x18002d61e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\opaqueblob.c`
- `0x18002d66d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\opaqueblob.c`
- `0x180081d97`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\opaqueblob.c`
- `0x180081dd7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\opaqueblob.c`

## pseudocode

```c
__int64 __fastcall MSCryptImportKeyOpaque(__int64 a1, _QWORD *a2, __int64 a3, int a4, _DWORD *Src, unsigned int a6)
{
  int v7; // edx
  int v8; // r8d
  __int64 v9; // r13
  unsigned int v10; // ecx
  int v11; // edi
  unsigned int v12; // eax
  int v13; // edx
  int v14; // r8d
  unsigned int v15; // ecx
  unsigned int v16; // r12d
  unsigned int v17; // r8d
  unsigned int v18; // ebx
  int v19; // eax
  int *v20; // rcx
  __int64 v21; // rdi
  unsigned int SymmetricKey; // esi
  int v23; // r8d
  int v24; // eax
  __int64 v26; // r9
  int v27; // edi
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // r9d
  __int64 v32; // r8
  char *v33; // rbx
  size_t Size; // [rsp+28h] [rbp-D8h]
  bool v35; // [rsp+40h] [rbp-C0h]
  int v36[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v37; // [rsp+50h] [rbp-B0h]
  unsigned int v38; // [rsp+54h] [rbp-ACh]
  int v39[2]; // [rsp+58h] [rbp-A8h]
  _QWORD *v40; // [rsp+60h] [rbp-A0h]
  __int64 v41; // [rsp+70h] [rbp-90h] BYREF
  int v42; // [rsp+78h] [rbp-88h]
  unsigned int v43; // [rsp+7Ch] [rbp-84h]
  int v44; // [rsp+80h] [rbp-80h]
  int v45; // [rsp+84h] [rbp-7Ch]
  unsigned int v46; // [rsp+88h] [rbp-78h]
  int v47; // [rsp+8Ch] [rbp-74h] BYREF
  char v48; // [rsp+90h] [rbp-70h] BYREF
  char v49; // [rsp+D0h] [rbp-30h] BYREF
  char v50; // [rsp+190h] [rbp+90h] BYREF

  *(_QWORD *)v39 = a3;
  v40 = a2;
  v37 = a4;
  memset_0(&v47, 0, 0x214u);
  v9 = 0;
  *(_QWORD *)v36 = 0;
  if ( a6 < 0x1C )
  {
    SymmetricKey = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        v8,
        (unsigned int)"status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\opaqueblob.c",
        13);
  }
  else
  {
    v10 = Src[6];
    v41 = *(_QWORD *)Src;
    v42 = Src[2];
    v43 = Src[3];
    v11 = *(_DWORD *)(a1 + 8);
    v44 = Src[4];
    v45 = Src[5];
    v35 = 0;
    v46 = v10;
    if ( v11 != 65538 )
    {
      switch ( v11 )
      {
        case 65537:
          v12 = 552;
          if ( v10 <= 0x40 )
            v12 = 360;
          v35 = v10 > 0x40;
          goto LABEL_4;
        case 65539:
          v12 = 172;
          goto LABEL_4;
        case 65540:
          v12 = 204;
          goto LABEL_4;
        case 65541:
          v12 = 444;
          goto LABEL_4;
        case 65542:
          v12 = 436;
          goto LABEL_4;
        case 65543:
          v12 = 312;
          goto LABEL_4;
        case 65544:
          v12 = 92;
          goto LABEL_4;
        case 65545:
          v12 = 60;
          goto LABEL_4;
        default:
          return (unsigned int)-1073741595;
      }
    }
    v12 = 560;
LABEL_4:
    if ( a6 != v12 )
    {
      v26 = 299;
      goto LABEL_78;
    }
    memcpy_0(&v41, Src, v12);
    if ( v41 == (a6 | 0x4D53534B00000000LL) && v42 == v11 )
    {
      v15 = *(_DWORD *)(a1 + 16);
      if ( v44 == v15 )
      {
        v16 = v43;
        v17 = HIBYTE(v43) + 1;
        v18 = v43 & 0xFFFFFF;
        v38 = v17;
        if ( v11 != 65544 )
        {
          if ( v18 < 6 )
          {
            if ( v18 == 3 )
            {
              if ( v17 <= v15 )
                goto LABEL_12;
            }
            else if ( !HIBYTE(v43) )
            {
LABEL_12:
              if ( !v18 || (v19 = qword_180084120[14 * (unsigned int)(unsigned __int16)v11 - 14], _bittest(&v19, v18)) )
              {
                if ( v11 == 65543 )
                {
                  SymmetricKey = 0;
                  v20 = (int *)&v48;
                  v27 = 6;
                  goto LABEL_79;
                }
LABEL_15:
                v20 = &v47;
                if ( v11 == 65545 )
                {
LABEL_16:
                  v21 = *(_QWORD *)v39;
                  LODWORD(Size) = v46;
                  SymmetricKey = MSCryptGenerateSymmetricKey(a1, (int)v36, v39[0], v37, v20, Size, 128);
                  if ( (SymmetricKey & 0x80000000) != 0 )
                  {
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      WPP_SF_sDsd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        v13,
                        v23,
                        (unsigned int)"status",
                        SymmetricKey,
                        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\opaqueblob.c",
                        123);
                    }
                    v9 = *(_QWORD *)v36;
                  }
                  else
                  {
                    v16 = v43;
                    v9 = *(_QWORD *)v36;
                    v17 = v38;
LABEL_18:
                    *(_DWORD *)(v21 + 12) = v18;
                    if ( v18 == 3 )
                      *(_DWORD *)(v21 + 20) = v17;
                    v24 = *(_DWORD *)(a1 + 8);
                    if ( v24 == 65543
                      || (v28 = v24 - 65538) == 0
                      || (v29 = v28 - 1) == 0
                      || (v30 = v29 - 1) == 0
                      || (unsigned int)(v30 - 1) <= 1 )
                    {
                      memcpy_0(
                        (void *)(v21 + 40),
                        (char *)&v41 + a6 - (unsigned __int64)*(unsigned int *)(v21 + 16),
                        *(unsigned int *)(v21 + 16));
                    }
                    if ( *(_DWORD *)(a1 + 8) == 65537 )
                    {
                      v33 = &v49;
                      if ( v35 )
                        v33 = &v50;
                      memcpy_0((void *)(v21 + 320), v33, 0x100u);
                      *(_BYTE *)(v21 + 576) = v33[256];
                      *(_BYTE *)(v21 + 577) = v33[257];
                      goto LABEL_26;
                    }
                    if ( *(_DWORD *)(a1 + 8) != 65543 )
                    {
                      if ( *(_DWORD *)(a1 + 8) == 65544 )
                      {
                        *(_DWORD *)(v21 + 12) = 0;
                        *(_DWORD *)(v21 + 20) = v16;
                      }
                      goto LABEL_26;
                    }
                    v31 = v47;
                    if ( (unsigned int)(v47 - 16) <= 0x3F0 && v47 == v45 )
                    {
                      v32 = *(unsigned int *)(v21 + 56);
                      *(_DWORD *)(v21 + 336) = v47;
                      *(_DWORD *)(v21 + 24) = v31;
                      if ( !(unsigned int)SymCryptRc2ExpandKeyEx(v21 + 192, v21 + 60, v32) )
                      {
LABEL_26:
                        if ( *(_DWORD *)(v21 + 24) == v45 )
                        {
                          *v40 = v9;
                          return SymmetricKey;
                        }
                        SymmetricKey = -1073741811;
                        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                        {
                          WPP_SF_sDsd(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            v13,
                            v17,
                            (unsigned int)"status",
                            13,
                            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\opaqueblob.c",
                            231);
                        }
                        goto LABEL_33;
                      }
                      SymmetricKey = -1073741811;
                    }
                    else
                    {
                      SymmetricKey = -1073741811;
                      DebugTraceError(
                        3221225485LL,
                        "status",
                        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\opaqueblob.c",
                        458);
                    }
                  }
LABEL_33:
                  if ( v9 )
                    MSCryptDestroyKey(v9);
                  return SymmetricKey;
                }
                SymmetricKey = 0;
                v27 = v11 - 65537;
LABEL_79:
                switch ( v27 )
                {
                  case 0:
                  case 1:
                  case 2:
                  case 3:
                  case 4:
                  case 5:
                  case 6:
                  case 7:
                    goto LABEL_16;
                  default:
                    v21 = *(_QWORD *)v39;
                    goto LABEL_18;
                }
              }
            }
          }
          SymmetricKey = -1073741811;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v13,
              v17,
              (unsigned int)"status",
              13,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\opaqueblob.c",
              89);
          return SymmetricKey;
        }
        v13 = v43 % v15;
        if ( !(v43 % v15) )
          goto LABEL_15;
        v26 = 330;
LABEL_78:
        SymmetricKey = -1073741811;
        DebugTraceError(
          3221225485LL,
          "status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\opaqueblob.c",
          v26);
        return SymmetricKey;
      }
    }
    SymmetricKey = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        v14,
        (unsigned int)"status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\opaqueblob.c",
        58);
  }
  return SymmetricKey;
}

```

## disassembly

```asm
0x18002d2e0  push    rbp
0x18002d2e2  push    rbx
0x18002d2e3  push    rsi
0x18002d2e4  push    r12
0x18002d2e6  push    r13
0x18002d2e8  push    r14
0x18002d2ea  push    r15
0x18002d2ec  lea     rbp, [rsp-1B0h]
0x18002d2f4  sub     rsp, 2B0h
0x18002d2fb  mov     rbx, [rbp+1E0h+Src]
0x18002d302  mov     r14, rcx
0x18002d305  mov     r15d, [rbp+1E0h+arg_28]
0x18002d30c  lea     rcx, [rbp+1E0h+var_258+4]; void *
0x18002d310  mov     qword ptr [rsp+2E0h+var_288], r8
0x18002d315  mov     r8d, 214h; Size
0x18002d31b  mov     [rsp+2E0h+var_280], rdx
0x18002d320  xor     edx, edx; Val
0x18002d322  mov     [rsp+2E0h+var_290], r9d
0x18002d327  call    memset_0
0x18002d32c  xor     r13d, r13d
0x18002d32f  mov     qword ptr [rsp+2E0h+var_298], r13
0x18002d334  cmp     r15d, 1Ch
0x18002d338  jb      loc_18002D643
0x18002d33e  mov     eax, [rbx]
0x18002d340  lea     rsi, cs:180000000h
0x18002d347  mov     ecx, [rbx+18h]
0x18002d34a  mov     dword ptr [rsp+2E0h+var_270], eax
0x18002d34e  mov     eax, [rbx+4]
0x18002d351  mov     dword ptr [rsp+2E0h+var_270+4], eax
0x18002d355  mov     eax, [rbx+8]
0x18002d358  mov     [rsp+2E0h+var_268], eax
0x18002d35c  mov     eax, [rbx+0Ch]
0x18002d35f  mov     [rsp+2E0h+var_264], eax
0x18002d363  mov     eax, [rbx+10h]
0x18002d366  mov     [rsp+2E0h+var_38], rdi
0x18002d36e  mov     edi, [r14+8]
0x18002d372  mov     [rbp+1E0h+var_260], eax
0x18002d375  mov     eax, [rbx+14h]
0x18002d378  mov     [rbp+1E0h+var_25C], eax
0x18002d37b  mov     [rsp+2E0h+var_2A0], r13b
0x18002d380  mov     dword ptr [rbp+1E0h+var_258], ecx
0x18002d383  cmp     edi, 10002h
0x18002d389  jnz     loc_180081D12
0x18002d38f  mov     eax, 230h
0x18002d394  cmp     r15d, eax
0x18002d397  jnz     loc_18002D6E8
0x18002d39d  mov     r8d, eax; Size
0x18002d3a0  lea     rcx, [rsp+2E0h+var_270]; void *
0x18002d3a5  mov     rdx, rbx; Src
0x18002d3a8  call    memcpy_0
0x18002d3ad  cmp     dword ptr [rsp+2E0h+var_270+4], 4D53534Bh
0x18002d3b5  jnz     loc_18002D69A
0x18002d3bb  cmp     dword ptr [rsp+2E0h+var_270], r15d
0x18002d3c0  jnz     loc_18002D69A
0x18002d3c6  cmp     [rsp+2E0h+var_268], edi
0x18002d3ca  jnz     loc_18002D69A
0x18002d3d0  mov     ecx, [r14+10h]
0x18002d3d4  cmp     [rbp+1E0h+var_260], ecx
0x18002d3d7  jnz     loc_18002D69A
0x18002d3dd  mov     r12d, [rsp+2E0h+var_264]
0x18002d3e2  mov     r8d, r12d
0x18002d3e5  shr     r8d, 18h
0x18002d3e9  mov     ebx, r12d
0x18002d3ec  inc     r8d
0x18002d3ef  and     ebx, 0FFFFFFh
0x18002d3f5  mov     [rsp+2E0h+var_28C], r8d
0x18002d3fa  cmp     edi, 10008h
0x18002d400  jz      loc_18002D559
0x18002d406  cmp     ebx, 6
0x18002d409  jnb     loc_18002D5EC
0x18002d40f  cmp     ebx, 3
0x18002d412  jz      loc_18002D6F3
0x18002d418  cmp     r8d, 1
0x18002d41c  jnz     loc_18002D5EC
0x18002d422  test    ebx, ebx
0x18002d424  jz      short loc_18002D43F
0x18002d426  movzx   eax, di
0x18002d429  dec     eax
0x18002d42b  imul    rax, 70h ; 'p'
0x18002d42f  mov     eax, [rax+rsi+84120h]
0x18002d436  bt      eax, ebx
0x18002d439  jnb     loc_18002D5EC
0x18002d43f  cmp     edi, 10007h
0x18002d445  jz      loc_18002D701
0x18002d44b  lea     rcx, [rbp+1E0h+var_258+4]
0x18002d44f  cmp     edi, 10009h
0x18002d455  jnz     loc_18002D6CD
0x18002d45b  mov     eax, dword ptr [rbp+1E0h+var_258]; jumptable 0000000180081DCB cases 65537-65544
0x18002d45e  lea     rdx, [rsp+2E0h+var_298]; int
0x18002d463  mov     rdi, qword ptr [rsp+2E0h+var_288]
0x18002d468  mov     r9d, [rsp+2E0h+var_290]; int
0x18002d46d  mov     r8, rdi; int
0x18002d470  mov     [rsp+2E0h+var_2B0], 80h; int
0x18002d478  mov     dword ptr [rsp+2E0h+Size], eax; Size
0x18002d47c  mov     [rsp+2E0h+var_2C0], rcx; Src
0x18002d481  mov     rcx, r14; int
0x18002d484  call    MSCryptGenerateSymmetricKey
0x18002d489  mov     esi, eax
0x18002d48b  test    eax, eax
0x18002d48d  js      loc_18002D52C
0x18002d493  mov     r12d, [rsp+2E0h+var_264]
0x18002d498  mov     r13, qword ptr [rsp+2E0h+var_298]
0x18002d49d  mov     r8d, [rsp+2E0h+var_28C]
0x18002d4a2  mov     [rdi+0Ch], ebx
0x18002d4a5  cmp     ebx, 3
0x18002d4a8  jz      loc_18002D712
0x18002d4ae  mov     eax, [r14+8]
0x18002d4b2  cmp     eax, 10007h
0x18002d4b7  jnz     loc_18002D71B
0x18002d4bd  mov     r8d, [rdi+10h]; Size
0x18002d4c1  lea     rdx, [rsp+2E0h+var_270]
0x18002d4c6  mov     rax, r15
0x18002d4c9  lea     rcx, [rdi+28h]; void *
0x18002d4cd  sub     rax, r8
0x18002d4d0  add     rdx, rax; Src
0x18002d4d3  call    memcpy_0
0x18002d4d8  mov     ecx, [r14+8]
0x18002d4dc  sub     ecx, 10001h
0x18002d4e2  jz      loc_18002D7AD
0x18002d4e8  sub     ecx, 6
0x18002d4eb  jz      loc_18002D75F
0x18002d4f1  cmp     ecx, 1
0x18002d4f4  jz      loc_18002D74F
0x18002d4fa  mov     eax, [rbp+1E0h+var_25C]
0x18002d4fd  cmp     [rdi+18h], eax
0x18002d500  jnz     loc_18002D59D
0x18002d506  mov     rax, [rsp+2E0h+var_280]
0x18002d50b  mov     [rax], r13
0x18002d50e  mov     rdi, [rsp+2E0h+var_38]
0x18002d516  mov     eax, esi
0x18002d518  add     rsp, 2B0h
0x18002d51f  pop     r15
0x18002d521  pop     r14
0x18002d523  pop     r13
0x18002d525  pop     r12
0x18002d527  pop     rsi
0x18002d528  pop     rbx
0x18002d529  pop     rbp
0x18002d52a  retn
0x18002d52c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d533  lea     rax, WPP_GLOBAL_Control
0x18002d53a  cmp     rcx, rax
0x18002d53d  jz      short loc_18002D545
0x18002d53f  test    byte ptr [rcx+1Ch], 1
0x18002d543  jnz     short loc_18002D573
0x18002d545  mov     r13, qword ptr [rsp+2E0h+var_298]
0x18002d54a  test    r13, r13
0x18002d54d  jz      short loc_18002D50E
0x18002d54f  mov     rcx, r13
0x18002d552  call    MSCryptDestroyKey
0x18002d557  jmp     short loc_18002D50E
0x18002d559  xor     edx, edx
0x18002d55b  mov     eax, r12d
0x18002d55e  div     ecx
0x18002d560  test    edx, edx
0x18002d562  jz      loc_18002D44B
0x18002d568  mov     r9d, 14Ah
0x18002d56e  jmp     loc_180081D97
0x18002d573  mov     rcx, [rcx+10h]
0x18002d577  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002d57e  mov     [rsp+2E0h+var_2B0], 17Bh
0x18002d586  lea     r9, aStatus_0; "status"
0x18002d58d  mov     [rsp+2E0h+Size], rax
0x18002d592  mov     dword ptr [rsp+2E0h+var_2C0], esi
0x18002d596  call    WPP_SF_sDsd
0x18002d59b  jmp     short loc_18002D545
0x18002d59d  mov     esi, 0C000000Dh
0x18002d5a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d5a9  lea     rax, WPP_GLOBAL_Control
0x18002d5b0  cmp     rcx, rax
0x18002d5b3  jz      short loc_18002D54A
0x18002d5b5  test    byte ptr [rcx+1Ch], 1
0x18002d5b9  jz      short loc_18002D54A
0x18002d5bb  mov     rcx, [rcx+10h]
0x18002d5bf  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002d5c6  mov     [rsp+2E0h+var_2B0], 1E7h
0x18002d5ce  lea     r9, aStatus_0; "status"
0x18002d5d5  mov     [rsp+2E0h+Size], rax
0x18002d5da  mov     dword ptr [rsp+2E0h+var_2C0], 0C000000Dh
0x18002d5e2  call    WPP_SF_sDsd
0x18002d5e7  jmp     loc_18002D54A
0x18002d5ec  mov     esi, 0C000000Dh
0x18002d5f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d5f8  lea     rax, WPP_GLOBAL_Control
0x18002d5ff  cmp     rcx, rax
0x18002d602  jz      loc_18002D50E
0x18002d608  test    byte ptr [rcx+1Ch], 1
0x18002d60c  jz      loc_18002D50E
0x18002d612  mov     [rsp+2E0h+var_2B0], 159h
0x18002d61a  mov     rcx, [rcx+10h]
0x18002d61e  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002d625  mov     [rsp+2E0h+Size], rax
0x18002d62a  lea     r9, aStatus_0; "status"
0x18002d631  mov     dword ptr [rsp+2E0h+var_2C0], 0C000000Dh
0x18002d639  call    WPP_SF_sDsd
0x18002d63e  jmp     loc_18002D50E
0x18002d643  mov     esi, 0C000000Dh
0x18002d648  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d64f  lea     rax, WPP_GLOBAL_Control
0x18002d656  cmp     rcx, rax
0x18002d659  jz      loc_18002D516
0x18002d65f  test    byte ptr [rcx+1Ch], 1
0x18002d663  jz      loc_18002D516
0x18002d669  mov     rcx, [rcx+10h]
0x18002d66d  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002d674  mov     [rsp+2E0h+var_2B0], 10Dh
0x18002d67c  lea     r9, aStatus_0; "status"
0x18002d683  mov     [rsp+2E0h+Size], rax
0x18002d688  mov     dword ptr [rsp+2E0h+var_2C0], 0C000000Dh
0x18002d690  call    WPP_SF_sDsd
0x18002d695  jmp     loc_18002D516
0x18002d69a  mov     esi, 0C000000Dh
0x18002d69f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d6a6  lea     rax, WPP_GLOBAL_Control
0x18002d6ad  cmp     rcx, rax
0x18002d6b0  jz      loc_18002D50E
0x18002d6b6  test    byte ptr [rcx+1Ch], 1
0x18002d6ba  jz      loc_18002D50E
0x18002d6c0  mov     [rsp+2E0h+var_2B0], 13Ah
0x18002d6c8  jmp     loc_18002D61A
0x18002d6cd  xor     esi, esi
0x18002d6cf  add     edi, 0FFFEFFFFh; switch 8 cases
0x18002d6d5  cmp     edi, 7
0x18002d6d8  jbe     loc_180081DBA
0x18002d6de  mov     rdi, qword ptr [rsp+2E0h+var_288]; jumptable 0000000180081DCB default case
0x18002d6e3  jmp     loc_18002D4A2
0x18002d6e8  mov     r9d, 12Bh
0x18002d6ee  jmp     loc_180081D97
0x18002d6f3  cmp     r8d, ecx
0x18002d6f6  ja      loc_18002D5EC
0x18002d6fc  jmp     loc_18002D422
0x18002d701  xor     esi, esi
0x18002d703  lea     rcx, [rbp+1E0h+var_250]
0x18002d707  add     edi, 0FFFEFFFFh
0x18002d70d  jmp     loc_180081DBA
0x18002d712  mov     [rdi+14h], r8d
0x18002d716  jmp     loc_18002D4AE
0x18002d71b  sub     eax, 10002h
0x18002d720  jz      loc_18002D4BD
0x18002d726  sub     eax, 1
0x18002d729  jz      loc_18002D4BD
0x18002d72f  sub     eax, 1
0x18002d732  jz      loc_18002D4BD
0x18002d738  sub     eax, 1
0x18002d73b  jz      loc_18002D4BD
0x18002d741  cmp     eax, 1
0x18002d744  jnz     loc_18002D4D8
0x18002d74a  jmp     loc_18002D4BD
0x18002d74f  mov     dword ptr [rdi+0Ch], 0
0x18002d756  mov     [rdi+14h], r12d
0x18002d75a  jmp     loc_18002D4FA
0x18002d75f  mov     r9d, dword ptr [rbp+1E0h+var_258+4]
0x18002d763  lea     eax, [r9-10h]
0x18002d767  cmp     eax, 3F0h
0x18002d76c  ja      loc_180081DD1
0x18002d772  cmp     r9d, [rbp+1E0h+var_25C]
0x18002d776  jnz     loc_180081DD1
0x18002d77c  mov     r8d, [rdi+38h]
0x18002d780  lea     rdx, [rdi+3Ch]
0x18002d784  lea     rcx, [rdi+0C0h]
0x18002d78b  mov     [rdi+150h], r9d
0x18002d792  mov     [rdi+18h], r9d
0x18002d796  call    SymCryptRc2ExpandKeyEx
0x18002d79b  test    eax, eax
0x18002d79d  jz      loc_18002D4FA
0x18002d7a3  mov     esi, 0C000000Dh
0x18002d7a8  jmp     loc_18002D54A
0x18002d7ad  cmp     [rsp+2E0h+var_2A0], 0
0x18002d7b2  lea     rax, [rbp+1E0h+var_150]
0x18002d7b9  lea     rbx, [rbp+1E0h+var_210]
0x18002d7bd  mov     r8d, 100h; Size
0x18002d7c3  cmovnz  rbx, rax
0x18002d7c7  lea     rcx, [rdi+140h]; void *
0x18002d7ce  mov     rdx, rbx; Src
0x18002d7d1  call    memcpy_0
0x18002d7d6  movzx   eax, byte ptr [rbx+100h]
0x18002d7dd  mov     [rdi+240h], al
0x18002d7e3  movzx   eax, byte ptr [rbx+101h]
0x18002d7ea  mov     [rdi+241h], al
0x18002d7f0  jmp     loc_18002D4FA
0x180081d12  lea     eax, [rdi-10001h]; switch 9 cases
0x180081d18  cmp     eax, 8
0x180081d1b  ja      short def_180081D27; jumptable 0000000180081D27 default case, case 65538
0x180081d1d  mov     eax, ds:(jpt_180081D27 - 180000000h)[rsi+rax*4]
0x180081d24  add     rax, rsi
0x180081d27  jmp     rax; switch jump
0x180081d2d  mov     eax, 0ACh; jumptable 0000000180081D27 case 65539
0x180081d32  jmp     loc_18002D394
0x180081d37  mov     eax, 0CCh; jumptable 0000000180081D27 case 65540
0x180081d3c  jmp     loc_18002D394
0x180081d41  mov     eax, 1BCh; jumptable 0000000180081D27 case 65541
0x180081d46  jmp     loc_18002D394
0x180081d4b  mov     eax, 1B4h; jumptable 0000000180081D27 case 65542
0x180081d50  jmp     loc_18002D394
0x180081d55  mov     eax, 138h; jumptable 0000000180081D27 case 65543
0x180081d5a  jmp     loc_18002D394
0x180081d5f  mov     eax, 5Ch ; '\'; jumptable 0000000180081D27 case 65544
0x180081d64  jmp     loc_18002D394
0x180081d69  mov     eax, 3Ch ; '<'; jumptable 0000000180081D27 case 65545
0x180081d6e  jmp     loc_18002D394
  ... truncated ...
```
