# sub_1800ED9BC

- ea: `0x1800ed9bc`
- end: `0x1800ee6be`
- name: `sub_1800ED9BC`
- size: `3330`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800ebe30`

## callees

- `0x180004678`
- `0x180007f5c`
- `0x180009628`
- `0x18000b710`
- `0x18000d9d4`
- `0x18000eeac`
- `0x1800102f8`
- `0x180010448`
- `0x180012208`
- `0x1800153c8`
- `0x180015a2c`
- `0x180015e7c`
- `0x180023770`
- `0x18002dc2c`
- `0x18002dff4`
- `0x180031598`
- `0x1800a7a44`
- `0x1800a7ae8`
- `0x1800e5e68`
- `0x1800e5fcc`
- `0x1800e6068`
- `0x1800ea758`
- `0x1800eae88`
- `0x1800ed9bc`
- `0x1800ee6c0`
- `0x1800f3b5c`
- `0x1800f4270`
- `0x18013b830`

## string_xrefs

- `0x1800eda70`: `../../../../third_party/wp.client/msinternal/src/browser/src/esp/urlrep/src/urlrep.cpp`
- `0x1800edc24`: `../../../../third_party/wp.client/msinternal/src/browser/src/esp/urlrep/src/urlrep.cpp`
- `0x1800edfbc`: `../../../../third_party/wp.client/msinternal/src/browser/src/esp/urlrep/src/urlrep.cpp`
- `0x1800ee199`: `../../../../third_party/wp.client/msinternal/src/browser/src/esp/urlrep/src/urlrep.cpp`
- `0x1800ee2bf`: `../../../../third_party/wp.client/msinternal/src/browser/src/esp/urlrep/src/urlrep.cpp`
- `0x1800ee4ca`: `../../../../third_party/wp.client/msinternal/src/browser/src/esp/urlrep/src/urlrep.cpp`
- `0x1800ee4f0`: `CacheFilter::Allow`
- `0x1800ee2e5`: `CacheFilter::Evaluate`
- `0x1800ee1bf`: `CacheFilter::CallServer`

## pseudocode

```c
__int64 __fastcall sub_1800ED9BC(__int64 a1, _QWORD *a2)
{
  char v4; // r14
  __int64 v5; // rax
  char v6; // r15
  __int64 v7; // rax
  __int64 v8; // rcx
  volatile signed __int32 *v9; // rbx
  char v10; // al
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 result; // rax
  volatile signed __int32 *v14; // rbx
  __int64 v15; // rbx
  __int64 v16; // rcx
  volatile signed __int32 *v17; // rbx
  __int64 v18; // rcx
  char v19; // r12
  volatile signed __int32 *v20; // rbx
  char *v21; // rax
  char v22; // bl
  __int64 v23; // rcx
  __int64 v24; // r14
  __int64 v25; // rbx
  __int64 v26; // r8
  __int64 v27; // rax
  __int64 v28; // rcx
  int v29; // eax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rbx
  _QWORD *v33; // rdx
  _QWORD *v34; // rdx
  _QWORD *v35; // rax
  __int64 v36; // rcx
  __int64 v37; // rax
  __int64 v38; // rbx
  _QWORD *v39; // rdx
  _QWORD *v40; // rdx
  _QWORD *v41; // rax
  signed __int32 v42; // eax
  bool v43; // zf
  signed __int32 v44; // eax
  __int16 v45; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v46; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v47; // [rsp+48h] [rbp-B8h]
  __int128 v48; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v49; // [rsp+68h] [rbp-98h]
  char v50; // [rsp+78h] [rbp-88h]
  __int128 v51; // [rsp+80h] [rbp-80h] BYREF
  __int128 v52; // [rsp+90h] [rbp-70h]
  _BYTE v53[8]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v54[16]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v55[40]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v56; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v57; // [rsp+E8h] [rbp-18h] BYREF
  volatile signed __int32 *v58; // [rsp+F0h] [rbp-10h]
  _BYTE v59[40]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v60[16]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v61[40]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v62[32]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v63[40]; // [rsp+178h] [rbp+78h] BYREF
  __int64 v64; // [rsp+1A0h] [rbp+A0h] BYREF
  volatile signed __int32 *v65; // [rsp+1A8h] [rbp+A8h]
  _QWORD v66[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v67; // [rsp+1C0h] [rbp+C0h]
  unsigned __int64 v68; // [rsp+1C8h] [rbp+C8h]
  int v69; // [rsp+1D0h] [rbp+D0h]
  _QWORD v70[2]; // [rsp+1D8h] [rbp+D8h] BYREF
  __int64 v71; // [rsp+1E8h] [rbp+E8h]
  unsigned __int64 v72; // [rsp+1F0h] [rbp+F0h]
  char v73; // [rsp+1F8h] [rbp+F8h]
  _BYTE v74[8]; // [rsp+200h] [rbp+100h] BYREF

  v4 = 0;
  LODWORD(v46) = 0;
  if ( qword_18021BF90 && *(_DWORD *)qword_18021BF90 )
  {
    v5 = sub_1800A7A44(*a2);
    sub_1800153C8(v53, "uri", v5);
    LODWORD(v46) = 0;
    sub_18000B710(&v56, &v46, &v45);
    sub_180015A2C(&v56, &v64, v53);
    v51 = 0;
    v52 = 0;
    sub_180004678(&v51, "../../../../third_party/wp.client/msinternal/src/browser/src/esp/urlrep/src/urlrep.cpp", 86);
    v48 = 0;
    v49 = 0;
    sub_180004678(&v48, "Lookup", 6);
    sub_180015E7C((unsigned int)&qword_18021BF90, (unsigned int)&v48, (unsigned int)&v51, 181, (__int64)&v56);
    sub_1800102F8(v59);
    sub_180010448(&v57);
    sub_1800F3B5C(v53, 64, 1, sub_18000D430);
  }
  sub_180012208(&v46);
  v6 = *(_BYTE *)(*(_QWORD *)(a1 + 24) + 130LL);
  v7 = a2[1];
  if ( v7 )
    _InterlockedIncrement((volatile signed __int32 *)(v7 + 8));
  v8 = *a2;
  v9 = (volatile signed __int32 *)a2[1];
  v56 = v46;
  if ( v9 )
    _InterlockedIncrement(v9 + 2);
  v57 = v8;
  v58 = v9;
  v59[0] = v6;
  v59[8] = 0;
  if ( v9 )
  {
    if ( !_InterlockedDecrement(v9 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( !_InterlockedDecrement(v9 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  v10 = sub_1800A7AE8(*a2);
  LOBYTE(v45) = v10;
  HIBYTE(v45) = 1;
  *(_WORD *)(*(_QWORD *)(*a2 + 368LL) + 25LL) = v45;
  if ( v10 )
  {
    v15 = *(_QWORD *)(*a2 + 368LL);
    v16 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 184LL);
    if ( v16 )
      sub_180031598(v16, &v64);
    else
      sub_180023770(&v64);
    LOBYTE(v45) = *(_BYTE *)(v64 + 8);
    HIBYTE(v45) = 1;
    *(_WORD *)(v15 + 27) = v45;
    v17 = v65;
    if ( v65 )
    {
      if ( _InterlockedExchangeAdd(v65 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
      }
    }
    if ( *(_BYTE *)(*a2 + 448LL) )
      goto LABEL_31;
    v18 = *(_QWORD *)(*(_QWORD *)(a1 + 24) + 184LL);
    if ( v18 )
      sub_180031598(v18, &v64);
    else
      sub_180023770(&v64);
    v4 = 1;
    v19 = 1;
    if ( *(_BYTE *)(v64 + 8) )
LABEL_31:
      v19 = 0;
    if ( (v4 & 1) != 0 )
    {
      v20 = v65;
      if ( v65 )
      {
        if ( _InterlockedExchangeAdd(v65 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
          if ( !_InterlockedDecrement(v20 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
        }
      }
    }
    if ( !v19 )
      goto LABEL_50;
    sub_180012208(&v64);
    v21 = (char *)sub_18002DC2C(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 184LL), v60, *a2, *a2 + 416LL);
    if ( v21[120] )
      v22 = *v21;
    else
      v22 = 0;
    if ( !v63[32] )
    {
      sub_180007F5C(v63);
      sub_180007F5C(v62);
      sub_180007F5C(v61);
    }
    v23 = *(_QWORD *)(*a2 + 368LL);
    LODWORD(v46) = 4;
    sub_1800E5E68(v23, &v46, &v64);
    v24 = *(_QWORD *)(*a2 + 368LL);
    if ( v22 )
      sub_1800E5FCC(*(_QWORD *)(*a2 + 368LL), 1);
    LOBYTE(v45) = v22;
    HIBYTE(v45) = 1;
    *(_WORD *)(v24 + 21) = v45;
    if ( v22 )
    {
      v25 = *(_QWORD *)(*a2 + 368LL);
      v48 = 0;
      v49 = 0;
      sub_180004678(&v48, &qword_180149390, 0);
      v50 = 1;
      LODWORD(v46) = 0;
      BYTE4(v46) = 1;
      sub_1800E6068(v25, 2, 0, 0, (__int64)&v48);
      if ( qword_18021BF90 && *(_DWORD *)qword_18021BF90 )
      {
        v27 = sub_1800A7A44(*a2);
        sub_1800153C8(v60, "uri", v27);
        LODWORD(v46) = 0;
        sub_18000B710(v53, &v46, &v45);
        sub_180015A2C(v53, &v46, v60);
        v48 = 0;
        v49 = 0;
        sub_180004678(
          &v48,
          "../../../../third_party/wp.client/msinternal/src/browser/src/esp/urlrep/src/urlrep.cpp",
          86);
        v51 = 0;
        v52 = 0;
        sub_180004678(&v51, "TopTrafficHit", 13);
        sub_180015E7C((unsigned int)&qword_18021BF90, (unsigned int)&v51, (unsigned int)&v48, 215, (__int64)v53);
        sub_1800102F8(v55);
        sub_180010448(v54);
        sub_1800F3B5C(v60, 64, 1, sub_18000D430);
      }
    }
    else
    {
LABEL_50:
      sub_180012208(v74);
      sub_18002DFF4(
        *(_QWORD *)(*(_QWORD *)(a1 + 24) + 184LL),
        (unsigned int)v66,
        *(_DWORD *)a2 + 376,
        *a2,
        *a2 + 416LL,
        *(_BYTE *)(*a2 + 257LL));
      v28 = *(_QWORD *)(*a2 + 368LL);
      LODWORD(v46) = 5;
      sub_1800E5E68(v28, &v46, v74);
      v29 = v69;
      if ( !v69 )
      {
        sub_1800E5FCC(*(_QWORD *)(*a2 + 368LL), 2);
        v29 = v69;
      }
      LOBYTE(v45) = v29 != 2;
      HIBYTE(v45) = 1;
      *(_WORD *)(*(_QWORD *)(*a2 + 368LL) + 23LL) = v45;
      sub_18000D9D4(*a2 + 384LL, v66);
      if ( v69 )
      {
        if ( v69 == 1 )
        {
          if ( qword_18021BF90 && *(_DWORD *)qword_18021BF90 )
          {
            v31 = sub_1800A7A44(*a2);
            sub_1800153C8(v60, "uri", v31);
            LODWORD(v46) = 0;
            sub_18000B710(v53, &v46, &v45);
            sub_180015A2C(v53, &v64, v60);
            v48 = 0;
            v49 = 0;
            sub_180004678(
              &v48,
              "../../../../third_party/wp.client/msinternal/src/browser/src/esp/urlrep/src/urlrep.cpp",
              86);
            v51 = 0;
            v52 = 0;
            sub_180004678(&v51, "CacheFilter::Evaluate", 21);
            sub_180015E7C((unsigned int)&qword_18021BF90, (unsigned int)&v51, (unsigned int)&v48, 249, (__int64)v53);
            sub_1800102F8(v55);
            sub_180010448(v54);
            sub_1800F3B5C(v60, 64, 1, sub_18000D430);
          }
          v32 = *(_QWORD *)(*a2 + 368LL);
          v48 = 0;
          v49 = 0;
          v33 = v66;
          if ( v68 > 0xF )
            v33 = (_QWORD *)v66[0];
          sub_180009628(&v48, v33, v67);
          v50 = 1;
          v46 = 0;
          v47 = 0;
          if ( v73 )
          {
            v34 = v70;
            if ( v72 > 0xF )
              v34 = (_QWORD *)v70[0];
            sub_180009628(&v46, v34, v71);
          }
          else
          {
            sub_180004678(&v46, &qword_180149390, 0);
          }
          v35 = (_QWORD *)sub_1800EA758(&v64, &v46);
          sub_1800E6068(v32, 3, 3, *v35, (__int64)&v48);
          sub_180007F5C(&v46);
          v36 = *(_QWORD *)(a1 + 56);
          if ( v36 )
            (*(void (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v36 + 8LL))(v36, a1 + 24, a2);
          if ( v73 )
            sub_180007F5C(v70);
        }
        else
        {
          if ( qword_18021BF90 && *(_DWORD *)qword_18021BF90 )
          {
            v30 = sub_1800A7A44(*a2);
            sub_1800153C8(v60, "uri", v30);
            LODWORD(v46) = 0;
            sub_18000B710(v53, &v46, &v45);
            sub_180015A2C(v53, &v64, v60);
            v48 = 0;
            v49 = 0;
            sub_180004678(
              &v48,
              "../../../../third_party/wp.client/msinternal/src/browser/src/esp/urlrep/src/urlrep.cpp",
              86);
            v51 = 0;
            v52 = 0;
            sub_180004678(&v51, "CacheFilter::CallServer", 23);
            sub_180015E7C((unsigned int)&qword_18021BF90, (unsigned int)&v51, (unsigned int)&v48, 262, (__int64)v53);
            sub_1800102F8(v55);
            sub_180010448(v54);
            sub_1800F3B5C(v60, 64, 1, sub_18000D430);
          }
          sub_1800EAE88(a1, a2);
          if ( v73 )
            sub_180007F5C(v70);
        }
      }
      else
      {
        if ( qword_18021BF90 && *(_DWORD *)qword_18021BF90 )
        {
          v37 = sub_1800A7A44(*a2);
          sub_1800153C8(v60, "uri", v37);
          LODWORD(v46) = 0;
          sub_18000B710(v53, &v46, &v45);
          sub_180015A2C(v53, &v64, v60);
          v48 = 0;
          v49 = 0;
          sub_180004678(
            &v48,
            "../../../../third_party/wp.client/msinternal/src/browser/src/esp/urlrep/src/urlrep.cpp",
            86);
          v51 = 0;
          v52 = 0;
          sub_180004678(&v51, "CacheFilter::Allow", 18);
          sub_180015E7C((unsigned int)&qword_18021BF90, (unsigned int)&v51, (unsigned int)&v48, 239, (__int64)v53);
          sub_1800102F8(v55);
          sub_180010448(v54);
          sub_1800F3B5C(v60, 64, 1, sub_18000D430);
        }
        v38 = *(_QWORD *)(*a2 + 368LL);
        v48 = 0;
        v49 = 0;
        v39 = v66;
        if ( v68 > 0xF )
          v39 = (_QWORD *)v66[0];
        sub_180009628(&v48, v39, v67);
        v50 = 1;
        v46 = 0;
        v47 = 0;
        if ( v73 )
        {
          v40 = v70;
          if ( v72 > 0xF )
            v40 = (_QWORD *)v70[0];
          sub_180009628(&v46, v40, v71);
        }
        else
        {
          sub_180004678(&v46, &qword_180149390, 0);
        }
        v41 = (_QWORD *)sub_1800EA758(&v64, &v46);
        sub_1800E6068(v38, 3, 0, *v41, (__int64)&v48);
        sub_180007F5C(&v46);
        if ( v73 )
          sub_180007F5C(v70);
      }
      sub_180007F5C(v66);
    }
    LOBYTE(v26) = v6;
    result = sub_1800EE6C0(&v56, &v57, v26);
    v14 = v58;
    if ( v58 )
    {
      v42 = _InterlockedExchangeAdd(v58 + 2, 0xFFFFFFFF);
      v43 = v42 == 1;
      result = (unsigned int)(v42 - 1);
      if ( v43 )
        goto LABEL_90;
    }
  }
  else
  {
    if ( qword_18021BF90 && *(_DWORD *)qword_18021BF90 )
    {
      v12 = sub_1800A7A44(*a2);
      sub_1800153C8(v60, "uri", v12);
      LODWORD(v46) = 0;
      sub_18000B710(v53, &v46, &v45);
      sub_180015A2C(v53, &v64, v60);
      v48 = 0;
      v49 = 0;
      sub_180004678(&v48, "../../../../third_party/wp.client/msinternal/src/browser/src/esp/urlrep/src/urlrep.cpp", 86);
      v51 = 0;
      v52 = 0;
      sub_180004678(&v51, "UnsupportedDestinationScheme", 28);
      sub_18000EEAC((unsigned int)&qword_18021BF90, (unsigned int)&v51, (unsigned int)&v48, 193, (__int64)v53);
      sub_1800102F8(v55);
      sub_180010448(v54);
      sub_1800F3B5C(v60, 64, 1, sub_18000D430);
    }
    LOBYTE(v11) = v6;
    result = sub_1800EE6C0(&v56, &v57, v11);
    v14 = v58;
    if ( v58 )
    {
      result = (unsigned int)_InterlockedDecrement(v58 + 2);
      if ( !(_DWORD)result )
      {
LABEL_90:
        (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
        v44 = _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF);
        v43 = v44 == 1;
        result = (unsigned int)(v44 - 1);
        if ( v43 )
          return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800ed9bc  mov     [rsp-8+arg_10], rbx
0x1800ed9c1  push    rbp
0x1800ed9c2  push    rsi
0x1800ed9c3  push    rdi
0x1800ed9c4  push    r12
0x1800ed9c6  push    r13
0x1800ed9c8  push    r14
0x1800ed9ca  push    r15
0x1800ed9cc  lea     rbp, [rsp-110h]
0x1800ed9d4  sub     rsp, 210h
0x1800ed9db  mov     rax, cs:__security_cookie
0x1800ed9e2  xor     rax, rsp
0x1800ed9e5  mov     [rbp+140h+var_38], rax
0x1800ed9ec  mov     rdi, rdx
0x1800ed9ef  mov     rsi, rcx
0x1800ed9f2  xor     r13d, r13d
0x1800ed9f5  mov     r14d, r13d
0x1800ed9f8  mov     dword ptr [rsp+240h+var_208], r13d
0x1800ed9fd  mov     rax, cs:qword_18021BF90
0x1800eda04  test    rax, rax
0x1800eda07  jz      loc_1800EDAF4
0x1800eda0d  cmp     [rax], r13d
0x1800eda10  jbe     loc_1800EDAF4
0x1800eda16  mov     rcx, [rdx]
0x1800eda19  call    sub_1800A7A44
0x1800eda1e  mov     r8, rax
0x1800eda21  lea     rdx, aUri; "uri"
0x1800eda28  lea     rcx, [rbp+140h+var_1A0]
0x1800eda2c  call    sub_1800153C8
0x1800eda31  mov     dword ptr [rsp+240h+var_208], r13d
0x1800eda36  lea     r8, [rsp+240h+var_210]
0x1800eda3b  lea     rdx, [rsp+240h+var_208]
0x1800eda40  lea     rcx, [rbp+140h+var_160]
0x1800eda44  call    sub_18000B710
0x1800eda49  lea     r8, [rbp+140h+var_1A0]
0x1800eda4d  lea     rdx, [rbp+140h+var_A0]
0x1800eda54  lea     rcx, [rbp+140h+var_160]
0x1800eda58  call    sub_180015A2C
0x1800eda5d  xorps   xmm0, xmm0
0x1800eda60  movups  [rbp+140h+var_1C0], xmm0
0x1800eda64  xorps   xmm1, xmm1
0x1800eda67  movdqu  [rbp+140h+var_1B0], xmm1
0x1800eda6c  lea     r8d, [r13+56h]
0x1800eda70  lea     rdx, aThirdPartyWpCl_52; "../../../../third_party/wp.client/msint"...
0x1800eda77  lea     rcx, [rbp+140h+var_1C0]
0x1800eda7b  call    sub_180004678
0x1800eda80  xorps   xmm0, xmm0
0x1800eda83  movups  [rsp+240h+var_1E8], xmm0
0x1800eda88  xorps   xmm1, xmm1
0x1800eda8b  movdqu  [rsp+240h+var_1D8], xmm1
0x1800eda91  lea     r8d, [r13+6]
0x1800eda95  lea     rdx, aLookup_0; "Lookup"
0x1800eda9c  lea     rcx, [rsp+240h+var_1E8]
0x1800edaa1  call    sub_180004678
0x1800edaa6  lea     rax, [rbp+140h+var_160]
0x1800edaaa  mov     [rsp+240h+var_220], rax
0x1800edaaf  mov     r9d, 0B5h
0x1800edab5  lea     r8, [rbp+140h+var_1C0]
0x1800edab9  lea     rdx, [rsp+240h+var_1E8]
0x1800edabe  lea     rcx, qword_18021BF90
0x1800edac5  call    sub_180015E7C
0x1800edaca  lea     rcx, [rbp+140h+var_148]
0x1800edace  call    sub_1800102F8
0x1800edad3  lea     rcx, [rbp+140h+var_158]
0x1800edad7  call    sub_180010448
0x1800edadc  lea     r9, sub_18000D430
0x1800edae3  lea     edx, [r13+40h]
0x1800edae7  lea     r8d, [r13+1]
0x1800edaeb  lea     rcx, [rbp+140h+var_1A0]
0x1800edaef  call    sub_1800F3B5C
0x1800edaf4  lea     rcx, [rsp+240h+var_208]
0x1800edaf9  call    sub_180012208
0x1800edafe  mov     rax, [rsi+18h]
0x1800edb02  mov     r15b, [rax+82h]
0x1800edb09  mov     rax, [rdi+8]
0x1800edb0d  test    rax, rax
0x1800edb10  jz      short loc_1800EDB16
0x1800edb12  lock inc dword ptr [rax+8]
0x1800edb16  mov     rcx, [rdi]
0x1800edb19  mov     rbx, [rdi+8]
0x1800edb1d  mov     rax, qword ptr [rsp+240h+var_208]
0x1800edb22  mov     [rbp+140h+var_160], rax
0x1800edb26  test    rbx, rbx
0x1800edb29  jz      short loc_1800EDB2F
0x1800edb2b  lock inc dword ptr [rbx+8]
0x1800edb2f  mov     [rbp+140h+var_158], rcx
0x1800edb33  mov     [rbp+140h+var_150], rbx
0x1800edb37  mov     [rbp+140h+var_148], r15b
0x1800edb3b  mov     [rbp+140h+var_140], r13b
0x1800edb3f  or      r12d, 0FFFFFFFFh
0x1800edb43  test    rbx, rbx
0x1800edb46  jz      short loc_1800EDB81
0x1800edb48  mov     eax, r12d
0x1800edb4b  lock xadd [rbx+8], eax
0x1800edb50  add     eax, r12d
0x1800edb53  jnz     short loc_1800EDB81
0x1800edb55  mov     rax, [rbx]
0x1800edb58  mov     rcx, rbx
0x1800edb5b  mov     rax, [rax]
0x1800edb5e  call    cs:__guard_dispatch_icall_fptr
0x1800edb64  mov     eax, r12d
0x1800edb67  lock xadd [rbx+0Ch], eax
0x1800edb6c  add     eax, r12d
0x1800edb6f  jnz     short loc_1800EDB81
0x1800edb71  mov     rax, [rbx]
0x1800edb74  mov     rcx, rbx
0x1800edb77  mov     rax, [rax+8]
0x1800edb7b  call    cs:__guard_dispatch_icall_fptr
0x1800edb81  mov     rcx, [rdi]
0x1800edb84  call    sub_1800A7AE8
0x1800edb89  mov     byte ptr [rsp+240h+var_210], al
0x1800edb8d  mov     byte ptr [rsp+240h+var_210+1], 1
0x1800edb92  mov     rcx, [rdi]
0x1800edb95  mov     rdx, [rcx+170h]
0x1800edb9c  movzx   ecx, [rsp+240h+var_210]
0x1800edba1  mov     [rdx+19h], cx
0x1800edba5  test    al, al
0x1800edba7  jnz     loc_1800EDCF7
0x1800edbad  mov     rax, cs:qword_18021BF90
0x1800edbb4  test    rax, rax
0x1800edbb7  jz      loc_1800EDCAA
0x1800edbbd  cmp     [rax], r13d
0x1800edbc0  jbe     loc_1800EDCAA
0x1800edbc6  mov     rcx, [rdi]
0x1800edbc9  call    sub_1800A7A44
0x1800edbce  mov     r8, rax
0x1800edbd1  lea     rdx, aUri; "uri"
0x1800edbd8  lea     rcx, [rbp+140h+var_120]
0x1800edbdc  call    sub_1800153C8
0x1800edbe1  mov     dword ptr [rsp+240h+var_208], r13d
0x1800edbe6  lea     r8, [rsp+240h+var_210]
0x1800edbeb  lea     rdx, [rsp+240h+var_208]
0x1800edbf0  lea     rcx, [rbp+140h+var_1A0]
0x1800edbf4  call    sub_18000B710
0x1800edbf9  lea     r8, [rbp+140h+var_120]
0x1800edbfd  lea     rdx, [rbp+140h+var_A0]
0x1800edc04  lea     rcx, [rbp+140h+var_1A0]
0x1800edc08  call    sub_180015A2C
0x1800edc0d  xorps   xmm0, xmm0
0x1800edc10  movups  [rsp+240h+var_1E8], xmm0
0x1800edc15  xorps   xmm1, xmm1
0x1800edc18  movdqu  [rsp+240h+var_1D8], xmm1
0x1800edc1e  mov     r8d, 56h ; 'V'
0x1800edc24  lea     rdx, aThirdPartyWpCl_52; "../../../../third_party/wp.client/msint"...
0x1800edc2b  lea     rcx, [rsp+240h+var_1E8]
0x1800edc30  call    sub_180004678
0x1800edc35  xorps   xmm0, xmm0
0x1800edc38  movups  [rbp+140h+var_1C0], xmm0
0x1800edc3c  xorps   xmm1, xmm1
0x1800edc3f  movdqu  [rbp+140h+var_1B0], xmm1
0x1800edc44  mov     r8d, 1Ch
0x1800edc4a  lea     rdx, aUnsupporteddes; "UnsupportedDestinationScheme"
0x1800edc51  lea     rcx, [rbp+140h+var_1C0]
0x1800edc55  call    sub_180004678
0x1800edc5a  lea     rax, [rbp+140h+var_1A0]
0x1800edc5e  mov     [rsp+240h+var_220], rax
0x1800edc63  mov     r9d, 0C1h
0x1800edc69  lea     r8, [rsp+240h+var_1E8]
0x1800edc6e  lea     rdx, [rbp+140h+var_1C0]
0x1800edc72  lea     rcx, qword_18021BF90
0x1800edc79  call    sub_18000EEAC
0x1800edc7e  lea     rcx, [rbp+140h+var_188]
0x1800edc82  call    sub_1800102F8
0x1800edc87  lea     rcx, [rbp+140h+var_198]
0x1800edc8b  call    sub_180010448
0x1800edc90  lea     r9, sub_18000D430
0x1800edc97  mov     edx, 40h ; '@'
0x1800edc9c  lea     r8d, [rdx-3Fh]
0x1800edca0  lea     rcx, [rbp+140h+var_120]
0x1800edca4  call    sub_1800F3B5C
0x1800edca9  nop
0x1800edcaa  mov     r8b, r15b
0x1800edcad  lea     rdx, [rbp+140h+var_158]
0x1800edcb1  lea     rcx, [rbp+140h+var_160]
0x1800edcb5  call    sub_1800EE6C0
0x1800edcba  mov     rbx, [rbp+140h+var_150]
0x1800edcbe  test    rbx, rbx
0x1800edcc1  jz      loc_1800EE694
0x1800edcc7  mov     eax, r12d
0x1800edcca  lock xadd [rbx+8], eax
0x1800edccf  add     eax, r12d
0x1800edcd2  jnz     loc_1800EE694
0x1800edcd8  mov     rax, [rbx]
0x1800edcdb  mov     rcx, rbx
0x1800edcde  mov     rax, [rax]
0x1800edce1  call    cs:__guard_dispatch_icall_fptr
0x1800edce7  mov     eax, r12d
0x1800edcea  lock xadd [rbx+0Ch], eax
0x1800edcef  add     eax, r12d
0x1800edcf2  jmp     loc_1800EE681
0x1800edcf7  mov     rax, [rdi]
0x1800edcfa  mov     rbx, [rax+170h]
0x1800edd01  mov     rax, [rsi+18h]
0x1800edd05  mov     rcx, [rax+0B8h]
0x1800edd0c  test    rcx, rcx
0x1800edd0f  jz      short loc_1800EDD1F
0x1800edd11  lea     rdx, [rbp+140h+var_A0]
0x1800edd18  call    sub_180031598
0x1800edd1d  jmp     short loc_1800EDD2B
0x1800edd1f  lea     rcx, [rbp+140h+var_A0]
0x1800edd26  call    sub_180023770
0x1800edd2b  mov     rax, [rbp+140h+var_A0]
0x1800edd32  mov     cl, [rax+8]
0x1800edd35  mov     byte ptr [rsp+240h+var_210], cl
0x1800edd39  mov     byte ptr [rsp+240h+var_210+1], 1
0x1800edd3e  movzx   eax, [rsp+240h+var_210]
0x1800edd43  mov     [rbx+1Bh], ax
0x1800edd47  mov     rbx, [rbp+140h+var_98]
0x1800edd4e  test    rbx, rbx
0x1800edd51  jz      short loc_1800EDD8C
0x1800edd53  mov     eax, r12d
0x1800edd56  lock xadd [rbx+8], eax
0x1800edd5b  add     eax, r12d
0x1800edd5e  jnz     short loc_1800EDD8C
0x1800edd60  mov     rax, [rbx]
0x1800edd63  mov     rcx, rbx
0x1800edd66  mov     rax, [rax]
0x1800edd69  call    cs:__guard_dispatch_icall_fptr
0x1800edd6f  mov     eax, r12d
0x1800edd72  lock xadd [rbx+0Ch], eax
0x1800edd77  add     eax, r12d
0x1800edd7a  jnz     short loc_1800EDD8C
0x1800edd7c  mov     rax, [rbx]
0x1800edd7f  mov     rcx, rbx
0x1800edd82  mov     rax, [rax+8]
0x1800edd86  call    cs:__guard_dispatch_icall_fptr
0x1800edd8c  mov     rax, [rdi]
0x1800edd8f  cmp     [rax+1C0h], r13b
0x1800edd96  jnz     short loc_1800EDDD8
0x1800edd98  mov     rax, [rsi+18h]
0x1800edd9c  mov     rcx, [rax+0B8h]
0x1800edda3  test    rcx, rcx
0x1800edda6  jz      short loc_1800EDDB6
0x1800edda8  lea     rdx, [rbp+140h+var_A0]
0x1800eddaf  call    sub_180031598
0x1800eddb4  jmp     short loc_1800EDDC2
0x1800eddb6  lea     rcx, [rbp+140h+var_A0]
0x1800eddbd  call    sub_180023770
0x1800eddc2  mov     rax, [rbp+140h+var_A0]
0x1800eddc9  mov     r14d, 1
0x1800eddcf  cmp     [rax+8], r13b
0x1800eddd3  mov     r12b, r14b
0x1800eddd6  jz      short loc_1800EDDDB
0x1800eddd8  mov     r12b, r13b
0x1800edddb  test    r14b, 1
0x1800edddf  jz      short loc_1800EDE2A
0x1800edde1  mov     rbx, [rbp+140h+var_98]
0x1800edde8  test    rbx, rbx
0x1800eddeb  jz      short loc_1800EDE2A
0x1800edded  or      r14d, 0FFFFFFFFh
0x1800eddf1  mov     eax, r14d
0x1800eddf4  lock xadd [rbx+8], eax
0x1800eddf9  add     eax, r14d
0x1800eddfc  jnz     short loc_1800EDE2A
0x1800eddfe  mov     rax, [rbx]
0x1800ede01  mov     rcx, rbx
0x1800ede04  mov     rax, [rax]
0x1800ede07  call    cs:__guard_dispatch_icall_fptr
0x1800ede0d  mov     eax, r14d
0x1800ede10  lock xadd [rbx+0Ch], eax
0x1800ede15  add     eax, r14d
0x1800ede18  jnz     short loc_1800EDE2A
0x1800ede1a  mov     rax, [rbx]
0x1800ede1d  mov     rcx, rbx
0x1800ede20  mov     rax, [rax+8]
0x1800ede24  call    cs:__guard_dispatch_icall_fptr
0x1800ede2a  test    r12b, r12b
0x1800ede2d  jz      loc_1800EE046
0x1800ede33  lea     rcx, [rbp+140h+var_A0]
0x1800ede3a  call    sub_180012208
0x1800ede3f  mov     r8, [rdi]
0x1800ede42  lea     r9, [r8+1A0h]
0x1800ede49  mov     rcx, [rsi+18h]
0x1800ede4d  lea     rdx, [rbp+140h+var_120]
0x1800ede51  mov     rcx, [rcx+0B8h]
0x1800ede58  call    sub_18002DC2C
0x1800ede5d  cmp     [rax+78h], r13b
0x1800ede61  jz      short loc_1800EDE67
0x1800ede63  mov     bl, [rax]
0x1800ede65  jmp     short loc_1800EDE6A
0x1800ede67  mov     bl, r13b
0x1800ede6a  cmp     [rbp+140h+var_A8], r13b
0x1800ede71  jnz     short loc_1800EDE8E
0x1800ede73  lea     rcx, [rbp+140h+var_C8]
0x1800ede77  call    sub_180007F5C
0x1800ede7c  lea     rcx, [rbp+140h+var_E8]
0x1800ede80  call    sub_180007F5C
0x1800ede85  lea     rcx, [rbp+140h+var_110]
0x1800ede89  call    sub_180007F5C
0x1800ede8e  mov     rax, [rdi]
0x1800ede91  mov     rcx, [rax+170h]
0x1800ede98  mov     dword ptr [rsp+240h+var_208], 4
0x1800edea0  lea     r8, [rbp+140h+var_A0]
0x1800edea7  lea     rdx, [rsp+240h+var_208]
0x1800edeac  call    sub_1800E5E68
0x1800edeb1  mov     rax, [rdi]
0x1800edeb4  mov     r14, [rax+170h]
0x1800edebb  mov     r12d, 1
0x1800edec1  test    bl, bl
0x1800edec3  jz      short loc_1800EDED0
  ... truncated ...
```
