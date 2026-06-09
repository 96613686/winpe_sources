# GetAppModelIdentityActivationProperties(void *,ushort const *,ushort const *,ulong,AppModel::RuntimeBehavior *,bool *,bool *,bool *,bool *,bool *)

- ea: `0x180012b9c`
- end: `0x180013285`
- name: `?GetAppModelIdentityActivationProperties@@YAJPEAXPEBG1KPEAW4RuntimeBehavior@AppModel@@PEA_N3333@Z`
- size: `1769`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, enum AppModel::RuntimeBehavior *, bool *, bool *, bool *, bool *, bool *)`
- caller_count: `4`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180028aa4`
- `0x180029ce4`
- `0x18002b828`
- `0x1800327a0`

## callees

- `0x180004eb0`
- `0x180005880`
- `0x180007b30`
- `0x180007c78`
- `0x180007ca0`
- `0x180009470`
- `0x18000cd00`
- `0x18000dd68`
- `0x18000e430`
- `0x180012b9c`
- `0x180018280`
- `0x18001855c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180012e91`
- `msvcrt!_wcsicmp` at `0x180012e91`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180012d46`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180013230`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180012d46`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180013230`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180012f1a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180013137`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180012f1a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180013137`

## string_xrefs

- `0x180012ed8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180012beb`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180012d1e`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180012d7f`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180012db9`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180012e35`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180012e63`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180012ef3`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180012f79`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180012fab`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180013019`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180013046`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

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
  bool *v10; // rdi
  bool *v11; // r14
  __int64 v15; // rdx
  unsigned int Activation; // ebx
  int v18; // edx
  bool *v19; // r8
  bool *v20; // r10
  bool *v21; // r12
  char v22; // cl
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // rdx
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rcx
  int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int16 v36; // r8
  char v37; // cl
  int v38; // edx
  bool v39; // al
  bool *v40; // rdx
  bool *v41; // rdx
  __int64 v42; // rcx
  int v43; // r8d
  char v44; // cl
  int v45; // edx
  bool v46; // al
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // rcx
  unsigned int v50; // [rsp+20h] [rbp-E0h]
  int v51; // [rsp+20h] [rbp-E0h]
  __int64 v52; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v53; // [rsp+38h] [rbp-C8h] BYREF
  int v54; // [rsp+40h] [rbp-C0h]
  __int64 v55; // [rsp+48h] [rbp-B8h]
  __int64 v56; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v57[4]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v58; // [rsp+70h] [rbp-90h]
  __int64 v59; // [rsp+78h] [rbp-88h]
  __int128 v60; // [rsp+80h] [rbp-80h]
  __int128 v61; // [rsp+90h] [rbp-70h]
  __int128 v62; // [rsp+A0h] [rbp-60h]
  __int128 v63; // [rsp+B0h] [rbp-50h]
  __int128 v64; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v65; // [rsp+D0h] [rbp-30h]
  __int64 v66; // [rsp+D8h] [rbp-28h]
  __int128 v67; // [rsp+E0h] [rbp-20h]
  __int128 v68; // [rsp+F0h] [rbp-10h]
  __int64 v69; // [rsp+100h] [rbp+0h]
  int v70; // [rsp+108h] [rbp+8h]
  __int128 v71; // [rsp+110h] [rbp+10h] BYREF
  int v72; // [rsp+120h] [rbp+20h]
  __int64 v73; // [rsp+128h] [rbp+28h]
  __int128 v74; // [rsp+130h] [rbp+30h]
  __int128 v75; // [rsp+140h] [rbp+40h]
  __int64 v76; // [rsp+150h] [rbp+50h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]
  bool v78; // [rsp+190h] [rbp+90h] BYREF

  v10 = a7;
  v11 = a8;
  if ( !a1 )
  {
    v15 = 4363;
LABEL_3:
    Activation = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)0x80070057LL,
      v50);
    return Activation;
  }
  v18 = a4 & 0x270;
  if ( (a4 & 0x270) != 0 && (((a4 & 0x270) - 1LL) & a4 & 0x270) != 0 )
  {
    v15 = 4366;
    goto LABEL_3;
  }
  v19 = a6;
  v20 = a9;
  v21 = a10;
  *a7 = 0;
  *v19 = 0;
  *v20 = 0;
  *v21 = 0;
  *v11 = 0;
  if ( (a4 & 0x270) == 0 )
  {
    if ( (a4 & 0x1880) != 0 )
    {
      v15 = 4412;
      goto LABEL_3;
    }
    v52 = 0;
    v23 = StateRepository::Cache::Manager_NoThrow::Open(&v52);
    Activation = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1140,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)v23,
        v50);
      v26 = v52;
      v52 = 0;
      goto LABEL_26;
    }
    v56 = 0;
    v27 = StateRepository::Cache::Entity::User_NoThrow::GetByToken(
            (struct StateRepository::Cache::Manager_NoThrow *)&v52,
            a1,
            &v56);
    Activation = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1143,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)v27,
        v50);
LABEL_30:
      v26 = v52;
      v52 = 0;
LABEL_26:
      if ( v26 )
        SRCacheManager_Close(v26, v24, v25);
      return Activation;
    }
    if ( !v56 )
    {
      Activation = wil::details::in1diag3::Return_Win32(
                     retaddr,
                     (void *)0x1146,
                     (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                     (const char *)2,
                     v50);
      goto LABEL_30;
    }
    v58 = 0;
    *(_OWORD *)v57 = 0;
    v59 = 0;
    v60 = 0;
    v61 = 0;
    v62 = 0;
    v63 = 0;
    v78 = 0;
    Activation = StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(
                   &v52,
                   v56,
                   a2,
                   4);
    if ( (Activation & 0x80000000) != 0 )
    {
      v28 = 4430;
LABEL_35:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)Activation,
        (int)v57);
LABEL_36:
      StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(
        (StateRepository::Cache::Entity::Application_NoThrow *)v57,
        v29);
      goto LABEL_30;
    }
    if ( !v78 )
    {
      Activation = wil::details::in1diag3::Return_Win32(
                     retaddr,
                     (void *)0x1151,
                     (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                     (const char *)2,
                     (unsigned int)v57);
      goto LABEL_36;
    }
    if ( a3 && _wcsicmp(a3, &String2) )
    {
      v53 = 0;
      v54 = 0;
      v55 = 0;
      v30 = StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplicationAndCategory(
              (StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow *)&v53,
              (struct StateRepository::Cache::Manager_NoThrow *)&v52,
              *(unsigned __int64 *)v57,
              a3);
      Activation = v30;
      if ( v30 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3B9,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
          (const char *)(unsigned int)v30,
          (int)v57);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1158,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)Activation,
          v51);
        goto LABEL_43;
      }
      v78 = 0;
      v64 = 0;
      v67 = 0;
      v68 = 0;
      v65 = 0;
      v66 = 0;
      v69 = 0;
      v70 = 0;
      v33 = StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(&v53, v31, &v64, &v78);
      Activation = v33;
      if ( v33 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x115E,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)(unsigned int)v33,
          (int)v57);
LABEL_47:
        StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v64);
LABEL_43:
        v32 = v53;
        v53 = 0;
        if ( v32 )
          SRCacheContext_Close(v32);
        goto LABEL_36;
      }
      if ( !v78 )
      {
        Activation = wil::details::in1diag3::Return_Win32(
                       retaddr,
                       (void *)0x1161,
                       (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                       (const char *)2,
                       (unsigned int)v57);
        goto LABEL_47;
      }
      v72 = 0;
      v71 = 0;
      v74 = 0;
      v75 = 0;
      v73 = 0;
      v76 = 0;
      v78 = 0;
      Activation = StateRepository::Cache::Entity::ApplicationExtension_NoThrow::GetActivation(
                     (StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v64,
                     (struct StateRepository::Cache::Manager_NoThrow *)&v52,
                     (struct StateRepository::Cache::Entity::Activation_NoThrow *)&v71,
                     &v78);
      if ( (Activation & 0x80000000) != 0 )
      {
        v34 = 4454;
LABEL_52:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v34,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
          (const char *)Activation,
          (int)v57);
LABEL_53:
        StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(
          (StateRepository::Cache::Entity::Activation_NoThrow *)&v71,
          v35);
        goto LABEL_47;
      }
      if ( !v78 )
      {
        Activation = wil::details::in1diag3::Return_Win32(
                       retaddr,
                       (void *)0x1169,
                       (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                       (const char *)2,
                       (unsigned int)v57);
        goto LABEL_53;
      }
      v36 = v72;
      v37 = 1;
      if ( (v72 & 0x100) != 0 )
      {
        v38 = 0;
        *(_DWORD *)a5 = 0;
      }
      else if ( (v72 & 0x10) != 0 )
      {
        v38 = 1;
        *(_DWORD *)a5 = 1;
      }
      else
      {
        if ( (v72 & 0x20) != 0 )
        {
          v38 = 2;
        }
        else
        {
          if ( (v72 & 0x200) == 0 )
          {
            Activation = -2147024809;
            v34 = 4478;
            goto LABEL_52;
          }
          v38 = 3;
        }
        *(_DWORD *)a5 = v38;
      }
      *a6 = (v36 & 0x80) != 0;
      if ( v38 || (v36 & 0x40) == 0 )
      {
        *v10 = 0;
        if ( v38 == 1 && (v36 & 0x400) == 0 && (v36 & 0x800) != 0 )
        {
          *v11 = 1;
          goto LABEL_70;
        }
      }
      else
      {
        *v10 = 1;
      }
      *v11 = 0;
      if ( v38 )
      {
LABEL_71:
        v39 = 0;
LABEL_72:
        v40 = a9;
        *a9 = v39;
        if ( (v36 & 0x1000) == 0 || (v36 & 0x80) != 0 )
          v37 = 0;
        *v21 = v37;
        StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(
          (StateRepository::Cache::Entity::Activation_NoThrow *)&v71,
          (__int64)v40);
        StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v64);
        v42 = v53;
        v53 = 0;
        if ( v42 )
          SRCacheContext_Close(v42);
LABEL_101:
        StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(
          (StateRepository::Cache::Entity::Application_NoThrow *)v57,
          (__int64)v41);
        v49 = v52;
        v52 = 0;
        if ( v49 )
          SRCacheManager_Close(v49, v47, v48);
        return 0;
      }
LABEL_70:
      v39 = 1;
      if ( (v36 & 8) != 0 )
        goto LABEL_72;
      goto LABEL_71;
    }
    v43 = HIDWORD(v58);
    v44 = 1;
    if ( (v58 & 0x10000000000LL) != 0 )
    {
      v45 = 0;
      *(_DWORD *)a5 = 0;
    }
    else if ( (v58 & 0x1000000000LL) != 0 )
    {
      v45 = 1;
      *(_DWORD *)a5 = 1;
    }
    else
    {
      if ( (v58 & 0x2000000000LL) != 0 )
      {
        v45 = 2;
      }
      else
      {
        if ( (v58 & 0x20000000000LL) == 0 )
        {
          Activation = -2147024809;
          v28 = 4516;
          goto LABEL_35;
        }
        v45 = 3;
      }
      *(_DWORD *)a5 = v45;
    }
    *a6 = (v43 & 0x80) != 0;
    if ( v45 || (v43 & 0x10000) == 0 )
    {
      *v10 = 0;
      if ( v45 == 1 && (v43 & 0x400) == 0 && (v43 & 0x800) != 0 )
      {
        *v11 = 1;
        goto LABEL_95;
      }
    }
    else
    {
      *v10 = 1;
    }
    *v11 = 0;
    if ( v45 )
    {
LABEL_96:
      v46 = 0;
LABEL_97:
      v41 = a9;
      *a9 = v46;
      if ( (v43 & 0x40) == 0 || (v43 & 0x80) != 0 )
        v44 = 0;
      *v21 = v44;
      goto LABEL_101;
    }
LABEL_95:
    v46 = 1;
    if ( (v43 & 8) != 0 )
      goto LABEL_97;
    goto LABEL_96;
  }
  v22 = 1;
  switch ( v18 )
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
      v15 = 4398;
      goto LABEL_3;
  }
  *v19 = (a4 & 0x80) != 0;
  *v10 = HIBYTE(a4) & 1;
  *v11 = (a4 & 0x800) != 0;
  *v20 = (a4 & 0x1000) != 0;
  if ( (a4 & 0x2000) == 0 || (a4 & 0x80) != 0 )
    v22 = 0;
  *v21 = v22;
  return 0;
}

```

## disassembly

```asm
0x180012b9c  mov     [rsp-8+arg_8], rbx
0x180012ba1  mov     [rsp-8+arg_10], rsi
0x180012ba6  mov     [rsp-8+arg_18], rdi
0x180012bab  push    rbp
0x180012bac  push    r12
0x180012bae  push    r13
0x180012bb0  push    r14
0x180012bb2  push    r15
0x180012bb4  lea     rbp, [rsp-60h]
0x180012bb9  sub     rsp, 160h
0x180012bc0  mov     rdi, [rbp+80h+arg_30]
0x180012bc7  xor     r11d, r11d
0x180012bca  mov     r14, [rbp+80h+arg_38]
0x180012bd1  mov     rsi, r8
0x180012bd4  mov     r13, rdx
0x180012bd7  mov     r15, rcx
0x180012bda  test    rcx, rcx
0x180012bdd  jnz     short loc_180012C06
0x180012bdf  mov     edx, 110Bh; void *
0x180012be4  mov     rcx, [rbp+88h]; this
0x180012beb  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180012bf2  mov     ebx, 80070057h
0x180012bf7  mov     r9d, ebx; char *
0x180012bfa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012bff  mov     eax, ebx
0x180012c01  jmp     loc_18001323E
0x180012c06  mov     edx, r9d
0x180012c09  and     edx, 270h
0x180012c0f  jz      short loc_180012C23
0x180012c11  mov     ecx, edx
0x180012c13  lea     rax, [rdx-1]
0x180012c17  test    rcx, rax
0x180012c1a  jz      short loc_180012C23
0x180012c1c  mov     edx, 110Eh
0x180012c21  jmp     short loc_180012BE4
0x180012c23  mov     r8, [rbp+80h+arg_28]
0x180012c2a  mov     r10, [rbp+80h+arg_40]
0x180012c31  mov     r12, [rbp+80h+arg_48]
0x180012c38  mov     [rdi], r11b
0x180012c3b  mov     [r8], r11b
0x180012c3e  mov     [r10], r11b
0x180012c41  mov     [r12], r11b
0x180012c45  mov     [r14], r11b
0x180012c48  test    edx, edx
0x180012c4a  jz      loc_180012CEF
0x180012c50  mov     ecx, 1
0x180012c55  cmp     edx, 10h
0x180012c58  jz      short loc_180012CA0
0x180012c5a  cmp     edx, 20h ; ' '
0x180012c5d  jz      short loc_180012C94
0x180012c5f  cmp     edx, 40h ; '@'
0x180012c62  jz      short loc_180012C85
0x180012c64  cmp     edx, 200h
0x180012c6a  jz      short loc_180012C76
0x180012c6c  mov     edx, 112Eh
0x180012c71  jmp     loc_180012BE4
0x180012c76  mov     rax, [rbp+80h+arg_20]
0x180012c7d  mov     dword ptr [rax], 3
0x180012c83  jmp     short loc_180012CA9
0x180012c85  mov     rax, [rbp+80h+arg_20]
0x180012c8c  mov     dword ptr [rax], 2
0x180012c92  jmp     short loc_180012CA9
0x180012c94  mov     rax, [rbp+80h+arg_20]
0x180012c9b  mov     [rax], r11d
0x180012c9e  jmp     short loc_180012CA9
0x180012ca0  mov     rax, [rbp+80h+arg_20]
0x180012ca7  mov     [rax], ecx
0x180012ca9  mov     edx, r9d
0x180012cac  and     edx, 80h
0x180012cb2  setnz   al
0x180012cb5  mov     [r8], al
0x180012cb8  mov     eax, r9d
0x180012cbb  shr     eax, 8
0x180012cbe  and     al, cl
0x180012cc0  mov     [rdi], al
0x180012cc2  mov     eax, r9d
0x180012cc5  shr     eax, 0Bh
0x180012cc8  and     al, cl
0x180012cca  mov     [r14], al
0x180012ccd  mov     eax, r9d
0x180012cd0  shr     eax, 0Ch
0x180012cd3  and     al, cl
0x180012cd5  mov     [r10], al
0x180012cd8  bt      r9d, 0Dh
0x180012cdd  jnb     short loc_180012CE3
0x180012cdf  test    edx, edx
0x180012ce1  jz      short loc_180012CE6
0x180012ce3  mov     cl, r11b
0x180012ce6  mov     [r12], cl
0x180012cea  jmp     loc_18001323C
0x180012cef  test    r9d, 1880h
0x180012cf6  jz      short loc_180012D02
0x180012cf8  mov     edx, 113Ch
0x180012cfd  jmp     loc_180012BE4
0x180012d02  lea     rcx, [rsp+180h+var_150]
0x180012d07  mov     [rsp+180h+var_150], r11
0x180012d0c  call    ?Open@Manager_NoThrow@Cache@StateRepository@@QEAAJW4SRCacheFlags@@@Z; StateRepository::Cache::Manager_NoThrow::Open(SRCacheFlags)
0x180012d11  mov     ebx, eax
0x180012d13  test    eax, eax
0x180012d15  jns     short loc_180012D57
0x180012d17  mov     rcx, [rbp+88h]; this
0x180012d1e  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180012d25  mov     r9d, eax; char *
0x180012d28  mov     edx, 1140h; void *
0x180012d2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012d32  mov     rcx, [rsp+180h+var_150]
0x180012d37  and     [rsp+180h+var_150], 0
0x180012d3d  test    rcx, rcx
0x180012d40  jz      loc_180012BFF
0x180012d46  call    cs:__imp_SRCacheManager_Close
0x180012d4d  nop     dword ptr [rax+rax+00h]
0x180012d52  jmp     loc_180012BFF
0x180012d57  and     [rsp+180h+var_130], 0
0x180012d5d  lea     r8, [rsp+180h+var_130]; __int64 *
0x180012d62  mov     rdx, r15; void *
0x180012d65  lea     rcx, [rsp+180h+var_150]; struct StateRepository::Cache::Manager_NoThrow *
0x180012d6a  call    ?GetByToken@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByToken(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x180012d6f  xor     r15d, r15d
0x180012d72  mov     ebx, eax
0x180012d74  test    eax, eax
0x180012d76  jns     short loc_180012D9F
0x180012d78  mov     rcx, [rbp+88h]; this
0x180012d7f  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180012d86  mov     r9d, eax; char *
0x180012d89  mov     edx, 1143h; void *
0x180012d8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012d93  mov     rcx, [rsp+180h+var_150]
0x180012d98  mov     [rsp+180h+var_150], r15
0x180012d9d  jmp     short loc_180012D3D
0x180012d9f  mov     rdx, [rsp+180h+var_130]
0x180012da4  test    rdx, rdx
0x180012da7  jnz     short loc_180012DC9
0x180012da9  mov     rcx, [rbp+88h]; this
0x180012db0  lea     r9d, [rdx+2]; char *
0x180012db4  mov     edx, 1146h; void *
0x180012db9  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180012dc0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180012dc5  mov     ebx, eax
0x180012dc7  jmp     short loc_180012D93
0x180012dc9  xorps   xmm0, xmm0
0x180012dcc  mov     [rsp+180h+var_110], r15
0x180012dd1  xorps   xmm1, xmm1
0x180012dd4  movdqa  xmmword ptr [rsp+180h+var_120], xmm0
0x180012dda  lea     rax, [rbp+80h+arg_0]
0x180012de1  mov     [rsp+180h+var_108], r15
0x180012de6  mov     [rsp+180h+var_158], rax
0x180012deb  lea     rcx, [rsp+180h+var_150]
0x180012df0  lea     rax, [rsp+180h+var_120]
0x180012df5  movdqa  [rbp+80h+var_100], xmm0
0x180012dfa  mov     r9d, 4
0x180012e00  mov     qword ptr [rsp+180h+var_160], rax; unsigned int
0x180012e05  mov     r8, r13
0x180012e08  movdqa  [rbp+80h+var_F0], xmm1
0x180012e0d  movdqa  [rbp+80h+var_E0], xmm0
0x180012e12  movdqa  [rbp+80h+var_D0], xmm1
0x180012e17  mov     [rbp+80h+arg_0], r15b
0x180012e1e  call    ?GetByUserAndApplicationUserModelId@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x180012e23  mov     ebx, eax
0x180012e25  test    eax, eax
0x180012e27  jns     short loc_180012E53
0x180012e29  mov     edx, 114Eh; void *
0x180012e2e  mov     rcx, [rbp+88h]; this
0x180012e35  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180012e3c  mov     r9d, ebx; char *
0x180012e3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012e44  lea     rcx, [rsp+180h+var_120]; this
0x180012e49  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x180012e4e  jmp     loc_180012D93
0x180012e53  cmp     [rbp+80h+arg_0], r15b
0x180012e5a  jnz     short loc_180012E7E
0x180012e5c  mov     rcx, [rbp+88h]; this
0x180012e63  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180012e6a  mov     r9d, 2; char *
0x180012e70  mov     edx, 1151h; void *
0x180012e75  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180012e7a  mov     ebx, eax
0x180012e7c  jmp     short loc_180012E44
0x180012e7e  test    rsi, rsi
0x180012e81  jz      loc_180013162
0x180012e87  lea     rdx, String2; String2
0x180012e8e  mov     rcx, rsi; String1
0x180012e91  call    cs:__imp__wcsicmp
0x180012e98  nop     dword ptr [rax+rax+00h]
0x180012e9d  test    eax, eax
0x180012e9f  jz      loc_180013162
0x180012ea5  mov     r8, qword ptr [rsp+180h+var_120]; __int64
0x180012eaa  lea     rdx, [rsp+180h+var_150]; struct StateRepository::Cache::Manager_NoThrow *
0x180012eaf  mov     r9, rsi; unsigned __int16 *
0x180012eb2  mov     [rsp+180h+var_148], r15
0x180012eb7  lea     rcx, [rsp+180h+var_148]; this
0x180012ebc  mov     [rsp+180h+var_140], r15d
0x180012ec1  mov     [rsp+180h+var_138], r15
0x180012ec6  call    ?OpenByApplicationAndCategory@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_JPEBG@Z; StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplicationAndCategory(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *)
0x180012ecb  mov     ebx, eax
0x180012ecd  test    eax, eax
0x180012ecf  jns     short loc_180012F2B
0x180012ed1  mov     rcx, [rbp+88h]; this
0x180012ed8  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x180012edf  mov     r9d, eax; char *
0x180012ee2  mov     edx, 3B9h; void *
0x180012ee7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012eec  mov     rcx, [rbp+88h]; this
0x180012ef3  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180012efa  mov     r9d, ebx; char *
0x180012efd  mov     edx, 1158h; void *
0x180012f02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012f07  mov     rcx, [rsp+180h+var_148]
0x180012f0c  mov     [rsp+180h+var_148], r15
0x180012f11  test    rcx, rcx
0x180012f14  jz      loc_180012E44
0x180012f1a  call    cs:__imp_SRCacheContext_Close
0x180012f21  nop     dword ptr [rax+rax+00h]
0x180012f26  jmp     loc_180012E44
0x180012f2b  xorps   xmm0, xmm0
0x180012f2e  mov     [rbp+80h+arg_0], r15b
0x180012f35  xorps   xmm1, xmm1
0x180012f38  movdqa  [rbp+80h+var_C0], xmm0
0x180012f3d  lea     r9, [rbp+80h+arg_0]
0x180012f44  movdqa  [rbp+80h+var_A0], xmm0
0x180012f49  lea     r8, [rbp+80h+var_C0]
0x180012f4d  movdqa  [rbp+80h+var_90], xmm1
0x180012f52  lea     rcx, [rsp+180h+var_148]
0x180012f57  mov     [rbp+80h+var_B0], r15
0x180012f5b  mov     [rbp+80h+var_A8], r15
0x180012f5f  mov     [rbp+80h+var_80], r15
0x180012f63  mov     [rbp+80h+var_78], r15d
0x180012f67  call    ?Get@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@ApplicationExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)
0x180012f6c  mov     ebx, eax
0x180012f6e  test    eax, eax
0x180012f70  jns     short loc_180012F9B
0x180012f72  mov     rcx, [rbp+88h]; this
0x180012f79  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180012f80  mov     r9d, eax; char *
0x180012f83  mov     edx, 115Eh; void *
0x180012f88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012f8d  lea     rcx, [rbp+80h+var_C0]; this
0x180012f91  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x180012f96  jmp     loc_180012F07
0x180012f9b  cmp     [rbp+80h+arg_0], r15b
0x180012fa2  jnz     short loc_180012FC6
0x180012fa4  mov     rcx, [rbp+88h]; this
0x180012fab  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180012fb2  mov     r9d, 2; char *
0x180012fb8  mov     edx, 1161h; void *
0x180012fbd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180012fc2  mov     ebx, eax
0x180012fc4  jmp     short loc_180012F8D
0x180012fc6  xorps   xmm0, xmm0
0x180012fc9  mov     [rbp+80h+var_60], r15d
0x180012fcd  xorps   xmm1, xmm1
0x180012fd0  movdqa  [rbp+80h+var_70], xmm0
0x180012fd5  lea     r9, [rbp+80h+arg_0]; bool *
0x180012fdc  movdqa  [rbp+80h+var_50], xmm0
0x180012fe1  lea     r8, [rbp+80h+var_70]; struct StateRepository::Cache::Entity::Activation_NoThrow *
0x180012fe5  movdqa  [rbp+80h+var_40], xmm1
0x180012fea  lea     rdx, [rsp+180h+var_150]; struct StateRepository::Cache::Manager_NoThrow *
0x180012fef  mov     [rbp+80h+var_58], r15
0x180012ff3  lea     rcx, [rbp+80h+var_C0]; this
0x180012ff7  mov     [rbp+80h+var_30], r15
0x180012ffb  mov     [rbp+80h+arg_0], r15b
0x180013002  call    ?GetActivation@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEBAJAEAVManager_NoThrow@34@AEAVActivation_NoThrow@234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::GetActivation(StateRepository::Cache::Manager_NoThrow &,StateRepository::Cache::Entity::Activation_NoThrow &,bool &)
0x180013007  mov     ebx, eax
0x180013009  test    eax, eax
0x18001300b  jns     short loc_180013036
0x18001300d  mov     edx, 1166h; void *
0x180013012  mov     rcx, [rbp+88h]; this
0x180013019  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180013020  mov     r9d, ebx; char *
0x180013023  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013028  lea     rcx, [rbp+80h+var_70]; this
0x18001302c  call    ??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)
0x180013031  jmp     loc_180012F8D
0x180013036  cmp     [rbp+80h+arg_0], r15b
0x18001303d  jnz     short loc_180013061
0x18001303f  mov     rcx, [rbp+88h]; this
0x180013046  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18001304d  mov     r9d, 2; char *
0x180013053  mov     edx, 1169h; void *
0x180013058  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001305d  mov     ebx, eax
0x18001305f  jmp     short loc_180013028
0x180013061  mov     r8d, [rbp+80h+var_60]
0x180013065  mov     ecx, 1
0x18001306a  bt      r8d, 8
0x18001306f  jb      short loc_1800130B4
0x180013071  test    r8b, 10h
0x180013075  jnz     short loc_1800130A7
0x180013077  test    r8b, 20h
0x18001307b  jnz     short loc_180013097
0x18001307d  bt      r8d, 9
0x180013082  jb      short loc_180013090
0x180013084  mov     ebx, 80070057h
0x180013089  mov     edx, 117Eh
0x18001308e  jmp     short loc_180013012
0x180013090  mov     edx, 3
0x180013095  jmp     short loc_18001309C
0x180013097  mov     edx, 2
0x18001309c  mov     rax, [rbp+80h+arg_20]
0x1800130a3  mov     [rax], edx
0x1800130a5  jmp     short loc_1800130C1
  ... truncated ...
```
