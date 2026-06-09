# DdcMobileNetworksHelper::GetMobileNetworksProperties(Windows::Data::Json::IJsonValue * *)

- ea: `0x180023f8c`
- end: `0x18002426a`
- name: `?GetMobileNetworksProperties@DdcMobileNetworksHelper@@SAJPEAPEAUIJsonValue@Json@Data@Windows@@@Z`
- size: `734`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonValue **, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c034`

## callees

- `0x1800024c0`
- `0x180004060`
- `0x1800050b8`
- `0x18000fd48`
- `0x180013938`
- `0x180013ae8`
- `0x180013b38`
- `0x180023c64`
- `0x180023f8c`
- `0x180024270`
- `0x18002a010`

## string_xrefs

- `0x18002405d`: `Windows.Data.Json.JsonArray`
- `0x180023ff4`: `CPR(ppJsonValue)`
- `0x18002408e`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonArray).Get(), pJsonArray.GetAddressOf()))`
- `0x1800240ca`: `CHR(pJsonArray.As(&pJsonArrayAsVector))`
- `0x180024152`: `CHR(pJsonArrayAsVector->Append(pJsonValue.Get()))`
- `0x1800241af`: `CHR(pJsonArrayAsVector->Append(pJsonValue.Get()))`
- `0x1800241e4`: `CHR(pJsonArray.As(&pJsonArrayAsValue))`
- `0x180024008`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcmobilenetworkshelper.cpp`
- `0x180024035`: `CBR(*ppJsonValue == 0)`

## pseudocode

```c
__int64 __fastcall DdcMobileNetworksHelper::GetMobileNetworksProperties(
        struct Windows::Data::Json::IJsonValue **a1,
        int a2)
{
  int v3; // r8d
  int SimCount; // ebx
  struct Windows::Data::Json::IJsonValue *v5; // rax
  __int64 (__fastcall ***v6)(_QWORD, GUID *, __int64); // rcx
  char v8; // [rsp+20h] [rbp-60h]
  const char *v9; // [rsp+28h] [rbp-58h]
  int v10; // [rsp+30h] [rbp-50h] BYREF
  struct Windows::Data::Json::IJsonValue *v11; // [rsp+38h] [rbp-48h] BYREF
  __int64 (__fastcall ***v12)(_QWORD, GUID *, __int64); // [rsp+40h] [rbp-40h] BYREF
  struct Windows::Data::Json::IJsonValue *v13; // [rsp+48h] [rbp-38h] BYREF
  __int64 v14; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  __int64 v16; // [rsp+70h] [rbp-10h]

  v11 = 0;
  v12 = 0;
  v14 = 0;
  v13 = 0;
  v10 = 0;
  if ( !a1 )
  {
    v3 = -2147024809;
    SimCount = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_33;
    v9 = "CPR(ppJsonValue)";
    v8 = 49;
    goto LABEL_4;
  }
  if ( !*a1 )
  {
    v16 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonArray",
      0x1Cu,
      0x1Bu);
    SimCount = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonArray>(v16, &v12);
    if ( SimCount >= 0 )
    {
      SimCount = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
                   &v12,
                   (__int64)&v14);
      if ( SimCount >= 0 )
      {
        SimCount = DdcMobileNetworksHelper::GetSimCount((enum SimCount *)&v10);
        if ( SimCount >= 0 )
        {
          if ( v10 )
          {
            if ( (int)DdcMobileNetworksHelper::GetMobileNetworkPropertiesForCan(0, &v11) >= 0 )
            {
              SimCount = (*(__int64 (__fastcall **)(__int64, struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v14 + 104LL))(
                           v14,
                           v11);
              if ( SimCount < 0 )
              {
                if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                  goto LABEL_33;
                v9 = "CHR(pJsonArrayAsVector->Append(pJsonValue.Get()))";
                v8 = 66;
                goto LABEL_12;
              }
            }
            if ( v10 == 2 )
            {
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
              if ( (int)DdcMobileNetworksHelper::GetMobileNetworkPropertiesForCan(1u, &v11) >= 0 )
              {
                SimCount = (*(__int64 (__fastcall **)(__int64, struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v14 + 104LL))(
                             v14,
                             v11);
                if ( SimCount < 0 )
                {
                  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                    goto LABEL_33;
                  v9 = "CHR(pJsonArrayAsVector->Append(pJsonValue.Get()))";
                  v8 = 74;
                  goto LABEL_12;
                }
              }
            }
          }
          SimCount = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                       &v12,
                       (__int64)&v13);
          if ( SimCount >= 0 )
          {
            v5 = v13;
            v13 = 0;
            *a1 = v5;
            goto LABEL_33;
          }
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
            goto LABEL_33;
          v9 = "CHR(pJsonArray.As(&pJsonArrayAsValue))";
          v8 = 79;
          goto LABEL_12;
        }
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_33;
        v9 = "CHR(GetSimCount(&eSimCount))";
        v8 = 55;
      }
      else
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_33;
        v9 = "CHR(pJsonArray.As(&pJsonArrayAsVector))";
        v8 = 53;
      }
    }
    else
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_33;
      v9 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonArray).Get(), pJsonArray.GetAddressOf()))";
      v8 = 52;
    }
LABEL_12:
    v3 = SimCount;
LABEL_4:
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)a1,
      a2,
      v3,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmobilenetworkshelper.cpp",
      v8,
      v9);
    goto LABEL_33;
  }
  SimCount = -2147024809;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)a1,
      a2,
      -2147024809,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmobilenetworkshelper.cpp",
      50,
      "CBR(*ppJsonValue == 0)");
LABEL_33:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  v6 = v12;
  if ( v12 )
  {
    v12 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v6)[2])(v6);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
  return (unsigned int)SimCount;
}

```

## disassembly

```asm
0x180023f8c  mov     [rsp-8+arg_8], rbx
0x180023f91  mov     [rsp-8+arg_10], rdi
0x180023f96  push    rbp
0x180023f97  mov     rbp, rsp
0x180023f9a  sub     rsp, 80h
0x180023fa1  mov     rax, cs:__security_cookie
0x180023fa8  xor     rax, rsp
0x180023fab  mov     [rbp+var_8], rax
0x180023faf  mov     rdi, rcx
0x180023fb2  mov     [rbp+var_48], 0
0x180023fba  mov     [rbp+var_40], 0
0x180023fc2  mov     [rbp+var_30], 0
0x180023fca  mov     [rbp+var_38], 0
0x180023fd2  mov     [rbp+var_50], 0
0x180023fd9  test    rcx, rcx
0x180023fdc  jnz     short loc_180024019
0x180023fde  mov     r8d, 80070057h
0x180023fe4  mov     ebx, r8d
0x180023fe7  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180023fee  jz      loc_18002420C
0x180023ff4  lea     rax, aCprPpjsonvalue; "CPR(ppJsonValue)"
0x180023ffb  mov     [rsp+80h+var_58], rax
0x180024000  mov     dword ptr [rsp+80h+var_60], 31h ; '1'
0x180024008  lea     r9, aOnecoreuapShel_14; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18002400f  call    McTemplateU0dsqs_EventWriteTransfer
0x180024014  jmp     loc_18002420C
0x180024019  cmp     qword ptr [rcx], 0
0x18002401d  jz      short loc_18002404B
0x18002401f  mov     r8d, 80070057h
0x180024025  mov     ebx, r8d
0x180024028  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18002402f  jz      loc_18002420C
0x180024035  lea     rax, aCbrPpjsonvalue; "CBR(*ppJsonValue == 0)"
0x18002403c  mov     [rsp+80h+var_58], rax
0x180024041  mov     dword ptr [rsp+80h+var_60], 32h ; '2'
0x180024049  jmp     short loc_180024008
0x18002404b  mov     [rbp+var_10], 0
0x180024053  mov     r9d, 1Bh; unsigned int
0x180024059  lea     r8d, [r9+1]; unsigned int
0x18002405d  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x180024064  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180024068  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002406d  nop
0x18002406e  lea     rdx, [rbp+var_40]
0x180024072  mov     rcx, [rbp+var_10]
0x180024076  call    ??$ActivateInstance@UIJsonArray@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonArray@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonArray>(HSTRING__ *,Windows::Data::Json::IJsonArray * *)
0x18002407b  mov     ebx, eax
0x18002407d  test    eax, eax
0x18002407f  jns     short loc_1800240AA
0x180024081  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180024088  jz      loc_18002420C
0x18002408e  lea     rax, aChrActivateins_9; "CHR(ActivateInstance(HStringReference(R"...
0x180024095  mov     [rsp+80h+var_58], rax
0x18002409a  mov     dword ptr [rsp+80h+var_60], 34h ; '4'
0x1800240a2  mov     r8d, ebx
0x1800240a5  jmp     loc_180024008
0x1800240aa  lea     rdx, [rbp+var_30]
0x1800240ae  lea     rcx, [rbp+var_40]
0x1800240b2  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x1800240b7  mov     ebx, eax
0x1800240b9  test    eax, eax
0x1800240bb  jns     short loc_1800240E0
0x1800240bd  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800240c4  jz      loc_18002420C
0x1800240ca  lea     rax, aChrPjsonarrayA; "CHR(pJsonArray.As(&pJsonArrayAsVector))"
0x1800240d1  mov     [rsp+80h+var_58], rax
0x1800240d6  mov     dword ptr [rsp+80h+var_60], 35h ; '5'
0x1800240de  jmp     short loc_1800240A2
0x1800240e0  lea     rcx, [rbp+var_50]; enum SimCount *
0x1800240e4  call    ?GetSimCount@DdcMobileNetworksHelper@@CAJPEAW4SimCount@@@Z; DdcMobileNetworksHelper::GetSimCount(SimCount *)
0x1800240e9  mov     ebx, eax
0x1800240eb  test    eax, eax
0x1800240ed  jns     short loc_180024112
0x1800240ef  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800240f6  jz      loc_18002420C
0x1800240fc  lea     rax, aChrGetsimcount; "CHR(GetSimCount(&eSimCount))"
0x180024103  mov     [rsp+80h+var_58], rax
0x180024108  mov     dword ptr [rsp+80h+var_60], 37h ; '7'
0x180024110  jmp     short loc_1800240A2
0x180024112  cmp     [rbp+var_50], 0
0x180024116  jz      loc_1800241C8
0x18002411c  lea     rdx, [rbp+var_48]; struct Windows::Data::Json::IJsonValue **
0x180024120  xor     ecx, ecx; unsigned int
0x180024122  call    ?GetMobileNetworkPropertiesForCan@DdcMobileNetworksHelper@@CAJKPEAPEAUIJsonValue@Json@Data@Windows@@@Z; DdcMobileNetworksHelper::GetMobileNetworkPropertiesForCan(ulong,Windows::Data::Json::IJsonValue * *)
0x180024127  test    eax, eax
0x180024129  js      short loc_18002416B
0x18002412b  mov     rcx, [rbp+var_30]
0x18002412f  mov     rax, [rcx]
0x180024132  mov     rdx, [rbp+var_48]
0x180024136  mov     rax, [rax+68h]
0x18002413a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002413f  mov     ebx, eax
0x180024141  test    eax, eax
0x180024143  jns     short loc_18002416B
0x180024145  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18002414c  jz      loc_18002420C
0x180024152  lea     rax, aChrPjsonarraya; "CHR(pJsonArrayAsVector->Append(pJsonVal"...
0x180024159  mov     [rsp+80h+var_58], rax
0x18002415e  mov     dword ptr [rsp+80h+var_60], 42h ; 'B'
0x180024166  jmp     loc_1800240A2
0x18002416b  cmp     [rbp+var_50], 2
0x18002416f  jnz     short loc_1800241C8
0x180024171  lea     rcx, [rbp+var_48]
0x180024175  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002417a  lea     rdx, [rbp+var_48]; struct Windows::Data::Json::IJsonValue **
0x18002417e  mov     ecx, 1; unsigned int
0x180024183  call    ?GetMobileNetworkPropertiesForCan@DdcMobileNetworksHelper@@CAJKPEAPEAUIJsonValue@Json@Data@Windows@@@Z; DdcMobileNetworksHelper::GetMobileNetworkPropertiesForCan(ulong,Windows::Data::Json::IJsonValue * *)
0x180024188  test    eax, eax
0x18002418a  js      short loc_1800241C8
0x18002418c  mov     rcx, [rbp+var_30]
0x180024190  mov     rax, [rcx]
0x180024193  mov     rdx, [rbp+var_48]
0x180024197  mov     rax, [rax+68h]
0x18002419b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241a0  mov     ebx, eax
0x1800241a2  test    eax, eax
0x1800241a4  jns     short loc_1800241C8
0x1800241a6  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800241ad  jz      short loc_18002420C
0x1800241af  lea     rax, aChrPjsonarraya; "CHR(pJsonArrayAsVector->Append(pJsonVal"...
0x1800241b6  mov     [rsp+80h+var_58], rax
0x1800241bb  mov     dword ptr [rsp+80h+var_60], 4Ah ; 'J'
0x1800241c3  jmp     loc_1800240A2
0x1800241c8  lea     rdx, [rbp+var_38]
0x1800241cc  lea     rcx, [rbp+var_40]
0x1800241d0  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x1800241d5  mov     ebx, eax
0x1800241d7  test    eax, eax
0x1800241d9  jns     short loc_1800241FD
0x1800241db  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800241e2  jz      short loc_18002420C
0x1800241e4  lea     rax, aChrPjsonarrayA_0; "CHR(pJsonArray.As(&pJsonArrayAsValue))"
0x1800241eb  mov     [rsp+80h+var_58], rax
0x1800241f0  mov     dword ptr [rsp+80h+var_60], 4Fh ; 'O'
0x1800241f8  jmp     loc_1800240A2
0x1800241fd  mov     rax, [rbp+var_38]
0x180024201  mov     [rbp+var_38], 0
0x180024209  mov     [rdi], rax
0x18002420c  lea     rcx, [rbp+var_38]
0x180024210  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024215  nop
0x180024216  lea     rcx, [rbp+var_30]
0x18002421a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002421f  nop
0x180024220  mov     rcx, [rbp+var_40]
0x180024224  test    rcx, rcx
0x180024227  jz      short loc_18002423E
0x180024229  mov     [rbp+var_40], 0
0x180024231  mov     rax, [rcx]
0x180024234  mov     rax, [rax+10h]
0x180024238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002423d  nop
0x18002423e  lea     rcx, [rbp+var_48]
0x180024242  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180024247  mov     eax, ebx
0x180024249  mov     rcx, [rbp+var_8]
0x18002424d  xor     rcx, rsp; StackCookie
0x180024250  call    __security_check_cookie
0x180024255  lea     r11, [rsp+80h+var_s0]
0x18002425d  mov     rbx, [r11+18h]
0x180024261  mov     rdi, [r11+20h]
0x180024265  mov     rsp, r11
0x180024268  pop     rbp
0x180024269  retn
```
