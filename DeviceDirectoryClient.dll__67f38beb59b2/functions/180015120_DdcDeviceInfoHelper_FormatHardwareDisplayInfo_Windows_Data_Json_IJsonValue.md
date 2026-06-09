# DdcDeviceInfoHelper::FormatHardwareDisplayInfo(Windows::Data::Json::IJsonValue * *)

- ea: `0x180015120`
- end: `0x1800154fe`
- name: `?FormatHardwareDisplayInfo@DdcDeviceInfoHelper@@SAJPEAPEAUIJsonValue@Json@Data@Windows@@@Z`
- size: `990`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonValue **)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180015fbc`

## callees

- `0x1800024c0`
- `0x1800035b0`
- `0x180004060`
- `0x1800050b8`
- `0x180005a9c`
- `0x18000d08c`
- `0x18000fd48`
- `0x180013938`
- `0x180013ae8`
- `0x180013b38`
- `0x180013b88`
- `0x180014000`
- `0x1800145cc`
- `0x1800145e0`
- `0x180015120`
- `0x180015504`
- `0x18002a010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x18001525c`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x18001525c`

## string_xrefs

- `0x1800151ce`: `Windows.Data.Json.JsonArray`
- `0x180015290`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x18001544b`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`
- `0x180015199`: `CPR(ppJsonValue)`
- `0x180015437`: `CBR(*ppJsonValue == nullptr)`
- `0x180015200`: `CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonArray).Get(), pJsonArray.GetAddressOf()))`
- `0x18001523e`: `CHR(pJsonArray.As(&pJsonArrayAsVector))`
- `0x1800153c2`: `CHR(FormatIndividualHardwareDisplayInfo( pDisplayInfo->m_szDeviceIdentifier, pDisplayInfo->m_szDeviceName, pDisplayInfo->m_szDescription, pDisplayInfo->m_szDisplayMemoryEnglish, pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001539c`: `CHR(pJsonArrayAsVector->Append(pJsonValue.Get()))`
- `0x1800153f9`: `CHR(pJsonArray.As(&pJsonArrayAsValue))`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DdcDeviceInfoHelper::FormatHardwareDisplayInfo(struct Windows::Data::Json::IJsonValue **a1)
{
  int v2; // edx
  int v3; // ecx
  int v4; // ebx
  int v5; // r8d
  __int64 v6; // rax
  unsigned int v7; // r10d
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v10; // eax
  int v11; // ebx
  _QWORD *v12; // r12
  _QWORD *v13; // r14
  int v14; // esi
  int v15; // edi
  int v16; // ebx
  int v17; // eax
  struct Windows::Data::Json::IJsonValue *v18; // rax
  __int64 (__fastcall ***v19)(_QWORD, GUID *, __int64); // rcx
  int v21; // [rsp+20h] [rbp-E0h]
  char v22; // [rsp+20h] [rbp-E0h]
  const char *v23; // [rsp+28h] [rbp-D8h]
  __int64 (__fastcall ***v24)(_QWORD, GUID *, __int64); // [rsp+30h] [rbp-D0h] BYREF
  struct Windows::Data::Json::IJsonValue *v25; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE *v27; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v28; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v29; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+68h] [rbp-98h]
  _BYTE *v31; // [rsp+70h] [rbp-90h]
  _BYTE *v32; // [rsp+78h] [rbp-88h]
  _BYTE v33[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v34[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v35[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v36[32]; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+100h] [rbp+0h] BYREF
  __int64 v38; // [rsp+118h] [rbp+18h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v26 = 0;
  v24 = 0;
  v28 = 0;
  v25 = 0;
  std::vector<std::unique_ptr<DisplayInfo>>::vector<std::unique_ptr<DisplayInfo>>(&v29);
  if ( a1 )
  {
    if ( *a1 )
    {
      v5 = -2147024809;
      v4 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_32;
      v23 = "CBR(*ppJsonValue == nullptr)";
      v22 = 48;
    }
    else
    {
      v38 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonArray",
        0x1Cu,
        0x1Bu);
      v4 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonArray>(v38, &v24);
      if ( v4 >= 0 )
      {
        v4 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(
               &v24,
               (__int64)&v28);
        if ( v4 >= 0 )
        {
          LODWORD(v27) = 0;
          SHTaskPoolGetUniqueContext();
          v6 = lambda_5ce3936d8ad826038f88bbedacf4b390_::_lambda_5ce3936d8ad826038f88bbedacf4b390_(
                 &hstringHeader,
                 &v29,
                 &v27);
          v10 = Windows::Internal::ComTaskPool::QueueTask__lambda_5ce3936d8ad826038f88bbedacf4b390___(v9, v8, v7, v6);
          v11 = v10;
          if ( v10 >= 0 )
            v11 = (int)v27;
          else
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x756,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
              (const char *)(unsigned int)v10,
              v21);
          v12 = (_QWORD *)*((_QWORD *)&v29 + 1);
          v13 = (_QWORD *)v29;
          if ( (__int64)(*((_QWORD *)&v29 + 1) - v29) >> 3 && v11 >= 0 )
          {
            while ( v13 != v12 )
            {
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
              v27 = v33;
              v14 = std::wstring::wstring(v33, *v13 + 2080LL);
              v31 = v34;
              v15 = std::wstring::wstring(v34, *v13 + 520LL);
              v32 = v35;
              v16 = std::wstring::wstring(v35, *v13);
              v17 = std::wstring::wstring(v36, *v13 + 5720LL);
              v4 = DdcDeviceInfoHelper::FormatIndividualHardwareDisplayInfo(v17, v16, v15, v14, (__int64)&v26);
              if ( v4 < 0 )
              {
                if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                  goto LABEL_32;
                v23 = "CHR(FormatIndividualHardwareDisplayInfo( pDisplayInfo->m_szDeviceIdentifier, pDisplayInfo->m_szDev"
                      "iceName, pDisplayInfo->m_szDescription, pDisplayInfo->m_szDisplayMemoryEnglish, pJsonValue.Release"
                      "AndGetAddressOf()))";
                v22 = 71;
                goto LABEL_8;
              }
              v4 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v28 + 104LL))(v28, v26);
              if ( v4 < 0 )
              {
                if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                  goto LABEL_32;
                v23 = "CHR(pJsonArrayAsVector->Append(pJsonValue.Get()))";
                v22 = 72;
                goto LABEL_8;
              }
              ++v13;
            }
          }
          v4 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                 &v24,
                 (__int64)&v25);
          if ( v4 >= 0 )
          {
            v18 = v25;
            v25 = 0;
            *a1 = v18;
            goto LABEL_32;
          }
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
            goto LABEL_32;
          v23 = "CHR(pJsonArray.As(&pJsonArrayAsValue))";
          v22 = 77;
        }
        else
        {
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
            goto LABEL_32;
          v23 = "CHR(pJsonArray.As(&pJsonArrayAsVector))";
          v22 = 51;
        }
      }
      else
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_32;
        v23 = "CHR(ActivateInstance(HStringReference(RuntimeClass_Windows_Data_Json_JsonArray).Get(), pJsonArray.GetAddressOf()))";
        v22 = 50;
      }
LABEL_8:
      v5 = v4;
    }
    McTemplateU0dsqs_EventWriteTransfer(
      v3,
      v2,
      v5,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
      v22,
      v23);
  }
  else
  {
    v4 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v3,
        v2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        47,
        "CPR(ppJsonValue)");
  }
LABEL_32:
  if ( (_QWORD)v29 )
  {
    std::_Destroy_range<std::allocator<std::unique_ptr<DisplayInfo>>>(v29, *((__int64 *)&v29 + 1));
    std::_Deallocate<16>((_QWORD *)v29, (v30 - v29) & 0xFFFFFFFFFFFFFFF8uLL);
    v29 = 0;
    v30 = 0;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  v19 = v24;
  if ( v24 )
  {
    v24 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v19)[2])(v19);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180015120  mov     [rsp-8+arg_8], rbx
0x180015125  mov     [rsp-8+arg_10], rsi
0x18001512a  push    rbp
0x18001512b  push    rdi
0x18001512c  push    r12
0x18001512e  push    r14
0x180015130  push    r15
0x180015132  lea     rbp, [rsp-30h]
0x180015137  sub     rsp, 130h
0x18001513e  mov     rax, cs:__security_cookie
0x180015145  xor     rax, rsp
0x180015148  mov     [rbp+50h+var_30], rax
0x18001514c  mov     r15, rcx
0x18001514f  mov     [rsp+150h+var_110], 0
0x180015158  mov     [rsp+150h+var_120], 0
0x180015161  mov     [rsp+150h+var_100], 0
0x18001516a  mov     [rsp+150h+var_118], 0
0x180015173  lea     rcx, [rsp+150h+var_F8]
0x180015178  call    ??0?$vector@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<DisplayInfo>>::vector<std::unique_ptr<DisplayInfo>>(void)
0x18001517d  nop
0x18001517e  test    r15, r15
0x180015181  jnz     short loc_1800151B2
0x180015183  mov     r8d, 80070057h
0x180015189  mov     ebx, r8d
0x18001518c  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180015193  jz      loc_180015458
0x180015199  lea     rax, aCprPpjsonvalue; "CPR(ppJsonValue)"
0x1800151a0  mov     [rsp+150h+var_128], rax
0x1800151a5  mov     dword ptr [rsp+150h+var_130], 32Fh
0x1800151ad  jmp     loc_18001544B
0x1800151b2  cmp     qword ptr [r15], 0
0x1800151b6  jnz     loc_180015425
0x1800151bc  mov     [rbp+50h+var_38], 0
0x1800151c4  mov     r9d, 1Bh; unsigned int
0x1800151ca  lea     r8d, [r9+1]; unsigned int
0x1800151ce  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonArray@@3QBGB; "Windows.Data.Json.JsonArray"
0x1800151d5  lea     rcx, [rbp+50h+hstringHeader]; hstringHeader
0x1800151d9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800151de  nop
0x1800151df  lea     rdx, [rsp+150h+var_120]
0x1800151e4  mov     rcx, [rbp+50h+var_38]
0x1800151e8  call    ??$ActivateInstance@UIJsonArray@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonArray@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonArray>(HSTRING__ *,Windows::Data::Json::IJsonArray * *)
0x1800151ed  mov     ebx, eax
0x1800151ef  test    eax, eax
0x1800151f1  jns     short loc_18001521C
0x1800151f3  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800151fa  jz      loc_180015458
0x180015200  lea     rax, aChrActivateins_9; "CHR(ActivateInstance(HStringReference(R"...
0x180015207  mov     [rsp+150h+var_128], rax
0x18001520c  mov     dword ptr [rsp+150h+var_130], 332h
0x180015214  mov     r8d, ebx
0x180015217  jmp     loc_18001544B
0x18001521c  lea     rdx, [rsp+150h+var_100]
0x180015221  lea     rcx, [rsp+150h+var_120]
0x180015226  call    ??$As@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>>)
0x18001522b  mov     ebx, eax
0x18001522d  test    eax, eax
0x18001522f  jns     short loc_180015254
0x180015231  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180015238  jz      loc_180015458
0x18001523e  lea     rax, aChrPjsonarrayA; "CHR(pJsonArray.As(&pJsonArrayAsVector))"
0x180015245  mov     [rsp+150h+var_128], rax
0x18001524a  mov     dword ptr [rsp+150h+var_130], 333h
0x180015252  jmp     short loc_180015214
0x180015254  mov     dword ptr [rsp+150h+var_108], 0
0x18001525c  call    cs:__imp_SHTaskPoolGetUniqueContext
0x180015262  mov     r10d, eax
0x180015265  lea     r8, [rsp+150h+var_108]
0x18001526a  lea     rdx, [rsp+150h+var_F8]
0x18001526f  lea     rcx, [rbp+50h+hstringHeader]
0x180015273  call    _lambda_5ce3936d8ad826038f88bbedacf4b390____lambda_5ce3936d8ad826038f88bbedacf4b390_
0x180015278  mov     r9, rax
0x18001527b  mov     r8d, r10d
0x18001527e  call    Windows__Internal__ComTaskPool__QueueTask__lambda_5ce3936d8ad826038f88bbedacf4b390___
0x180015283  mov     ebx, eax
0x180015285  test    eax, eax
0x180015287  jns     short loc_1800152A3
0x180015289  mov     rcx, [rbp+58h]; this
0x18001528d  mov     r9d, eax; char *
0x180015290  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180015297  mov     edx, 756h; void *
0x18001529c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800152a1  jmp     short loc_1800152A7
0x1800152a3  mov     ebx, dword ptr [rsp+150h+var_108]
0x1800152a7  mov     r14, qword ptr [rsp+150h+var_F8]
0x1800152ac  mov     r12, qword ptr [rsp+150h+var_F8+8]
0x1800152b1  mov     rax, r12
0x1800152b4  sub     rax, r14
0x1800152b7  sar     rax, 3
0x1800152bb  test    rax, rax
0x1800152be  jz      loc_1800153DB
0x1800152c4  test    ebx, ebx
0x1800152c6  js      loc_1800153DB
0x1800152cc  cmp     r14, r12
0x1800152cf  jz      loc_1800153DB
0x1800152d5  lea     rcx, [rsp+150h+var_110]
0x1800152da  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800152df  lea     rax, [rbp+50h+var_D0]
0x1800152e3  mov     [rsp+150h+var_108], rax
0x1800152e8  mov     rdx, [r14]
0x1800152eb  add     rdx, 820h
0x1800152f2  lea     rcx, [rbp+50h+var_D0]
0x1800152f6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800152fb  mov     rsi, rax
0x1800152fe  lea     rax, [rbp+50h+var_B0]
0x180015302  mov     [rsp+150h+var_E0], rax
0x180015307  mov     rdx, [r14]
0x18001530a  add     rdx, 208h
0x180015311  lea     rcx, [rbp+50h+var_B0]
0x180015315  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001531a  mov     rdi, rax
0x18001531d  lea     rax, [rbp+50h+var_90]
0x180015321  mov     [rsp+150h+var_D8], rax
0x180015326  mov     rdx, [r14]
0x180015329  lea     rcx, [rbp+50h+var_90]
0x18001532d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180015332  mov     rbx, rax
0x180015335  mov     rdx, [r14]
0x180015338  add     rdx, 1658h
0x18001533f  lea     rcx, [rbp+50h+var_70]
0x180015343  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180015348  nop
0x180015349  lea     rcx, [rsp+150h+var_110]
0x18001534e  mov     [rsp+150h+var_130], rcx
0x180015353  mov     r9, rsi
0x180015356  mov     r8, rdi
0x180015359  mov     rdx, rbx
0x18001535c  mov     rcx, rax
0x18001535f  call    ?FormatIndividualHardwareDisplayInfo@DdcDeviceInfoHelper@@SAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@000PEAPEAUIJsonValue@Json@Data@Windows@@@Z; DdcDeviceInfoHelper::FormatIndividualHardwareDisplayInfo(std::wstring,std::wstring,std::wstring,std::wstring,Windows::Data::Json::IJsonValue * *)
0x180015364  mov     ebx, eax
0x180015366  test    eax, eax
0x180015368  js      short loc_1800153B5
0x18001536a  mov     rcx, [rsp+150h+var_100]
0x18001536f  mov     rax, [rcx]
0x180015372  mov     rdx, [rsp+150h+var_110]
0x180015377  mov     rax, [rax+68h]
0x18001537b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015380  mov     ebx, eax
0x180015382  test    eax, eax
0x180015384  js      short loc_18001538F
0x180015386  add     r14, 8
0x18001538a  jmp     loc_1800152CC
0x18001538f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180015396  jz      loc_180015458
0x18001539c  lea     rax, aChrPjsonarraya; "CHR(pJsonArrayAsVector->Append(pJsonVal"...
0x1800153a3  mov     [rsp+150h+var_128], rax
0x1800153a8  mov     dword ptr [rsp+150h+var_130], 348h
0x1800153b0  jmp     loc_180015214
0x1800153b5  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800153bc  jz      loc_180015458
0x1800153c2  lea     rax, aChrFormatindiv; "CHR(FormatIndividualHardwareDisplayInfo"...
0x1800153c9  mov     [rsp+150h+var_128], rax
0x1800153ce  mov     dword ptr [rsp+150h+var_130], 347h
0x1800153d6  jmp     loc_180015214
0x1800153db  lea     rdx, [rsp+150h+var_118]
0x1800153e0  lea     rcx, [rsp+150h+var_120]
0x1800153e5  call    ??$As@UIJsonValue@Json@Data@Windows@@@?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJsonValue@Json@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>>)
0x1800153ea  mov     ebx, eax
0x1800153ec  test    eax, eax
0x1800153ee  jns     short loc_180015412
0x1800153f0  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800153f7  jz      short loc_180015458
0x1800153f9  lea     rax, aChrPjsonarrayA_0; "CHR(pJsonArray.As(&pJsonArrayAsValue))"
0x180015400  mov     [rsp+150h+var_128], rax
0x180015405  mov     dword ptr [rsp+150h+var_130], 34Dh
0x18001540d  jmp     loc_180015214
0x180015412  mov     rax, [rsp+150h+var_118]
0x180015417  mov     [rsp+150h+var_118], 0
0x180015420  mov     [r15], rax
0x180015423  jmp     short loc_180015458
0x180015425  mov     r8d, 80070057h
0x18001542b  mov     ebx, r8d
0x18001542e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180015435  jz      short loc_180015458
0x180015437  lea     rax, aCbrPpjsonvalue_0; "CBR(*ppJsonValue == nullptr)"
0x18001543e  mov     [rsp+150h+var_128], rax
0x180015443  mov     dword ptr [rsp+150h+var_130], 330h
0x18001544b  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180015452  call    McTemplateU0dsqs_EventWriteTransfer
0x180015457  nop
0x180015458  mov     rcx, qword ptr [rsp+150h+var_F8]
0x18001545d  test    rcx, rcx
0x180015460  jz      short loc_180015494
0x180015462  mov     rdx, qword ptr [rsp+150h+var_F8+8]
0x180015467  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@UDisplayInfo@@U?$default_delete@UDisplayInfo@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<DisplayInfo>>>(std::unique_ptr<DisplayInfo> *,std::unique_ptr<DisplayInfo> * const,std::allocator<std::unique_ptr<DisplayInfo>> &)
0x18001546c  mov     rcx, qword ptr [rsp+150h+var_F8]
0x180015471  mov     rdx, [rsp+150h+var_E8]
0x180015476  sub     rdx, rcx
0x180015479  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001547d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015482  xorps   xmm0, xmm0
0x180015485  movdqu  [rsp+150h+var_F8], xmm0
0x18001548b  mov     [rsp+150h+var_E8], 0
0x180015494  lea     rcx, [rsp+150h+var_118]
0x180015499  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001549e  nop
0x18001549f  lea     rcx, [rsp+150h+var_100]
0x1800154a4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800154a9  nop
0x1800154aa  mov     rcx, [rsp+150h+var_120]
0x1800154af  test    rcx, rcx
0x1800154b2  jz      short loc_1800154CA
0x1800154b4  mov     [rsp+150h+var_120], 0
0x1800154bd  mov     rax, [rcx]
0x1800154c0  mov     rax, [rax+10h]
0x1800154c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154c9  nop
0x1800154ca  lea     rcx, [rsp+150h+var_110]
0x1800154cf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800154d4  mov     eax, ebx
0x1800154d6  mov     rcx, [rbp+50h+var_30]
0x1800154da  xor     rcx, rsp; StackCookie
0x1800154dd  call    __security_check_cookie
0x1800154e2  lea     r11, [rsp+150h+var_20]
0x1800154ea  mov     rbx, [r11+38h]
0x1800154ee  mov     rsi, [r11+40h]
0x1800154f2  mov     rsp, r11
0x1800154f5  pop     r15
0x1800154f7  pop     r14
0x1800154f9  pop     r12
0x1800154fb  pop     rdi
0x1800154fc  pop     rbp
0x1800154fd  retn
```
