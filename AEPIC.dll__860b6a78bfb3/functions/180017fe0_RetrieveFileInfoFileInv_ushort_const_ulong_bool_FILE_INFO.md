# RetrieveFileInfoFileInv(ushort const *,ulong,bool,_FILE_INFO *)

- ea: `0x180017fe0`
- end: `0x1800186c5`
- name: `?RetrieveFileInfoFileInv@@YAJPEBGK_NPEAU_FILE_INFO@@@Z`
- size: `1765`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, char, struct _FILE_INFO *)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x18001c860`

## callees

- `0x180005890`
- `0x180005d10`
- `0x180005ec0`
- `0x180005f28`
- `0x18000cb30`
- `0x18000d914`
- `0x18000f868`
- `0x18000faf0`
- `0x180017fe0`
- `0x18001b220`
- `0x18001b26c`
- `0x18001c5f0`
- `0x180027900`
- `0x1800295dc`
- `0x1800c26f8`
- `0x1800c3280`

## string_xrefs

- `0x1800181a2`: `StringCchCopyW [%#x]`
- `0x1800181fe`: `StringCchCopyW [%#x]`
- `0x180018277`: `StringCbCopyW [%#x]`
- `0x1800182d1`: `StringCbCopyW [%#x]`
- `0x18001832d`: `StringCbCopyW [%#x]`
- `0x1800183db`: `StringCbCopyW [%#x]`
- `0x180018437`: `StringCbCopyW [%#x]`
- `0x180018493`: `StringCbCopyW [%#x]`
- `0x1800184ef`: `StringCbCopyW [%#x]`
- `0x18001854b`: `StringCbCopyW [%#x]`
- `0x1800185a7`: `StringCbCopyW [%#x]`
- `0x180018603`: `StringCbCopyW [%#x]`

## pseudocode

```c
__int64 __fastcall RetrieveFileInfoFileInv(const unsigned __int16 *a1, int a2, char a3, struct _FILE_INFO *a4)
{
  int v7; // r13d
  int v8; // r12d
  int v9; // r15d
  bool v10; // bl
  __int64 v11; // rdx
  __int64 v12; // rcx
  bool v13; // zf
  TelCacheProvider *v14; // rax
  bool v15; // al
  unsigned int FileInfoFromRpc; // ebx
  const unsigned __int16 *v17; // r8
  int v18; // eax
  unsigned __int64 v19; // r11
  const unsigned __int16 *v20; // r8
  int v21; // eax
  const unsigned __int16 *v22; // r8
  int v23; // eax
  const unsigned __int16 *v24; // r8
  int v25; // eax
  const unsigned __int16 *v26; // r8
  int v27; // eax
  int v28; // eax
  const unsigned __int16 *v29; // r8
  int v30; // eax
  const unsigned __int16 *v31; // r8
  int v32; // eax
  const unsigned __int16 *v33; // r8
  int v34; // eax
  const unsigned __int16 *v35; // r8
  int v36; // eax
  const unsigned __int16 *v37; // r8
  int v38; // eax
  const unsigned __int16 *v39; // r8
  int v40; // eax
  const unsigned __int16 *v41; // r8
  int v42; // eax
  const char *v44; // rax
  const std::exception *v45; // [rsp+38h] [rbp-390h] BYREF
  _BYTE v46[32]; // [rsp+40h] [rbp-388h] BYREF
  _BYTE v47[88]; // [rsp+60h] [rbp-368h] BYREF
  unsigned __int16 *v48[4]; // [rsp+B8h] [rbp-310h] BYREF
  unsigned __int16 *v49[4]; // [rsp+D8h] [rbp-2F0h] BYREF
  unsigned __int16 *v50[4]; // [rsp+F8h] [rbp-2D0h] BYREF
  unsigned __int16 *v51[8]; // [rsp+118h] [rbp-2B0h] BYREF
  unsigned __int16 *v52[4]; // [rsp+158h] [rbp-270h] BYREF
  unsigned __int16 *v53[4]; // [rsp+178h] [rbp-250h] BYREF
  unsigned __int16 *v54[4]; // [rsp+198h] [rbp-230h] BYREF
  unsigned __int16 *v55[8]; // [rsp+1B8h] [rbp-210h] BYREF
  unsigned __int16 *v56[32]; // [rsp+1F8h] [rbp-1D0h] BYREF
  unsigned __int16 *v57[4]; // [rsp+2F8h] [rbp-D0h] BYREF
  unsigned __int16 *v58[4]; // [rsp+318h] [rbp-B0h] BYREF
  unsigned __int16 *v59[4]; // [rsp+338h] [rbp-90h] BYREF
  int v60; // [rsp+358h] [rbp-70h]
  unsigned int v61; // [rsp+380h] [rbp-48h]

  v7 = a2 & 0x10;
  v8 = a2 & 0x20;
  v9 = a2 & 0x40;
  v10 = (a2 & 0x10) != 0 || (a2 & 0x20) != 0 || (a2 & 0x40) != 0 || !a3;
  v11 = 4;
  v12 = *(unsigned int *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL);
  if ( dword_180122CE8 > (int)v12 )
  {
    Init_thread_header(&dword_180122CE8);
    if ( dword_180122CE8 == -1 )
    {
      atexit(RetrieveFileInfoFileInv_::_2_::_dynamic_atexit_destructor_for__fileCacheProvider__);
      Init_thread_footer(&dword_180122CE8);
    }
  }
  LOBYTE(v11) = 0;
  wil::init_once_nothrow__lambda_eed0231a23d8c5c16b0fe5d0e10ec71b___(v12, v11);
  v13 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl'::`2'::impl) == 0;
  v14 = qword_180121630;
  if ( v13 )
    v14 = g_CacheProvider;
  v15 = v14 && *((_QWORD *)v14 + 11);
  if ( !v10 && !v15 && (a2 & 0x10000) == 0 )
  {
    FileInfoFromRpc = RetrieveFileInfoFromRpc(a1, a4);
    if ( (FileInfoFromRpc & 0x80000000) == 0 )
    {
      AslLogCallPrintf(3, "RetrieveFileInfoFileInv", 578, "Retrieved \"%ls\" info from RPC", a1);
      return FileInfoFromRpc;
    }
  }
  try
  {
    UtcThrottle::DisableThrottling = 1;
    std::wstring::wstring(v46, a1);
    File::File((File *)v47, v8 != 0, v9 != 0);
    std::wstring::_Tidy_deallocate(v46);
    if ( !v48[2] || !v49[2] )
    {
      FileInfoFromRpc = v60;
      if ( v60 >= 0 )
        FileInfoFromRpc = -2147467259;
      File::~File((File *)v47);
      return FileInfoFromRpc;
    }
    v17 = (const unsigned __int16 *)v48;
    if ( v48[3] > (unsigned __int16 *)7 )
      v17 = v48[0];
    v18 = StringCchCopyW(*((unsigned __int16 **)a4 + 1), 0x2Du, v17);
    FileInfoFromRpc = v18;
    if ( v18 < 0 )
    {
      AslLogCallPrintf(1, "RetrieveFileInfoFileInv", 607, "StringCchCopyW [%#x]", v18);
      File::~File((File *)v47);
      return FileInfoFromRpc;
    }
    v20 = (const unsigned __int16 *)v49;
    if ( v49[3] > (unsigned __int16 *)7 )
      v20 = v49[0];
    v21 = StringCchCopyW(*(unsigned __int16 **)a4, v19, v20);
    FileInfoFromRpc = v21;
    if ( v21 < 0 )
    {
      AslLogCallPrintf(1, "RetrieveFileInfoFileInv", 613, "StringCchCopyW [%#x]", v21);
      File::~File((File *)v47);
      return FileInfoFromRpc;
    }
    if ( !v7 && !v8 && !v9 )
      goto LABEL_74;
    v22 = (const unsigned __int16 *)v56;
    if ( v56[3] > (unsigned __int16 *)7 )
      v22 = v56[0];
    v23 = StringCbCopyW(*((unsigned __int16 **)a4 + 2), 0x208u, v22);
    FileInfoFromRpc = v23;
    if ( v23 < 0 )
    {
      AslLogCallPrintf(1, "RetrieveFileInfoFileInv", 622, "StringCbCopyW [%#x]", v23);
      File::~File((File *)v47);
      return FileInfoFromRpc;
    }
    v24 = (const unsigned __int16 *)v52;
    if ( v52[3] > (unsigned __int16 *)7 )
      v24 = v52[0];
    v25 = StringCbCopyW(*((unsigned __int16 **)a4 + 3), 0x208u, v24);
    FileInfoFromRpc = v25;
    if ( v25 < 0 )
    {
      AslLogCallPrintf(1, "RetrieveFileInfoFileInv", 629, "StringCbCopyW [%#x]", v25);
      File::~File((File *)v47);
      return FileInfoFromRpc;
    }
    v26 = (const unsigned __int16 *)v51;
    if ( v51[3] > (unsigned __int16 *)7 )
      v26 = v51[0];
    v27 = StringCbCopyW(*((unsigned __int16 **)a4 + 4), 0x208u, v26);
    FileInfoFromRpc = v27;
    if ( v27 < 0 )
    {
      AslLogCallPrintf(1, "RetrieveFileInfoFileInv", 636, "StringCbCopyW [%#x]", v27);
      File::~File((File *)v47);
      return FileInfoFromRpc;
    }
    v28 = StringCbPrintfW(*((unsigned __int16 **)a4 + 5), 0x208u, L"%d", v61);
    FileInfoFromRpc = v28;
    if ( v28 < 0 )
    {
      AslLogCallPrintf(1, "RetrieveFileInfoFileInv", 643, "StringCbPrintfW [%#x]", v28);
      File::~File((File *)v47);
      return FileInfoFromRpc;
    }
    v29 = (const unsigned __int16 *)v54;
    if ( v54[3] > (unsigned __int16 *)7 )
      v29 = v54[0];
    v30 = StringCbCopyW(*((unsigned __int16 **)a4 + 6), 0x208u, v29);
    FileInfoFromRpc = v30;
    if ( v30 < 0 )
    {
      AslLogCallPrintf(1, "RetrieveFileInfoFileInv", 650, "StringCbCopyW [%#x]", v30);
      File::~File((File *)v47);
      return FileInfoFromRpc;
    }
    v31 = (const unsigned __int16 *)v53;
    if ( v53[3] > (unsigned __int16 *)7 )
      v31 = v53[0];
    v32 = StringCbCopyW(*((unsigned __int16 **)a4 + 7), 0x208u, v31);
    FileInfoFromRpc = v32;
    if ( v32 < 0 )
    {
      AslLogCallPrintf(1, "RetrieveFileInfoFileInv", 657, "StringCbCopyW [%#x]", v32);
      File::~File((File *)v47);
      return FileInfoFromRpc;
    }
    v33 = (const unsigned __int16 *)v55;
    if ( v55[3] > (unsigned __int16 *)7 )
      v33 = v55[0];
    v34 = StringCbCopyW(*((unsigned __int16 **)a4 + 8), 0x208u, v33);
    FileInfoFromRpc = v34;
    if ( v34 < 0 )
    {
      AslLogCallPrintf(1, "RetrieveFileInfoFileInv", 664, "StringCbCopyW [%#x]", v34);
      File::~File((File *)v47);
      return FileInfoFromRpc;
    }
    v35 = (const unsigned __int16 *)v50;
    if ( v50[3] > (unsigned __int16 *)7 )
      v35 = v50[0];
    v36 = StringCbCopyW(*((unsigned __int16 **)a4 + 9), 0x208u, v35);
    FileInfoFromRpc = v36;
    if ( v36 < 0 )
    {
      AslLogCallPrintf(1, "RetrieveFileInfoFileInv", 671, "StringCbCopyW [%#x]", v36);
      File::~File((File *)v47);
      return FileInfoFromRpc;
    }
    v37 = (const unsigned __int16 *)v57;
    if ( v57[3] > (unsigned __int16 *)7 )
      v37 = v57[0];
    v38 = StringCbCopyW(*((unsigned __int16 **)a4 + 10), 0x208u, v37);
    FileInfoFromRpc = v38;
    if ( v38 < 0 )
    {
      AslLogCallPrintf(1, "RetrieveFileInfoFileInv", 678, "StringCbCopyW [%#x]", v38);
      File::~File((File *)v47);
      return FileInfoFromRpc;
    }
    v39 = (const unsigned __int16 *)v58;
    if ( v58[3] > (unsigned __int16 *)7 )
      v39 = v58[0];
    v40 = StringCbCopyW(*((unsigned __int16 **)a4 + 11), 0x208u, v39);
    FileInfoFromRpc = v40;
    if ( v40 < 0 )
    {
      AslLogCallPrintf(1, "RetrieveFileInfoFileInv", 685, "StringCbCopyW [%#x]", v40);
      File::~File((File *)v47);
      return FileInfoFromRpc;
    }
    v41 = (const unsigned __int16 *)v59;
    if ( v59[3] > (unsigned __int16 *)7 )
      v41 = v59[0];
    v42 = StringCbCopyW(*((unsigned __int16 **)a4 + 12), 0x208u, v41);
    FileInfoFromRpc = v42;
    if ( v42 < 0 )
    {
      AslLogCallPrintf(1, "RetrieveFileInfoFileInv", 692, "StringCbCopyW [%#x]", v42);
      File::~File((File *)v47);
    }
    else
    {
LABEL_74:
      File::~File((File *)v47);
      FileInfoFromRpc = 0;
    }
  }
  catch ( const std::exception *v45 )
  {
    v44 = (const char *)(*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v45 + 8LL))(v45);
    AslLogCallPrintf(1, "RetrieveFileInfoFileInv", 699, "Exception caught: %s", v44);
    return (unsigned int)-2147467259;
  }
  catch ( ... )
  {
    AslLogCallPrintf(1, "RetrieveFileInfoFileInv", 706, "Unknown exception caught [%#x]", -2147467259);
    return (unsigned int)-2147467259;
  }
  return FileInfoFromRpc;
}

```

## disassembly

```asm
0x180017fe0  mov     [rsp+arg_8], rbx
0x180017fe5  mov     [rsp+arg_10], rsi
0x180017fea  push    rdi
0x180017feb  push    r12
0x180017fed  push    r13
0x180017fef  push    r14
0x180017ff1  push    r15
0x180017ff3  sub     rsp, 3A0h
0x180017ffa  mov     rax, cs:__security_cookie
0x180018001  xor     rax, rsp
0x180018004  mov     [rsp+3C8h+var_38], rax
0x18001800c  mov     rdi, r9
0x18001800f  mov     r14d, edx
0x180018012  mov     rsi, rcx
0x180018015  mov     al, dl
0x180018017  and     al, 1
0x180018019  mov     [rsp+3C8h+var_395], al
0x18001801d  mov     r13d, edx
0x180018020  and     r13d, 10h
0x180018024  setnz   [rsp+3C8h+var_396]
0x180018029  mov     r12d, edx
0x18001802c  and     r12d, 20h
0x180018030  setnz   [rsp+3C8h+var_397]
0x180018035  mov     r15d, edx
0x180018038  and     r15d, 40h
0x18001803c  setnz   [rsp+3C8h+var_398]
0x180018041  test    r13d, r13d
0x180018044  jnz     short loc_180018059
0x180018046  test    r12d, r12d
0x180018049  jnz     short loc_180018059
0x18001804b  test    r15d, r15d
0x18001804e  jnz     short loc_180018059
0x180018050  test    r8b, r8b
0x180018053  jz      short loc_180018059
0x180018055  xor     bl, bl
0x180018057  jmp     short loc_18001805B
0x180018059  mov     bl, 1
0x18001805b  mov     ecx, cs:_tls_index
0x180018061  mov     rax, gs:58h
0x18001806a  mov     edx, 4
0x18001806f  mov     rax, [rax+rcx*8]
0x180018073  mov     ecx, [rdx+rax]
0x180018076  cmp     cs:dword_180122CE8, ecx
0x18001807c  jg      loc_18001868D
0x180018082  xor     dl, dl
0x180018084  call    wil__init_once_nothrow__lambda_eed0231a23d8c5c16b0fe5d0e10ec71b___
0x180018089  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite> `wil::Feature<__WilFeatureTraits_Feature_AmiCache_SQLite>::GetImpl(void)'::`2'::impl
0x180018090  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AmiCache_SQLite@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AmiCache_SQLite>::__private_IsEnabled(void)
0x180018095  test    al, al
0x180018097  mov     rax, cs:qword_180121630
0x18001809e  jnz     short loc_1800180A7
0x1800180a0  mov     rax, cs:?g_CacheProvider@@3PEAVTelCacheProvider@@EA; TelCacheProvider * g_CacheProvider
0x1800180a7  test    rax, rax
0x1800180aa  jz      short loc_1800180B7
0x1800180ac  cmp     qword ptr [rax+58h], 0
0x1800180b1  jz      short loc_1800180B7
0x1800180b3  mov     al, 1
0x1800180b5  jmp     short loc_1800180B9
0x1800180b7  xor     al, al
0x1800180b9  test    bl, bl
0x1800180bb  jnz     short loc_180018101
0x1800180bd  test    al, al
0x1800180bf  jnz     short loc_180018101
0x1800180c1  bt      r14d, 10h
0x1800180c6  jb      short loc_180018101
0x1800180c8  mov     rdx, rdi; struct _FILE_INFO *
0x1800180cb  mov     rcx, rsi; unsigned __int16 *
0x1800180ce  call    ?RetrieveFileInfoFromRpc@@YAJPEBGPEAU_FILE_INFO@@@Z; RetrieveFileInfoFromRpc(ushort const *,_FILE_INFO *)
0x1800180d3  mov     ebx, eax
0x1800180d5  test    eax, eax
0x1800180d7  js      short loc_180018101
0x1800180d9  mov     [rsp+3C8h+var_3A8], rsi
0x1800180de  lea     r9, aRetrievedLsInf_0; "Retrieved \"%ls\" info from RPC"
0x1800180e5  mov     r8d, 242h
0x1800180eb  lea     rdx, aRetrievefilein; "RetrieveFileInfoFileInv"
0x1800180f2  mov     ecx, 3
0x1800180f7  call    AslLogCallPrintf
0x1800180fc  jmp     loc_18001865E
0x180018101  mov     r14d, 1
0x180018107  mov     cs:?DisableThrottling@UtcThrottle@@2_NA, r14b; bool UtcThrottle::DisableThrottling
0x18001810e  mov     rdx, rsi
0x180018111  lea     rcx, [rsp+3C8h+var_388]
0x180018116  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001811b  nop
0x18001811c  mov     al, [rsp+3C8h+var_398]
0x180018120  mov     [rsp+3C8h+var_3A0], al
0x180018124  mov     al, [rsp+3C8h+var_397]
0x180018128  mov     byte ptr [rsp+3C8h+var_3A8], al
0x18001812c  mov     r9b, [rsp+3C8h+var_396]
0x180018131  mov     r8b, [rsp+3C8h+var_395]
0x180018136  lea     rdx, [rsp+3C8h+var_388]
0x18001813b  lea     rcx, [rsp+3C8h+var_368]
0x180018140  call    ??0File@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N111@Z; File::File(std::wstring const &,bool,bool,bool,bool)
0x180018145  nop
0x180018146  lea     rcx, [rsp+3C8h+var_388]
0x18001814b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018150  cmp     [rsp+3C8h+var_300], 0
0x180018159  jz      loc_18001863C
0x18001815f  cmp     [rsp+3C8h+var_2E0], 0
0x180018168  jz      loc_18001863C
0x18001816e  lea     r8, [rsp+3C8h+var_310]
0x180018176  cmp     [rsp+3C8h+var_2F8], 7
0x18001817f  cmova   r8, [rsp+3C8h+var_310]; unsigned __int16 *
0x180018188  lea     r11d, [r14+2Ch]
0x18001818c  mov     edx, r11d; unsigned __int64
0x18001818f  mov     rcx, [rdi+8]; unsigned __int16 *
0x180018193  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018198  mov     ebx, eax
0x18001819a  test    eax, eax
0x18001819c  jns     short loc_1800181CF
0x18001819e  mov     dword ptr [rsp+3C8h+var_3A8], eax
0x1800181a2  lea     r9, aStringcchcopyw_0; "StringCchCopyW [%#x]"
0x1800181a9  mov     r8d, 25Fh
0x1800181af  lea     rdx, aRetrievefilein; "RetrieveFileInfoFileInv"
0x1800181b6  mov     ecx, r14d
0x1800181b9  call    AslLogCallPrintf
0x1800181be  nop
0x1800181bf  lea     rcx, [rsp+3C8h+var_368]; this
0x1800181c4  call    ??1File@@UEAA@XZ; File::~File(void)
0x1800181c9  nop
0x1800181ca  jmp     loc_18001865E
0x1800181cf  lea     r8, [rsp+3C8h+var_2F0]
0x1800181d7  cmp     [rsp+3C8h+var_2D8], 7
0x1800181e0  cmova   r8, [rsp+3C8h+var_2F0]; unsigned __int16 *
0x1800181e9  mov     rdx, r11; unsigned __int64
0x1800181ec  mov     rcx, [rdi]; unsigned __int16 *
0x1800181ef  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800181f4  mov     ebx, eax
0x1800181f6  test    eax, eax
0x1800181f8  jns     short loc_18001822B
0x1800181fa  mov     dword ptr [rsp+3C8h+var_3A8], eax
0x1800181fe  lea     r9, aStringcchcopyw_0; "StringCchCopyW [%#x]"
0x180018205  mov     r8d, 265h
0x18001820b  lea     rdx, aRetrievefilein; "RetrieveFileInfoFileInv"
0x180018212  mov     ecx, r14d
0x180018215  call    AslLogCallPrintf
0x18001821a  nop
0x18001821b  lea     rcx, [rsp+3C8h+var_368]; this
0x180018220  call    ??1File@@UEAA@XZ; File::~File(void)
0x180018225  nop
0x180018226  jmp     loc_18001865E
0x18001822b  test    r13d, r13d
0x18001822e  jnz     short loc_18001823E
0x180018230  test    r12d, r12d
0x180018233  jnz     short loc_18001823E
0x180018235  test    r15d, r15d
0x180018238  jz      loc_18001862D
0x18001823e  lea     r8, [rsp+3C8h+var_1D0]
0x180018246  mov     r15d, 7
0x18001824c  cmp     [rsp+3C8h+var_1B8], r15
0x180018254  cmova   r8, [rsp+3C8h+var_1D0]; unsigned __int16 *
0x18001825d  mov     esi, 208h
0x180018262  mov     edx, esi; unsigned __int64
0x180018264  mov     rcx, [rdi+10h]; unsigned __int16 *
0x180018268  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18001826d  mov     ebx, eax
0x18001826f  test    eax, eax
0x180018271  jns     short loc_1800182A2
0x180018273  mov     dword ptr [rsp+3C8h+var_3A8], eax
0x180018277  lea     r9, aStringcbcopywX; "StringCbCopyW [%#x]"
0x18001827e  lea     r8d, [rsi+66h]
0x180018282  lea     rdx, aRetrievefilein; "RetrieveFileInfoFileInv"
0x180018289  mov     ecx, r14d
0x18001828c  call    AslLogCallPrintf
0x180018291  nop
0x180018292  lea     rcx, [rsp+3C8h+var_368]; this
0x180018297  call    ??1File@@UEAA@XZ; File::~File(void)
0x18001829c  nop
0x18001829d  jmp     loc_18001865E
0x1800182a2  lea     r8, [rsp+3C8h+var_270]
0x1800182aa  cmp     [rsp+3C8h+var_258], r15
0x1800182b2  cmova   r8, [rsp+3C8h+var_270]; unsigned __int16 *
0x1800182bb  mov     rdx, rsi; unsigned __int64
0x1800182be  mov     rcx, [rdi+18h]; unsigned __int16 *
0x1800182c2  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800182c7  mov     ebx, eax
0x1800182c9  test    eax, eax
0x1800182cb  jns     short loc_1800182FE
0x1800182cd  mov     dword ptr [rsp+3C8h+var_3A8], eax
0x1800182d1  lea     r9, aStringcbcopywX; "StringCbCopyW [%#x]"
0x1800182d8  mov     r8d, 275h
0x1800182de  lea     rdx, aRetrievefilein; "RetrieveFileInfoFileInv"
0x1800182e5  mov     ecx, r14d
0x1800182e8  call    AslLogCallPrintf
0x1800182ed  nop
0x1800182ee  lea     rcx, [rsp+3C8h+var_368]; this
0x1800182f3  call    ??1File@@UEAA@XZ; File::~File(void)
0x1800182f8  nop
0x1800182f9  jmp     loc_18001865E
0x1800182fe  lea     r8, [rsp+3C8h+var_2B0]
0x180018306  cmp     [rsp+3C8h+var_298], r15
0x18001830e  cmova   r8, [rsp+3C8h+var_2B0]; unsigned __int16 *
0x180018317  mov     rdx, rsi; unsigned __int64
0x18001831a  mov     rcx, [rdi+20h]; unsigned __int16 *
0x18001831e  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180018323  mov     ebx, eax
0x180018325  test    eax, eax
0x180018327  jns     short loc_18001835A
0x180018329  mov     dword ptr [rsp+3C8h+var_3A8], eax
0x18001832d  lea     r9, aStringcbcopywX; "StringCbCopyW [%#x]"
0x180018334  mov     r8d, 27Ch
0x18001833a  lea     rdx, aRetrievefilein; "RetrieveFileInfoFileInv"
0x180018341  mov     ecx, r14d
0x180018344  call    AslLogCallPrintf
0x180018349  nop
0x18001834a  lea     rcx, [rsp+3C8h+var_368]; this
0x18001834f  call    ??1File@@UEAA@XZ; File::~File(void)
0x180018354  nop
0x180018355  jmp     loc_18001865E
0x18001835a  mov     r9d, [rsp+3C8h+var_48]
0x180018362  lea     r8, aD; "%d"
0x180018369  mov     rdx, rsi; unsigned __int64
0x18001836c  mov     rcx, [rdi+28h]; unsigned __int16 *
0x180018370  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180018375  mov     ebx, eax
0x180018377  test    eax, eax
0x180018379  jns     short loc_1800183AC
0x18001837b  mov     dword ptr [rsp+3C8h+var_3A8], eax
0x18001837f  lea     r9, aStringcbprintf; "StringCbPrintfW [%#x]"
0x180018386  mov     r8d, 283h
0x18001838c  lea     rdx, aRetrievefilein; "RetrieveFileInfoFileInv"
0x180018393  mov     ecx, r14d
0x180018396  call    AslLogCallPrintf
0x18001839b  nop
0x18001839c  lea     rcx, [rsp+3C8h+var_368]; this
0x1800183a1  call    ??1File@@UEAA@XZ; File::~File(void)
0x1800183a6  nop
0x1800183a7  jmp     loc_18001865E
0x1800183ac  lea     r8, [rsp+3C8h+var_230]
0x1800183b4  cmp     [rsp+3C8h+var_218], r15
0x1800183bc  cmova   r8, [rsp+3C8h+var_230]; unsigned __int16 *
0x1800183c5  mov     rdx, rsi; unsigned __int64
0x1800183c8  mov     rcx, [rdi+30h]; unsigned __int16 *
0x1800183cc  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800183d1  mov     ebx, eax
0x1800183d3  test    eax, eax
0x1800183d5  jns     short loc_180018408
0x1800183d7  mov     dword ptr [rsp+3C8h+var_3A8], eax
0x1800183db  lea     r9, aStringcbcopywX; "StringCbCopyW [%#x]"
0x1800183e2  mov     r8d, 28Ah
0x1800183e8  lea     rdx, aRetrievefilein; "RetrieveFileInfoFileInv"
0x1800183ef  mov     ecx, r14d
0x1800183f2  call    AslLogCallPrintf
0x1800183f7  nop
0x1800183f8  lea     rcx, [rsp+3C8h+var_368]; this
0x1800183fd  call    ??1File@@UEAA@XZ; File::~File(void)
0x180018402  nop
0x180018403  jmp     loc_18001865E
0x180018408  lea     r8, [rsp+3C8h+var_250]
0x180018410  cmp     [rsp+3C8h+var_238], r15
0x180018418  cmova   r8, [rsp+3C8h+var_250]; unsigned __int16 *
0x180018421  mov     rdx, rsi; unsigned __int64
0x180018424  mov     rcx, [rdi+38h]; unsigned __int16 *
0x180018428  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18001842d  mov     ebx, eax
0x18001842f  test    eax, eax
0x180018431  jns     short loc_180018464
0x180018433  mov     dword ptr [rsp+3C8h+var_3A8], eax
0x180018437  lea     r9, aStringcbcopywX; "StringCbCopyW [%#x]"
0x18001843e  mov     r8d, 291h
0x180018444  lea     rdx, aRetrievefilein; "RetrieveFileInfoFileInv"
0x18001844b  mov     ecx, r14d
0x18001844e  call    AslLogCallPrintf
0x180018453  nop
0x180018454  lea     rcx, [rsp+3C8h+var_368]; this
0x180018459  call    ??1File@@UEAA@XZ; File::~File(void)
0x18001845e  nop
0x18001845f  jmp     loc_18001865E
0x180018464  lea     r8, [rsp+3C8h+var_210]
0x18001846c  cmp     [rsp+3C8h+var_1F8], r15
0x180018474  cmova   r8, [rsp+3C8h+var_210]; unsigned __int16 *
0x18001847d  mov     rdx, rsi; unsigned __int64
0x180018480  mov     rcx, [rdi+40h]; unsigned __int16 *
0x180018484  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180018489  mov     ebx, eax
0x18001848b  test    eax, eax
0x18001848d  jns     short loc_1800184C0
0x18001848f  mov     dword ptr [rsp+3C8h+var_3A8], eax
0x180018493  lea     r9, aStringcbcopywX; "StringCbCopyW [%#x]"
0x18001849a  mov     r8d, 298h
0x1800184a0  lea     rdx, aRetrievefilein; "RetrieveFileInfoFileInv"
0x1800184a7  mov     ecx, r14d
0x1800184aa  call    AslLogCallPrintf
0x1800184af  nop
0x1800184b0  lea     rcx, [rsp+3C8h+var_368]; this
0x1800184b5  call    ??1File@@UEAA@XZ; File::~File(void)
0x1800184ba  nop
0x1800184bb  jmp     loc_18001865E
0x1800184c0  lea     r8, [rsp+3C8h+var_2D0]
0x1800184c8  cmp     [rsp+3C8h+var_2B8], r15
0x1800184d0  cmova   r8, [rsp+3C8h+var_2D0]; unsigned __int16 *
0x1800184d9  mov     rdx, rsi; unsigned __int64
0x1800184dc  mov     rcx, [rdi+48h]; unsigned __int16 *
0x1800184e0  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800184e5  mov     ebx, eax
0x1800184e7  test    eax, eax
0x1800184e9  jns     short loc_18001851C
0x1800184eb  mov     dword ptr [rsp+3C8h+var_3A8], eax
0x1800184ef  lea     r9, aStringcbcopywX; "StringCbCopyW [%#x]"
0x1800184f6  mov     r8d, 29Fh
  ... truncated ...
```
