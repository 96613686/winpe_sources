# sub_1800DFC5C

- ea: `0x1800dfc5c`
- end: `0x1800e0655`
- name: `sub_1800DFC5C`
- size: `2553`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800421c4`

## callees

- `0x180004678`
- `0x180007f5c`
- `0x180009628`
- `0x18000b710`
- `0x18000eeac`
- `0x1800102f8`
- `0x180010448`
- `0x180014eb0`
- `0x180020270`
- `0x180028008`
- `0x18002951c`
- `0x180029634`
- `0x18002b350`
- `0x18002c040`
- `0x18003483c`
- `0x180038d88`
- `0x1800dec28`
- `0x1800df9e8`
- `0x1800dfc5c`
- `0x1800f4270`
- `0x1800fe870`
- `0x1800fee70`
- `0x18013bf50`

## string_xrefs

- `0x1800dfdf7`: `../../../../third_party/wp.client/msinternal/src/base/service/src/remote_data/cache_serializer.cpp`
- `0x1800dffc6`: `../../../../third_party/wp.client/msinternal/src/base/service/src/remote_data/cache_serializer.cpp`
- `0x1800e054f`: `../../../../third_party/wp.client/msinternal/src/base/service/src/remote_data/cache_serializer.cpp`
- `0x1800dfe27`: `SerializableUriCache::ParseFileStreamError`
- `0x1800e0578`: `SerializableUriCache::InvalidCacheVersion`
- `0x1800dff0c`: `/cache_data`
- `0x1800dfff8`: `SerializableUriCache::InvalidCacheData`

## pseudocode

```c
_OWORD *__fastcall sub_1800DFC5C(_OWORD *a1, _QWORD *a2)
{
  __int64 v4; // r8
  __int64 v5; // rax
  __int128 *v6; // rax
  _DWORD *v7; // rbx
  __int64 v8; // rbx
  __int64 v9; // rdi
  __int64 i; // r15
  __int64 *v11; // rbx
  __int64 v12; // rax
  unsigned int *v13; // rbx
  unsigned int v14; // r14d
  __int64 *v15; // rbx
  __int64 v16; // rax
  __int128 **v17; // rbx
  __int128 *v18; // rax
  __int64 v19; // rbx
  char v20; // al
  __int64 v21; // rax
  __int64 v22; // rbx
  __int128 *v23; // rdx
  __int128 *v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rbx
  _BYTE v28[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v29; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v30; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v31; // [rsp+58h] [rbp-A8h]
  __int64 v32; // [rsp+60h] [rbp-A0h]
  int v33; // [rsp+68h] [rbp-98h]
  int v34; // [rsp+78h] [rbp-88h]
  __int128 *v35; // [rsp+80h] [rbp-80h]
  __int128 v36; // [rsp+88h] [rbp-78h] BYREF
  __int64 v37; // [rsp+98h] [rbp-68h]
  __int64 v38; // [rsp+A0h] [rbp-60h]
  _OWORD *v39; // [rsp+A8h] [rbp-58h]
  _BYTE v40[40]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v41[40]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v42[40]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v43[208]; // [rsp+128h] [rbp+28h] BYREF
  char v44; // [rsp+1F8h] [rbp+F8h]
  __int128 *v45; // [rsp+200h] [rbp+100h] BYREF
  __int128 v46; // [rsp+208h] [rbp+108h] BYREF
  __int64 v47; // [rsp+218h] [rbp+118h]
  unsigned __int64 v48; // [rsp+220h] [rbp+120h]
  __int128 v49; // [rsp+228h] [rbp+128h] BYREF
  __int64 v50; // [rsp+238h] [rbp+138h]
  __int64 v51; // [rsp+240h] [rbp+140h]
  __int128 v52; // [rsp+248h] [rbp+148h] BYREF
  __int64 v53; // [rsp+258h] [rbp+158h]
  unsigned __int64 v54; // [rsp+260h] [rbp+160h]
  __int128 v55; // [rsp+268h] [rbp+168h] BYREF
  __int64 v56; // [rsp+278h] [rbp+178h]
  __int64 v57; // [rsp+280h] [rbp+180h]
  __int128 v58; // [rsp+288h] [rbp+188h] BYREF
  __int64 v59; // [rsp+298h] [rbp+198h]
  unsigned __int64 v60; // [rsp+2A0h] [rbp+1A0h]
  char v61; // [rsp+2A8h] [rbp+1A8h]
  __int128 v62; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int64 v63; // [rsp+2C0h] [rbp+1C0h]
  __int64 v64; // [rsp+2D0h] [rbp+1D0h]
  __int64 v65; // [rsp+2E0h] [rbp+1E0h]
  __int64 v66; // [rsp+2E8h] [rbp+1E8h]
  int v67; // [rsp+308h] [rbp+208h]

  v39 = a1;
  *a1 = 0;
  sub_1800DF9E8();
  v34 = 1;
  v4 = a2[2];
  v52 = 0;
  v53 = 0;
  v54 = 0;
  if ( *a2 == v4 )
  {
    v5 = 0;
    v53 = 0;
    v54 = 15;
    LOBYTE(v52) = 0;
  }
  else
  {
    sub_180004678(&v52, *a2, v4 - *a2);
    v5 = v53;
  }
  v34 = 3;
  if ( !v5 )
    goto LABEL_76;
  sub_18013BF50(&v62, 0, 104);
  sub_180028008((unsigned int)&v62, 3, 0, 1024, 0);
  v6 = &v52;
  if ( v54 > 0xF )
    v6 = (__int128 *)v52;
  *(_QWORD *)&v49 = v6;
  *((_QWORD *)&v49 + 1) = v6;
  sub_180020270(&v62, &v49);
  if ( v67 )
  {
    if ( !qword_18021BF90 || !*(_DWORD *)qword_18021BF90 )
      goto LABEL_73;
    LODWORD(v45) = 0;
    sub_18000B710(&v29, &v45, v28);
    v45 = &v46;
    v46 = 0;
    v47 = 0;
    v48 = 0;
    sub_180004678(
      &v46,
      "../../../../third_party/wp.client/msinternal/src/base/service/src/remote_data/cache_serializer.cpp",
      98);
    v49 = 0;
    v50 = 0;
    v51 = 0;
    sub_180004678(&v49, "SerializableUriCache::ParseFileStreamError", 42);
    sub_18000EEAC((unsigned int)&qword_18021BF90, (unsigned int)&v49, (unsigned int)&v46, 29, (__int64)&v29);
    goto LABEL_72;
  }
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  sub_180038D88(&v29, "/version", 8);
  v7 = (_DWORD *)sub_18003483C(&v29, &v62, 0);
  if ( (_QWORD)v30 )
    FreeExperience_0(*((_QWORD *)&v30 + 1));
  FreeExperience(*((_QWORD *)&v29 + 1));
  if ( !v7 || *v7 != 1 )
  {
    if ( !qword_18021BF90 || !*(_DWORD *)qword_18021BF90 )
      goto LABEL_73;
    LODWORD(v45) = 0;
    sub_18000B710(&v29, &v45, v28);
    *(_QWORD *)&v49 = &v55;
    v55 = 0;
    v56 = 0;
    v57 = 0;
    sub_180004678(
      &v55,
      "../../../../third_party/wp.client/msinternal/src/base/service/src/remote_data/cache_serializer.cpp",
      98);
    v36 = 0;
    v37 = 0;
    v38 = 0;
    sub_180004678(&v36, "SerializableUriCache::InvalidCacheVersion", 41);
    sub_18000EEAC((unsigned int)&qword_18021BF90, (unsigned int)&v36, (unsigned int)&v55, 38, (__int64)&v29);
    goto LABEL_72;
  }
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  sub_180038D88(&v29, "/cache_data", 11);
  v8 = sub_18003483C(&v29, &v62, 0);
  if ( (_QWORD)v30 )
    FreeExperience_0(*((_QWORD *)&v30 + 1));
  FreeExperience(*((_QWORD *)&v29 + 1));
  if ( !v8 )
    goto LABEL_73;
  if ( *(_WORD *)(v8 + 22) == 4 )
  {
    v9 = *(_QWORD *)(v8 + 16) & 0xFFFFFFFFFFFFLL;
    for ( i = v9 + 24LL * *(_QWORD *)v8; v9 != i; v9 += 24 )
    {
      v29 = 0;
      v30 = 0;
      v31 = 0;
      v32 = 0;
      v33 = 0;
      sub_180038D88(&v29, "/file_hash", 10);
      v11 = (__int64 *)sub_18003483C(&v29, v9, 0);
      if ( (_QWORD)v30 )
        FreeExperience_0(*((_QWORD *)&v30 + 1));
      FreeExperience(*((_QWORD *)&v29 + 1));
      if ( v11 )
      {
        if ( (*((_WORD *)v11 + 11) & 0x1000) == 0 )
          v11 = (__int64 *)(v11[2] & 0xFFFFFFFFFFFFLL);
      }
      else
      {
        v11 = &qword_180149390;
      }
      v55 = 0;
      v56 = 0;
      v57 = 0;
      v12 = sub_1800FE870(v11);
      sub_180004678(&v55, v11, v12);
      v29 = 0;
      v30 = 0;
      v31 = 0;
      v32 = 0;
      v33 = 0;
      sub_180038D88(&v29, "/result", 7);
      v13 = (unsigned int *)sub_18003483C(&v29, v9, 0);
      if ( (_QWORD)v30 )
        FreeExperience_0(*((_QWORD *)&v30 + 1));
      FreeExperience(*((_QWORD *)&v29 + 1));
      if ( v13 )
        v14 = *v13;
      else
        v14 = 0;
      v29 = 0;
      v30 = 0;
      v31 = 0;
      v32 = 0;
      v33 = 0;
      sub_180038D88(&v29, "/server_context", 15);
      v15 = (__int64 *)sub_18003483C(&v29, v9, 0);
      if ( (_QWORD)v30 )
        FreeExperience_0(*((_QWORD *)&v30 + 1));
      FreeExperience(*((_QWORD *)&v29 + 1));
      if ( v15 )
      {
        if ( (*((_WORD *)v15 + 11) & 0x1000) == 0 )
          v15 = (__int64 *)(v15[2] & 0xFFFFFFFFFFFFLL);
      }
      else
      {
        v15 = &qword_180149390;
      }
      v46 = 0;
      v47 = 0;
      v48 = 0;
      v16 = sub_1800FE870(v15);
      sub_180004678(&v46, v15, v16);
      v29 = 0;
      v30 = 0;
      v31 = 0;
      v32 = 0;
      v33 = 0;
      sub_180038D88(&v29, "/expiration_time", 16);
      v17 = (__int128 **)sub_18003483C(&v29, v9, 0);
      if ( (_QWORD)v30 )
        FreeExperience_0(*((_QWORD *)&v30 + 1));
      FreeExperience(*((_QWORD *)&v29 + 1));
      if ( v17 )
        v18 = *v17;
      else
        v18 = 0;
      v45 = v18;
      v29 = 0;
      v30 = 0;
      v31 = 0;
      v32 = 0;
      v33 = 0;
      sub_180038D88(&v29, "/response_category", 18);
      v19 = sub_18003483C(&v29, v9, 0);
      if ( (_QWORD)v30 )
        FreeExperience_0(*((_QWORD *)&v30 + 1));
      FreeExperience(*((_QWORD *)&v29 + 1));
      v20 = 0;
      v61 = 0;
      if ( v19 )
      {
        if ( (*(_WORD *)(v19 + 22) & 0x1000) == 0 )
          v19 = *(_QWORD *)(v19 + 16) & 0xFFFFFFFFFFFFLL;
        v58 = 0;
        v59 = 0;
        v60 = 0;
        v21 = sub_1800FE870(v19);
        sub_180004678(&v58, v19, v21);
        v20 = 1;
        v61 = 1;
      }
      v22 = *(_QWORD *)a1;
      v35 = &v29;
      LOBYTE(v31) = 0;
      if ( v20 )
      {
        v29 = 0;
        v30 = 0u;
        v23 = &v58;
        if ( v60 > 0xF )
          v23 = (__int128 *)v58;
        sub_180009628(&v29, v23, v59);
        LOBYTE(v31) = 1;
      }
      v36 = 0;
      v37 = 0;
      v38 = 0;
      v24 = &v46;
      if ( v48 > 0xF )
        v24 = (__int128 *)v46;
      sub_180009628(&v36, v24, v47);
      v25 = sub_180029634(v40, &v36, v14, &v29);
      sub_18002951C(v42, v25);
      v44 = 0;
      sub_1800DEC28(v22, &v55, v42, &v45);
      if ( v44 != -1 )
      {
        if ( v44 )
        {
          sub_18002C040(v42);
        }
        else
        {
          if ( v43[32] )
            sub_180007F5C(v43);
          sub_180007F5C(v42);
        }
      }
      if ( v41[32] )
        sub_180007F5C(v41);
      sub_180007F5C(v40);
      if ( v61 )
        sub_180007F5C(&v58);
      sub_180007F5C(&v46);
      sub_180007F5C(&v55);
    }
    goto LABEL_73;
  }
  if ( qword_18021BF90 && *(_DWORD *)qword_18021BF90 )
  {
    LODWORD(v45) = 0;
    sub_18000B710(&v29, &v45, v28);
    v35 = &v46;
    v46 = 0;
    v47 = 0;
    v48 = 0;
    sub_180004678(
      &v46,
      "../../../../third_party/wp.client/msinternal/src/base/service/src/remote_data/cache_serializer.cpp",
      98);
    v49 = 0;
    v50 = 0;
    v51 = 0;
    sub_180004678(&v49, "SerializableUriCache::InvalidCacheData", 38);
    sub_18000EEAC((unsigned int)&qword_18021BF90, (unsigned int)&v49, (unsigned int)&v46, 47, (__int64)&v29);
LABEL_72:
    sub_1800102F8((char *)&v30 + 8);
    sub_180010448((char *)&v29 + 8);
  }
LABEL_73:
  v26 = v64;
  if ( v64 )
  {
    v63 = 0;
    v62 = 0;
    sub_18002B350(v64);
    FreeExperience(v26);
  }
  FreeExperience_0(v66);
  FreeExperience(v65);
LABEL_76:
  sub_180007F5C(&v52);
  return a1;
}

```

## disassembly

```asm
0x1800dfc5c  mov     [rsp-8+arg_10], rbx
0x1800dfc61  push    rbp
0x1800dfc62  push    rsi
0x1800dfc63  push    rdi
0x1800dfc64  push    r12
0x1800dfc66  push    r13
0x1800dfc68  push    r14
0x1800dfc6a  push    r15
0x1800dfc6c  lea     rbp, [rsp-230h]
0x1800dfc74  sub     rsp, 330h
0x1800dfc7b  mov     rax, cs:__security_cookie
0x1800dfc82  xor     rax, rsp
0x1800dfc85  mov     [rbp+260h+var_40], rax
0x1800dfc8c  mov     rbx, rdx
0x1800dfc8f  mov     rsi, rcx
0x1800dfc92  mov     [rbp+260h+var_2B8], rcx
0x1800dfc96  mov     [rsp+360h+var_2E8], 1
0x1800dfc9e  xorps   xmm0, xmm0
0x1800dfca1  movups  xmmword ptr [rcx], xmm0
0x1800dfca4  call    sub_1800DF9E8
0x1800dfca9  nop
0x1800dfcaa  mov     [rsp+360h+var_2E8], 1
0x1800dfcb2  mov     r8, [rbx+10h]
0x1800dfcb6  xorps   xmm0, xmm0
0x1800dfcb9  movups  [rbp+260h+var_118], xmm0
0x1800dfcc0  xor     r12d, r12d
0x1800dfcc3  mov     [rbp+260h+var_108], r12
0x1800dfcca  mov     [rbp+260h+var_100], r12
0x1800dfcd1  cmp     [rbx], r8
0x1800dfcd4  jnz     short loc_1800DFCF4
0x1800dfcd6  mov     eax, r12d
0x1800dfcd9  mov     [rbp+260h+var_108], rax
0x1800dfce0  mov     [rbp+260h+var_100], 0Fh
0x1800dfceb  mov     byte ptr [rbp+260h+var_118], r12b
0x1800dfcf2  jmp     short loc_1800DFD0D
0x1800dfcf4  sub     r8, [rbx]
0x1800dfcf7  mov     rdx, [rbx]
0x1800dfcfa  lea     rcx, [rbp+260h+var_118]
0x1800dfd01  call    sub_180004678
0x1800dfd06  mov     rax, [rbp+260h+var_108]
0x1800dfd0d  mov     ebx, 3
0x1800dfd12  mov     [rsp+360h+var_2E8], ebx
0x1800dfd16  test    rax, rax
0x1800dfd19  jz      loc_1800E061B
0x1800dfd1f  xor     edx, edx
0x1800dfd21  lea     r8d, [rbx+65h]
0x1800dfd25  lea     rcx, [rbp+260h+var_B0]
0x1800dfd2c  call    sub_18013BF50
0x1800dfd31  mov     [rsp+360h+var_340], r12
0x1800dfd36  mov     r9d, 400h
0x1800dfd3c  xor     r8d, r8d
0x1800dfd3f  mov     edx, ebx
0x1800dfd41  lea     rcx, [rbp+260h+var_B0]
0x1800dfd48  call    sub_180028008
0x1800dfd4d  nop
0x1800dfd4e  lea     rax, [rbp+260h+var_118]
0x1800dfd55  cmp     [rbp+260h+var_100], 0Fh
0x1800dfd5d  cmova   rax, qword ptr [rbp+260h+var_118]
0x1800dfd65  mov     qword ptr [rbp+260h+var_138], rax
0x1800dfd6c  mov     qword ptr [rbp+260h+var_138+8], rax
0x1800dfd73  lea     rdx, [rbp+260h+var_138]
0x1800dfd7a  lea     rcx, [rbp+260h+var_B0]
0x1800dfd81  call    sub_180020270
0x1800dfd86  cmp     [rbp+260h+var_58], r12d
0x1800dfd8d  jz      loc_1800DFE69
0x1800dfd93  mov     rax, cs:qword_18021BF90
0x1800dfd9a  test    rax, rax
0x1800dfd9d  jz      loc_1800E05C6
0x1800dfda3  cmp     [rax], r12d
0x1800dfda6  jbe     loc_1800E05C6
0x1800dfdac  mov     dword ptr [rbp+260h+var_160], 0
0x1800dfdb6  lea     r8, [rsp+360h+var_330]
0x1800dfdbb  lea     rdx, [rbp+260h+var_160]
0x1800dfdc2  lea     rcx, [rsp+360h+var_328]
0x1800dfdc7  call    sub_18000B710
0x1800dfdcc  nop
0x1800dfdcd  lea     rax, [rbp+260h+var_158]
0x1800dfdd4  mov     [rbp+260h+var_160], rax
0x1800dfddb  xorps   xmm0, xmm0
0x1800dfdde  movups  [rbp+260h+var_158], xmm0
0x1800dfde5  mov     [rbp+260h+var_148], r12
0x1800dfdec  mov     [rbp+260h+var_140], r12
0x1800dfdf3  lea     r8d, [rbx+5Fh]
0x1800dfdf7  lea     rdx, aThirdPartyWpCl_48; "../../../../third_party/wp.client/msint"...
0x1800dfdfe  lea     rcx, [rbp+260h+var_158]
0x1800dfe05  call    sub_180004678
0x1800dfe0a  nop
0x1800dfe0b  xorps   xmm0, xmm0
0x1800dfe0e  movups  [rbp+260h+var_138], xmm0
0x1800dfe15  mov     [rbp+260h+var_128], r12
0x1800dfe1c  mov     [rbp+260h+var_120], r12
0x1800dfe23  lea     r8d, [rbx+27h]
0x1800dfe27  lea     rdx, aSerializableur; "SerializableUriCache::ParseFileStreamEr"...
0x1800dfe2e  lea     rcx, [rbp+260h+var_138]
0x1800dfe35  call    sub_180004678
0x1800dfe3a  nop
0x1800dfe3b  lea     rax, [rsp+360h+var_328]
0x1800dfe40  mov     [rsp+360h+var_340], rax
0x1800dfe45  lea     r9d, [rbx+1Ah]
0x1800dfe49  lea     r8, [rbp+260h+var_158]
0x1800dfe50  lea     rdx, [rbp+260h+var_138]
0x1800dfe57  lea     rcx, qword_18021BF90
0x1800dfe5e  call    sub_18000EEAC
0x1800dfe63  nop
0x1800dfe64  jmp     loc_1800E05B1
0x1800dfe69  xorps   xmm0, xmm0
0x1800dfe6c  movdqu  [rsp+360h+var_328], xmm0
0x1800dfe72  xorps   xmm1, xmm1
0x1800dfe75  movdqu  [rsp+360h+var_318], xmm1
0x1800dfe7b  mov     [rsp+360h+var_308], r12
0x1800dfe80  mov     [rsp+360h+var_300], r12
0x1800dfe85  mov     [rsp+360h+var_2F8], r12d
0x1800dfe8a  mov     r8d, 8
0x1800dfe90  lea     rdx, aVersion_1; "/version"
0x1800dfe97  lea     rcx, [rsp+360h+var_328]
0x1800dfe9c  call    sub_180038D88
0x1800dfea1  xor     r8d, r8d
0x1800dfea4  lea     rdx, [rbp+260h+var_B0]
0x1800dfeab  lea     rcx, [rsp+360h+var_328]
0x1800dfeb0  call    sub_18003483C
0x1800dfeb5  mov     rbx, rax
0x1800dfeb8  cmp     qword ptr [rsp+360h+var_318], r12
0x1800dfebd  jz      short loc_1800DFEC9
0x1800dfebf  mov     rcx, qword ptr [rsp+360h+var_318+8]
0x1800dfec4  call    FreeExperience_0
0x1800dfec9  mov     rcx, qword ptr [rsp+360h+var_328+8]
0x1800dfece  call    FreeExperience
0x1800dfed3  test    rbx, rbx
0x1800dfed6  jz      loc_1800E04E9
0x1800dfedc  cmp     dword ptr [rbx], 1
0x1800dfedf  jnz     loc_1800E04E9
0x1800dfee5  xorps   xmm0, xmm0
0x1800dfee8  movdqu  [rsp+360h+var_328], xmm0
0x1800dfeee  xorps   xmm1, xmm1
0x1800dfef1  movdqu  [rsp+360h+var_318], xmm1
0x1800dfef7  mov     [rsp+360h+var_308], r12
0x1800dfefc  mov     [rsp+360h+var_300], r12
0x1800dff01  mov     [rsp+360h+var_2F8], r12d
0x1800dff06  mov     r8d, 0Bh
0x1800dff0c  lea     rdx, aCacheData; "/cache_data"
0x1800dff13  lea     rcx, [rsp+360h+var_328]
0x1800dff18  call    sub_180038D88
0x1800dff1d  xor     r8d, r8d
0x1800dff20  lea     rdx, [rbp+260h+var_B0]
0x1800dff27  lea     rcx, [rsp+360h+var_328]
0x1800dff2c  call    sub_18003483C
0x1800dff31  mov     rbx, rax
0x1800dff34  cmp     qword ptr [rsp+360h+var_318], r12
0x1800dff39  jz      short loc_1800DFF45
0x1800dff3b  mov     rcx, qword ptr [rsp+360h+var_318+8]
0x1800dff40  call    FreeExperience_0
0x1800dff45  mov     rcx, qword ptr [rsp+360h+var_328+8]
0x1800dff4a  call    FreeExperience
0x1800dff4f  test    rbx, rbx
0x1800dff52  jz      loc_1800E05C6
0x1800dff58  cmp     word ptr [rbx+16h], 4
0x1800dff5d  jz      loc_1800E003C
0x1800dff63  mov     rax, cs:qword_18021BF90
0x1800dff6a  test    rax, rax
0x1800dff6d  jz      loc_1800E05C6
0x1800dff73  cmp     [rax], r12d
0x1800dff76  jbe     loc_1800E05C6
0x1800dff7c  mov     dword ptr [rbp+260h+var_160], 0
0x1800dff86  lea     r8, [rsp+360h+var_330]
0x1800dff8b  lea     rdx, [rbp+260h+var_160]
0x1800dff92  lea     rcx, [rsp+360h+var_328]
0x1800dff97  call    sub_18000B710
0x1800dff9c  nop
0x1800dff9d  lea     rax, [rbp+260h+var_158]
0x1800dffa4  mov     [rbp+260h+var_2E0], rax
0x1800dffa8  xorps   xmm0, xmm0
0x1800dffab  movups  [rbp+260h+var_158], xmm0
0x1800dffb2  mov     [rbp+260h+var_148], r12
0x1800dffb9  mov     [rbp+260h+var_140], r12
0x1800dffc0  mov     r8d, 62h ; 'b'
0x1800dffc6  lea     rdx, aThirdPartyWpCl_48; "../../../../third_party/wp.client/msint"...
0x1800dffcd  lea     rcx, [rbp+260h+var_158]
0x1800dffd4  call    sub_180004678
0x1800dffd9  nop
0x1800dffda  xorps   xmm0, xmm0
0x1800dffdd  movups  [rbp+260h+var_138], xmm0
0x1800dffe4  mov     [rbp+260h+var_128], r12
0x1800dffeb  mov     [rbp+260h+var_120], r12
0x1800dfff2  mov     r8d, 26h ; '&'
0x1800dfff8  lea     rdx, aSerializableur_0; "SerializableUriCache::InvalidCacheData"
0x1800dffff  lea     rcx, [rbp+260h+var_138]
0x1800e0006  call    sub_180004678
0x1800e000b  nop
0x1800e000c  lea     rax, [rsp+360h+var_328]
0x1800e0011  mov     [rsp+360h+var_340], rax
0x1800e0016  mov     r9d, 2Fh ; '/'
0x1800e001c  lea     r8, [rbp+260h+var_158]
0x1800e0023  lea     rdx, [rbp+260h+var_138]
0x1800e002a  lea     rcx, qword_18021BF90
0x1800e0031  call    sub_18000EEAC
0x1800e0036  nop
0x1800e0037  jmp     loc_1800E05B1
0x1800e003c  mov     r13, 0FFFFFFFFFFFFh
0x1800e0046  mov     rdi, [rbx+10h]
0x1800e004a  and     rdi, r13
0x1800e004d  mov     rax, [rbx]
0x1800e0050  lea     rcx, [rax+rax*2]
0x1800e0054  lea     r15, [rdi+rcx*8]
0x1800e0058  cmp     rdi, r15
0x1800e005b  jz      loc_1800E05C6
0x1800e0061  mov     r14d, 1000h
0x1800e0067  xorps   xmm0, xmm0
0x1800e006a  movdqu  [rsp+360h+var_328], xmm0
0x1800e0070  xorps   xmm1, xmm1
0x1800e0073  movdqu  [rsp+360h+var_318], xmm1
0x1800e0079  mov     [rsp+360h+var_308], r12
0x1800e007e  mov     [rsp+360h+var_300], r12
0x1800e0083  mov     [rsp+360h+var_2F8], r12d
0x1800e0088  mov     r8d, 0Ah
0x1800e008e  lea     rdx, aFileHash; "/file_hash"
0x1800e0095  lea     rcx, [rsp+360h+var_328]
0x1800e009a  call    sub_180038D88
0x1800e009f  xor     r8d, r8d
0x1800e00a2  mov     rdx, rdi
0x1800e00a5  lea     rcx, [rsp+360h+var_328]
0x1800e00aa  call    sub_18003483C
0x1800e00af  mov     rbx, rax
0x1800e00b2  cmp     qword ptr [rsp+360h+var_318], r12
0x1800e00b7  jz      short loc_1800E00C3
0x1800e00b9  mov     rcx, qword ptr [rsp+360h+var_318+8]
0x1800e00be  call    FreeExperience_0
0x1800e00c3  mov     rcx, qword ptr [rsp+360h+var_328+8]
0x1800e00c8  call    FreeExperience
0x1800e00cd  test    rbx, rbx
0x1800e00d0  jz      short loc_1800E00E2
0x1800e00d2  test    [rbx+16h], r14w
0x1800e00d7  jnz     short loc_1800E00E9
0x1800e00d9  mov     rbx, [rbx+10h]
0x1800e00dd  and     rbx, r13
0x1800e00e0  jmp     short loc_1800E00E9
0x1800e00e2  lea     rbx, qword_180149390
0x1800e00e9  xorps   xmm0, xmm0
0x1800e00ec  movups  [rbp+260h+var_F8], xmm0
0x1800e00f3  mov     [rbp+260h+var_E8], r12
0x1800e00fa  mov     [rbp+260h+var_E0], r12
0x1800e0101  mov     rcx, rbx
0x1800e0104  call    sub_1800FE870
0x1800e0109  mov     r8, rax
0x1800e010c  mov     rdx, rbx
0x1800e010f  lea     rcx, [rbp+260h+var_F8]
0x1800e0116  call    sub_180004678
0x1800e011b  nop
0x1800e011c  xorps   xmm0, xmm0
0x1800e011f  movdqu  [rsp+360h+var_328], xmm0
0x1800e0125  xorps   xmm1, xmm1
0x1800e0128  movdqu  [rsp+360h+var_318], xmm1
0x1800e012e  mov     [rsp+360h+var_308], r12
0x1800e0133  mov     [rsp+360h+var_300], r12
0x1800e0138  mov     [rsp+360h+var_2F8], r12d
0x1800e013d  mov     r8d, 7
0x1800e0143  lea     rdx, aResult; "/result"
0x1800e014a  lea     rcx, [rsp+360h+var_328]
0x1800e014f  call    sub_180038D88
0x1800e0154  xor     r8d, r8d
0x1800e0157  mov     rdx, rdi
0x1800e015a  lea     rcx, [rsp+360h+var_328]
0x1800e015f  call    sub_18003483C
0x1800e0164  mov     rbx, rax
0x1800e0167  cmp     qword ptr [rsp+360h+var_318], r12
0x1800e016c  jz      short loc_1800E0178
0x1800e016e  mov     rcx, qword ptr [rsp+360h+var_318+8]
0x1800e0173  call    FreeExperience_0
0x1800e0178  mov     rcx, qword ptr [rsp+360h+var_328+8]
0x1800e017d  call    FreeExperience
0x1800e0182  test    rbx, rbx
0x1800e0185  jz      short loc_1800E018C
0x1800e0187  mov     r14d, [rbx]
0x1800e018a  jmp     short loc_1800E018F
0x1800e018c  mov     r14d, r12d
0x1800e018f  xorps   xmm0, xmm0
0x1800e0192  movdqu  [rsp+360h+var_328], xmm0
0x1800e0198  xorps   xmm1, xmm1
0x1800e019b  movdqu  [rsp+360h+var_318], xmm1
0x1800e01a1  mov     [rsp+360h+var_308], r12
0x1800e01a6  mov     [rsp+360h+var_300], r12
0x1800e01ab  mov     [rsp+360h+var_2F8], r12d
0x1800e01b0  mov     r8d, 0Fh
0x1800e01b6  lea     rdx, aServerContext; "/server_context"
0x1800e01bd  lea     rcx, [rsp+360h+var_328]
0x1800e01c2  call    sub_180038D88
0x1800e01c7  xor     r8d, r8d
0x1800e01ca  mov     rdx, rdi
0x1800e01cd  lea     rcx, [rsp+360h+var_328]
0x1800e01d2  call    sub_18003483C
0x1800e01d7  mov     rbx, rax
0x1800e01da  cmp     qword ptr [rsp+360h+var_318], r12
0x1800e01df  jz      short loc_1800E01EB
0x1800e01e1  mov     rcx, qword ptr [rsp+360h+var_318+8]
0x1800e01e6  call    FreeExperience_0
0x1800e01eb  mov     rcx, qword ptr [rsp+360h+var_328+8]
0x1800e01f0  call    FreeExperience
0x1800e01f5  test    rbx, rbx
0x1800e01f8  jz      short loc_1800E020E
0x1800e01fa  mov     eax, 1000h
0x1800e01ff  test    [rbx+16h], ax
  ... truncated ...
```
