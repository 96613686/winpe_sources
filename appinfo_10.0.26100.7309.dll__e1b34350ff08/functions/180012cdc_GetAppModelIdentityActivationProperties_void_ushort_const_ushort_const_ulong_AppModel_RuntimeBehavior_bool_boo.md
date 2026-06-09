# GetAppModelIdentityActivationProperties(void *,ushort const *,ushort const *,ulong,AppModel::RuntimeBehavior *,bool *,bool *,bool *,bool *,bool *)

- ea: `0x180012cdc`
- end: `0x1800133c5`
- name: `?GetAppModelIdentityActivationProperties@@YAJPEAXPEBG1KPEAW4RuntimeBehavior@AppModel@@PEA_N3333@Z`
- size: `1769`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, enum AppModel::RuntimeBehavior *, bool *, bool *, bool *, bool *, bool *)`
- caller_count: `4`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180027464`
- `0x1800286a4`
- `0x18002a1d8`
- `0x180032810`

## callees

- `0x180004eb0`
- `0x180005880`
- `0x180007b30`
- `0x180007c78`
- `0x180007ca0`
- `0x180009470`
- `0x18000cd00`
- `0x18000dca8`
- `0x18000e370`
- `0x180012cdc`
- `0x180018530`
- `0x18001880c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180012fd1`
- `msvcrt!_wcsicmp` at `0x180012fd1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180012e86`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180013370`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180012e86`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x180013370`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001305a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180013277`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001305a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180013277`

## string_xrefs

- `0x180013018`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180012d2b`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180012e5e`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180012ebf`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180012ef9`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180012f75`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180012fa3`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180013033`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800130b9`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800130eb`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180013159`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180013186`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

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
    v15 = 4542;
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
    v15 = 4545;
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
      v15 = 4591;
      goto LABEL_3;
    }
    v52 = 0;
    v23 = StateRepository::Cache::Manager_NoThrow::Open(&v52);
    Activation = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x11F3,
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
        (void *)0x11F6,
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
                     (void *)0x11F9,
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
      v28 = 4609;
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
                     (void *)0x1204,
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
          (void *)0x120B,
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
          (void *)0x1211,
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
                       (void *)0x1214,
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
        v34 = 4633;
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
                       (void *)0x121C,
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
            v34 = 4657;
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
          v28 = 4695;
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
      v15 = 4577;
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
0x180012cdc  mov     [rsp-8+arg_8], rbx
0x180012ce1  mov     [rsp-8+arg_10], rsi
0x180012ce6  mov     [rsp-8+arg_18], rdi
0x180012ceb  push    rbp
0x180012cec  push    r12
0x180012cee  push    r13
0x180012cf0  push    r14
0x180012cf2  push    r15
0x180012cf4  lea     rbp, [rsp-60h]
0x180012cf9  sub     rsp, 160h
0x180012d00  mov     rdi, [rbp+80h+arg_30]
0x180012d07  xor     r11d, r11d
0x180012d0a  mov     r14, [rbp+80h+arg_38]
0x180012d11  mov     rsi, r8
0x180012d14  mov     r13, rdx
0x180012d17  mov     r15, rcx
0x180012d1a  test    rcx, rcx
0x180012d1d  jnz     short loc_180012D46
0x180012d1f  mov     edx, 11BEh; void *
0x180012d24  mov     rcx, [rbp+88h]; this
0x180012d2b  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180012d32  mov     ebx, 80070057h
0x180012d37  mov     r9d, ebx; char *
0x180012d3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012d3f  mov     eax, ebx
0x180012d41  jmp     loc_18001337E
0x180012d46  mov     edx, r9d
0x180012d49  and     edx, 270h
0x180012d4f  jz      short loc_180012D63
0x180012d51  mov     ecx, edx
0x180012d53  lea     rax, [rdx-1]
0x180012d57  test    rcx, rax
0x180012d5a  jz      short loc_180012D63
0x180012d5c  mov     edx, 11C1h
0x180012d61  jmp     short loc_180012D24
0x180012d63  mov     r8, [rbp+80h+arg_28]
0x180012d6a  mov     r10, [rbp+80h+arg_40]
0x180012d71  mov     r12, [rbp+80h+arg_48]
0x180012d78  mov     [rdi], r11b
0x180012d7b  mov     [r8], r11b
0x180012d7e  mov     [r10], r11b
0x180012d81  mov     [r12], r11b
0x180012d85  mov     [r14], r11b
0x180012d88  test    edx, edx
0x180012d8a  jz      loc_180012E2F
0x180012d90  mov     ecx, 1
0x180012d95  cmp     edx, 10h
0x180012d98  jz      short loc_180012DE0
0x180012d9a  cmp     edx, 20h ; ' '
0x180012d9d  jz      short loc_180012DD4
0x180012d9f  cmp     edx, 40h ; '@'
0x180012da2  jz      short loc_180012DC5
0x180012da4  cmp     edx, 200h
0x180012daa  jz      short loc_180012DB6
0x180012dac  mov     edx, 11E1h
0x180012db1  jmp     loc_180012D24
0x180012db6  mov     rax, [rbp+80h+arg_20]
0x180012dbd  mov     dword ptr [rax], 3
0x180012dc3  jmp     short loc_180012DE9
0x180012dc5  mov     rax, [rbp+80h+arg_20]
0x180012dcc  mov     dword ptr [rax], 2
0x180012dd2  jmp     short loc_180012DE9
0x180012dd4  mov     rax, [rbp+80h+arg_20]
0x180012ddb  mov     [rax], r11d
0x180012dde  jmp     short loc_180012DE9
0x180012de0  mov     rax, [rbp+80h+arg_20]
0x180012de7  mov     [rax], ecx
0x180012de9  mov     edx, r9d
0x180012dec  and     edx, 80h
0x180012df2  setnz   al
0x180012df5  mov     [r8], al
0x180012df8  mov     eax, r9d
0x180012dfb  shr     eax, 8
0x180012dfe  and     al, cl
0x180012e00  mov     [rdi], al
0x180012e02  mov     eax, r9d
0x180012e05  shr     eax, 0Bh
0x180012e08  and     al, cl
0x180012e0a  mov     [r14], al
0x180012e0d  mov     eax, r9d
0x180012e10  shr     eax, 0Ch
0x180012e13  and     al, cl
0x180012e15  mov     [r10], al
0x180012e18  bt      r9d, 0Dh
0x180012e1d  jnb     short loc_180012E23
0x180012e1f  test    edx, edx
0x180012e21  jz      short loc_180012E26
0x180012e23  mov     cl, r11b
0x180012e26  mov     [r12], cl
0x180012e2a  jmp     loc_18001337C
0x180012e2f  test    r9d, 1880h
0x180012e36  jz      short loc_180012E42
0x180012e38  mov     edx, 11EFh
0x180012e3d  jmp     loc_180012D24
0x180012e42  lea     rcx, [rsp+180h+var_150]
0x180012e47  mov     [rsp+180h+var_150], r11
0x180012e4c  call    ?Open@Manager_NoThrow@Cache@StateRepository@@QEAAJW4SRCacheFlags@@@Z; StateRepository::Cache::Manager_NoThrow::Open(SRCacheFlags)
0x180012e51  mov     ebx, eax
0x180012e53  test    eax, eax
0x180012e55  jns     short loc_180012E97
0x180012e57  mov     rcx, [rbp+88h]; this
0x180012e5e  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180012e65  mov     r9d, eax; char *
0x180012e68  mov     edx, 11F3h; void *
0x180012e6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012e72  mov     rcx, [rsp+180h+var_150]
0x180012e77  and     [rsp+180h+var_150], 0
0x180012e7d  test    rcx, rcx
0x180012e80  jz      loc_180012D3F
0x180012e86  call    cs:__imp_SRCacheManager_Close
0x180012e8d  nop     dword ptr [rax+rax+00h]
0x180012e92  jmp     loc_180012D3F
0x180012e97  and     [rsp+180h+var_130], 0
0x180012e9d  lea     r8, [rsp+180h+var_130]; __int64 *
0x180012ea2  mov     rdx, r15; void *
0x180012ea5  lea     rcx, [rsp+180h+var_150]; struct StateRepository::Cache::Manager_NoThrow *
0x180012eaa  call    ?GetByToken@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByToken(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x180012eaf  xor     r15d, r15d
0x180012eb2  mov     ebx, eax
0x180012eb4  test    eax, eax
0x180012eb6  jns     short loc_180012EDF
0x180012eb8  mov     rcx, [rbp+88h]; this
0x180012ebf  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180012ec6  mov     r9d, eax; char *
0x180012ec9  mov     edx, 11F6h; void *
0x180012ece  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012ed3  mov     rcx, [rsp+180h+var_150]
0x180012ed8  mov     [rsp+180h+var_150], r15
0x180012edd  jmp     short loc_180012E7D
0x180012edf  mov     rdx, [rsp+180h+var_130]
0x180012ee4  test    rdx, rdx
0x180012ee7  jnz     short loc_180012F09
0x180012ee9  mov     rcx, [rbp+88h]; this
0x180012ef0  lea     r9d, [rdx+2]; char *
0x180012ef4  mov     edx, 11F9h; void *
0x180012ef9  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180012f00  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180012f05  mov     ebx, eax
0x180012f07  jmp     short loc_180012ED3
0x180012f09  xorps   xmm0, xmm0
0x180012f0c  mov     [rsp+180h+var_110], r15
0x180012f11  xorps   xmm1, xmm1
0x180012f14  movdqa  xmmword ptr [rsp+180h+var_120], xmm0
0x180012f1a  lea     rax, [rbp+80h+arg_0]
0x180012f21  mov     [rsp+180h+var_108], r15
0x180012f26  mov     [rsp+180h+var_158], rax
0x180012f2b  lea     rcx, [rsp+180h+var_150]
0x180012f30  lea     rax, [rsp+180h+var_120]
0x180012f35  movdqa  [rbp+80h+var_100], xmm0
0x180012f3a  mov     r9d, 4
0x180012f40  mov     qword ptr [rsp+180h+var_160], rax; unsigned int
0x180012f45  mov     r8, r13
0x180012f48  movdqa  [rbp+80h+var_F0], xmm1
0x180012f4d  movdqa  [rbp+80h+var_E0], xmm0
0x180012f52  movdqa  [rbp+80h+var_D0], xmm1
0x180012f57  mov     [rbp+80h+arg_0], r15b
0x180012f5e  call    ?GetByUserAndApplicationUserModelId@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x180012f63  mov     ebx, eax
0x180012f65  test    eax, eax
0x180012f67  jns     short loc_180012F93
0x180012f69  mov     edx, 1201h; void *
0x180012f6e  mov     rcx, [rbp+88h]; this
0x180012f75  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180012f7c  mov     r9d, ebx; char *
0x180012f7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012f84  lea     rcx, [rsp+180h+var_120]; this
0x180012f89  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x180012f8e  jmp     loc_180012ED3
0x180012f93  cmp     [rbp+80h+arg_0], r15b
0x180012f9a  jnz     short loc_180012FBE
0x180012f9c  mov     rcx, [rbp+88h]; this
0x180012fa3  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180012faa  mov     r9d, 2; char *
0x180012fb0  mov     edx, 1204h; void *
0x180012fb5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180012fba  mov     ebx, eax
0x180012fbc  jmp     short loc_180012F84
0x180012fbe  test    rsi, rsi
0x180012fc1  jz      loc_1800132A2
0x180012fc7  lea     rdx, String2; String2
0x180012fce  mov     rcx, rsi; String1
0x180012fd1  call    cs:__imp__wcsicmp
0x180012fd8  nop     dword ptr [rax+rax+00h]
0x180012fdd  test    eax, eax
0x180012fdf  jz      loc_1800132A2
0x180012fe5  mov     r8, qword ptr [rsp+180h+var_120]; __int64
0x180012fea  lea     rdx, [rsp+180h+var_150]; struct StateRepository::Cache::Manager_NoThrow *
0x180012fef  mov     r9, rsi; unsigned __int16 *
0x180012ff2  mov     [rsp+180h+var_148], r15
0x180012ff7  lea     rcx, [rsp+180h+var_148]; this
0x180012ffc  mov     [rsp+180h+var_140], r15d
0x180013001  mov     [rsp+180h+var_138], r15
0x180013006  call    ?OpenByApplicationAndCategory@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_JPEBG@Z; StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplicationAndCategory(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *)
0x18001300b  mov     ebx, eax
0x18001300d  test    eax, eax
0x18001300f  jns     short loc_18001306B
0x180013011  mov     rcx, [rbp+88h]; this
0x180013018  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001301f  mov     r9d, eax; char *
0x180013022  mov     edx, 3B9h; void *
0x180013027  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001302c  mov     rcx, [rbp+88h]; this
0x180013033  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18001303a  mov     r9d, ebx; char *
0x18001303d  mov     edx, 120Bh; void *
0x180013042  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013047  mov     rcx, [rsp+180h+var_148]
0x18001304c  mov     [rsp+180h+var_148], r15
0x180013051  test    rcx, rcx
0x180013054  jz      loc_180012F84
0x18001305a  call    cs:__imp_SRCacheContext_Close
0x180013061  nop     dword ptr [rax+rax+00h]
0x180013066  jmp     loc_180012F84
0x18001306b  xorps   xmm0, xmm0
0x18001306e  mov     [rbp+80h+arg_0], r15b
0x180013075  xorps   xmm1, xmm1
0x180013078  movdqa  [rbp+80h+var_C0], xmm0
0x18001307d  lea     r9, [rbp+80h+arg_0]
0x180013084  movdqa  [rbp+80h+var_A0], xmm0
0x180013089  lea     r8, [rbp+80h+var_C0]
0x18001308d  movdqa  [rbp+80h+var_90], xmm1
0x180013092  lea     rcx, [rsp+180h+var_148]
0x180013097  mov     [rbp+80h+var_B0], r15
0x18001309b  mov     [rbp+80h+var_A8], r15
0x18001309f  mov     [rbp+80h+var_80], r15
0x1800130a3  mov     [rbp+80h+var_78], r15d
0x1800130a7  call    ?Get@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@ApplicationExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)
0x1800130ac  mov     ebx, eax
0x1800130ae  test    eax, eax
0x1800130b0  jns     short loc_1800130DB
0x1800130b2  mov     rcx, [rbp+88h]; this
0x1800130b9  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800130c0  mov     r9d, eax; char *
0x1800130c3  mov     edx, 1211h; void *
0x1800130c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800130cd  lea     rcx, [rbp+80h+var_C0]; this
0x1800130d1  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x1800130d6  jmp     loc_180013047
0x1800130db  cmp     [rbp+80h+arg_0], r15b
0x1800130e2  jnz     short loc_180013106
0x1800130e4  mov     rcx, [rbp+88h]; this
0x1800130eb  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800130f2  mov     r9d, 2; char *
0x1800130f8  mov     edx, 1214h; void *
0x1800130fd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180013102  mov     ebx, eax
0x180013104  jmp     short loc_1800130CD
0x180013106  xorps   xmm0, xmm0
0x180013109  mov     [rbp+80h+var_60], r15d
0x18001310d  xorps   xmm1, xmm1
0x180013110  movdqa  [rbp+80h+var_70], xmm0
0x180013115  lea     r9, [rbp+80h+arg_0]; bool *
0x18001311c  movdqa  [rbp+80h+var_50], xmm0
0x180013121  lea     r8, [rbp+80h+var_70]; struct StateRepository::Cache::Entity::Activation_NoThrow *
0x180013125  movdqa  [rbp+80h+var_40], xmm1
0x18001312a  lea     rdx, [rsp+180h+var_150]; struct StateRepository::Cache::Manager_NoThrow *
0x18001312f  mov     [rbp+80h+var_58], r15
0x180013133  lea     rcx, [rbp+80h+var_C0]; this
0x180013137  mov     [rbp+80h+var_30], r15
0x18001313b  mov     [rbp+80h+arg_0], r15b
0x180013142  call    ?GetActivation@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEBAJAEAVManager_NoThrow@34@AEAVActivation_NoThrow@234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::GetActivation(StateRepository::Cache::Manager_NoThrow &,StateRepository::Cache::Entity::Activation_NoThrow &,bool &)
0x180013147  mov     ebx, eax
0x180013149  test    eax, eax
0x18001314b  jns     short loc_180013176
0x18001314d  mov     edx, 1219h; void *
0x180013152  mov     rcx, [rbp+88h]; this
0x180013159  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180013160  mov     r9d, ebx; char *
0x180013163  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013168  lea     rcx, [rbp+80h+var_70]; this
0x18001316c  call    ??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)
0x180013171  jmp     loc_1800130CD
0x180013176  cmp     [rbp+80h+arg_0], r15b
0x18001317d  jnz     short loc_1800131A1
0x18001317f  mov     rcx, [rbp+88h]; this
0x180013186  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18001318d  mov     r9d, 2; char *
0x180013193  mov     edx, 121Ch; void *
0x180013198  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001319d  mov     ebx, eax
0x18001319f  jmp     short loc_180013168
0x1800131a1  mov     r8d, [rbp+80h+var_60]
0x1800131a5  mov     ecx, 1
0x1800131aa  bt      r8d, 8
0x1800131af  jb      short loc_1800131F4
0x1800131b1  test    r8b, 10h
0x1800131b5  jnz     short loc_1800131E7
0x1800131b7  test    r8b, 20h
0x1800131bb  jnz     short loc_1800131D7
0x1800131bd  bt      r8d, 9
0x1800131c2  jb      short loc_1800131D0
0x1800131c4  mov     ebx, 80070057h
0x1800131c9  mov     edx, 1231h
0x1800131ce  jmp     short loc_180013152
0x1800131d0  mov     edx, 3
0x1800131d5  jmp     short loc_1800131DC
0x1800131d7  mov     edx, 2
0x1800131dc  mov     rax, [rbp+80h+arg_20]
0x1800131e3  mov     [rax], edx
0x1800131e5  jmp     short loc_180013201
  ... truncated ...
```
