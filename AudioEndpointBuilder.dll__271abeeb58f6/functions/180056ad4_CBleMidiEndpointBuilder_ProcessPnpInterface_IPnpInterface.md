# CBleMidiEndpointBuilder::ProcessPnpInterface(IPnpInterface *)

- ea: `0x180056ad4`
- end: `0x180056fb8`
- name: `?ProcessPnpInterface@CBleMidiEndpointBuilder@@SAJPEAUIPnpInterface@@@Z`
- size: `1252`
- prototype: `__int64 __fastcall(struct IPnpInterface *)`
- caller_count: `3`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003741c`
- `0x180037a74`
- `0x18004c0cc`

## callees

- `0x180001734`
- `0x180002250`
- `0x180006b0c`
- `0x18000fb60`
- `0x180010dd0`
- `0x18001f374`
- `0x18001f8bc`
- `0x18003e920`
- `0x18004986c`
- `0x1800565dc`
- `0x180056908`
- `0x180056ad4`
- `0x180056fc0`
- `0x180068010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180056d58`
- `ntdll!RtlInitUnicodeString` at `0x180056d58`
- `ntdll!RtlNtStatusToDosError` at `0x180056d74`
- `ntdll!RtlNtStatusToDosError` at `0x180056d74`
- `ntdll!RtlHashUnicodeString` at `0x180056d6c`
- `ntdll!RtlHashUnicodeString` at `0x180056d6c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180056ed8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180056ee2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180056eec`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180056ed8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180056ee2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180056eec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056f58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056f69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056f58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056f69`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CBleMidiEndpointBuilder::ProcessPnpInterface(struct IPnpInterface *a1)
{
  unsigned __int16 *v2; // rbx
  unsigned __int64 v3; // r15
  __int64 (__fastcall *v4)(struct IPnpInterface *, LPVOID *); // rdi
  signed int DeviceContainerDisplayName; // edi
  int BleMidiCapabilities; // eax
  unsigned __int8 v7; // di
  unsigned __int8 v8; // r14
  const struct _tlgProvider_t *v9; // rax
  int v10; // r8d
  int v11; // r9d
  NTSTATUS v12; // eax
  signed int v13; // eax
  __int64 v14; // rsi
  const wchar_t *v15; // rax
  __int64 v16; // r9
  const unsigned __int16 *v17; // r8
  const struct _tlgProvider_t *v18; // rax
  int v19; // r8d
  int v20; // r9d
  const struct _tlgProvider_t *v21; // rax
  int v22; // r8d
  int v23; // r9d
  unsigned __int8 v25[4]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 v26; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int8 v27[3]; // [rsp+55h] [rbp-ABh] BYREF
  unsigned __int64 v28; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  ULONG HashValue; // [rsp+68h] [rbp-98h] BYREF
  LPVOID v31; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v32; // [rsp+78h] [rbp-88h] BYREF
  __int64 v33; // [rsp+80h] [rbp-80h] BYREF
  __int64 (__fastcall ***v34)(_QWORD, GUID *, __int64 *); // [rsp+88h] [rbp-78h] BYREF
  __int64 v35; // [rsp+90h] [rbp-70h] BYREF
  const char *v36; // [rsp+98h] [rbp-68h] BYREF
  PROPVARIANT pvar[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v38; // [rsp+B0h] [rbp-50h]
  unsigned __int16 *v39; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v40; // [rsp+C0h] [rbp-40h] BYREF
  LPVOID v41; // [rsp+C8h] [rbp-38h] BYREF
  struct IPnpInterface *v42; // [rsp+D0h] [rbp-30h] BYREF
  PROPVARIANT v43[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v44; // [rsp+E8h] [rbp-18h]
  struct _UNICODE_STRING DestinationString; // [rsp+F0h] [rbp-10h] BYREF
  PROPVARIANT v46[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v47; // [rsp+110h] [rbp+10h]
  unsigned __int16 v48[104]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v49[264]; // [rsp+1F0h] [rbp+F0h] BYREF
  WCHAR SourceString[264]; // [rsp+400h] [rbp+300h] BYREF

  v35 = 0;
  v42 = a1;
  if ( a1 )
    (*(void (__fastcall **)(struct IPnpInterface *))(*(_QWORD *)a1 + 8LL))(a1);
  v34 = 0;
  v33 = 0;
  pv = 0;
  v2 = 0;
  v32 = 0;
  HashValue = 0;
  DestinationString = 0;
  v3 = 0;
  v28 = 0;
  *(_OWORD *)pvar = 0;
  v38 = 0;
  *(_OWORD *)v46 = 0;
  v47 = 0;
  *(_OWORD *)v43 = 0;
  v44 = 0;
  v4 = *(__int64 (__fastcall **)(struct IPnpInterface *, LPVOID *))(*(_QWORD *)a1 + 32LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  DeviceContainerDisplayName = v4(a1, &pv);
  if ( DeviceContainerDisplayName >= 0 )
  {
    *(_WORD *)v25 = 0;
    BleMidiCapabilities = CBleMidiEndpointBuilder::GetBleMidiCapabilities((const unsigned __int16 *)pv, v25, &v25[1]);
    DeviceContainerDisplayName = BleMidiCapabilities;
    if ( BleMidiCapabilities == -2147418113 )
    {
      DeviceContainerDisplayName = CBleMidiEndpointBuilder::ReadDeviceTag((const unsigned __int16 *)pv, &v28);
      if ( DeviceContainerDisplayName < 0 )
        goto LABEL_35;
      v7 = 1;
      *(_WORD *)v25 = 257;
      v8 = 1;
      v3 = v28;
    }
    else
    {
      if ( BleMidiCapabilities < 0 )
        goto LABEL_35;
      v8 = v25[1];
      v7 = v25[0];
    }
    v9 = AudioEndpointBuilderTelemetryProvider::Provider();
    if ( *(_DWORD *)v9 > 4u )
    {
      v28 = v3;
      v26 = v8;
      v27[0] = v7;
      v31 = pv;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
        (_DWORD)v9,
        (unsigned int)&byte_180077017,
        v10,
        v11,
        (__int64)&v31,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v28);
    }
    DeviceContainerDisplayName = (*(__int64 (__fastcall **)(struct IPnpInterface *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)a1 + 24LL))(
                                   a1,
                                   &v34);
    if ( DeviceContainerDisplayName >= 0 )
    {
      DeviceContainerDisplayName = (**v34)(v34, &GUID_d666063f_1587_4e43_81f1_b948e807363f, &v35);
      if ( DeviceContainerDisplayName >= 0 )
      {
        DeviceContainerDisplayName = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v35 + 32LL))(
                                       v35,
                                       0,
                                       &v33);
        if ( DeviceContainerDisplayName >= 0 )
        {
          DeviceContainerDisplayName = (*(__int64 (__fastcall **)(__int64, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)v33 + 40LL))(
                                         v33,
                                         &DEVPKEY_Device_InstanceId,
                                         pvar);
          if ( DeviceContainerDisplayName >= 0 )
          {
            DeviceContainerDisplayName = (*(__int64 (__fastcall **)(__int64, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)v33 + 40LL))(
                                           v33,
                                           &DEVPKEY_Device_ContainerId,
                                           v43);
            if ( DeviceContainerDisplayName >= 0 )
            {
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                &v32,
                0);
              DeviceContainerDisplayName = CBleMidiEndpointBuilder::GetDeviceContainerDisplayName(
                                             (const struct _GUID *)v43[1],
                                             &v32);
              if ( DeviceContainerDisplayName < 0 )
                goto LABEL_34;
              StringCchPrintfW(SourceString, 0x104u, L"%s%I64u", pvar[1], v3);
              RtlInitUnicodeString(&DestinationString, SourceString);
              v12 = RtlHashUnicodeString(&DestinationString, 1u, 0, &HashValue);
              v13 = RtlNtStatusToDosError(v12);
              DeviceContainerDisplayName = v13;
              if ( v13 > 0 )
                DeviceContainerDisplayName = (unsigned __int16)v13 | 0x80070000;
              if ( DeviceContainerDisplayName < 0 )
              {
LABEL_34:
                v2 = v32;
              }
              else
              {
                v14 = 0;
                v2 = v32;
                do
                {
                  if ( v25[v14] )
                  {
                    v15 = L"MIDI IN";
                    if ( (_DWORD)v14 )
                      v15 = L"MIDI OUT";
                    StringCchPrintfW(v49, 0x104u, L"%s (Bluetooth %s)", v2, v15);
                    v16 = HashValue;
                    if ( (_DWORD)v14 )
                      v16 = HashValue + 1;
                    v17 = L"VMIDI_%08I32X.BLE10";
                    if ( !v3 )
                      v17 = L"MIDII_%08I32X.BLE10";
                    StringCchPrintfW(v48, 0x64u, v17, v16);
                    DeviceContainerDisplayName = CreateMidiPort(
                                                   (const unsigned __int16 *)pvar[1],
                                                   (const unsigned __int16 *)pv,
                                                   v48,
                                                   v49,
                                                   (enum __MIDL___MIDL_itf_devicetopology_0000_0000_0011)((_DWORD)v14 != 0),
                                                   0,
                                                   v3);
                    v18 = AudioEndpointBuilderTelemetryProvider::Provider();
                    if ( *(_DWORD *)v18 > 4u )
                    {
                      LODWORD(v31) = DeviceContainerDisplayName;
                      LODWORD(v28) = v14;
                      v39 = v49;
                      v40 = v48;
                      v41 = pv;
                      v36 = (const char *)pvar[1];
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                        (_DWORD)v18,
                        (unsigned int)&dword_180076F7C,
                        v19,
                        v20,
                        (__int64)&v36,
                        (__int64)&v41,
                        (__int64)&v40,
                        (__int64)&v39,
                        (__int64)&v28,
                        (__int64)&v31);
                    }
                    if ( DeviceContainerDisplayName && DeviceContainerDisplayName != -2147024713 )
                      break;
                  }
                  v14 = (unsigned int)(v14 + 1);
                }
                while ( (int)v14 < 2 );
              }
            }
          }
        }
      }
    }
  }
LABEL_35:
  PropVariantClear(pvar);
  PropVariantClear(v46);
  PropVariantClear(v43);
  if ( DeviceContainerDisplayName < 0 )
  {
    v21 = AudioEndpointBuilderTelemetryProvider::Provider();
    if ( *(_DWORD *)v21 > 2u )
    {
      LODWORD(v28) = DeviceContainerDisplayName;
      LODWORD(v31) = 421;
      v36 = "CBleMidiEndpointBuilder::ProcessPnpInterface";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v21,
        (unsigned int)&byte_180076F27,
        v22,
        v23,
        (__int64)&v36,
        (__int64)&v31,
        (__int64)&v28);
    }
    if ( DeviceContainerDisplayName == -2147024713 )
      DeviceContainerDisplayName = 0;
  }
  if ( v2 )
    CoTaskMemFree(v2);
  if ( pv )
    CoTaskMemFree(pv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
  return (unsigned int)DeviceContainerDisplayName;
}

```

## disassembly

```asm
0x180056ad4  push    rbp
0x180056ad6  push    rbx
0x180056ad7  push    rsi
0x180056ad8  push    rdi
0x180056ad9  push    r14
0x180056adb  push    r15
0x180056add  lea     rbp, [rsp-528h]
0x180056ae5  sub     rsp, 628h
0x180056aec  mov     rax, cs:__security_cookie
0x180056af3  xor     rax, rsp
0x180056af6  mov     [rbp+550h+var_40], rax
0x180056afd  mov     rsi, rcx
0x180056b00  mov     [rbp+550h+var_5C0], 0
0x180056b08  mov     [rbp+550h+var_580], rcx
0x180056b0c  test    rcx, rcx
0x180056b0f  jz      short loc_180056B1E
0x180056b11  mov     rax, [rcx]
0x180056b14  mov     rax, [rax+8]
0x180056b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056b1d  nop
0x180056b1e  mov     [rbp+550h+var_5C8], 0
0x180056b26  mov     [rbp+550h+var_5D0], 0
0x180056b2e  mov     [rsp+650h+pv], 0
0x180056b37  xor     ebx, ebx
0x180056b39  mov     [rsp+650h+var_5D8], rbx
0x180056b3e  mov     [rsp+650h+HashValue], ebx
0x180056b42  xorps   xmm0, xmm0
0x180056b45  movups  xmmword ptr [rbp+550h+DestinationString.Length], xmm0
0x180056b49  xor     r15d, r15d
0x180056b4c  mov     [rsp+650h+var_5F8], r15
0x180056b51  xor     eax, eax
0x180056b53  movups  xmmword ptr [rbp+550h+pvar], xmm0
0x180056b57  mov     [rbp+550h+var_5A0], rax
0x180056b5b  xorps   xmm1, xmm1
0x180056b5e  movups  xmmword ptr [rbp+550h+var_550], xmm1
0x180056b62  mov     [rbp+550h+var_540], rax
0x180056b66  movups  xmmword ptr [rbp+550h+var_578], xmm0
0x180056b6a  mov     [rbp+550h+var_568], rax
0x180056b6e  mov     rax, [rsi]
0x180056b71  mov     rdi, [rax+20h]
0x180056b75  xor     edx, edx
0x180056b77  lea     rcx, [rsp+650h+pv]
0x180056b7c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180056b81  lea     rdx, [rsp+650h+pv]
0x180056b86  mov     rcx, rsi
0x180056b89  mov     rax, rdi
0x180056b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056b91  mov     edi, eax
0x180056b93  test    eax, eax
0x180056b95  js      loc_180056ED4
0x180056b9b  mov     word ptr [rsp+650h+var_600], r15w
0x180056ba1  lea     r8, [rsp+650h+var_600+1]; unsigned __int8 *
0x180056ba6  lea     rdx, [rsp+650h+var_600]; unsigned __int8 *
0x180056bab  mov     rcx, [rsp+650h+pv]; unsigned __int16 *
0x180056bb0  call    ?GetBleMidiCapabilities@CBleMidiEndpointBuilder@@SAJPEBGPEAE1@Z; CBleMidiEndpointBuilder::GetBleMidiCapabilities(ushort const *,uchar *,uchar *)
0x180056bb5  mov     edi, eax
0x180056bb7  cmp     eax, 8000FFFFh
0x180056bbc  jnz     short loc_180056BEB
0x180056bbe  lea     rdx, [rsp+650h+var_5F8]; unsigned __int64 *
0x180056bc3  mov     rcx, [rsp+650h+pv]; unsigned __int16 *
0x180056bc8  call    ?ReadDeviceTag@CBleMidiEndpointBuilder@@CAJPEBGPEA_K@Z; CBleMidiEndpointBuilder::ReadDeviceTag(ushort const *,unsigned __int64 *)
0x180056bcd  mov     edi, eax
0x180056bcf  test    eax, eax
0x180056bd1  js      loc_180056ED4
0x180056bd7  mov     dil, 1
0x180056bda  mov     word ptr [rsp+650h+var_600], 101h
0x180056be1  mov     r14b, dil
0x180056be4  mov     r15, [rsp+650h+var_5F8]
0x180056be9  jmp     short loc_180056BFD
0x180056beb  test    eax, eax
0x180056bed  js      loc_180056ED4
0x180056bf3  mov     r14b, [rsp+650h+var_600+1]
0x180056bf8  mov     dil, [rsp+650h+var_600]
0x180056bfd  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x180056c02  mov     ecx, [rax]
0x180056c04  cmp     ecx, 4
0x180056c07  jbe     short loc_180056C59
0x180056c09  mov     [rsp+650h+var_5F8], r15
0x180056c0e  mov     [rsp+650h+var_5FC], r14b
0x180056c13  mov     [rsp+650h+var_5FB], dil
0x180056c18  mov     rcx, [rsp+650h+pv]
0x180056c1d  mov     [rsp+650h+var_5E0], rcx
0x180056c22  lea     rcx, [rsp+650h+var_5F8]
0x180056c27  mov     [rsp+650h+var_618], rcx
0x180056c2c  lea     rcx, [rsp+650h+var_5FC]
0x180056c31  mov     [rsp+650h+var_620], rcx
0x180056c36  lea     rcx, [rsp+650h+var_5FB]
0x180056c3b  mov     qword ptr [rsp+650h+var_628], rcx
0x180056c40  lea     rcx, [rsp+650h+var_5E0]
0x180056c45  mov     qword ptr [rsp+650h+var_630], rcx
0x180056c4a  lea     rdx, byte_180077017
0x180056c51  mov     rcx, rax
0x180056c54  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@4AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)
0x180056c59  mov     rax, [rsi]
0x180056c5c  lea     rdx, [rbp+550h+var_5C8]
0x180056c60  mov     rcx, rsi
0x180056c63  mov     rax, [rax+18h]
0x180056c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056c6c  mov     edi, eax
0x180056c6e  test    eax, eax
0x180056c70  js      loc_180056ED4
0x180056c76  mov     rcx, [rbp+550h+var_5C8]
0x180056c7a  mov     rax, [rcx]
0x180056c7d  lea     r8, [rbp+550h+var_5C0]
0x180056c81  lea     rdx, _GUID_d666063f_1587_4e43_81f1_b948e807363f
0x180056c88  mov     rax, [rax]
0x180056c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056c90  mov     edi, eax
0x180056c92  test    eax, eax
0x180056c94  js      loc_180056ED4
0x180056c9a  mov     rcx, [rbp+550h+var_5C0]
0x180056c9e  mov     rax, [rcx]
0x180056ca1  lea     r8, [rbp+550h+var_5D0]
0x180056ca5  xor     edx, edx
0x180056ca7  mov     rax, [rax+20h]
0x180056cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056cb0  mov     edi, eax
0x180056cb2  test    eax, eax
0x180056cb4  js      loc_180056ED4
0x180056cba  mov     rcx, [rbp+550h+var_5D0]
0x180056cbe  mov     rax, [rcx]
0x180056cc1  lea     r8, [rbp+550h+pvar]
0x180056cc5  lea     rdx, DEVPKEY_Device_InstanceId
0x180056ccc  mov     rax, [rax+28h]
0x180056cd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056cd5  mov     edi, eax
0x180056cd7  test    eax, eax
0x180056cd9  js      loc_180056ED4
0x180056cdf  mov     rcx, [rbp+550h+var_5D0]
0x180056ce3  mov     rax, [rcx]
0x180056ce6  lea     r8, [rbp+550h+var_578]
0x180056cea  lea     rdx, DEVPKEY_Device_ContainerId
0x180056cf1  mov     rax, [rax+28h]
0x180056cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056cfa  mov     edi, eax
0x180056cfc  test    eax, eax
0x180056cfe  js      loc_180056ED4
0x180056d04  xor     edx, edx
0x180056d06  lea     rcx, [rsp+650h+var_5D8]
0x180056d0b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180056d10  lea     rdx, [rsp+650h+var_5D8]; unsigned __int16 **
0x180056d15  mov     rcx, [rbp+550h+var_578+8]; struct _GUID *
0x180056d19  call    ?GetDeviceContainerDisplayName@CBleMidiEndpointBuilder@@CAJPEBU_GUID@@PEAPEAG@Z; CBleMidiEndpointBuilder::GetDeviceContainerDisplayName(_GUID const *,ushort * *)
0x180056d1e  mov     edi, eax
0x180056d20  test    eax, eax
0x180056d22  js      loc_180056ECF
0x180056d28  mov     qword ptr [rsp+650h+var_630], r15
0x180056d2d  mov     r9, [rbp+550h+pvar+8]
0x180056d31  lea     r8, aSI64u; "%s%I64u"
0x180056d38  mov     r14d, 104h
0x180056d3e  mov     edx, r14d; unsigned __int64
0x180056d41  lea     rcx, [rbp+550h+SourceString]; unsigned __int16 *
0x180056d48  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180056d4d  lea     rdx, [rbp+550h+SourceString]; SourceString
0x180056d54  lea     rcx, [rbp+550h+DestinationString]; DestinationString
0x180056d58  call    cs:__imp_RtlInitUnicodeString
0x180056d5e  lea     r9, [rsp+650h+HashValue]; HashValue
0x180056d63  xor     r8d, r8d; HashAlgorithm
0x180056d66  mov     dl, 1; CaseInSensitive
0x180056d68  lea     rcx, [rbp+550h+DestinationString]; String
0x180056d6c  call    cs:__imp_RtlHashUnicodeString
0x180056d72  mov     ecx, eax; Status
0x180056d74  call    cs:__imp_RtlNtStatusToDosError
0x180056d7a  mov     edi, eax
0x180056d7c  test    eax, eax
0x180056d7e  jle     short loc_180056D89
0x180056d80  movzx   edi, ax
0x180056d83  or      edi, 80070000h
0x180056d89  test    edi, edi
0x180056d8b  js      loc_180056ECF
0x180056d91  xor     esi, esi
0x180056d93  mov     rbx, [rsp+650h+var_5D8]
0x180056d98  cmp     [rsp+rsi+650h+var_600], 0
0x180056d9d  jz      loc_180056EC2
0x180056da3  lea     rcx, aMidiOut; "MIDI OUT"
0x180056daa  lea     rax, aMidiIn; "MIDI IN"
0x180056db1  test    esi, esi
0x180056db3  cmovnz  rax, rcx
0x180056db7  mov     qword ptr [rsp+650h+var_630], rax
0x180056dbc  mov     r9, rbx
0x180056dbf  lea     r8, aSBluetoothS; "%s (Bluetooth %s)"
0x180056dc6  mov     rdx, r14; unsigned __int64
0x180056dc9  lea     rcx, [rbp+550h+var_460]; unsigned __int16 *
0x180056dd0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180056dd5  mov     r9d, [rsp+650h+HashValue]
0x180056dda  test    esi, esi
0x180056ddc  jz      short loc_180056DE1
0x180056dde  inc     r9d
0x180056de1  lea     r8, aVmidi08i32xBle; "VMIDI_%08I32X.BLE10"
0x180056de8  lea     rax, aMidii08i32xBle; "MIDII_%08I32X.BLE10"
0x180056def  test    r15, r15
0x180056df2  cmovz   r8, rax; unsigned __int16 *
0x180056df6  mov     edx, 64h ; 'd'; unsigned __int64
0x180056dfb  lea     rcx, [rbp+550h+var_530]; unsigned __int16 *
0x180056dff  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180056e04  xor     eax, eax
0x180056e06  test    esi, esi
0x180056e08  setnz   al
0x180056e0b  mov     [rsp+650h+var_620], r15; unsigned __int64
0x180056e10  mov     [rsp+650h+var_628], 0; unsigned int
0x180056e18  mov     [rsp+650h+var_630], eax; enum __MIDL___MIDL_itf_devicetopology_0000_0000_0011
0x180056e1c  lea     r9, [rbp+550h+var_460]; unsigned __int16 *
0x180056e23  lea     r8, [rbp+550h+var_530]; unsigned __int16 *
0x180056e27  mov     rdx, [rsp+650h+pv]; unsigned __int16 *
0x180056e2c  mov     rcx, [rbp+550h+pvar+8]; unsigned __int16 *
0x180056e30  call    ?CreateMidiPort@@YAJPEBG000W4__MIDL___MIDL_itf_devicetopology_0000_0000_0011@@I_K@Z; CreateMidiPort(ushort const *,ushort const *,ushort const *,ushort const *,__MIDL___MIDL_itf_devicetopology_0000_0000_0011,uint,unsigned __int64)
0x180056e35  mov     edi, eax
0x180056e37  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x180056e3c  mov     ecx, [rax]
0x180056e3e  cmp     ecx, 4
0x180056e41  jbe     short loc_180056EB6
0x180056e43  mov     dword ptr [rsp+650h+var_5E0], edi
0x180056e47  mov     dword ptr [rsp+650h+var_5F8], esi
0x180056e4b  lea     rcx, [rbp+550h+var_460]
0x180056e52  mov     [rbp+550h+var_598], rcx
0x180056e56  lea     rcx, [rbp+550h+var_530]
0x180056e5a  mov     [rbp+550h+var_590], rcx
0x180056e5e  mov     rcx, [rsp+650h+pv]
0x180056e63  mov     [rbp+550h+var_588], rcx
0x180056e67  mov     rcx, [rbp+550h+pvar+8]
0x180056e6b  mov     [rbp+550h+var_5B8], rcx
0x180056e6f  lea     rcx, [rsp+650h+var_5E0]
0x180056e74  mov     [rsp+650h+var_608], rcx
0x180056e79  lea     rcx, [rsp+650h+var_5F8]
0x180056e7e  mov     [rsp+650h+var_610], rcx
0x180056e83  lea     rcx, [rbp+550h+var_598]
0x180056e87  mov     [rsp+650h+var_618], rcx
0x180056e8c  lea     rcx, [rbp+550h+var_590]
0x180056e90  mov     [rsp+650h+var_620], rcx
0x180056e95  lea     rcx, [rbp+550h+var_588]
0x180056e99  mov     qword ptr [rsp+650h+var_628], rcx
0x180056e9e  lea     rcx, [rbp+550h+var_5B8]
0x180056ea2  mov     qword ptr [rsp+650h+var_630], rcx
0x180056ea7  lea     rdx, dword_180076F7C
0x180056eae  mov     rcx, rax
0x180056eb1  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@333AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180056eb6  test    edi, edi
0x180056eb8  jz      short loc_180056EC2
0x180056eba  cmp     edi, 800700B7h
0x180056ec0  jnz     short loc_180056ED4
0x180056ec2  inc     esi
0x180056ec4  cmp     esi, 2
0x180056ec7  jl      loc_180056D98
0x180056ecd  jmp     short loc_180056ED4
0x180056ecf  mov     rbx, [rsp+650h+var_5D8]
0x180056ed4  lea     rcx, [rbp+550h+pvar]; pvar
0x180056ed8  call    cs:__imp_PropVariantClear
0x180056ede  lea     rcx, [rbp+550h+var_550]; pvar
0x180056ee2  call    cs:__imp_PropVariantClear
0x180056ee8  lea     rcx, [rbp+550h+var_578]; pvar
0x180056eec  call    cs:__imp_PropVariantClear
0x180056ef2  test    edi, edi
0x180056ef4  jns     short loc_180056F50
0x180056ef6  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x180056efb  mov     ecx, [rax]
0x180056efd  cmp     ecx, 2
0x180056f00  jbe     short loc_180056F45
0x180056f02  mov     dword ptr [rsp+650h+var_5F8], edi
0x180056f06  mov     dword ptr [rsp+650h+var_5E0], 1A5h
0x180056f0e  lea     rcx, aCblemidiendpoi_1; "CBleMidiEndpointBuilder::ProcessPnpInte"...
0x180056f15  mov     [rbp+550h+var_5B8], rcx
0x180056f19  lea     rcx, [rsp+650h+var_5F8]
0x180056f1e  mov     [rsp+650h+var_620], rcx
0x180056f23  lea     rcx, [rsp+650h+var_5E0]
0x180056f28  mov     qword ptr [rsp+650h+var_628], rcx
0x180056f2d  lea     rcx, [rbp+550h+var_5B8]
0x180056f31  mov     qword ptr [rsp+650h+var_630], rcx
0x180056f36  lea     rdx, byte_180076F27
0x180056f3d  mov     rcx, rax
0x180056f40  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180056f45  xor     eax, eax
0x180056f47  cmp     edi, 800700B7h
0x180056f4d  cmovz   edi, eax
0x180056f50  test    rbx, rbx
0x180056f53  jz      short loc_180056F5F
0x180056f55  mov     rcx, rbx; pv
0x180056f58  call    cs:__imp_CoTaskMemFree
0x180056f5e  nop
0x180056f5f  mov     rcx, [rsp+650h+pv]; pv
0x180056f64  test    rcx, rcx
0x180056f67  jz      short loc_180056F70
0x180056f69  call    cs:__imp_CoTaskMemFree
0x180056f6f  nop
0x180056f70  lea     rcx, [rbp+550h+var_5D0]
0x180056f74  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180056f79  nop
0x180056f7a  lea     rcx, [rbp+550h+var_5C8]
0x180056f7e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180056f83  nop
0x180056f84  lea     rcx, [rbp+550h+var_580]
0x180056f88  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180056f8d  nop
0x180056f8e  lea     rcx, [rbp+550h+var_5C0]
0x180056f92  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180056f97  mov     eax, edi
0x180056f99  mov     rcx, [rbp+550h+var_40]
0x180056fa0  xor     rcx, rsp; StackCookie
0x180056fa3  call    __security_check_cookie
0x180056fa8  add     rsp, 628h
0x180056faf  pop     r15
  ... truncated ...
```
