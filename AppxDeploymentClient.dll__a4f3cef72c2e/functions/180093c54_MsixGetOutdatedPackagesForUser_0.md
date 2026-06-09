# MsixGetOutdatedPackagesForUser_0

- ea: `0x180093c54`
- end: `0x180094085`
- name: `MsixGetOutdatedPackagesForUser_0`
- size: `1073`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update`

## callers

- `0x18008f960`

## callees

- `0x180005cdc`
- `0x180006c5c`
- `0x180008a1c`
- `0x180014460`
- `0x180018f80`
- `0x180023ae0`
- `0x180027680`
- `0x180039028`
- `0x180051870`
- `0x180051ca0`
- `0x1800522e8`
- `0x180087d3c`
- `0x1800927cc`
- `0x1800928a8`
- `0x180092adc`
- `0x180092f2c`
- `0x180092f94`
- `0x1800938c8`
- `0x180093c54`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180093d93`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180093ffd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009403e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180093d93`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180093ffd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009403e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180093ccc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180094012`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180094053`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180093ccc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180094012`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180094053`

## pseudocode

```c
__int64 __fastcall MsixGetOutdatedPackagesForUser_0(__int64 a1, __int64 a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rcx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rdx
  unsigned __int64 v16; // r14
  unsigned __int64 v17; // rbx
  __int64 v18; // r15
  _QWORD *v19; // rdi
  __int64 v20; // rsi
  int v21; // edi
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  char v29; // [rsp+30h] [rbp-D0h] BYREF
  bool v30[7]; // [rsp+31h] [rbp-CFh] BYREF
  __int64 v31; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v32; // [rsp+40h] [rbp-C0h] BYREF
  int v33; // [rsp+48h] [rbp-B8h]
  __int64 v34; // [rsp+50h] [rbp-B0h]
  _QWORD v35[2]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v36; // [rsp+68h] [rbp-98h]
  char v37; // [rsp+70h] [rbp-90h]
  _OWORD v38[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v39; // [rsp+98h] [rbp-68h]
  __int128 v40; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v41; // [rsp+B0h] [rbp-50h]
  __int128 v42; // [rsp+B8h] [rbp-48h]
  __int64 v43; // [rsp+C8h] [rbp-38h]
  __int64 v44; // [rsp+D0h] [rbp-30h]
  __int64 v45; // [rsp+D8h] [rbp-28h]
  __int128 v46; // [rsp+E0h] [rbp-20h]
  int v47; // [rsp+F0h] [rbp-10h]
  __int64 v48; // [rsp+F8h] [rbp-8h]
  __int64 v49; // [rsp+100h] [rbp+0h]
  _BYTE v50[144]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v51[12]; // [rsp+1A0h] [rbp+A0h] BYREF
  void *retaddr; // [rsp+248h] [rbp+148h]

  v31 = 0;
  v4 = sub_180023AE0(&v31);
  if ( v4 < 0 )
  {
    v5 = 318;
LABEL_3:
    sub_180008A1C(
      retaddr,
      v5,
      "onecore\\admin\\appmodel\\packagemanager\\client\\outdatedpackagesfinder.cpp",
      (unsigned int)v4);
LABEL_4:
    v8 = v31;
    v31 = 0;
    if ( v8 )
      SRCacheManager_Close(v8, v6, v7);
    return (unsigned int)v4;
  }
  memset(v51, 0, 76);
  v51[10] = 0;
  v29 = 0;
  v4 = sub_180005CDC(&v31, a1, 0, v51, &v29);
  if ( v4 < 0 )
  {
    v5 = 322;
    goto LABEL_3;
  }
  if ( v29 )
  {
    v32 = 0;
    v33 = 0;
    v34 = 0;
    v4 = sub_180092F2C(&v31, v51[0], &v32);
    if ( v4 < 0 )
    {
      v12 = 332;
LABEL_12:
      sub_180008A1C(
        retaddr,
        v12,
        "onecore\\admin\\appmodel\\packagemanager\\client\\outdatedpackagesfinder.cpp",
        (unsigned int)v4);
      goto LABEL_13;
    }
    v39 = 0;
    v29 = 0;
    memset(v38, 0, sizeof(v38));
    v4 = sub_180092F94(&v32, 1, v38, &v29);
    if ( v4 < 0 )
    {
      v12 = 336;
      goto LABEL_12;
    }
    sub_1800927CC(v50, a1);
    if ( v29 )
    {
      while ( 1 )
      {
        v41 = 0;
        v40 = 0;
        v42 = 0;
        v43 = 0;
        v44 = 0;
        v45 = 0;
        v46 = 0;
        v47 = 0;
        v48 = 0;
        v49 = 0;
        v30[0] = 0;
        v4 = sub_180018F80(&v31, *((__int64 *)&v38[0] + 1), 47, (__int64 *)&v40, v30);
        if ( v4 < 0 )
          break;
        if ( v30[0] )
        {
          v30[0] = 0;
          v4 = sub_180092ADC(v50, &v40, 0, v30);
          if ( v4 < 0 )
          {
            v15 = 353;
            goto LABEL_28;
          }
        }
        ++v33;
        v4 = sub_180092F94(&v32, 1, v38, &v29);
        if ( v4 < 0 )
        {
          v15 = 356;
          goto LABEL_28;
        }
        sub_180006C5C(&v40);
        if ( !v29 )
          goto LABEL_23;
      }
      v15 = 349;
LABEL_28:
      sub_180008A1C(
        retaddr,
        v15,
        "onecore\\admin\\appmodel\\packagemanager\\client\\outdatedpackagesfinder.cpp",
        (unsigned int)v4);
      sub_180006C5C(&v40);
      goto LABEL_29;
    }
LABEL_23:
    v35[0] = 0;
    v35[1] = 0;
    v36 = 0;
    v37 = 1;
    v14 = sub_1800938C8(v50, v35);
    v4 = v14;
    if ( v14 < 0 )
    {
      sub_180008A1C(
        retaddr,
        360,
        "onecore\\admin\\appmodel\\packagemanager\\client\\outdatedpackagesfinder.cpp",
        (unsigned int)v14);
      sub_180039028(v35);
LABEL_29:
      sub_1800928A8(v50);
LABEL_13:
      v13 = v32;
      v32 = 0;
      if ( v13 )
        SRCacheContext_Close(v13);
      goto LABEL_4;
    }
    v16 = v36;
    v17 = 0;
    v18 = v35[0];
    while ( v17 != v16 )
    {
      if ( v17 < v16 )
      {
        _mm_lfence();
        v19 = *(_QWORD **)(v18 + 8 * v17);
      }
      else
      {
        v19 = 0;
      }
      v20 = sub_180051CA0(24);
      *(_QWORD *)(v20 + 16) = 0;
      *(_OWORD *)v20 = 0;
      v21 = sub_180014460(v20, *v19);
      if ( v21 < 0 )
      {
        v22 = 366;
        goto LABEL_40;
      }
      v21 = sub_180027680(a2, v20);
      if ( v21 < 0 )
      {
        v22 = 367;
LABEL_40:
        sub_180008A1C(
          retaddr,
          v22,
          "onecore\\admin\\appmodel\\packagemanager\\client\\outdatedpackagesfinder.cpp",
          (unsigned int)v21);
        sub_180087D3C(v20, 1);
        sub_180039028(v35);
        sub_1800928A8(v50);
        v25 = v32;
        v32 = 0;
        if ( v25 )
          SRCacheContext_Close(v25);
        v26 = v31;
        v31 = 0;
        if ( v26 )
          SRCacheManager_Close(v26, v23, v24);
        return (unsigned int)v21;
      }
      ++v17;
    }
    sub_180039028(v35);
    sub_1800928A8(v50);
    v27 = v32;
    v32 = 0;
    if ( v27 )
      SRCacheContext_Close(v27);
  }
  v28 = v31;
  v31 = 0;
  if ( v28 )
    SRCacheManager_Close(v28, v10, v11);
  return 0;
}

```

## disassembly

```asm
0x180093c54  mov     [rsp-8+arg_10], rbx
0x180093c59  push    rbp
0x180093c5a  push    rsi
0x180093c5b  push    rdi
0x180093c5c  push    r12
0x180093c5e  push    r13
0x180093c60  push    r14
0x180093c62  push    r15
0x180093c64  lea     rbp, [rsp-110h]
0x180093c6c  sub     rsp, 210h
0x180093c73  mov     rax, cs:__security_cookie
0x180093c7a  xor     rax, rsp
0x180093c7d  mov     [rbp+140h+var_40], rax
0x180093c84  mov     rdi, rcx
0x180093c87  xor     r13d, r13d
0x180093c8a  lea     rcx, [rsp+240h+var_208]
0x180093c8f  mov     [rsp+240h+var_208], r13
0x180093c94  mov     r12, rdx
0x180093c97  call    sub_180023AE0
0x180093c9c  mov     ebx, eax
0x180093c9e  test    eax, eax
0x180093ca0  jns     short loc_180093CD9
0x180093ca2  mov     edx, 13Eh
0x180093ca7  mov     rcx, [rbp+148h]
0x180093cae  lea     r8, aOnecoreAdminAp_57; "onecore\\admin\\appmodel\\packagemanage"...
0x180093cb5  mov     r9d, ebx
0x180093cb8  call    sub_180008A1C
0x180093cbd  mov     rcx, [rsp+240h+var_208]
0x180093cc2  mov     [rsp+240h+var_208], r13
0x180093cc7  test    rcx, rcx
0x180093cca  jz      short loc_180093CD2
0x180093ccc  call    cs:SRCacheManager_Close
0x180093cd2  mov     eax, ebx
0x180093cd4  jmp     loc_18009405B
0x180093cd9  xor     edx, edx; Val
0x180093cdb  mov     [rbp+140h+var_A0], r13
0x180093ce2  lea     rcx, [rbp+140h+var_98]; void *
0x180093ce9  lea     r8d, [rdx+44h]; Size
0x180093ced  call    memset
0x180093cf2  lea     rax, [rsp+240h+var_210]
0x180093cf7  mov     [rbp+140h+var_50], r13
0x180093cfe  lea     r9, [rbp+140h+var_A0]
0x180093d05  mov     [rsp+240h+var_220], rax
0x180093d0a  xor     r8d, r8d
0x180093d0d  mov     [rsp+240h+var_210], r13b
0x180093d12  mov     rdx, rdi
0x180093d15  lea     rcx, [rsp+240h+var_208]
0x180093d1a  call    sub_180005CDC
0x180093d1f  mov     ebx, eax
0x180093d21  test    eax, eax
0x180093d23  jns     short loc_180093D2F
0x180093d25  mov     edx, 142h
0x180093d2a  jmp     loc_180093CA7
0x180093d2f  cmp     [rsp+240h+var_210], r13b
0x180093d34  jz      loc_180094044
0x180093d3a  mov     rdx, [rbp+140h+var_A0]
0x180093d41  lea     r8, [rsp+240h+var_200]
0x180093d46  lea     rcx, [rsp+240h+var_208]
0x180093d4b  mov     [rsp+240h+var_200], r13
0x180093d50  mov     [rsp+240h+var_1F8], r13d
0x180093d55  mov     [rsp+240h+var_1F0], r13
0x180093d5a  call    sub_180092F2C
0x180093d5f  mov     ebx, eax
0x180093d61  test    eax, eax
0x180093d63  jns     short loc_180093D9E
0x180093d65  mov     edx, 14Ch
0x180093d6a  mov     rcx, [rbp+148h]
0x180093d71  lea     r8, aOnecoreAdminAp_57; "onecore\\admin\\appmodel\\packagemanage"...
0x180093d78  mov     r9d, ebx
0x180093d7b  call    sub_180008A1C
0x180093d80  mov     rcx, [rsp+240h+var_200]
0x180093d85  mov     [rsp+240h+var_200], r13
0x180093d8a  test    rcx, rcx
0x180093d8d  jz      loc_180093CBD
0x180093d93  call    cs:SRCacheContext_Close
0x180093d99  jmp     loc_180093CBD
0x180093d9e  xorps   xmm0, xmm0
0x180093da1  mov     [rbp+140h+var_1A8], r13
0x180093da5  xorps   xmm1, xmm1
0x180093da8  mov     [rsp+240h+var_210], r13b
0x180093dad  mov     esi, 1
0x180093db2  lea     r9, [rsp+240h+var_210]
0x180093db7  mov     edx, esi
0x180093db9  lea     r8, [rsp+240h+var_1C8]
0x180093dbe  lea     rcx, [rsp+240h+var_200]
0x180093dc3  movdqu  [rsp+240h+var_1C8], xmm0
0x180093dc9  movdqu  [rbp+140h+var_1B8], xmm1
0x180093dce  call    sub_180092F94
0x180093dd3  mov     ebx, eax
0x180093dd5  test    eax, eax
0x180093dd7  jns     short loc_180093DE0
0x180093dd9  mov     edx, 150h
0x180093dde  jmp     short loc_180093D6A
0x180093de0  mov     rdx, rdi
0x180093de3  lea     rcx, [rbp+140h+var_130]
0x180093de7  call    sub_1800927CC
0x180093dec  cmp     [rsp+240h+var_210], r13b
0x180093df1  jz      loc_180093EBB
0x180093df7  lea     rdi, [rbp+140h+var_188]
0x180093dfb  mov     rdx, qword ptr [rbp+140h+var_1C8+8]
0x180093dff  lea     rax, [rsp+240h+var_20F]
0x180093e04  xorps   xmm0, xmm0
0x180093e07  mov     [rbp+140h+var_190], r13
0x180093e0b  xorps   xmm1, xmm1
0x180093e0e  movdqa  [rbp+140h+var_1A0], xmm0
0x180093e13  movups  xmmword ptr [rdi], xmm1
0x180093e16  lea     r9, [rbp+140h+var_1A0]
0x180093e1a  mov     [rbp+140h+var_178], r13
0x180093e1e  mov     r8d, 2Fh ; '/'
0x180093e24  mov     [rbp+140h+var_170], r13
0x180093e28  lea     rcx, [rsp+240h+var_208]
0x180093e2d  mov     [rbp+140h+var_168], r13
0x180093e31  movdqa  [rbp+140h+var_160], xmm0
0x180093e36  mov     [rbp+140h+var_150], r13d
0x180093e3a  mov     [rbp+140h+var_148], r13
0x180093e3e  mov     [rbp+140h+var_140], r13
0x180093e42  mov     [rsp+240h+var_20F], r13b
0x180093e47  mov     [rsp+240h+var_220], rax
0x180093e4c  call    sub_180018F80
0x180093e51  mov     ebx, eax
0x180093e53  test    eax, eax
0x180093e55  js      loc_180093F18
0x180093e5b  cmp     [rsp+240h+var_20F], r13b
0x180093e60  jz      short loc_180093E86
0x180093e62  lea     r9, [rsp+240h+var_20F]
0x180093e67  mov     [rsp+240h+var_20F], r13b
0x180093e6c  xor     r8d, r8d
0x180093e6f  lea     rdx, [rbp+140h+var_1A0]
0x180093e73  lea     rcx, [rbp+140h+var_130]
0x180093e77  call    sub_180092ADC
0x180093e7c  mov     ebx, eax
0x180093e7e  test    eax, eax
0x180093e80  js      loc_180093F0A
0x180093e86  add     [rsp+240h+var_1F8], esi
0x180093e8a  lea     r9, [rsp+240h+var_210]
0x180093e8f  lea     r8, [rsp+240h+var_1C8]
0x180093e94  mov     rdx, rsi
0x180093e97  lea     rcx, [rsp+240h+var_200]
0x180093e9c  call    sub_180092F94
0x180093ea1  mov     ebx, eax
0x180093ea3  test    eax, eax
0x180093ea5  js      short loc_180093F11
0x180093ea7  lea     rcx, [rbp+140h+var_1A0]
0x180093eab  call    sub_180006C5C
0x180093eb0  cmp     [rsp+240h+var_210], r13b
0x180093eb5  jnz     loc_180093DFB
0x180093ebb  lea     rdx, [rsp+240h+var_1E8]
0x180093ec0  mov     [rsp+240h+var_1E8], r13
0x180093ec5  lea     rcx, [rbp+140h+var_130]
0x180093ec9  mov     [rsp+240h+var_1E0], r13
0x180093ece  mov     [rsp+240h+var_1D8], r13
0x180093ed3  mov     [rsp+240h+var_1D0], sil
0x180093ed8  call    sub_1800938C8
0x180093edd  mov     ebx, eax
0x180093edf  test    eax, eax
0x180093ee1  jns     short loc_180093F4A
0x180093ee3  mov     rcx, [rbp+148h]
0x180093eea  lea     r8, aOnecoreAdminAp_57; "onecore\\admin\\appmodel\\packagemanage"...
0x180093ef1  mov     r9d, eax
0x180093ef4  mov     edx, 168h
0x180093ef9  call    sub_180008A1C
0x180093efe  lea     rcx, [rsp+240h+var_1E8]
0x180093f03  call    sub_180039028
0x180093f08  jmp     short loc_180093F3C
0x180093f0a  mov     edx, 161h
0x180093f0f  jmp     short loc_180093F1D
0x180093f11  mov     edx, 164h
0x180093f16  jmp     short loc_180093F1D
0x180093f18  mov     edx, 15Dh
0x180093f1d  mov     rcx, [rbp+148h]
0x180093f24  lea     r8, aOnecoreAdminAp_57; "onecore\\admin\\appmodel\\packagemanage"...
0x180093f2b  mov     r9d, ebx
0x180093f2e  call    sub_180008A1C
0x180093f33  lea     rcx, [rbp+140h+var_1A0]
0x180093f37  call    sub_180006C5C
0x180093f3c  lea     rcx, [rbp+140h+var_130]
0x180093f40  call    sub_1800928A8
0x180093f45  jmp     loc_180093D80
0x180093f4a  mov     r14, [rsp+240h+var_1D8]
0x180093f4f  mov     rbx, r13
0x180093f52  mov     r15, [rsp+240h+var_1E8]
0x180093f57  cmp     rbx, r14
0x180093f5a  jz      loc_18009401C
0x180093f60  jb      short loc_180093F67
0x180093f62  mov     rdi, r13
0x180093f65  jmp     short loc_180093F6E
0x180093f67  lfence
0x180093f6a  mov     rdi, [r15+rbx*8]
0x180093f6e  mov     ecx, 18h
0x180093f73  call    sub_180051CA0
0x180093f78  xorps   xmm0, xmm0
0x180093f7b  mov     rcx, rax
0x180093f7e  mov     rsi, rax
0x180093f81  mov     [rax+10h], r13
0x180093f85  movups  xmmword ptr [rax], xmm0
0x180093f88  mov     rdx, [rdi]
0x180093f8b  call    sub_180014460
0x180093f90  mov     edi, eax
0x180093f92  test    eax, eax
0x180093f94  js      short loc_180093FB3
0x180093f96  mov     rdx, rsi
0x180093f99  mov     rcx, r12
0x180093f9c  call    sub_180027680
0x180093fa1  mov     edi, eax
0x180093fa3  test    eax, eax
0x180093fa5  js      short loc_180093FAC
0x180093fa7  inc     rbx
0x180093faa  jmp     short loc_180093F57
0x180093fac  mov     edx, 16Fh
0x180093fb1  jmp     short loc_180093FB8
0x180093fb3  mov     edx, 16Eh
0x180093fb8  mov     rcx, [rbp+148h]
0x180093fbf  lea     r8, aOnecoreAdminAp_57; "onecore\\admin\\appmodel\\packagemanage"...
0x180093fc6  mov     r9d, edi
0x180093fc9  call    sub_180008A1C
0x180093fce  mov     edx, 1
0x180093fd3  mov     rcx, rsi
0x180093fd6  call    sub_180087D3C
0x180093fdb  lea     rcx, [rsp+240h+var_1E8]
0x180093fe0  call    sub_180039028
0x180093fe5  lea     rcx, [rbp+140h+var_130]
0x180093fe9  call    sub_1800928A8
0x180093fee  mov     rcx, [rsp+240h+var_200]
0x180093ff3  mov     [rsp+240h+var_200], r13
0x180093ff8  test    rcx, rcx
0x180093ffb  jz      short loc_180094003
0x180093ffd  call    cs:SRCacheContext_Close
0x180094003  mov     rcx, [rsp+240h+var_208]
0x180094008  mov     [rsp+240h+var_208], r13
0x18009400d  test    rcx, rcx
0x180094010  jz      short loc_180094018
0x180094012  call    cs:SRCacheManager_Close
0x180094018  mov     eax, edi
0x18009401a  jmp     short loc_18009405B
0x18009401c  lea     rcx, [rsp+240h+var_1E8]
0x180094021  call    sub_180039028
0x180094026  lea     rcx, [rbp+140h+var_130]
0x18009402a  call    sub_1800928A8
0x18009402f  mov     rcx, [rsp+240h+var_200]
0x180094034  mov     [rsp+240h+var_200], r13
0x180094039  test    rcx, rcx
0x18009403c  jz      short loc_180094044
0x18009403e  call    cs:SRCacheContext_Close
0x180094044  mov     rcx, [rsp+240h+var_208]
0x180094049  mov     [rsp+240h+var_208], r13
0x18009404e  test    rcx, rcx
0x180094051  jz      short loc_180094059
0x180094053  call    cs:SRCacheManager_Close
0x180094059  xor     eax, eax
0x18009405b  mov     rcx, [rbp+140h+var_40]
0x180094062  xor     rcx, rsp; StackCookie
0x180094065  call    __security_check_cookie
0x18009406a  mov     rbx, [rsp+240h+arg_10]
0x180094072  add     rsp, 210h
0x180094079  pop     r15
0x18009407b  pop     r14
0x18009407d  pop     r13
0x18009407f  pop     r12
0x180094081  pop     rdi
0x180094082  pop     rsi
0x180094083  pop     rbp
0x180094084  retn
```
