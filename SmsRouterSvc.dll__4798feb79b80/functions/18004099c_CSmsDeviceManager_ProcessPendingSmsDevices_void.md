# CSmsDeviceManager::ProcessPendingSmsDevices(void)

- ea: `0x18004099c`
- end: `0x180041aa2`
- name: `?ProcessPendingSmsDevices@CSmsDeviceManager@@AEAAJXZ`
- size: `4358`
- prototype: `__int64 __fastcall(CSmsDeviceManager *__hidden this)`
- caller_count: `4`
- callee_count: `30`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003fb18`
- `0x18003fe20`
- `0x180040918`
- `0x18004332c`

## callees

- `0x180003a60`
- `0x180003a90`
- `0x180003f50`
- `0x180004974`
- `0x180004998`
- `0x1800069f0`
- `0x180006c84`
- `0x18001446c`
- `0x1800216e4`
- `0x18003d318`
- `0x18003d3dc`
- `0x18003d654`
- `0x18003d784`
- `0x18003d89c`
- `0x18003de28`
- `0x18003e3e8`
- `0x18003e4e0`
- `0x18003e600`
- `0x18003e790`
- `0x18003e9a0`
- `0x18003eb68`
- `0x18004099c`
- `0x180043e14`
- `0x180044028`
- `0x180044234`
- `0x180044624`
- `0x180051420`
- `0x180051628`
- `0x180053be8`
- `0x18006f010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800410f9`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800410f9`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180040c4c`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180040c4c`
- `IPHLPAPI!GetIfEntry2` at `0x180040c5d`
- `IPHLPAPI!GetIfEntry2` at `0x180040c5d`
- `wwapi!WwanQueryInterface` at `0x180040ba0`
- `wwapi!WwanQueryInterface` at `0x180040ba0`

## string_xrefs

- `0x180040e62`: `Created WwanSmsDevice: %S for Interface %s`
- `0x1800413c1`: `Created CellularSmsDevice: %S for Interface %s SmsModel: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CSmsDeviceManager::ProcessPendingSmsDevices(CSmsDeviceManager *this)
{
  _QWORD *v2; // rax
  _QWORD *v3; // rax
  _QWORD *v4; // rax
  _QWORD *v5; // rax
  void *v6; // rcx
  _QWORD *v7; // rbx
  void *v8; // rcx
  __int64 *v9; // rbx
  __int64 v10; // rcx
  int Interface; // eax
  signed int v12; // edi
  const char *v13; // rax
  const char *v14; // rax
  struct WWAN_INTERFACE_OBJECT *v15; // rdi
  __int64 *v16; // rax
  __int64 v17; // rcx
  __int64 *v18; // rdi
  __int64 v19; // r8
  const char *GuidDisplayStringInternal; // rax
  const wchar_t *v21; // r9
  __int64 v22; // rax
  __int64 v23; // r8
  __int64 v24; // rax
  __int64 v25; // r8
  __int64 v26; // rax
  __int64 v27; // rsi
  _QWORD *v28; // rdi
  __int64 v29; // r9
  __int64 v30; // rax
  const char *v31; // rax
  const char *v32; // rax
  __int128 v33; // xmm6
  const char *v34; // rdi
  const char *v35; // rax
  _BYTE *v36; // rdx
  __int64 **v37; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 *v40; // rbx
  __int64 **v41; // rcx
  __int64 *k; // rax
  __int64 *m; // rcx
  __int64 *v44; // rbx
  char *v45; // r14
  _QWORD *v46; // rdi
  __int64 v47; // r12
  struct _GUID *v48; // rax
  struct _GUID *v49; // rdi
  struct _GUID *v50; // rsi
  __int64 *v51; // rdi
  struct _GUID *v52; // rdi
  _QWORD *v53; // rdi
  _QWORD *v54; // rsi
  _QWORD *v55; // rax
  __int64 v56; // r8
  __int64 v57; // rcx
  _QWORD *v58; // rdi
  const char *v59; // rax
  const wchar_t *v60; // r9
  _QWORD *v61; // rax
  __int64 v62; // r8
  __int64 v63; // rax
  __int64 v64; // rsi
  _QWORD *v65; // rdi
  unsigned __int16 *v66; // r9
  __int64 v67; // rax
  __int64 v68; // rax
  const unsigned __int16 *v69; // rdi
  __int64 v70; // rax
  CCellularSmsDevice *v71; // rdi
  _QWORD *v72; // rax
  __int64 v73; // rcx
  __int64 v74; // rax
  __int64 **v75; // rcx
  __int64 *n; // rax
  __int64 *ii; // rcx
  __int64 *v78; // rbx
  __int64 **v79; // rcx
  __int64 *jj; // rax
  __int64 *kk; // rcx
  __int64 *v82; // rbx
  __int64 *v83; // rdi
  __int64 v84; // rcx
  __int64 **v85; // rcx
  __int64 *mm; // rax
  __int64 *nn; // rcx
  int v88; // eax
  __int64 *v89; // rdi
  __int64 v90; // rcx
  __int64 **v91; // rcx
  __int64 *i1; // rax
  __int64 *i2; // rcx
  void (__fastcall ***v94)(_QWORD, GUID *, struct _GUID **); // r9
  struct _GUID *v95; // rcx
  void (__fastcall ***v96)(_QWORD, GUID *, struct _GUID **); // r9
  struct _GUID *v97; // rcx
  __int64 **v98; // rcx
  __int64 *i3; // rax
  __int64 *i4; // rcx
  _QWORD *v101; // rbx
  void *v102; // rcx
  struct _GUID *v104; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD *v105; // [rsp+50h] [rbp-B8h] BYREF
  int v106[2]; // [rsp+58h] [rbp-B0h] BYREF
  struct WWAN_INTERFACE_OBJECT *v107; // [rsp+60h] [rbp-A8h] BYREF
  void *Block[2]; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int16 *v109; // [rsp+78h] [rbp-90h] BYREF
  struct _WNF_STATE_NAME *v110; // [rsp+80h] [rbp-88h] BYREF
  CCellularSmsDevice *v111; // [rsp+88h] [rbp-80h] BYREF
  void *v112[2]; // [rsp+90h] [rbp-78h] BYREF
  void *v113[2]; // [rsp+A0h] [rbp-68h] BYREF
  void *v114[2]; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v115; // [rsp+C0h] [rbp-48h] BYREF
  char v116[8]; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v117; // [rsp+D0h] [rbp-38h] BYREF
  _BYTE v118[16]; // [rsp+E0h] [rbp-28h] BYREF
  _QWORD *v119; // [rsp+F0h] [rbp-18h] BYREF
  _BYTE v120[16]; // [rsp+100h] [rbp-8h] BYREF
  void **v121; // [rsp+110h] [rbp+8h]
  char *v122; // [rsp+118h] [rbp+10h]
  _BYTE v123[16]; // [rsp+120h] [rbp+18h] BYREF
  char v124[16]; // [rsp+130h] [rbp+28h] BYREF
  char v125[16]; // [rsp+140h] [rbp+38h] BYREF
  char v126[16]; // [rsp+150h] [rbp+48h] BYREF
  char v127[16]; // [rsp+160h] [rbp+58h] BYREF
  char v128[16]; // [rsp+170h] [rbp+68h] BYREF
  char v129[16]; // [rsp+180h] [rbp+78h] BYREF
  char v130[16]; // [rsp+190h] [rbp+88h] BYREF
  char v131[16]; // [rsp+1A0h] [rbp+98h] BYREF
  char v132[16]; // [rsp+1B0h] [rbp+A8h] BYREF
  char v133[16]; // [rsp+1C0h] [rbp+B8h] BYREF
  char v134[16]; // [rsp+1D0h] [rbp+C8h] BYREF
  char v135[16]; // [rsp+1E0h] [rbp+D8h] BYREF
  char v136[16]; // [rsp+1F0h] [rbp+E8h] BYREF
  GUID Buf2; // [rsp+200h] [rbp+F8h] BYREF
  __int128 v138; // [rsp+210h] [rbp+108h] BYREF
  __int64 v139; // [rsp+220h] [rbp+118h]
  unsigned __int64 v140; // [rsp+228h] [rbp+120h]
  __int128 v141; // [rsp+230h] [rbp+128h] BYREF
  __int64 v142; // [rsp+240h] [rbp+138h]
  unsigned __int64 v143; // [rsp+248h] [rbp+140h]
  __int128 *v144; // [rsp+268h] [rbp+160h]
  void **v145; // [rsp+278h] [rbp+170h] BYREF
  _BYTE v146[56]; // [rsp+280h] [rbp+178h] BYREF
  _BYTE *v147; // [rsp+2B8h] [rbp+1B0h]
  struct _MIB_IF_ROW2 InterfaceLuid; // [rsp+2C8h] [rbp+1C0h] BYREF

  v113[1] = 0;
  v2 = operator new(0x28u);
  *v2 = v2;
  v2[1] = v2;
  v2[2] = v2;
  *((_WORD *)v2 + 12) = 257;
  v113[0] = v2;
  v112[1] = 0;
  v3 = operator new(0x28u);
  *v3 = v3;
  v3[1] = v3;
  v3[2] = v3;
  *((_WORD *)v3 + 12) = 257;
  v112[0] = v3;
  v107 = 0;
  v114[1] = 0;
  v4 = operator new(0x28u);
  *v4 = v4;
  v4[1] = v4;
  v4[2] = v4;
  *((_WORD *)v4 + 12) = 257;
  v114[0] = v4;
  Block[1] = 0;
  v5 = operator new(0x30u);
  *v5 = v5;
  v5[1] = v5;
  v5[2] = v5;
  *((_WORD *)v5 + 12) = 257;
  Block[0] = v5;
  v121 = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
  v122 = (char *)this + 96;
  (**((void (__fastcall ***)(char *))this + 12))((char *)this + 96);
  if ( !*((_DWORD *)this + 9) )
  {
    LogSmsRouterInfo(
      "CSmsDeviceManager::ProcessPendingSmsDevices",
      0x4A5u,
      "Skipping processing of pending interface guids (%d) since m_Initialized is false",
      *((_DWORD *)this + 82));
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 12) + 8LL))((char *)this + 96);
    v6 = Block[0];
    v7 = (_QWORD *)*((_QWORD *)Block[0] + 1);
    if ( !*((_BYTE *)v7 + 25) )
    {
      do
      {
        std::_Tree_val<std::_Tree_simple_types<_GUID>>::_Erase_tree<std::allocator<std::_Tree_node<_GUID,void *>>>(
          Block,
          Block,
          v7[2]);
        v8 = v7;
        v7 = (_QWORD *)*v7;
        operator delete(v8);
      }
      while ( !*((_BYTE *)v7 + 25) );
      v6 = Block[0];
    }
    goto LABEL_178;
  }
  std::set<ATL::CComPtr<ISmsDeviceChangeReceiver>>::operator=((__int64 *)v112, (__int64 *)this + 29);
  v9 = (__int64 *)**((_QWORD **)this + 40);
  while ( !*((_BYTE *)v9 + 25) )
  {
    if ( *(_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,SmsDeviceInformation,CGuidLessCompare,std::allocator<std::pair<_GUID const,SmsDeviceInformation>>,0>>::find(
                      (char *)this + 256,
                      &v111,
                      (char *)v9 + 28) == *((_QWORD *)this + 32) )
      goto LABEL_48;
    v107 = 0;
    v104 = 0;
    v106[0] = 0;
    v10 = *((_QWORD *)this + 6);
    if ( !v10 )
    {
      LOWORD(v12) = 21;
      goto LABEL_18;
    }
    Interface = WwanQueryInterface(v10, (char *)v9 + 28, 7);
    v12 = Interface;
    if ( Interface )
    {
      if ( Interface > 0 )
LABEL_18:
        v12 = (unsigned __int16)v12 | 0x80070000;
      LogSmsRouterError("CSmsDeviceManager::GetWwanInterfaceObject", 0x19Au, v12, "WwanQueryInterface failed");
      goto LABEL_20;
    }
    if ( v106[0] >= 0x8E8u && v104 )
    {
      v107 = (struct WWAN_INTERFACE_OBJECT *)v104;
      v12 = 0;
    }
    else
    {
      LogSmsRouterError("CSmsDeviceManager::GetWwanInterfaceObject", 0x1A1u, -2147418113, "WWAN_INTERFACE_OBJECT size");
      v12 = -2147418113;
    }
LABEL_20:
    if ( v12 >= 0 )
    {
      *(_QWORD *)&v141 = off_1800704F8;
      *((_QWORD *)&v141 + 1) = &v107;
      v144 = &v141;
      Windows::Sms::Common::undo_action::undo_action(&v145, (__int64 *)&v141);
      v15 = v107;
      if ( *(_QWORD *)((char *)v107 + 2252) == *(_QWORD *)&GUID_NULL.Data1
        && *(_QWORD *)((char *)v107 + 2260) == *(_QWORD *)GUID_NULL.Data4 )
      {
        if ( *(_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,SmsDeviceInformation,CGuidLessCompare,std::allocator<std::pair<_GUID const,SmsDeviceInformation>>,0>>::find(
                          (char *)this + 304,
                          &v115,
                          (char *)v9 + 28) == *((_QWORD *)this + 38) )
        {
          if ( *((_DWORD *)v15 + 161) )
          {
            v138 = 0;
            v139 = 0;
            v140 = 7;
            LOWORD(v138) = 0;
            v104 = 0;
            *(_QWORD *)v106 = 0;
            v16 = (__int64 *)std::map<_GUID,std::wstring,CGuidLessCompare,std::allocator<std::pair<_GUID const,std::wstring>>>::operator[](
                               (__int64 *)this + 32,
                               (__int64 *)((char *)v9 + 28));
            v18 = v16;
            if ( (unsigned __int64)v16[3] <= 7 )
              v19 = (__int64)v16;
            else
              v19 = *v16;
            if ( (int)CSmsDeviceManager::CreateSwDevice(
                        v17,
                        (const GUID *)((char *)v9 + 28),
                        v19,
                        (char *)&v138,
                        (__int64 *)&v104,
                        (__int64 *)v106) >= 0 )
            {
              GuidDisplayStringInternal = GetGuidDisplayStringInternal(
                                            (const struct _GUID *)((char *)v9 + 28),
                                            &byte_18008DA30,
                                            0x200u);
              v21 = (const wchar_t *)&v138;
              if ( v140 > 7 )
                v21 = (const wchar_t *)v138;
              LogSmsRouterInfo(
                "CSmsDeviceManager::ProcessPendingSmsDevices",
                0x4F5u,
                "Created WwanSmsDevice: %S for Interface %s",
                v21,
                GuidDisplayStringInternal);
              v22 = std::map<_GUID,SmsDeviceInformation,CGuidLessCompare,std::allocator<std::pair<_GUID const,SmsDeviceInformation>>>::operator[](
                      (__int64 *)this + 38,
                      (__int64 *)((char *)v9 + 28));
              std::wstring::operator=(v22 + 64, v18, v23);
              v24 = std::map<_GUID,SmsDeviceInformation,CGuidLessCompare,std::allocator<std::pair<_GUID const,SmsDeviceInformation>>>::operator[](
                      (__int64 *)this + 38,
                      (__int64 *)((char *)v9 + 28));
              std::wstring::operator=(v24 + 32, &v138, v25);
              v26 = std::map<_GUID,SmsDeviceInformation,CGuidLessCompare,std::allocator<std::pair<_GUID const,SmsDeviceInformation>>>::operator[](
                      (__int64 *)this + 38,
                      (__int64 *)((char *)v9 + 28));
              *(_QWORD *)(v26 + 112) = v104;
              v27 = std::map<_GUID,SmsDeviceInformation,CGuidLessCompare,std::allocator<std::pair<_GUID const,SmsDeviceInformation>>>::operator[](
                      (__int64 *)this + 38,
                      (__int64 *)((char *)v9 + 28))
                  + 136;
              v28 = operator new(0x10u);
              v105 = v28;
              v29 = *(_QWORD *)v106;
              *v28 = &AutoSwDeviceHandle::`vftable';
              v28[1] = v29;
              LogSmsRouterInfo("AutoSwDeviceHandle::Reset", 0x7Au, "HSWDEVICE 0x%08X added", v29);
              std::shared_ptr<AutoSwDeviceHandle>::reset<AutoSwDeviceHandle,0>(v27, v28);
              LODWORD(v28) = *((_DWORD *)v107 + 569);
              *(_DWORD *)(std::map<_GUID,SmsDeviceInformation,CGuidLessCompare,std::allocator<std::pair<_GUID const,SmsDeviceInformation>>>::operator[](
                            (__int64 *)this + 38,
                            (__int64 *)((char *)v9 + 28))
                        + 152) = (_DWORD)v28;
              if ( (int)CSmsDeviceManager::CreateSmsDeviceFromInterfaceObject(
                          this,
                          (const struct _GUID *)((char *)v9 + 28),
                          v107) >= 0 )
              {
                v30 = std::map<_GUID,SmsDeviceInformation,CGuidLessCompare,std::allocator<std::pair<_GUID const,SmsDeviceInformation>>>::operator[](
                        (__int64 *)this + 38,
                        (__int64 *)((char *)v9 + 28));
                std::_Tree<std::_Tset_traits<ATL::CComPtr<ISmsModel>,std::less<ATL::CComPtr<ISmsModel>>,std::allocator<ATL::CComPtr<ISmsModel>>,0>>::insert<0,0>(
                  (__int64 *)v113,
                  (__int64)&v119,
                  (__int64 *)(v30 + 128));
              }
            }
            std::wstring::~wstring((char **)&v138);
          }
          else
          {
            v31 = GetGuidDisplayStringInternal((const struct _GUID *)((char *)v9 + 28), &byte_18008DA30, 0x200u);
            LogSmsRouterInfo(
              "CSmsDeviceManager::ProcessPendingSmsDevices",
              0x507u,
              "Interface %s does not have sms capability.",
              v31);
          }
        }
        std::_Tree<std::_Tset_traits<_GUID,CGuidLessCompare,std::allocator<_GUID>,0>>::insert<0,0>(
          (__int64 *)Block,
          (__int64)v118,
          (__int64 *)((char *)v9 + 28));
        v32 = GetGuidDisplayStringInternal((const struct _GUID *)((char *)v9 + 28), &byte_18008DA30, 0x200u);
        LogSmsRouterInfo(
          "CSmsDeviceManager::ProcessPendingSmsDevices",
          0x50Cu,
          "Interface %s has CellularVoiceGuid == GUID_NULL",
          v32);
      }
      else
      {
        v33 = *(_OWORD *)((char *)v9 + 28);
        *(_OWORD *)std::map<_GUID,_GUID,CGuidLessCompare,std::allocator<std::pair<_GUID const,_GUID>>>::operator[](
                     (__int64 *)this + 34,
                     (struct WWAN_INTERFACE_OBJECT *)((char *)v107 + 2252)) = v33;
        v34 = GetGuidDisplayStringInternal((const struct _GUID *)((char *)v107 + 2252), qword_18008DC30, 0x40u);
        v35 = GetGuidDisplayStringInternal((const struct _GUID *)((char *)v9 + 28), &byte_18008DA30, 0x200u);
        LogSmsRouterInfo(
          "CSmsDeviceManager::ProcessPendingSmsDevices",
          0x4E1u,
          "Interface %s has CellularVoiceGuid %s",
          v35,
          v34);
        std::_Tree<std::_Tset_traits<_GUID,CGuidLessCompare,std::allocator<_GUID>,0>>::insert<0,0>(
          (__int64 *)Block,
          (__int64)&v117,
          (__int64 *)((char *)v9 + 28));
      }
      v145 = &Windows::Sms::Common::undo_action::`vftable';
      if ( !v147 )
      {
        std::_Xbad_function_call();
        break;
      }
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v147 + 16LL))(v147);
      if ( v147 )
      {
        v36 = v146;
        LOBYTE(v36) = v147 != v146;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v147 + 32LL))(v147, v36);
      }
    }
    else
    {
      InterfaceLuid.InterfaceLuid.Value = 0;
      memset_0(&InterfaceLuid.InterfaceIndex, 0, 0x540u);
      if ( !ConvertInterfaceGuidToLuid((const GUID *)((char *)v9 + 28), &InterfaceLuid.InterfaceLuid) )
        GetIfEntry2(&InterfaceLuid);
      if ( InterfaceLuid.PhysicalMediumType == NdisPhysicalMediumWirelessWan
        || InterfaceLuid.MediaType == NdisMediumWirelessWan
        && InterfaceLuid.PhysicalMediumType == NdisPhysicalMediumUnspecified )
      {
        v14 = GetGuidDisplayStringInternal((const struct _GUID *)((char *)v9 + 28), &byte_18008DA30, 0x200u);
        LogSmsRouterError(
          "CSmsDeviceManager::ProcessPendingSmsDevices",
          0x4BEu,
          v12,
          "GetWwanInterfaceObject failed for Interface with PhysicalMediumType=%d, MediaType=%d, Guid=%s",
          InterfaceLuid.PhysicalMediumType,
          InterfaceLuid.MediaType,
          v14);
      }
      else
      {
        v13 = GetGuidDisplayStringInternal((const struct _GUID *)((char *)v9 + 28), &byte_18008DA30, 0x200u);
        LogSmsRouterInfo(
          "CSmsDeviceManager::ProcessPendingSmsDevices",
          0x4C9u,
          "GetWwanInterfaceObject returned hr=0x%08X for Interface with PhysicalMediumType=%d, MediaType=%d, Guid=%s",
          v12,
          InterfaceLuid.PhysicalMediumType,
          InterfaceLuid.MediaType,
          v13);
      }
      std::_Tree<std::_Tset_traits<_GUID,CGuidLessCompare,std::allocator<_GUID>,0>>::insert<0,0>(
        (__int64 *)Block,
        (__int64)&Buf2,
        (__int64 *)((char *)v9 + 28));
    }
LABEL_48:
    v37 = (__int64 **)v9[2];
    if ( *((_BYTE *)v37 + 25) )
    {
      for ( i = (__int64 *)v9[1]; !*((_BYTE *)i + 25) && v9 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v9 = i;
      v9 = i;
    }
    else
    {
      v9 = (__int64 *)v9[2];
      for ( j = *v37; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v9 = j;
    }
  }
  v40 = *(__int64 **)Block[0];
  while ( !*((_BYTE *)v40 + 25) )
  {
    std::_Tree<std::_Tset_traits<_GUID,CGuidLessCompare,std::allocator<_GUID>,0>>::erase(
      (char *)this + 320,
      (char *)v40 + 28);
    v41 = (__int64 **)v40[2];
    if ( *((_BYTE *)v41 + 25) )
    {
      for ( k = (__int64 *)v40[1]; !*((_BYTE *)k + 25) && v40 == (__int64 *)k[2]; k = (__int64 *)k[1] )
        v40 = k;
      v40 = k;
    }
    else
    {
      v40 = (__int64 *)v40[2];
      for ( m = *v41; !*((_BYTE *)m + 25); m = (__int64 *)*m )
        v40 = m;
    }
  }
  v44 = (__int64 *)**((_QWORD **)this + 36);
  v45 = (char *)this + 168;
  while ( !*((_BYTE *)v44 + 25) )
  {
    v45 = (char *)this + 168;
    v46 = (_QWORD *)v44[4];
    v105 = v46;
    if ( *(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::find(
                      (char *)this + 168,
                      v116,
                      &v105) != *((_QWORD *)this + 22) )
    {
      v105 = v46;
      v47 = *(_QWORD *)(*(_QWORD *)std::_Hash<stdext::_Hmap_traits<ISmsModel *,SmsDeviceInformation,stdext::hash_compare<ISmsModel *,std::less<ISmsModel *>>,std::allocator<std::pair<ISmsModel * const,SmsDeviceInformation>>,0>>::_Try_emplace<ISmsModel *,>(
                                     (__int64)this + 168,
                                     (__int64)v136,
                                     &v105)
                      + 144LL);
      v117 = v47;
      if ( v47 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 8LL))(v47);
        Buf2 = GUID_NULL;
        (*(void (__fastcall **)(__int64, GUID *))(*(_QWORD *)v47 + 24LL))(v47, &Buf2);
        v48 = (struct _GUID *)*((_QWORD *)this + 34);
        v49 = *(struct _GUID **)v48->Data4;
        v50 = v48;
        if ( v49[1].Data4[1] )
        {
          v51 = (__int64 *)((char *)this + 272);
        }
        else
        {
          do
          {
            if ( memcmp_0(&v49[1].Data4[4], &Buf2, 0x10u) >= 0 )
            {
              v50 = v49;
              v49 = *(struct _GUID **)&v49->Data1;
            }
            else
            {
              v49 = *(struct _GUID **)&v49[1].Data1;
            }
          }
          while ( !v49[1].Data4[1] );
          v51 = (__int64 *)((char *)this + 272);
          v48 = (struct _GUID *)*((_QWORD *)this + 34);
        }
        v104 = v48;
        if ( v50[1].Data4[1] || memcmp_0(&Buf2, &v50[1].Data4[4], 0x10u) < 0 )
          v50 = v104;
        if ( v50 != (struct _GUID *)*v51 )
        {
          v52 = (struct _GUID *)std::map<_GUID,_GUID,CGuidLessCompare,std::allocator<std::pair<_GUID const,_GUID>>>::operator[](
                                  v51,
                                  &Buf2);
          v104 = v52;
          if ( *(_QWORD *)std::_Tree<std::_Tmap_traits<_GUID,SmsDeviceInformation,CGuidLessCompare,std::allocator<std::pair<_GUID const,SmsDeviceInformation>>,0>>::find(
                            (char *)this + 256,
                            v118,
                            v52) != *((_QWORD *)this + 32) )
          {
            v141 = 0;
            v142 = 0;
            v143 = 7;
            LOWORD(v141) = 0;
            *(_QWORD *)v106 = 0;
            v109 = 0;
            v53 = (_QWORD *)std::map<_GUID,std::wstring,CGuidLessCompare,std::allocator<std::pair<_GUID const,std::wstring>>>::operator[](
                              (__int64 *)this + 32,
                              v52);
            v54 = v44 + 4;
            v105 = (_QWORD *)v44[4];
            v55 = (_QWORD *)std::_Hash<stdext::_Hmap_traits<ISmsModel *,SmsDeviceInformation,stdext::hash_compare<ISmsModel *,std::less<ISmsModel *>>,std::allocator<std::pair<ISmsModel * const,SmsDeviceInformation>>,0>>::_Try_emplace<ISmsModel *,>(
                              (__int64)this + 168,
                              (__int64)v124,
                              &v105);
            std::wstring::operator=(*v55 + 88LL, v53, v56);
            if ( v53[3] > 7u )
              v53 = (_QWORD *)*v53;
            if ( (int)CSmsDeviceManager::CreateSwDevice(
                        v57,
                        v104,
                        (__int64)v53,
                        (char *)&v141,
                        (__int64 *)v106,
                        (__int64 *)&v109) >= 0 )
            {
              v58 = (_QWORD *)*v54;
              v59 = GetGuidDisplayStringInternal(v104, &byte_18008DA30, 0x200u);
              v60 = (const wchar_t *)&v141;
              if ( v143 > 7 )
                v60 = (const wchar_t *)v141;
              LogSmsRouterInfo(
                "CSmsDeviceManager::ProcessPendingSmsDevices",
                0x531u,
                "Created CellularSmsDevice: %S for Interface %s SmsModel: 0x%08X",
                v60,
                v59,
                (_DWORD)v58);
              v105 = (_QWORD *)*v54;
              v61 = (_QWORD *)std::_Hash<stdext::_Hmap_traits<ISmsModel *,SmsDeviceInformation,stdext::hash_compare<ISmsModel *,std::less<ISmsModel *>>,std::allocator<std::pair<ISmsModel * const,SmsDeviceInformation>>,0>>::_Try_emplace<ISmsModel *,>(
                                (__int64)this + 168,
                                (__int64)v125,
                                &v105);
              std::wstring::operator=(*v61 + 56LL, &v141, v62);
              v105 = (_QWORD *)*v54;
              v63 = std::_Hash<stdext::_Hmap_traits<ISmsModel *,SmsDeviceInformation,stdext::hash_compare<ISmsModel *,std::less<ISmsModel *>>,std::allocator<std::pair<ISmsModel * const,SmsDeviceInformation>>,0>>::_Try_emplace<ISmsModel *,>(
                      (__int64)this + 168,
                      (__int64)v126,
                      &v105);
              *(_QWORD *)(*(_QWORD *)v63 + 136LL) = *(_QWORD *)v106;
              v105 = (_QWORD *)*v54;
              v64 = *(_QWORD *)std::_Hash<stdext::_Hmap_traits<ISmsModel *,SmsDeviceInformation,stdext::hash_compare<ISmsModel *,std::less<ISmsModel *>>,std::allocator<std::pair<ISmsModel * const,SmsDeviceInformation>>,0>>::_Try_emplace<ISmsModel *,>(
                                 (__int64)this + 168,
                                 (__int64)v127,
                                 &v105);
              v65 = operator new(0x10u);
              v119 = v65;
              v66 = v109;
              *v65 = &AutoSwDeviceHandle::`vftable';
              v65[1] = v66;
              LogSmsRouterInfo("AutoSwDeviceHandle::Reset", 0x7Au, "HSWDEVICE 0x%08X added", (_DWORD)v66);
              std::shared_ptr<AutoSwDeviceHandle>::reset<AutoSwDeviceHandle,0>(v64 + 160, v65);
              LODWORD(v65) = *((_DWORD *)v107 + 569);
              v115 = v44[4];
              *(_DWORD *)(*(_QWORD *)std::_Hash<stdext::_Hmap_traits<ISmsModel *,SmsDeviceInformation,stdext::hash_compare<ISmsModel *,std::less<ISmsModel *>>,std::allocator<std::pair<ISmsModel * const,SmsDeviceInformation>>,0>>::_Try_emplace<ISmsModel *,>(
                                       (__int64)this + 168,
                                       (__int64)v128,
                                       &v115)
                        + 176LL) = (_DWORD)v65;
              v104 = (struct _GUID *)v44[4];
              v105 = *(_QWORD **)std::_Hash<stdext::_Hmap_traits<ISmsModel *,SmsDeviceInformation,stdext::hash_compare<ISmsModel *,std::less<ISmsModel *>>,std::allocator<std::pair<ISmsModel * const,SmsDeviceInformation>>,0>>::_Try_emplace<ISmsModel *,>(
                                   (__int64)this + 168,
                                   (__int64)v129,
                                   &v104);
              v111 = (CCellularSmsDevice *)operator new(0x3F8u);
              v106[0] = *(_DWORD *)(*(_QWORD *)std::_Hash<stdext::_Hmap_traits<ISmsModel *,SmsDeviceInformation,stdext::hash_compare<ISmsModel *,std::less<ISmsModel *>>,std::allocator<std::pair<ISmsModel * const,SmsDeviceInformation>>,0>>::_Try_emplace<ISmsModel *,>(
                                                 (__int64)this + 168,
                                                 (__int64)v130,
                                                 &v104)
                                  + 176LL);
              v110 = (struct _WNF_STATE_NAME *)(*(_QWORD *)std::_Hash<stdext::_Hmap_traits<ISmsModel *,SmsDeviceInformation,stdext::hash_compare<ISmsModel *,std::less<ISmsModel *>>,std::allocator<std::pair<ISmsModel * const,SmsDeviceInformation>>,0>>::_Try_emplace<ISmsModel *,>(
                                                             (__int64)this + 168,
                                                             (__int64)v131,
                                                             &v104)
                                              + 136LL);
              v67 = *(_QWORD *)std::_Hash<stdext::_Hmap_traits<ISmsModel *,SmsDeviceInformation,stdext::hash_compare<ISmsModel *,std::less<ISmsModel *>>,std::allocator<std::pair<ISmsModel * const,SmsDeviceInformation>>,0>>::_Try_emplace<ISmsModel *,>(
                                 (__int64)this + 168,
                                 (__int64)v132,
                                 &v104)
                  + 88LL;
              v109 = (unsigned __int16 *)v67;
              if ( *(_QWORD *)(v67 + 24) > 7u )
                v109 = *(unsigned __int16 **)v67;
              v68 = std::_Hash<stdext::_Hmap_traits<ISmsModel *,SmsDeviceInformation,stdext::hash_compare<ISmsModel *,std::less<ISmsModel *>>,std::allocator<std::pair<ISmsModel * const,SmsDeviceInformation>>,0>>::_Try_emplace<ISmsModel *,>(
                      (__int64)this + 168,
                      (__int64)v133,
                      &v104);
              v69 = (const unsigned __int16 *)(*(_QWORD *)v68 + 56LL);
              if ( *(_QWORD *)(*(_QWORD *)v68 + 80LL) > 7u )
                v69 = *(const unsigned __int16 **)v69;
              v70 = std::_Hash<stdext::_Hmap_traits<ISmsModel *,SmsDeviceInformation,stdext::hash_compare<ISmsModel *,std::less<ISmsModel *>>,std::allocator<std::pair<ISmsModel * const,SmsDeviceInformation>>,0>>::_Try_emplace<ISmsModel *,>(
                      (__int64)this + 168,
                      (__int64)v134,
                      &v104);
              v71 = CCellularSmsDevice::CCellularSmsDevice(
                      v111,
                      (struct ISmsModel *)v104,
                      *(struct ICan **)(*(_QWORD *)v70 + 144LL),
                      v69,
                      v109,
                      v110,
                      v106[0]);
              v72 = v105;
              v73 = v105[19];
              if ( v73 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
                v72 = v105;
              }
              v72[19] = v71;
              std::_Tree<std::_Tset_traits<ATL::CComPtr<ISmsModel>,std::less<ATL::CComPtr<ISmsModel>>,std::allocator<ATL::CComPtr<ISmsModel>>,0>>::insert<0,0>(
                (__int64 *)v114,
                (__int64)v135,
                v44 + 4);
              v110 = (struct _WNF_STATE_NAME *)v44[4];
              v74 = std::_Hash<stdext::_Hmap_traits<ISmsModel *,SmsDeviceInformation,stdext::hash_compare<ISmsModel *,std::less<ISmsModel *>>,std::allocator<std::pair<ISmsModel * const,SmsDeviceInformation>>,0>>::_Try_emplace<ISmsModel *,>(
                      (__int64)this + 168,
                      (__int64)v120,
                      &v110);
              std::_Tree<std::_Tset_traits<ATL::CComPtr<ISmsModel>,std::less<ATL::CComPtr<ISmsModel>>,std::allocator<ATL::CComPtr<ISmsModel>>,0>>::insert<0,0>(
                (__int64 *)v113,
                (__int64)v123,
                (__int64 *)(*(_QWORD *)v74 + 152LL));
            }
            std::wstring::~wstring((char **)&v141);
          }
        }
      }
      if ( v47 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    }
    v75 = (__int64 **)v44[2];
    if ( *((_BYTE *)v75 + 25) )
    {
      for ( n = (__int64 *)v44[1]; !*((_BYTE *)n + 25) && v44 == (__int64 *)n[2]; n = (__int64 *)n[1] )
        v44 = n;
      v44 = n;
    }
    else
    {
      v44 = (__int64 *)v44[2];
      for ( ii = *v75; !*((_BYTE *)ii + 25); ii = (__int64 *)*ii )
        v44 = ii;
    }
  }
  v78 = *(__int64 **)v114[0];
  while ( !*((_BYTE *)v78 + 25) )
  {
    v111 = (CCellularSmsDevice *)v78[4];
    if ( *(_QWORD *)(*(_QWORD *)std::_Hash<stdext::_Hmap_traits<ISmsModel *,SmsDeviceInformation,stdext::hash_compare<ISmsModel *,std::less<ISmsModel *>>,std::allocator<std::pair<ISmsModel * const,SmsDeviceInformation>>,0>>::_Try_emplace<ISmsModel *,>(
                                  (__int64)v45,
                                  (__int64)v123,
                                  &v111)
                   + 152LL) )
    {
      std::_Tree<std::_Tset_traits<ATL::CComPtr<ISmsModel>,std::less<ATL::CComPtr<ISmsModel>>,std::allocator<ATL::CComPtr<ISmsModel>>,0>>::erase(
        (char *)this + 288,
        v78 + 4);
      std::_Tree<std::_Tset_traits<ATL::CComPtr<ISmsModel>,std::less<ATL::CComPtr<ISmsModel>>,std::allocator<ATL::CComPtr<ISmsModel>>,0>>::insert<0,0>(
        (__int64 *)this + 19,
        (__int64)v120,
        v78 + 4);
    }
    v79 = (__int64 **)v78[2];
    if ( *((_BYTE *)v79 + 25) )
    {
      for ( jj = (__int64 *)v78[1]; !*((_BYTE *)jj + 25) && v78 == (__int64 *)jj[2]; jj = (__int64 *)jj[1] )
        v78 = jj;
      v78 = jj;
    }
    else
    {
      v78 = (__int64 *)v78[2];
      for ( kk = *v79; !*((_BYTE *)kk + 25); kk = (__int64 *)*kk )
        v78 = kk;
    }
    v45 = (char *)this + 168;
  }
  LogSmsRouterInfo(
    "CSmsDeviceManager::ProcessPendingSmsDevices",
    0x552u,
    "Pending interface guids (%d). Pending sms models (%d)",
    *((_DWORD *)this + 82),
    *((_DWORD *)this + 74));
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 12) + 8LL))((char *)this + 96);
  v82 = *(__int64 **)v113[0];
  while ( !*((_BYTE *)v82 + 25) )
  {
    v83 = *(__int64 **)v112[0];
    while ( !*((_BYTE *)v83 + 25) )
    {
      v84 = v83[4];
      if ( v84 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v84 + 24LL))(v84, v82[4]);
      v85 = (__int64 **)v83[2];
      if ( *((_BYTE *)v85 + 25) )
      {
        for ( mm = (__int64 *)v83[1]; !*((_BYTE *)mm + 25) && v83 == (__int64 *)mm[2]; mm = (__int64 *)mm[1] )
          v83 = mm;
        v83 = mm;
      }
      else
      {
        v83 = (__int64 *)v83[2];
        for ( nn = *v85; !*((_BYTE *)nn + 25); nn = (__int64 *)*nn )
          v83 = nn;
      }
    }
    v88 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v82[4] + 24LL))(v82[4]);
    if ( v88 )
    {
      LogSmsRouterError(
        "CSmsDeviceManager::ProcessPendingSmsDevices",
        0x566u,
        v88,
        "Failed to initialize SmsDevice 0x%08X.",
        v82[4]);
      v89 = *(__int64 **)v112[0];
      while ( !*((_BYTE *)v89 + 25) )
      {
        v90 = v89[4];
        if ( v90 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v90 + 32LL))(v90, v82[4]);
        v91 = (__int64 **)v89[2];
        if ( *((_BYTE *)v91 + 25) )
        {
          for ( i1 = (__int64 *)v89[1]; !*((_BYTE *)i1 + 25) && v89 == (__int64 *)i1[2]; i1 = (__int64 *)i1[1] )
            v89 = i1;
          v89 = i1;
        }
        else
        {
          v89 = (__int64 *)v89[2];
          for ( i2 = *v91; !*((_BYTE *)i2 + 25); i2 = (__int64 *)*i2 )
            v89 = i2;
        }
      }
    }
    if ( !*((_QWORD *)this + 9) )
    {
      v94 = (void (__fastcall ***)(_QWORD, GUID *, struct _GUID **))v82[4];
      v95 = 0;
      v104 = 0;
      if ( v94 )
      {
        (**v94)(v94, &GUID_db316d16_3b15_4980_9706_f50ff46e702e, &v104);
        v95 = v104;
      }
      if ( v95 )
      {
        LogSmsRouterInfo(
          "CSmsDeviceManager::ProcessPendingSmsDevices",
          0x575u,
          "Start processing text messages for SmsDevice 0x%08X.",
          (_DWORD)v95);
        (*(void (__fastcall **)(struct _GUID *))(*(_QWORD *)&v104->Data1 + 152LL))(v104);
        v95 = v104;
      }
      if ( v95 )
        (*(void (__fastcall **)(struct _GUID *))(*(_QWORD *)&v95->Data1 + 16LL))(v95);
    }
    if ( !*((_QWORD *)this + 10) )
    {
      v96 = (void (__fastcall ***)(_QWORD, GUID *, struct _GUID **))v82[4];
      v97 = 0;
      v104 = 0;
      if ( v96 )
      {
        (**v96)(v96, &GUID_db316d16_3b15_4980_9706_f50ff46e702e, &v104);
        v97 = v104;
      }
      if ( v97 )
      {
        LogSmsRouterInfo(
          "CSmsDeviceManager::ProcessPendingSmsDevices",
          0x57Fu,
          "Start processing wap messages for SmsDevice 0x%08X.",
          (_DWORD)v97);
        (*(void (__fastcall **)(struct _GUID *))(*(_QWORD *)&v104->Data1 + 160LL))(v104);
        v97 = v104;
      }
      if ( v97 )
        (*(void (__fastcall **)(struct _GUID *))(*(_QWORD *)&v97->Data1 + 16LL))(v97);
    }
    v98 = (__int64 **)v82[2];
    if ( *((_BYTE *)v98 + 25) )
    {
      for ( i3 = (__int64 *)v82[1]; !*((_BYTE *)i3 + 25) && v82 == (__int64 *)i3[2]; i3 = (__int64 *)i3[1] )
        v82 = i3;
      v82 = i3;
    }
    else
    {
      v82 = (__int64 *)v82[2];
      for ( i4 = *v98; !*((_BYTE *)i4 + 25); i4 = (__int64 *)*i4 )
        v82 = i4;
    }
  }
  v6 = Block[0];
  v101 = (_QWORD *)*((_QWORD *)Block[0] + 1);
  if ( !*((_BYTE *)v101 + 25) )
  {
    do
    {
      std::_Tree_val<std::_Tree_simple_types<_GUID>>::_Erase_tree<std::allocator<std::_Tree_node<_GUID,void *>>>(
        Block,
        Block,
        v101[2]);
      v102 = v101;
      v101 = (_QWORD *)*v101;
      operator delete(v102);
    }
    while ( !*((_BYTE *)v101 + 25) );
    v6 = Block[0];
  }
LABEL_178:
  operator delete(v6);
  std::_Tree<std::_Tset_traits<ATL::CComPtr<ISmsDevice>,std::less<ATL::CComPtr<ISmsDevice>>,std::allocator<ATL::CComPtr<ISmsDevice>>,0>>::~_Tree<std::_Tset_traits<ATL::CComPtr<ISmsDevice>,std::less<ATL::CComPtr<ISmsDevice>>,std::allocator<ATL::CComPtr<ISmsDevice>>,0>>(v114);
  std::_Tree<std::_Tset_traits<ATL::CComPtr<ISmsDevice>,std::less<ATL::CComPtr<ISmsDevice>>,std::allocator<ATL::CComPtr<ISmsDevice>>,0>>::~_Tree<std::_Tset_traits<ATL::CComPtr<ISmsDevice>,std::less<ATL::CComPtr<ISmsDevice>>,std::allocator<ATL::CComPtr<ISmsDevice>>,0>>(v112);
  std::_Tree<std::_Tset_traits<ATL::CComPtr<ISmsDevice>,std::less<ATL::CComPtr<ISmsDevice>>,std::allocator<ATL::CComPtr<ISmsDevice>>,0>>::~_Tree<std::_Tset_traits<ATL::CComPtr<ISmsDevice>,std::less<ATL::CComPtr<ISmsDevice>>,std::allocator<ATL::CComPtr<ISmsDevice>>,0>>(v113);
  return 0;
}

```

## disassembly

```asm
0x18004099c  mov     rax, rsp
0x18004099f  push    rbp
0x1800409a0  push    rbx
0x1800409a1  push    rsi
0x1800409a2  push    rdi
0x1800409a3  push    r12
0x1800409a5  push    r13
0x1800409a7  push    r14
0x1800409a9  push    r15
0x1800409ab  lea     rbp, [rax-778h]
0x1800409b2  sub     rsp, 838h
0x1800409b9  movaps  xmmword ptr [rax-58h], xmm6
0x1800409bd  mov     rax, cs:__security_cookie
0x1800409c4  xor     rax, rsp
0x1800409c7  mov     [rbp+770h+var_60], rax
0x1800409ce  mov     r15, rcx
0x1800409d1  xor     esi, esi
0x1800409d3  mov     [rbp+770h+var_7D8], rsi
0x1800409d7  mov     [rbp+770h+var_7D0], rsi
0x1800409db  lea     ebx, [rsi+28h]
0x1800409de  mov     ecx, ebx; Size
0x1800409e0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800409e5  mov     [rax], rax
0x1800409e8  mov     [rax+8], rax
0x1800409ec  mov     [rax+10h], rax
0x1800409f0  mov     word ptr [rax+18h], 101h
0x1800409f6  mov     [rbp+770h+var_7D8], rax
0x1800409fa  mov     [rbp+770h+var_7E8], rsi
0x1800409fe  mov     [rbp+770h+var_7E0], rsi
0x180040a02  mov     ecx, ebx; Size
0x180040a04  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180040a09  mov     [rax], rax
0x180040a0c  mov     [rax+8], rax
0x180040a10  mov     [rax+10h], rax
0x180040a14  mov     word ptr [rax+18h], 101h
0x180040a1a  mov     [rbp+770h+var_7E8], rax
0x180040a1e  mov     [rsp+870h+var_818], rsi
0x180040a23  mov     [rbp+770h+var_7C8], rsi
0x180040a27  mov     [rbp+770h+var_7C0], rsi
0x180040a2b  mov     ecx, ebx; Size
0x180040a2d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180040a32  mov     [rax], rax
0x180040a35  mov     [rax+8], rax
0x180040a39  mov     [rax+10h], rax
0x180040a3d  mov     word ptr [rax+18h], 101h
0x180040a43  mov     [rbp+770h+var_7C8], rax
0x180040a47  mov     [rsp+870h+Block], rsi
0x180040a4c  mov     [rsp+870h+var_808], rsi
0x180040a51  lea     r14d, [rsi+30h]
0x180040a55  mov     ecx, r14d; Size
0x180040a58  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180040a5d  mov     [rax], rax
0x180040a60  mov     [rax+8], rax
0x180040a64  mov     [rax+10h], rax
0x180040a68  mov     word ptr [rax+18h], 101h
0x180040a6e  mov     [rsp+870h+Block], rax
0x180040a73  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x180040a7a  mov     [rbp+770h+var_768], rax
0x180040a7e  lea     rdi, [r15+60h]
0x180040a82  mov     [rbp+770h+var_760], rdi
0x180040a86  mov     rax, [rdi]
0x180040a89  mov     rcx, rdi
0x180040a8c  mov     rax, [rax]
0x180040a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040a94  nop
0x180040a95  cmp     [r15+24h], esi
0x180040a99  jnz     short loc_180040B0E
0x180040a9b  mov     r9d, [r15+148h]
0x180040aa2  lea     r8, aSkippingProces; "Skipping processing of pending interfac"...
0x180040aa9  mov     edx, 4A5h; unsigned int
0x180040aae  lea     rcx, aCsmsdevicemana_17; "CSmsDeviceManager::ProcessPendingSmsDev"...
0x180040ab5  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180040aba  nop
0x180040abb  mov     rax, [rdi]
0x180040abe  mov     rcx, rdi
0x180040ac1  mov     rax, [rax+8]
0x180040ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040aca  nop
0x180040acb  mov     rcx, [rsp+870h+Block]
0x180040ad0  mov     rbx, [rcx+8]
0x180040ad4  cmp     [rbx+19h], sil
0x180040ad8  jnz     short loc_180040B06
0x180040ada  mov     r8, [rbx+10h]
0x180040ade  lea     rdx, [rsp+870h+Block]
0x180040ae3  lea     rcx, [rsp+870h+Block]
0x180040ae8  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U_GUID@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U_GUID@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U_GUID@@PEAX@std@@@1@PEAU?$_Tree_node@U_GUID@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<_GUID>>::_Erase_tree<std::allocator<std::_Tree_node<_GUID,void *>>>(std::allocator<std::_Tree_node<_GUID,void *>> &,std::_Tree_node<_GUID,void *> *)
0x180040aed  mov     rcx, rbx; Block
0x180040af0  mov     rbx, [rbx]
0x180040af3  mov     rdx, r14
0x180040af6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180040afb  cmp     [rbx+19h], sil
0x180040aff  jz      short loc_180040ADA
0x180040b01  mov     rcx, [rsp+870h+Block]
0x180040b06  mov     rdx, r14
0x180040b09  jmp     loc_180041A52
0x180040b0e  lea     rdx, [r15+0E8h]
0x180040b15  lea     rcx, [rbp+770h+var_7E8]
0x180040b19  call    ??4?$set@V?$CComPtr@UISmsDeviceChangeReceiver@@@ATL@@U?$less@V?$CComPtr@UISmsDeviceChangeReceiver@@@ATL@@@std@@V?$allocator@V?$CComPtr@UISmsDeviceChangeReceiver@@@ATL@@@4@@std@@QEAAAEAV01@AEBV01@@Z; std::set<ATL::CComPtr<ISmsDeviceChangeReceiver>>::operator=(std::set<ATL::CComPtr<ISmsDeviceChangeReceiver>> const &)
0x180040b1e  mov     rbx, [r15+140h]
0x180040b25  mov     rbx, [rbx]
0x180040b28  lea     r13, aCsmsdevicemana_17; "CSmsDeviceManager::ProcessPendingSmsDev"...
0x180040b2f  xor     edi, edi
0x180040b31  cmp     [rbx+19h], dil
0x180040b35  jnz     loc_180041100
0x180040b3b  lea     r14, [rbx+1Ch]
0x180040b3f  lea     rsi, [r15+100h]
0x180040b46  mov     r8, r14
0x180040b49  lea     rdx, [rbp+770h+var_7F0]
0x180040b4d  mov     rcx, rsi
0x180040b50  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@USmsDeviceInformation@@VCGuidLessCompare@@V?$allocator@U?$pair@$$CBU_GUID@@USmsDeviceInformation@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@USmsDeviceInformation@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,SmsDeviceInformation,CGuidLessCompare,std::allocator<std::pair<_GUID const,SmsDeviceInformation>>,0>>::find(_GUID const &)
0x180040b55  mov     rcx, [rsi]
0x180040b58  cmp     [rax], rcx
0x180040b5b  jz      loc_1800410AA
0x180040b61  mov     [rsp+870h+var_818], rdi
0x180040b66  mov     [rsp+870h+var_830], rdi
0x180040b6b  mov     [rsp+870h+var_820], edi
0x180040b6f  mov     rcx, [r15+30h]
0x180040b73  test    rcx, rcx
0x180040b76  jz      short loc_180040BF2
0x180040b78  mov     [rsp+870h+var_838], rdi
0x180040b7d  mov     qword ptr [rsp+870h+var_840], rdi
0x180040b82  lea     rax, [rsp+870h+var_830]
0x180040b87  mov     [rsp+870h+var_848], rax
0x180040b8c  lea     rax, [rsp+870h+var_820]
0x180040b91  mov     [rsp+870h+var_850], rax
0x180040b96  xor     r9d, r9d
0x180040b99  lea     r8d, [r9+7]
0x180040b9d  mov     rdx, r14
0x180040ba0  call    cs:__imp_WwanQueryInterface
0x180040ba6  mov     edi, eax
0x180040ba8  test    eax, eax
0x180040baa  jz      short loc_180040BB0
0x180040bac  jle     short loc_180040C00
0x180040bae  jmp     short loc_180040BF7
0x180040bb0  cmp     [rsp+870h+var_820], 8E8h
0x180040bb8  jb      short loc_180040BCD
0x180040bba  mov     rax, [rsp+870h+var_830]
0x180040bbf  test    rax, rax
0x180040bc2  jz      short loc_180040BCD
0x180040bc4  mov     [rsp+870h+var_818], rax
0x180040bc9  xor     edi, edi
0x180040bcb  jmp     short loc_180040C1B
0x180040bcd  lea     r9, aWwanInterfaceO; "WWAN_INTERFACE_OBJECT size"
0x180040bd4  mov     edx, 1A1h; unsigned int
0x180040bd9  mov     r8d, 8000FFFFh; int
0x180040bdf  lea     rcx, aCsmsdevicemana_2; "CSmsDeviceManager::GetWwanInterfaceObje"...
0x180040be6  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180040beb  mov     edi, 8000FFFFh
0x180040bf0  jmp     short loc_180040C1B
0x180040bf2  mov     edi, 15h
0x180040bf7  movzx   edi, di
0x180040bfa  or      edi, 80070000h
0x180040c00  lea     r9, aWwanqueryinter_0; "WwanQueryInterface failed"
0x180040c07  mov     r8d, edi; int
0x180040c0a  mov     edx, 19Ah; unsigned int
0x180040c0f  lea     rcx, aCsmsdevicemana_2; "CSmsDeviceManager::GetWwanInterfaceObje"...
0x180040c16  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180040c1b  test    edi, edi
0x180040c1d  jns     loc_180040D22
0x180040c23  mov     qword ptr [rbp+770h+InterfaceLuid], 0
0x180040c2e  xor     edx, edx; Val
0x180040c30  mov     r8d, 540h; Size
0x180040c36  lea     rcx, [rbp+770h+var_5A8]; void *
0x180040c3d  call    memset_0
0x180040c42  lea     rdx, [rbp+770h+InterfaceLuid]; InterfaceLuid
0x180040c49  mov     rcx, r14; InterfaceGuid
0x180040c4c  call    cs:__imp_ConvertInterfaceGuidToLuid
0x180040c52  test    eax, eax
0x180040c54  jnz     short loc_180040C63
0x180040c56  lea     rcx, [rbp+770h+InterfaceLuid]; Row
0x180040c5d  call    cs:__imp_GetIfEntry2
0x180040c63  mov     eax, [rbp+770h+var_13C]
0x180040c69  cmp     eax, 8
0x180040c6c  jz      short loc_180040CC2
0x180040c6e  cmp     [rbp+770h+var_140], 9
0x180040c75  jnz     short loc_180040C7B
0x180040c77  test    eax, eax
0x180040c79  jz      short loc_180040CC2
0x180040c7b  mov     r8d, 200h; unsigned __int64
0x180040c81  lea     rdx, byte_18008DA30; char *
0x180040c88  mov     rcx, r14; struct _GUID *
0x180040c8b  call    ?GetGuidDisplayStringInternal@@YAPEBDPEBU_GUID@@PEAD_K@Z; GetGuidDisplayStringInternal(_GUID const *,char *,unsigned __int64)
0x180040c90  mov     qword ptr [rsp+870h+var_840], rax
0x180040c95  mov     eax, [rbp+770h+var_140]
0x180040c9b  mov     dword ptr [rsp+870h+var_848], eax
0x180040c9f  mov     eax, [rbp+770h+var_13C]
0x180040ca5  mov     dword ptr [rsp+870h+var_850], eax
0x180040ca9  mov     r9d, edi
0x180040cac  lea     r8, aGetwwaninterfa; "GetWwanInterfaceObject returned hr=0x%0"...
0x180040cb3  mov     edx, 4C9h; unsigned int
0x180040cb8  mov     rcx, r13; char *
0x180040cbb  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180040cc0  jmp     short loc_180040D07
0x180040cc2  mov     r8d, 200h; unsigned __int64
0x180040cc8  lea     rdx, byte_18008DA30; char *
0x180040ccf  mov     rcx, r14; struct _GUID *
0x180040cd2  call    ?GetGuidDisplayStringInternal@@YAPEBDPEBU_GUID@@PEAD_K@Z; GetGuidDisplayStringInternal(_GUID const *,char *,unsigned __int64)
0x180040cd7  mov     qword ptr [rsp+870h+var_840], rax
0x180040cdc  mov     eax, [rbp+770h+var_140]
0x180040ce2  mov     dword ptr [rsp+870h+var_848], eax
0x180040ce6  mov     eax, [rbp+770h+var_13C]
0x180040cec  mov     dword ptr [rsp+870h+var_850], eax
0x180040cf0  lea     r9, aGetwwaninterfa_0; "GetWwanInterfaceObject failed for Inter"...
0x180040cf7  mov     r8d, edi; int
0x180040cfa  mov     edx, 4BEh; unsigned int
0x180040cff  mov     rcx, r13; char *
0x180040d02  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180040d07  mov     r8, r14
0x180040d0a  lea     rdx, [rbp+770h+Buf2]
0x180040d11  lea     rcx, [rsp+870h+Block]
0x180040d16  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@U_GUID@@VCGuidLessCompare@@V?$allocator@U_GUID@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U_GUID@@@std@@@std@@@std@@_N@1@AEBU_GUID@@@Z; std::_Tree<std::_Tset_traits<_GUID,CGuidLessCompare,std::allocator<_GUID>,0>>::insert<0,0>(_GUID const &)
0x180040d1b  xor     edi, edi
0x180040d1d  jmp     loc_1800410AA
0x180040d22  lea     rax, off_1800704F8
0x180040d29  mov     qword ptr [rbp+770h+var_648], rax
0x180040d30  lea     rax, [rsp+870h+var_818]
0x180040d35  mov     qword ptr [rbp+770h+var_648+8], rax
0x180040d3c  lea     rax, [rbp+770h+var_648]
0x180040d43  mov     [rbp+770h+var_610], rax
0x180040d4a  lea     rdx, [rbp+770h+var_648]
0x180040d51  lea     rcx, [rbp+770h+var_600]
0x180040d58  call    ??0undo_action@Common@Sms@Windows@@QEAA@V?$function@$$A6AXXZ@std@@@Z; Windows::Sms::Common::undo_action::undo_action(std::function<void (void)>)
0x180040d5d  nop
0x180040d5e  mov     rdi, [rsp+870h+var_818]
0x180040d63  lea     rdx, [rdi+8CCh]
0x180040d6a  mov     rax, [rdx]
0x180040d6d  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180040d74  jnz     loc_180040FE0
0x180040d7a  mov     rax, [rdx+8]
0x180040d7e  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180040d85  jnz     loc_180040FE0
0x180040d8b  lea     r12, [r15+130h]
0x180040d92  mov     r8, r14
0x180040d95  lea     rdx, [rbp+770h+var_7B8]
0x180040d99  mov     rcx, r12
0x180040d9c  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@USmsDeviceInformation@@VCGuidLessCompare@@V?$allocator@U?$pair@$$CBU_GUID@@USmsDeviceInformation@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@USmsDeviceInformation@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,SmsDeviceInformation,CGuidLessCompare,std::allocator<std::pair<_GUID const,SmsDeviceInformation>>,0>>::find(_GUID const &)
0x180040da1  mov     rcx, [r12]
0x180040da5  cmp     [rax], rcx
0x180040da8  jnz     loc_180040FA1
0x180040dae  xor     ecx, ecx
0x180040db0  cmp     [rdi+284h], ecx
0x180040db6  jz      loc_180040F75
0x180040dbc  xorps   xmm0, xmm0
0x180040dbf  movups  [rbp+770h+var_668], xmm0
0x180040dc6  mov     [rbp+770h+var_658], rcx
0x180040dcd  mov     [rbp+770h+var_650], 7
0x180040dd8  mov     word ptr [rbp+770h+var_668], cx
0x180040ddf  mov     [rsp+870h+var_830], rcx
0x180040de4  mov     qword ptr [rsp+870h+var_820], rcx
0x180040de9  mov     rdx, r14
0x180040dec  mov     rcx, rsi
0x180040def  call    ??A?$map@U_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCGuidLessCompare@@V?$allocator@U?$pair@$$CBU_GUID@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@3@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBU_GUID@@@Z; std::map<_GUID,std::wstring,CGuidLessCompare,std::allocator<std::pair<_GUID const,std::wstring>>>::operator[](_GUID const &)
0x180040df4  mov     rdi, rax
0x180040df7  cmp     qword ptr [rax+18h], 7
0x180040dfc  jbe     short loc_180040E03
0x180040dfe  mov     r8, [rax]
0x180040e01  jmp     short loc_180040E06
0x180040e03  mov     r8, rdi
0x180040e06  lea     rax, [rsp+870h+var_820]
0x180040e0b  mov     [rsp+870h+var_848], rax
0x180040e10  lea     rax, [rsp+870h+var_830]
0x180040e15  mov     [rsp+870h+var_850], rax
0x180040e1a  lea     r9, [rbp+770h+var_668]
0x180040e21  mov     rdx, r14
0x180040e24  call    ?CreateSwDevice@CSmsDeviceManager@@AEAAJAEBU_GUID@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAU_WNF_STATE_NAME@@PEAPEAUHSWDEVICE__@@@Z; CSmsDeviceManager::CreateSwDevice(_GUID const &,ushort const *,std::wstring &,_WNF_STATE_NAME *,HSWDEVICE__ * *)
0x180040e29  test    eax, eax
0x180040e2b  js      loc_180040F67
0x180040e31  mov     r8d, 200h; unsigned __int64
0x180040e37  lea     rdx, byte_18008DA30; char *
0x180040e3e  mov     rcx, r14; struct _GUID *
0x180040e41  call    ?GetGuidDisplayStringInternal@@YAPEBDPEBU_GUID@@PEAD_K@Z; GetGuidDisplayStringInternal(_GUID const *,char *,unsigned __int64)
0x180040e46  lea     r9, [rbp+770h+var_668]
0x180040e4d  cmp     [rbp+770h+var_650], 7
0x180040e55  cmova   r9, qword ptr [rbp+770h+var_668]
0x180040e5d  mov     [rsp+870h+var_850], rax
0x180040e62  lea     r8, aCreatedWwansms; "Created WwanSmsDevice: %S for Interface"...
0x180040e69  mov     edx, 4F5h; unsigned int
0x180040e6e  mov     rcx, r13; char *
0x180040e71  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180040e76  mov     rdx, r14
0x180040e79  mov     rcx, r12
0x180040e7c  call    ??A?$map@U_GUID@@USmsDeviceInformation@@VCGuidLessCompare@@V?$allocator@U?$pair@$$CBU_GUID@@USmsDeviceInformation@@@std@@@std@@@std@@QEAAAEAUSmsDeviceInformation@@AEBU_GUID@@@Z; std::map<_GUID,SmsDeviceInformation,CGuidLessCompare,std::allocator<std::pair<_GUID const,SmsDeviceInformation>>>::operator[](_GUID const &)
0x180040e81  lea     rcx, [rax+40h]
0x180040e85  mov     rdx, rdi
0x180040e88  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180040e8d  mov     rdx, r14
0x180040e90  mov     rcx, r12
0x180040e93  call    ??A?$map@U_GUID@@USmsDeviceInformation@@VCGuidLessCompare@@V?$allocator@U?$pair@$$CBU_GUID@@USmsDeviceInformation@@@std@@@std@@@std@@QEAAAEAUSmsDeviceInformation@@AEBU_GUID@@@Z; std::map<_GUID,SmsDeviceInformation,CGuidLessCompare,std::allocator<std::pair<_GUID const,SmsDeviceInformation>>>::operator[](_GUID const &)
0x180040e98  lea     rcx, [rax+20h]
0x180040e9c  lea     rdx, [rbp+770h+var_668]
0x180040ea3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180040ea8  mov     rdx, r14
0x180040eab  mov     rcx, r12
0x180040eae  call    ??A?$map@U_GUID@@USmsDeviceInformation@@VCGuidLessCompare@@V?$allocator@U?$pair@$$CBU_GUID@@USmsDeviceInformation@@@std@@@std@@@std@@QEAAAEAUSmsDeviceInformation@@AEBU_GUID@@@Z; std::map<_GUID,SmsDeviceInformation,CGuidLessCompare,std::allocator<std::pair<_GUID const,SmsDeviceInformation>>>::operator[](_GUID const &)
0x180040eb3  mov     rcx, [rsp+870h+var_830]
0x180040eb8  mov     [rax+70h], rcx
0x180040ebc  mov     rdx, r14
0x180040ebf  mov     rcx, r12
0x180040ec2  call    ??A?$map@U_GUID@@USmsDeviceInformation@@VCGuidLessCompare@@V?$allocator@U?$pair@$$CBU_GUID@@USmsDeviceInformation@@@std@@@std@@@std@@QEAAAEAUSmsDeviceInformation@@AEBU_GUID@@@Z; std::map<_GUID,SmsDeviceInformation,CGuidLessCompare,std::allocator<std::pair<_GUID const,SmsDeviceInformation>>>::operator[](_GUID const &)
0x180040ec7  lea     rsi, [rax+88h]
  ... truncated ...
```
