# SystemSettings::PenSettings::DevicesPenSetActionModifierBase::GetValue(IInspectable * *)

- ea: `0x180029580`
- end: `0x180029779`
- name: `?GetValue@DevicesPenSetActionModifierBase@PenSettings@SystemSettings@@UEAAJPEAPEAUIInspectable@@@Z`
- size: `505`
- prototype: `int(SystemSettings::PenSettings::DevicesPenSetActionModifierBase *__hidden this, struct IInspectable **)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000a2bc`
- `0x180012868`
- `0x180014710`
- `0x180019a40`
- `0x180019b90`
- `0x18001bb6c`
- `0x180027dcc`
- `0x180029580`
- `0x18002ee30`
- `0x18002efa4`
- `0x180052e6c`
- `0x180052eec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800296c6`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800296c6`

## string_xrefs

- `0x180029648`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`
- `0x180029721`: `shellcommon\shell\settingshandlers\pen\lib\penbuttoncustomization.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::PenSettings::DevicesPenSetActionModifierBase::GetValue(
        SystemSettings::PenSettings::DevicesPenSetActionModifierBase *this,
        struct IInspectable **a2)
{
  int v4; // ecx
  int v5; // eax
  __int64 v6; // rcx
  unsigned int v7; // r9d
  SystemSettings::DataModel *v8; // rbx
  struct IInspectable **v9; // r8
  int ResourceStringValue; // eax
  unsigned int v11; // ebx
  __int64 v12; // r9
  wchar_t *v13; // rax
  int String; // eax
  __int64 v15; // rdx
  int v17; // [rsp+20h] [rbp-40h]
  int v18; // [rsp+20h] [rbp-40h]
  wchar_t *Str; // [rsp+30h] [rbp-30h] BYREF
  __int64 v20; // [rsp+38h] [rbp-28h]
  __int64 v21; // [rsp+40h] [rbp-20h]
  unsigned __int16 *v22[3]; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  unsigned int v24; // [rsp+80h] [rbp+20h] BYREF
  unsigned __int16 *v25; // [rsp+88h] [rbp+28h] BYREF

  *a2 = 0;
  v4 = *((_DWORD *)this + 68);
  v25 = 0;
  SystemSettings::PenSettings::ActionTypeOptionManager::GetPrimitiveSpecificParameters(v4, &v25, 0, 0, 0, 0);
  v5 = *((_DWORD *)this + 69);
  if ( v5 != 5 )
  {
    if ( v5 != 2 )
      return 0;
    Str = 0;
    v20 = 0;
    v21 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&Str);
    v20 = -1;
    v21 = -1;
    if ( (int)SHRegAllocData(HKEY_CURRENT_USER, v25, L"CustomAppId", v12, (void **)&Str) >= 0 )
    {
      v13 = wcschr(Str, 0x40u);
      if ( v13 )
      {
        memset(v22, 0, sizeof(v22));
        String = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
                   v22,
                   v13 + 1,
                   -1);
        v11 = String;
        if ( String < 0 )
        {
          v15 = 1116;
LABEL_15:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v15,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
            (const char *)(unsigned int)String,
            v18);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v22);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&Str);
          return v11;
        }
        String = SystemSettings::DataModel::PropValueHelper::CreateString(v22[0], a2);
        v11 = String;
        if ( String < 0 )
        {
          v15 = 1117;
          goto LABEL_15;
        }
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v22);
      }
      SystemSettings::PenSettings::PenSettingsCacheSingleton::UpdateActionValueCache(*((unsigned int *)this + 68), Str);
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&Str);
    return 0;
  }
  v24 = -1;
  SHRegGetDWORD(HKEY_CURRENT_USER, v25, L"PenWorkspaceVerb", &v24);
  if ( v24 == -1 )
    v6 = 0;
  else
    v6 = v24;
  v8 = (SystemSettings::DataModel *)SystemSettings::PenSettings::FindResourceTagFromEnum<enum SystemSettings::PenSettings::PenWorkspaceVerb,SystemSettings::PenSettings::PenWorkspaceVerbResourceMapping_>(v6);
  SystemSettings::PenSettings::PenSettingsCacheSingleton::UpdateActionValueCachePenWorkspace(
    *((unsigned int *)this + 68),
    v7);
  if ( v8 )
  {
    ResourceStringValue = SystemSettings::DataModel::GetResourceStringValue(v8, a2, v9);
    v11 = ResourceStringValue;
    if ( ResourceStringValue < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x465,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penbuttoncustomization.cpp",
        (const char *)(unsigned int)ResourceStringValue,
        v17);
      return v11;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180029580  mov     [rsp-18h+arg_10], rbx
0x180029585  push    rbp
0x180029586  push    rsi
0x180029587  push    rdi
0x180029588  mov     rbp, rsp
0x18002958b  sub     rsp, 60h
0x18002958f  mov     qword ptr [rdx], 0
0x180029596  mov     rsi, rdx
0x180029599  mov     rdi, rcx
0x18002959c  mov     [rsp+60h+var_38], 0; unsigned int *
0x1800295a5  mov     ecx, [rcx+110h]
0x1800295ab  lea     rdx, [rbp+arg_8]
0x1800295af  xor     r9d, r9d
0x1800295b2  mov     [rbp+arg_8], 0
0x1800295ba  xor     r8d, r8d
0x1800295bd  mov     [rsp+60h+var_40], 0; int
0x1800295c6  call    ?GetPrimitiveSpecificParameters@ActionTypeOptionManager@PenSettings@SystemSettings@@SAXW4PenClickType@@PEAPEBG1PEAPEAV?$vector@UPenActionTypeResourceMapping_@PenSettings@SystemSettings@@V?$allocator@UPenActionTypeResourceMapping_@PenSettings@SystemSettings@@@std@@@std@@11@Z; SystemSettings::PenSettings::ActionTypeOptionManager::GetPrimitiveSpecificParameters(PenClickType,ushort const * *,ushort const * *,std::vector<SystemSettings::PenSettings::PenActionTypeResourceMapping_> * *,ushort const * *,ushort const * *)
0x1800295cb  mov     eax, [rdi+114h]
0x1800295d1  cmp     eax, 5
0x1800295d4  jnz     loc_180029661
0x1800295da  mov     rdx, [rbp+arg_8]; unsigned __int16 *
0x1800295de  lea     r9, [rbp+arg_0]; unsigned int *
0x1800295e2  lea     r8, aPenworkspaceve; "PenWorkspaceVerb"
0x1800295e9  mov     [rbp+arg_0], 0FFFFFFFFh
0x1800295f0  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1800295f7  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800295fc  mov     r9d, [rbp+arg_0]
0x180029600  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180029604  cmp     r9d, ebx
0x180029607  jz      short loc_18002960E
0x180029609  mov     ecx, r9d
0x18002960c  jmp     short loc_180029610
0x18002960e  xor     ecx, ecx
0x180029610  call    ??$FindResourceTagFromEnum@W4PenWorkspaceVerb@PenSettings@SystemSettings@@UPenWorkspaceVerbResourceMapping_@23@@PenSettings@SystemSettings@@YAPEBGW4PenWorkspaceVerb@01@PEBUPenWorkspaceVerbResourceMapping_@01@I@Z; SystemSettings::PenSettings::FindResourceTagFromEnum<SystemSettings::PenSettings::PenWorkspaceVerb,SystemSettings::PenSettings::PenWorkspaceVerbResourceMapping_>(SystemSettings::PenSettings::PenWorkspaceVerb,SystemSettings::PenSettings::PenWorkspaceVerbResourceMapping_ const *,uint)
0x180029615  mov     ecx, [rdi+110h]
0x18002961b  mov     edx, r9d
0x18002961e  mov     rbx, rax
0x180029621  call    ?UpdateActionValueCachePenWorkspace@PenSettingsCacheSingleton@PenSettings@SystemSettings@@SAXW4PenClickType@@K@Z; SystemSettings::PenSettings::PenSettingsCacheSingleton::UpdateActionValueCachePenWorkspace(PenClickType,ulong)
0x180029626  test    rbx, rbx
0x180029629  jz      loc_180029767
0x18002962f  mov     rdx, rsi; struct IInspectable **
0x180029632  mov     rcx, rbx; this
0x180029635  call    ?GetResourceStringValue@DataModel@SystemSettings@@YAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::GetResourceStringValue(ushort const *,IInspectable * *)
0x18002963a  mov     ebx, eax
0x18002963c  test    eax, eax
0x18002963e  jns     loc_180029767
0x180029644  mov     rcx, [rbp+18h]; this
0x180029648  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x18002964f  mov     r9d, eax; char *
0x180029652  mov     edx, 465h; void *
0x180029657  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002965c  jmp     loc_180029742
0x180029661  cmp     eax, 2
0x180029664  jnz     loc_180029767
0x18002966a  lea     rcx, [rbp+Str]
0x18002966e  mov     [rbp+Str], 0
0x180029676  mov     [rbp+var_28], 0
0x18002967e  mov     [rbp+var_20], 0
0x180029686  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002968b  mov     rdx, [rbp+arg_8]; unsigned __int16 *
0x18002968f  lea     rax, [rbp+Str]
0x180029693  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180029697  mov     [rsp+60h+var_40], rax; int
0x18002969c  lea     r8, pszValue; "CustomAppId"
0x1800296a3  mov     [rbp+var_28], rbx
0x1800296a7  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1800296ae  mov     [rbp+var_20], rbx
0x1800296b2  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x1800296b7  test    eax, eax
0x1800296b9  js      loc_18002975E
0x1800296bf  mov     rcx, [rbp+Str]; Str
0x1800296c3  lea     edx, [rbx+41h]; Ch
0x1800296c6  call    cs:__imp_wcschr
0x1800296cc  test    rax, rax
0x1800296cf  jz      short loc_18002974F
0x1800296d1  lea     rdx, [rax+2]
0x1800296d5  mov     [rbp+var_18], 0
0x1800296dd  mov     r8, rbx
0x1800296e0  mov     [rbp+var_10], 0
0x1800296e8  lea     rcx, [rbp+var_18]
0x1800296ec  mov     [rbp+var_8], 0
0x1800296f4  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800296f9  mov     ebx, eax
0x1800296fb  test    eax, eax
0x1800296fd  jns     short loc_180029706
0x1800296ff  mov     edx, 45Ch
0x180029704  jmp     short loc_18002971D
0x180029706  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x18002970a  mov     rdx, rsi; struct IInspectable **
0x18002970d  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180029712  mov     ebx, eax
0x180029714  test    eax, eax
0x180029716  jns     short loc_180029746
0x180029718  mov     edx, 45Dh; void *
0x18002971d  mov     rcx, [rbp+18h]; this
0x180029721  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\settingshandlers\\p"...
0x180029728  mov     r9d, eax; char *
0x18002972b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029730  lea     rcx, [rbp+var_18]
0x180029734  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180029739  lea     rcx, [rbp+Str]
0x18002973d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180029742  mov     eax, ebx
0x180029744  jmp     short loc_180029769
0x180029746  lea     rcx, [rbp+var_18]
0x18002974a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002974f  mov     rdx, [rbp+Str]
0x180029753  mov     ecx, [rdi+110h]
0x180029759  call    ?UpdateActionValueCache@PenSettingsCacheSingleton@PenSettings@SystemSettings@@SAXW4PenClickType@@PEBG@Z; SystemSettings::PenSettings::PenSettingsCacheSingleton::UpdateActionValueCache(PenClickType,ushort const *)
0x18002975e  lea     rcx, [rbp+Str]
0x180029762  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180029767  xor     eax, eax
0x180029769  mov     rbx, [rsp+60h+arg_10]
0x180029771  add     rsp, 60h
0x180029775  pop     rdi
0x180029776  pop     rsi
0x180029777  pop     rbp
0x180029778  retn
```
