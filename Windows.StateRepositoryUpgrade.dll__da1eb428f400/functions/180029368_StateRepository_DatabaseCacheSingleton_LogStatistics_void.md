# StateRepository::DatabaseCacheSingleton::LogStatistics(void)

- ea: `0x180029368`
- end: `0x180029743`
- name: `?LogStatistics@DatabaseCacheSingleton@StateRepository@@SAJXZ`
- size: `987`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180029288`

## callees

- `0x180001aac`
- `0x180002fc4`
- `0x18000c3bc`
- `0x180015204`
- `0x180029368`

## import_xrefs

- `StateRepository.Core!sqlite3_status` at `0x1800293b8`
- `StateRepository.Core!sqlite3_status` at `0x1800293fa`
- `StateRepository.Core!sqlite3_status` at `0x180029430`
- `StateRepository.Core!sqlite3_status` at `0x180029466`
- `StateRepository.Core!sqlite3_status` at `0x18002949c`
- `StateRepository.Core!sqlite3_status` at `0x1800294d2`
- `StateRepository.Core!sqlite3_status` at `0x180029508`
- `StateRepository.Core!sqlite3_status` at `0x18002953e`
- `StateRepository.Core!sqlite3_status` at `0x180029574`
- `StateRepository.Core!sqlite3_status` at `0x1800293b8`
- `StateRepository.Core!sqlite3_status` at `0x1800293fa`
- `StateRepository.Core!sqlite3_status` at `0x180029430`
- `StateRepository.Core!sqlite3_status` at `0x180029466`
- `StateRepository.Core!sqlite3_status` at `0x18002949c`
- `StateRepository.Core!sqlite3_status` at `0x1800294d2`
- `StateRepository.Core!sqlite3_status` at `0x180029508`
- `StateRepository.Core!sqlite3_status` at `0x18002953e`
- `StateRepository.Core!sqlite3_status` at `0x180029574`

## string_xrefs

- `0x1800293cc`: `onecore\base\appmodel\staterepository\dataaccesslayer\databasecachesingleton.cpp`

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
  __int64 v16; // r8
  bool v17; // sf
  _DWORD *v18; // rbx
  StateRepository::Time *v19; // rcx
  int v20; // r8d
  int v21; // r9d
  int v23; // [rsp+20h] [rbp-120h]
  int v24; // [rsp+C0h] [rbp-80h] BYREF
  int v25; // [rsp+C4h] [rbp-7Ch] BYREF
  int v26; // [rsp+C8h] [rbp-78h] BYREF
  int v27; // [rsp+CCh] [rbp-74h] BYREF
  int v28; // [rsp+D0h] [rbp-70h] BYREF
  int v29; // [rsp+D4h] [rbp-6Ch] BYREF
  int v30; // [rsp+D8h] [rbp-68h] BYREF
  int v31; // [rsp+DCh] [rbp-64h] BYREF
  int v32; // [rsp+E0h] [rbp-60h] BYREF
  int v33; // [rsp+E4h] [rbp-5Ch] BYREF
  int v34; // [rsp+E8h] [rbp-58h] BYREF
  int v35; // [rsp+ECh] [rbp-54h] BYREF
  int v36; // [rsp+F0h] [rbp-50h] BYREF
  int v37; // [rsp+F4h] [rbp-4Ch] BYREF
  int v38; // [rsp+F8h] [rbp-48h] BYREF
  int v39; // [rsp+FCh] [rbp-44h] BYREF
  int v40; // [rsp+100h] [rbp-40h] BYREF
  int v41; // [rsp+104h] [rbp-3Ch] BYREF
  int v42; // [rsp+108h] [rbp-38h] BYREF
  int v43; // [rsp+10Ch] [rbp-34h] BYREF
  int v44; // [rsp+110h] [rbp-30h] BYREF
  int v45; // [rsp+114h] [rbp-2Ch] BYREF
  int v46; // [rsp+118h] [rbp-28h] BYREF
  int v47; // [rsp+11Ch] [rbp-24h] BYREF
  int v48; // [rsp+120h] [rbp-20h] BYREF
  int v49; // [rsp+124h] [rbp-1Ch] BYREF
  int v50; // [rsp+128h] [rbp-18h] BYREF
  int v51; // [rsp+12Ch] [rbp-14h] BYREF
  __int64 v52; // [rsp+130h] [rbp-10h] BYREF
  unsigned __int64 v53; // [rsp+138h] [rbp-8h] BYREF
  __int64 v54; // [rsp+140h] [rbp+0h] BYREF
  _QWORD v55[5]; // [rsp+148h] [rbp+8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+38h]
  int v57; // [rsp+180h] [rbp+40h] BYREF
  int v58; // [rsp+188h] [rbp+48h] BYREF
  int v59; // [rsp+190h] [rbp+50h] BYREF
  int v60; // [rsp+198h] [rbp+58h] BYREF

  v57 = 0;
  v35 = 0;
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
  v60 = 0;
  v59 = 0;
  v58 = 0;
  v0 = sqlite3_status(0, &v35, &v34, 0);
  if ( v0 > 0 )
    v0 = (unsigned __int16)v0 | 0x87AF0000;
  if ( v0 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecachesingleton.cpp",
      (const char *)(unsigned int)v0,
      v23);
  v1 = sqlite3_status(7, &v57, &v33, 0);
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
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecachesingleton.cpp",
      (const char *)(unsigned int)v1,
      v23);
  v3 = sqlite3_status(1, &v32, &v31, 0);
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
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecachesingleton.cpp",
      (const char *)(unsigned int)v3,
      v23);
  v5 = sqlite3_status(2, &v30, &v29, 0);
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
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecachesingleton.cpp",
      (const char *)(unsigned int)v5,
      v23);
  v7 = sqlite3_status(3, &v28, &v27, 0);
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
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecachesingleton.cpp",
      (const char *)(unsigned int)v7,
      v23);
  v9 = sqlite3_status(4, &v26, &v25, 0);
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
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecachesingleton.cpp",
      (const char *)(unsigned int)v9,
      v23);
  v11 = sqlite3_status(8, &v57, &v24, 0);
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
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecachesingleton.cpp",
      (const char *)(unsigned int)v11,
      v23);
  v13 = sqlite3_status(5, &v57, &v60, 0);
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
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecachesingleton.cpp",
      (const char *)(unsigned int)v13,
      v23);
  v15 = sqlite3_status(9, &v59, &v58, 0);
  v17 = v15 < 0;
  if ( v15 > 0 )
  {
    v15 = (unsigned __int16)v15 | 0x87AF0000;
    v17 = v15 < 0;
  }
  if ( v17 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecachesingleton.cpp",
      (const char *)(unsigned int)v15,
      v23);
  v18 = (_DWORD *)*((_QWORD *)StateRepository::DatabaseCacheSingleton::s_cache + 7);
  if ( *v18 > 5u
    && (unsigned __int8)tlgKeywordOn(
                          *((_QWORD *)StateRepository::DatabaseCacheSingleton::s_cache + 7),
                          0x200000000000LL,
                          v16) )
  {
    v36 = v58;
    v37 = v59;
    v38 = v60;
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
    v50 = v35;
    v52 = 0x1000000;
    v53 = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v19)
        - StateRepository::DatabaseCacheSingleton::s_whenInitialized;
    v54 = *((_QWORD *)StateRepository::DatabaseCacheSingleton::s_cache + 5);
    v55[0] = *((_QWORD *)StateRepository::DatabaseCacheSingleton::s_cache + 4);
    v51 = *((_DWORD *)StateRepository::DatabaseCacheSingleton::s_cache + 4);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (_DWORD)v18,
      (unsigned int)byte_180045E43,
      v20,
      v21,
      (__int64)&v51,
      (__int64)v55,
      (__int64)&v54,
      (__int64)&v53,
      (__int64)&v50,
      (__int64)&v49,
      (__int64)&v48,
      (__int64)&v47,
      (__int64)&v46,
      (__int64)&v45,
      (__int64)&v44,
      (__int64)&v43,
      (__int64)&v42,
      (__int64)&v41,
      (__int64)&v40,
      (__int64)&v39,
      (__int64)&v38,
      (__int64)&v37,
      (__int64)&v36,
      (__int64)&v52);
  }
  return 0;
}

```

## disassembly

```asm
0x180029368  push    rbp
0x18002936a  push    rbx
0x18002936b  push    rsi
0x18002936c  push    rdi
0x18002936d  lea     rbp, [rsp-18h]
0x180029372  sub     rsp, 158h
0x180029379  xor     edi, edi
0x18002937b  lea     r8, [rbp+30h+var_88]
0x18002937f  xor     r9d, r9d
0x180029382  mov     [rbp+30h+arg_0], edi
0x180029385  lea     rdx, [rbp+30h+var_84]
0x180029389  mov     [rbp+30h+var_84], edi
0x18002938c  xor     ecx, ecx
0x18002938e  mov     [rbp+30h+var_88], edi
0x180029391  mov     [rbp+30h+var_8C], edi
0x180029394  mov     [rbp+30h+var_90], edi
0x180029397  mov     [rbp+30h+var_94], edi
0x18002939a  mov     [rbp+30h+var_98], edi
0x18002939d  mov     [rbp+30h+var_9C], edi
0x1800293a0  mov     [rbp+30h+var_A0], edi
0x1800293a3  mov     [rbp+30h+var_A4], edi
0x1800293a6  mov     [rbp+30h+var_A8], edi
0x1800293a9  mov     [rbp+30h+var_AC], edi
0x1800293ac  mov     [rbp+30h+var_B0], edi
0x1800293af  mov     [rbp+30h+arg_18], edi
0x1800293b2  mov     [rbp+30h+arg_10], edi
0x1800293b5  mov     [rbp+30h+arg_8], edi
0x1800293b8  call    cs:__imp_sqlite3_status
0x1800293be  mov     ebx, 87AF0000h
0x1800293c3  test    eax, eax
0x1800293c5  jle     short loc_1800293CC
0x1800293c7  movzx   eax, ax
0x1800293ca  or      eax, ebx
0x1800293cc  lea     rsi, aOnecoreBaseApp_51; "onecore\\base\\appmodel\\staterepositor"...
0x1800293d3  test    eax, eax
0x1800293d5  jns     short loc_1800293EB
0x1800293d7  mov     rcx, [rbp+38h]; this
0x1800293db  mov     r9d, eax; char *
0x1800293de  mov     r8, rsi; unsigned int
0x1800293e1  mov     edx, 4Bh ; 'K'; void *
0x1800293e6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800293eb  xor     r9d, r9d
0x1800293ee  lea     r8, [rbp+30h+var_8C]
0x1800293f2  lea     rdx, [rbp+30h+arg_0]
0x1800293f6  lea     ecx, [r9+7]
0x1800293fa  call    cs:__imp_sqlite3_status
0x180029400  test    eax, eax
0x180029402  jle     short loc_18002940B
0x180029404  movzx   eax, ax
0x180029407  or      eax, ebx
0x180029409  test    eax, eax
0x18002940b  jns     short loc_180029421
0x18002940d  mov     rcx, [rbp+38h]; this
0x180029411  mov     r9d, eax; char *
0x180029414  mov     r8, rsi; unsigned int
0x180029417  mov     edx, 4Ch ; 'L'; void *
0x18002941c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180029421  xor     r9d, r9d
0x180029424  lea     r8, [rbp+30h+var_94]
0x180029428  lea     rdx, [rbp+30h+var_90]
0x18002942c  lea     ecx, [r9+1]
0x180029430  call    cs:__imp_sqlite3_status
0x180029436  test    eax, eax
0x180029438  jle     short loc_180029441
0x18002943a  movzx   eax, ax
0x18002943d  or      eax, ebx
0x18002943f  test    eax, eax
0x180029441  jns     short loc_180029457
0x180029443  mov     rcx, [rbp+38h]; this
0x180029447  mov     r9d, eax; char *
0x18002944a  mov     r8, rsi; unsigned int
0x18002944d  mov     edx, 4Dh ; 'M'; void *
0x180029452  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180029457  xor     r9d, r9d
0x18002945a  lea     r8, [rbp+30h+var_9C]
0x18002945e  lea     rdx, [rbp+30h+var_98]
0x180029462  lea     ecx, [r9+2]
0x180029466  call    cs:__imp_sqlite3_status
0x18002946c  test    eax, eax
0x18002946e  jle     short loc_180029477
0x180029470  movzx   eax, ax
0x180029473  or      eax, ebx
0x180029475  test    eax, eax
0x180029477  jns     short loc_18002948D
0x180029479  mov     rcx, [rbp+38h]; this
0x18002947d  mov     r9d, eax; char *
0x180029480  mov     r8, rsi; unsigned int
0x180029483  mov     edx, 4Eh ; 'N'; void *
0x180029488  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002948d  xor     r9d, r9d
0x180029490  lea     r8, [rbp+30h+var_A4]
0x180029494  lea     rdx, [rbp+30h+var_A0]
0x180029498  lea     ecx, [r9+3]
0x18002949c  call    cs:__imp_sqlite3_status
0x1800294a2  test    eax, eax
0x1800294a4  jle     short loc_1800294AD
0x1800294a6  movzx   eax, ax
0x1800294a9  or      eax, ebx
0x1800294ab  test    eax, eax
0x1800294ad  jns     short loc_1800294C3
0x1800294af  mov     rcx, [rbp+38h]; this
0x1800294b3  mov     r9d, eax; char *
0x1800294b6  mov     r8, rsi; unsigned int
0x1800294b9  mov     edx, 4Fh ; 'O'; void *
0x1800294be  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800294c3  xor     r9d, r9d
0x1800294c6  lea     r8, [rbp+30h+var_AC]
0x1800294ca  lea     rdx, [rbp+30h+var_A8]
0x1800294ce  lea     ecx, [r9+4]
0x1800294d2  call    cs:__imp_sqlite3_status
0x1800294d8  test    eax, eax
0x1800294da  jle     short loc_1800294E3
0x1800294dc  movzx   eax, ax
0x1800294df  or      eax, ebx
0x1800294e1  test    eax, eax
0x1800294e3  jns     short loc_1800294F9
0x1800294e5  mov     rcx, [rbp+38h]; this
0x1800294e9  mov     r9d, eax; char *
0x1800294ec  mov     r8, rsi; unsigned int
0x1800294ef  mov     edx, 50h ; 'P'; void *
0x1800294f4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800294f9  xor     r9d, r9d
0x1800294fc  lea     r8, [rbp+30h+var_B0]
0x180029500  lea     rdx, [rbp+30h+arg_0]
0x180029504  lea     ecx, [r9+8]
0x180029508  call    cs:__imp_sqlite3_status
0x18002950e  test    eax, eax
0x180029510  jle     short loc_180029519
0x180029512  movzx   eax, ax
0x180029515  or      eax, ebx
0x180029517  test    eax, eax
0x180029519  jns     short loc_18002952F
0x18002951b  mov     rcx, [rbp+38h]; this
0x18002951f  mov     r9d, eax; char *
0x180029522  mov     r8, rsi; unsigned int
0x180029525  mov     edx, 51h ; 'Q'; void *
0x18002952a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002952f  xor     r9d, r9d
0x180029532  lea     r8, [rbp+30h+arg_18]
0x180029536  lea     rdx, [rbp+30h+arg_0]
0x18002953a  lea     ecx, [r9+5]
0x18002953e  call    cs:__imp_sqlite3_status
0x180029544  test    eax, eax
0x180029546  jle     short loc_18002954F
0x180029548  movzx   eax, ax
0x18002954b  or      eax, ebx
0x18002954d  test    eax, eax
0x18002954f  jns     short loc_180029565
0x180029551  mov     rcx, [rbp+38h]; this
0x180029555  mov     r9d, eax; char *
0x180029558  mov     r8, rsi; unsigned int
0x18002955b  mov     edx, 52h ; 'R'; void *
0x180029560  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180029565  xor     r9d, r9d
0x180029568  lea     r8, [rbp+30h+arg_8]
0x18002956c  lea     rdx, [rbp+30h+arg_10]
0x180029570  lea     ecx, [r9+9]
0x180029574  call    cs:__imp_sqlite3_status
0x18002957a  test    eax, eax
0x18002957c  jle     short loc_180029585
0x18002957e  movzx   eax, ax
0x180029581  or      eax, ebx
0x180029583  test    eax, eax
0x180029585  jns     short loc_18002959B
0x180029587  mov     rcx, [rbp+38h]; this
0x18002958b  mov     r9d, eax; char *
0x18002958e  mov     r8, rsi; unsigned int
0x180029591  mov     edx, 53h ; 'S'; void *
0x180029596  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002959b  mov     rax, cs:?s_cache@DatabaseCacheSingleton@StateRepository@@0PEAVDatabaseCache@2@EA; StateRepository::DatabaseCache * StateRepository::DatabaseCacheSingleton::s_cache
0x1800295a2  mov     rbx, [rax+38h]
0x1800295a6  mov     eax, [rbx]
0x1800295a8  cmp     eax, 5
0x1800295ab  jbe     loc_180029735
0x1800295b1  mov     rdx, 200000000000h
0x1800295bb  mov     rcx, rbx
0x1800295be  call    _tlgKeywordOn
0x1800295c3  test    al, al
0x1800295c5  jz      loc_180029735
0x1800295cb  mov     eax, [rbp+30h+arg_8]
0x1800295ce  mov     [rbp+30h+var_80], eax
0x1800295d1  mov     eax, [rbp+30h+arg_10]
0x1800295d4  mov     [rbp+30h+var_7C], eax
0x1800295d7  mov     eax, [rbp+30h+arg_18]
0x1800295da  mov     [rbp+30h+var_78], eax
0x1800295dd  mov     eax, [rbp+30h+var_B0]
0x1800295e0  mov     [rbp+30h+var_74], eax
0x1800295e3  mov     eax, [rbp+30h+var_AC]
0x1800295e6  mov     [rbp+30h+var_70], eax
0x1800295e9  mov     eax, [rbp+30h+var_A8]
0x1800295ec  mov     [rbp+30h+var_6C], eax
0x1800295ef  mov     eax, [rbp+30h+var_A4]
0x1800295f2  mov     [rbp+30h+var_68], eax
0x1800295f5  mov     eax, [rbp+30h+var_A0]
0x1800295f8  mov     [rbp+30h+var_64], eax
0x1800295fb  mov     eax, [rbp+30h+var_9C]
0x1800295fe  mov     [rbp+30h+var_60], eax
0x180029601  mov     eax, [rbp+30h+var_98]
0x180029604  mov     [rbp+30h+var_5C], eax
0x180029607  mov     eax, [rbp+30h+var_94]
0x18002960a  mov     [rbp+30h+var_58], eax
0x18002960d  mov     eax, [rbp+30h+var_90]
0x180029610  mov     [rbp+30h+var_54], eax
0x180029613  mov     eax, [rbp+30h+var_8C]
0x180029616  mov     [rbp+30h+var_50], eax
0x180029619  mov     eax, [rbp+30h+var_88]
0x18002961c  mov     [rbp+30h+var_4C], eax
0x18002961f  mov     eax, [rbp+30h+var_84]
0x180029622  mov     [rbp+30h+var_48], eax
0x180029625  mov     [rbp+30h+var_40], 1000000h
0x18002962d  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x180029632  sub     rax, cs:?s_whenInitialized@DatabaseCacheSingleton@StateRepository@@0_KA; unsigned __int64 StateRepository::DatabaseCacheSingleton::s_whenInitialized
0x180029639  mov     rcx, cs:?s_cache@DatabaseCacheSingleton@StateRepository@@0PEAVDatabaseCache@2@EA; StateRepository::DatabaseCache * StateRepository::DatabaseCacheSingleton::s_cache
0x180029640  mov     [rbp+30h+var_38], rax
0x180029644  mov     rax, [rcx+28h]
0x180029648  mov     [rbp+30h+var_30], rax
0x18002964c  mov     rax, [rcx+20h]
0x180029650  mov     [rbp+30h+var_28], rax
0x180029654  mov     eax, [rcx+10h]
0x180029657  mov     [rbp+30h+var_44], eax
0x18002965a  lea     rax, [rbp+30h+var_40]
0x18002965e  mov     [rsp+170h+var_B8], rax
0x180029666  lea     rax, [rbp+30h+var_80]
0x18002966a  mov     [rsp+170h+var_C0], rax
0x180029672  lea     rax, [rbp+30h+var_7C]
0x180029676  mov     [rsp+170h+var_C8], rax
0x18002967e  lea     rax, [rbp+30h+var_78]
0x180029682  mov     [rsp+170h+var_D0], rax
0x18002968a  lea     rax, [rbp+30h+var_74]
0x18002968e  mov     [rsp+170h+var_D8], rax
0x180029696  lea     rax, [rbp+30h+var_70]
0x18002969a  mov     [rsp+170h+var_E0], rax
0x1800296a2  lea     rax, [rbp+30h+var_6C]
0x1800296a6  mov     [rsp+170h+var_E8], rax
0x1800296ae  lea     rax, [rbp+30h+var_68]
0x1800296b2  mov     [rsp+170h+var_F0], rax
0x1800296ba  lea     rax, [rbp+30h+var_64]
0x1800296be  mov     [rsp+170h+var_F8], rax
0x1800296c3  lea     rax, [rbp+30h+var_60]
0x1800296c7  mov     [rsp+170h+var_100], rax
0x1800296cc  lea     rax, [rbp+30h+var_5C]
0x1800296d0  mov     [rsp+170h+var_108], rax
0x1800296d5  lea     rax, [rbp+30h+var_58]
0x1800296d9  mov     [rsp+170h+var_110], rax
0x1800296de  lea     rax, [rbp+30h+var_54]
0x1800296e2  mov     [rsp+170h+var_118], rax
0x1800296e7  lea     rax, [rbp+30h+var_50]
0x1800296eb  mov     [rsp+170h+var_120], rax
0x1800296f0  lea     rax, [rbp+30h+var_4C]
0x1800296f4  mov     [rsp+170h+var_128], rax
0x1800296f9  lea     rax, [rbp+30h+var_48]
0x1800296fd  mov     [rsp+170h+var_130], rax
0x180029702  lea     rax, [rbp+30h+var_38]
0x180029706  mov     [rsp+170h+var_138], rax
0x18002970b  lea     rax, [rbp+30h+var_30]
0x18002970f  mov     [rsp+170h+var_140], rax
0x180029714  lea     rax, [rbp+30h+var_28]
0x180029718  mov     [rsp+170h+var_148], rax
0x18002971d  lea     rax, [rbp+30h+var_44]
0x180029721  mov     [rsp+170h+var_150], rax
0x180029726  lea     rdx, byte_180045E43
0x18002972d  mov     rcx, rbx
0x180029730  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@U2@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@443333333333333334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180029735  xor     eax, eax
0x180029737  add     rsp, 158h
0x18002973e  pop     rdi
0x18002973f  pop     rsi
0x180029740  pop     rbx
0x180029741  pop     rbp
0x180029742  retn
```
