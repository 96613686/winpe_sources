# GetAppModelIdentityActivationProperties(void *,ushort const *,ushort const *,ulong,AppModel::RuntimeBehavior *,bool *,bool *,bool *,bool *,bool *)

- ea: `0x18000a938`
- end: `0x18000b09b`
- name: `?GetAppModelIdentityActivationProperties@@YAJPEAXPEBG1KPEAW4RuntimeBehavior@AppModel@@PEA_N3333@Z`
- size: `1891`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, const unsigned __int16 *, __int16, enum AppModel::RuntimeBehavior *, bool *, bool *, bool *, bool *, bool *)`
- caller_count: `4`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002bc04`
- `0x18002c480`
- `0x18002ed98`
- `0x180035dbc`

## callees

- `0x1800046a4`
- `0x180004f60`
- `0x180005220`
- `0x18000720c`
- `0x1800077c0`
- `0x18000a938`
- `0x18000b0a4`
- `0x18000b180`
- `0x18000b210`
- `0x18000b2c0`
- `0x18001177c`
- `0x180018dbc`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000ac92`
- `msvcrt!_wcsicmp` at `0x18000ac92`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18000ab1b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18000abae`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18000b060`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18000ab1b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18000abae`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18000b060`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18000aabc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18000aabc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000ad15`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000add5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000af66`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000ad15`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000add5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000af66`

## string_xrefs

- `0x18000aad9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Manager.hpp`
- `0x18000acd3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18000a973`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000aaf4`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000ab53`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000ab8d`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000ac24`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000ac57`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000acee`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000ad6e`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000ada0`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000ae2e`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000ae60`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000aea7`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000afaa`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

## pseudocode

```c
__int64 __fastcall GetAppModelIdentityActivationProperties(
        void *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int16 a4,
        enum AppModel::RuntimeBehavior *a5,
        bool *a6,
        bool *a7,
        bool *a8,
        bool *a9,
        bool *a10)
{
  __int64 v12; // rdx
  unsigned int v13; // ebx
  int v15; // edx
  bool *v16; // r8
  bool *v17; // rsi
  bool *v18; // r14
  bool *v19; // r10
  bool *v20; // r13
  char v21; // bl
  char v22; // bl
  unsigned int v23; // edi
  __int64 v24; // rcx
  int v25; // eax
  __int64 v26; // rcx
  int v27; // eax
  int v28; // eax
  __int64 v29; // rdx
  __int64 *v30; // rcx
  int v31; // eax
  __int64 *v32; // rcx
  int Activation; // eax
  __int16 v34; // cx
  int v35; // edx
  bool v36; // al
  __int64 *v37; // rcx
  int v38; // ecx
  int v39; // edx
  bool v40; // al
  __int64 v41; // rcx
  unsigned int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
  int v44; // [rsp+20h] [rbp-E0h]
  __int64 v45; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v46; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v47; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v48; // [rsp+48h] [rbp-B8h]
  __int64 v49; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v50[4]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v51; // [rsp+70h] [rbp-90h]
  __int64 v52; // [rsp+78h] [rbp-88h]
  __int128 v53; // [rsp+80h] [rbp-80h]
  __int128 v54; // [rsp+90h] [rbp-70h]
  __int128 v55; // [rsp+A0h] [rbp-60h]
  __int128 v56; // [rsp+B0h] [rbp-50h]
  __int128 v57; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v58; // [rsp+D0h] [rbp-30h]
  __int64 v59; // [rsp+D8h] [rbp-28h]
  __int128 v60; // [rsp+E0h] [rbp-20h]
  __int128 v61; // [rsp+F0h] [rbp-10h]
  __int64 v62; // [rsp+100h] [rbp+0h]
  int v63; // [rsp+108h] [rbp+8h]
  __int128 v64; // [rsp+110h] [rbp+10h] BYREF
  int v65; // [rsp+120h] [rbp+20h]
  __int64 v66; // [rsp+128h] [rbp+28h]
  __int128 v67; // [rsp+130h] [rbp+30h]
  __int128 v68; // [rsp+140h] [rbp+40h]
  __int64 v69; // [rsp+150h] [rbp+50h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]
  bool v71; // [rsp+1A0h] [rbp+A0h] BYREF
  const unsigned __int16 *v72; // [rsp+1A8h] [rbp+A8h]

  v72 = a2;
  if ( !a1 )
  {
    v12 = 5180;
LABEL_3:
    v13 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)0x80070057LL,
      v42);
    return v13;
  }
  v15 = a4 & 0x270;
  if ( (a4 & 0x270) != 0 && (((a4 & 0x270) - 1LL) & a4 & 0x270) != 0 )
  {
    v12 = 5183;
    goto LABEL_3;
  }
  v16 = a6;
  v17 = a7;
  v18 = a8;
  v19 = a9;
  v20 = a10;
  *a6 = 0;
  *v17 = 0;
  *v18 = 0;
  *v19 = 0;
  *v20 = 0;
  if ( (a4 & 0x270) != 0 )
  {
    v21 = 1;
    switch ( v15 )
    {
      case 16:
        *(_DWORD *)a5 = 1;
        break;
      case 32:
        *(_DWORD *)a5 = 0;
        break;
      case 64:
        *(_DWORD *)a5 = 2;
        break;
      case 512:
        *(_DWORD *)a5 = 3;
        break;
      default:
        v12 = 5215;
        goto LABEL_3;
    }
    *v16 = (a4 & 0x80) != 0;
    *v17 = HIBYTE(a4) & 1;
    *v18 = (a4 & 0x800) != 0;
    *v19 = (a4 & 0x1000) != 0;
    if ( (a4 & 0x2000) == 0 || (a4 & 0x80) != 0 )
      v21 = 0;
    *v20 = v21;
    return 0;
  }
  if ( (a4 & 0x1880) != 0 )
  {
    v12 = 5229;
    goto LABEL_3;
  }
  v45 = 0;
  v22 = 1;
  v46 = &v45;
  LOBYTE(v48) = 1;
  v47 = 0;
  v23 = SRCacheManager_Open(0, &v47);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(&v46);
  if ( (v23 & 0x80000000) == 0 )
  {
    v49 = 0;
    v25 = StateRepository::Cache::Entity::User_NoThrow::GetByToken(
            (struct StateRepository::Cache::Manager_NoThrow *)&v45,
            a1,
            &v49);
    v23 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1474,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)v25,
        v42);
LABEL_31:
      v24 = v45;
      v45 = 0;
      goto LABEL_26;
    }
    if ( !v49 )
    {
      v13 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x1477,
              (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
              (const char *)2,
              v42);
      goto LABEL_34;
    }
    *(_OWORD *)v50 = 0;
    v51 = 0;
    v52 = 0;
    v53 = 0;
    v54 = 0;
    v55 = 0;
    v56 = 0;
    v71 = 0;
    v27 = StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(&v45, v49, v72, 4);
    v23 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x147F,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)v27,
        (int)v50);
LABEL_38:
      StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v50);
      goto LABEL_31;
    }
    if ( !v71 )
    {
      v13 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x1482,
              (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
              (const char *)2,
              (unsigned int)v50);
LABEL_41:
      StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v50);
LABEL_34:
      v26 = v45;
      v45 = 0;
      if ( v26 )
        SRCacheManager_Close();
      return v13;
    }
    if ( a3 && _wcsicmp(a3, &String2) )
    {
      v46 = 0;
      LODWORD(v47) = 0;
      v48 = 0;
      v28 = StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplicationAndCategory(
              (StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow *)&v46,
              (struct StateRepository::Cache::Manager_NoThrow *)&v45,
              *(__int64 *)v50,
              a3);
      v23 = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3B9,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
          (const char *)(unsigned int)v28,
          (int)v50);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1489,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)v23,
          v44);
        goto LABEL_46;
      }
      v71 = 0;
      v57 = 0;
      v60 = 0;
      v61 = 0;
      v58 = 0;
      v59 = 0;
      v62 = 0;
      v63 = 0;
      v31 = StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(&v46, v29, &v57, &v71);
      v23 = v31;
      if ( v31 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x148F,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)(unsigned int)v31,
          (int)v50);
LABEL_50:
        StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v57);
LABEL_46:
        v30 = v46;
        v46 = 0;
        if ( v30 )
          SRCacheContext_Close();
        goto LABEL_38;
      }
      if ( !v71 )
      {
        v13 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x1492,
                (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                (const char *)2,
                (unsigned int)v50);
        goto LABEL_53;
      }
      v65 = 0;
      v64 = 0;
      v67 = 0;
      v68 = 0;
      v66 = 0;
      v69 = 0;
      v71 = 0;
      Activation = StateRepository::Cache::Entity::ApplicationExtension_NoThrow::GetActivation(
                     (StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v57,
                     (struct StateRepository::Cache::Manager_NoThrow *)&v45,
                     (struct StateRepository::Cache::Entity::Activation_NoThrow *)&v64,
                     &v71);
      v23 = Activation;
      if ( Activation < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1497,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)(unsigned int)Activation,
          (int)v50);
        StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow((StateRepository::Cache::Entity::Activation_NoThrow *)&v64);
        goto LABEL_50;
      }
      if ( !v71 )
      {
        v13 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x149A,
                (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                (const char *)2,
                (unsigned int)v50);
LABEL_59:
        StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow((StateRepository::Cache::Entity::Activation_NoThrow *)&v64);
LABEL_53:
        StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v57);
        v32 = v46;
        v46 = 0;
        if ( v32 )
          SRCacheContext_Close();
        goto LABEL_41;
      }
      v34 = v65;
      if ( (v65 & 0x100) != 0 )
      {
        v35 = 0;
        *(_DWORD *)a5 = 0;
      }
      else if ( (v65 & 0x10) != 0 )
      {
        v35 = 1;
        *(_DWORD *)a5 = 1;
      }
      else
      {
        if ( (v65 & 0x20) != 0 )
        {
          v35 = 2;
        }
        else
        {
          if ( (v65 & 0x200) == 0 )
          {
            v13 = -2147024809;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x14AF,
              (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
              (const char *)0x80070057LL,
              (int)v50);
            goto LABEL_59;
          }
          v35 = 3;
        }
        *(_DWORD *)a5 = v35;
      }
      *a6 = (v34 & 0x80) != 0;
      if ( v35 || (v34 & 0x40) == 0 )
      {
        *v17 = 0;
        if ( v35 == 1 && (v34 & 0x400) == 0 && (v34 & 0x800) != 0 )
        {
          *v18 = 1;
          goto LABEL_74;
        }
      }
      else
      {
        *v17 = 1;
      }
      *v18 = 0;
      if ( v35 )
      {
LABEL_75:
        v36 = 0;
LABEL_76:
        *a9 = v36;
        if ( (v34 & 0x1000) == 0 || (v34 & 0x80) != 0 )
          v22 = 0;
        *v20 = v22;
        StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow((StateRepository::Cache::Entity::Activation_NoThrow *)&v64);
        StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v57);
        v37 = v46;
        v46 = 0;
        if ( v37 )
          SRCacheContext_Close();
LABEL_105:
        StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v50);
        v41 = v45;
        v45 = 0;
        if ( v41 )
          SRCacheManager_Close();
        return 0;
      }
LABEL_74:
      v36 = 1;
      if ( (v34 & 8) != 0 )
        goto LABEL_76;
      goto LABEL_75;
    }
    v38 = HIDWORD(v51);
    if ( (v51 & 0x10000000000LL) != 0 )
    {
      v39 = 0;
      *(_DWORD *)a5 = 0;
    }
    else if ( (v51 & 0x1000000000LL) != 0 )
    {
      v39 = 1;
      *(_DWORD *)a5 = 1;
    }
    else
    {
      if ( (v51 & 0x2000000000LL) != 0 )
      {
        v39 = 2;
      }
      else
      {
        if ( (v51 & 0x20000000000LL) == 0 )
        {
          v13 = -2147024809;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x14D5,
            (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
            (const char *)0x80070057LL,
            (int)v50);
          goto LABEL_41;
        }
        v39 = 3;
      }
      *(_DWORD *)a5 = v39;
    }
    *a6 = (v38 & 0x80) != 0;
    if ( v39 || (v38 & 0x10000) == 0 )
    {
      *v17 = 0;
      if ( v39 == 1 && (v38 & 0x400) == 0 && (v38 & 0x800) != 0 )
      {
        *v18 = 1;
        goto LABEL_99;
      }
    }
    else
    {
      *v17 = 1;
    }
    *v18 = 0;
    if ( v39 )
    {
LABEL_100:
      v40 = 0;
LABEL_101:
      *a9 = v40;
      if ( (v38 & 0x40) == 0 || (v38 & 0x80) != 0 )
        v22 = 0;
      *v20 = v22;
      goto LABEL_105;
    }
LABEL_99:
    v40 = 1;
    if ( (v38 & 8) != 0 )
      goto LABEL_101;
    goto LABEL_100;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA5,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Manager.hpp",
    (const char *)v23,
    v42);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1471,
    (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
    (const char *)v23,
    v43);
  v24 = v45;
  v45 = 0;
LABEL_26:
  if ( v24 )
    SRCacheManager_Close();
  return v23;
}

```

## disassembly

```asm
0x18000a938  mov     [rsp-8+arg_10], rbx
0x18000a93d  mov     [rsp-8+arg_8], rdx
0x18000a942  push    rbp
0x18000a943  push    rsi
0x18000a944  push    rdi
0x18000a945  push    r12
0x18000a947  push    r13
0x18000a949  push    r14
0x18000a94b  push    r15
0x18000a94d  lea     rbp, [rsp-60h]
0x18000a952  sub     rsp, 160h
0x18000a959  xor     r11d, r11d
0x18000a95c  mov     r15, r8
0x18000a95f  mov     r12, rcx
0x18000a962  test    rcx, rcx
0x18000a965  jnz     short loc_18000A98E
0x18000a967  mov     edx, 143Ch; void *
0x18000a96c  mov     rcx, [rbp+98h]; this
0x18000a973  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18000a97a  mov     ebx, 80070057h
0x18000a97f  mov     r9d, ebx; char *
0x18000a982  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a987  mov     eax, ebx
0x18000a989  jmp     loc_18000B068
0x18000a98e  mov     edx, r9d
0x18000a991  and     edx, 270h
0x18000a997  jz      short loc_18000A9AB
0x18000a999  mov     ecx, edx
0x18000a99b  lea     rax, [rdx-1]
0x18000a99f  test    rcx, rax
0x18000a9a2  jz      short loc_18000A9AB
0x18000a9a4  mov     edx, 143Fh
0x18000a9a9  jmp     short loc_18000A96C
0x18000a9ab  mov     r8, [rbp+90h+arg_28]
0x18000a9b2  mov     rsi, [rbp+90h+arg_30]
0x18000a9b9  mov     r14, [rbp+90h+arg_38]
0x18000a9c0  mov     r10, [rbp+90h+arg_40]
0x18000a9c7  mov     r13, [rbp+90h+arg_48]
0x18000a9ce  mov     [r8], r11b
0x18000a9d1  mov     [rsi], r11b
0x18000a9d4  mov     [r14], r11b
0x18000a9d7  mov     [r10], r11b
0x18000a9da  mov     [r13+0], r11b
0x18000a9de  test    edx, edx
0x18000a9e0  jz      loc_18000AA85
0x18000a9e6  mov     ebx, 1
0x18000a9eb  cmp     edx, 10h
0x18000a9ee  jz      short loc_18000AA36
0x18000a9f0  cmp     edx, 20h ; ' '
0x18000a9f3  jz      short loc_18000AA2A
0x18000a9f5  cmp     edx, 40h ; '@'
0x18000a9f8  jz      short loc_18000AA1B
0x18000a9fa  cmp     edx, 200h
0x18000aa00  jz      short loc_18000AA0C
0x18000aa02  mov     edx, 145Fh
0x18000aa07  jmp     loc_18000A96C
0x18000aa0c  mov     rax, [rbp+90h+arg_20]
0x18000aa13  mov     dword ptr [rax], 3
0x18000aa19  jmp     short loc_18000AA3F
0x18000aa1b  mov     rax, [rbp+90h+arg_20]
0x18000aa22  mov     dword ptr [rax], 2
0x18000aa28  jmp     short loc_18000AA3F
0x18000aa2a  mov     rax, [rbp+90h+arg_20]
0x18000aa31  mov     [rax], r11d
0x18000aa34  jmp     short loc_18000AA3F
0x18000aa36  mov     rax, [rbp+90h+arg_20]
0x18000aa3d  mov     [rax], ebx
0x18000aa3f  mov     ecx, r9d
0x18000aa42  and     ecx, 80h
0x18000aa48  setnz   al
0x18000aa4b  mov     [r8], al
0x18000aa4e  mov     eax, r9d
0x18000aa51  shr     eax, 8
0x18000aa54  and     al, bl
0x18000aa56  mov     [rsi], al
0x18000aa58  mov     eax, r9d
0x18000aa5b  shr     eax, 0Bh
0x18000aa5e  and     al, bl
0x18000aa60  mov     [r14], al
0x18000aa63  mov     eax, r9d
0x18000aa66  shr     eax, 0Ch
0x18000aa69  and     al, bl
0x18000aa6b  mov     [r10], al
0x18000aa6e  bt      r9d, 0Dh
0x18000aa73  jnb     short loc_18000AA79
0x18000aa75  test    ecx, ecx
0x18000aa77  jz      short loc_18000AA7C
0x18000aa79  mov     bl, r11b
0x18000aa7c  mov     [r13+0], bl
0x18000aa80  jmp     loc_18000B066
0x18000aa85  test    r9d, 1880h
0x18000aa8c  jz      short loc_18000AA98
0x18000aa8e  mov     edx, 146Dh
0x18000aa93  jmp     loc_18000A96C
0x18000aa98  lea     rax, [rsp+190h+var_160]
0x18000aa9d  mov     [rsp+190h+var_160], r11
0x18000aaa2  mov     ebx, 1
0x18000aaa7  mov     [rsp+190h+var_158], rax
0x18000aaac  lea     rdx, [rsp+190h+var_150]
0x18000aab1  mov     byte ptr [rsp+190h+var_148], bl
0x18000aab5  xor     ecx, ecx
0x18000aab7  mov     [rsp+190h+var_150], r11
0x18000aabc  call    cs:__imp_SRCacheManager_Open
0x18000aac2  lea     rcx, [rsp+190h+var_158]
0x18000aac7  mov     edi, eax
0x18000aac9  call    ??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)
0x18000aace  test    edi, edi
0x18000aad0  jns     short loc_18000AB28
0x18000aad2  mov     rcx, [rbp+98h]; this
0x18000aad9  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000aae0  mov     r9d, edi; char *
0x18000aae3  mov     edx, 0A5h; void *
0x18000aae8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aaed  mov     rcx, [rbp+98h]; this
0x18000aaf4  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18000aafb  mov     r9d, edi; char *
0x18000aafe  mov     edx, 1471h; void *
0x18000ab03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ab08  mov     rcx, [rsp+190h+var_160]
0x18000ab0d  mov     [rsp+190h+var_160], 0
0x18000ab16  test    rcx, rcx
0x18000ab19  jz      short loc_18000AB21
0x18000ab1b  call    cs:__imp_SRCacheManager_Close
0x18000ab21  mov     eax, edi
0x18000ab23  jmp     loc_18000B068
0x18000ab28  lea     r8, [rsp+190h+var_140]; __int64 *
0x18000ab2d  mov     [rsp+190h+var_140], 0
0x18000ab36  mov     rdx, r12; void *
0x18000ab39  lea     rcx, [rsp+190h+var_160]; struct StateRepository::Cache::Manager_NoThrow *
0x18000ab3e  call    ?GetByToken@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByToken(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x18000ab43  xor     r12d, r12d
0x18000ab46  mov     edi, eax
0x18000ab48  test    eax, eax
0x18000ab4a  jns     short loc_18000AB73
0x18000ab4c  mov     rcx, [rbp+98h]; this
0x18000ab53  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18000ab5a  mov     r9d, eax; char *
0x18000ab5d  mov     edx, 1474h; void *
0x18000ab62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ab67  mov     rcx, [rsp+190h+var_160]
0x18000ab6c  mov     [rsp+190h+var_160], r12
0x18000ab71  jmp     short loc_18000AB16
0x18000ab73  mov     rdx, [rsp+190h+var_140]
0x18000ab78  test    rdx, rdx
0x18000ab7b  jnz     short loc_18000ABB9
0x18000ab7d  mov     rcx, [rbp+98h]; this
0x18000ab84  lea     r9d, [rdx+2]; char *
0x18000ab88  mov     edx, 1477h; void *
0x18000ab8d  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18000ab94  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000ab99  mov     ebx, eax
0x18000ab9b  mov     rcx, [rsp+190h+var_160]
0x18000aba0  mov     [rsp+190h+var_160], r12
0x18000aba5  test    rcx, rcx
0x18000aba8  jz      loc_18000A987
0x18000abae  call    cs:__imp_SRCacheManager_Close
0x18000abb4  jmp     loc_18000A987
0x18000abb9  mov     r8, [rbp+90h+arg_8]
0x18000abc0  lea     rax, [rbp+90h+arg_0]
0x18000abc7  xorps   xmm0, xmm0
0x18000abca  mov     [rsp+190h+var_168], rax
0x18000abcf  xorps   xmm1, xmm1
0x18000abd2  movdqa  xmmword ptr [rsp+190h+var_130], xmm0
0x18000abd8  lea     rax, [rsp+190h+var_130]
0x18000abdd  mov     [rsp+190h+var_120], r12
0x18000abe2  mov     r9d, 4
0x18000abe8  mov     qword ptr [rsp+190h+var_170], rax; int
0x18000abed  lea     rcx, [rsp+190h+var_160]
0x18000abf2  mov     [rsp+190h+var_118], r12
0x18000abf7  movdqa  [rbp+90h+var_110], xmm0
0x18000abfc  movdqa  [rbp+90h+var_100], xmm1
0x18000ac01  movdqa  [rbp+90h+var_F0], xmm0
0x18000ac06  movdqa  [rbp+90h+var_E0], xmm1
0x18000ac0b  mov     [rbp+90h+arg_0], r12b
0x18000ac12  call    ?GetByUserAndApplicationUserModelId@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x18000ac17  mov     edi, eax
0x18000ac19  test    eax, eax
0x18000ac1b  jns     short loc_18000AC47
0x18000ac1d  mov     rcx, [rbp+98h]; this
0x18000ac24  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18000ac2b  mov     r9d, eax; char *
0x18000ac2e  mov     edx, 147Fh; void *
0x18000ac33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ac38  lea     rcx, [rsp+190h+var_130]; this
0x18000ac3d  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18000ac42  jmp     loc_18000AB67
0x18000ac47  cmp     [rbp+90h+arg_0], r12b
0x18000ac4e  jnz     short loc_18000AC7F
0x18000ac50  mov     rcx, [rbp+98h]; this
0x18000ac57  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18000ac5e  mov     r9d, 2; char *
0x18000ac64  mov     edx, 1482h; void *
0x18000ac69  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000ac6e  mov     ebx, eax
0x18000ac70  lea     rcx, [rsp+190h+var_130]; this
0x18000ac75  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18000ac7a  jmp     loc_18000AB9B
0x18000ac7f  test    r15, r15
0x18000ac82  jz      loc_18000AF89
0x18000ac88  lea     rdx, String2; String2
0x18000ac8f  mov     rcx, r15; String1
0x18000ac92  call    cs:__imp__wcsicmp
0x18000ac98  test    eax, eax
0x18000ac9a  jz      loc_18000AF89
0x18000aca0  mov     r8, qword ptr [rsp+190h+var_130]; __int64
0x18000aca5  lea     rdx, [rsp+190h+var_160]; struct StateRepository::Cache::Manager_NoThrow *
0x18000acaa  mov     r9, r15; unsigned __int16 *
0x18000acad  mov     [rsp+190h+var_158], r12
0x18000acb2  lea     rcx, [rsp+190h+var_158]; this
0x18000acb7  mov     dword ptr [rsp+190h+var_150], r12d
0x18000acbc  mov     [rsp+190h+var_148], r12
0x18000acc1  call    ?OpenByApplicationAndCategory@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_JPEBG@Z; StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplicationAndCategory(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *)
0x18000acc6  mov     edi, eax
0x18000acc8  test    eax, eax
0x18000acca  jns     short loc_18000AD20
0x18000accc  mov     rcx, [rbp+98h]; this
0x18000acd3  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000acda  mov     r9d, eax; char *
0x18000acdd  mov     edx, 3B9h; void *
0x18000ace2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ace7  mov     rcx, [rbp+98h]; this
0x18000acee  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18000acf5  mov     r9d, edi; char *
0x18000acf8  mov     edx, 1489h; void *
0x18000acfd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ad02  mov     rcx, [rsp+190h+var_158]
0x18000ad07  mov     [rsp+190h+var_158], r12
0x18000ad0c  test    rcx, rcx
0x18000ad0f  jz      loc_18000AC38
0x18000ad15  call    cs:__imp_SRCacheContext_Close
0x18000ad1b  jmp     loc_18000AC38
0x18000ad20  xorps   xmm0, xmm0
0x18000ad23  mov     [rbp+90h+arg_0], r12b
0x18000ad2a  xorps   xmm1, xmm1
0x18000ad2d  movdqa  [rbp+90h+var_D0], xmm0
0x18000ad32  lea     r9, [rbp+90h+arg_0]
0x18000ad39  movdqa  [rbp+90h+var_B0], xmm0
0x18000ad3e  lea     r8, [rbp+90h+var_D0]
0x18000ad42  movdqa  [rbp+90h+var_A0], xmm1
0x18000ad47  lea     rcx, [rsp+190h+var_158]
0x18000ad4c  mov     [rbp+90h+var_C0], r12
0x18000ad50  mov     [rbp+90h+var_B8], r12
0x18000ad54  mov     [rbp+90h+var_90], r12
0x18000ad58  mov     [rbp+90h+var_88], r12d
0x18000ad5c  call    ?Get@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@ApplicationExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)
0x18000ad61  mov     edi, eax
0x18000ad63  test    eax, eax
0x18000ad65  jns     short loc_18000AD90
0x18000ad67  mov     rcx, [rbp+98h]; this
0x18000ad6e  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18000ad75  mov     r9d, eax; char *
0x18000ad78  mov     edx, 148Fh; void *
0x18000ad7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ad82  lea     rcx, [rbp+90h+var_D0]; this
0x18000ad86  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x18000ad8b  jmp     loc_18000AD02
0x18000ad90  cmp     [rbp+90h+arg_0], r12b
0x18000ad97  jnz     short loc_18000ADE0
0x18000ad99  mov     rcx, [rbp+98h]; this
0x18000ada0  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18000ada7  mov     r9d, 2; char *
0x18000adad  mov     edx, 1492h; void *
0x18000adb2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000adb7  mov     ebx, eax
0x18000adb9  lea     rcx, [rbp+90h+var_D0]; this
0x18000adbd  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x18000adc2  mov     rcx, [rsp+190h+var_158]
0x18000adc7  mov     [rsp+190h+var_158], r12
0x18000adcc  test    rcx, rcx
0x18000adcf  jz      loc_18000AC70
0x18000add5  call    cs:__imp_SRCacheContext_Close
0x18000addb  jmp     loc_18000AC70
0x18000ade0  xorps   xmm0, xmm0
0x18000ade3  mov     [rbp+90h+var_70], r12d
0x18000ade7  xorps   xmm1, xmm1
0x18000adea  movdqa  [rbp+90h+var_80], xmm0
0x18000adef  lea     r9, [rbp+90h+arg_0]; bool *
0x18000adf6  movdqa  [rbp+90h+var_60], xmm0
0x18000adfb  lea     r8, [rbp+90h+var_80]; struct StateRepository::Cache::Entity::Activation_NoThrow *
0x18000adff  movdqa  [rbp+90h+var_50], xmm1
0x18000ae04  lea     rdx, [rsp+190h+var_160]; struct StateRepository::Cache::Manager_NoThrow *
0x18000ae09  mov     [rbp+90h+var_68], r12
0x18000ae0d  lea     rcx, [rbp+90h+var_D0]; this
0x18000ae11  mov     [rbp+90h+var_40], r12
0x18000ae15  mov     [rbp+90h+arg_0], r12b
0x18000ae1c  call    ?GetActivation@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEBAJAEAVManager_NoThrow@34@AEAVActivation_NoThrow@234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::GetActivation(StateRepository::Cache::Manager_NoThrow &,StateRepository::Cache::Entity::Activation_NoThrow &,bool &)
0x18000ae21  mov     edi, eax
0x18000ae23  test    eax, eax
0x18000ae25  jns     short loc_18000AE50
0x18000ae27  mov     rcx, [rbp+98h]; this
0x18000ae2e  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18000ae35  mov     r9d, eax; char *
0x18000ae38  mov     edx, 1497h; void *
0x18000ae3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ae42  lea     rcx, [rbp+90h+var_80]; this
0x18000ae46  call    ??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)
0x18000ae4b  jmp     loc_18000AD82
0x18000ae50  cmp     [rbp+90h+arg_0], r12b
0x18000ae57  jnz     short loc_18000AE87
0x18000ae59  mov     rcx, [rbp+98h]; this
  ... truncated ...
```
