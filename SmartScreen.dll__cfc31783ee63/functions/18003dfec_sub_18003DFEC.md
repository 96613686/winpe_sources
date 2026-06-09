# sub_18003DFEC

- ea: `0x18003dfec`
- end: `0x18003f041`
- name: `sub_18003DFEC`
- size: `4181`
- prototype: ``
- caller_count: `1`
- callee_count: `38`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002fd00`

## callees

- `0x180004678`
- `0x180007f5c`
- `0x1800096e8`
- `0x18000b710`
- `0x18000bc94`
- `0x18000c4c8`
- `0x18000cf04`
- `0x18000d450`
- `0x1800106b8`
- `0x180014eb0`
- `0x180016a0c`
- `0x180018844`
- `0x180019118`
- `0x180019d00`
- `0x180023968`
- `0x1800239f8`
- `0x180023e8c`
- `0x18002436c`
- `0x180024cc0`
- `0x18002590c`
- `0x180026558`
- `0x1800271a4`
- `0x180029458`
- `0x18002b794`
- `0x18002beb8`
- `0x18002c668`
- `0x18002d3d8`
- `0x18002d550`
- `0x18003563c`
- `0x180035818`
- `0x18003dfec`
- `0x180049970`
- `0x1800499a4`
- `0x1800e4920`
- `0x1800f3c24`
- `0x1800f4270`
- `0x18013b830`
- `0x18013bf50`

## string_xrefs

- `0x18003eb0d`: `customSynchronousLookupUris`
- `0x18003e3dc`: `../../../../third_party/wp.client/msinternal/src/browser/src/esp/smartscreen/src/remote_data/browser_remotedata.cpp`
- `0x18003e951`: `../../../../third_party/wp.client/msinternal/src/browser/src/esp/smartscreen/src/remote_data/browser_remotedata.cpp`
- `0x18003ebac`: `../../../../third_party/wp.client/msinternal/src/browser/src/esp/smartscreen/src/remote_data/browser_remotedata.cpp`
- `0x18003ee3a`: `../../../../third_party/wp.client/msinternal/src/browser/src/esp/smartscreen/src/remote_data/browser_remotedata.cpp`

## pseudocode

```c
__int64 __fastcall sub_18003DFEC(_QWORD *a1, __int64 a2, __int64 a3, _QWORD *a4, __int64 a5, char a6)
{
  __int64 v10; // xmm3_8
  __int128 *v11; // rdx
  _QWORD *v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  volatile signed __int32 *v16; // rbx
  __int64 v17; // rax
  __int128 *v18; // rcx
  volatile signed __int32 *v19; // rbx
  volatile signed __int32 *v20; // rbx
  _QWORD *v21; // rbx
  _QWORD *v22; // rdi
  __int64 v23; // rdx
  _QWORD *v24; // rcx
  __int64 v25; // rax
  __int128 *v26; // rax
  char v27; // r12
  __int64 v28; // rsi
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  volatile signed __int32 *v32; // rbx
  __int64 v33; // rdx
  __int64 v34; // rbx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rsi
  __int64 *v40; // rax
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rbx
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 *v48; // rax
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // rax
  _BYTE v53[8]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v54; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v55[2]; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v56[2]; // [rsp+70h] [rbp-90h] BYREF
  char v57; // [rsp+78h] [rbp-88h]
  __int64 v58; // [rsp+80h] [rbp-80h] BYREF
  volatile signed __int32 *v59; // [rsp+88h] [rbp-78h]
  __int128 v60; // [rsp+90h] [rbp-70h] BYREF
  __int128 v61; // [rsp+A0h] [rbp-60h]
  __int128 v62; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v63; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v64[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v65; // [rsp+F8h] [rbp-8h] BYREF
  __m128i v66; // [rsp+108h] [rbp+8h]
  _BYTE v67[32]; // [rsp+118h] [rbp+18h] BYREF
  char v68; // [rsp+138h] [rbp+38h]
  _BYTE v69[16]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v70[40]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v71[32]; // [rsp+198h] [rbp+98h] BYREF
  _BYTE v72[40]; // [rsp+1B8h] [rbp+B8h] BYREF
  _BYTE v73[16]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v74[40]; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v75[32]; // [rsp+218h] [rbp+118h] BYREF
  _BYTE v76[40]; // [rsp+238h] [rbp+138h] BYREF
  __int128 v77; // [rsp+260h] [rbp+160h] BYREF
  __int128 v78; // [rsp+270h] [rbp+170h]
  _QWORD v79[2]; // [rsp+280h] [rbp+180h] BYREF
  __int64 v80; // [rsp+290h] [rbp+190h]
  unsigned __int64 v81; // [rsp+298h] [rbp+198h]
  __int64 v82; // [rsp+2A0h] [rbp+1A0h]
  _OWORD v83[2]; // [rsp+2B0h] [rbp+1B0h] BYREF
  _OWORD v84[2]; // [rsp+2D0h] [rbp+1D0h] BYREF
  char v85; // [rsp+2F0h] [rbp+1F0h]
  __int128 v86; // [rsp+300h] [rbp+200h] BYREF
  __m128i v87[2]; // [rsp+310h] [rbp+210h] BYREF
  _BYTE v88[32]; // [rsp+338h] [rbp+238h] BYREF
  _BYTE v89[32]; // [rsp+358h] [rbp+258h] BYREF
  char v90; // [rsp+378h] [rbp+278h]
  _QWORD v91[4]; // [rsp+380h] [rbp+280h] BYREF
  volatile signed __int32 *v92; // [rsp+3A0h] [rbp+2A0h]
  _QWORD v93[2]; // [rsp+3B0h] [rbp+2B0h] BYREF
  __int64 v94; // [rsp+3C0h] [rbp+2C0h] BYREF
  __int64 v95; // [rsp+3C8h] [rbp+2C8h]
  volatile signed __int32 *v96; // [rsp+3D0h] [rbp+2D0h]
  _BYTE v97[32]; // [rsp+3E8h] [rbp+2E8h] BYREF
  _BYTE v98[32]; // [rsp+408h] [rbp+308h] BYREF
  char v99; // [rsp+428h] [rbp+328h]
  _QWORD v100[2]; // [rsp+430h] [rbp+330h] BYREF
  __int64 v101; // [rsp+440h] [rbp+340h] BYREF
  unsigned __int64 v102; // [rsp+448h] [rbp+348h]
  __int64 v103; // [rsp+450h] [rbp+350h]
  _BYTE v104[32]; // [rsp+468h] [rbp+368h] BYREF
  _BYTE v105[32]; // [rsp+488h] [rbp+388h] BYREF
  char v106; // [rsp+4A8h] [rbp+3A8h]

  *(_QWORD *)&v62 = a5;
  LODWORD(v54) = 0;
  v77 = 0;
  v78 = 0;
  sub_180004678(&v77, "RemoteData", 10);
  sub_1800E4920(a1, &v86, a3, &v77);
  sub_180007F5C(&v77);
  if ( v90 )
  {
    v65 = v86;
    v10 = v87[0].m128i_i64[0];
    v66 = v87[0];
    v87[0] = _mm_load_si128((const __m128i *)&xmmword_180149C10);
    LOWORD(v86) = 0;
    LOBYTE(v82) = 0;
    memset(v83, 0, sizeof(v83));
    v11 = &v65;
    if ( _mm_srli_si128(v66, 8).m128i_u64[0] > 7 )
      v11 = (__int128 *)v65;
    sub_1800096E8(v83, v11, v10);
    v85 = 0;
    if ( (_BYTE)v82 )
    {
      memset(v84, 0, sizeof(v84));
      v12 = v79;
      if ( v81 > 7 )
        v12 = (_QWORD *)v79[0];
      sub_1800096E8(v84, v12, v80);
      v85 = 1;
      if ( (_BYTE)v82 )
        sub_1800106B8(v79);
    }
    sub_18013BF50(v93, 0, 128);
    sub_18003563C(v93);
    if ( !v99 )
    {
      sub_18000BC94(a2, v93);
      *(_BYTE *)(a2 + 120) = 0;
      if ( v99 )
      {
        sub_18002D550(v93, 0);
LABEL_16:
        if ( v85 )
          sub_1800106B8(v84);
        sub_1800106B8(v83);
        sub_1800106B8(&v65);
        goto LABEL_3;
      }
LABEL_15:
      sub_180007F5C(v98);
      sub_180007F5C(v97);
      sub_180007F5C(&v94);
      goto LABEL_16;
    }
    v91[0] = v93[0];
    v91[1] = v93[1];
    v91[2] = v94;
    v91[3] = v95;
    v92 = v96;
    v95 = 0;
    v96 = 0;
    v13 = a4[1];
    if ( v13 )
      _InterlockedIncrement((volatile signed __int32 *)(v13 + 8));
    v55[0] = *a4;
    v55[1] = a4[1];
    v54 = 0;
    v57 = 0;
    v14 = sub_180023968(v64, v91, "F95BA787499AB4FA9EFFF472CE383A14");
    v15 = sub_180024CC0(
            (_DWORD)a1,
            (unsigned int)&v58,
            (unsigned int)v83,
            (unsigned int)"customSettings",
            v14,
            (__int64)v56,
            (__int64)&v54,
            (__int64)v55,
            a5,
            0);
    sub_18002C668(a1 + 7, v15);
    v16 = v59;
    if ( v59 )
    {
      if ( _InterlockedExchangeAdd(v59 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
        if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      }
    }
    if ( a1[7] )
    {
      v77 = 0;
      v78 = 0;
      sub_180004678(&v77, &qword_18014B5C8, _mm_srli_si128(*(__m128i *)&off_18014B5B8, 8).m128i_u64[0]);
      v21 = (_QWORD *)sub_1800F3C24(64);
      if ( v21 )
      {
        *v21 = off_18014CD98;
        v21[7] = v21;
      }
      else
      {
        v21 = 0;
      }
      v22 = v21;
      sub_18013BF50(v100, 0, 128);
      sub_180035818(v100);
      if ( v106 )
      {
        v79[0] = v100[0];
        v79[1] = v100[1];
        v80 = v101;
        v81 = v102;
        v82 = v103;
        v102 = 0;
        v103 = 0;
        v25 = a4[1];
        if ( v25 )
          _InterlockedIncrement((volatile signed __int32 *)(v25 + 8));
        v58 = *a4;
        v59 = (volatile signed __int32 *)a4[1];
        if ( a6 )
        {
          v22 = 0;
          v26 = (__int128 *)v55;
          v27 = 1;
          v28 = v55[0];
        }
        else
        {
          v28 = 0;
          v26 = &v63;
          v21 = 0;
          v27 = 6;
        }
        *(_QWORD *)v26 = 0;
        v54 = v21;
        v56[0] = 0;
        v56[1] = 2;
        v57 = 1;
        v29 = sub_180016A0C(v67, &v77, "-0");
        v30 = sub_1800239F8(&v60, v79, v29);
        v31 = sub_18002590C(
                (_DWORD)a1,
                (unsigned int)v64,
                (unsigned int)v83,
                (unsigned int)"edgeSettings",
                v30,
                (__int64)v56,
                (__int64)&v54,
                (__int64)&v58,
                v62,
                0);
        sub_18002C668(a1 + 9, v31);
        v32 = (volatile signed __int32 *)*((_QWORD *)&v64[0] + 1);
        if ( *((_QWORD *)&v64[0] + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v64[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
            if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
          }
        }
        sub_180007F5C(v67);
        if ( (v27 & 4) != 0 )
        {
          v27 &= ~4u;
          v34 = v63;
          if ( (_QWORD)v63 )
          {
            v35 = *(_QWORD *)(v63 + 56);
            if ( v35 )
            {
              LOBYTE(v33) = v35 != (_QWORD)v63;
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v35 + 32LL))(v35, v33);
              *(_QWORD *)(v34 + 56) = 0;
            }
            FreeExperience(v34);
          }
        }
        if ( (v27 & 2) != 0 )
        {
          v27 &= ~2u;
          if ( v28 )
          {
            v36 = *(_QWORD *)(v28 + 56);
            if ( v36 )
            {
              LOBYTE(v33) = v36 != v28;
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v36 + 32LL))(v36, v33);
              *(_QWORD *)(v28 + 56) = 0;
            }
            FreeExperience(v28);
          }
        }
        if ( (v27 & 1) != 0 && v55[0] )
          sub_18002D3D8(v55[0], 1);
        if ( a1[9] )
        {
          v63 = 0;
          v38 = a4[1];
          if ( v38 )
            _InterlockedAdd((volatile signed __int32 *)(v38 + 8), 1u);
          v58 = *a4;
          v59 = (volatile signed __int32 *)a4[1];
          v55[0] = 0;
          v57 = 0;
          v64[0] = 0;
          v39 = v62;
          sub_180026558(
            (_DWORD)a1,
            (unsigned int)&v63,
            (unsigned int)v83,
            (unsigned int)"customSynchronousLookupUris",
            (__int64)v64,
            (__int64)v56,
            (__int64)v55,
            (__int64)&v58,
            v62,
            0);
          v40 = (__int64 *)sub_180023E8C(v55, &v63);
          v41 = *v40;
          *v40 = 0;
          v42 = a1[14];
          a1[14] = v41;
          if ( v42 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v42 + 8LL))(v42, 1);
          if ( v55[0] )
            (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v55[0] + 8LL))(v55[0], 1);
          if ( a1[14] )
          {
            v62 = 0;
            v44 = a4[1];
            if ( v44 )
              _InterlockedAdd((volatile signed __int32 *)(v44 + 8), 1u);
            v58 = *a4;
            v59 = (volatile signed __int32 *)a4[1];
            v55[0] = 0;
            v57 = 0;
            v45 = sub_1800499A4(v67);
            v46 = sub_180049970(v64);
            v47 = sub_1800239F8(&v60, v46, v45);
            sub_1800271A4(
              (_DWORD)a1,
              (unsigned int)&v62,
              (unsigned int)v83,
              (unsigned int)"topTraffic",
              v47,
              (__int64)v56,
              (__int64)v55,
              (__int64)&v58,
              v39,
              0);
            sub_18002BEB8(v64);
            sub_180007F5C(v67);
            v48 = (__int64 *)sub_18002436C(v55, &v62);
            v49 = *v48;
            *v48 = 0;
            v50 = a1[15];
            a1[15] = v49;
            if ( v50 )
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v50 + 8LL))(v50, 1);
            if ( v55[0] )
              (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v55[0] + 8LL))(v55[0], 1);
            if ( a1[15] )
            {
              *(_BYTE *)(a2 + 120) = 1;
              sub_18000D450(&v62);
              sub_18000D450(&v63);
              if ( v82 )
                sub_180019D00(v82);
              sub_18002B794(v100);
              if ( v22 )
                sub_18002D3D8(v22, 1);
              sub_180007F5C(&v77);
              if ( v92 )
                sub_180019D00(v92);
              sub_18002B794(v93);
              if ( v85 )
                sub_1800106B8(v84);
              sub_1800106B8(v83);
              sub_1800106B8(&v65);
              sub_18000CF04(&v86);
              return a2;
            }
            LODWORD(v54) = 0;
            sub_18000B710(v73, &v54, v53);
            v68 = 0;
            sub_180029458(v64, "NullTopTrafficFilter");
            sub_180029458(
              &v60,
              "../../../../third_party/wp.client/msinternal/src/browser/src/esp/smartscreen/src/remote_data/browser_remotedata.cpp");
            v51 = sub_18000C4C8(
                    (unsigned int)v69,
                    127,
                    (unsigned int)&v60,
                    383,
                    (__int64)v64,
                    0,
                    (__int64)v67,
                    (__int64)v73);
            sub_180018844(a2, v51);
            sub_180007F5C(v72);
            sub_180007F5C(v71);
            sub_180007F5C(v70);
            sub_180007F5C(&v60);
            sub_180007F5C(v64);
            sub_18000D450(&v62);
            sub_18000D450(&v63);
            if ( v82 )
              sub_180019D00(v82);
            sub_18002B794(v100);
            if ( v22 )
              sub_18002D3D8(v22, 1);
            sub_180007F5C(&v77);
            if ( v92 )
              sub_180019D00(v92);
            sub_18002B794(v93);
          }
          else
          {
            LODWORD(v54) = 0;
            sub_18000B710(v73, &v54, v53);
            v68 = 0;
            sub_180029458(v64, "NullCustomBloomFilter");
            sub_180029458(
              &v60,
              "../../../../third_party/wp.client/msinternal/src/browser/src/esp/smartscreen/src/remote_data/browser_remotedata.cpp");
            v43 = sub_18000C4C8(
                    (unsigned int)v69,
                    127,
                    (unsigned int)&v60,
                    366,
                    (__int64)v64,
                    0,
                    (__int64)v67,
                    (__int64)v73);
            sub_180018844(a2, v43);
            sub_180007F5C(v72);
            sub_180007F5C(v71);
            sub_180007F5C(v70);
            sub_180007F5C(&v60);
            sub_180007F5C(v64);
            sub_18000D450(&v63);
            if ( v82 )
              sub_180019D00(v82);
            if ( v106 )
            {
              if ( v103 )
                sub_180019D00(v103);
            }
            else
            {
              sub_180007F5C(v105);
              sub_180007F5C(v104);
              sub_180007F5C(&v101);
            }
            if ( v22 )
              sub_18002D3D8(v22, 1);
            sub_180007F5C(&v77);
            if ( v92 )
              sub_180019D00(v92);
            if ( v99 )
            {
              if ( v96 )
                sub_180019D00(v96);
            }
            else
            {
              sub_180007F5C(v98);
              sub_180007F5C(v97);
              sub_180007F5C(&v94);
            }
          }
          if ( v85 )
            sub_1800106B8(v84);
          sub_1800106B8(v83);
          sub_1800106B8(&v65);
          if ( !v90 )
          {
            sub_180019118(&v86, 0);
            return a2;
          }
          goto LABEL_123;
        }
        LODWORD(v54) = 0;
        sub_18000B710(v73, &v54, v53);
        v68 = 0;
        memset(v64, 0, sizeof(v64));
        sub_180004678(v64, "NullEdgeSettingsHolder", 22);
        v60 = 0;
        v61 = 0;
        sub_180004678(
          &v60,
          "../../../../third_party/wp.client/msinternal/src/browser/src/esp/smartscreen/src/remote_data/browser_remotedata.cpp",
          115);
        v37 = sub_18000C4C8(
                (unsigned int)v69,
                127,
                (unsigned int)&v60,
                351,
                (__int64)v64,
                0,
                (__int64)v67,
                (__int64)v73);
        sub_180018844(a2, v37);
        sub_180007F5C(v72);
        sub_180007F5C(v71);
        sub_180007F5C(v70);
        sub_180007F5C(&v60);
        sub_180007F5C(v64);
        if ( v82 )
          sub_180019D00(v82);
        if ( v106 )
        {
          if ( v103 )
            sub_180019D00(v103);
        }
        else
        {
          sub_180007F5C(v105);
          sub_180007F5C(v104);
          sub_180007F5C(&v101);
        }
        if ( v22 )
          sub_18002D3D8(v22, 1);
        sub_180007F5C(&v77);
        if ( v92 )
          sub_180019D00(v92);
        if ( v99 )
        {
          if ( v96 )
            sub_180019D00(v96);
          goto LABEL_16;
        }
        goto LABEL_15;
      }
      sub_18000BC94(a2, v100);
      *(_BYTE *)(a2 + 120) = 0;
      if ( v106 )
      {
        sub_18002D550(v100, 0);
      }
      else
      {
        sub_180007F5C(v105);
        sub_180007F5C(v104);
        sub_180007F5C(&v101);
      }
      if ( v21 )
      {
        v24 = (_QWORD *)v21[7];
        if ( v24 )
        {
          LOBYTE(v23) = v24 != v21;
          (*(void (__fastcall **)(_QWORD *, __int64))(*v24 + 32LL))(v24, v23);
          v21[7] = 0;
        }
        FreeExperience(v21);
      }
      v18 = &v77;
    }
    else
    {
      LODWORD(v54) = 0;
      sub_18000B710(v67, &v54, v53);
      LOBYTE(v82) = 0;
      v60 = 0;
      v61 = 0;
      sub_180004678(&v60, "NullCustomSettingsHolder", 24);
      v77 = 0;
      v78 = 0;
      sub_180004678(
        &v77,
        "../../../../third_party/wp.client/msinternal/src/browser/src/esp/smartscreen/src/remote_data/browser_remotedata.cpp",
        115);
      v17 = sub_18000C4C8((unsigned int)v73, 127, (unsigned int)&v77, 327, (__int64)&v60, 0, (__int64)v79, (__int64)v67);
      *(_OWORD *)a2 = *(_OWORD *)v17;
      *(_OWORD *)(a2 + 16) = 0;
      *(_QWORD *)(a2 + 32) = 0;
      *(_QWORD *)(a2 + 40) = 0;
      *(_OWORD *)(a2 + 16) = *(_OWORD *)(v17 + 16);
      *(_OWORD *)(a2 + 32) = *(_OWORD *)(v17 + 32);
      *(_QWORD *)(v17 + 32) = 0;
      *(_QWORD *)(v17 + 40) = 15;
      *(_BYTE *)(v17 + 16) = 0;
      *(_DWORD *)(a2 + 48) = *(_DWORD *)(v17 + 48);
      *(_OWORD *)(a2 + 56) = 0;
      *(_QWORD *)(a2 + 72) = 0;
      *(_QWORD *)(a2 + 80) = 0;
      *(_OWORD *)(a2 + 56) = *(_OWORD *)(v17 + 56);
      *(_OWORD *)(a2 + 72) = *(_OWORD *)(v17 + 72);
      *(_QWORD *)(v17 + 72) = 0;
      *(_QWORD *)(v17 + 80) = 15;
      *(_BYTE *)(v17 + 56) = 0;
      *(_OWORD *)(a2 + 88) = 0;
      *(_QWORD *)(a2 + 104) = 0;
      *(_QWORD *)(a2 + 112) = 0;
      *(_OWORD *)(a2 + 88) = *(_OWORD *)(v17 + 88);
      *(_OWORD *)(a2 + 104) = *(_OWORD *)(v17 + 104);
      *(_QWORD *)(v17 + 104) = 0;
      *(_QWORD *)(v17 + 112) = 15;
      *(_BYTE *)(v17 + 88) = 0;
      *(_BYTE *)(a2 + 120) = 0;
      sub_180007F5C(v76);
      sub_180007F5C(v75);
      sub_180007F5C(v74);
      sub_180007F5C(&v77);
      v18 = &v60;
    }
    sub_180007F5C(v18);
    v19 = v92;
    if ( v92 )
    {
      if ( _InterlockedExchangeAdd(v92 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
    }
    if ( v99 )
    {
      v20 = v96;
      if ( v96 )
      {
        if ( _InterlockedExchangeAdd(v96 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
          if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
        }
      }
      goto LABEL_16;
    }
    goto LABEL_15;
  }
  sub_18000BC94(a2, &v86);
  *(_BYTE *)(a2 + 120) = 0;
LABEL_3:
  if ( v90 )
  {
LABEL_123:
    sub_1800106B8(&v86);
    return a2;
  }
  sub_180007F5C(v89);
  sub_180007F5C(v88);
  sub_180007F5C(v87);
  return a2;
}

```

## disassembly

```asm
0x18003dfec  push    rbp
0x18003dfee  push    rbx
0x18003dfef  push    rsi
0x18003dff0  push    rdi
0x18003dff1  push    r12
0x18003dff3  push    r13
0x18003dff5  push    r14
0x18003dff7  push    r15
0x18003dff9  lea     rbp, [rsp-3C8h]
0x18003e001  sub     rsp, 4C8h
0x18003e008  mov     rax, cs:__security_cookie
0x18003e00f  xor     rax, rsp
0x18003e012  mov     [rbp+400h+var_50], rax
0x18003e019  mov     r15, r9
0x18003e01c  mov     rbx, r8
0x18003e01f  mov     r14, rdx
0x18003e022  mov     r13, rcx
0x18003e025  mov     rsi, [rbp+400h+arg_20]
0x18003e02c  mov     qword ptr [rbp+400h+var_450], rsi
0x18003e030  xor     r12d, r12d
0x18003e033  mov     dword ptr [rsp+500h+var_4A8], r12d
0x18003e038  xorps   xmm0, xmm0
0x18003e03b  movups  [rbp+400h+var_2A0], xmm0
0x18003e042  xorps   xmm1, xmm1
0x18003e045  movdqu  [rbp+400h+var_290], xmm1
0x18003e04d  lea     r8d, [r12+0Ah]
0x18003e052  lea     rdx, aRemotedata; "RemoteData"
0x18003e059  lea     rcx, [rbp+400h+var_2A0]
0x18003e060  call    sub_180004678
0x18003e065  lea     r9, [rbp+400h+var_2A0]
0x18003e06c  mov     r8, rbx
0x18003e06f  lea     rdx, [rbp+400h+var_200]
0x18003e076  mov     rcx, r13
0x18003e079  call    sub_1800E4920
0x18003e07e  lea     rcx, [rbp+400h+var_2A0]
0x18003e085  call    sub_180007F5C
0x18003e08a  cmp     [rbp+400h+var_188], r12b
0x18003e091  jnz     short loc_18003E0BF
0x18003e093  lea     rdx, [rbp+400h+var_200]
0x18003e09a  mov     rcx, r14
0x18003e09d  call    sub_18000BC94
0x18003e0a2  mov     [r14+78h], r12b
0x18003e0a6  cmp     [rbp+400h+var_188], r12b
0x18003e0ad  jz      loc_18003EA7E
0x18003e0b3  lea     rcx, [rbp+400h+var_200]
0x18003e0ba  jmp     loc_18003EF64
0x18003e0bf  movaps  xmm2, [rbp+400h+var_200]
0x18003e0c6  movups  [rbp+400h+var_408], xmm2
0x18003e0ca  movaps  xmm3, [rbp+400h+var_1F0]
0x18003e0d1  movups  [rbp+400h+var_3F8], xmm3
0x18003e0d5  movdqa  xmm0, cs:xmmword_180149C10
0x18003e0dd  movdqa  [rbp+400h+var_1F0], xmm0
0x18003e0e5  mov     word ptr [rbp+400h+var_200], r12w
0x18003e0ed  mov     byte ptr [rbp+400h+var_260], r12b
0x18003e0f4  xorps   xmm0, xmm0
0x18003e0f7  movups  [rbp+400h+var_250], xmm0
0x18003e0fe  xorps   xmm1, xmm1
0x18003e101  movdqa  [rbp+400h+var_240], xmm1
0x18003e109  lea     rdx, [rbp+400h+var_408]
0x18003e10d  movq    rcx, xmm2
0x18003e112  movdqa  xmm0, xmm3
0x18003e116  psrldq  xmm0, 8
0x18003e11b  movq    rax, xmm0
0x18003e120  cmp     rax, 7
0x18003e124  cmova   rdx, rcx
0x18003e128  movq    r8, xmm3
0x18003e12d  lea     rcx, [rbp+400h+var_250]
0x18003e134  call    sub_1800096E8
0x18003e139  mov     [rbp+400h+var_210], r12b
0x18003e140  cmp     byte ptr [rbp+400h+var_260], r12b
0x18003e147  jz      short loc_18003E1A4
0x18003e149  xorps   xmm0, xmm0
0x18003e14c  movups  [rbp+400h+var_230], xmm0
0x18003e153  xorps   xmm1, xmm1
0x18003e156  movdqa  [rbp+400h+var_220], xmm1
0x18003e15e  lea     rdx, [rbp+400h+var_280]
0x18003e165  cmp     [rbp+400h+var_268], 7
0x18003e16d  cmova   rdx, [rbp+400h+var_280]
0x18003e175  mov     r8, [rbp+400h+var_270]
0x18003e17c  lea     rcx, [rbp+400h+var_230]
0x18003e183  call    sub_1800096E8
0x18003e188  mov     [rbp+400h+var_210], 1
0x18003e18f  cmp     byte ptr [rbp+400h+var_260], r12b
0x18003e196  jz      short loc_18003E1A4
0x18003e198  lea     rcx, [rbp+400h+var_280]
0x18003e19f  call    sub_1800106B8
0x18003e1a4  xor     edx, edx
0x18003e1a6  mov     r8d, 80h
0x18003e1ac  lea     rcx, [rbp+400h+var_150]
0x18003e1b3  call    sub_18013BF50
0x18003e1b8  lea     rcx, [rbp+400h+var_150]
0x18003e1bf  call    sub_18003563C
0x18003e1c4  cmp     [rbp+400h+var_D8], r12b
0x18003e1cb  jnz     short loc_18003E24C
0x18003e1cd  lea     rdx, [rbp+400h+var_150]
0x18003e1d4  mov     rcx, r14
0x18003e1d7  call    sub_18000BC94
0x18003e1dc  mov     [r14+78h], r12b
0x18003e1e0  cmp     [rbp+400h+var_D8], r12b
0x18003e1e7  jz      short loc_18003E1F9
0x18003e1e9  xor     edx, edx
0x18003e1eb  lea     rcx, [rbp+400h+var_150]
0x18003e1f2  call    sub_18002D550
0x18003e1f7  jmp     short loc_18003E21D
0x18003e1f9  lea     rcx, [rbp+400h+var_F8]
0x18003e200  call    sub_180007F5C
0x18003e205  lea     rcx, [rbp+400h+var_118]
0x18003e20c  call    sub_180007F5C
0x18003e211  lea     rcx, [rbp+400h+var_140]
0x18003e218  call    sub_180007F5C
0x18003e21d  cmp     [rbp+400h+var_210], r12b
0x18003e224  jz      short loc_18003E232
0x18003e226  lea     rcx, [rbp+400h+var_230]
0x18003e22d  call    sub_1800106B8
0x18003e232  lea     rcx, [rbp+400h+var_250]
0x18003e239  call    sub_1800106B8
0x18003e23e  lea     rcx, [rbp+400h+var_408]
0x18003e242  call    sub_1800106B8
0x18003e247  jmp     loc_18003E0A6
0x18003e24c  mov     rax, [rbp+400h+var_150]
0x18003e253  mov     [rbp+400h+var_180], rax
0x18003e25a  mov     rax, [rbp+400h+var_148]
0x18003e261  mov     [rbp+400h+var_178], rax
0x18003e268  mov     rax, [rbp+400h+var_140]
0x18003e26f  mov     [rbp+400h+var_170], rax
0x18003e276  mov     rax, [rbp+400h+var_138]
0x18003e27d  mov     [rbp+400h+var_168], rax
0x18003e284  mov     rax, [rbp+400h+var_130]
0x18003e28b  mov     [rbp+400h+var_160], rax
0x18003e292  mov     [rbp+400h+var_138], r12
0x18003e299  mov     [rbp+400h+var_130], r12
0x18003e2a0  mov     rax, [r15+8]
0x18003e2a4  test    rax, rax
0x18003e2a7  jz      short loc_18003E2AD
0x18003e2a9  lock inc dword ptr [rax+8]
0x18003e2ad  mov     rax, [r15]
0x18003e2b0  mov     [rsp+500h+var_4A0], rax
0x18003e2b5  mov     rax, [r15+8]
0x18003e2b9  mov     [rsp+500h+var_498], rax
0x18003e2be  mov     [rsp+500h+var_4A8], r12
0x18003e2c3  mov     [rsp+500h+var_488], r12b
0x18003e2c8  lea     r8, aF95ba787499ab4; "F95BA787499AB4FA9EFFF472CE383A14"
0x18003e2cf  lea     rdx, [rbp+400h+var_180]
0x18003e2d6  lea     rcx, [rbp+400h+var_430]
0x18003e2da  call    sub_180023968
0x18003e2df  mov     [rsp+500h+var_4B8], r12b
0x18003e2e4  mov     [rsp+500h+var_4C0], rsi
0x18003e2e9  lea     rcx, [rsp+500h+var_4A0]
0x18003e2ee  mov     [rsp+500h+var_4C8], rcx
0x18003e2f3  lea     rcx, [rsp+500h+var_4A8]
0x18003e2f8  mov     [rsp+500h+var_4D0], rcx
0x18003e2fd  lea     rcx, [rsp+500h+var_490]
0x18003e302  mov     [rsp+500h+var_4D8], rcx
0x18003e307  mov     [rsp+500h+var_4E0], rax
0x18003e30c  lea     r9, aCustomsettings; "customSettings"
0x18003e313  lea     r8, [rbp+400h+var_250]
0x18003e31a  lea     rdx, [rbp+400h+var_480]
0x18003e31e  mov     rcx, r13
0x18003e321  call    sub_180024CC0
0x18003e326  mov     rdx, rax
0x18003e329  lea     rcx, [r13+38h]
0x18003e32d  call    sub_18002C668
0x18003e332  or      esi, 0FFFFFFFFh
0x18003e335  mov     rbx, [rbp+400h+var_478]
0x18003e339  test    rbx, rbx
0x18003e33c  jz      short loc_18003E373
0x18003e33e  mov     eax, esi
0x18003e340  lock xadd [rbx+8], eax
0x18003e345  add     eax, esi
0x18003e347  jnz     short loc_18003E373
0x18003e349  mov     rax, [rbx]
0x18003e34c  mov     rcx, rbx
0x18003e34f  mov     rax, [rax]
0x18003e352  call    cs:__guard_dispatch_icall_fptr
0x18003e358  mov     eax, esi
0x18003e35a  lock xadd [rbx+0Ch], eax
0x18003e35f  add     eax, esi
0x18003e361  jnz     short loc_18003E373
0x18003e363  mov     rax, [rbx]
0x18003e366  mov     rcx, rbx
0x18003e369  mov     rax, [rax+8]
0x18003e36d  call    cs:__guard_dispatch_icall_fptr
0x18003e373  cmp     [r13+38h], r12
0x18003e377  jnz     loc_18003E5AE
0x18003e37d  mov     dword ptr [rsp+500h+var_4A8], r12d
0x18003e382  lea     r8, [rsp+500h+var_4B0]
0x18003e387  lea     rdx, [rsp+500h+var_4A8]
0x18003e38c  lea     rcx, [rbp+400h+var_3E8]
0x18003e390  call    sub_18000B710
0x18003e395  mov     byte ptr [rbp+400h+var_260], r12b
0x18003e39c  xorps   xmm0, xmm0
0x18003e39f  movups  [rbp+400h+var_470], xmm0
0x18003e3a3  xorps   xmm1, xmm1
0x18003e3a6  movdqu  [rbp+400h+var_460], xmm1
0x18003e3ab  mov     r8d, 18h
0x18003e3b1  lea     rdx, aNullcustomsett; "NullCustomSettingsHolder"
0x18003e3b8  lea     rcx, [rbp+400h+var_470]
0x18003e3bc  call    sub_180004678
0x18003e3c1  xorps   xmm0, xmm0
0x18003e3c4  movups  [rbp+400h+var_2A0], xmm0
0x18003e3cb  xorps   xmm1, xmm1
0x18003e3ce  movdqu  [rbp+400h+var_290], xmm1
0x18003e3d6  mov     r8d, 73h ; 's'
0x18003e3dc  lea     rdx, aThirdPartyWpCl_4; "../../../../third_party/wp.client/msint"...
0x18003e3e3  lea     rcx, [rbp+400h+var_2A0]
0x18003e3ea  call    sub_180004678
0x18003e3ef  lea     rax, [rbp+400h+var_3E8]
0x18003e3f3  mov     [rsp+500h+var_4C8], rax
0x18003e3f8  lea     rax, [rbp+400h+var_280]
0x18003e3ff  mov     [rsp+500h+var_4D0], rax
0x18003e404  mov     [rsp+500h+var_4D8], r12
0x18003e409  lea     rax, [rbp+400h+var_470]
0x18003e40d  mov     [rsp+500h+var_4E0], rax
0x18003e412  mov     r9d, 147h
0x18003e418  lea     r8, [rbp+400h+var_2A0]
0x18003e41f  mov     edx, 7Fh
0x18003e424  lea     rcx, [rbp+400h+var_320]
0x18003e42b  call    sub_18000C4C8
0x18003e430  mov     rcx, rax
0x18003e433  movups  xmm0, xmmword ptr [rax]
0x18003e436  movdqu  xmmword ptr [r14], xmm0
0x18003e43b  xorps   xmm0, xmm0
0x18003e43e  movups  xmmword ptr [r14+10h], xmm0
0x18003e443  mov     [r14+20h], r12
0x18003e447  mov     [r14+28h], r12
0x18003e44b  movups  xmm0, xmmword ptr [rax+10h]
0x18003e44f  movups  xmmword ptr [r14+10h], xmm0
0x18003e454  movups  xmm1, xmmword ptr [rax+20h]
0x18003e458  movups  xmmword ptr [r14+20h], xmm1
0x18003e45d  mov     [rax+20h], r12
0x18003e461  mov     edx, 0Fh
0x18003e466  mov     [rax+28h], rdx
0x18003e46a  mov     [rax+10h], r12b
0x18003e46e  mov     eax, [rax+30h]
0x18003e471  mov     [r14+30h], eax
0x18003e475  xorps   xmm0, xmm0
0x18003e478  movups  xmmword ptr [r14+38h], xmm0
0x18003e47d  mov     [r14+48h], r12
0x18003e481  mov     [r14+50h], r12
0x18003e485  movups  xmm0, xmmword ptr [rcx+38h]
0x18003e489  movups  xmmword ptr [r14+38h], xmm0
0x18003e48e  movups  xmm1, xmmword ptr [rcx+48h]
0x18003e492  movups  xmmword ptr [r14+48h], xmm1
0x18003e497  mov     [rcx+48h], r12
0x18003e49b  mov     [rcx+50h], rdx
0x18003e49f  mov     [rcx+38h], r12b
0x18003e4a3  xorps   xmm0, xmm0
0x18003e4a6  movups  xmmword ptr [r14+58h], xmm0
0x18003e4ab  mov     [r14+68h], r12
0x18003e4af  mov     [r14+70h], r12
0x18003e4b3  movups  xmm0, xmmword ptr [rcx+58h]
0x18003e4b7  movups  xmmword ptr [r14+58h], xmm0
0x18003e4bc  movups  xmm1, xmmword ptr [rcx+68h]
0x18003e4c0  movups  xmmword ptr [r14+68h], xmm1
0x18003e4c5  mov     [rcx+68h], r12
0x18003e4c9  mov     [rcx+70h], rdx
0x18003e4cd  mov     [rcx+58h], r12b
0x18003e4d1  mov     [r14+78h], r12b
0x18003e4d5  lea     rcx, [rbp+400h+var_2C8]
0x18003e4dc  call    sub_180007F5C
0x18003e4e1  lea     rcx, [rbp+400h+var_2E8]
0x18003e4e8  call    sub_180007F5C
0x18003e4ed  lea     rcx, [rbp+400h+var_310]
0x18003e4f4  call    sub_180007F5C
0x18003e4f9  lea     rcx, [rbp+400h+var_2A0]
0x18003e500  call    sub_180007F5C
0x18003e505  lea     rcx, [rbp+400h+var_470]
0x18003e509  call    sub_180007F5C
0x18003e50e  mov     rbx, [rbp+400h+var_160]
0x18003e515  test    rbx, rbx
0x18003e518  jz      short loc_18003E54F
0x18003e51a  mov     eax, esi
0x18003e51c  lock xadd [rbx+8], eax
0x18003e521  add     eax, esi
0x18003e523  jnz     short loc_18003E54F
0x18003e525  mov     rax, [rbx]
0x18003e528  mov     rcx, rbx
0x18003e52b  mov     rax, [rax]
0x18003e52e  call    cs:__guard_dispatch_icall_fptr
0x18003e534  mov     eax, esi
0x18003e536  lock xadd [rbx+0Ch], eax
0x18003e53b  add     eax, esi
0x18003e53d  jnz     short loc_18003E54F
0x18003e53f  mov     rax, [rbx]
0x18003e542  mov     rcx, rbx
0x18003e545  mov     rax, [rax+8]
0x18003e549  call    cs:__guard_dispatch_icall_fptr
0x18003e54f  cmp     [rbp+400h+var_D8], r12b
0x18003e556  jz      loc_18003E1F9
0x18003e55c  mov     rbx, [rbp+400h+var_130]
0x18003e563  test    rbx, rbx
0x18003e566  jz      loc_18003E21D
0x18003e56c  mov     eax, esi
0x18003e56e  lock xadd [rbx+8], eax
0x18003e573  add     eax, esi
0x18003e575  jnz     loc_18003E21D
0x18003e57b  mov     rax, [rbx]
0x18003e57e  mov     rcx, rbx
0x18003e581  mov     rax, [rax]
0x18003e584  call    cs:__guard_dispatch_icall_fptr
  ... truncated ...
```
