# CEcoScoreTaskHandler::Worker(void)

- ea: `0x1800073f0`
- end: `0x180007869`
- name: `?Worker@CEcoScoreTaskHandler@@EEAAJXZ`
- size: `1145`
- prototype: `__int64 __fastcall(CEcoScoreTaskHandler *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800024d8`
- `0x1800032d8`
- `0x1800058fc`
- `0x180005e6c`
- `0x180006654`
- `0x180006858`
- `0x1800073f0`
- `0x180007c56`
- `0x180007c62`
- `0x180007c90`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18000751d`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18000751d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800074dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800074dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800076e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007721`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007731`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007794`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800076e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007721`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007731`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180007794`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007767`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007767`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000774d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000774d`

## string_xrefs

- `0x1800075b5`: `onecore\base\sustainability\tasks\ecoscore\dll\ecoscoretask.cpp`
- `0x18000766d`: `onecore\base\sustainability\tasks\ecoscore\dll\ecoscoretask.cpp`
- `0x18000770d`: `onecore\base\sustainability\tasks\ecoscore\dll\ecoscoretask.cpp`
- `0x180007804`: `onecore\base\sustainability\tasks\ecoscore\dll\ecoscoretask.cpp`

## pseudocode

```c
__int64 __fastcall CEcoScoreTaskHandler::Worker(CEcoScoreTaskHandler *this)
{
  HRESULT v1; // eax
  int v2; // edx
  unsigned int v3; // r8d
  int v4; // ebx
  int v5; // eax
  PCWSTR v6; // rcx
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rbx
  HRESULT v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rcx
  PCWSTR v19; // rcx
  PCWSTR v21; // rcx
  int v22[2]; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v23; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v24; // [rsp+38h] [rbp-D0h] BYREF
  HSTRING v25; // [rsp+40h] [rbp-C8h] BYREF
  PCWSTR StringRawBuffer; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v28; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v29; // [rsp+60h] [rbp-A8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-A0h] BYREF
  HSTRING string; // [rsp+80h] [rbp-88h] BYREF
  void **v32; // [rsp+88h] [rbp-80h] BYREF
  int v33; // [rsp+90h] [rbp-78h] BYREF
  char v34; // [rsp+94h] [rbp-74h]
  int v35; // [rsp+B8h] [rbp-50h] BYREF
  const char *v36; // [rsp+C0h] [rbp-48h]
  __int64 v37; // [rsp+C8h] [rbp-40h]
  char v38; // [rsp+D0h] [rbp-38h]
  int v39; // [rsp+D8h] [rbp-30h]
  char v40[152]; // [rsp+E0h] [rbp-28h] BYREF
  __int128 v41; // [rsp+178h] [rbp+70h]
  int v42; // [rsp+188h] [rbp+80h]
  __int64 v43; // [rsp+190h] [rbp+88h]
  int *v44; // [rsp+198h] [rbp+90h]
  __int64 v45; // [rsp+1A0h] [rbp+98h]
  __int64 v46; // [rsp+1A8h] [rbp+A0h]
  void ***v47; // [rsp+1B0h] [rbp+A8h]
  __int64 v48; // [rsp+1B8h] [rbp+B0h]
  int v49; // [rsp+1C0h] [rbp+B8h]
  int *v50; // [rsp+1C8h] [rbp+C0h]
  char v51; // [rsp+1D0h] [rbp+C8h]
  wil::details::in1diag3 *retaddr; // [rsp+220h] [rbp+118h]

  v33 = 0;
  v34 = 0;
  v38 = 0;
  v35 = 0;
  v36 = "GetEcoScoreActivity";
  v37 = 0;
  v39 = 0;
  v41 = 0;
  memset_0(v40, 0, sizeof(v40));
  v42 = 1;
  v43 = 0;
  v45 = 0;
  v44 = &v33;
  v47 = &v32;
  v50 = &v35;
  v32 = &EcoScoreTaskTelemetry::GetEcoScoreActivity::`vftable';
  v46 = 0;
  v48 = 0;
  v49 = 0;
  v51 = 0;
  EcoScoreTaskTelemetry::GetEcoScoreActivity::StartActivity((EcoScoreTaskTelemetry::GetEcoScoreActivity *)&v32);
  *(_QWORD *)v22 = 0;
  string = 0;
  v1 = WindowsCreateStringReference(
         L"Windows.Internal.Sustainability.EcoScore.EcoScoreManager",
         0x38u,
         &hstringHeader,
         &string);
  if ( v1 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v1, v2, v3);
    JUMPOUT(0x180007868LL);
  }
  *(_QWORD *)v22 = 0;
  StringRawBuffer = 0;
  v4 = RoActivateInstance(string, &StringRawBuffer);
  if ( v4 < 0 )
    goto LABEL_36;
  v5 = memcmp_0(&GUID_aabf0a84_5377_48df_9d4f_5e3efa4fccbe, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u);
  v6 = StringRawBuffer;
  if ( !v5 )
  {
    *(_QWORD *)v22 = StringRawBuffer;
    goto LABEL_7;
  }
  v4 = (**(__int64 (__fastcall ***)(PCWSTR, GUID *, int *))StringRawBuffer)(
         StringRawBuffer,
         &GUID_aabf0a84_5377_48df_9d4f_5e3efa4fccbe,
         v22);
  (*(void (__fastcall **)(PCWSTR))(*(_QWORD *)StringRawBuffer + 16LL))(StringRawBuffer);
  if ( v4 < 0 )
  {
LABEL_36:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecore\\base\\sustainability\\tasks\\ecoscore\\dll\\ecoscoretask.cpp",
      (const char *)(unsigned int)v4,
      v22[0]);
LABEL_37:
    v21 = *(PCWSTR *)v22;
    if ( *(_QWORD *)v22 )
    {
      *(_QWORD *)v22 = 0;
      (*(void (__fastcall **)(PCWSTR))(*(_QWORD *)v21 + 16LL))(v21);
    }
    EcoScoreTaskTelemetry::GetEcoScoreActivity::~GetEcoScoreActivity((EcoScoreTaskTelemetry::GetEcoScoreActivity *)&v32);
    return (unsigned int)v4;
  }
  v6 = *(PCWSTR *)v22;
LABEL_7:
  v23 = 0;
  v7 = (*(__int64 (__fastcall **)(PCWSTR, __int64 *))(*(_QWORD *)v6 + 48LL))(v6, &v23);
  v4 = v7;
  if ( v7 < 0 )
  {
    v8 = 60;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\sustainability\\tasks\\ecoscore\\dll\\ecoscoretask.cpp",
      (const char *)(unsigned int)v7,
      v22[0]);
LABEL_10:
    v9 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    goto LABEL_37;
  }
  v28 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 48LL))(v23, &v28);
  v4 = v7;
  if ( v7 < 0 )
  {
    v8 = 62;
    goto LABEL_9;
  }
  v29 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 56LL))(v23, &v29);
  v4 = v7;
  if ( v7 < 0 )
  {
    v8 = 64;
    goto LABEL_9;
  }
  v24 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 64LL))(v23, &v24);
  v4 = v10;
  if ( v10 < 0 )
  {
    v11 = 66;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\sustainability\\tasks\\ecoscore\\dll\\ecoscoretask.cpp",
      (const char *)(unsigned int)v10,
      v22[0]);
    goto LABEL_19;
  }
  LODWORD(v27) = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 56LL))(v24, &v27);
  v4 = v10;
  if ( v10 < 0 )
  {
    v11 = 68;
    goto LABEL_18;
  }
  v25 = 0;
  if ( (_DWORD)v27 )
  {
    v13 = v23;
    v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v23 + 80LL);
    WindowsDeleteString(0);
    v25 = 0;
    v15 = v14(v13, &v25);
    v4 = v15;
    if ( v15 < 0 )
    {
      v16 = 72;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecore\\base\\sustainability\\tasks\\ecoscore\\dll\\ecoscoretask.cpp",
        (const char *)(unsigned int)v15,
        v22[0]);
      WindowsDeleteString(v25);
      v25 = 0;
LABEL_19:
      v12 = v24;
      if ( v24 )
      {
        v24 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      }
      goto LABEL_10;
    }
  }
  else
  {
    WindowsDeleteString(0);
    v25 = 0;
    v15 = WindowsCreateString(L"{}", 2u, &v25);
    v4 = v15;
    if ( v15 < 0 )
    {
      v16 = 76;
      goto LABEL_26;
    }
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v25, 0);
  EcoScoreTaskTelemetry::EcoScoreResultEvent<double &,double &,unsigned short const *>(&v29, &v28, &StringRawBuffer);
  wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(&v32);
  WindowsDeleteString(v25);
  v17 = v24;
  v25 = 0;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  v18 = v23;
  if ( v23 )
  {
    v23 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  v19 = *(PCWSTR *)v22;
  if ( *(_QWORD *)v22 )
  {
    *(_QWORD *)v22 = 0;
    (*(void (__fastcall **)(PCWSTR))(*(_QWORD *)v19 + 16LL))(v19);
  }
  EcoScoreTaskTelemetry::GetEcoScoreActivity::~GetEcoScoreActivity((EcoScoreTaskTelemetry::GetEcoScoreActivity *)&v32);
  return 0;
}

```

## disassembly

```asm
0x1800073f0  mov     rax, rsp
0x1800073f3  push    rbp
0x1800073f4  push    rbx
0x1800073f5  push    rsi
0x1800073f6  push    rdi
0x1800073f7  lea     rbp, [rax-118h]
0x1800073fe  sub     rsp, 1F8h
0x180007405  movaps  xmmword ptr [rax-38h], xmm6
0x180007409  mov     rax, cs:__security_cookie
0x180007410  xor     rax, rsp
0x180007413  mov     [rbp+110h+var_40], rax
0x18000741a  xor     esi, esi
0x18000741c  lea     rax, aGetecoscoreact; "GetEcoScoreActivity"
0x180007423  xorps   xmm0, xmm0
0x180007426  mov     [rbp+110h+var_188], esi
0x180007429  xor     edx, edx; Val
0x18000742b  mov     [rbp+110h+var_184], sil
0x18000742f  mov     r8d, 98h; Size
0x180007435  mov     [rbp+110h+var_148], sil
0x180007439  lea     rcx, [rbp+110h+var_138]; void *
0x18000743d  mov     [rbp+110h+var_160], esi
0x180007440  mov     [rbp+110h+var_158], rax
0x180007444  mov     [rbp+110h+var_150], rsi
0x180007448  mov     [rbp+110h+var_140], esi
0x18000744b  movdqa  [rbp+110h+var_A0], xmm0
0x180007450  call    memset_0
0x180007455  xor     eax, eax
0x180007457  mov     [rbp+110h+var_90], 1
0x180007461  mov     [rbp+110h+var_88], rax
0x180007468  lea     rcx, [rbp+110h+var_190]; this
0x18000746c  lea     rax, [rbp+110h+var_188]
0x180007470  mov     [rbp+110h+var_78], rsi
0x180007477  mov     [rbp+110h+var_80], rax
0x18000747e  lea     rax, [rbp+110h+var_190]
0x180007482  mov     [rbp+110h+var_68], rax
0x180007489  lea     rax, [rbp+110h+var_160]
0x18000748d  mov     [rbp+110h+var_50], rax
0x180007494  lea     rax, ??_7GetEcoScoreActivity@EcoScoreTaskTelemetry@@6B@; const EcoScoreTaskTelemetry::GetEcoScoreActivity::`vftable'
0x18000749b  mov     [rbp+110h+var_190], rax
0x18000749f  mov     [rbp+110h+var_70], rsi
0x1800074a6  mov     [rbp+110h+var_60], rsi
0x1800074ad  mov     [rbp+110h+var_58], esi
0x1800074b3  mov     [rbp+110h+var_48], sil
0x1800074ba  call    ?StartActivity@GetEcoScoreActivity@EcoScoreTaskTelemetry@@QEAAXXZ; EcoScoreTaskTelemetry::GetEcoScoreActivity::StartActivity(void)
0x1800074bf  lea     r9, [rsp+210h+string]; string
0x1800074c4  mov     qword ptr [rsp+210h+var_1F0], rsi
0x1800074c9  lea     r8, [rsp+210h+hstringHeader]; hstringHeader
0x1800074ce  mov     [rsp+210h+string], rsi
0x1800074d3  lea     edx, [rsi+38h]; length
0x1800074d6  lea     rcx, ?RuntimeClass_Windows_Internal_Sustainability_EcoScore_EcoScoreManager@@3QBGB; "Windows.Internal.Sustainability.EcoScor"...
0x1800074dd  call    cs:__imp_WindowsCreateStringReference
0x1800074e3  test    eax, eax
0x1800074e5  js      loc_180007861
0x1800074eb  mov     rcx, qword ptr [rsp+210h+var_1F0]
0x1800074f0  mov     rbx, [rsp+210h+string]
0x1800074f5  test    rcx, rcx
0x1800074f8  jz      short loc_18000750B
0x1800074fa  mov     qword ptr [rsp+210h+var_1F0], rsi
0x1800074ff  mov     rax, [rcx]
0x180007502  mov     rax, [rax+10h]
0x180007506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000750b  lea     rdx, [rsp+210h+var_1D0]
0x180007510  mov     qword ptr [rsp+210h+var_1F0], rsi; int
0x180007515  mov     rcx, rbx
0x180007518  mov     [rsp+210h+var_1D0], rsi
0x18000751d  call    cs:__imp_RoActivateInstance
0x180007523  mov     ebx, eax
0x180007525  test    eax, eax
0x180007527  js      loc_1800077FD
0x18000752d  mov     r8d, 10h; Size
0x180007533  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18000753a  lea     rcx, _GUID_aabf0a84_5377_48df_9d4f_5e3efa4fccbe; Buf1
0x180007541  call    memcmp_0
0x180007546  mov     rcx, [rsp+210h+var_1D0]
0x18000754b  test    eax, eax
0x18000754d  jnz     short loc_180007556
0x18000754f  mov     qword ptr [rsp+210h+var_1F0], rcx
0x180007554  jmp     short loc_18000758D
0x180007556  mov     rax, [rcx]
0x180007559  lea     r8, [rsp+210h+var_1F0]
0x18000755e  lea     rdx, _GUID_aabf0a84_5377_48df_9d4f_5e3efa4fccbe
0x180007565  mov     rax, [rax]
0x180007568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000756d  mov     rcx, [rsp+210h+var_1D0]
0x180007572  mov     ebx, eax
0x180007574  mov     rax, [rcx]
0x180007577  mov     rax, [rax+10h]
0x18000757b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007580  test    ebx, ebx
0x180007582  js      loc_1800077FD
0x180007588  mov     rcx, qword ptr [rsp+210h+var_1F0]
0x18000758d  mov     [rsp+210h+var_1E8], rsi
0x180007592  lea     rdx, [rsp+210h+var_1E8]
0x180007597  mov     rax, [rcx]
0x18000759a  mov     rax, [rax+30h]
0x18000759e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075a3  mov     ebx, eax
0x1800075a5  test    eax, eax
0x1800075a7  jns     short loc_1800075E8
0x1800075a9  mov     edx, 3Ch ; '<'; void *
0x1800075ae  mov     rcx, [rbp+118h]; this
0x1800075b5  lea     r8, aOnecoreBaseSus; "onecore\\base\\sustainability\\tasks\\e"...
0x1800075bc  mov     r9d, eax; char *
0x1800075bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800075c4  mov     rcx, [rsp+210h+var_1E8]
0x1800075c9  test    rcx, rcx
0x1800075cc  jz      loc_180007818
0x1800075d2  mov     [rsp+210h+var_1E8], rsi
0x1800075d7  mov     rax, [rcx]
0x1800075da  mov     rax, [rax+10h]
0x1800075de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075e3  jmp     loc_180007818
0x1800075e8  mov     rcx, [rsp+210h+var_1E8]
0x1800075ed  lea     rdx, [rsp+210h+var_1C0]
0x1800075f2  xorps   xmm6, xmm6
0x1800075f5  movsd   [rsp+210h+var_1C0], xmm6
0x1800075fb  mov     rax, [rcx]
0x1800075fe  mov     rax, [rax+30h]
0x180007602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007607  mov     ebx, eax
0x180007609  test    eax, eax
0x18000760b  jns     short loc_180007614
0x18000760d  mov     edx, 3Eh ; '>'
0x180007612  jmp     short loc_1800075AE
0x180007614  mov     rcx, [rsp+210h+var_1E8]
0x180007619  lea     rdx, [rsp+210h+var_1B8]
0x18000761e  movsd   [rsp+210h+var_1B8], xmm6
0x180007624  mov     rax, [rcx]
0x180007627  mov     rax, [rax+38h]
0x18000762b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007630  mov     ebx, eax
0x180007632  test    eax, eax
0x180007634  jns     short loc_180007640
0x180007636  mov     edx, 40h ; '@'
0x18000763b  jmp     loc_1800075AE
0x180007640  mov     rcx, [rsp+210h+var_1E8]
0x180007645  lea     rdx, [rsp+210h+var_1E0]
0x18000764a  mov     [rsp+210h+var_1E0], rsi
0x18000764f  mov     rax, [rcx]
0x180007652  mov     rax, [rax+40h]
0x180007656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000765b  mov     ebx, eax
0x18000765d  test    eax, eax
0x18000765f  jns     short loc_1800076A0
0x180007661  mov     edx, 42h ; 'B'; void *
0x180007666  mov     rcx, [rbp+118h]; this
0x18000766d  lea     r8, aOnecoreBaseSus; "onecore\\base\\sustainability\\tasks\\e"...
0x180007674  mov     r9d, eax; char *
0x180007677  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000767c  mov     rcx, [rsp+210h+var_1E0]
0x180007681  test    rcx, rcx
0x180007684  jz      loc_1800075C4
0x18000768a  mov     [rsp+210h+var_1E0], rsi
0x18000768f  mov     rax, [rcx]
0x180007692  mov     rax, [rax+10h]
0x180007696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000769b  jmp     loc_1800075C4
0x1800076a0  mov     rcx, [rsp+210h+var_1E0]
0x1800076a5  lea     rdx, [rsp+210h+var_1C8]
0x1800076aa  mov     dword ptr [rsp+210h+var_1C8], esi
0x1800076ae  mov     rax, [rcx]
0x1800076b1  mov     rax, [rax+38h]
0x1800076b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076ba  mov     ebx, eax
0x1800076bc  test    eax, eax
0x1800076be  jns     short loc_1800076C7
0x1800076c0  mov     edx, 44h ; 'D'
0x1800076c5  jmp     short loc_180007666
0x1800076c7  xor     ecx, ecx; string
0x1800076c9  mov     [rsp+210h+var_1D8], rsi
0x1800076ce  cmp     dword ptr [rsp+210h+var_1C8], esi
0x1800076d2  jbe     short loc_180007731
0x1800076d4  mov     rdi, [rsp+210h+var_1E8]
0x1800076d9  mov     rax, [rdi]
0x1800076dc  mov     rbx, [rax+50h]
0x1800076e0  call    cs:__imp_WindowsDeleteString
0x1800076e6  lea     rdx, [rsp+210h+var_1D8]
0x1800076eb  mov     [rsp+210h+var_1D8], rsi
0x1800076f0  mov     rcx, rdi
0x1800076f3  mov     rax, rbx
0x1800076f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076fb  mov     ebx, eax
0x1800076fd  test    eax, eax
0x1800076ff  jns     short loc_180007760
0x180007701  mov     edx, 48h ; 'H'; void *
0x180007706  mov     rcx, [rbp+118h]; this
0x18000770d  lea     r8, aOnecoreBaseSus; "onecore\\base\\sustainability\\tasks\\e"...
0x180007714  mov     r9d, eax; char *
0x180007717  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000771c  mov     rcx, [rsp+210h+var_1D8]; string
0x180007721  call    cs:__imp_WindowsDeleteString
0x180007727  mov     [rsp+210h+var_1D8], rsi
0x18000772c  jmp     loc_18000767C
0x180007731  call    cs:__imp_WindowsDeleteString
0x180007737  lea     r8, [rsp+210h+var_1D8]; string
0x18000773c  mov     [rsp+210h+var_1D8], rsi
0x180007741  mov     edx, 2; length
0x180007746  lea     rcx, sourceString; "{}"
0x18000774d  call    cs:__imp_WindowsCreateString
0x180007753  mov     ebx, eax
0x180007755  test    eax, eax
0x180007757  jns     short loc_180007760
0x180007759  mov     edx, 4Ch ; 'L'
0x18000775e  jmp     short loc_180007706
0x180007760  mov     rcx, [rsp+210h+var_1D8]; string
0x180007765  xor     edx, edx; length
0x180007767  call    cs:__imp_WindowsGetStringRawBuffer
0x18000776d  lea     r8, [rsp+210h+var_1D0]
0x180007772  mov     [rsp+210h+var_1D0], rax
0x180007777  lea     rdx, [rsp+210h+var_1C0]
0x18000777c  lea     rcx, [rsp+210h+var_1B8]
0x180007781  call    ??$EcoScoreResultEvent@AEANAEANPEBG@EcoScoreTaskTelemetry@@SAXAEAN0$$QEAPEBG@Z; EcoScoreTaskTelemetry::EcoScoreResultEvent<double &,double &,ushort const *>(double &,double &,ushort const * &&)
0x180007786  lea     rcx, [rbp+110h+var_190]
0x18000778a  call    ?Stop@?$ActivityBase@VEcoScoreTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000778f  mov     rcx, [rsp+210h+var_1D8]; string
0x180007794  call    cs:__imp_WindowsDeleteString
0x18000779a  mov     rcx, [rsp+210h+var_1E0]
0x18000779f  mov     [rsp+210h+var_1D8], rsi
0x1800077a4  test    rcx, rcx
0x1800077a7  jz      short loc_1800077BA
0x1800077a9  mov     [rsp+210h+var_1E0], rsi
0x1800077ae  mov     rax, [rcx]
0x1800077b1  mov     rax, [rax+10h]
0x1800077b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077ba  mov     rcx, [rsp+210h+var_1E8]
0x1800077bf  test    rcx, rcx
0x1800077c2  jz      short loc_1800077D5
0x1800077c4  mov     [rsp+210h+var_1E8], rsi
0x1800077c9  mov     rax, [rcx]
0x1800077cc  mov     rax, [rax+10h]
0x1800077d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077d5  mov     rcx, qword ptr [rsp+210h+var_1F0]
0x1800077da  test    rcx, rcx
0x1800077dd  jz      short loc_1800077F0
0x1800077df  mov     qword ptr [rsp+210h+var_1F0], rsi
0x1800077e4  mov     rax, [rcx]
0x1800077e7  mov     rax, [rax+10h]
0x1800077eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077f0  lea     rcx, [rbp+110h+var_190]; this
0x1800077f4  call    ??1GetEcoScoreActivity@EcoScoreTaskTelemetry@@QEAA@XZ; EcoScoreTaskTelemetry::GetEcoScoreActivity::~GetEcoScoreActivity(void)
0x1800077f9  xor     eax, eax
0x1800077fb  jmp     short loc_18000783E
0x1800077fd  mov     rcx, [rbp+118h]; this
0x180007804  lea     r8, aOnecoreBaseSus; "onecore\\base\\sustainability\\tasks\\e"...
0x18000780b  mov     r9d, ebx; char *
0x18000780e  mov     edx, 3Ah ; ':'; void *
0x180007813  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007818  mov     rcx, qword ptr [rsp+210h+var_1F0]
0x18000781d  test    rcx, rcx
0x180007820  jz      short loc_180007833
0x180007822  mov     qword ptr [rsp+210h+var_1F0], rsi
0x180007827  mov     rax, [rcx]
0x18000782a  mov     rax, [rax+10h]
0x18000782e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007833  lea     rcx, [rbp+110h+var_190]; this
0x180007837  call    ??1GetEcoScoreActivity@EcoScoreTaskTelemetry@@QEAA@XZ; EcoScoreTaskTelemetry::GetEcoScoreActivity::~GetEcoScoreActivity(void)
0x18000783c  mov     eax, ebx
0x18000783e  mov     rcx, [rbp+110h+var_40]
0x180007845  xor     rcx, rsp; StackCookie
0x180007848  call    __security_check_cookie
0x18000784d  movaps  xmm6, [rsp+210h+var_38+8]
0x180007855  add     rsp, 1F8h
0x18000785c  pop     rdi
0x18000785d  pop     rsi
0x18000785e  pop     rbx
0x18000785f  pop     rbp
0x180007860  retn
0x180007861  mov     ecx, eax; this
0x180007863  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
