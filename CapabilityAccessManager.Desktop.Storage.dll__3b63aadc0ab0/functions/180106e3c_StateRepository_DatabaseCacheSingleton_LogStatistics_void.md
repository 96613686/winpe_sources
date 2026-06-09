# StateRepository::DatabaseCacheSingleton::LogStatistics(void)

- ea: `0x180106e3c`
- end: `0x180107341`
- name: `?LogStatistics@DatabaseCacheSingleton@StateRepository@@SAJXZ`
- size: `1285`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180106ddc`

## callees

- `0x18000163c`
- `0x180003060`
- `0x180013f60`
- `0x1800f7630`
- `0x180106e3c`

## import_xrefs

- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18010717e`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18010717e`

## string_xrefs

- `0x180106ec9`: `onecore\base\appmodel\staterepository\dataaccesslayer\databasecachesingleton.cpp`

## pseudocode

```c
__int64 StateRepository::DatabaseCacheSingleton::LogStatistics(void)
{
  signed int v0; // eax
  signed int v1; // eax
  bool v2; // sf
  signed int v3; // eax
  bool v4; // sf
  signed int v5; // eax
  bool v6; // sf
  signed int v7; // eax
  bool v8; // sf
  signed int v9; // eax
  bool v10; // sf
  signed int v11; // eax
  bool v12; // sf
  signed int v13; // eax
  bool v14; // sf
  signed int v15; // eax
  bool v16; // sf
  __int64 v17; // rbx
  int v19; // [rsp+30h] [rbp-D0h] BYREF
  int v20; // [rsp+34h] [rbp-CCh] BYREF
  int v21; // [rsp+38h] [rbp-C8h] BYREF
  int v22; // [rsp+3Ch] [rbp-C4h] BYREF
  int v23; // [rsp+40h] [rbp-C0h] BYREF
  int v24; // [rsp+44h] [rbp-BCh] BYREF
  int v25; // [rsp+48h] [rbp-B8h] BYREF
  int v26; // [rsp+4Ch] [rbp-B4h] BYREF
  int v27; // [rsp+50h] [rbp-B0h] BYREF
  int v28; // [rsp+54h] [rbp-ACh] BYREF
  int v29; // [rsp+58h] [rbp-A8h] BYREF
  int v30; // [rsp+5Ch] [rbp-A4h] BYREF
  int v31; // [rsp+60h] [rbp-A0h] BYREF
  int v32; // [rsp+64h] [rbp-9Ch] BYREF
  int v33; // [rsp+68h] [rbp-98h] BYREF
  int v34; // [rsp+6Ch] [rbp-94h] BYREF
  int v35; // [rsp+70h] [rbp-90h] BYREF
  int v36; // [rsp+74h] [rbp-8Ch] BYREF
  int v37; // [rsp+78h] [rbp-88h] BYREF
  int v38; // [rsp+7Ch] [rbp-84h] BYREF
  int v39; // [rsp+80h] [rbp-80h] BYREF
  int v40; // [rsp+84h] [rbp-7Ch] BYREF
  int v41; // [rsp+88h] [rbp-78h] BYREF
  int v42; // [rsp+8Ch] [rbp-74h] BYREF
  int v43; // [rsp+90h] [rbp-70h] BYREF
  int v44; // [rsp+94h] [rbp-6Ch] BYREF
  int v45; // [rsp+98h] [rbp-68h] BYREF
  int v46; // [rsp+9Ch] [rbp-64h] BYREF
  int v47; // [rsp+A0h] [rbp-60h] BYREF
  int v48; // [rsp+A4h] [rbp-5Ch] BYREF
  int v49; // [rsp+A8h] [rbp-58h] BYREF
  int v50; // [rsp+ACh] [rbp-54h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v52; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int64 v53; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v54; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v55; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v56[32]; // [rsp+E0h] [rbp-20h] BYREF
  int *v57; // [rsp+100h] [rbp+0h]
  __int64 v58; // [rsp+108h] [rbp+8h]
  __int64 *v59; // [rsp+110h] [rbp+10h]
  __int64 v60; // [rsp+118h] [rbp+18h]
  __int64 *v61; // [rsp+120h] [rbp+20h]
  __int64 v62; // [rsp+128h] [rbp+28h]
  unsigned __int64 *v63; // [rsp+130h] [rbp+30h]
  __int64 v64; // [rsp+138h] [rbp+38h]
  int *v65; // [rsp+140h] [rbp+40h]
  __int64 v66; // [rsp+148h] [rbp+48h]
  int *v67; // [rsp+150h] [rbp+50h]
  __int64 v68; // [rsp+158h] [rbp+58h]
  int *v69; // [rsp+160h] [rbp+60h]
  __int64 v70; // [rsp+168h] [rbp+68h]
  int *v71; // [rsp+170h] [rbp+70h]
  __int64 v72; // [rsp+178h] [rbp+78h]
  int *v73; // [rsp+180h] [rbp+80h]
  __int64 v74; // [rsp+188h] [rbp+88h]
  int *v75; // [rsp+190h] [rbp+90h]
  __int64 v76; // [rsp+198h] [rbp+98h]
  int *v77; // [rsp+1A0h] [rbp+A0h]
  __int64 v78; // [rsp+1A8h] [rbp+A8h]
  int *v79; // [rsp+1B0h] [rbp+B0h]
  __int64 v80; // [rsp+1B8h] [rbp+B8h]
  int *v81; // [rsp+1C0h] [rbp+C0h]
  __int64 v82; // [rsp+1C8h] [rbp+C8h]
  int *v83; // [rsp+1D0h] [rbp+D0h]
  __int64 v84; // [rsp+1D8h] [rbp+D8h]
  int *v85; // [rsp+1E0h] [rbp+E0h]
  __int64 v86; // [rsp+1E8h] [rbp+E8h]
  int *v87; // [rsp+1F0h] [rbp+F0h]
  __int64 v88; // [rsp+1F8h] [rbp+F8h]
  int *v89; // [rsp+200h] [rbp+100h]
  __int64 v90; // [rsp+208h] [rbp+108h]
  int *v91; // [rsp+210h] [rbp+110h]
  __int64 v92; // [rsp+218h] [rbp+118h]
  int *v93; // [rsp+220h] [rbp+120h]
  __int64 v94; // [rsp+228h] [rbp+128h]
  __int64 *v95; // [rsp+230h] [rbp+130h]
  __int64 v96; // [rsp+238h] [rbp+138h]
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v19 = 0;
  v34 = 0;
  v33 = 0;
  v32 = 0;
  v31 = 0;
  v30 = 0;
  v29 = 0;
  v28 = 0;
  v27 = 0;
  v26 = 0;
  v25 = 0;
  v24 = 0;
  v23 = 0;
  v22 = 0;
  v21 = 0;
  v20 = 0;
  v0 = sqlite3_status(0, &v34, &v33, 0);
  if ( v0 > 0 )
    v0 = (unsigned __int16)v0 | 0x87AF0000;
  if ( v0 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4B,
      (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecachesingleton.cpp",
      (const char *)(unsigned int)v0);
  v1 = sqlite3_status(7, &v19, &v32, 0);
  v2 = v1 < 0;
  if ( v1 > 0 )
  {
    v1 = (unsigned __int16)v1 | 0x87AF0000;
    v2 = v1 < 0;
  }
  if ( v2 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4C,
      (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecachesingleton.cpp",
      (const char *)(unsigned int)v1);
  v3 = sqlite3_status(1, &v31, &v30, 0);
  v4 = v3 < 0;
  if ( v3 > 0 )
  {
    v3 = (unsigned __int16)v3 | 0x87AF0000;
    v4 = v3 < 0;
  }
  if ( v4 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4D,
      (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecachesingleton.cpp",
      (const char *)(unsigned int)v3);
  v5 = sqlite3_status(2, &v29, &v28, 0);
  v6 = v5 < 0;
  if ( v5 > 0 )
  {
    v5 = (unsigned __int16)v5 | 0x87AF0000;
    v6 = v5 < 0;
  }
  if ( v6 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4E,
      (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecachesingleton.cpp",
      (const char *)(unsigned int)v5);
  v7 = sqlite3_status(3, &v27, &v26, 0);
  v8 = v7 < 0;
  if ( v7 > 0 )
  {
    v7 = (unsigned __int16)v7 | 0x87AF0000;
    v8 = v7 < 0;
  }
  if ( v8 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4F,
      (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecachesingleton.cpp",
      (const char *)(unsigned int)v7);
  v9 = sqlite3_status(4, &v25, &v24, 0);
  v10 = v9 < 0;
  if ( v9 > 0 )
  {
    v9 = (unsigned __int16)v9 | 0x87AF0000;
    v10 = v9 < 0;
  }
  if ( v10 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x50,
      (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecachesingleton.cpp",
      (const char *)(unsigned int)v9);
  v11 = sqlite3_status(8, &v19, &v23, 0);
  v12 = v11 < 0;
  if ( v11 > 0 )
  {
    v11 = (unsigned __int16)v11 | 0x87AF0000;
    v12 = v11 < 0;
  }
  if ( v12 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x51,
      (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecachesingleton.cpp",
      (const char *)(unsigned int)v11);
  v13 = sqlite3_status(5, &v19, &v22, 0);
  v14 = v13 < 0;
  if ( v13 > 0 )
  {
    v13 = (unsigned __int16)v13 | 0x87AF0000;
    v14 = v13 < 0;
  }
  if ( v14 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x52,
      (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecachesingleton.cpp",
      (const char *)(unsigned int)v13);
  v15 = sqlite3_status(9, &v21, &v20, 0);
  v16 = v15 < 0;
  if ( v15 > 0 )
  {
    v15 = (unsigned __int16)v15 | 0x87AF0000;
    v16 = v15 < 0;
  }
  if ( v16 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x53,
      (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecachesingleton.cpp",
      (const char *)(unsigned int)v15);
  v17 = *((_QWORD *)StateRepository::DatabaseCacheSingleton::s_cache + 7);
  if ( *(_DWORD *)v17 > 5u
    && (*(_QWORD *)(v17 + 16) & 0x200000000000LL) != 0
    && (*(_QWORD *)(v17 + 24) & 0x200000000000LL) == *(_QWORD *)(v17 + 24) )
  {
    v35 = v20;
    v36 = v21;
    v37 = v22;
    v38 = v23;
    v39 = v24;
    v40 = v25;
    v41 = v26;
    v42 = v27;
    v43 = v28;
    v44 = v29;
    v45 = v30;
    v46 = v31;
    v47 = v32;
    v48 = v33;
    v49 = v34;
    v52 = 0x1000000;
    UnbiasedTime = 0;
    QueryUnbiasedInterruptTime(&UnbiasedTime);
    v96 = 8;
    v53 = UnbiasedTime / 0x2710 - StateRepository::DatabaseCacheSingleton::s_whenInitialized;
    v54 = *((_QWORD *)StateRepository::DatabaseCacheSingleton::s_cache + 5);
    v55 = *((_QWORD *)StateRepository::DatabaseCacheSingleton::s_cache + 4);
    v50 = *((_DWORD *)StateRepository::DatabaseCacheSingleton::s_cache + 4);
    v95 = &v52;
    v93 = &v35;
    v91 = &v36;
    v89 = &v37;
    v87 = &v38;
    v85 = &v39;
    v83 = &v40;
    v81 = &v41;
    v79 = &v42;
    v77 = &v43;
    v75 = &v44;
    v73 = &v45;
    v94 = 4;
    v92 = 4;
    v90 = 4;
    v88 = 4;
    v86 = 4;
    v84 = 4;
    v82 = 4;
    v80 = 4;
    v78 = 4;
    v76 = 4;
    v74 = 4;
    v71 = &v46;
    v72 = 4;
    v69 = &v47;
    v70 = 4;
    v67 = &v48;
    v68 = 4;
    v65 = &v49;
    v66 = 4;
    v63 = &v53;
    v61 = &v54;
    v59 = &v55;
    v57 = &v50;
    v64 = 8;
    v62 = 8;
    v60 = 8;
    v58 = 4;
    tlgWriteTransfer_EventWriteTransfer(v17, &unk_18012A430, 0, 0, 22, v56);
  }
  return 0;
}

```

## disassembly

```asm
0x180106e3c  push    rbp
0x180106e3e  push    rbx
0x180106e3f  push    rsi
0x180106e40  push    rdi
0x180106e41  push    r14
0x180106e43  push    r15
0x180106e45  lea     rbp, [rsp-158h]
0x180106e4d  sub     rsp, 258h
0x180106e54  mov     rax, cs:__security_cookie
0x180106e5b  xor     rax, rsp
0x180106e5e  mov     [rbp+180h+var_40], rax
0x180106e65  xor     edi, edi
0x180106e67  lea     r8, [rsp+280h+var_218]
0x180106e6c  xor     r9d, r9d
0x180106e6f  mov     [rsp+280h+var_250], edi
0x180106e73  lea     rdx, [rsp+280h+var_214]
0x180106e78  mov     [rsp+280h+var_214], edi
0x180106e7c  xor     ecx, ecx
0x180106e7e  mov     [rsp+280h+var_218], edi
0x180106e82  mov     [rsp+280h+var_21C], edi
0x180106e86  mov     [rsp+280h+var_220], edi
0x180106e8a  mov     [rsp+280h+var_224], edi
0x180106e8e  mov     [rsp+280h+var_228], edi
0x180106e92  mov     [rsp+280h+var_22C], edi
0x180106e96  mov     [rsp+280h+var_230], edi
0x180106e9a  mov     [rsp+280h+var_234], edi
0x180106e9e  mov     [rsp+280h+var_238], edi
0x180106ea2  mov     [rsp+280h+var_23C], edi
0x180106ea6  mov     [rsp+280h+var_240], edi
0x180106eaa  mov     [rsp+280h+var_244], edi
0x180106eae  mov     [rsp+280h+var_248], edi
0x180106eb2  mov     [rsp+280h+var_24C], edi
0x180106eb6  call    sqlite3_status
0x180106ebb  mov     ebx, 87AF0000h
0x180106ec0  test    eax, eax
0x180106ec2  jle     short loc_180106EC9
0x180106ec4  movzx   eax, ax
0x180106ec7  or      eax, ebx
0x180106ec9  lea     rsi, aOnecoreBaseApp_22; "onecore\\base\\appmodel\\staterepositor"...
0x180106ed0  test    eax, eax
0x180106ed2  jns     short loc_180106EEB
0x180106ed4  mov     rcx, [rbp+188h]; this
0x180106edb  mov     r9d, eax; char *
0x180106ede  mov     r8, rsi; unsigned int
0x180106ee1  mov     edx, 4Bh ; 'K'; void *
0x180106ee6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180106eeb  xor     r9d, r9d
0x180106eee  lea     r8, [rsp+280h+var_21C]
0x180106ef3  lea     rdx, [rsp+280h+var_250]
0x180106ef8  lea     ecx, [r9+7]
0x180106efc  call    sqlite3_status
0x180106f01  test    eax, eax
0x180106f03  jle     short loc_180106F0C
0x180106f05  movzx   eax, ax
0x180106f08  or      eax, ebx
0x180106f0a  test    eax, eax
0x180106f0c  jns     short loc_180106F25
0x180106f0e  mov     rcx, [rbp+188h]; this
0x180106f15  mov     r9d, eax; char *
0x180106f18  mov     r8, rsi; unsigned int
0x180106f1b  mov     edx, 4Ch ; 'L'; void *
0x180106f20  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180106f25  xor     r9d, r9d
0x180106f28  lea     r8, [rsp+280h+var_224]
0x180106f2d  lea     rdx, [rsp+280h+var_220]
0x180106f32  lea     ecx, [r9+1]
0x180106f36  call    sqlite3_status
0x180106f3b  test    eax, eax
0x180106f3d  jle     short loc_180106F46
0x180106f3f  movzx   eax, ax
0x180106f42  or      eax, ebx
0x180106f44  test    eax, eax
0x180106f46  jns     short loc_180106F5F
0x180106f48  mov     rcx, [rbp+188h]; this
0x180106f4f  mov     r9d, eax; char *
0x180106f52  mov     r8, rsi; unsigned int
0x180106f55  mov     edx, 4Dh ; 'M'; void *
0x180106f5a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180106f5f  xor     r9d, r9d
0x180106f62  lea     r8, [rsp+280h+var_22C]
0x180106f67  lea     rdx, [rsp+280h+var_228]
0x180106f6c  lea     ecx, [r9+2]
0x180106f70  call    sqlite3_status
0x180106f75  test    eax, eax
0x180106f77  jle     short loc_180106F80
0x180106f79  movzx   eax, ax
0x180106f7c  or      eax, ebx
0x180106f7e  test    eax, eax
0x180106f80  jns     short loc_180106F99
0x180106f82  mov     rcx, [rbp+188h]; this
0x180106f89  mov     r9d, eax; char *
0x180106f8c  mov     r8, rsi; unsigned int
0x180106f8f  mov     edx, 4Eh ; 'N'; void *
0x180106f94  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180106f99  xor     r9d, r9d
0x180106f9c  lea     r8, [rsp+280h+var_234]
0x180106fa1  lea     rdx, [rsp+280h+var_230]
0x180106fa6  lea     ecx, [r9+3]
0x180106faa  call    sqlite3_status
0x180106faf  test    eax, eax
0x180106fb1  jle     short loc_180106FBA
0x180106fb3  movzx   eax, ax
0x180106fb6  or      eax, ebx
0x180106fb8  test    eax, eax
0x180106fba  jns     short loc_180106FD3
0x180106fbc  mov     rcx, [rbp+188h]; this
0x180106fc3  mov     r9d, eax; char *
0x180106fc6  mov     r8, rsi; unsigned int
0x180106fc9  mov     edx, 4Fh ; 'O'; void *
0x180106fce  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180106fd3  xor     r9d, r9d
0x180106fd6  lea     r8, [rsp+280h+var_23C]
0x180106fdb  lea     rdx, [rsp+280h+var_238]
0x180106fe0  lea     r14d, [r9+4]
0x180106fe4  mov     ecx, r14d
0x180106fe7  call    sqlite3_status
0x180106fec  test    eax, eax
0x180106fee  jle     short loc_180106FF7
0x180106ff0  movzx   eax, ax
0x180106ff3  or      eax, ebx
0x180106ff5  test    eax, eax
0x180106ff7  jns     short loc_180107010
0x180106ff9  mov     rcx, [rbp+188h]; this
0x180107000  mov     r9d, eax; char *
0x180107003  mov     r8, rsi; unsigned int
0x180107006  mov     edx, 50h ; 'P'; void *
0x18010700b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180107010  xor     r9d, r9d
0x180107013  lea     r8, [rsp+280h+var_240]
0x180107018  lea     rdx, [rsp+280h+var_250]
0x18010701d  lea     r15d, [r9+8]
0x180107021  mov     ecx, r15d
0x180107024  call    sqlite3_status
0x180107029  test    eax, eax
0x18010702b  jle     short loc_180107034
0x18010702d  movzx   eax, ax
0x180107030  or      eax, ebx
0x180107032  test    eax, eax
0x180107034  jns     short loc_18010704D
0x180107036  mov     rcx, [rbp+188h]; this
0x18010703d  mov     r9d, eax; char *
0x180107040  mov     r8, rsi; unsigned int
0x180107043  mov     edx, 51h ; 'Q'; void *
0x180107048  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010704d  xor     r9d, r9d
0x180107050  lea     r8, [rsp+280h+var_244]
0x180107055  lea     rdx, [rsp+280h+var_250]
0x18010705a  lea     ecx, [r9+5]
0x18010705e  call    sqlite3_status
0x180107063  test    eax, eax
0x180107065  jle     short loc_18010706E
0x180107067  movzx   eax, ax
0x18010706a  or      eax, ebx
0x18010706c  test    eax, eax
0x18010706e  jns     short loc_180107087
0x180107070  mov     rcx, [rbp+188h]; this
0x180107077  mov     r9d, eax; char *
0x18010707a  mov     r8, rsi; unsigned int
0x18010707d  mov     edx, 52h ; 'R'; void *
0x180107082  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180107087  xor     r9d, r9d
0x18010708a  lea     r8, [rsp+280h+var_24C]
0x18010708f  lea     rdx, [rsp+280h+var_248]
0x180107094  lea     ecx, [r9+9]
0x180107098  call    sqlite3_status
0x18010709d  test    eax, eax
0x18010709f  jle     short loc_1801070A8
0x1801070a1  movzx   eax, ax
0x1801070a4  or      eax, ebx
0x1801070a6  test    eax, eax
0x1801070a8  jns     short loc_1801070C1
0x1801070aa  mov     rcx, [rbp+188h]; this
0x1801070b1  mov     r9d, eax; char *
0x1801070b4  mov     r8, rsi; unsigned int
0x1801070b7  mov     edx, 53h ; 'S'; void *
0x1801070bc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801070c1  mov     rax, cs:?s_cache@DatabaseCacheSingleton@StateRepository@@0PEAVDatabaseCache@2@EA; StateRepository::DatabaseCache * StateRepository::DatabaseCacheSingleton::s_cache
0x1801070c8  mov     rbx, [rax+38h]
0x1801070cc  mov     eax, [rbx]
0x1801070ce  cmp     eax, 5
0x1801070d1  jbe     loc_180107320
0x1801070d7  mov     rcx, [rbx+18h]
0x1801070db  mov     rdx, 200000000000h
0x1801070e5  mov     rax, [rbx+10h]
0x1801070e9  test    rdx, rax
0x1801070ec  jz      loc_180107320
0x1801070f2  mov     rax, rcx
0x1801070f5  and     rax, rdx
0x1801070f8  cmp     rax, rcx
0x1801070fb  jnz     loc_180107320
0x180107101  mov     eax, [rsp+280h+var_24C]
0x180107105  lea     rcx, [rbp+180h+UnbiasedTime]; UnbiasedTime
0x180107109  mov     [rsp+280h+var_210], eax
0x18010710d  mov     eax, [rsp+280h+var_248]
0x180107111  mov     [rsp+280h+var_20C], eax
0x180107115  mov     eax, [rsp+280h+var_244]
0x180107119  mov     [rsp+280h+var_208], eax
0x18010711d  mov     eax, [rsp+280h+var_240]
0x180107121  mov     [rsp+280h+var_204], eax
0x180107125  mov     eax, [rsp+280h+var_23C]
0x180107129  mov     [rbp+180h+var_200], eax
0x18010712c  mov     eax, [rsp+280h+var_238]
0x180107130  mov     [rbp+180h+var_1FC], eax
0x180107133  mov     eax, [rsp+280h+var_234]
0x180107137  mov     [rbp+180h+var_1F8], eax
0x18010713a  mov     eax, [rsp+280h+var_230]
0x18010713e  mov     [rbp+180h+var_1F4], eax
0x180107141  mov     eax, [rsp+280h+var_22C]
0x180107145  mov     [rbp+180h+var_1F0], eax
0x180107148  mov     eax, [rsp+280h+var_228]
0x18010714c  mov     [rbp+180h+var_1EC], eax
0x18010714f  mov     eax, [rsp+280h+var_224]
0x180107153  mov     [rbp+180h+var_1E8], eax
0x180107156  mov     eax, [rsp+280h+var_220]
0x18010715a  mov     [rbp+180h+var_1E4], eax
0x18010715d  mov     eax, [rsp+280h+var_21C]
0x180107161  mov     [rbp+180h+var_1E0], eax
0x180107164  mov     eax, [rsp+280h+var_218]
0x180107168  mov     [rbp+180h+var_1DC], eax
0x18010716b  mov     eax, [rsp+280h+var_214]
0x18010716f  mov     [rbp+180h+var_1D8], eax
0x180107172  mov     [rbp+180h+var_1C8], 1000000h
0x18010717a  mov     [rbp+180h+UnbiasedTime], rdi
0x18010717e  call    cs:__imp_QueryUnbiasedInterruptTime
0x180107184  mov     rcx, cs:?s_cache@DatabaseCacheSingleton@StateRepository@@0PEAVDatabaseCache@2@EA; StateRepository::DatabaseCache * StateRepository::DatabaseCacheSingleton::s_cache
0x18010718b  mov     rax, 346DC5D63886594Bh
0x180107195  mul     [rbp+180h+UnbiasedTime]
0x180107199  mov     [rbp+180h+var_48], r15
0x1801071a0  shr     rdx, 0Bh
0x1801071a4  sub     rdx, cs:?s_whenInitialized@DatabaseCacheSingleton@StateRepository@@0_KA; unsigned __int64 StateRepository::DatabaseCacheSingleton::s_whenInitialized
0x1801071ab  mov     [rbp+180h+var_1C0], rdx
0x1801071af  mov     rax, [rcx+28h]
0x1801071b3  mov     [rbp+180h+var_1B8], rax
0x1801071b7  mov     rax, [rcx+20h]
0x1801071bb  mov     [rbp+180h+var_1B0], rax
0x1801071bf  mov     eax, [rcx+10h]
0x1801071c2  mov     [rbp+180h+var_1D4], eax
0x1801071c5  lea     rax, [rbp+180h+var_1C8]
0x1801071c9  mov     [rbp+180h+var_50], rax
0x1801071d0  lea     rax, [rsp+280h+var_210]
0x1801071d5  mov     [rbp+180h+var_60], rax
0x1801071dc  lea     rax, [rsp+280h+var_20C]
0x1801071e1  mov     [rbp+180h+var_70], rax
0x1801071e8  lea     rax, [rsp+280h+var_208]
0x1801071ed  mov     [rbp+180h+var_80], rax
0x1801071f4  lea     rax, [rsp+280h+var_204]
0x1801071f9  mov     [rbp+180h+var_90], rax
0x180107200  lea     rax, [rbp+180h+var_200]
0x180107204  mov     [rbp+180h+var_A0], rax
0x18010720b  lea     rax, [rbp+180h+var_1FC]
0x18010720f  mov     [rbp+180h+var_B0], rax
0x180107216  lea     rax, [rbp+180h+var_1F8]
0x18010721a  mov     [rbp+180h+var_C0], rax
0x180107221  lea     rax, [rbp+180h+var_1F4]
0x180107225  mov     [rbp+180h+var_D0], rax
0x18010722c  lea     rax, [rbp+180h+var_1F0]
0x180107230  mov     [rbp+180h+var_E0], rax
0x180107237  lea     rax, [rbp+180h+var_1EC]
0x18010723b  mov     [rbp+180h+var_F0], rax
0x180107242  lea     rax, [rbp+180h+var_1E8]
0x180107246  mov     [rbp+180h+var_100], rax
0x18010724d  mov     [rbp+180h+var_58], r14
0x180107254  mov     [rbp+180h+var_68], r14
0x18010725b  mov     [rbp+180h+var_78], r14
0x180107262  mov     [rbp+180h+var_88], r14
0x180107269  mov     [rbp+180h+var_98], r14
0x180107270  mov     [rbp+180h+var_A8], r14
0x180107277  mov     [rbp+180h+var_B8], r14
0x18010727e  mov     [rbp+180h+var_C8], r14
0x180107285  mov     [rbp+180h+var_D8], r14
0x18010728c  mov     [rbp+180h+var_E8], r14
0x180107293  lea     rax, [rbp+180h+var_1E4]
0x180107297  mov     [rbp+180h+var_F8], r14
0x18010729e  mov     [rbp+180h+var_110], rax
0x1801072a2  lea     rdx, unk_18012A430
0x1801072a9  lea     rax, [rbp+180h+var_1E0]
0x1801072ad  mov     [rbp+180h+var_108], r14
0x1801072b1  mov     [rbp+180h+var_120], rax
0x1801072b5  xor     r9d, r9d
0x1801072b8  lea     rax, [rbp+180h+var_1DC]
0x1801072bc  mov     [rbp+180h+var_118], r14
0x1801072c0  mov     [rbp+180h+var_130], rax
0x1801072c4  xor     r8d, r8d
0x1801072c7  lea     rax, [rbp+180h+var_1D8]
0x1801072cb  mov     [rbp+180h+var_128], r14
0x1801072cf  mov     [rbp+180h+var_140], rax
0x1801072d3  mov     rcx, rbx
0x1801072d6  lea     rax, [rbp+180h+var_1C0]
0x1801072da  mov     [rbp+180h+var_138], r14
0x1801072de  mov     [rbp+180h+var_150], rax
0x1801072e2  lea     rax, [rbp+180h+var_1B8]
0x1801072e6  mov     [rbp+180h+var_160], rax
0x1801072ea  lea     rax, [rbp+180h+var_1B0]
0x1801072ee  mov     [rbp+180h+var_170], rax
0x1801072f2  lea     rax, [rbp+180h+var_1D4]
0x1801072f6  mov     [rbp+180h+var_180], rax
0x1801072fa  lea     rax, [rbp+180h+var_1A0]
0x1801072fe  mov     [rsp+280h+var_258], rax
0x180107303  mov     [rsp+280h+var_260], 16h
0x18010730b  mov     [rbp+180h+var_148], r15
  ... truncated ...
```
