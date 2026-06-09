# WindowsPerformanceRecorder::CETWProperties::AddHardwareCounters(WindowsPerformanceRecorder::CHardwareCounterElement const *,WindowsPerformanceRecorder::CControlManager *)

- ea: `0x18001656c`
- end: `0x180016e53`
- name: `?AddHardwareCounters@CETWProperties@WindowsPerformanceRecorder@@AEAAJPEBVCHardwareCounterElement@2@PEAVCControlManager@2@@Z`
- size: `2279`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CETWProperties *__hidden this, const struct WindowsPerformanceRecorder::CHardwareCounterElement *, struct WindowsPerformanceRecorder::CControlManager *)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18003d11c`

## callees

- `0x1800024d0`
- `0x18000a0f0`
- `0x180015e2c`
- `0x18001656c`
- `0x180016e5c`
- `0x180016f08`
- `0x180017d70`
- `0x180017dd8`
- `0x180018d08`
- `0x18001e6e0`
- `0x180035084`
- `0x180039de4`
- `0x180041cf0`
- `0x180044230`
- `0x180049320`
- `0x180064be8`
- `0x18008c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800167b7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016a6b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016a89`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016aa7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016ac5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016ae3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016b01`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016b20`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016b3c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016b57`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016b72`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016b8e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016cc0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016cf0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016d1e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800167b7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016a6b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016a89`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016aa7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016ac5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016ae3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016b01`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016b20`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016b3c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016b57`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016b72`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016b8e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016cc0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016cf0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180016d1e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800167e1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800167e1`

## string_xrefs

- `0x1800165ef`: `COMGUARD`

## pseudocode

```c
__int64 __fastcall WindowsPerformanceRecorder::CETWProperties::AddHardwareCounters(
        WindowsPerformanceRecorder::CETWProperties *this,
        const struct WindowsPerformanceRecorder::CHardwareCounterElement *a2,
        struct WindowsPerformanceRecorder::CControlManager *a3)
{
  signed int v6; // ebx
  __int64 v8; // rax
  __int64 v9; // rdi
  unsigned int v10; // ebx
  const unsigned __int16 *v11; // rbx
  const unsigned __int16 *v12; // rax
  const struct _GUID *v13; // r8
  __int64 v14; // rdx
  _KPROFILE_SOURCE v15; // eax
  __int64 *v16; // rbx
  __int64 i; // rbx
  struct _PROFILE_SOURCE_INFO *ProfileSources; // rax
  _OWORD *v19; // rdx
  __int64 v20; // r8
  struct _PROFILE_SOURCE_INFO *v21; // rsi
  int v22; // r13d
  struct _PROFILE_SOURCE_INFO *j; // rdi
  unsigned int Source; // edi
  const unsigned __int16 *v25; // rdi
  const unsigned __int16 *v26; // rax
  const struct _GUID *v27; // r8
  __int64 v28; // rax
  __int64 v29; // rcx
  __int64 k; // rax
  __int64 v31; // rbx
  const unsigned __int16 *v32; // rsi
  const unsigned __int16 *v33; // rdi
  const unsigned __int16 *v34; // rax
  const struct _GUID *v35; // r8
  __int64 v36; // rax
  _OWORD *v37; // rdx
  __int64 v38; // rax
  unsigned __int16 *v39; // rbx
  unsigned __int16 **v40; // rdx
  __int64 v41; // rax
  _OWORD *v42; // rdx
  unsigned int v43; // eax
  const unsigned __int16 *v44; // rbx
  const unsigned __int16 *v45; // rax
  const struct _GUID *v46; // r8
  __int64 v47; // rax
  unsigned int *Format; // [rsp+20h] [rbp-40h]
  char *v49; // [rsp+28h] [rbp-38h]
  struct IControlErrorInfo *v50; // [rsp+38h] [rbp-28h]
  _KPROFILE_SOURCE v51; // [rsp+40h] [rbp-20h] BYREF
  __int64 v52; // [rsp+48h] [rbp-18h] BYREF
  __int128 v53; // [rsp+50h] [rbp-10h] BYREF
  __int64 v54; // [rsp+A0h] [rbp+40h] BYREF
  unsigned __int16 *v55; // [rsp+A8h] [rbp+48h] BYREF
  unsigned int v56; // [rsp+B8h] [rbp+58h] BYREF

  *((_QWORD *)this + 4) = (*(__int64 (__fastcall **)(const struct WindowsPerformanceRecorder::CHardwareCounterElement *))(*(_QWORD *)a2 + 16LL))(a2);
  *((_BYTE *)this + 40) = *((_BYTE *)a2 + 24);
  if ( Performance::COSVersionInfo::IsWin8AndUp() && GetTraceQueryInformation() )
  {
    if ( *((_QWORD *)a2 + 20) )
    {
      *((_QWORD *)this + 28) = *((_QWORD *)a2 + 18);
      v6 = WindowsPerformanceRecorder::CETWProperties::RegisterMicroArchitecturalCounters(this, a2, a3);
      if ( v6 < 0 )
      {
        WindowsPerformanceRecorder::TraceHR(
          (WindowsPerformanceRecorder *)2,
          "AddHardwareCounters",
          (const char *)0x971,
          v6,
          "COMGUARD",
          v49);
        return (unsigned int)v6;
      }
    }
    if ( *((_QWORD *)a2 + 9) )
    {
      v8 = **((_QWORD **)a2 + 8);
      v52 = v8;
      while ( !*(_BYTE *)(v8 + 25) )
      {
        v9 = v8 + 26;
        v51 = ProfileTime;
        v10 = 0;
        LODWORD(v55) = 0;
        LODWORD(v54) = 0;
        v56 = 0;
        if ( (unsigned int)QueryProfileSourceDetail(
                             (const unsigned __int16 *)(v8 + 26),
                             &v51,
                             (unsigned int *)&v55,
                             (unsigned int *)&v54) )
        {
          if ( *(_WORD *)(v9 + 256) )
          {
            if ( (int)WindowsPerformanceRecorder::Impl::ConvertToULONG(
                        (wchar_t *)(v9 + 256),
                        (const unsigned __int16 *)(unsigned int)v55,
                        v54,
                        (unsigned int)&v56,
                        Format) < 0 )
              return 3310882831LL;
            v10 = v56;
          }
          v14 = *((_QWORD *)this + 13);
          v15 = v51;
          *(_QWORD *)&v53 = v9;
          *((_QWORD *)&v53 + 1) = __PAIR64__(v10, v51);
          if ( v14 == *((_QWORD *)this + 14) )
          {
            std::vector<WindowsPerformanceRecorder::CETWProperties::EventCounter>::_Emplace_reallocate<WindowsPerformanceRecorder::CETWProperties::EventCounter const &>(
              (char *)this + 96,
              v14,
              &v53);
          }
          else
          {
            *(_QWORD *)v14 = v9;
            *(_DWORD *)(v14 + 8) = v15;
            *(_DWORD *)(v14 + 12) = v10;
            *((_QWORD *)this + 13) += 16LL;
          }
        }
        else
        {
          if ( a3 )
          {
            v11 = (const unsigned __int16 *)*((_QWORD *)this + 40);
            v12 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct WindowsPerformanceRecorder::CHardwareCounterElement *))(*(_QWORD *)a2 + 16LL))(a2);
            WindowsPerformanceRecorder::CControlManager::AddProviderControlWarningInfo(
              a3,
              -984086999,
              v13,
              0,
              v12,
              v11,
              0,
              v50);
            (*(void (__fastcall **)(const struct WindowsPerformanceRecorder::CHardwareCounterElement *))(*(_QWORD *)a2 + 16LL))(a2);
            WindowsPerformanceRecorder::TraceHR(
              (WindowsPerformanceRecorder *)3,
              "AddHardwareCounters",
              (const char *)0x982,
              0xC5580629,
              "%ws, %ws",
              *((const char **)this + 40));
          }
          if ( *((_BYTE *)this + 40) )
            return 3310880297LL;
        }
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CHardwareCounterElement::CCounter>>,std::_Iterator_base0>::operator++(&v52);
        v8 = v52;
      }
    }
    if ( *((_QWORD *)a2 + 7) && *((_QWORD *)a2 + 5) )
    {
      v16 = (__int64 *)*((_QWORD *)a2 + 6);
      LODWORD(v54) = 0;
      for ( i = *v16; !*(_BYTE *)(i + 25); i = k )
      {
        ProfileSources = QueryProfileSources();
        v21 = ProfileSources;
        if ( !ProfileSources )
          goto LABEL_37;
        v22 = 0;
        for ( j = ProfileSources; ; j = (struct _PROFILE_SOURCE_INFO *)((char *)j + j->NextEntryOffset) )
        {
          if ( !(unsigned int)_o__wcsicmp(i + 26, j->Description) )
          {
            Source = j->Source;
            v22 = 1;
            LODWORD(v54) = Source;
            goto LABEL_33;
          }
          if ( !j->NextEntryOffset )
            break;
        }
        Source = v54;
LABEL_33:
        free(v21);
        if ( v22 )
        {
          v19 = (_OWORD *)*((_QWORD *)this + 7);
          *(_QWORD *)&v53 = i + 26;
          DWORD2(v53) = Source;
          if ( v19 == *((_OWORD **)this + 8) )
          {
            std::vector<WindowsPerformanceRecorder::CETWProperties::EventCounter>::_Emplace_reallocate<WindowsPerformanceRecorder::CETWProperties::EventCounter const &>(
              (char *)this + 48,
              v19,
              &v53);
          }
          else
          {
            *v19 = v53;
            *((_QWORD *)this + 7) += 16LL;
          }
        }
        else
        {
LABEL_37:
          if ( a3 )
          {
            v25 = (const unsigned __int16 *)*((_QWORD *)this + 40);
            v26 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct WindowsPerformanceRecorder::CHardwareCounterElement *))(*(_QWORD *)a2 + 16LL))(a2);
            WindowsPerformanceRecorder::CControlManager::AddProviderControlWarningInfo(
              a3,
              -984087000,
              v27,
              0,
              v26,
              v25,
              0,
              v50);
            v28 = (*(__int64 (__fastcall **)(const struct WindowsPerformanceRecorder::CHardwareCounterElement *))(*(_QWORD *)a2 + 16LL))(a2);
            WindowsPerformanceRecorder::TraceHR(
              (WindowsPerformanceRecorder *)3,
              "AddHardwareCounters",
              (const char *)0x9AB,
              0xC5580628,
              "%ws, %ws",
              *((const char **)this + 40),
              v28);
          }
          if ( *((_BYTE *)this + 40) )
            return 3310880296LL;
        }
        v29 = *(_QWORD *)(i + 16);
        if ( *(_BYTE *)(v29 + 25) )
        {
          for ( k = *(_QWORD *)(i + 8); !*(_BYTE *)(k + 25) && i == *(_QWORD *)(k + 16); k = *(_QWORD *)(k + 8) )
            i = k;
        }
        else
        {
          k = std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::IProfileElement *>>::_Min(
                v29,
                v19,
                v20);
        }
      }
      v31 = **((_QWORD **)a2 + 4);
      v54 = v31;
      while ( !*(_BYTE *)(v31 + 25) )
      {
        if ( *(_DWORD *)(v31 + 44) <= Performance::COSVersionInfo::GetOSVersionInfo()->dwBuildNumber )
        {
          *(_QWORD *)&v53 = *(_QWORD *)(v31 + 32);
          DWORD2(v53) = *(unsigned __int16 *)(v31 + 40);
          std::vector<WindowsPerformanceRecorder::CETWProperties::EventCounterEvent>::_Emplace_one_at_back<WindowsPerformanceRecorder::CETWProperties::EventCounterEvent const &>(
            (char *)this + 72,
            &v53);
        }
        else
        {
          if ( a3 )
          {
            v32 = *(const unsigned __int16 **)(v31 + 32);
            v33 = (const unsigned __int16 *)*((_QWORD *)this + 40);
            v34 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct WindowsPerformanceRecorder::CHardwareCounterElement *))(*(_QWORD *)a2 + 16LL))(a2);
            WindowsPerformanceRecorder::CControlManager::AddProviderControlWarningInfo(
              a3,
              -984080383,
              v35,
              0,
              v34,
              v33,
              v32,
              v50);
            WindowsPerformanceRecorder::TraceHR(
              (WindowsPerformanceRecorder *)3,
              "AddHardwareCounters",
              (const char *)0x9C4,
              0xC5582001,
              "%ws, %ws",
              *((const char **)this + 40),
              *(_QWORD *)(v31 + 32));
          }
          if ( *((_BYTE *)this + 40) )
            return 3310886913LL;
        }
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CBaseProfileElement::CStack>>,std::_Iterator_base0>::operator++(&v54);
        v31 = v54;
      }
    }
    if ( !*((_QWORD *)a2 + 13) )
      goto LABEL_125;
    *((_DWORD *)this + 30) = 0;
    v36 = **((_QWORD **)a2 + 12);
    v54 = v36;
    while ( !*(_BYTE *)(v36 + 25) )
    {
      v37 = (_OWORD *)*((_QWORD *)this + 20);
      *(_QWORD *)&v53 = *(_QWORD *)(v36 + 32);
      DWORD2(v53) = *(unsigned __int16 *)(v36 + 40);
      if ( v37 == *((_OWORD **)this + 21) )
      {
        std::vector<WindowsPerformanceRecorder::CETWProperties::EventCounter>::_Emplace_reallocate<WindowsPerformanceRecorder::CETWProperties::EventCounter const &>(
          (char *)this + 152,
          v37,
          &v53);
      }
      else
      {
        *v37 = v53;
        *((_QWORD *)this + 20) += 16LL;
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CBaseProfileElement::CStack>>,std::_Iterator_base0>::operator++(&v54);
      v36 = v54;
    }
    if ( !*((_QWORD *)a2 + 11) )
      goto LABEL_125;
    v38 = **((_QWORD **)a2 + 10);
    v54 = v38;
    while ( !*(_BYTE *)(v38 + 25) )
    {
      v39 = (unsigned __int16 *)(v38 + 26);
      if ( (unsigned int)_o__wcsicmp(v38 + 26, L"conditionalbranches") )
      {
        if ( (unsigned int)_o__wcsicmp(v39, L"nearrelativecalls") )
        {
          if ( (unsigned int)_o__wcsicmp(v39, L"nearindirectcalls") )
          {
            if ( (unsigned int)_o__wcsicmp(v39, L"nearreturns") )
            {
              if ( (unsigned int)_o__wcsicmp(v39, L"nearindirectjumps") )
              {
                if ( (unsigned int)_o__wcsicmp(v39, L"nearrelativejumps") )
                {
                  if ( (unsigned int)_o__wcsicmp(v39, L"farbranches") )
                  {
                    if ( (unsigned int)_o__wcsicmp(v39, L"kernel") )
                    {
                      if ( (unsigned int)_o__wcsicmp(v39, L"user") )
                      {
                        if ( (unsigned int)_o__wcsicmp(v39, L"stackmode") )
                        {
                          if ( !(unsigned int)_o__wcsicmp(v39, L"sampled") )
                            *((_DWORD *)this + 30) |= 0x400u;
                        }
                        else
                        {
                          *((_DWORD *)this + 30) |= 0x200u;
                        }
                      }
                      else
                      {
                        *((_DWORD *)this + 30) |= 2u;
                      }
                    }
                    else
                    {
                      *((_DWORD *)this + 30) |= 1u;
                    }
                  }
                  else
                  {
                    *((_DWORD *)this + 30) |= 0x100u;
                  }
                }
                else
                {
                  *((_DWORD *)this + 30) |= 0x80u;
                }
              }
              else
              {
                *((_DWORD *)this + 30) |= 0x40u;
              }
            }
            else
            {
              *((_DWORD *)this + 30) |= 0x20u;
            }
          }
          else
          {
            *((_DWORD *)this + 30) |= 0x10u;
          }
        }
        else
        {
          *((_DWORD *)this + 30) |= 8u;
        }
      }
      else
      {
        *((_DWORD *)this + 30) |= 4u;
      }
      v40 = (unsigned __int16 **)*((_QWORD *)this + 17);
      v55 = v39;
      if ( v40 == *((unsigned __int16 ***)this + 18) )
      {
        std::vector<WindowsPerformanceRecorder::CETWProperties::CEventSession *>::_Emplace_reallocate<WindowsPerformanceRecorder::CETWProperties::CEventSession * const &>(
          (char *)this + 128,
          v40,
          &v55);
      }
      else
      {
        *v40 = v39;
        *((_QWORD *)this + 17) += 8LL;
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CHardwareCounterElement::CCounter>>,std::_Iterator_base0>::operator++(&v54);
      v38 = v54;
    }
    if ( (*((_BYTE *)this + 120) & 3) == 3 )
      return 3310880309LL;
    if ( (*((_DWORD *)this + 30) & 0xFFFFFDFC) != 0 && (*((_DWORD *)this + 30) & 0x200) != 0 )
    {
      return 3310880310LL;
    }
    else
    {
LABEL_125:
      if ( *((_QWORD *)a2 + 15) )
      {
        *((_QWORD *)this + 22) = 0;
        v41 = **((_QWORD **)a2 + 14);
        v54 = v41;
        while ( !*(_BYTE *)(v41 + 25) )
        {
          v42 = (_OWORD *)*((_QWORD *)this + 26);
          *(_QWORD *)&v53 = *(_QWORD *)(v41 + 32);
          DWORD2(v53) = *(unsigned __int16 *)(v41 + 40);
          if ( v42 == *((_OWORD **)this + 27) )
          {
            std::vector<WindowsPerformanceRecorder::CETWProperties::EventCounter>::_Emplace_reallocate<WindowsPerformanceRecorder::CETWProperties::EventCounter const &>(
              (char *)this + 200,
              v42,
              &v53);
          }
          else
          {
            *v42 = v53;
            *((_QWORD *)this + 26) += 16LL;
          }
          std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CBaseProfileElement::CStack>>,std::_Iterator_base0>::operator++(&v54);
          v41 = v54;
        }
        *((_DWORD *)this + 48) = *((_DWORD *)a2 + 32);
        *((_QWORD *)this + 23) = *((_QWORD *)a2 + 17);
        *((_DWORD *)this + 44) = *((_DWORD *)this + 44) & 0xFFFFFFF0 | 1;
        if ( (unsigned int)_o__wcsicmp(*((_QWORD *)a2 + 17), L"User") )
        {
          if ( (unsigned int)_o__wcsicmp(*((_QWORD *)a2 + 17), L"Kernel") )
          {
            if ( !(unsigned int)_o__wcsicmp(*((_QWORD *)a2 + 17), L"UserKernel") )
            {
              *((_DWORD *)this + 44) &= 0xF5FFFFFF;
              *((_DWORD *)this + 44) |= 0x5000000u;
            }
          }
          else
          {
            *((_DWORD *)this + 44) &= 0xF4FFFFFF;
            *((_DWORD *)this + 44) |= 0x4000000u;
          }
        }
        else
        {
          *((_DWORD *)this + 44) &= 0xF3FFFFFF;
          *((_DWORD *)this + 44) |= 0x3000000u;
        }
        v43 = *((_DWORD *)a2 + 32);
        if ( v43 > 4 )
        {
          if ( v43 > 8 )
          {
            if ( v43 > 0x10 )
            {
              if ( v43 <= 0x20 )
              {
                *((_DWORD *)this + 44) &= 0xFFF3FFFF;
                *((_DWORD *)this + 44) |= 0x30000u;
              }
            }
            else
            {
              *((_DWORD *)this + 44) &= 0xFFF2FFFF;
              *((_DWORD *)this + 44) |= 0x20000u;
            }
          }
          else
          {
            *((_DWORD *)this + 44) &= 0xFFF1FFFF;
            *((_DWORD *)this + 44) |= 0x10000u;
          }
        }
        else
        {
          *((_DWORD *)this + 44) &= 0xFFF0FFFF;
        }
      }
      return 0;
    }
  }
  else
  {
    if ( a3 )
    {
      v44 = (const unsigned __int16 *)*((_QWORD *)this + 40);
      v45 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct WindowsPerformanceRecorder::CHardwareCounterElement *))(*(_QWORD *)a2 + 16LL))(a2);
      WindowsPerformanceRecorder::CControlManager::AddProviderControlWarningInfo(
        a3,
        -984087001,
        v46,
        0,
        v45,
        v44,
        0,
        v50);
      v47 = (*(__int64 (__fastcall **)(const struct WindowsPerformanceRecorder::CHardwareCounterElement *))(*(_QWORD *)a2 + 16LL))(a2);
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)3,
        "AddHardwareCounters",
        (const char *)0x964,
        0xC5580627,
        "%ws, %ws",
        *((const char **)this + 40),
        v47);
    }
    return *((_BYTE *)this + 40) != 0 ? 0xC5580627 : 0;
  }
}

```

## disassembly

```asm
0x18001656c  mov     [rsp-38h+arg_10], rbx
0x180016571  push    rbp
0x180016572  push    rsi
0x180016573  push    rdi
0x180016574  push    r12
0x180016576  push    r13
0x180016578  push    r14
0x18001657a  push    r15
0x18001657c  mov     rbp, rsp
0x18001657f  sub     rsp, 60h
0x180016583  mov     rax, [rdx]
0x180016586  mov     r14, rcx
0x180016589  mov     rcx, rdx
0x18001658c  mov     r12, r8
0x18001658f  mov     r15, rdx
0x180016592  mov     rax, [rax+10h]
0x180016596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001659b  mov     [r14+20h], rax
0x18001659f  mov     al, [r15+18h]
0x1800165a3  mov     [r14+28h], al
0x1800165a7  call    ?IsWin8AndUp@COSVersionInfo@Performance@@SA_NXZ; Performance::COSVersionInfo::IsWin8AndUp(void)
0x1800165ac  xor     esi, esi
0x1800165ae  test    al, al
0x1800165b0  jz      loc_180016DAF
0x1800165b6  call    ?GetTraceQueryInformation@@YAP6AK_KW4_TRACE_QUERY_INFO_CLASS@@PEAXKPEAK@ZXZ; GetTraceQueryInformation(void)
0x1800165bb  test    rax, rax
0x1800165be  jz      loc_180016DAF
0x1800165c4  cmp     [r15+0A0h], rsi
0x1800165cb  jz      short loc_18001661A
0x1800165cd  mov     rax, [r15+90h]
0x1800165d4  mov     r8, r12; struct WindowsPerformanceRecorder::CControlManager *
0x1800165d7  mov     rdx, r15; struct WindowsPerformanceRecorder::CHardwareCounterElement *
0x1800165da  mov     [r14+0E0h], rax
0x1800165e1  mov     rcx, r14; this
0x1800165e4  call    ?RegisterMicroArchitecturalCounters@CETWProperties@WindowsPerformanceRecorder@@AEAAJPEBVCHardwareCounterElement@2@PEAVCControlManager@2@@Z; WindowsPerformanceRecorder::CETWProperties::RegisterMicroArchitecturalCounters(WindowsPerformanceRecorder::CHardwareCounterElement const *,WindowsPerformanceRecorder::CControlManager *)
0x1800165e9  mov     ebx, eax
0x1800165eb  test    eax, eax
0x1800165ed  jns     short loc_18001661A
0x1800165ef  lea     rax, aComguard; "COMGUARD"
0x1800165f6  mov     r9d, ebx; unsigned int
0x1800165f9  mov     r8d, 971h; char *
0x1800165ff  mov     [rsp+60h+Format], rax; Format
0x180016604  lea     rdx, aAddhardwarecou; "AddHardwareCounters"
0x18001660b  lea     ecx, [rsi+2]; this
0x18001660e  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180016613  mov     eax, ebx
0x180016615  jmp     loc_180016E3B
0x18001661a  lea     r13, aWsWs_6; "%ws, %ws"
0x180016621  cmp     [r15+48h], rsi
0x180016625  jz      loc_18001676D
0x18001662b  mov     rax, [r15+40h]
0x18001662f  mov     rax, [rax]
0x180016632  mov     [rbp+var_18], rax
0x180016636  cmp     [rax+19h], sil
0x18001663a  jnz     loc_18001676D
0x180016640  lea     rdi, [rax+1Ah]
0x180016644  mov     [rbp+var_20], esi
0x180016647  mov     ebx, esi
0x180016649  mov     dword ptr [rbp+arg_8], esi
0x18001664c  mov     rcx, rdi; unsigned __int16 *
0x18001664f  mov     dword ptr [rbp+arg_0], esi
0x180016652  lea     r9, [rbp+arg_0]; unsigned int *
0x180016656  mov     [rbp+arg_18], ebx
0x180016659  lea     r8, [rbp+arg_8]; unsigned int *
0x18001665d  lea     rdx, [rbp+var_20]; enum _KPROFILE_SOURCE *
0x180016661  call    ?QueryProfileSourceDetail@@YAHPEBGPEAW4_KPROFILE_SOURCE@@PEAK2@Z; QueryProfileSourceDetail(ushort const *,_KPROFILE_SOURCE *,ulong *,ulong *)
0x180016666  test    eax, eax
0x180016668  jnz     loc_1800166FA
0x18001666e  test    r12, r12
0x180016671  jz      short loc_1800166EA
0x180016673  mov     rax, [r15]
0x180016676  mov     rcx, r15
0x180016679  mov     rbx, [r14+140h]
0x180016680  mov     rax, [rax+10h]
0x180016684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016689  mov     [rsp+60h+var_30], rsi; unsigned __int16 *
0x18001668e  xor     r9d, r9d; struct _GUID *
0x180016691  mov     [rsp+60h+var_38], rbx; unsigned __int16 *
0x180016696  mov     edx, 0C5580629h; int
0x18001669b  mov     rcx, r12; this
0x18001669e  mov     [rsp+60h+Format], rax; unsigned __int16 *
0x1800166a3  call    ?AddProviderControlWarningInfo@CControlManager@WindowsPerformanceRecorder@@QEAAXJAEBU_GUID@@PEBU3@PEBG22PEAUIControlErrorInfo@@@Z; WindowsPerformanceRecorder::CControlManager::AddProviderControlWarningInfo(long,_GUID const &,_GUID const *,ushort const *,ushort const *,ushort const *,IControlErrorInfo *)
0x1800166a8  mov     rax, [r15]
0x1800166ab  mov     rcx, r15
0x1800166ae  mov     rax, [rax+10h]
0x1800166b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166b7  mov     [rsp+60h+var_30], rax
0x1800166bc  lea     rdx, aAddhardwarecou; "AddHardwareCounters"
0x1800166c3  mov     rax, [r14+140h]
0x1800166ca  mov     r9d, 0C5580629h; unsigned int
0x1800166d0  mov     [rsp+60h+var_38], rax; char *
0x1800166d5  mov     r8d, 982h; char *
0x1800166db  mov     ecx, 3; this
0x1800166e0  mov     [rsp+60h+Format], r13; Format
0x1800166e5  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x1800166ea  cmp     [r14+28h], sil
0x1800166ee  jz      short loc_180016751
0x1800166f0  mov     eax, 0C5580629h
0x1800166f5  jmp     loc_180016E3B
0x1800166fa  lea     rcx, [rdi+100h]; String
0x180016701  cmp     [rcx], si
0x180016704  jz      short loc_18001671D
0x180016706  mov     r8d, dword ptr [rbp+arg_0]; unsigned int
0x18001670a  lea     r9, [rbp+arg_18]; unsigned int
0x18001670e  mov     edx, dword ptr [rbp+arg_8]; unsigned __int16 *
0x180016711  call    ?ConvertToULONG@Impl@WindowsPerformanceRecorder@@YAJPEBGKKPEAK@Z; WindowsPerformanceRecorder::Impl::ConvertToULONG(ushort const *,ulong,ulong,ulong *)
0x180016716  test    eax, eax
0x180016718  js      short loc_180016763
0x18001671a  mov     ebx, [rbp+arg_18]
0x18001671d  mov     rdx, [r14+68h]
0x180016721  lea     rcx, [r14+60h]
0x180016725  mov     eax, [rbp+var_20]
0x180016728  mov     qword ptr [rbp+var_10], rdi
0x18001672c  mov     dword ptr [rbp+var_10+8], eax
0x18001672f  mov     dword ptr [rbp+var_10+0Ch], ebx
0x180016732  cmp     rdx, [r14+70h]
0x180016736  jz      short loc_180016748
0x180016738  mov     [rdx], rdi
0x18001673b  mov     [rdx+8], eax
0x18001673e  mov     [rdx+0Ch], ebx
0x180016741  add     qword ptr [rcx+8], 10h
0x180016746  jmp     short loc_180016751
0x180016748  lea     r8, [rbp+var_10]
0x18001674c  call    ??$_Emplace_reallocate@AEBUEventCounter@CETWProperties@WindowsPerformanceRecorder@@@?$vector@UEventCounter@CETWProperties@WindowsPerformanceRecorder@@V?$allocator@UEventCounter@CETWProperties@WindowsPerformanceRecorder@@@std@@@std@@AEAAPEAUEventCounter@CETWProperties@WindowsPerformanceRecorder@@QEAU234@AEBU234@@Z; std::vector<WindowsPerformanceRecorder::CETWProperties::EventCounter>::_Emplace_reallocate<WindowsPerformanceRecorder::CETWProperties::EventCounter const &>(WindowsPerformanceRecorder::CETWProperties::EventCounter * const,WindowsPerformanceRecorder::CETWProperties::EventCounter const &)
0x180016751  lea     rcx, [rbp+var_18]
0x180016755  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@UCCounter@CHardwareCounterElement@WindowsPerformanceRecorder@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CHardwareCounterElement::CCounter>>,std::_Iterator_base0>::operator++(void)
0x18001675a  mov     rax, [rbp+var_18]
0x18001675e  jmp     loc_180016636
0x180016763  mov     eax, 0C558100Fh
0x180016768  jmp     loc_180016E3B
0x18001676d  cmp     [r15+38h], rsi
0x180016771  jz      loc_1800169D2
0x180016777  cmp     [r15+28h], rsi
0x18001677b  jz      loc_1800169D2
0x180016781  mov     rbx, [r15+30h]
0x180016785  mov     dword ptr [rbp+arg_0], esi
0x180016788  mov     rbx, [rbx]
0x18001678b  cmp     [rbx+19h], sil
0x18001678f  jnz     loc_1800168F7
0x180016795  call    ?QueryProfileSources@@YAPEAU_PROFILE_SOURCE_INFO@@XZ; QueryProfileSources(void)
0x18001679a  mov     rsi, rax
0x18001679d  test    rax, rax
0x1800167a0  jz      loc_180016830
0x1800167a6  xor     r13d, r13d
0x1800167a9  mov     rdi, rax
0x1800167ac  lea     rax, [rbx+1Ah]
0x1800167b0  mov     rcx, rax
0x1800167b3  lea     rdx, [rdi+18h]
0x1800167b7  call    cs:__imp__o__wcsicmp
0x1800167bd  test    eax, eax
0x1800167bf  jz      short loc_1800167CD
0x1800167c1  cmp     [rdi], r13d
0x1800167c4  jz      short loc_1800167DB
0x1800167c6  mov     eax, [rdi]
0x1800167c8  add     rdi, rax
0x1800167cb  jmp     short loc_1800167AC
0x1800167cd  mov     edi, [rdi+4]
0x1800167d0  mov     r13d, 1
0x1800167d6  mov     dword ptr [rbp+arg_0], edi
0x1800167d9  jmp     short loc_1800167DE
0x1800167db  mov     edi, dword ptr [rbp+arg_0]
0x1800167de  mov     rcx, rsi; Block
0x1800167e1  call    cs:__imp_free
0x1800167e7  xor     esi, esi
0x1800167e9  test    r13d, r13d
0x1800167ec  jz      short loc_180016827
0x1800167ee  mov     rdx, [r14+38h]
0x1800167f2  lea     rax, [rbx+1Ah]
0x1800167f6  lea     rcx, [r14+30h]
0x1800167fa  mov     qword ptr [rbp+var_10], rax
0x1800167fe  mov     dword ptr [rbp+var_10+8], edi
0x180016801  cmp     rdx, [r14+40h]
0x180016805  jz      short loc_180016819
0x180016807  movups  xmm0, [rbp+var_10]
0x18001680b  movdqu  xmmword ptr [rdx], xmm0
0x18001680f  add     qword ptr [rcx+8], 10h
0x180016814  jmp     loc_1800168B4
0x180016819  lea     r8, [rbp+var_10]
0x18001681d  call    ??$_Emplace_reallocate@AEBUEventCounter@CETWProperties@WindowsPerformanceRecorder@@@?$vector@UEventCounter@CETWProperties@WindowsPerformanceRecorder@@V?$allocator@UEventCounter@CETWProperties@WindowsPerformanceRecorder@@@std@@@std@@AEAAPEAUEventCounter@CETWProperties@WindowsPerformanceRecorder@@QEAU234@AEBU234@@Z; std::vector<WindowsPerformanceRecorder::CETWProperties::EventCounter>::_Emplace_reallocate<WindowsPerformanceRecorder::CETWProperties::EventCounter const &>(WindowsPerformanceRecorder::CETWProperties::EventCounter * const,WindowsPerformanceRecorder::CETWProperties::EventCounter const &)
0x180016822  jmp     loc_1800168B4
0x180016827  lea     r13, aWsWs_6; "%ws, %ws"
0x18001682e  jmp     short loc_180016832
0x180016830  xor     esi, esi
0x180016832  test    r12, r12
0x180016835  jz      short loc_1800168AE
0x180016837  mov     rax, [r15]
0x18001683a  mov     rcx, r15
0x18001683d  mov     rdi, [r14+140h]
0x180016844  mov     rax, [rax+10h]
0x180016848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001684d  mov     [rsp+60h+var_30], rsi; unsigned __int16 *
0x180016852  xor     r9d, r9d; struct _GUID *
0x180016855  mov     [rsp+60h+var_38], rdi; unsigned __int16 *
0x18001685a  mov     edx, 0C5580628h; int
0x18001685f  mov     rcx, r12; this
0x180016862  mov     [rsp+60h+Format], rax; unsigned __int16 *
0x180016867  call    ?AddProviderControlWarningInfo@CControlManager@WindowsPerformanceRecorder@@QEAAXJAEBU_GUID@@PEBU3@PEBG22PEAUIControlErrorInfo@@@Z; WindowsPerformanceRecorder::CControlManager::AddProviderControlWarningInfo(long,_GUID const &,_GUID const *,ushort const *,ushort const *,ushort const *,IControlErrorInfo *)
0x18001686c  mov     rax, [r15]
0x18001686f  mov     rcx, r15
0x180016872  mov     rax, [rax+10h]
0x180016876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001687b  mov     [rsp+60h+var_30], rax
0x180016880  lea     rdx, aAddhardwarecou; "AddHardwareCounters"
0x180016887  mov     rax, [r14+140h]
0x18001688e  mov     r9d, 0C5580628h; unsigned int
0x180016894  mov     [rsp+60h+var_38], rax; char *
0x180016899  mov     r8d, 9ABh; char *
0x18001689f  mov     ecx, 3; this
0x1800168a4  mov     [rsp+60h+Format], r13; Format
0x1800168a9  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x1800168ae  cmp     [r14+28h], sil
0x1800168b2  jnz     short loc_1800168ED
0x1800168b4  mov     rcx, [rbx+10h]
0x1800168b8  cmp     [rcx+19h], sil
0x1800168bc  jz      short loc_1800168D9
0x1800168be  mov     rax, [rbx+8]
0x1800168c2  jmp     short loc_1800168D1
0x1800168c4  cmp     rbx, [rax+10h]
0x1800168c8  jnz     short loc_1800168DE
0x1800168ca  mov     rbx, rax
0x1800168cd  mov     rax, [rax+8]
0x1800168d1  cmp     [rax+19h], sil
0x1800168d5  jz      short loc_1800168C4
0x1800168d7  jmp     short loc_1800168DE
0x1800168d9  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@PEAUIProfileElement@WindowsPerformanceRecorder@@@std@@@std@@SAPEAU?$_Tree_node@PEAUIProfileElement@WindowsPerformanceRecorder@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::IProfileElement *>>::_Min(std::_Tree_node<WindowsPerformanceRecorder::IProfileElement *,void *> *)
0x1800168de  mov     rbx, rax
0x1800168e1  lea     r13, aWsWs_6; "%ws, %ws"
0x1800168e8  jmp     loc_18001678B
0x1800168ed  mov     eax, 0C5580628h
0x1800168f2  jmp     loc_180016E3B
0x1800168f7  mov     rbx, [r15+20h]
0x1800168fb  mov     rbx, [rbx]
0x1800168fe  mov     [rbp+arg_0], rbx
0x180016902  cmp     [rbx+19h], sil
0x180016906  jnz     loc_1800169D2
0x18001690c  call    ?GetOSVersionInfo@COSVersionInfo@Performance@@SAAEBU_OSVERSIONINFOEXW@@XZ; Performance::COSVersionInfo::GetOSVersionInfo(void)
0x180016911  mov     eax, [rax+0Ch]
0x180016914  cmp     [rbx+2Ch], eax
0x180016917  jbe     loc_1800169A4
0x18001691d  test    r12, r12
0x180016920  jz      short loc_180016994
0x180016922  mov     rax, [r15]
0x180016925  mov     rcx, r15
0x180016928  mov     rsi, [rbx+20h]
0x18001692c  mov     rdi, [r14+140h]
0x180016933  mov     rax, [rax+10h]
0x180016937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001693c  mov     [rsp+60h+var_30], rsi; unsigned __int16 *
0x180016941  xor     r9d, r9d; struct _GUID *
0x180016944  mov     [rsp+60h+var_38], rdi; unsigned __int16 *
0x180016949  mov     edx, 0C5582001h; int
0x18001694e  mov     rcx, r12; this
0x180016951  mov     [rsp+60h+Format], rax; unsigned __int16 *
0x180016956  call    ?AddProviderControlWarningInfo@CControlManager@WindowsPerformanceRecorder@@QEAAXJAEBU_GUID@@PEBU3@PEBG22PEAUIControlErrorInfo@@@Z; WindowsPerformanceRecorder::CControlManager::AddProviderControlWarningInfo(long,_GUID const &,_GUID const *,ushort const *,ushort const *,ushort const *,IControlErrorInfo *)
0x18001695b  mov     rax, [rbx+20h]
0x18001695f  lea     rdx, aAddhardwarecou; "AddHardwareCounters"
0x180016966  mov     [rsp+60h+var_30], rax
0x18001696b  mov     r9d, 0C5582001h; unsigned int
0x180016971  mov     rax, [r14+140h]
0x180016978  mov     r8d, 9C4h; char *
0x18001697e  mov     [rsp+60h+var_38], rax; char *
0x180016983  mov     ecx, 3; this
0x180016988  mov     [rsp+60h+Format], r13; Format
0x18001698d  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180016992  xor     esi, esi
0x180016994  cmp     [r14+28h], sil
0x180016998  jz      short loc_1800169C0
0x18001699a  mov     eax, 0C5582001h
0x18001699f  jmp     loc_180016E3B
0x1800169a4  mov     rax, [rbx+20h]
0x1800169a8  lea     rcx, [r14+48h]
0x1800169ac  mov     qword ptr [rbp+var_10], rax
0x1800169b0  lea     rdx, [rbp+var_10]
0x1800169b4  movzx   eax, word ptr [rbx+28h]
0x1800169b8  mov     dword ptr [rbp+var_10+8], eax
0x1800169bb  call    ??$_Emplace_one_at_back@AEBUEventCounterEvent@CETWProperties@WindowsPerformanceRecorder@@@?$vector@UEventCounterEvent@CETWProperties@WindowsPerformanceRecorder@@V?$allocator@UEventCounterEvent@CETWProperties@WindowsPerformanceRecorder@@@std@@@std@@AEAAAEAUEventCounterEvent@CETWProperties@WindowsPerformanceRecorder@@AEBU234@@Z; std::vector<WindowsPerformanceRecorder::CETWProperties::EventCounterEvent>::_Emplace_one_at_back<WindowsPerformanceRecorder::CETWProperties::EventCounterEvent const &>(WindowsPerformanceRecorder::CETWProperties::EventCounterEvent const &)
0x1800169c0  lea     rcx, [rbp+arg_0]
0x1800169c4  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@UCStack@CBaseProfileElement@WindowsPerformanceRecorder@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CBaseProfileElement::CStack>>,std::_Iterator_base0>::operator++(void)
0x1800169c9  mov     rbx, [rbp+arg_0]
0x1800169cd  jmp     loc_180016902
0x1800169d2  cmp     [r15+68h], rsi
0x1800169d6  jz      loc_180016C13
0x1800169dc  mov     [r14+78h], esi
0x1800169e0  mov     rax, [r15+60h]
0x1800169e4  mov     rax, [rax]
0x1800169e7  mov     [rbp+arg_0], rax
0x1800169eb  cmp     [rax+19h], sil
0x1800169ef  jnz     short loc_180016A3E
0x1800169f1  mov     rcx, [rax+20h]
0x1800169f5  mov     rdx, [r14+0A0h]
0x1800169fc  mov     qword ptr [rbp+var_10], rcx
0x180016a00  movzx   ecx, word ptr [rax+28h]
0x180016a04  mov     dword ptr [rbp+var_10+8], ecx
0x180016a07  lea     rcx, [r14+98h]
0x180016a0e  cmp     rdx, [r14+0A8h]
0x180016a15  jz      short loc_180016A26
0x180016a17  movups  xmm0, [rbp+var_10]
0x180016a1b  movdqu  xmmword ptr [rdx], xmm0
0x180016a1f  add     qword ptr [rcx+8], 10h
0x180016a24  jmp     short loc_180016A2F
  ... truncated ...
```
