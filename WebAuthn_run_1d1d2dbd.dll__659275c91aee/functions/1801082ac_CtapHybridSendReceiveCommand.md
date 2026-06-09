# CtapHybridSendReceiveCommand

- ea: `0x1801082ac`
- end: `0x180108dc6`
- name: `CtapHybridSendReceiveCommand`
- size: `2842`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `49`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180107458`

## callees

- `0x18000a210`
- `0x18000af70`
- `0x180015db0`
- `0x18001687c`
- `0x180017620`
- `0x18001cd78`
- `0x18001d5fc`
- `0x1800205e4`
- `0x180021878`
- `0x180031740`
- `0x1800350b4`
- `0x180036da4`
- `0x180037f6c`
- `0x18003c234`
- `0x180042050`
- `0x180045274`
- `0x1800467a4`
- `0x18004696c`
- `0x180046988`
- `0x180049e44`
- `0x1800524a0`
- `0x1800537a4`
- `0x18005e500`
- `0x18006b260`
- `0x18006c82c`
- `0x18006cb84`
- `0x18007969c`
- `0x180081454`
- `0x1800928d4`
- `0x18009aed0`
- `0x1800d1dbc`
- `0x1800d70ac`
- `0x1800d734c`
- `0x1800e3eb8`
- `0x1800fc5ec`
- `0x180103f98`
- `0x180103fe8`
- `0x180106c5c`
- `0x180106e74`
- `0x180106fa4`
- `0x1801071bc`
- `0x180107340`
- `0x180107524`
- `0x1801076ec`
- `0x1801082ac`
- `0x1801235dc`
- `0x18012b96c`
- `0x18012be78`
- `0x18013c090`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801087db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801089f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180108bb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801087db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801089f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180108bb2`

## string_xrefs

- `0x180108493`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybrid.cpp`
- `0x18010899c`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybrid.cpp`
- `0x180108c46`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybrid.cpp`
- `0x180108c5b`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybrid.cpp`
- `0x180108c6f`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybrid.cpp`
- `0x180108c84`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybrid.cpp`
- `0x180108c99`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybrid.cpp`
- `0x180108cae`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybrid.cpp`
- `0x180108cc6`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybrid.cpp`
- `0x180108d04`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybrid.cpp`
- `0x180108d15`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybrid.cpp`
- `0x180108d9e`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybrid.cpp`
- `0x180108db3`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybrid.cpp`
- `0x180108422`: `LinkedDevice`
- `0x1801084bf`: `CallerLinkedDevice`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CtapHybridSendReceiveCommand(_QWORD *a1)
{
  __int64 v2; // rax
  __int64 v3; // rsi
  __int64 v4; // rcx
  char v5; // r12
  char *v6; // rax
  __int64 v7; // rdx
  unsigned int v8; // r14d
  const char *v9; // r14
  int v10; // r8d
  struct _CTAPCBOR_HYBRID_STORAGE_LINKED_DATA *v11; // r8
  int v12; // r15d
  int v13; // eax
  _WORD *v14; // rax
  int v15; // r8d
  __int64 v16; // rdx
  int v17; // eax
  __int16 v18; // r13
  std::_Ref_count_base *v19; // rdx
  wil *v20; // rcx
  int v21; // eax
  std::_Ref_count_base *v22; // rdx
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm2
  __int128 v26; // xmm3
  __int128 v27; // xmm4
  __int128 v28; // xmm5
  __int64 v29; // xmm6_8
  __int64 Message; // rax
  int v31; // r9d
  unsigned int InfoMessage; // eax
  unsigned int v33; // eax
  unsigned int InfoResponse; // eax
  unsigned int v35; // eax
  __int64 v36; // r8
  HLOCAL v37; // rcx
  __int64 v38; // rax
  __int128 v39; // kr30_16
  int v40; // edx
  unsigned __int8 *v41; // rax
  int v42; // eax
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // r8
  wil::details::in1diag3 *v46; // r9
  int v47; // eax
  unsigned int v48; // r15d
  HLOCAL v49; // rcx
  wil *v50; // rcx
  __int64 result; // rax
  int v52; // r10d
  int v53; // ecx
  unsigned int updated; // eax
  HLOCAL v55; // rcx
  unsigned int v56; // eax
  unsigned int v57; // eax
  int v58; // edx
  char v59; // al
  int v60; // ecx
  const char *v61; // r9
  int v62; // eax
  void *v63; // rcx
  const char *v64; // r9
  _BYTE *v65; // rdx
  _BYTE v66[32]; // [rsp+0h] [rbp-258h] BYREF
  unsigned int v67[2]; // [rsp+20h] [rbp-238h]
  char *v68; // [rsp+28h] [rbp-230h]
  int v69; // [rsp+30h] [rbp-228h] BYREF
  HLOCAL v70; // [rsp+38h] [rbp-220h] BYREF
  __int128 v71; // [rsp+40h] [rbp-218h] BYREF
  __int64 v72; // [rsp+50h] [rbp-208h]
  std::_Ref_count_base *v73[2]; // [rsp+58h] [rbp-200h] BYREF
  const char *v74; // [rsp+68h] [rbp-1F0h] BYREF
  char v75; // [rsp+70h] [rbp-1E8h]
  __int128 v76; // [rsp+78h] [rbp-1E0h] BYREF
  __int64 v77; // [rsp+88h] [rbp-1D0h]
  __int128 v78; // [rsp+90h] [rbp-1C8h] BYREF
  __int64 v79; // [rsp+A0h] [rbp-1B8h]
  unsigned int v80[4]; // [rsp+A8h] [rbp-1B0h] BYREF
  __int64 v81; // [rsp+B8h] [rbp-1A0h]
  _QWORD *v82; // [rsp+C0h] [rbp-198h]
  _BYTE v83[24]; // [rsp+C8h] [rbp-190h] BYREF
  int v84; // [rsp+E0h] [rbp-178h] BYREF
  __int128 v85; // [rsp+E4h] [rbp-174h]
  unsigned int v86; // [rsp+F4h] [rbp-164h]
  __int64 v87; // [rsp+F8h] [rbp-160h]
  __int64 v88; // [rsp+100h] [rbp-158h]
  __int128 v89; // [rsp+108h] [rbp-150h] BYREF
  _BYTE v90[72]; // [rsp+120h] [rbp-138h] BYREF
  _BYTE v91[32]; // [rsp+168h] [rbp-F0h] BYREF
  __int128 v92; // [rsp+188h] [rbp-D0h]
  _OWORD Destination[6]; // [rsp+1A0h] [rbp-B8h] BYREF
  __int64 v94; // [rsp+200h] [rbp-58h]
  HLOCAL hMem; // [rsp+210h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  v82 = a1;
  v2 = a1[39];
  v3 = *(_QWORD *)(v2 + 56);
  if ( (*(_BYTE *)(v3 + 8) & 0x20) != 0 && (a1[9] || *(_QWORD *)(v3 + 184)) )
  {
    try
    {
      CtapHybridInternal::CtapHybridEvent::CtapHybridEvent((CtapHybridInternal::CtapHybridEvent *)v90);
      v92 = *(_OWORD *)(v3 + 16);
      v5 = 0;
      v6 = *(char **)(v3 + 144);
      if ( v6 && *(_DWORD *)(v3 + 136) )
        v5 = *v6;
      LOWORD(v69) = 0;
      *(_OWORD *)v73 = 0;
      v89 = *(_OWORD *)(v3 + 16);
      if ( (byte_1801AEA03 & 0x20) != 0 )
        McTemplateU0j_EventWriteTransfer(v4, &EVENT_CTAP_HYBRID_PROTOCOL_SETUP_START, &v89);
      try
      {
        v74 = "Undefined";
        v7 = a1[9];
        if ( v7 )
        {
          hMem = 0;
          *(_QWORD *)&v76 = &hMem;
          *((_QWORD *)&v76 + 1) = 0;
          LOBYTE(v77) = 1;
          std::wstring::wstring(&v84, v7);
          v8 = (unsigned int)CtapHybridInternal::RetrieveLinkedDeviceData(
                               *(_QWORD *)(a1[39] + 64LL),
                               &v84,
                               (char *)&v76 + 8) >> 31;
          std::wstring::_Tidy_deallocate(&v84);
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_CTAPCBOR_HYBRID_STORAGE_LINKED_DATA *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,_CTAPCBOR_HYBRID_STORAGE_LINKED_DATA *,_CTAPCBOR_HYBRID_STORAGE_LINKED_DATA *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_CTAPCBOR_HYBRID_STORAGE_LINKED_DATA *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,_CTAPCBOR_HYBRID_STORAGE_LINKED_DATA *,_CTAPCBOR_HYBRID_STORAGE_LINKED_DATA *,0,std::nullptr_t>>>>(&v76);
          if ( (unsigned __int8)v8 != 1 )
          {
            v9 = "LinkedDevice";
            v74 = "LinkedDevice";
            std::string::_Assign<char>(v91, "LinkedDevice", 12);
            LOBYTE(v10) = v5;
            v12 = CtapHybridLinkedDeviceHandshake(a1[4], (_DWORD)hMem, v10, (unsigned int)v90, (__int64)v73);
            if ( v12 == -2147019873 )
            {
              v13 = CtapHybridInternal::RemoveLinkedDeviceData(*(CtapHybridInternal **)(a1[39] + 64LL), hMem, v11);
              if ( v13 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x24B,
                  (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybrid.cpp",
                  (const char *)(unsigned int)v13,
                  v67[0]);
            }
            if ( v12 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x24D,
                (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybrid.cpp",
                (const char *)(unsigned int)v12,
                v67[0]);
            v14 = hMem;
          }
          else
          {
            v9 = "CallerLinkedDevice";
            v74 = "CallerLinkedDevice";
            std::string::_Assign<char>(v91, "CallerLinkedDevice", 18);
            v16 = *(_QWORD *)(v3 + 192);
            if ( !v16 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x25B,
                (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybrid.cpp",
                (const char *)0x57,
                v67[0]);
            LOBYTE(v15) = v5;
            v17 = CtapHybridLinkedDeviceHandshake(a1[4], v16, v15, (unsigned int)v90, (__int64)v73);
            if ( v17 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x25E,
                (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybrid.cpp",
                (const char *)(unsigned int)v17,
                v67[0]);
            v14 = *(_WORD **)(v3 + 192);
          }
          v18 = v14[36];
          v19 = v73[0];
          *((_QWORD *)v73[0] + 17) = *(_QWORD *)(a1[39] + 64LL);
          *((_WORD *)v19 + 124) = v18;
          wil::details::unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned char *,void (*)(void *),&void FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned char *,unsigned char *,0,std::nullptr_t>>(&hMem);
        }
        else
        {
          v9 = "QR";
          v74 = "QR";
          std::string::_Assign<char>(v91, "QR", 2);
          *(_QWORD *)v67 = &v69;
          v21 = CtapHybridQrCodeHandshake(a1[4], v3, v90, v73);
          if ( v21 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x268,
              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybrid.cpp",
              (const char *)(unsigned int)v21,
              v67[0]);
          memset_0(Destination, 0, 0x68u);
          memcpy_s_2(
            Destination,
            0x68u,
            *(const void *const *)(*(_QWORD *)(v3 + 184) + 8LL),
            **(unsigned int **)(v3 + 184));
          v22 = v73[0];
          v23 = Destination[0];
          v24 = Destination[1];
          v25 = Destination[2];
          v26 = Destination[3];
          v27 = Destination[4];
          v28 = Destination[5];
          v29 = v94;
          v20 = *(wil **)(a1[39] + 64LL);
          *((_QWORD *)v73[0] + 17) = v20;
          v18 = v69;
          *((_WORD *)v22 + 124) = v69;
          *((_OWORD *)v22 + 9) = v23;
          *((_OWORD *)v22 + 10) = v24;
          *((_OWORD *)v22 + 11) = v25;
          *((_OWORD *)v22 + 12) = v26;
          *((_OWORD *)v22 + 13) = v27;
          *((_OWORD *)v22 + 14) = v28;
          *((_QWORD *)v22 + 30) = v29;
          *((_BYTE *)v22 + 250) = 1;
        }
      }
      catch ( ... )
      {
        v59 = wil::ResultFromCaughtException(v20);
        if ( byte_1801AEA03 < 0 )
          McTemplateU0jsdd_EventWriteTransfer(
            v60,
            (unsigned int)&EVENT_CTAP_HYBRID_PROTOCOL_SETUP_STOP_WITH_ERROR,
            (unsigned int)v66 + 264,
            (_DWORD)v74,
            v59,
            v59);
        wil::details::in1diag3::Throw_CaughtException(
          retaddr,
          (void *)0x273,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybrid.cpp",
          v61);
      }
      if ( (byte_1801AEA03 & 0x40) != 0 )
        McTemplateU0jsdd_EventWriteTransfer(
          (_DWORD)v20,
          (unsigned int)&EVENT_CTAP_HYBRID_PROTOCOL_SETUP_STOP,
          (unsigned int)&v89,
          (_DWORD)v9,
          0,
          0);
      try
      {
        v74 = (const char *)v73;
        v75 = 1;
        v76 = 0;
        v77 = 0;
        v70 = 0;
        Message = CtapHybridInternal::Noise::WaitAndGetMessage(v73[0], &v71, v90, 0);
        std::vector<unsigned char>::operator=(&v76, Message);
        std::vector<unsigned char>::_Tidy(&v71);
        CtapDevicePublishWnfState(0x20u, 0x192u, 0, 0);
        hMem = 0;
        *(_QWORD *)&v71 = &hMem;
        *((_QWORD *)&v71 + 1) = 0;
        LOBYTE(v72) = 1;
        InfoMessage = CtapCborDecodeHybridGetInfoMessage(
                        DWORD2(v76) - (int)v76,
                        v76,
                        (unsigned int)&v71 + 8,
                        v31,
                        *(__int64 *)v67,
                        (__int64)v68);
        v33 = CtapCborErrorToWin32Error(InfoMessage);
        if ( v33 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x28F,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybrid.cpp",
            (const char *)v33,
            v67[0]);
        wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v71);
        *(_QWORD *)&v71 = &v70;
        *((_QWORD *)&v71 + 1) = 0;
        LOBYTE(v72) = 1;
        InfoResponse = CtapCborDecodeGetInfoResponse(
                         *(_DWORD *)hMem,
                         *((_QWORD *)hMem + 1),
                         (unsigned int)&v71 + 8,
                         0,
                         0);
        v35 = CtapCborErrorToWin32Error(InfoResponse);
        if ( v35 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x292,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybrid.cpp",
            (const char *)v35,
            v67[0]);
        wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v71);
        v37 = hMem;
        hMem = 0;
        if ( v37 )
          LocalFree(v37);
      }
      catch ( ... )
      {
        std::string::operator=(v90, "FAILED_TO_RECEIVE_GETINFO_MESSAGE");
        throw;
      }
      *(_QWORD *)v67 = v3;
      LOBYTE(v36) = v5;
      CtapHybridReencodeRequestMessage(v83, v90, v36, v70);
      try
      {
        CtapHybridInternal::Noise::WriteMessage(v73[0], v83);
        CtapDevicePublishWnfState(0x20u, 0x193u, 0, 0);
      }
      catch ( ... )
      {
        std::string::operator=(v90, "FAILED_TO_SEND_CTAP_REQUEST");
        throw;
      }
      try
      {
        v71 = 0;
        v72 = 0;
        v38 = CtapHybridInternal::Noise::WaitAndGetMessage(v73[0], &v84, v90, 0);
        std::vector<unsigned char>::operator=(&v71, v38);
        std::vector<unsigned char>::_Tidy(&v84);
        v39 = v71;
        if ( (_QWORD)v71 == *((_QWORD *)&v71 + 1) )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x2B1,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybrid.cpp",
            (const char *)0x83760001LL,
            v67[0]);
      }
      catch ( ... )
      {
        std::string::operator=(v90, "FAILED_RECEIVING_CTAP_RESULT");
        throw;
      }
      if ( *(_BYTE *)v39 != 1 )
      {
        std::string::operator=(v90, "RECEIVED_NON_CTAP_RESPONSE");
        v56 = wil::verify_hresult<long>(2205548546LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2BC,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybrid.cpp",
          (const char *)v56,
          v67[0]);
      }
      v40 = DWORD2(v39) - v39;
      if ( *((_QWORD *)&v39 + 1) - (_QWORD)v39 >= 2u && *(_BYTE *)(v39 + 1) )
      {
        LODWORD(hMem) = 0;
        BYTE4(hMem) = 0;
        v41 = (unsigned __int8 *)std::vector<unsigned char>::operator[](&v71, 1);
        v42 = snprintf((char *const)&hMem, 5u, "0x%02x", *v41);
        if ( v42 < 0 || (LOBYTE(v44) = 0, (unsigned int)v42 > 5) )
          LOBYTE(v44) = 1;
        if ( (unsigned __int8)wil::verify_bool<bool,0>(v44, v43, v45, retaddr, *(_QWORD *)v67) )
          wil::details::in1diag3::_FailFast_Unexpected(
            v46,
            (void *)0x2C3,
            (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybrid.cpp",
            (const char *)v46);
        std::string::string(&v84, "RECEIVED_CTAP_ERROR_RESPONSE: ");
        std::string::append(&v84, &hMem);
        std::string::operator=(v90, &v84);
        std::vector<unsigned char>::operator[](&v71, 1);
        v57 = wil::verify_hresult<long>(2148073504LL);
        LODWORD(v68) = v58;
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x2CF,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybrid.cpp",
          (const char *)v57,
          (int)"Authenticator returned error 0x%02x",
          v68);
      }
      v85 = 0;
      v88 = 0;
      v84 = 1;
      *(_QWORD *)((char *)&v85 + 4) = a1 + 5;
      *(_OWORD *)v80 = 0;
      v81 = 0;
      v78 = 0;
      v79 = 0;
      LOBYTE(v40) = v5;
      v47 = CtapHybridReencodeResponse((unsigned int)v90, v40, (unsigned int)&v71, v3, (__int64)v80, (__int64)&v78);
      v48 = v47;
      if ( v47 >= 0 )
      {
        v87 = *(_QWORD *)v80;
        v86 = v80[2] - v80[0];
        a1[31] = v78;
        *((_DWORD *)a1 + 60) = DWORD2(v78) - v78;
        if ( v5 == 1 )
        {
          if ( v18 == 1 )
          {
            *((_DWORD *)a1 + 59) = 1;
          }
          else
          {
            v69 = 0;
            CtapCborGetMakeCredentialOptions(*(unsigned int *)(v3 + 136), *(_QWORD *)(v3 + 144), &v69, &hMem);
            v52 = v69;
            if ( v69 && (unsigned int)CtapCborFallbackToNonResidentKey(v70, *(_QWORD *)(v3 + 152)) )
              v52 = 0;
            *((_DWORD *)a1 + 59) = v52;
          }
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WebAuthnApiUpdates>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_WebAuthnApiUpdates>::GetImpl'::`2'::impl) )
          {
            v53 = *((_DWORD *)v70 + 26);
            *((_DWORD *)a1 + 65) = v53;
            if ( !v53 )
              *((_DWORD *)a1 + 65) = 48;
          }
        }
        updated = CtapDeviceUpdateControlBlockResponse(a1, &v84);
        if ( updated )
        {
          try
          {
            wil::details::in1diag3::Throw_Win32(
              retaddr,
              (void *)0x300,
              (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybrid.cpp",
              (const char *)updated,
              v67[0]);
          }
          catch ( ... )
          {
            v65 = v66;
            std::string::operator=(v65 + 288, "FAILED_BUILDING_RESULT_CONTROL_BLOCK");
            throw;
          }
        }
        std::string::_Assign<char>(v90, "SUCCESS", 7);
        *((_DWORD *)a1 + 81) = 0;
        CtapDeviceUpdateControlBlockState(a1);
        std::vector<unsigned char>::_Tidy(&v78);
        std::vector<unsigned char>::_Tidy(v80);
        std::vector<unsigned char>::_Tidy(&v71);
        std::vector<unsigned char>::_Tidy(v83);
        v55 = v70;
        v70 = 0;
        if ( v55 )
          LocalFree(v55);
        std::vector<unsigned char>::_Tidy(&v76);
        v75 = 0;
        CtapHybridSendReceiveCommand_::_3_::_lambda_1_::operator()(&v74);
        if ( v73[1] )
          std::_Ref_count_base::_Decref(v73[1]);
        CtapHybridInternal::CtapHybridEvent::~CtapHybridEvent((CtapHybridInternal::CtapHybridEvent *)v90);
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2D7,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybrid.cpp",
          (const char *)(unsigned int)v47,
          v67[0]);
        std::vector<unsigned char>::_Tidy(&v78);
        std::vector<unsigned char>::_Tidy(v80);
        std::vector<unsigned char>::_Tidy(&v71);
        std::vector<unsigned char>::_Tidy(v83);
        v49 = v70;
        v70 = 0;
        if ( v49 )
          LocalFree(v49);
        std::vector<unsigned char>::_Tidy(&v76);
        v75 = 0;
        CtapHybridSendReceiveCommand_::_3_::_lambda_1_::operator()(&v74);
        if ( v73[1] )
          std::_Ref_count_base::_Decref(v73[1]);
        CtapHybridInternal::CtapHybridEvent::~CtapHybridEvent((CtapHybridInternal::CtapHybridEvent *)v90);
        result = v48;
      }
    }
    catch ( ... )
    {
      v62 = wil::ResultFromCaughtException(v50);
      v63 = v82;
      *((_DWORD *)v82 + 81) = v62;
      CtapDeviceUpdateControlBlockState(v63);
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x313,
                             (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybrid.cpp",
                             v64);
    }
  }
  else
  {
    *((_DWORD *)a1 + 81) = -2146893771;
    CtapDeviceUpdateControlBlockState(a1);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1801082ac  mov     rax, rsp
0x1801082af  mov     [rax+10h], rbx
0x1801082b3  mov     [rax+18h], rsi
0x1801082b7  push    rdi
0x1801082b8  push    r12
0x1801082ba  push    r13
0x1801082bc  push    r14
0x1801082be  push    r15
0x1801082c0  sub     rsp, 230h
0x1801082c7  movaps  xmmword ptr [rax-38h], xmm6
0x1801082cb  mov     rax, cs:__security_cookie
0x1801082d2  xor     rax, rsp
0x1801082d5  mov     [rsp+258h+var_40], rax
0x1801082dd  mov     rbx, rcx
0x1801082e0  mov     [rsp+258h+var_198], rcx
0x1801082e8  mov     rax, [rcx+138h]
0x1801082ef  mov     rsi, [rax+38h]
0x1801082f3  test    byte ptr [rsi+8], 20h
0x1801082f7  jz      loc_180108BF5
0x1801082fd  xor     r13d, r13d
0x180108300  cmp     [rcx+48h], r13
0x180108304  jnz     short loc_180108313
0x180108306  cmp     [rsi+0B8h], r13
0x18010830d  jz      loc_180108BF5
0x180108313  lea     rcx, [rsp+258h+var_138]; this
0x18010831b  call    ??0CtapHybridEvent@CtapHybridInternal@@QEAA@XZ; CtapHybridInternal::CtapHybridEvent::CtapHybridEvent(void)
0x180108320  nop
0x180108321  movups  xmm0, xmmword ptr [rsi+10h]
0x180108325  movdqu  [rsp+258h+var_D0], xmm0
0x18010832e  mov     r12b, r13b
0x180108331  mov     rax, [rsi+90h]
0x180108338  mov     edi, 1
0x18010833d  test    rax, rax
0x180108340  jz      short loc_18010834D
0x180108342  cmp     [rsi+88h], edi
0x180108348  jb      short loc_18010834D
0x18010834a  mov     r12b, [rax]
0x18010834d  mov     word ptr [rsp+258h+var_228], r13w
0x180108353  xorps   xmm0, xmm0
0x180108356  movdqu  xmmword ptr [rsp+258h+var_200], xmm0
0x18010835c  movups  xmm0, xmmword ptr [rsi+10h]
0x180108360  movdqu  [rsp+258h+var_150], xmm0
0x180108369  test    cs:byte_1801AEA03, 20h
0x180108370  jz      short loc_180108386
0x180108372  lea     r8, [rsp+258h+var_150]
0x18010837a  lea     rdx, EVENT_CTAP_HYBRID_PROTOCOL_SETUP_START
0x180108381  call    McTemplateU0j_EventWriteTransfer
0x180108386  lea     rax, aUndefined; "Undefined"
0x18010838d  mov     [rsp+258h+var_1F0], rax
0x180108392  mov     rdx, [rbx+48h]
0x180108396  test    rdx, rdx
0x180108399  jz      loc_18010855C
0x18010839f  mov     [rsp+258h+hMem], r13
0x1801083a7  lea     rax, [rsp+258h+hMem]
0x1801083af  mov     qword ptr [rsp+258h+var_1E0], rax
0x1801083b4  mov     qword ptr [rsp+258h+var_1E0+8], r13
0x1801083bc  mov     byte ptr [rsp+258h+var_1D0], dil
0x1801083c4  lea     rcx, [rsp+258h+var_178]
0x1801083cc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801083d1  nop
0x1801083d2  mov     rcx, [rbx+138h]
0x1801083d9  lea     r8, [rsp+258h+var_1E0+8]
0x1801083e1  lea     rdx, [rsp+258h+var_178]
0x1801083e9  mov     rcx, [rcx+40h]
0x1801083ed  call    ?RetrieveLinkedDeviceData@CtapHybridInternal@@YAJQEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAU_CTAPCBOR_HYBRID_STORAGE_LINKED_DATA@@@Z; CtapHybridInternal::RetrieveLinkedDeviceData(void * const,std::wstring const &,_CTAPCBOR_HYBRID_STORAGE_LINKED_DATA * *)
0x1801083f2  mov     r14d, eax
0x1801083f5  shr     r14d, 1Fh
0x1801083f9  lea     rcx, [rsp+258h+var_178]
0x180108401  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180108406  nop
0x180108407  lea     rcx, [rsp+258h+var_1E0]
0x18010840c  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_CTAPCBOR_HYBRID_STORAGE_LINKED_DATA@@P6AXPEAX@Z$1?FidoFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_CTAPCBOR_HYBRID_STORAGE_LINKED_DATA *,void (*)(void *),&FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,_CTAPCBOR_HYBRID_STORAGE_LINKED_DATA *,_CTAPCBOR_HYBRID_STORAGE_LINKED_DATA *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_CTAPCBOR_HYBRID_STORAGE_LINKED_DATA *,void (*)(void *),&FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,_CTAPCBOR_HYBRID_STORAGE_LINKED_DATA *,_CTAPCBOR_HYBRID_STORAGE_LINKED_DATA *,0,std::nullptr_t>>>>(void)
0x180108411  xor     r14b, dil
0x180108414  lea     rcx, [rsp+258h+var_F0]
0x18010841c  jz      loc_1801084BF
0x180108422  lea     r14, aLinkeddevice; "LinkedDevice"
0x180108429  mov     [rsp+258h+var_1F0], r14
0x18010842e  mov     r8d, 0Ch
0x180108434  mov     rdx, r14
0x180108437  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x18010843c  lea     rax, [rsp+258h+var_200]
0x180108441  mov     qword ptr [rsp+258h+var_238], rax; int
0x180108446  lea     r9, [rsp+258h+var_138]
0x18010844e  mov     r8b, r12b
0x180108451  mov     rdx, [rsp+258h+hMem]
0x180108459  mov     rcx, [rbx+20h]
0x18010845d  call    CtapHybridLinkedDeviceHandshake
0x180108462  mov     r15d, eax
0x180108465  cmp     eax, 8007139Fh
0x18010846a  jnz     short loc_1801084A4
0x18010846c  mov     rcx, [rbx+138h]
0x180108473  mov     rdx, [rsp+258h+hMem]; void *
0x18010847b  mov     rcx, [rcx+40h]; this
0x18010847f  call    ?RemoveLinkedDeviceData@CtapHybridInternal@@YAJQEAXQEAU_CTAPCBOR_HYBRID_STORAGE_LINKED_DATA@@@Z; CtapHybridInternal::RemoveLinkedDeviceData(void * const,_CTAPCBOR_HYBRID_STORAGE_LINKED_DATA * const)
0x180108484  mov     rcx, [rsp+258h]; this
0x18010848c  test    eax, eax
0x18010848e  jns     short loc_1801084A4
0x180108490  mov     r9d, eax; char *
0x180108493  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18010849a  mov     edx, 24Bh; void *
0x18010849f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801084a4  mov     rcx, [rsp+258h]; this
0x1801084ac  test    r15d, r15d
0x1801084af  js      loc_180108C43
0x1801084b5  mov     rax, [rsp+258h+hMem]
0x1801084bd  jmp     short loc_180108526
0x1801084bf  lea     r14, aCallerlinkedde; "CallerLinkedDevice"
0x1801084c6  mov     [rsp+258h+var_1F0], r14
0x1801084cb  mov     r8d, 12h
0x1801084d1  mov     rdx, r14
0x1801084d4  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x1801084d9  mov     rdx, [rsi+0C0h]
0x1801084e0  mov     rcx, [rsp+258h]; this
0x1801084e8  test    rdx, rdx
0x1801084eb  jz      loc_180108C57
0x1801084f1  lea     rax, [rsp+258h+var_200]
0x1801084f6  mov     qword ptr [rsp+258h+var_238], rax; int
0x1801084fb  lea     r9, [rsp+258h+var_138]
0x180108503  mov     r8b, r12b
0x180108506  mov     rcx, [rbx+20h]
0x18010850a  call    CtapHybridLinkedDeviceHandshake
0x18010850f  mov     rcx, [rsp+258h]; this
0x180108517  test    eax, eax
0x180108519  js      loc_180108C6C
0x18010851f  mov     rax, [rsi+0C0h]
0x180108526  movzx   r13d, word ptr [rax+48h]
0x18010852b  mov     rdx, [rsp+258h+var_200]
0x180108530  mov     rax, [rbx+138h]
0x180108537  mov     rcx, [rax+40h]
0x18010853b  mov     [rdx+88h], rcx
0x180108542  mov     [rdx+0F8h], r13w
0x18010854a  lea     rcx, [rsp+258h+hMem]
0x180108552  call    ??1?$unique_storage@U?$resource_policy@PEAEP6AXPEAX@Z$1?FidoFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAEPEAE$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<uchar *,void (*)(void *),&FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<uchar *,void (*)(void *),&FidoFree(void *),wistd::integral_constant<unsigned __int64,0>,uchar *,uchar *,0,std::nullptr_t>>(void)
0x180108557  jmp     loc_18010867E
0x18010855c  lea     r14, aQr; "QR"
0x180108563  mov     [rsp+258h+var_1F0], r14
0x180108568  mov     r8d, 2
0x18010856e  mov     rdx, r14
0x180108571  lea     rcx, [rsp+258h+var_F0]
0x180108579  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x18010857e  lea     rax, [rsp+258h+var_228]
0x180108583  mov     qword ptr [rsp+258h+var_238], rax; int
0x180108588  lea     r9, [rsp+258h+var_200]
0x18010858d  lea     r8, [rsp+258h+var_138]
0x180108595  mov     rdx, rsi
0x180108598  mov     rcx, [rbx+20h]
0x18010859c  call    CtapHybridQrCodeHandshake
0x1801085a1  mov     rcx, [rsp+258h]; this
0x1801085a9  test    eax, eax
0x1801085ab  js      loc_180108C81
0x1801085b1  mov     r15d, 68h ; 'h'
0x1801085b7  mov     r8d, r15d; Size
0x1801085ba  xor     edx, edx; Val
0x1801085bc  lea     rcx, [rsp+258h+Destination]; void *
0x1801085c4  call    memset_0
0x1801085c9  mov     r8, [rsi+0B8h]
0x1801085d0  mov     r9d, [r8]; SourceSize
0x1801085d3  mov     r8, [r8+8]; Source
0x1801085d7  mov     edx, r15d; DestinationSize
0x1801085da  lea     rcx, [rsp+258h+Destination]; Destination
0x1801085e2  call    memcpy_s_2
0x1801085e7  mov     rdx, [rsp+258h+var_200]
0x1801085ec  movaps  xmm0, [rsp+258h+Destination]
0x1801085f4  movaps  xmm1, [rsp+258h+var_A8]
0x1801085fc  movaps  xmm2, [rsp+258h+var_98]
0x180108604  movaps  xmm3, [rsp+258h+var_88]
0x18010860c  movaps  xmm4, [rsp+258h+var_78]
0x180108614  movaps  xmm5, [rsp+258h+var_68]
0x18010861c  movsd   xmm6, [rsp+258h+var_58]
0x180108625  mov     rax, [rbx+138h]
0x18010862c  mov     rcx, [rax+40h]
0x180108630  mov     [rdx+88h], rcx
0x180108637  movzx   r13d, word ptr [rsp+258h+var_228]
0x18010863d  mov     [rdx+0F8h], r13w
0x180108645  movups  xmmword ptr [rdx+90h], xmm0
0x18010864c  movups  xmmword ptr [rdx+0A0h], xmm1
0x180108653  movups  xmmword ptr [rdx+0B0h], xmm2
0x18010865a  movups  xmmword ptr [rdx+0C0h], xmm3
0x180108661  movups  xmmword ptr [rdx+0D0h], xmm4
0x180108668  movups  xmmword ptr [rdx+0E0h], xmm5
0x18010866f  movsd   qword ptr [rdx+0F0h], xmm6
0x180108677  mov     [rdx+0FAh], dil
0x18010867e  xor     r15d, r15d
0x180108681  test    cs:byte_1801AEA03, 40h
0x180108688  jz      short loc_1801086AB
0x18010868a  mov     dword ptr [rsp+258h+var_230], r15d
0x18010868f  mov     [rsp+258h+var_238], r15d; unsigned int
0x180108694  mov     r9, r14
0x180108697  lea     r8, [rsp+258h+var_150]
0x18010869f  lea     rdx, EVENT_CTAP_HYBRID_PROTOCOL_SETUP_STOP
0x1801086a6  call    McTemplateU0jsdd_EventWriteTransfer
0x1801086ab  lea     rax, [rsp+258h+var_200]
0x1801086b0  mov     [rsp+258h+var_1F0], rax
0x1801086b5  mov     [rsp+258h+var_1E8], dil
0x1801086ba  xorps   xmm0, xmm0
0x1801086bd  movdqu  [rsp+258h+var_1E0], xmm0
0x1801086c3  mov     [rsp+258h+var_1D0], r15
0x1801086cb  mov     [rsp+258h+var_220], r15
0x1801086d0  xor     r9d, r9d
0x1801086d3  lea     r8, [rsp+258h+var_138]
0x1801086db  lea     rdx, [rsp+258h+var_218]
0x1801086e0  mov     rcx, [rsp+258h+var_200]
0x1801086e5  call    ?WaitAndGetMessage@Noise@CtapHybridInternal@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@AEAUCtapHybridEvent@2@E@Z; CtapHybridInternal::Noise::WaitAndGetMessage(CtapHybridInternal::CtapHybridEvent &,uchar)
0x1801086ea  mov     rdx, rax
0x1801086ed  lea     rcx, [rsp+258h+var_1E0]
0x1801086f2  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x1801086f7  lea     rcx, [rsp+258h+var_218]
0x1801086fc  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180108701  xor     r9d, r9d
0x180108704  xor     r8d, r8d
0x180108707  mov     edx, 192h
0x18010870c  lea     r14d, [r9+20h]
0x180108710  mov     ecx, r14d
0x180108713  call    _CtapDevicePublishWnfState
0x180108718  mov     [rsp+258h+hMem], r15
0x180108720  lea     rax, [rsp+258h+hMem]
0x180108728  mov     qword ptr [rsp+258h+var_218], rax
0x18010872d  mov     qword ptr [rsp+258h+var_218+8], r15
0x180108732  mov     byte ptr [rsp+258h+var_208], dil
0x180108737  mov     ecx, dword ptr [rsp+258h+var_1E0+8]
0x18010873e  mov     rdx, qword ptr [rsp+258h+var_1E0]
0x180108743  sub     ecx, edx
0x180108745  lea     r8, [rsp+258h+var_218+8]
0x18010874a  call    CtapCborDecodeHybridGetInfoMessage
0x18010874f  mov     ecx, eax
0x180108751  call    CtapCborErrorToWin32Error
0x180108756  mov     rcx, [rsp+258h]; this
0x18010875e  test    eax, eax
0x180108760  jnz     loc_180108C96
0x180108766  lea     rcx, [rsp+258h+var_218]
0x18010876b  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180108770  lea     rax, [rsp+258h+var_220]
0x180108775  mov     qword ptr [rsp+258h+var_218], rax
0x18010877a  mov     qword ptr [rsp+258h+var_218+8], r15
0x18010877f  mov     byte ptr [rsp+258h+var_208], dil
0x180108784  mov     qword ptr [rsp+258h+var_238], r15; unsigned int
0x180108789  xor     r9d, r9d
0x18010878c  lea     r8, [rsp+258h+var_218+8]
0x180108791  mov     rcx, [rsp+258h+hMem]
0x180108799  mov     rdx, [rcx+8]
0x18010879d  mov     ecx, [rcx]
0x18010879f  call    CtapCborDecodeGetInfoResponse
0x1801087a4  mov     ecx, eax
0x1801087a6  call    CtapCborErrorToWin32Error
0x1801087ab  mov     rcx, [rsp+258h]; this
0x1801087b3  test    eax, eax
0x1801087b5  jnz     loc_180108CAB
0x1801087bb  lea     rcx, [rsp+258h+var_218]
0x1801087c0  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1801087c5  nop
0x1801087c6  mov     rcx, [rsp+258h+hMem]; hMem
0x1801087ce  mov     [rsp+258h+hMem], r15
0x1801087d6  test    rcx, rcx
0x1801087d9  jz      short loc_1801087E2
0x1801087db  call    cs:__imp_LocalFree
0x1801087e1  nop
0x1801087e2  mov     qword ptr [rsp+258h+var_238], rsi; int
0x1801087e7  mov     r9, [rsp+258h+var_220]
0x1801087ec  mov     r8b, r12b
0x1801087ef  lea     rdx, [rsp+258h+var_138]
0x1801087f7  lea     rcx, [rsp+258h+var_190]
0x1801087ff  call    CtapHybridReencodeRequestMessage
0x180108804  nop
0x180108805  lea     rdx, [rsp+258h+var_190]
0x18010880d  mov     rcx, [rsp+258h+var_200]
0x180108812  call    ?WriteMessage@Noise@CtapHybridInternal@@QEAAXAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; CtapHybridInternal::Noise::WriteMessage(std::vector<uchar> const &)
0x180108817  xor     r9d, r9d
0x18010881a  xor     r8d, r8d
0x18010881d  mov     edx, 193h
0x180108822  mov     ecx, r14d
0x180108825  call    _CtapDevicePublishWnfState
0x18010882a  nop
0x18010882b  xorps   xmm0, xmm0
0x18010882e  movdqu  [rsp+258h+var_218], xmm0
0x180108834  mov     [rsp+258h+var_208], r15
0x180108839  xor     r9d, r9d
0x18010883c  lea     r8, [rsp+258h+var_138]
0x180108844  lea     rdx, [rsp+258h+var_178]
0x18010884c  mov     rcx, [rsp+258h+var_200]
0x180108851  call    ?WaitAndGetMessage@Noise@CtapHybridInternal@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@AEAUCtapHybridEvent@2@E@Z; CtapHybridInternal::Noise::WaitAndGetMessage(CtapHybridInternal::CtapHybridEvent &,uchar)
0x180108856  mov     rdx, rax
0x180108859  lea     rcx, [rsp+258h+var_218]
0x18010885e  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x180108863  lea     rcx, [rsp+258h+var_178]
0x18010886b  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180108870  mov     rcx, qword ptr [rsp+258h+var_218]
0x180108875  mov     rdx, qword ptr [rsp+258h+var_218+8]
0x18010887a  cmp     rcx, rdx
0x18010887d  setnz   al
0x180108880  mov     r10, [rsp+258h]
0x180108888  test    al, al
0x18010888a  jz      loc_180108CC0
0x180108890  cmp     [rcx], dil
0x180108893  jnz     loc_180108CDB
0x180108899  sub     rdx, rcx
0x18010889c  cmp     rdx, 2
0x1801088a0  jb      short loc_18010890B
0x1801088a2  cmp     [rcx+1], r15b
0x1801088a6  jz      short loc_18010890B
0x1801088a8  xor     eax, eax
  ... truncated ...
```
