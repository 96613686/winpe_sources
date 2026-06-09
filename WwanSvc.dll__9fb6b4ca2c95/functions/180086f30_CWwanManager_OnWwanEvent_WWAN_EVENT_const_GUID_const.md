# CWwanManager::OnWwanEvent(WWAN_EVENT const *,_GUID const *)

- ea: `0x180086f30`
- end: `0x180087a6f`
- name: `?OnWwanEvent@CWwanManager@@UEAAXPEBUWWAN_EVENT@@PEBU_GUID@@@Z`
- size: `2879`
- prototype: `void __fastcall(CWwanManager *__hidden this, const struct WWAN_EVENT *, const struct _GUID *)`
- caller_count: `0`
- callee_count: `38`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800085d0`
- `0x18000a32c`
- `0x180011650`
- `0x180012300`
- `0x180014f1c`
- `0x180015d6c`
- `0x180016c50`
- `0x180018abc`
- `0x180019e08`
- `0x18001d640`
- `0x18001e9b4`
- `0x18001e9f0`
- `0x180021df8`
- `0x180030230`
- `0x180072f68`
- `0x180073498`
- `0x180074408`
- `0x180074758`
- `0x180074cec`
- `0x180076810`
- `0x1800769a4`
- `0x180076a20`
- `0x180076fb0`
- `0x18007cbb8`
- `0x180086f30`
- `0x180087a78`
- `0x180087c38`
- `0x180087fc4`
- `0x1800881f0`
- `0x180088544`
- `0x180088640`
- `0x1800886b4`
- `0x180088a28`
- `0x180088ac8`
- `0x180088f64`
- `0x18008922c`
- `0x180093260`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180087959`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180087959`

## string_xrefs

- `0x1800871e6`: `WwanEventCodeDeviceServices (type %d) size %d is less than                                 expected %d`
- `0x1800873ff`: ` WwanEventCodeDeviceServices: Not a QC based Modem - marking as WWAN_INTF_TYPE_MBIM_1`
- `0x18008720c`: ` WwanEventCodeDeviceServices (type %d)`
- `0x1800872e5`: `[%u] WwanQueryDeviceServiceCommand _WinPhoneExtensionCommandIDModemExecutorNumber failed`
- `0x18008726a`: `WwanEventCodeDeviceServices: Intf GUID does not map to a CWwanNetworkInterface`
- `0x18008738f`: ` WWAN_DEVICE_CAPS comes before EventCodeDeviceServices. Setting MaxContextsBitMask`
- `0x18008735d`: `[%u] WwanQueryDeviceServiceCommand _WinPhoneExtensionCommandIDMaxCntxtNumber failed`
- `0x1800873dc`: `Error [%u] WwanQueryDeviceServiceCommand _WinPhoneExtensionCommandIDModemDualSIMCap failed`
- `0x1800873a9`: ` WWAN_DEVICE_CAPS comes after EventCodeDeviceServices. MaxContextsBitMask to be set`
- `0x1800871bd`: `WwanEventCodeDeviceServiceCommand (type %d) size %d is less than expected %d`
- `0x180087110`: ` WwanEventCodeDeviceServiceResponse (type %d)`
- `0x18008706c`: `WwanEventCodeDeviceServiceEvent (type %d)`
- `0x180087941`: ` Received last WwanEventCodePreshutdown response - Preshutdown is complete`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CWwanManager::OnWwanEvent(HANDLE *this, const struct WWAN_EVENT *a2, const struct _GUID *a3)
{
  int v6; // ecx
  struct CWwanNetworkInterface *v7; // rcx
  const struct _GUID *v8; // rdx
  unsigned int v9; // ebx
  unsigned int v10; // r15d
  unsigned int *v11; // r8
  unsigned int v12; // eax
  __int64 v13; // r9
  const struct _GUID *v14; // rdx
  __int64 v15; // rax
  int v16; // ecx
  const unsigned __int16 *v17; // r8
  __int64 v18; // r9
  __int64 v19; // r8
  unsigned int i; // ecx
  __int64 v21; // rax
  struct CWwanNetworkInterface *v22; // rax
  struct CWwanNetworkInterface *v23; // rbx
  const unsigned __int16 *v24; // r8
  __int64 v25; // r8
  struct CWwanNetworkInterface *v26; // rax
  unsigned int DeviceServiceCommand; // eax
  __int64 v28; // r9
  struct CWwanNetworkInterface *v29; // rax
  unsigned int v30; // eax
  struct CWwanNetworkInterface *v31; // rax
  int v32; // eax
  const unsigned __int16 *v33; // r8
  const struct _GUID *v34; // rdx
  unsigned int v35; // r9d
  int v36; // r9d
  unsigned int v37; // eax
  unsigned int v38; // eax
  struct CWwanNetworkInterface *v39; // rax
  int v40; // ecx
  int v41; // ecx
  int v42; // ecx
  int v43; // ecx
  __int64 v44; // r9
  __int64 v45; // rdx
  unsigned int v46; // eax
  const unsigned __int16 *v47; // r8
  const struct _GUID *v48; // rdx
  int v49; // r9d
  struct CWwanNetworkInterface *Interface; // rax
  struct CWwanNetworkInterface *v51; // rbx
  unsigned int v52; // eax
  struct CWwanNetworkInterface *v53; // rcx
  __int64 v54; // rbx
  __int64 ExecutorFromInterfaceGuid; // rax
  struct CWwanManager *Instance; // rax
  __int64 v57; // [rsp+20h] [rbp-E0h]
  __int64 v58; // [rsp+28h] [rbp-D8h]
  struct _GUID v59; // [rsp+50h] [rbp-B0h] BYREF
  std::_Ref_count_base *v60[2]; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v61[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v62; // [rsp+90h] [rbp-70h]
  _BYTE v63[40]; // [rsp+A0h] [rbp-60h] BYREF
  char v64[32]; // [rsp+C8h] [rbp-38h] BYREF
  char v65[32]; // [rsp+E8h] [rbp-18h] BYREF
  char v66[32]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v67; // [rsp+128h] [rbp+28h]
  char v68[32]; // [rsp+130h] [rbp+30h] BYREF

  *(_OWORD *)v60 = 0;
  WwanLog::Enter("CWwanManager::OnWwanEvent");
  if ( !a2 || !a3 )
  {
    WwanLog::Error("CWwanManager::OnWwanEvent", 0, L"pEvent or pInterfaceGuid is NULL");
    WwanLog::Exit("CWwanManager::OnWwanEvent");
    return;
  }
  WwanLog::Info("CWwanManager::OnWwanEvent", 0, L" pEvent->code: %u", *((unsigned int *)a2 + 1));
  v6 = *((_DWORD *)a2 + 1);
  if ( v6 > 42 )
  {
    v40 = v6 - 44;
    if ( !v40 )
    {
      if ( *(_DWORD *)a2 == 1 )
      {
        wwan::unique_autoref_tx::unique_autoref_tx((wwan::unique_autoref_tx *)&v59, *((void **)a2 + 3));
        v54 = *(_QWORD *)&v59.Data1;
        WwanLog::Info(
          "CWwanManager::OnWwanEvent",
          0,
          L" Received WwanEventCodePreshutdown response { RequestId : %d }",
          *(unsigned int *)(*(_QWORD *)&v59.Data1 + 52LL));
        std::list<unsigned long>::remove(this + 35, v54 + 52);
        if ( !this[36] )
        {
          WwanLog::Info(
            "CWwanManager::OnWwanEvent",
            0,
            L" Received last WwanEventCodePreshutdown response - Preshutdown is complete");
          SetEvent(this[37]);
        }
        wwan::unique_autoref_tx::~unique_autoref_tx((wwan::unique_autoref_tx *)&v59);
      }
      goto LABEL_148;
    }
    v41 = v40 - 13;
    if ( v41 )
    {
      v42 = v41 - 1;
      if ( !v42 )
      {
        if ( *(_DWORD *)a2 != 1 || *((_DWORD *)a2 + 4) != 1 )
        {
          v32 = *((_DWORD *)a2 + 4);
          v28 = *(unsigned int *)a2;
          v33 = L"WwanEventCodeDeviceCapsEx not query response (type %d setQueryType %d). Ignored";
          v34 = a3;
LABEL_133:
          WwanLog::Info("CWwanManager::OnWwanEvent", v34, v33, v28, v32);
          goto LABEL_148;
        }
        v49 = *((_DWORD *)a2 + 8);
        v14 = a3;
        if ( v49 == -1073479647 )
        {
          WwanLog::Error(
            "CWwanManager::OnWwanEvent",
            a3,
            L"WwanEventCodeDeviceCapsEx query timed out reqHandle 0x%x ",
            *((_QWORD *)a2 + 3));
          CWwanManager::ProcessDevCapsQueryTimeout((CWwanManager *)this, a3, *((void **)a2 + 3));
          goto LABEL_148;
        }
        if ( !v49 )
        {
          v12 = *((_DWORD *)a2 + 22);
          if ( v12 >= 0x1C0 )
          {
            CWwanManager::ProcessDevCapsEx((CWwanManager *)this, a3, (const struct WWAN_EVENT *)((char *)a2 + 92), 0);
            goto LABEL_148;
          }
          v58 = 448;
          v13 = 1;
          v17 = L"WwanEventCodeDeviceCapsEx (type %d) size %d is less than                                expected %d";
          goto LABEL_94;
        }
        WwanLog::Error(
          "CWwanManager::OnWwanEvent",
          a3,
          L"WwanEventCodeDeviceCapsEx query failed 0x%x reqHandle 0x%x. Will resort to DeviceCaps query");
        Interface = CWwanManager::GetInterface((CWwanManager *)this, a3);
        v51 = Interface;
        if ( Interface )
        {
          *((_DWORD *)Interface + 172) = 0;
          *(_QWORD *)&v59.Data1 = -1;
          memset(v61, 0, sizeof(v61));
          v62 = 0;
          v52 = WwanTxmSendReqFromSource(a3, 0, 0, 1, v61, 0, 0, &v59, -1);
          if ( v52 )
          {
            WwanLog::Error("CWwanManager::OnWwanEvent", 0, L"dim-get-device-caps failed [%d]", v52);
            return;
          }
          *((_QWORD *)v51 + 100) = *(_QWORD *)&v59.Data1;
          goto LABEL_148;
        }
        v24 = L"pInterface->SetReqHandlePendDeviceCap returned nullptr";
LABEL_52:
        WwanLog::Error("CWwanManager::OnWwanEvent", a3, v24);
        goto LABEL_148;
      }
      v43 = v42 - 8;
      if ( v43 )
      {
        if ( v43 == 1 )
          WwanLog::Info("CWwanManager::OnWwanEvent", a3, L" WwanEventCodeMPDPList ignored");
        goto LABEL_148;
      }
      if ( !CWwanManager::GetInterface((CWwanManager *)this, a3) )
      {
        v24 = L"WwanEventCodeMPDPState: Intf GUID does not map to a CWwanNetworkInterface";
        goto LABEL_52;
      }
      if ( *(_DWORD *)a2 == 1 && !*((_DWORD *)a2 + 4) )
      {
        v44 = *((unsigned int *)a2 + 8);
        if ( (_DWORD)v44 )
        {
          WwanLog::Error(
            "CWwanManager::OnWwanEvent",
            a3,
            L"WwanEventCodeMPDPState failure response 0x%x reqHandle 0x%p",
            v44,
            *((_QWORD *)a2 + 3));
          goto LABEL_148;
        }
        v12 = *((_DWORD *)a2 + 22);
        if ( v12 >= 0x1C )
        {
          if ( *((_DWORD *)a2 + 23) )
          {
            v59 = (struct _GUID)*((_OWORD *)a2 + 6);
            CWwanManager::DeviceRemovalHandler((CWwanManager *)this, &v59);
          }
          else
          {
            memset(v63, 0, sizeof(v63));
            std::wstring::wstring(v64);
            std::wstring::wstring(v65);
            std::wstring::wstring(v66);
            v67 = 0;
            std::wstring::wstring(v68);
            v63[0] = 1;
            v63[1] = *(_BYTE *)(v45 + 25) != 0;
            *(struct _GUID *)&v63[20] = *a3;
            v46 = CWwanManager::AddInterfaceToList(
                    (CWwanManager *)this,
                    (const struct _GUID *)a2 + 6,
                    (const struct PnpDeviceProperties *)v63);
            if ( v46 )
              WwanLog::Error(
                "CWwanManager::OnWwanEvent",
                a3,
                L"WwanEventCodeMPDPState: [%u] failed in adding interface to list",
                v46);
            else
              CWwanManager::ChildDeviceArrivalHandler((CWwanManager *)this, a3, (const struct _GUID *)a2 + 6);
            PnpDeviceProperties::~PnpDeviceProperties((PnpDeviceProperties *)v63);
          }
          goto LABEL_148;
        }
        v58 = 28;
        v13 = 1;
        v17 = L"WwanEventCodeMPDPState (type %d) size %d is less than                                expected %d";
LABEL_93:
        v14 = a3;
        goto LABEL_94;
      }
      v47 = L"WwanEventCodeMPDPState invalid type (%d) or invalid setQueryType (%d)";
      v48 = a3;
    }
    else
    {
      if ( *(_DWORD *)a2 == 1 && *((_DWORD *)a2 + 4) == 1 )
      {
        if ( *((_DWORD *)a2 + 8) )
        {
          v53 = CWwanManager::GetInterface((CWwanManager *)this, a3);
          if ( v53 )
            *((_WORD *)v53 + 504) |= 0x100u;
          goto LABEL_148;
        }
        v12 = *((_DWORD *)a2 + 22);
        if ( v12 >= 0x18 )
        {
          CWwanManager::ProcessSysCaps((CWwanManager *)this, a3, (const struct WWAN_EVENT *)((char *)a2 + 92), 0);
          goto LABEL_148;
        }
        v58 = 24;
        v13 = 1;
        v17 = L"WwanEventCodeSysCap (type %d) size %d is less than                                expected %d";
        v14 = 0;
        goto LABEL_94;
      }
      v47 = L"WwanEventCodeSysCap invalid type (%d) or invalid setQueryType (%d)";
      v48 = 0;
    }
    WwanLog::Error("CWwanManager::OnWwanEvent", v48, v47, *(unsigned int *)a2, *((_DWORD *)a2 + 4));
    goto LABEL_148;
  }
  switch ( v6 )
  {
    case 42:
      v39 = CWwanManager::GetInterface((CWwanManager *)this, a3);
      v8 = a3;
      if ( !v39 )
      {
        WwanLog::Error(
          "CWwanManager::OnWwanEvent",
          a3,
          L"WwanEventCodeDevicePowerStateD3Exit: Intf GUID does not map to a CWwanNetworkInterface");
        break;
      }
      *((_DWORD *)v39 + 207) = 1;
      goto LABEL_18;
    case 0:
      if ( *(_DWORD *)a2 == 1 && *((_DWORD *)a2 + 4) == 1 )
      {
        v36 = *((_DWORD *)a2 + 8);
        if ( v36 == -1073479647 )
        {
          WwanLog::Error(
            "CWwanManager::OnWwanEvent",
            a3,
            L"WwanEventCodeDeviceCaps query timed out reqHandle 0x%x ",
            *((_QWORD *)a2 + 3));
          CWwanManager::ProcessDevCapsQueryTimeout((CWwanManager *)this, a3, *((void **)a2 + 3));
        }
        else if ( v36 )
        {
          v57 = *((_QWORD *)a2 + 3);
          WwanLog::Error("CWwanManager::OnWwanEvent", a3, L"WwanEventCodeDeviceCaps query failed 0x%x reqHandle 0x%x ");
        }
        else
        {
          v37 = *((_DWORD *)a2 + 22);
          if ( v37 > 8 )
          {
            v38 = v37 - 8;
            if ( v38 >= 0x14C && (*((_BYTE *)a2 + 93) == 1 || v38 >= 0x158 && *((_BYTE *)a2 + 93) >= 2u) )
            {
              CWwanManager::ProcessDeviceCaps((CWwanManager *)this, a3, (const struct WWAN_EVENT *)((char *)a2 + 92));
              break;
            }
          }
        }
      }
      else
      {
        WwanLog::Info(
          "CWwanManager::OnWwanEvent",
          a3,
          L"WwanEventCodeDeviceCaps not query response (type %d setQueryType %d). Ignored",
          *(unsigned int *)a2,
          *((_DWORD *)a2 + 4));
      }
      v58 = 352;
      v12 = *((_DWORD *)a2 + 22);
      v13 = *(unsigned int *)a2;
      v17 = L"WwanEventCodeDeviceCaps (type %d) size %d is less than                                expected %d";
      goto LABEL_93;
    case 12:
      v35 = 0;
      if ( *(_DWORD *)a2 == 1 )
        v35 = *((_DWORD *)a2 + 8);
      if ( *((_DWORD *)a2 + 22) < 0x100u )
        WwanLog::Error(
          "CWwanManager::OnWwanEvent",
          a3,
          L"Received a data buffer too small for WWAN_CONTEXT_STATE in  WwanEventCodeContextState event: pEvent->dataSize:"
           " %d, sizeof(WWAN_CONTEXT_STATE): %d",
          *((unsigned int *)a2 + 22),
          256);
      else
        CWwanManager::ProcessContextStateEvent(
          (CWwanManager *)this,
          a3,
          (const struct WWAN_EVENT *)((char *)a2 + 92),
          v35);
      break;
    case 27:
      v18 = *(unsigned int *)a2;
      if ( *((_DWORD *)a2 + 22) < 0x14u )
      {
        WwanLog::Error(
          "CWwanManager::OnWwanEvent",
          0,
          L"WwanEventCodeDeviceServices (type %d) size %d is less than                                 expected %d",
          v18,
          *((_DWORD *)a2 + 22),
          20);
        v19 = 1;
LABEL_41:
        CWwanManager::UpdateWwanInterfaceType(this, a3, v19);
        break;
      }
      WwanLog::Info("CWwanManager::OnWwanEvent", 0, L" WwanEventCodeDeviceServices (type %d)", v18);
      if ( a2 == (const struct WWAN_EVENT *)-92LL || !*((_DWORD *)a2 + 27) )
      {
LABEL_73:
        WwanLog::Info(
          "CWwanManager::OnWwanEvent",
          0,
          L" WwanEventCodeDeviceServices: Not a QC based Modem - marking as WWAN_INTF_TYPE_MBIM_1");
        v19 = 4;
        goto LABEL_41;
      }
      for ( i = 0; ; ++i )
      {
        if ( i >= *((_DWORD *)a2 + 27) )
          goto LABEL_73;
        v21 = WinPhoneExtensionDeviceServiceGuid - *((_QWORD *)a2 + 14);
        if ( (_QWORD)WinPhoneExtensionDeviceServiceGuid == *((_QWORD *)a2 + 14) )
          v21 = *((_QWORD *)&WinPhoneExtensionDeviceServiceGuid + 1) - *((_QWORD *)a2 + 15);
        if ( !v21 )
          break;
      }
      v22 = CWwanManager::GetInterface((CWwanManager *)this, a3);
      v23 = v22;
      if ( !v22 )
      {
        v24 = L"WwanEventCodeDeviceServices: Intf GUID does not map to a CWwanNetworkInterface";
        goto LABEL_52;
      }
      if ( *((_DWORD *)v22 + 52) == 2 )
      {
        if ( *((_DWORD *)v22 + 53) >= 0x9Bu )
        {
LABEL_55:
          v25 = 3;
LABEL_56:
          CWwanManager::UpdateWwanInterfaceType(this, a3, v25);
          if ( !(unsigned int)CWwanManager::_IsRilBasedModem(*((unsigned int *)v23 + 50)) )
            break;
          v26 = CWwanManager::GetInterface((CWwanManager *)this, a3);
          DeviceServiceCommand = CWwanManager::WwanQueryDeviceServiceCommand((CWwanManager *)this, v26, 0xBEEF1005);
          if ( DeviceServiceCommand )
            WwanLog::Error(
              "CWwanManager::OnWwanEvent",
              0,
              L"[%u] WwanQueryDeviceServiceCommand _WinPhoneExtensionCommandIDModemExecutorNumber failed",
              DeviceServiceCommand);
          v28 = *((unsigned int *)v23 + 52);
          if ( (unsigned int)v28 < 2 || (_DWORD)v28 == 2 && *((_DWORD *)v23 + 53) < 0x64u )
          {
            v32 = *((_DWORD *)v23 + 53);
            v33 = L" Apollo BSP (major %d minor %d)";
            v34 = 0;
            goto LABEL_133;
          }
          WwanLog::Info("CWwanManager::OnWwanEvent", 0, L"BSP (major %d minor %d)");
          if ( *((_DWORD *)v23 + 50) == 3 )
          {
            if ( (*((_BYTE *)v23 + 1008) & 2) != 0 )
            {
              WwanLog::Info(
                "CWwanManager::OnWwanEvent",
                0,
                L" WWAN_DEVICE_CAPS comes before EventCodeDeviceServices. Setting MaxContextsBitMask");
              *((_WORD *)v23 + 504) |= 0x10u;
            }
            else
            {
              WwanLog::Info(
                "CWwanManager::OnWwanEvent",
                0,
                L" WWAN_DEVICE_CAPS comes after EventCodeDeviceServices. MaxContextsBitMask to be set");
            }
          }
          else
          {
            v29 = CWwanManager::GetInterface((CWwanManager *)this, a3);
            v30 = CWwanManager::WwanQueryDeviceServiceCommand((CWwanManager *)this, v29, 0xBEEF1009);
            if ( v30 )
              WwanLog::Error(
                "CWwanManager::OnWwanEvent",
                0,
                L"[%u] WwanQueryDeviceServiceCommand _WinPhoneExtensionCommandIDMaxCntxtNumber failed",
                v30);
          }
          v31 = CWwanManager::GetInterface((CWwanManager *)this, a3);
          if ( CWwanManager::WwanQueryDeviceServiceCommand((CWwanManager *)this, v31, 0xBEEF1008) )
            WwanLog::Error(
              "CWwanManager::OnWwanEvent",
              0,
              L"Error [%u] WwanQueryDeviceServiceCommand _WinPhoneExtensionCommandIDModemDualSIMCap failed");
          break;
        }
      }
      else if ( *((_DWORD *)v22 + 52) >= 2u )
      {
        goto LABEL_55;
      }
      v25 = 2;
      goto LABEL_56;
    case 29:
      v12 = *((_DWORD *)a2 + 22);
      v13 = *(unsigned int *)a2;
      v14 = 0;
      if ( v12 >= 0x18 )
      {
        WwanLog::Info("CWwanManager::OnWwanEvent", 0, L" WwanEventCodeDeviceServiceResponse (type %d)", v13);
        v15 = WinPhoneExtensionDeviceServiceGuid - *(_QWORD *)((char *)a2 + 92);
        if ( (_QWORD)WinPhoneExtensionDeviceServiceGuid == *(_QWORD *)((char *)a2 + 92) )
          v15 = *((_QWORD *)&WinPhoneExtensionDeviceServiceGuid + 1) - *(_QWORD *)((char *)a2 + 100);
        if ( v15 )
          break;
        v16 = *((_DWORD *)a2 + 27);
        v11 = (unsigned int *)((char *)a2 + 116);
        if ( ((v16 + 1091629051) & 0xEFFFFFFF) == 0 && *((_DWORD *)a2 + 28) >= 8u )
        {
          CWwanManager::UpdateWwanModemExecutorId((CWwanManager *)this, a3, *v11, *((_DWORD *)a2 + 30));
          break;
        }
        if ( ((v16 + 1091629047) & 0xEFFFFFFF) == 0 && *((_DWORD *)a2 + 28) >= 4u )
        {
          CWwanManager::UpdateWwanMaxNumContextsPerExecutor((CWwanManager *)this, a3, *v11);
          break;
        }
        if ( ((v16 + 1091629048) & 0xEFFFFFFF) != 0 || *((_DWORD *)a2 + 28) < 0x10u )
          break;
LABEL_23:
        CWwanManager::UpdateWwanModemMultiSimCapabilities(
          (CWwanManager *)this,
          a3,
          (struct WWAN_WINPHONE_MODEMTYPE_CAP *)v11);
        break;
      }
      v58 = 24;
      v17 = L"WwanEventCodeDeviceServiceCommand (type %d) size %d is less than expected %d";
LABEL_94:
      LODWORD(v57) = v12;
      WwanLog::Error("CWwanManager::OnWwanEvent", v14, v17, v13, v57, v58);
      break;
    case 31:
      v9 = *((_DWORD *)a2 + 27);
      v10 = *((_DWORD *)a2 + 28);
      WwanLog::Info("CWwanManager::OnWwanEvent", 0, L"WwanEventCodeDeviceServiceEvent (type %d)", *(unsigned int *)a2);
      if ( v9 != -554758139 && v9 != -1091629048 || v10 < 0x10 )
      {
        WwanLog::Verbose("CWwanManager::OnWwanEvent", 0, L"0x%x DSEvent PLSize %d", v9, v10);
        break;
      }
      WwanLog::Info(
        "CWwanManager::OnWwanEvent",
        0,
        L" ModemDualSIMCap DSEvent PLSize 0x%x fTypeKnown 0x%x nExecutors 0x%x                               nActiveExecut"
         "ors 0x%x nActiveDataExecutors 0x%x",
        v10,
        *((_DWORD *)a2 + 29),
        *((_DWORD *)a2 + 30),
        *((_DWORD *)a2 + 31),
        *((_DWORD *)a2 + 32));
      v11 = (unsigned int *)((char *)a2 + 116);
      goto LABEL_23;
    case 40:
      if ( *(_DWORD *)a2 != 2 )
      {
        WwanLog::Error("CWwanManager::OnWwanEvent", 0, L"WwanEventCodeDevicePowerState: Unexpected Response Header");
        break;
      }
      if ( *((_DWORD *)a2 + 22) < 4u )
      {
        WwanLog::Error("CWwanManager::OnWwanEvent", 0, L"WwanEventCodeDevicePowerState: Invalid event size (%u)");
        break;
      }
      WwanLog::Verbose(
        "CWwanManager::OnWwanEvent",
        a3,
        L"WwanEventCodeDevicePowerState: Power state: D%d",
        *((unsigned int *)a2 + 23));
      v7 = CWwanManager::GetInterface((CWwanManager *)this, a3);
      v8 = a3;
      if ( !v7 )
      {
        WwanLog::Error(
          "CWwanManager::OnWwanEvent",
          a3,
          L"WwanEventCodeDevicePowerState: Intf GUID does not map to a CWwanNetworkInterface");
        break;
      }
      *((_DWORD *)v7 + 206) = *((_DWORD *)a2 + 23);
LABEL_18:
      CWwanManager::resetInterface((CWwanManager *)this, v8);
      break;
  }
LABEL_148:
  ExecutorFromInterfaceGuid = CWwanManager::GetExecutorFromInterfaceGuid(this, &v59, a3);
  std::shared_ptr<ProfileHolder>::operator=(v60, ExecutorFromInterfaceGuid);
  if ( *(_QWORD *)v59.Data4 )
    std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)v59.Data4);
  if ( v60[0] )
    (*(void (__fastcall **)(std::_Ref_count_base *, const struct WWAN_EVENT *, const struct _GUID *))(*(_QWORD *)v60[0] + 416LL))(
      v60[0],
      a2,
      a3);
  else
    WwanLog::Verbose("CWwanManager::OnWwanEvent", a3, L"pInterfaceGuid doesn't belong to any Executor");
  Instance = CWwanManager::GetInstance();
  CWwanManager::GetRnRObjectForInterfaceGuid(Instance, &v59, a3);
  if ( (unsigned __int8)std::operator==<_TRAFFIC_DESCRIPTOR>(&v59) )
    WwanLog::Warning("CWwanManager::OnWwanEvent", a3, L"RnR Object not found for given interface");
  else
    CWwanResetRecovery::OnNdisNotification(*(CWwanResetRecovery **)&v59.Data1, a2);
  WwanLog::Exit("CWwanManager::OnWwanEvent");
  if ( *(_QWORD *)v59.Data4 )
    std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)v59.Data4);
  if ( v60[1] )
    std::_Ref_count_base::_Decref(v60[1]);
}

```

## disassembly

```asm
0x180086f30  push    rbp
0x180086f32  push    rbx
0x180086f33  push    rsi
0x180086f34  push    rdi
0x180086f35  push    r12
0x180086f37  push    r14
0x180086f39  push    r15
0x180086f3b  lea     rbp, [rsp-60h]
0x180086f40  sub     rsp, 160h
0x180086f47  mov     rax, cs:__security_cookie
0x180086f4e  xor     rax, rsp
0x180086f51  mov     [rbp+90h+var_40], rax
0x180086f55  mov     rsi, r8
0x180086f58  mov     rdi, rdx
0x180086f5b  mov     r14, rcx
0x180086f5e  xorps   xmm0, xmm0
0x180086f61  movdqu  xmmword ptr [rsp+190h+var_130], xmm0
0x180086f67  lea     r12, aCwwanmanagerOn_2; "CWwanManager::OnWwanEvent"
0x180086f6e  mov     rcx, r12; char *
0x180086f71  call    ?Enter@WwanLog@@SAXPEBD@Z; WwanLog::Enter(char const *)
0x180086f76  test    rdi, rdi
0x180086f79  jz      loc_180087A37
0x180086f7f  test    rsi, rsi
0x180086f82  jz      loc_180087A37
0x180086f88  mov     r9d, [rdi+4]
0x180086f8c  lea     r8, aPeventCodeU; " pEvent->code: %u"
0x180086f93  xor     edx, edx; struct _GUID *
0x180086f95  mov     rcx, r12; char *
0x180086f98  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180086f9d  mov     ecx, [rdi+4]
0x180086fa0  cmp     ecx, 2Ah ; '*'
0x180086fa3  jg      loc_180087572
0x180086fa9  jz      loc_180087544
0x180086faf  test    ecx, ecx
0x180086fb1  jz      loc_18008745A
0x180086fb7  cmp     ecx, 0Ch
0x180086fba  jz      loc_18008741B
0x180086fc0  cmp     ecx, 1Bh
0x180086fc3  jz      loc_1800871C9
0x180086fc9  cmp     ecx, 1Dh
0x180086fcc  jz      loc_1800870FC
0x180086fd2  cmp     ecx, 1Fh
0x180086fd5  jz      loc_180087062
0x180086fdb  cmp     ecx, 28h ; '('
0x180086fde  jnz     loc_180087969
0x180086fe4  cmp     dword ptr [rdi], 2
0x180086fe7  jz      short loc_180086FF7
0x180086fe9  lea     r8, aWwaneventcoded_10; "WwanEventCodeDevicePowerState: Unexpect"...
0x180086ff0  xor     edx, edx
0x180086ff2  jmp     loc_180087274
0x180086ff7  mov     r9d, [rdi+58h]
0x180086ffb  mov     rcx, r12; char *
0x180086ffe  cmp     r9d, 4
0x180087002  jnb     short loc_180087017
0x180087004  lea     r8, aWwaneventcoded_23; "WwanEventCodeDevicePowerState: Invalid "...
0x18008700b  xor     edx, edx; struct _GUID *
0x18008700d  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180087012  jmp     loc_180087969
0x180087017  mov     r9d, [rdi+5Ch]
0x18008701b  lea     r8, aWwaneventcoded_20; "WwanEventCodeDevicePowerState: Power st"...
0x180087022  mov     rdx, rsi; struct _GUID *
0x180087025  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x18008702a  mov     rdx, rsi; struct _GUID *
0x18008702d  mov     rcx, r14; this
0x180087030  call    ?GetInterface@CWwanManager@@AEAAPEAVCWwanNetworkInterface@@PEBU_GUID@@@Z; CWwanManager::GetInterface(_GUID const *)
0x180087035  mov     rcx, rax
0x180087038  mov     rdx, rsi; struct _GUID *
0x18008703b  test    rax, rax
0x18008703e  jnz     short loc_18008704C
0x180087040  lea     r8, aWwaneventcoded_13; "WwanEventCodeDevicePowerState: Intf GUI"...
0x180087047  jmp     loc_180087274
0x18008704c  mov     eax, [rdi+5Ch]
0x18008704f  mov     [rcx+338h], eax
0x180087055  mov     rcx, r14; this
0x180087058  call    ?resetInterface@CWwanManager@@AEAAXPEBU_GUID@@@Z; CWwanManager::resetInterface(_GUID const *)
0x18008705d  jmp     loc_180087969
0x180087062  mov     ebx, [rdi+6Ch]
0x180087065  mov     r15d, [rdi+70h]
0x180087069  mov     r9d, [rdi]
0x18008706c  lea     r8, aWwaneventcoded_17; "WwanEventCodeDeviceServiceEvent (type %"...
0x180087073  xor     edx, edx; struct _GUID *
0x180087075  mov     rcx, r12; char *
0x180087078  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18008707d  cmp     ebx, 0DEEF1005h
0x180087083  jz      short loc_18008708D
0x180087085  cmp     ebx, 0BEEF1008h
0x18008708b  jnz     short loc_1800870DE
0x18008708d  mov     eax, 10h
0x180087092  cmp     r15d, eax
0x180087095  jb      short loc_1800870DE
0x180087097  mov     eax, [rdi+80h]
0x18008709d  mov     dword ptr [rsp+190h+var_158], eax
0x1800870a1  mov     eax, [rdi+7Ch]
0x1800870a4  mov     dword ptr [rsp+190h+var_160], eax
0x1800870a8  mov     eax, [rdi+78h]
0x1800870ab  mov     dword ptr [rsp+190h+var_168], eax
0x1800870af  mov     eax, [rdi+74h]
0x1800870b2  mov     dword ptr [rsp+190h+var_170], eax
0x1800870b6  mov     r9d, r15d
0x1800870b9  lea     r8, aModemdualsimca_0; " ModemDualSIMCap DSEvent PLSize 0x%x fT"...
0x1800870c0  xor     edx, edx; struct _GUID *
0x1800870c2  mov     rcx, r12; char *
0x1800870c5  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800870ca  lea     r8, [rdi+74h]; struct WWAN_WINPHONE_MODEMTYPE_CAP *
0x1800870ce  mov     rdx, rsi; struct _GUID *
0x1800870d1  mov     rcx, r14; this
0x1800870d4  call    ?UpdateWwanModemMultiSimCapabilities@CWwanManager@@AEAAXPEBU_GUID@@PEAUWWAN_WINPHONE_MODEMTYPE_CAP@@@Z; CWwanManager::UpdateWwanModemMultiSimCapabilities(_GUID const *,WWAN_WINPHONE_MODEMTYPE_CAP *)
0x1800870d9  jmp     loc_180087969
0x1800870de  mov     dword ptr [rsp+190h+var_170], r15d
0x1800870e3  mov     r9d, ebx
0x1800870e6  lea     r8, a0xXDseventPlsi; "0x%x DSEvent PLSize %d"
0x1800870ed  xor     edx, edx; struct _GUID *
0x1800870ef  mov     rcx, r12; char *
0x1800870f2  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800870f7  jmp     loc_180087969
0x1800870fc  mov     eax, [rdi+58h]
0x1800870ff  mov     r9d, [rdi]
0x180087102  xor     edx, edx; struct _GUID *
0x180087104  mov     rcx, r12; char *
0x180087107  cmp     eax, 18h
0x18008710a  jb      loc_1800871B4
0x180087110  lea     r8, aWwaneventcoded_22; " WwanEventCodeDeviceServiceResponse (ty"...
0x180087117  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18008711c  mov     rax, qword ptr cs:_WinPhoneExtensionDeviceServiceGuid
0x180087123  sub     rax, [rdi+5Ch]
0x180087127  jnz     short loc_180087134
0x180087129  mov     rax, qword ptr cs:_WinPhoneExtensionDeviceServiceGuid+8
0x180087130  sub     rax, [rdi+64h]
0x180087134  test    rax, rax
0x180087137  jnz     loc_180087969
0x18008713d  mov     ecx, [rdi+6Ch]
0x180087140  lea     r8, [rdi+74h]
0x180087144  lea     eax, [rcx+4110EFFBh]
0x18008714a  mov     edx, 0EFFFFFFFh
0x18008714f  test    edx, eax
0x180087151  jnz     short loc_180087170
0x180087153  cmp     dword ptr [rdi+70h], 8
0x180087157  jb      short loc_180087170
0x180087159  mov     r9d, [r8+4]; unsigned int
0x18008715d  mov     r8d, [r8]; unsigned int
0x180087160  mov     rdx, rsi; struct _GUID *
0x180087163  mov     rcx, r14; this
0x180087166  call    ?UpdateWwanModemExecutorId@CWwanManager@@AEAAXPEBU_GUID@@KK@Z; CWwanManager::UpdateWwanModemExecutorId(_GUID const *,ulong,ulong)
0x18008716b  jmp     loc_180087969
0x180087170  lea     eax, [rcx+4110EFF7h]
0x180087176  test    edx, eax
0x180087178  jnz     short loc_180087193
0x18008717a  cmp     dword ptr [rdi+70h], 4
0x18008717e  jb      short loc_180087193
0x180087180  mov     r8d, [r8]; unsigned int
0x180087183  mov     rdx, rsi; struct _GUID *
0x180087186  mov     rcx, r14; this
0x180087189  call    ?UpdateWwanMaxNumContextsPerExecutor@CWwanManager@@AEAAXPEBU_GUID@@K@Z; CWwanManager::UpdateWwanMaxNumContextsPerExecutor(_GUID const *,ulong)
0x18008718e  jmp     loc_180087969
0x180087193  lea     eax, [rcx+4110EFF8h]
0x180087199  test    edx, eax
0x18008719b  jnz     loc_180087969
0x1800871a1  mov     eax, 10h
0x1800871a6  cmp     [rdi+70h], eax
0x1800871a9  jb      loc_180087969
0x1800871af  jmp     loc_1800870CE
0x1800871b4  mov     [rsp+190h+var_168], 18h
0x1800871bd  lea     r8, aWwaneventcoded_15; "WwanEventCodeDeviceServiceCommand (type"...
0x1800871c4  jmp     loc_180087536
0x1800871c9  mov     eax, [rdi+58h]
0x1800871cc  mov     r9d, [rdi]
0x1800871cf  xor     edx, edx; struct _GUID *
0x1800871d1  mov     rcx, r12; char *
0x1800871d4  cmp     eax, 14h
0x1800871d7  jnb     short loc_180087208
0x1800871d9  mov     [rsp+190h+var_168], 14h
0x1800871e2  mov     dword ptr [rsp+190h+var_170], eax
0x1800871e6  lea     r8, aWwaneventcoded_8; "WwanEventCodeDeviceServices (type %d) s"...
0x1800871ed  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800871f2  mov     r8d, 1
0x1800871f8  mov     rdx, rsi
0x1800871fb  mov     rcx, r14
0x1800871fe  call    ?UpdateWwanInterfaceType@CWwanManager@@AEAAXPEBU_GUID@@W4_WWAN_INTERFACE_TYPE@@@Z; CWwanManager::UpdateWwanInterfaceType(_GUID const *,_WWAN_INTERFACE_TYPE)
0x180087203  jmp     loc_180087969
0x180087208  lea     rbx, [rdi+5Ch]
0x18008720c  lea     r8, aWwaneventcoded_7; " WwanEventCodeDeviceServices (type %d)"
0x180087213  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180087218  test    rbx, rbx
0x18008721b  jz      loc_1800873FF
0x180087221  cmp     dword ptr [rbx+10h], 0
0x180087225  jbe     loc_1800873FF
0x18008722b  xor     ecx, ecx
0x18008722d  cmp     ecx, [rbx+10h]
0x180087230  jnb     loc_1800873FF
0x180087236  mov     rax, qword ptr cs:_WinPhoneExtensionDeviceServiceGuid
0x18008723d  sub     rax, [rbx+14h]
0x180087241  jnz     short loc_18008724E
0x180087243  mov     rax, qword ptr cs:_WinPhoneExtensionDeviceServiceGuid+8
0x18008724a  sub     rax, [rbx+1Ch]
0x18008724e  test    rax, rax
0x180087251  jz      short loc_180087257
0x180087253  inc     ecx
0x180087255  jmp     short loc_18008722D
0x180087257  mov     rdx, rsi; struct _GUID *
0x18008725a  mov     rcx, r14; this
0x18008725d  call    ?GetInterface@CWwanManager@@AEAAPEAVCWwanNetworkInterface@@PEBU_GUID@@@Z; CWwanManager::GetInterface(_GUID const *)
0x180087262  mov     rbx, rax
0x180087265  test    rax, rax
0x180087268  jnz     short loc_180087281
0x18008726a  lea     r8, aWwaneventcoded_6; "WwanEventCodeDeviceServices: Intf GUID "...
0x180087271  mov     rdx, rsi; struct _GUID *
0x180087274  mov     rcx, r12; char *
0x180087277  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18008727c  jmp     loc_180087969
0x180087281  cmp     dword ptr [rax+0D0h], 2
0x180087288  jnz     loc_180087370
0x18008728e  cmp     dword ptr [rax+0D4h], 9Bh
0x180087298  jb      loc_180087376
0x18008729e  mov     r8d, 3
0x1800872a4  mov     rdx, rsi
0x1800872a7  mov     rcx, r14
0x1800872aa  call    ?UpdateWwanInterfaceType@CWwanManager@@AEAAXPEBU_GUID@@W4_WWAN_INTERFACE_TYPE@@@Z; CWwanManager::UpdateWwanInterfaceType(_GUID const *,_WWAN_INTERFACE_TYPE)
0x1800872af  mov     ecx, [rbx+0C8h]
0x1800872b5  call    ?_IsRilBasedModem@CWwanManager@@SAHW4_WWAN_INTERFACE_TYPE@@@Z; CWwanManager::_IsRilBasedModem(_WWAN_INTERFACE_TYPE)
0x1800872ba  test    eax, eax
0x1800872bc  jz      loc_180087969
0x1800872c2  mov     rdx, rsi; struct _GUID *
0x1800872c5  mov     rcx, r14; this
0x1800872c8  call    ?GetInterface@CWwanManager@@AEAAPEAVCWwanNetworkInterface@@PEBU_GUID@@@Z; CWwanManager::GetInterface(_GUID const *)
0x1800872cd  mov     rdx, rax; struct CWwanNetworkInterface *
0x1800872d0  mov     r8d, 0BEEF1005h; unsigned int
0x1800872d6  mov     rcx, r14; this
0x1800872d9  call    ?WwanQueryDeviceServiceCommand@CWwanManager@@AEAAKPEAVCWwanNetworkInterface@@K@Z; CWwanManager::WwanQueryDeviceServiceCommand(CWwanNetworkInterface *,ulong)
0x1800872de  test    eax, eax
0x1800872e0  jz      short loc_1800872F6
0x1800872e2  mov     r9d, eax
0x1800872e5  lea     r8, aUWwanquerydevi_1; "[%u] WwanQueryDeviceServiceCommand _Win"...
0x1800872ec  xor     edx, edx; struct _GUID *
0x1800872ee  mov     rcx, r12; char *
0x1800872f1  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800872f6  mov     r9d, [rbx+0D0h]
0x1800872fd  cmp     r9d, 2
0x180087301  jb      loc_1800873EB
0x180087307  jnz     short loc_180087316
0x180087309  cmp     dword ptr [rbx+0D4h], 64h ; 'd'
0x180087310  jb      loc_1800873EB
0x180087316  mov     eax, [rbx+0D4h]
0x18008731c  mov     dword ptr [rsp+190h+var_170], eax
0x180087320  lea     r8, aBspMajorDMinor; "BSP (major %d minor %d)"
0x180087327  xor     edx, edx; struct _GUID *
0x180087329  mov     rcx, r12; char *
0x18008732c  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180087331  cmp     dword ptr [rbx+0C8h], 3
0x180087338  jz      short loc_180087381
0x18008733a  mov     rdx, rsi; struct _GUID *
0x18008733d  mov     rcx, r14; this
0x180087340  call    ?GetInterface@CWwanManager@@AEAAPEAVCWwanNetworkInterface@@PEBU_GUID@@@Z; CWwanManager::GetInterface(_GUID const *)
0x180087345  mov     rdx, rax; struct CWwanNetworkInterface *
0x180087348  mov     r8d, 0BEEF1009h; unsigned int
0x18008734e  mov     rcx, r14; this
0x180087351  call    ?WwanQueryDeviceServiceCommand@CWwanManager@@AEAAKPEAVCWwanNetworkInterface@@K@Z; CWwanManager::WwanQueryDeviceServiceCommand(CWwanNetworkInterface *,ulong)
0x180087356  test    eax, eax
0x180087358  jz      short loc_1800873B5
0x18008735a  mov     r9d, eax
0x18008735d  lea     r8, aUWwanquerydevi_0; "[%u] WwanQueryDeviceServiceCommand _Win"...
0x180087364  xor     edx, edx; struct _GUID *
0x180087366  mov     rcx, r12; char *
0x180087369  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18008736e  jmp     short loc_1800873B5
0x180087370  jnb     loc_18008729E
0x180087376  mov     r8d, 2
0x18008737c  jmp     loc_1800872A4
0x180087381  xor     edx, edx; struct _GUID *
0x180087383  mov     rcx, r12; char *
0x180087386  test    byte ptr [rbx+3F0h], 2
0x18008738d  jz      short loc_1800873A9
0x18008738f  lea     r8, aWwanDeviceCaps_0; " WWAN_DEVICE_CAPS comes before EventCod"...
0x180087396  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18008739b  mov     eax, 10h
0x1800873a0  or      [rbx+3F0h], ax
0x1800873a7  jmp     short loc_1800873B5
0x1800873a9  lea     r8, aWwanDeviceCaps_2; " WWAN_DEVICE_CAPS comes after EventCode"...
0x1800873b0  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800873b5  mov     rdx, rsi; struct _GUID *
0x1800873b8  mov     rcx, r14; this
0x1800873bb  call    ?GetInterface@CWwanManager@@AEAAPEAVCWwanNetworkInterface@@PEBU_GUID@@@Z; CWwanManager::GetInterface(_GUID const *)
0x1800873c0  mov     rdx, rax; struct CWwanNetworkInterface *
0x1800873c3  mov     r8d, 0BEEF1008h; unsigned int
0x1800873c9  mov     rcx, r14; this
0x1800873cc  call    ?WwanQueryDeviceServiceCommand@CWwanManager@@AEAAKPEAVCWwanNetworkInterface@@K@Z; CWwanManager::WwanQueryDeviceServiceCommand(CWwanNetworkInterface *,ulong)
0x1800873d1  test    eax, eax
0x1800873d3  jz      loc_180087969
0x1800873d9  mov     r9d, eax
0x1800873dc  lea     r8, aErrorUWwanquer; "Error [%u] WwanQueryDeviceServiceComman"...
0x1800873e3  mov     rcx, r12
0x1800873e6  jmp     loc_18008700B
0x1800873eb  mov     eax, [rbx+0D4h]
0x1800873f1  lea     r8, aApolloBspMajor_0; " Apollo BSP (major %d minor %d)"
0x1800873f8  xor     edx, edx
0x1800873fa  jmp     loc_180087857
0x1800873ff  lea     r8, aWwaneventcoded_14; " WwanEventCodeDeviceServices: Not a QC "...
0x180087406  xor     edx, edx; struct _GUID *
0x180087408  mov     rcx, r12; char *
0x18008740b  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180087410  mov     r8d, 4
  ... truncated ...
```
