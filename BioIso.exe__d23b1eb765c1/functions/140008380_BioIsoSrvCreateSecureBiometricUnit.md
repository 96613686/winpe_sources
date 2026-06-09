# BioIsoSrvCreateSecureBiometricUnit

- ea: `0x140008380`
- end: `0x14000895f`
- name: `BioIsoSrvCreateSecureBiometricUnit`
- size: `1503`
- prototype: `__int64 __fastcall(struct _WINBIO_UNIT_SCHEMA *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct _GUID *Buf1, WINBIO_UNIT_ID **)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x140006c0c`
- `0x140006c30`
- `0x140006d54`
- `0x14000791c`
- `0x1400081b8`
- `0x140008380`
- `0x140008968`
- `0x1400089ac`
- `0x14000a2e4`
- `0x14000a420`
- `0x14000c9c4`
- `0x14000cda8`
- `0x140011bc8`
- `0x140012974`
- `0x14001bd40`
- `0x14001c2dc`
- `0x14001cb6c`
- `0x140043748`
- `0x1400597d4`

## string_xrefs

- `0x140008452`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400084a7`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140008509`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140008549`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400085c5`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140008613`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14000869d`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400086f9`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14000876f`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140008810`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140008918`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400083bf`: `CreateSecureBiometricUnit`

## pseudocode

```c
__int64 __fastcall BioIsoSrvCreateSecureBiometricUnit(
        struct _WINBIO_UNIT_SCHEMA *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct _GUID *Buf1,
        WINBIO_UNIT_ID **a6)
{
  int PlugIn; // eax
  unsigned int v11; // ebx
  int DllPlugIn; // eax
  unsigned int v13; // ebx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // eax
  unsigned int v17; // ebx
  int v18; // eax
  unsigned int v19; // ebx
  int v20; // eax
  unsigned int v21; // ebx
  int BiometricUnit; // eax
  unsigned int v23; // ebx
  int v24; // eax
  unsigned int v25; // ebx
  WINBIO_UNIT_ID *v26; // rax
  int v27; // [rsp+20h] [rbp-228h]
  struct _WINBIO_UNIT_SCHEMA *v28; // [rsp+30h] [rbp-218h] BYREF
  __int64 v29; // [rsp+38h] [rbp-210h] BYREF
  struct _GUID Buf2; // [rsp+40h] [rbp-208h] BYREF
  struct _WINBIO_UNIT_SCHEMA **v31; // [rsp+50h] [rbp-1F8h]
  char v32; // [rsp+58h] [rbp-1F0h]
  _BYTE v33[32]; // [rsp+60h] [rbp-1E8h] BYREF
  _BYTE v34[32]; // [rsp+80h] [rbp-1C8h] BYREF
  _BYTE v35[32]; // [rsp+A0h] [rbp-1A8h] BYREF
  _QWORD v36[42]; // [rsp+C0h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  v28 = a1;
  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v36,
    "CreateSecureBiometricUnit");
  v36[0] = &BioIsoProvider::CreateSecureBiometricUnit::`vftable';
  Buf2 = *Buf1;
  BioIsoProvider::CreateSecureBiometricUnit::StartActivity(
    (BioIsoProvider::CreateSecureBiometricUnit *)v36,
    v28,
    a2,
    a3,
    a4,
    &Buf2);
  if ( v28 && a2 && a3 && a4 )
  {
    if ( !v28->UnitId )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x28,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
        (const char *)0x80098002LL,
        v27);
      BioIsoProvider::CreateSecureBiometricUnit::~CreateSecureBiometricUnit((BioIsoProvider::CreateSecureBiometricUnit *)v36);
      return 2148106242LL;
    }
    Buf2 = 0;
    if ( !memcmp_0(Buf1, &Buf2, 0x10u) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
        (const char *)0x80070057LL,
        v27);
      BioIsoProvider::CreateSecureBiometricUnit::~CreateSecureBiometricUnit((BioIsoProvider::CreateSecureBiometricUnit *)v36);
      return 2147942487LL;
    }
    std::wstring::wstring(v33, a2);
    PlugIn = PlugInManager::FindPlugIn(v33, 0);
    v11 = PlugIn;
    if ( PlugIn == -2147024894 )
    {
      DllPlugIn = PlugInManager::MakeDllPlugIn((__int64)v33);
      v13 = DllPlugIn;
      if ( DllPlugIn < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x34,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
          (const char *)(unsigned int)DllPlugIn,
          v27);
        std::wstring::_Tidy_deallocate(v33);
        BioIsoProvider::CreateSecureBiometricUnit::~CreateSecureBiometricUnit((BioIsoProvider::CreateSecureBiometricUnit *)v36);
        return v13;
      }
    }
    else if ( PlugIn < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x38,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
        (const char *)(unsigned int)PlugIn,
        v27);
      std::wstring::_Tidy_deallocate(v33);
      BioIsoProvider::CreateSecureBiometricUnit::~CreateSecureBiometricUnit((BioIsoProvider::CreateSecureBiometricUnit *)v36);
      return v11;
    }
    std::wstring::wstring(v34, a3);
    v14 = PlugInManager::FindPlugIn(v34, 0);
    v15 = v14;
    if ( v14 == -2147024894 )
    {
      v16 = PlugInManager::MakeDllPlugIn((__int64)v34);
      v17 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3F,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
          (const char *)(unsigned int)v16,
          v27);
        std::wstring::_Tidy_deallocate(v34);
        std::wstring::_Tidy_deallocate(v33);
        BioIsoProvider::CreateSecureBiometricUnit::~CreateSecureBiometricUnit((BioIsoProvider::CreateSecureBiometricUnit *)v36);
        return v17;
      }
    }
    else if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x43,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
        (const char *)(unsigned int)v14,
        v27);
      std::wstring::_Tidy_deallocate(v34);
      std::wstring::_Tidy_deallocate(v33);
      BioIsoProvider::CreateSecureBiometricUnit::~CreateSecureBiometricUnit((BioIsoProvider::CreateSecureBiometricUnit *)v36);
      return v15;
    }
    std::wstring::wstring(v35, a4);
    v18 = PlugInManager::FindPlugIn(v35, 0);
    v19 = v18;
    if ( v18 == -2147024894 )
    {
      v20 = PlugInManager::MakeDllPlugIn((__int64)v35);
      v21 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4A,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
          (const char *)(unsigned int)v20,
          v27);
        std::wstring::_Tidy_deallocate(v35);
        std::wstring::_Tidy_deallocate(v34);
        std::wstring::_Tidy_deallocate(v33);
        BioIsoProvider::CreateSecureBiometricUnit::~CreateSecureBiometricUnit((BioIsoProvider::CreateSecureBiometricUnit *)v36);
        return v21;
      }
    }
    else if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4E,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
        (const char *)(unsigned int)v18,
        v27);
      std::wstring::_Tidy_deallocate(v35);
      std::wstring::_Tidy_deallocate(v34);
      std::wstring::_Tidy_deallocate(v33);
      BioIsoProvider::CreateSecureBiometricUnit::~CreateSecureBiometricUnit((BioIsoProvider::CreateSecureBiometricUnit *)v36);
      return v19;
    }
    Buf2 = 0;
    BiometricUnit = HardwareManager::MakeBiometricUnit(v28, &Buf2);
    v23 = BiometricUnit;
    if ( BiometricUnit >= 0 )
    {
      v31 = &v28;
      v32 = 1;
      v24 = BiometricUnit::Configure(*(_QWORD *)&Buf2.Data1, v33, v34, v35);
      v25 = v24;
      if ( v24 >= 0 )
      {
        v26 = (WINBIO_UNIT_ID *)operator new(4u);
        *v26 = 0;
        *v26 = v28->UnitId;
        v29 = 0;
        *a6 = v26;
        HardwareManager::AddHandle(v26);
        wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v36, 0);
        std::unique_ptr<_BIO_ISO_UNIT_SESSION_CONTEXT>::~unique_ptr<_BIO_ISO_UNIT_SESSION_CONTEXT>(&v29);
        if ( *(_QWORD *)Buf2.Data4 )
          std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)Buf2.Data4);
        std::wstring::_Tidy_deallocate(v35);
        std::wstring::_Tidy_deallocate(v34);
        std::wstring::_Tidy_deallocate(v33);
        BioIsoProvider::CreateSecureBiometricUnit::~CreateSecureBiometricUnit((BioIsoProvider::CreateSecureBiometricUnit *)v36);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5E,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
          (const char *)(unsigned int)v24,
          (int)Buf1);
        HardwareManager::DeleteBiometricUnit(v28->UnitId);
        if ( *(_QWORD *)Buf2.Data4 )
          std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)Buf2.Data4);
        std::wstring::_Tidy_deallocate(v35);
        std::wstring::_Tidy_deallocate(v34);
        std::wstring::_Tidy_deallocate(v33);
        BioIsoProvider::CreateSecureBiometricUnit::~CreateSecureBiometricUnit((BioIsoProvider::CreateSecureBiometricUnit *)v36);
        return v25;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x54,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
        (const char *)(unsigned int)BiometricUnit,
        v27);
      if ( *(_QWORD *)Buf2.Data4 )
        std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)Buf2.Data4);
      std::wstring::_Tidy_deallocate(v35);
      std::wstring::_Tidy_deallocate(v34);
      std::wstring::_Tidy_deallocate(v33);
      BioIsoProvider::CreateSecureBiometricUnit::~CreateSecureBiometricUnit((BioIsoProvider::CreateSecureBiometricUnit *)v36);
      return v23;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80004003LL,
      v27);
    BioIsoProvider::CreateSecureBiometricUnit::~CreateSecureBiometricUnit((BioIsoProvider::CreateSecureBiometricUnit *)v36);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x140008380  push    rbx
0x140008382  push    rsi
0x140008383  push    rdi
0x140008384  push    r14
0x140008386  push    r15
0x140008388  sub     rsp, 220h
0x14000838f  mov     rax, cs:__security_cookie
0x140008396  xor     rax, rsp
0x140008399  mov     [rsp+248h+var_38], rax
0x1400083a1  mov     rsi, r9
0x1400083a4  mov     rdi, r8
0x1400083a7  mov     rbx, rdx
0x1400083aa  mov     [rsp+248h+var_218], rcx
0x1400083af  mov     r14, [rsp+248h+Buf1]
0x1400083b7  mov     r15, [rsp+248h+arg_28]
0x1400083bf  lea     rdx, aCreatesecurebi; "CreateSecureBiometricUnit"
0x1400083c6  lea     rcx, [rsp+248h+var_188]
0x1400083ce  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1400083d3  lea     rax, ??_7CreateSecureBiometricUnit@BioIsoProvider@@6B@; const BioIsoProvider::CreateSecureBiometricUnit::`vftable'
0x1400083da  mov     [rsp+248h+var_188], rax
0x1400083e2  movups  xmm0, xmmword ptr [r14]
0x1400083e6  movdqu  [rsp+248h+Buf2], xmm0
0x1400083ec  lea     rax, [rsp+248h+Buf2]
0x1400083f1  mov     [rsp+248h+var_220], rax; struct _GUID *
0x1400083f6  mov     [rsp+248h+var_228], rsi; int
0x1400083fb  mov     r9, rdi; unsigned __int16 *
0x1400083fe  mov     r8, rbx; unsigned __int16 *
0x140008401  mov     rdx, [rsp+248h+var_218]; struct _WINBIO_UNIT_SCHEMA *
0x140008406  lea     rcx, [rsp+248h+var_188]; this
0x14000840e  call    ?StartActivity@CreateSecureBiometricUnit@BioIsoProvider@@QEAAXPEBU_WINBIO_UNIT_SCHEMA@@PEBG11U_GUID@@@Z; BioIsoProvider::CreateSecureBiometricUnit::StartActivity(_WINBIO_UNIT_SCHEMA const *,ushort const *,ushort const *,ushort const *,_GUID)
0x140008413  nop
0x140008414  mov     rax, [rsp+248h+var_218]
0x140008419  test    rax, rax
0x14000841c  jz      loc_140008908
0x140008422  test    rbx, rbx
0x140008425  jz      loc_140008908
0x14000842b  test    rdi, rdi
0x14000842e  jz      loc_140008908
0x140008434  test    rsi, rsi
0x140008437  jz      loc_140008908
0x14000843d  cmp     dword ptr [rax], 0
0x140008440  jnz     short loc_140008478
0x140008442  mov     rcx, [rsp+248h]; this
0x14000844a  mov     ebx, 80098002h
0x14000844f  mov     r9d, ebx; char *
0x140008452  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140008459  mov     edx, 28h ; '('; void *
0x14000845e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008463  nop
0x140008464  lea     rcx, [rsp+248h+var_188]; this
0x14000846c  call    ??1CreateSecureBiometricUnit@BioIsoProvider@@QEAA@XZ; BioIsoProvider::CreateSecureBiometricUnit::~CreateSecureBiometricUnit(void)
0x140008471  mov     eax, ebx
0x140008473  jmp     loc_14000893F
0x140008478  xorps   xmm0, xmm0
0x14000847b  movups  [rsp+248h+Buf2], xmm0
0x140008480  mov     r8d, 10h; Size
0x140008486  lea     rdx, [rsp+248h+Buf2]; Buf2
0x14000848b  mov     rcx, r14; Buf1
0x14000848e  call    memcmp_0
0x140008493  test    eax, eax
0x140008495  jnz     short loc_1400084CB
0x140008497  mov     rcx, [rsp+248h]; this
0x14000849f  mov     ebx, 80070057h
0x1400084a4  mov     r9d, ebx; char *
0x1400084a7  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400084ae  lea     edx, [rax+2Ch]; void *
0x1400084b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400084b6  nop
0x1400084b7  lea     rcx, [rsp+248h+var_188]; this
0x1400084bf  call    ??1CreateSecureBiometricUnit@BioIsoProvider@@QEAA@XZ; BioIsoProvider::CreateSecureBiometricUnit::~CreateSecureBiometricUnit(void)
0x1400084c4  mov     eax, ebx
0x1400084c6  jmp     loc_14000893F
0x1400084cb  mov     rdx, rbx
0x1400084ce  lea     rcx, [rsp+248h+var_1E8]
0x1400084d3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1400084d8  nop
0x1400084d9  xor     edx, edx
0x1400084db  lea     rcx, [rsp+248h+var_1E8]
0x1400084e0  call    ?FindPlugIn@PlugInManager@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV?$shared_ptr@VPlugIn@@@3@@Z; PlugInManager::FindPlugIn(std::wstring const &,std::shared_ptr<PlugIn> *)
0x1400084e5  mov     ebx, eax
0x1400084e7  cmp     eax, 80070002h
0x1400084ec  jnz     short loc_14000853A
0x1400084ee  lea     rcx, [rsp+248h+var_1E8]
0x1400084f3  call    ?MakeDllPlugIn@PlugInManager@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PlugInManager::MakeDllPlugIn(std::wstring const &)
0x1400084f8  mov     ebx, eax
0x1400084fa  test    eax, eax
0x1400084fc  jns     short loc_14000857A
0x1400084fe  mov     rcx, [rsp+248h]; this
0x140008506  mov     r9d, eax; char *
0x140008509  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140008510  mov     edx, 34h ; '4'; void *
0x140008515  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000851a  nop
0x14000851b  lea     rcx, [rsp+248h+var_1E8]
0x140008520  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140008525  nop
0x140008526  lea     rcx, [rsp+248h+var_188]; this
0x14000852e  call    ??1CreateSecureBiometricUnit@BioIsoProvider@@QEAA@XZ; BioIsoProvider::CreateSecureBiometricUnit::~CreateSecureBiometricUnit(void)
0x140008533  mov     eax, ebx
0x140008535  jmp     loc_14000893F
0x14000853a  test    ebx, ebx
0x14000853c  jns     short loc_14000857A
0x14000853e  mov     rcx, [rsp+248h]; this
0x140008546  mov     r9d, ebx; char *
0x140008549  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140008550  mov     edx, 38h ; '8'; void *
0x140008555  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000855a  nop
0x14000855b  lea     rcx, [rsp+248h+var_1E8]
0x140008560  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140008565  nop
0x140008566  lea     rcx, [rsp+248h+var_188]; this
0x14000856e  call    ??1CreateSecureBiometricUnit@BioIsoProvider@@QEAA@XZ; BioIsoProvider::CreateSecureBiometricUnit::~CreateSecureBiometricUnit(void)
0x140008573  mov     eax, ebx
0x140008575  jmp     loc_14000893F
0x14000857a  mov     rdx, rdi
0x14000857d  lea     rcx, [rsp+248h+var_1C8]
0x140008585  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14000858a  nop
0x14000858b  xor     edx, edx
0x14000858d  lea     rcx, [rsp+248h+var_1C8]
0x140008595  call    ?FindPlugIn@PlugInManager@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV?$shared_ptr@VPlugIn@@@3@@Z; PlugInManager::FindPlugIn(std::wstring const &,std::shared_ptr<PlugIn> *)
0x14000859a  mov     ebx, eax
0x14000859c  cmp     eax, 80070002h
0x1400085a1  jnz     short loc_140008604
0x1400085a3  lea     rcx, [rsp+248h+var_1C8]
0x1400085ab  call    ?MakeDllPlugIn@PlugInManager@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PlugInManager::MakeDllPlugIn(std::wstring const &)
0x1400085b0  mov     ebx, eax
0x1400085b2  test    eax, eax
0x1400085b4  jns     loc_140008652
0x1400085ba  mov     rcx, [rsp+248h]; this
0x1400085c2  mov     r9d, eax; char *
0x1400085c5  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400085cc  mov     edx, 3Fh ; '?'; void *
0x1400085d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400085d6  nop
0x1400085d7  lea     rcx, [rsp+248h+var_1C8]
0x1400085df  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400085e4  nop
0x1400085e5  lea     rcx, [rsp+248h+var_1E8]
0x1400085ea  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400085ef  nop
0x1400085f0  lea     rcx, [rsp+248h+var_188]; this
0x1400085f8  call    ??1CreateSecureBiometricUnit@BioIsoProvider@@QEAA@XZ; BioIsoProvider::CreateSecureBiometricUnit::~CreateSecureBiometricUnit(void)
0x1400085fd  mov     eax, ebx
0x1400085ff  jmp     loc_14000893F
0x140008604  test    ebx, ebx
0x140008606  jns     short loc_140008652
0x140008608  mov     rcx, [rsp+248h]; this
0x140008610  mov     r9d, ebx; char *
0x140008613  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14000861a  mov     edx, 43h ; 'C'; void *
0x14000861f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008624  nop
0x140008625  lea     rcx, [rsp+248h+var_1C8]
0x14000862d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140008632  nop
0x140008633  lea     rcx, [rsp+248h+var_1E8]
0x140008638  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000863d  nop
0x14000863e  lea     rcx, [rsp+248h+var_188]; this
0x140008646  call    ??1CreateSecureBiometricUnit@BioIsoProvider@@QEAA@XZ; BioIsoProvider::CreateSecureBiometricUnit::~CreateSecureBiometricUnit(void)
0x14000864b  mov     eax, ebx
0x14000864d  jmp     loc_14000893F
0x140008652  mov     rdx, rsi
0x140008655  lea     rcx, [rsp+248h+var_1A8]
0x14000865d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140008662  nop
0x140008663  xor     edx, edx
0x140008665  lea     rcx, [rsp+248h+var_1A8]
0x14000866d  call    ?FindPlugIn@PlugInManager@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV?$shared_ptr@VPlugIn@@@3@@Z; PlugInManager::FindPlugIn(std::wstring const &,std::shared_ptr<PlugIn> *)
0x140008672  mov     ebx, eax
0x140008674  cmp     eax, 80070002h
0x140008679  jnz     short loc_1400086EA
0x14000867b  lea     rcx, [rsp+248h+var_1A8]
0x140008683  call    ?MakeDllPlugIn@PlugInManager@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PlugInManager::MakeDllPlugIn(std::wstring const &)
0x140008688  mov     ebx, eax
0x14000868a  test    eax, eax
0x14000868c  jns     loc_140008746
0x140008692  mov     rcx, [rsp+248h]; this
0x14000869a  mov     r9d, eax; char *
0x14000869d  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400086a4  mov     edx, 4Ah ; 'J'; void *
0x1400086a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400086ae  nop
0x1400086af  lea     rcx, [rsp+248h+var_1A8]
0x1400086b7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400086bc  nop
0x1400086bd  lea     rcx, [rsp+248h+var_1C8]
0x1400086c5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400086ca  nop
0x1400086cb  lea     rcx, [rsp+248h+var_1E8]
0x1400086d0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400086d5  nop
0x1400086d6  lea     rcx, [rsp+248h+var_188]; this
0x1400086de  call    ??1CreateSecureBiometricUnit@BioIsoProvider@@QEAA@XZ; BioIsoProvider::CreateSecureBiometricUnit::~CreateSecureBiometricUnit(void)
0x1400086e3  mov     eax, ebx
0x1400086e5  jmp     loc_14000893F
0x1400086ea  test    ebx, ebx
0x1400086ec  jns     short loc_140008746
0x1400086ee  mov     rcx, [rsp+248h]; this
0x1400086f6  mov     r9d, ebx; char *
0x1400086f9  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140008700  mov     edx, 4Eh ; 'N'; void *
0x140008705  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000870a  nop
0x14000870b  lea     rcx, [rsp+248h+var_1A8]
0x140008713  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140008718  nop
0x140008719  lea     rcx, [rsp+248h+var_1C8]
0x140008721  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140008726  nop
0x140008727  lea     rcx, [rsp+248h+var_1E8]
0x14000872c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140008731  nop
0x140008732  lea     rcx, [rsp+248h+var_188]; this
0x14000873a  call    ??1CreateSecureBiometricUnit@BioIsoProvider@@QEAA@XZ; BioIsoProvider::CreateSecureBiometricUnit::~CreateSecureBiometricUnit(void)
0x14000873f  mov     eax, ebx
0x140008741  jmp     loc_14000893F
0x140008746  xorps   xmm0, xmm0
0x140008749  movdqu  [rsp+248h+Buf2], xmm0
0x14000874f  lea     rdx, [rsp+248h+Buf2]
0x140008754  mov     rcx, [rsp+248h+var_218]
0x140008759  call    ?MakeBiometricUnit@HardwareManager@@SAJQEBU_WINBIO_UNIT_SCHEMA@@PEAV?$shared_ptr@VBiometricUnit@@@std@@@Z; HardwareManager::MakeBiometricUnit(_WINBIO_UNIT_SCHEMA const * const,std::shared_ptr<BiometricUnit> *)
0x14000875e  mov     ebx, eax
0x140008760  test    eax, eax
0x140008762  jns     short loc_1400087CC
0x140008764  mov     rcx, [rsp+248h]; this
0x14000876c  mov     r9d, eax; char *
0x14000876f  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140008776  mov     edx, 54h ; 'T'; void *
0x14000877b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008780  nop
0x140008781  mov     rcx, qword ptr [rsp+248h+Buf2+8]; this
0x140008786  test    rcx, rcx
0x140008789  jz      short loc_140008791
0x14000878b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140008790  nop
0x140008791  lea     rcx, [rsp+248h+var_1A8]
0x140008799  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000879e  nop
0x14000879f  lea     rcx, [rsp+248h+var_1C8]
0x1400087a7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400087ac  nop
0x1400087ad  lea     rcx, [rsp+248h+var_1E8]
0x1400087b2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400087b7  nop
0x1400087b8  lea     rcx, [rsp+248h+var_188]; this
0x1400087c0  call    ??1CreateSecureBiometricUnit@BioIsoProvider@@QEAA@XZ; BioIsoProvider::CreateSecureBiometricUnit::~CreateSecureBiometricUnit(void)
0x1400087c5  mov     eax, ebx
0x1400087c7  jmp     loc_14000893F
0x1400087cc  lea     rax, [rsp+248h+var_218]
0x1400087d1  mov     [rsp+248h+var_1F8], rax
0x1400087d6  mov     [rsp+248h+var_1F0], 1
0x1400087db  mov     [rsp+248h+var_228], r14; int
0x1400087e0  lea     r9, [rsp+248h+var_1A8]
0x1400087e8  lea     r8, [rsp+248h+var_1C8]
0x1400087f0  lea     rdx, [rsp+248h+var_1E8]
0x1400087f5  mov     rcx, qword ptr [rsp+248h+Buf2]
0x1400087fa  call    ?Configure@BiometricUnit@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00AEBU_GUID@@@Z; BiometricUnit::Configure(std::wstring const &,std::wstring const &,std::wstring const &,_GUID const &)
0x1400087ff  mov     ebx, eax
0x140008801  test    eax, eax
0x140008803  jns     short loc_14000887A
0x140008805  mov     rcx, [rsp+248h]; this
0x14000880d  mov     r9d, eax; char *
0x140008810  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140008817  mov     edx, 5Eh ; '^'; void *
0x14000881c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008821  nop
0x140008822  mov     rcx, [rsp+248h+var_218]
0x140008827  mov     ecx, [rcx]; unsigned int
0x140008829  call    ?DeleteBiometricUnit@HardwareManager@@SAJK@Z; HardwareManager::DeleteBiometricUnit(ulong)
0x14000882e  nop
0x14000882f  mov     rcx, qword ptr [rsp+248h+Buf2+8]; this
0x140008834  test    rcx, rcx
0x140008837  jz      short loc_14000883F
0x140008839  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x14000883e  nop
0x14000883f  lea     rcx, [rsp+248h+var_1A8]
0x140008847  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000884c  nop
0x14000884d  lea     rcx, [rsp+248h+var_1C8]
0x140008855  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14000885a  nop
0x14000885b  lea     rcx, [rsp+248h+var_1E8]
0x140008860  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140008865  nop
0x140008866  lea     rcx, [rsp+248h+var_188]; this
0x14000886e  call    ??1CreateSecureBiometricUnit@BioIsoProvider@@QEAA@XZ; BioIsoProvider::CreateSecureBiometricUnit::~CreateSecureBiometricUnit(void)
0x140008873  mov     eax, ebx
0x140008875  jmp     loc_14000893F
0x14000887a  mov     ecx, 4; Size
0x14000887f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140008884  xor     ecx, ecx
0x140008886  mov     [rax], ecx
0x140008888  mov     rcx, [rsp+248h+var_218]
0x14000888d  mov     edx, [rcx]
0x14000888f  mov     [rax], edx
0x140008891  mov     [rsp+248h+var_210], 0
0x14000889a  mov     [r15], rax
  ... truncated ...
```
