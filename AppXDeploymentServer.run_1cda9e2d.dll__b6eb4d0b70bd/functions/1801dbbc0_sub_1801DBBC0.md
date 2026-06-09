# sub_1801DBBC0

- ea: `0x1801dbbc0`
- end: `0x1801dc377`
- name: `sub_1801DBBC0`
- size: `1975`
- prototype: ``
- caller_count: `3`
- callee_count: `22`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800ce904`
- `0x1801e4714`
- `0x1801e7000`

## callees

- `0x18000dbbc`
- `0x18000f8d0`
- `0x180024b6c`
- `0x180028130`
- `0x180033c70`
- `0x1800358e4`
- `0x180037638`
- `0x180089ac8`
- `0x1800ab77c`
- `0x18010fb5c`
- `0x18011edd8`
- `0x180166f68`
- `0x180167f34`
- `0x18017d250`
- `0x1801dbaa4`
- `0x1801dbbc0`
- `0x1801e0298`
- `0x18034adc8`
- `0x18034af58`
- `0x18034b000`
- `0x18034b15c`
- `0x18034b370`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801dc0fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801dc10a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801dc1c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801dc1cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801dc23c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801dc265`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801dc0fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801dc10a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801dc1c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801dc1cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801dc23c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801dc265`

## string_xrefs

- `0x1801dbc05`: `onecore\admin\appmodel\packagemanager\server\appinstallerprocessor.cpp`
- `0x1801dbe86`: `onecore\admin\appmodel\packagemanager\server\appinstallerprocessor.cpp`
- `0x1801dc166`: `onecore\admin\appmodel\packagemanager\server\appinstallerprocessor.cpp`
- `0x1801dc19f`: `onecore\admin\appmodel\packagemanager\server\appinstallerprocessor.cpp`
- `0x1801dc203`: `onecore\admin\appmodel\packagemanager\server\appinstallerprocessor.cpp`
- `0x1801dc225`: `onecore\admin\appmodel\packagemanager\server\appinstallerprocessor.cpp`
- `0x1801dc24e`: `onecore\admin\appmodel\packagemanager\server\appinstallerprocessor.cpp`
- `0x1801dc277`: `onecore\admin\appmodel\packagemanager\server\appinstallerprocessor.cpp`
- `0x1801dc29e`: `onecore\admin\appmodel\packagemanager\server\appinstallerprocessor.cpp`
- `0x1801dc2c6`: `onecore\admin\appmodel\packagemanager\server\appinstallerprocessor.cpp`
- `0x1801dc2f3`: `onecore\admin\appmodel\packagemanager\server\appinstallerprocessor.cpp`
- `0x1801dc316`: `onecore\admin\appmodel\packagemanager\server\appinstallerprocessor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall sub_1801DBBC0(__int64 a1, __int64 a2, _QWORD *a3, unsigned int a4, __int64 a5, __int64 a6)
{
  __int64 v9; // r13
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  unsigned __int64 v13; // r14
  __int64 v14; // rax
  __int64 v15; // rdi
  __int64 v16; // r8
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 *v19; // rdx
  int v20; // eax
  __int64 v21; // rax
  struct _RTL_AVL_TABLE *v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rsi
  int v25; // eax
  int v26; // eax
  __int64 (__fastcall *v27)(__int64, __int64 *); // rbx
  int v28; // eax
  int v29; // eax
  unsigned int v30; // esi
  int v31; // eax
  int v32; // eax
  __int64 v33; // rcx
  int v34; // eax
  int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v40; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v41; // [rsp+60h] [rbp-A8h] BYREF
  LPVOID v42; // [rsp+68h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-98h] BYREF
  __int64 v44; // [rsp+78h] [rbp-90h] BYREF
  __int64 v45; // [rsp+80h] [rbp-88h] BYREF
  __int64 v46; // [rsp+88h] [rbp-80h] BYREF
  __int64 v47; // [rsp+90h] [rbp-78h] BYREF
  _QWORD v48[2]; // [rsp+98h] [rbp-70h] BYREF
  __int64 v49; // [rsp+A8h] [rbp-60h]
  int v50; // [rsp+B0h] [rbp-58h]
  __int64 v51; // [rsp+B8h] [rbp-50h]
  __int64 v52; // [rsp+C0h] [rbp-48h]
  __int128 v53; // [rsp+C8h] [rbp-40h]
  __int64 v54; // [rsp+D8h] [rbp-30h]
  __int64 v55; // [rsp+E0h] [rbp-28h]
  __int128 v56; // [rsp+E8h] [rbp-20h]
  _BYTE v57[8]; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v58; // [rsp+100h] [rbp-8h]
  _QWORD v59[2]; // [rsp+108h] [rbp+0h] BYREF
  __int64 v60; // [rsp+118h] [rbp+10h]
  int v61; // [rsp+120h] [rbp+18h]
  __int64 v62; // [rsp+128h] [rbp+20h]
  __int64 v63; // [rsp+130h] [rbp+28h]
  __int128 v64; // [rsp+138h] [rbp+30h]
  __int128 v65; // [rsp+148h] [rbp+40h]
  __int128 v66; // [rsp+158h] [rbp+50h]
  _QWORD v67[2]; // [rsp+168h] [rbp+60h] BYREF
  __int128 v68; // [rsp+178h] [rbp+70h]
  __int128 v69; // [rsp+188h] [rbp+80h]
  __int128 v70; // [rsp+198h] [rbp+90h]
  __int128 v71; // [rsp+1A8h] [rbp+A0h]
  __int128 v72; // [rsp+1B8h] [rbp+B0h]
  __int128 v73; // [rsp+1C8h] [rbp+C0h]
  __int128 v74; // [rsp+1D8h] [rbp+D0h]
  __int128 v75; // [rsp+1E8h] [rbp+E0h]
  void *retaddr; // [rsp+230h] [rbp+128h]
  int v78; // [rsp+248h] [rbp+140h] BYREF
  unsigned int v79; // [rsp+250h] [rbp+148h]

  v79 = a4;
  if ( a3[2] > 0x64u )
    return sub_18011EDD8(
             retaddr,
             2337,
             "onecore\\admin\\appmodel\\packagemanager\\server\\appinstallerprocessor.cpp",
             87);
  v9 = 0;
  v46 = 0;
  sub_18034ADC8(a6, a2, a4, &v46);
  LOBYTE(v78) = 0;
  v59[0] = 0;
  v59[1] = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v10 = sub_18034B15C(&v46, v59, &v78);
  v11 = v10;
  if ( v10 >= 0 )
  {
    while ( (_BYTE)v78 )
    {
      v10 = sub_18034B000(a6, a2, v60, v62, v61);
      v11 = v10;
      if ( v10 < 0 )
      {
        v12 = 2351;
        goto LABEL_28;
      }
      v10 = sub_18034B15C(&v46, v59, &v78);
      v11 = v10;
      if ( v10 < 0 )
      {
        v12 = 2353;
        goto LABEL_28;
      }
    }
    v13 = 0;
    v14 = a3[2];
    v58 = v14;
    while ( v13 != v14 )
    {
      if ( v13 < a3[2] )
      {
        _mm_lfence();
        v9 = *(_QWORD *)(*a3 + 8 * v13);
      }
      v15 = *(_QWORD *)(v9 + 8);
      v16 = 0;
      v17 = *(_QWORD *)(a1 + 152);
      if ( v17 )
      {
        v18 = *(_QWORD *)(v17 + 408);
        if ( v18 )
          v16 = sub_180089AC8(v18, v15, 0);
      }
      v39 = 0;
      v38 = 0;
      v19 = &v39;
      if ( v16 )
        v19 = 0;
      v20 = sub_18010FB5C(v15, 4, 0, 0, v16, (__int64)v19, (__int64)&v38);
      v11 = v20;
      if ( v20 < 0 )
      {
        v36 = 2369;
LABEL_59:
        sub_180024B6C(
          retaddr,
          v36,
          "onecore\\admin\\appmodel\\packagemanager\\server\\appinstallerprocessor.cpp",
          (unsigned int)v20);
        goto LABEL_60;
      }
      v21 = *(_QWORD *)(a1 + 152);
      if ( v21 )
      {
        v22 = *(struct _RTL_AVL_TABLE **)(v21 + 408);
        if ( v22 )
        {
          if ( v39 )
          {
            v20 = sub_180166F68(v22);
            v11 = v20;
            if ( v20 < 0 )
            {
              v36 = 2373;
              goto LABEL_59;
            }
          }
        }
      }
      v41 = 0;
      v23 = sub_1800AB77C(v57);
      sub_180167F34(&v41, v23);
      sub_18000DBBC(v57);
      v24 = v41;
      if ( !v41 )
      {
        v11 = -2147024882;
        sub_180024B6C(
          retaddr,
          2378,
          "onecore\\admin\\appmodel\\packagemanager\\server\\appinstallerprocessor.cpp",
          2147942414LL);
LABEL_57:
        sub_18000DBBC(&v41);
LABEL_60:
        sub_18000F8D0(v38);
        sub_180037638(&v39);
        goto LABEL_62;
      }
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v38 + 128LL))(v38) )
      {
        v44 = 0;
        v25 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v38 + 400LL))(v38, &v44);
        v11 = v25;
        if ( v25 < 0 )
        {
          sub_180024B6C(
            retaddr,
            2382,
            "onecore\\admin\\appmodel\\packagemanager\\server\\appinstallerprocessor.cpp",
            (unsigned int)v25);
          sub_18000DBBC(&v44);
          goto LABEL_57;
        }
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 72LL))(v24, v44);
        sub_18000DBBC(&v44);
      }
      else
      {
        v45 = 0;
        v26 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v38 + 408LL))(v38, &v45);
        v11 = v26;
        if ( v26 < 0 )
        {
          sub_180024B6C(
            retaddr,
            2388,
            "onecore\\admin\\appmodel\\packagemanager\\server\\appinstallerprocessor.cpp",
            (unsigned int)v26);
          sub_18000DBBC(&v45);
          goto LABEL_57;
        }
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 64LL))(v24, v45);
        sub_18000DBBC(&v45);
      }
      v40 = 0;
      v27 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 48LL);
      sub_18000DBBC(&v40);
      v28 = v27(v24, &v40);
      v11 = v28;
      if ( v28 < 0 )
      {
        sub_180024B6C(
          retaddr,
          2392,
          "onecore\\admin\\appmodel\\packagemanager\\server\\appinstallerprocessor.cpp",
          (unsigned int)v28);
        goto LABEL_54;
      }
      v48[0] = 0;
      v48[1] = 0;
      v49 = 0;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      v53 = 0;
      v55 = 0;
      v56 = 0;
      v54 = a2;
      v78 = 0;
      v29 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v40 + 32LL))(v40, &v78);
      v11 = v29;
      if ( v29 < 0 )
      {
        sub_180024B6C(
          retaddr,
          2398,
          "onecore\\admin\\appmodel\\packagemanager\\server\\appinstallerprocessor.cpp",
          (unsigned int)v29);
LABEL_52:
        sub_1801DBAA4(v48);
LABEL_54:
        sub_18000DBBC(&v40);
        goto LABEL_57;
      }
      v50 = v78;
      v30 = v79;
      LODWORD(v52) = v79;
      v42 = 0;
      v31 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v40 + 80LL))(v40, &v42);
      v11 = v31;
      if ( v31 < 0 )
      {
        sub_180024B6C(
          retaddr,
          2403,
          "onecore\\admin\\appmodel\\packagemanager\\server\\appinstallerprocessor.cpp",
          (unsigned int)v31);
        goto LABEL_50;
      }
      pv = 0;
      v32 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v40 + 40LL))(v40, &pv);
      v11 = v32;
      if ( v32 < 0 )
      {
        sub_180024B6C(
          retaddr,
          2406,
          "onecore\\admin\\appmodel\\packagemanager\\server\\appinstallerprocessor.cpp",
          (unsigned int)v32);
        goto LABEL_48;
      }
      v67[0] = 0;
      v67[1] = 0;
      v68 = 0;
      v69 = 0;
      v70 = 0;
      v71 = 0;
      v72 = 0;
      v73 = 0;
      v74 = 0;
      v75 = 0;
      v34 = sub_1801E0298(v33, a5, v42, pv, v67);
      v11 = v34;
      if ( v34 < 0 )
      {
        v37 = 2413;
        goto LABEL_46;
      }
      v49 = v67[0];
      LODWORD(v52) = v30;
      v35 = sub_18034B370(v48, *(_QWORD *)(v9 + 8));
      v11 = v35;
      v9 = 0;
      if ( v35 < 0 )
      {
        sub_180024B6C(
          retaddr,
          2416,
          "onecore\\admin\\appmodel\\packagemanager\\server\\appinstallerprocessor.cpp",
          (unsigned int)v35);
        sub_1800358E4(v67);
        CoTaskMemFree(pv);
        CoTaskMemFree(v42);
        sub_1801DBAA4(v48);
        sub_180028130(&unk_1804F8F38, &unk_180567C30);
        goto LABEL_54;
      }
      v47 = 0;
      v34 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v40 + 48LL))(v40, &v47);
      v11 = v34;
      if ( v34 < 0 )
      {
        v37 = 2419;
        goto LABEL_46;
      }
      v51 = v47;
      v34 = sub_18034AF58(v48, a6);
      v11 = v34;
      if ( v34 < 0 )
      {
        v37 = 2421;
LABEL_46:
        sub_180024B6C(
          retaddr,
          v37,
          "onecore\\admin\\appmodel\\packagemanager\\server\\appinstallerprocessor.cpp",
          (unsigned int)v34);
        sub_1800358E4(v67);
LABEL_48:
        CoTaskMemFree(pv);
LABEL_50:
        CoTaskMemFree(v42);
        goto LABEL_52;
      }
      sub_1800358E4(v67);
      CoTaskMemFree(pv);
      CoTaskMemFree(v42);
      sub_1801DBAA4(v48);
      sub_18000DBBC(&v40);
      sub_18000DBBC(&v41);
      sub_18000F8D0(v38);
      sub_180037638(&v39);
      ++v13;
      v14 = v58;
    }
    v11 = 0;
  }
  else
  {
    v12 = 2345;
LABEL_28:
    sub_180024B6C(
      retaddr,
      v12,
      "onecore\\admin\\appmodel\\packagemanager\\server\\appinstallerprocessor.cpp",
      (unsigned int)v10);
  }
LABEL_62:
  sub_1801DBAA4(v59);
  sub_180033C70(&v46);
  return v11;
}

```

## disassembly

```asm
0x1801dbbc0  mov     rax, rsp
0x1801dbbc3  mov     [rax+10h], rbx
0x1801dbbc7  mov     [rax+20h], r9d
0x1801dbbcb  mov     [rax+8], rcx
0x1801dbbcf  push    rbp
0x1801dbbd0  push    rsi
0x1801dbbd1  push    rdi
0x1801dbbd2  push    r12
0x1801dbbd4  push    r13
0x1801dbbd6  push    r14
0x1801dbbd8  push    r15
0x1801dbbda  lea     rbp, [rax-128h]
0x1801dbbe1  sub     rsp, 1F0h
0x1801dbbe8  mov     esi, r9d
0x1801dbbeb  mov     r15, r8
0x1801dbbee  mov     r12, rdx
0x1801dbbf1  cmp     qword ptr [r8+10h], 64h ; 'd'
0x1801dbbf6  jbe     short loc_1801DBC1B
0x1801dbbf8  mov     rcx, [rbp+128h]
0x1801dbbff  mov     r9d, 57h ; 'W'
0x1801dbc05  lea     r8, aOnecoreAdminAp_246; "onecore\\admin\\appmodel\\packagemanage"...
0x1801dbc0c  mov     edx, 921h
0x1801dbc11  call    sub_18011EDD8
0x1801dbc16  jmp     loc_1801DC35C
0x1801dbc1b  xor     r13d, r13d
0x1801dbc1e  mov     [rbp+120h+var_1A0], r13
0x1801dbc22  lea     r9, [rbp+120h+var_1A0]
0x1801dbc26  mov     r8d, esi
0x1801dbc29  mov     rcx, [rbp+120h+arg_28]
0x1801dbc30  call    sub_18034ADC8
0x1801dbc35  mov     byte ptr [rbp+120h+arg_10], r13b
0x1801dbc3c  mov     [rbp+120h+var_120], r13
0x1801dbc40  mov     [rbp+120h+var_118], r13
0x1801dbc44  mov     [rbp+120h+var_110], r13
0x1801dbc48  mov     [rbp+120h+var_108], r13d
0x1801dbc4c  mov     [rbp+120h+var_100], r13
0x1801dbc50  mov     [rbp+120h+var_F8], r13
0x1801dbc54  xorps   xmm0, xmm0
0x1801dbc57  movdqa  [rbp+120h+var_F0], xmm0
0x1801dbc5c  xorps   xmm1, xmm1
0x1801dbc5f  movdqa  [rbp+120h+var_E0], xmm1
0x1801dbc64  movdqa  [rbp+120h+var_D0], xmm0
0x1801dbc69  lea     r8, [rbp+120h+arg_10]
0x1801dbc70  lea     rdx, [rbp+120h+var_120]
0x1801dbc74  lea     rcx, [rbp+120h+var_1A0]
0x1801dbc78  call    sub_18034B15C
0x1801dbc7d  mov     ebx, eax
0x1801dbc7f  test    eax, eax
0x1801dbc81  jns     short loc_1801DBCD3
0x1801dbc83  mov     edx, 929h
0x1801dbc88  jmp     loc_1801DBE7C
0x1801dbc8d  mov     eax, [rbp+120h+var_108]
0x1801dbc90  mov     dword ptr [rsp+220h+var_200], eax
0x1801dbc94  mov     r9, [rbp+120h+var_100]
0x1801dbc98  mov     r8, [rbp+120h+var_110]
0x1801dbc9c  mov     rdx, r12
0x1801dbc9f  mov     rcx, [rbp+120h+arg_28]
0x1801dbca6  call    sub_18034B000
0x1801dbcab  mov     ebx, eax
0x1801dbcad  test    eax, eax
0x1801dbcaf  js      loc_1801DBE77
0x1801dbcb5  lea     r8, [rbp+120h+arg_10]
0x1801dbcbc  lea     rdx, [rbp+120h+var_120]
0x1801dbcc0  lea     rcx, [rbp+120h+var_1A0]
0x1801dbcc4  call    sub_18034B15C
0x1801dbcc9  mov     ebx, eax
0x1801dbccb  test    eax, eax
0x1801dbccd  js      loc_1801DBE70
0x1801dbcd3  cmp     byte ptr [rbp+120h+arg_10], r13b
0x1801dbcda  jnz     short loc_1801DBC8D
0x1801dbcdc  mov     r14, r13
0x1801dbcdf  mov     rax, [r15+10h]
0x1801dbce3  mov     [rbp+120h+var_128], rax
0x1801dbce7  cmp     r14, rax
0x1801dbcea  jz      loc_1801DC344
0x1801dbcf0  cmp     r14, [r15+10h]
0x1801dbcf4  jnb     short loc_1801DBD00
0x1801dbcf6  lfence
0x1801dbcf9  mov     rax, [r15]
0x1801dbcfc  mov     r13, [rax+r14*8]
0x1801dbd00  mov     rdi, [r13+8]
0x1801dbd04  xor     r8d, r8d
0x1801dbd07  mov     rsi, [rbp+120h+arg_0]
0x1801dbd0e  mov     rax, [rsi+98h]
0x1801dbd15  test    rax, rax
0x1801dbd18  jz      short loc_1801DBD31
0x1801dbd1a  mov     rcx, [rax+198h]
0x1801dbd21  test    rcx, rcx
0x1801dbd24  jz      short loc_1801DBD31
0x1801dbd26  mov     rdx, rdi
0x1801dbd29  call    sub_180089AC8
0x1801dbd2e  mov     r8, rax
0x1801dbd31  mov     [rsp+220h+var_1D8], 0
0x1801dbd3a  mov     [rsp+220h+var_1E0], 0
0x1801dbd43  lea     rdx, [rsp+220h+var_1D8]
0x1801dbd48  xor     ecx, ecx
0x1801dbd4a  test    r8, r8
0x1801dbd4d  cmovnz  rdx, rcx
0x1801dbd51  lea     rax, [rsp+220h+var_1E0]
0x1801dbd56  mov     [rsp+30h], rax
0x1801dbd5b  mov     [rsp+220h+var_1F8], rdx
0x1801dbd60  mov     [rsp+220h+var_200], r8
0x1801dbd65  xor     r9d, r9d
0x1801dbd68  xor     r8d, r8d
0x1801dbd6b  lea     edx, [rcx+4]
0x1801dbd6e  mov     rcx, rdi
0x1801dbd71  call    sub_18010FB5C
0x1801dbd76  mov     ebx, eax
0x1801dbd78  test    eax, eax
0x1801dbd7a  js      loc_1801DC311
0x1801dbd80  mov     rax, [rsi+98h]
0x1801dbd87  test    rax, rax
0x1801dbd8a  jz      short loc_1801DBDB4
0x1801dbd8c  mov     rcx, [rax+198h]; Table
0x1801dbd93  test    rcx, rcx
0x1801dbd96  jz      short loc_1801DBDB4
0x1801dbd98  mov     r8, [rsp+220h+var_1D8]
0x1801dbd9d  test    r8, r8
0x1801dbda0  jz      short loc_1801DBDB4
0x1801dbda2  mov     rdx, rdi
0x1801dbda5  call    sub_180166F68
0x1801dbdaa  mov     ebx, eax
0x1801dbdac  test    eax, eax
0x1801dbdae  js      loc_1801DC152
0x1801dbdb4  mov     [rsp+220h+var_1C8], 0
0x1801dbdbd  lea     rcx, [rbp+120h+var_130]
0x1801dbdc1  call    sub_1800AB77C
0x1801dbdc6  mov     rdx, rax
0x1801dbdc9  lea     rcx, [rsp+220h+var_1C8]
0x1801dbdce  call    sub_180167F34
0x1801dbdd3  lea     rcx, [rbp+120h+var_130]
0x1801dbdd7  call    sub_18000DBBC
0x1801dbddc  mov     rsi, [rsp+220h+var_1C8]
0x1801dbde1  test    rsi, rsi
0x1801dbde4  jz      loc_1801DC2E4
0x1801dbdea  mov     rdi, [rsp+220h+var_1E0]
0x1801dbdef  mov     rax, [rdi]
0x1801dbdf2  mov     rbx, [rax+80h]
0x1801dbdf9  mov     rcx, rbx
0x1801dbdfc  call    cs:__guard_check_icall_fptr
0x1801dbe02  mov     rcx, rdi
0x1801dbe05  call    rbx
0x1801dbe07  test    al, al
0x1801dbe09  jz      loc_1801DBE97
0x1801dbe0f  mov     [rsp+220h+var_1B0], 0
0x1801dbe18  mov     rdi, [rsp+220h+var_1E0]
0x1801dbe1d  mov     rax, [rdi]
0x1801dbe20  mov     rbx, [rax+190h]
0x1801dbe27  mov     rcx, rbx
0x1801dbe2a  call    cs:__guard_check_icall_fptr
0x1801dbe30  lea     rdx, [rsp+220h+var_1B0]
0x1801dbe35  mov     rcx, rdi
0x1801dbe38  call    rbx
0x1801dbe3a  mov     ebx, eax
0x1801dbe3c  xor     edi, edi
0x1801dbe3e  test    eax, eax
0x1801dbe40  js      loc_1801DC15C
0x1801dbe46  mov     rax, [rsi]
0x1801dbe49  mov     rbx, [rax+48h]
0x1801dbe4d  mov     rcx, rbx
0x1801dbe50  call    cs:__guard_check_icall_fptr
0x1801dbe56  mov     rdx, [rsp+220h+var_1B0]
0x1801dbe5b  mov     rcx, rsi
0x1801dbe5e  call    rbx
0x1801dbe60  nop
0x1801dbe61  lea     rcx, [rsp+220h+var_1B0]
0x1801dbe66  call    sub_18000DBBC
0x1801dbe6b  jmp     loc_1801DBEF3
0x1801dbe70  mov     edx, 931h
0x1801dbe75  jmp     short loc_1801DBE7C
0x1801dbe77  mov     edx, 92Fh
0x1801dbe7c  mov     rcx, [rbp+128h]
0x1801dbe83  mov     r9d, eax
0x1801dbe86  lea     r8, aOnecoreAdminAp_246; "onecore\\admin\\appmodel\\packagemanage"...
0x1801dbe8d  call    sub_180024B6C
0x1801dbe92  jmp     loc_1801DC347
0x1801dbe97  mov     [rsp+220h+var_1A8], 0
0x1801dbea0  mov     rdi, [rsp+220h+var_1E0]
0x1801dbea5  mov     rax, [rdi]
0x1801dbea8  mov     rbx, [rax+198h]
0x1801dbeaf  mov     rcx, rbx
0x1801dbeb2  call    cs:__guard_check_icall_fptr
0x1801dbeb8  lea     rdx, [rsp+220h+var_1A8]
0x1801dbebd  mov     rcx, rdi
0x1801dbec0  call    rbx
0x1801dbec2  mov     ebx, eax
0x1801dbec4  xor     edi, edi
0x1801dbec6  test    eax, eax
0x1801dbec8  js      loc_1801DC2BC
0x1801dbece  mov     rax, [rsi]
0x1801dbed1  mov     rbx, [rax+40h]
0x1801dbed5  mov     rcx, rbx
0x1801dbed8  call    cs:__guard_check_icall_fptr
0x1801dbede  mov     rdx, [rsp+220h+var_1A8]
0x1801dbee3  mov     rcx, rsi
0x1801dbee6  call    rbx
0x1801dbee8  nop
0x1801dbee9  lea     rcx, [rsp+220h+var_1A8]
0x1801dbeee  call    sub_18000DBBC
0x1801dbef3  mov     [rsp+220h+var_1D0], rdi
0x1801dbef8  mov     rax, [rsi]
0x1801dbefb  mov     rbx, [rax+30h]
0x1801dbeff  lea     rcx, [rsp+220h+var_1D0]
0x1801dbf04  call    sub_18000DBBC
0x1801dbf09  mov     rcx, rbx
0x1801dbf0c  call    cs:__guard_check_icall_fptr
0x1801dbf12  lea     rdx, [rsp+220h+var_1D0]
0x1801dbf17  mov     rcx, rsi
0x1801dbf1a  call    rbx
0x1801dbf1c  mov     ebx, eax
0x1801dbf1e  test    eax, eax
0x1801dbf20  js      loc_1801DC294
0x1801dbf26  mov     [rbp+120h+var_190], rdi
0x1801dbf2a  mov     [rbp+120h+var_188], rdi
0x1801dbf2e  mov     [rbp+120h+var_180], rdi
0x1801dbf32  mov     [rbp+120h+var_178], edi
0x1801dbf35  mov     [rbp+120h+var_170], rdi
0x1801dbf39  mov     [rbp+120h+var_168], 0
0x1801dbf41  xorps   xmm0, xmm0
0x1801dbf44  movdqa  [rbp+120h+var_160], xmm0
0x1801dbf49  mov     [rbp+120h+var_148], rdi
0x1801dbf4d  xorps   xmm1, xmm1
0x1801dbf50  movdqa  [rbp+120h+var_140], xmm1
0x1801dbf55  mov     [rbp+120h+var_150], r12
0x1801dbf59  mov     [rbp+120h+arg_10], edi
0x1801dbf5f  mov     rdi, [rsp+220h+var_1D0]
0x1801dbf64  mov     rax, [rdi]
0x1801dbf67  mov     rbx, [rax+20h]
0x1801dbf6b  mov     rcx, rbx
0x1801dbf6e  call    cs:__guard_check_icall_fptr
0x1801dbf74  lea     rdx, [rbp+120h+arg_10]
0x1801dbf7b  mov     rcx, rdi
0x1801dbf7e  call    rbx
0x1801dbf80  mov     ebx, eax
0x1801dbf82  test    eax, eax
0x1801dbf84  js      loc_1801DC26D
0x1801dbf8a  mov     eax, [rbp+120h+arg_10]
0x1801dbf90  mov     [rbp+120h+var_178], eax
0x1801dbf93  mov     esi, [rbp+120h+arg_18]
0x1801dbf99  mov     dword ptr [rbp+120h+var_168], esi
0x1801dbf9c  mov     [rsp+220h+var_1C0], 0
0x1801dbfa5  mov     rdi, [rsp+220h+var_1D0]
0x1801dbfaa  mov     rax, [rdi]
0x1801dbfad  mov     rbx, [rax+50h]
0x1801dbfb1  mov     rcx, rbx
0x1801dbfb4  call    cs:__guard_check_icall_fptr
0x1801dbfba  lea     rdx, [rsp+220h+var_1C0]
0x1801dbfbf  mov     rcx, rdi
0x1801dbfc2  call    rbx
0x1801dbfc4  mov     ebx, eax
0x1801dbfc6  test    eax, eax
0x1801dbfc8  js      loc_1801DC244
0x1801dbfce  mov     [rsp+220h+pv], 0
0x1801dbfd7  mov     rdi, [rsp+220h+var_1D0]
0x1801dbfdc  mov     rax, [rdi]
0x1801dbfdf  mov     rbx, [rax+28h]
0x1801dbfe3  mov     rcx, rbx
0x1801dbfe6  call    cs:__guard_check_icall_fptr
0x1801dbfec  lea     rdx, [rsp+220h+pv]
0x1801dbff1  mov     rcx, rdi
0x1801dbff4  call    rbx
0x1801dbff6  mov     ebx, eax
0x1801dbff8  test    eax, eax
0x1801dbffa  js      loc_1801DC21B
0x1801dc000  mov     [rbp+120h+var_C0], 0
0x1801dc008  mov     [rbp+120h+var_B8], 0
0x1801dc010  xorps   xmm0, xmm0
0x1801dc013  movdqa  [rbp+120h+var_B0], xmm0
0x1801dc018  xorps   xmm1, xmm1
0x1801dc01b  movdqa  [rbp+120h+var_A0], xmm1
0x1801dc023  movdqa  [rbp+120h+var_90], xmm0
0x1801dc02b  movdqa  [rbp+120h+var_80], xmm1
0x1801dc033  movdqa  [rbp+120h+var_70], xmm0
0x1801dc03b  movdqa  [rbp+120h+var_60], xmm1
0x1801dc043  movdqa  [rbp+120h+var_50], xmm0
0x1801dc04b  movdqa  [rbp+120h+var_40], xmm1
0x1801dc053  lea     rax, [rbp+120h+var_C0]
0x1801dc057  mov     [rsp+220h+var_200], rax
0x1801dc05c  mov     r9, [rsp+220h+pv]
0x1801dc061  mov     r8, [rsp+220h+var_1C0]
0x1801dc066  mov     rdx, [rbp+120h+arg_20]
0x1801dc06d  call    sub_1801E0298
0x1801dc072  mov     ebx, eax
0x1801dc074  test    eax, eax
0x1801dc076  js      loc_1801DC1F4
0x1801dc07c  mov     rax, [rbp+120h+var_C0]
0x1801dc080  mov     [rbp+120h+var_180], rax
0x1801dc084  mov     dword ptr [rbp+120h+var_168], esi
0x1801dc087  mov     rdx, [r13+8]
0x1801dc08b  lea     rcx, [rbp+120h+var_190]
0x1801dc08f  call    sub_18034B370
0x1801dc094  mov     ebx, eax
0x1801dc096  xor     r13d, r13d
0x1801dc099  test    eax, eax
0x1801dc09b  js      loc_1801DC195
0x1801dc0a1  mov     [rbp+120h+var_198], r13
0x1801dc0a5  mov     rdi, [rsp+220h+var_1D0]
0x1801dc0aa  mov     rax, [rdi]
0x1801dc0ad  mov     rbx, [rax+30h]
0x1801dc0b1  mov     rcx, rbx
  ... truncated ...
```
