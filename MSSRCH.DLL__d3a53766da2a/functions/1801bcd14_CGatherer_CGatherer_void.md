# CGatherer::CGatherer(void)

- ea: `0x1801bcd14`
- end: `0x1801bd6a7`
- name: `??0CGatherer@@QEAA@XZ`
- size: `2451`
- prototype: `CGatherer *__fastcall(CGatherer *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801b81e4`

## callees

- `0x18001d880`
- `0x180026b58`
- `0x18007cbf4`
- `0x18008cdf4`
- `0x18008d92c`
- `0x1800b172c`
- `0x1800c03ac`
- `0x1800e95f0`
- `0x1800ef01c`
- `0x1801244f0`
- `0x1801bca08`
- `0x1801bcb50`
- `0x1801bcc80`
- `0x1801bcd14`
- `0x1801bd6b0`
- `0x1801bd7cc`
- `0x1801bd88c`
- `0x1801bd9c4`
- `0x1801bda8c`
- `0x1801c3850`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1801bd634`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1801bd634`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801bd651`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1801bd651`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801bcedc`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801bd076`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801bd09e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801bd31b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801bd37c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801bd52c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801bd56f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801bcedc`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801bd076`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801bd09e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801bd31b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801bd37c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801bd52c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801bd56f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1801bd35f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1801bd35f`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x1801bd670`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolGetUniqueContext` at `0x1801bd670`

## pseudocode

```c
// Hidden C++ exception states: #wind=61
CGatherer *__fastcall CGatherer::CGatherer(CGatherer *this)
{
  __int64 *v2; // rbx
  __int64 size_of; // rax
  __int64 v4; // rax
  int v5; // edx
  _QWORD *v6; // rax
  HANDLE EventW; // rax
  const char *v8; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *((_DWORD *)this + 40) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_DWORD *)this + 46) = 1;
  *(_QWORD *)this = &CGatherer::`vftable'{for `ATL::IDispatchImpl<IGatherAdmin5,&__s_GUID const _GUID_de30a165_95ee_4e18_a0f4_0103f8badaa4,&_GUID const LIBID_MSSITLB,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)this + 1) = &CGatherer::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 2) = &CGatherer::`vftable'{for `IGather'};
  *((_QWORD *)this + 3) = &CGatherer::`vftable'{for `IGatherDataSite2'};
  *((_QWORD *)this + 4) = &CGatherer::`vftable'{for `IGatherDataSink'};
  *((_QWORD *)this + 5) = &IDriveChangeSink::`vftable';
  *((_QWORD *)this + 6) = &CGatherer::`vftable'{for `IGatherNotify2'};
  *((_QWORD *)this + 7) = &CGatherer::`vftable'{for `IGatherUsn'};
  *((_QWORD *)this + 8) = &CGatherer::`vftable'{for `CSecurityProxyFactory<CGatherer,IGatherAdmin5,&__s_GUID const _GUID_de30a165_95ee_4e18_a0f4_0103f8badaa4>'};
  *((_QWORD *)this + 9) = &CGatherer::`vftable'{for `IGatherNotifyInlineInternal'};
  *((_QWORD *)this + 10) = &CGatherer::`vftable'{for `IGatherDataChange'};
  *((_QWORD *)this + 11) = &CGatherer::`vftable'{for `IGatherLock'};
  *((_QWORD *)this + 12) = &CGatherer::`vftable'{for `IGatherStoreAppCleanup'};
  *((_QWORD *)this + 13) = &CGatherer::`vftable'{for `IGatherStoreAppSize'};
  *((_QWORD *)this + 14) = &CGatherer::`vftable'{for `IGathererPrivate'};
  *((_QWORD *)this + 15) = &CGatherer::`vftable'{for `ISyncTransferStatus'};
  *((_QWORD *)this + 16) = &CGatherer::`vftable'{for `ISyncTransferStatus2'};
  *((_QWORD *)this + 17) = &CGatherer::`vftable'{for `IGatherStoreScopeNotification'};
  *((_QWORD *)this + 18) = &CGatherer::`vftable'{for `IVolatilePropertyStoreEndpoint'};
  *((_QWORD *)this + 19) = &CGatherer::`vftable'{for `IGatherReportUsage'};
  *((_OWORD *)this + 12) = 0;
  *((_QWORD *)this + 26) = 0;
  v2 = (__int64 *)((char *)this + 224);
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  size_of = std::_Get_size_of_n<80>(1);
  v4 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  *(_QWORD *)v4 = v4;
  *(_QWORD *)(v4 + 8) = v4;
  *(_QWORD *)(v4 + 16) = v4;
  *(_WORD *)(v4 + 24) = 257;
  *v2 = v4;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 32) = (char *)this + 272;
  *((_QWORD *)this + 33) = 33;
  *((_WORD *)this + 136) = 0;
  *((_QWORD *)this + 31) = &TLMString<32,32,1024>::`vftable';
  *((_QWORD *)this + 44) = (char *)this + 368;
  *((_QWORD *)this + 45) = 33;
  *((_WORD *)this + 184) = 0;
  *((_QWORD *)this + 43) = &TLMString<32,32,1024>::`vftable';
  *((_QWORD *)this + 55) = 0;
  *((_QWORD *)this + 56) = 0;
  *((_BYTE *)this + 496) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 456));
  *((_QWORD *)this + 63) = 0;
  *((_QWORD *)this + 64) = 0;
  std::map<std::wstring,bool>::map<std::wstring,bool>((char *)this + 520);
  *((_QWORD *)this + 68) = (char *)this + 560;
  *((_QWORD *)this + 69) = 65;
  *((_WORD *)this + 280) = 0;
  *((_QWORD *)this + 67) = &CCICommonPathString::`vftable';
  *((_QWORD *)this + 88) = (char *)this + 720;
  *((_QWORD *)this + 89) = 65;
  *((_WORD *)this + 360) = 0;
  *((_QWORD *)this + 87) = &CCICommonPathString::`vftable';
  *((_QWORD *)this + 108) = (char *)this + 880;
  *((_QWORD *)this + 109) = 65;
  *((_WORD *)this + 440) = 0;
  *((_QWORD *)this + 107) = &CCICommonPathString::`vftable';
  *((_QWORD *)this + 127) = 0;
  *((_DWORD *)this + 256) = 1;
  *((_QWORD *)this + 129) = &CTComObjHMap<TLMString<32,32,1024>,CVariantObject,CLMSubStr>::`vftable';
  *((_QWORD *)this + 130) = HashCStringHashKey;
  *((_QWORD *)this + 131) = HashCStringHashKey;
  *((_DWORD *)this + 266) = 17;
  *((_DWORD *)this + 268) = 3;
  *((_DWORD *)this + 269) = 11;
  CTComObjHMap<unsigned long,CStartPage,unsigned long>::Init();
  *((_QWORD *)this + 137) = (char *)this + 1096;
  *((_QWORD *)this + 136) = (char *)this + 1096;
  *((_QWORD *)this + 138) = (char *)this + 1088;
  *((_DWORD *)this + 278) = 0;
  *((_DWORD *)this + 280) = 0;
  *((_QWORD *)this + 143) = (char *)this + 1144;
  *((_QWORD *)this + 142) = (char *)this + 1144;
  *((_QWORD *)this + 144) = (char *)this + 1136;
  *((_DWORD *)this + 290) = 0;
  *((_QWORD *)this + 141) = &CTLnkList<CProtocolAccessType>::`vftable';
  *((_DWORD *)this + 292) = -1;
  *(_QWORD *)((char *)this + 1172) = 1;
  *(_QWORD *)((char *)this + 1180) = 0;
  *(_QWORD *)((char *)this + 1188) = 0;
  *(_QWORD *)((char *)this + 1196) = 0;
  *((_DWORD *)this + 301) = 0;
  *((_QWORD *)this + 151) = 1;
  *((_DWORD *)this + 304) = 0;
  *((_DWORD *)this + 305) = 1;
  *((_DWORD *)this + 309) = 4;
  *((_DWORD *)this + 310) = -1;
  *((_DWORD *)this + 311) = -1;
  *((_QWORD *)this + 156) = 0;
  *((_DWORD *)this + 314) = 0;
  *((_DWORD *)this + 315) = 1;
  *((_BYTE *)this + 1312) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 1272));
  *((_QWORD *)this + 165) = 4;
  *((_DWORD *)this + 332) = 0;
  *((_QWORD *)this + 167) = 0;
  *((_QWORD *)this + 168) = 0;
  *((_BYTE *)this + 1392) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 1352));
  *((_QWORD *)this + 175) = 0;
  *((_QWORD *)this + 176) = 0;
  *((_QWORD *)this + 177) = 0;
  *((_QWORD *)this + 179) = 0;
  *((_QWORD *)this + 180) = 0;
  *((_QWORD *)this + 181) = 0;
  *((_DWORD *)this + 374) = 0;
  *((_QWORD *)this + 188) = 0;
  *((_QWORD *)this + 189) = 0;
  *((_QWORD *)this + 190) = 0;
  *((_QWORD *)this + 191) = 0;
  CSyncReadWrite::CSyncReadWrite((CGatherer *)((char *)this + 1536), v5);
  *((_QWORD *)this + 206) = 0;
  *((_QWORD *)this + 207) = 0;
  *((_QWORD *)this + 208) = 0;
  *((_DWORD *)this + 418) = 0;
  *((_DWORD *)this + 419) = 1;
  *((_QWORD *)this + 210) = 1;
  *((_DWORD *)this + 422) = 0;
  *((_QWORD *)this + 213) = (char *)this + 1720;
  *((_QWORD *)this + 214) = 33;
  *((_WORD *)this + 860) = 0;
  *((_QWORD *)this + 212) = &TLMString<32,32,1024>::`vftable';
  *((_QWORD *)this + 224) = 0;
  *((_DWORD *)this + 451) = 86400;
  *((_DWORD *)this + 452) = 86400;
  *((_QWORD *)this + 228) = (char *)this + 1840;
  *((_QWORD *)this + 229) = 33;
  *((_WORD *)this + 920) = 0;
  *((_QWORD *)this + 227) = &TLMString<32,32,1024>::`vftable';
  *((_QWORD *)this + 240) = (char *)this + 1936;
  *((_QWORD *)this + 241) = 33;
  *((_WORD *)this + 968) = 0;
  *((_QWORD *)this + 239) = &TLMString<32,32,1024>::`vftable';
  *((_DWORD *)this + 503) = 0;
  CSiteRestrCollection::CSiteRestrCollection((CGatherer *)((char *)this + 2016));
  *((_QWORD *)this + 252) = &CComContainedNoOuterQI<CSiteRestrCollection>::`vftable'{for `ATL::IDispatchImpl<ISiteRestrictions3,&__s_GUID const _GUID_13ceca1c_85e3_48f1_8b96_6c2335ff122a,&_GUID const LIBID_MSSITLB,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)this + 253) = &CComContainedNoOuterQI<CSiteRestrCollection>::`vftable'{for `ATL::ISupportErrorInfoImpl<&__s_GUID const _GUID_13ceca1c_85e3_48f1_8b96_6c2335ff122a>'};
  *((_QWORD *)this + 259) = &CComContainedNoOuterQI<CSiteRestrCollection>::`vftable';
  *((_QWORD *)this + 254) = this;
  CExtCll::CExtCll((CGatherer *)((char *)this + 2256));
  *((_QWORD *)this + 282) = &CComContainedNoOuterQI<CExtCll>::`vftable'{for `ATL::IDispatchImpl<IExtensions,&__s_GUID const _GUID_9d0876ca_02dc_453a_95d9_f2194a656442,&_GUID const LIBID_MSSITLB,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)this + 283) = &CComContainedNoOuterQI<CExtCll>::`vftable'{for `ATL::ISupportErrorInfoImpl<&__s_GUID const _GUID_9d0876ca_02dc_453a_95d9_f2194a656442>'};
  *((_QWORD *)this + 289) = &CComContainedNoOuterQI<CExtCll>::`vftable';
  *((_QWORD *)this + 284) = this;
  CStartPageCollection::CStartPageCollection((CGatherer *)((char *)this + 2504));
  *((_QWORD *)this + 313) = &CComContainedNoOuterQI<CStartPageCollection>::`vftable'{for `ATL::IDispatchImpl<IStartAddresses4,&__s_GUID const _GUID_3155ef53_8bdd_484b_86a1_b82b77e803ab,&_GUID const LIBID_MSSITLB,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)this + 314) = &CComContainedNoOuterQI<CStartPageCollection>::`vftable'{for `ATL::ISupportErrorInfoImpl<&__s_GUID const _GUID_3155ef53_8bdd_484b_86a1_b82b77e803ab>'};
  *((_QWORD *)this + 320) = &CComContainedNoOuterQI<CStartPageCollection>::`vftable';
  *((_QWORD *)this + 315) = this;
  CUMapCll::CUMapCll((CGatherer *)((char *)this + 2928));
  *((_QWORD *)this + 366) = &CComContainedNoOuterQI<CUMapCll>::`vftable'{for `ATL::IDispatchImpl<IMappings,&__s_GUID const _GUID_b05651d3_9b10_425e_b616_1fcd828db3b1,&_GUID const LIBID_MSSITLB,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)this + 367) = &CComContainedNoOuterQI<CUMapCll>::`vftable'{for `ATL::ISupportErrorInfoImpl<&__s_GUID const _GUID_b05651d3_9b10_425e_b616_1fcd828db3b1>'};
  *((_QWORD *)this + 373) = &CComContainedNoOuterQI<CUMapCll>::`vftable';
  *((_QWORD *)this + 368) = this;
  CProtocolCollection::CProtocolCollection((CGatherer *)((char *)this + 3232));
  *((_QWORD *)this + 404) = &CComContainedNoOuterQI<CProtocolCollection>::`vftable'{for `ATL::IDispatchImpl<IProtocols,&__s_GUID const _GUID_b05651d5_9b10_425e_b616_1fcd828db3b1,&_GUID const LIBID_MSSITLB,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)this + 405) = &CComContainedNoOuterQI<CProtocolCollection>::`vftable'{for `ATL::ISupportErrorInfoImpl<&__s_GUID const _GUID_b05651d5_9b10_425e_b616_1fcd828db3b1>'};
  *((_QWORD *)this + 411) = &CComContainedNoOuterQI<CProtocolCollection>::`vftable';
  *((_QWORD *)this + 406) = this;
  *((_QWORD *)this + 445) = 0;
  *((_QWORD *)this + 446) = 0;
  *((_DWORD *)this + 894) = 0;
  *((_QWORD *)this + 448) = 0;
  *((_DWORD *)this + 898) = 0;
  *((_QWORD *)this + 450) = 0;
  *((_QWORD *)this + 452) = (char *)this + 3632;
  *((_QWORD *)this + 453) = 193;
  *((_WORD *)this + 1816) = 0;
  *((_QWORD *)this + 451) = &TLMString<192,64,32767>::`vftable';
  *((_BYTE *)this + 4064) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 4024));
  CTPtrHashTable<TLMString<192,64,32767>>::CTPtrHashTable<TLMString<192,64,32767>>((char *)this + 4072);
  *((_QWORD *)this + 509) = &CTPtrHTblContainer<TLMString<192,64,32767>>::`vftable';
  *((_QWORD *)this + 516) = 0;
  *((_QWORD *)this + 517) = 0;
  *((_QWORD *)this + 518) = 0;
  *((_QWORD *)this + 519) = 0;
  *((_DWORD *)this + 1040) = 0;
  *((_DWORD *)this + 1041) = GetTickCount();
  *((_QWORD *)this + 521) = 0;
  *((_BYTE *)this + 4248) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 4208));
  *((_QWORD *)this + 532) = &CTComObjHMap<TLMString<32,32,1024>,CVariantObject,CLMSubStr>::`vftable';
  *((_QWORD *)this + 533) = HashCStringHashKey;
  *((_QWORD *)this + 534) = HashCStringHashKey;
  *((_DWORD *)this + 1072) = 17;
  *((_QWORD *)this + 537) = 3;
  CTComObjHMap<unsigned long,CInlineNotificationClient,unsigned long>::Init();
  *((_DWORD *)this + 1078) = 1;
  *((_QWORD *)this + 542) = (char *)this + 4336;
  *((_QWORD *)this + 541) = (char *)this + 4336;
  *((_QWORD *)this + 543) = (char *)this + 4328;
  *((_DWORD *)this + 1088) = 0;
  *((_QWORD *)this + 540) = &CTLnkListContainer<CInlineNotification>::`vftable';
  *((_DWORD *)this + 1090) = 0;
  *((_QWORD *)this + 546) = 0;
  *((_QWORD *)this + 547) = 0;
  *((_QWORD *)this + 548) = 0;
  *((_QWORD *)this + 549) = 0;
  *((_QWORD *)this + 550) = 0;
  *((_QWORD *)this + 551) = 0;
  *((_QWORD *)this + 552) = 0;
  *((_QWORD *)this + 553) = 0;
  *((_QWORD *)this + 554) = 0;
  *((_QWORD *)this + 555) = 0;
  *((_QWORD *)this + 556) = 0;
  *((_QWORD *)this + 557) = 0;
  *((_QWORD *)this + 558) = 0;
  *((_QWORD *)this + 559) = 0;
  *((_QWORD *)this + 560) = 0;
  *((_QWORD *)this + 561) = 0;
  *((_QWORD *)this + 562) = 0;
  *((_QWORD *)this + 563) = 0;
  *((_QWORD *)this + 564) = 0;
  *((_QWORD *)this + 565) = 0;
  *((_QWORD *)this + 566) = 0;
  *((_QWORD *)this + 567) = 0;
  *((_QWORD *)this + 568) = 0;
  *((_QWORD *)this + 569) = 0;
  *((_QWORD *)this + 570) = 0;
  *((_QWORD *)this + 571) = 0;
  *((_QWORD *)this + 572) = 0;
  *((_QWORD *)this + 573) = 0;
  *((_DWORD *)this + 1148) = 0;
  *((_BYTE *)this + 4596) = 0;
  *((_QWORD *)this + 575) = 0;
  *((_DWORD *)this + 1152) = 1;
  *((_QWORD *)this + 578) = (char *)this + 4640;
  *((_QWORD *)this + 579) = 65;
  *((_WORD *)this + 2320) = 0;
  *((_QWORD *)this + 577) = &CCICommonPathString::`vftable';
  *((_BYTE *)this + 4776) = 0;
  *((_QWORD *)this + 599) = (char *)this + 4808;
  *((_QWORD *)this + 600) = 193;
  *((_WORD *)this + 2404) = 0;
  *((_QWORD *)this + 598) = &TLMString<192,64,32767>::`vftable';
  *((_QWORD *)this + 650) = 0;
  *((_BYTE *)this + 5248) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 5208));
  *((_QWORD *)this + 657) = 1;
  *((_QWORD *)this + 658) = 0;
  *((_DWORD *)this + 1318) = 5;
  *((_BYTE *)this + 5276) = 0;
  *((_DWORD *)this + 1320) = -1;
  *((_DWORD *)this + 1321) = 0;
  *((_BYTE *)this + 5328) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 5288));
  std::map<unsigned long,unsigned long>::map<unsigned long,unsigned long>((char *)this + 5336);
  std::queue<TComNoUnkPointer<CStartPage>>::queue<TComNoUnkPointer<CStartPage>,std::deque<TComNoUnkPointer<CStartPage>>>((char *)this + 5352);
  *((_QWORD *)this + 674) = &DynamicArray<ATL::CComPtr<IGatherCrawl>>::`vftable';
  *((_QWORD *)this + 675) = 0;
  *((_QWORD *)this + 676) = 0;
  *((_BYTE *)this + 5416) = 0;
  *((_QWORD *)this + 678) = &DynamicArray<SDataChange *>::`vftable';
  *((_QWORD *)this + 679) = 0;
  *((_QWORD *)this + 680) = 0;
  *((_BYTE *)this + 5448) = 0;
  *((_QWORD *)this + 682) = 0;
  *((_QWORD *)this + 683) = 0;
  *((_QWORD *)this + 684) = 0;
  *((_QWORD *)this + 685) = 0;
  *((_QWORD *)this + 686) = 0;
  FileExclusionCache::FileExclusionCache((CGatherer *)((char *)this + 5496));
  *((_QWORD *)this + 690) = 0;
  *((_QWORD *)this + 691) = 0;
  v6 = operator new(0x30u);
  *v6 = v6;
  v6[1] = v6;
  v6[2] = v6;
  *((_WORD *)v6 + 12) = 257;
  *((_QWORD *)this + 690) = v6;
  InitializeSRWLock((PSRWLOCK)this + 692);
  *((_QWORD *)this + 693) = 0;
  CGatherer::UpdateConsistentState(this);
  EventW = CreateEventW(0, 1, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 3584,
    EventW);
  if ( ((*((_QWORD *)this + 448) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xF7,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\server\\gatherobj.cxx",
      v8);
  *((_DWORD *)this + 54) = SHTaskPoolGetUniqueContext();
  return this;
}

```

## disassembly

```asm
0x1801bcd14  mov     [rsp+arg_10], rbx
0x1801bcd19  mov     [rsp+arg_0], rcx
0x1801bcd1e  push    rbp
0x1801bcd1f  push    rsi
0x1801bcd20  push    rdi
0x1801bcd21  push    r13
0x1801bcd23  push    r14
0x1801bcd25  sub     rsp, 20h
0x1801bcd29  mov     rsi, rcx
0x1801bcd2c  xor     edi, edi
0x1801bcd2e  mov     [rcx+0A0h], edi
0x1801bcd34  mov     [rcx+0B0h], rdi
0x1801bcd3b  mov     dword ptr [rcx+0B8h], 1
0x1801bcd45  lea     rax, ??_7CGatherer@@6B?$IDispatchImpl@UIGatherAdmin5@@$1?_GUID_de30a165_95ee_4e18_a0f4_0103f8badaa4@@3U__s_GUID@@B$1?LIBID_MSSITLB@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const CGatherer::`vftable'{for `ATL::IDispatchImpl<IGatherAdmin5,&__s_GUID const _GUID_de30a165_95ee_4e18_a0f4_0103f8badaa4,&_GUID const LIBID_MSSITLB,1,0,ATL::CComTypeInfoHolder>'}
0x1801bcd4c  mov     [rcx], rax
0x1801bcd4f  lea     rax, ??_7CGatherer@@6BISupportErrorInfo@@@; const CGatherer::`vftable'{for `ISupportErrorInfo'}
0x1801bcd56  mov     [rcx+8], rax
0x1801bcd5a  lea     rax, ??_7CGatherer@@6BIGather@@@; const CGatherer::`vftable'{for `IGather'}
0x1801bcd61  mov     [rcx+10h], rax
0x1801bcd65  lea     rax, ??_7CGatherer@@6BIGatherDataSite2@@@; const CGatherer::`vftable'{for `IGatherDataSite2'}
0x1801bcd6c  mov     [rcx+18h], rax
0x1801bcd70  lea     rax, ??_7CGatherer@@6BIGatherDataSink@@@; const CGatherer::`vftable'{for `IGatherDataSink'}
0x1801bcd77  mov     [rcx+20h], rax
0x1801bcd7b  lea     rax, ??_7IDriveChangeSink@@6B@; const IDriveChangeSink::`vftable'
0x1801bcd82  mov     [rcx+28h], rax
0x1801bcd86  lea     rax, ??_7CGatherer@@6BIGatherNotify2@@@; const CGatherer::`vftable'{for `IGatherNotify2'}
0x1801bcd8d  mov     [rcx+30h], rax
0x1801bcd91  lea     rax, ??_7CGatherer@@6BIGatherUsn@@@; const CGatherer::`vftable'{for `IGatherUsn'}
0x1801bcd98  mov     [rcx+38h], rax
0x1801bcd9c  lea     rax, ??_7CGatherer@@6B?$CSecurityProxyFactory@VCGatherer@@UIGatherAdmin5@@$1?_GUID_de30a165_95ee_4e18_a0f4_0103f8badaa4@@3U__s_GUID@@B@@@; const CGatherer::`vftable'{for `CSecurityProxyFactory<CGatherer,IGatherAdmin5,&__s_GUID const _GUID_de30a165_95ee_4e18_a0f4_0103f8badaa4>'}
0x1801bcda3  mov     [rcx+40h], rax
0x1801bcda7  lea     rax, ??_7CGatherer@@6BIGatherNotifyInlineInternal@@@; const CGatherer::`vftable'{for `IGatherNotifyInlineInternal'}
0x1801bcdae  mov     [rcx+48h], rax
0x1801bcdb2  lea     rax, ??_7CGatherer@@6BIGatherDataChange@@@; const CGatherer::`vftable'{for `IGatherDataChange'}
0x1801bcdb9  mov     [rcx+50h], rax
0x1801bcdbd  lea     rax, ??_7CGatherer@@6BIGatherLock@@@; const CGatherer::`vftable'{for `IGatherLock'}
0x1801bcdc4  mov     [rcx+58h], rax
0x1801bcdc8  lea     rax, ??_7CGatherer@@6BIGatherStoreAppCleanup@@@; const CGatherer::`vftable'{for `IGatherStoreAppCleanup'}
0x1801bcdcf  mov     [rcx+60h], rax
0x1801bcdd3  lea     rax, ??_7CGatherer@@6BIGatherStoreAppSize@@@; const CGatherer::`vftable'{for `IGatherStoreAppSize'}
0x1801bcdda  mov     [rcx+68h], rax
0x1801bcdde  lea     rax, ??_7CGatherer@@6BIGathererPrivate@@@; const CGatherer::`vftable'{for `IGathererPrivate'}
0x1801bcde5  mov     [rcx+70h], rax
0x1801bcde9  lea     rax, ??_7CGatherer@@6BISyncTransferStatus@@@; const CGatherer::`vftable'{for `ISyncTransferStatus'}
0x1801bcdf0  mov     [rcx+78h], rax
0x1801bcdf4  lea     rax, ??_7CGatherer@@6BISyncTransferStatus2@@@; const CGatherer::`vftable'{for `ISyncTransferStatus2'}
0x1801bcdfb  mov     [rcx+80h], rax
0x1801bce02  lea     rax, ??_7CGatherer@@6BIGatherStoreScopeNotification@@@; const CGatherer::`vftable'{for `IGatherStoreScopeNotification'}
0x1801bce09  mov     [rcx+88h], rax
0x1801bce10  lea     rax, ??_7CGatherer@@6BIVolatilePropertyStoreEndpoint@@@; const CGatherer::`vftable'{for `IVolatilePropertyStoreEndpoint'}
0x1801bce17  mov     [rcx+90h], rax
0x1801bce1e  lea     rax, ??_7CGatherer@@6BIGatherReportUsage@@@; const CGatherer::`vftable'{for `IGatherReportUsage'}
0x1801bce25  mov     [rcx+98h], rax
0x1801bce2c  xorps   xmm0, xmm0
0x1801bce2f  movups  xmmword ptr [rcx+0C0h], xmm0
0x1801bce36  mov     [rcx+0D0h], rdi
0x1801bce3d  lea     rbx, [rcx+0E0h]
0x1801bce44  mov     [rbx], rdi
0x1801bce47  mov     [rbx+8], rdi
0x1801bce4b  lea     ecx, [rdi+1]
0x1801bce4e  call    ??$_Get_size_of_n@$0FA@@std@@YA_K_K@Z; std::_Get_size_of_n<80>(unsigned __int64)
0x1801bce53  mov     rcx, rax
0x1801bce56  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1801bce5b  mov     [rax], rax
0x1801bce5e  mov     [rax+8], rax
0x1801bce62  mov     [rax+10h], rax
0x1801bce66  mov     word ptr [rax+18h], 101h
0x1801bce6c  mov     [rbx], rax
0x1801bce6f  mov     [rsi+0F0h], rdi
0x1801bce76  lea     rcx, [rsi+110h]
0x1801bce7d  mov     [rsi+100h], rcx
0x1801bce84  mov     qword ptr [rsi+108h], 21h ; '!'
0x1801bce8f  mov     [rcx], di
0x1801bce92  lea     r14, ??_7?$TLMString@$0CA@$0CA@$0EAA@@@6B@; const TLMString<32,32,1024>::`vftable'
0x1801bce99  mov     [rsi+0F8h], r14
0x1801bcea0  lea     rcx, [rsi+170h]
0x1801bcea7  mov     [rsi+160h], rcx
0x1801bceae  mov     qword ptr [rsi+168h], 21h ; '!'
0x1801bceb9  mov     [rcx], di
0x1801bcebc  mov     [rsi+158h], r14
0x1801bcec3  mov     [rsi+1B8h], rdi
0x1801bceca  mov     [rsi+1C0h], rdi
0x1801bced1  lea     rcx, [rsi+1C8h]; lpCriticalSection
0x1801bced8  mov     [rcx+28h], dil
0x1801bcedc  call    cs:__imp_InitializeCriticalSection
0x1801bcee2  nop
0x1801bcee3  mov     [rsi+1F8h], rdi
0x1801bceea  mov     [rsi+200h], rdi
0x1801bcef1  lea     rcx, [rsi+208h]
0x1801bcef8  call    ??0?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,bool>::map<std::wstring,bool>(void)
0x1801bcefd  nop
0x1801bcefe  lea     rcx, [rsi+230h]
0x1801bcf05  mov     [rsi+220h], rcx
0x1801bcf0c  mov     qword ptr [rsi+228h], 41h ; 'A'
0x1801bcf17  mov     [rcx], di
0x1801bcf1a  lea     r8, ??_7CCICommonPathString@@6B@; const CCICommonPathString::`vftable'
0x1801bcf21  mov     [rsi+218h], r8
0x1801bcf28  lea     rcx, [rsi+2D0h]
0x1801bcf2f  mov     [rsi+2C0h], rcx
0x1801bcf36  mov     qword ptr [rsi+2C8h], 41h ; 'A'
0x1801bcf41  mov     [rcx], di
0x1801bcf44  mov     [rsi+2B8h], r8
0x1801bcf4b  lea     rcx, [rsi+370h]
0x1801bcf52  mov     [rsi+360h], rcx
0x1801bcf59  mov     qword ptr [rsi+368h], 41h ; 'A'
0x1801bcf64  mov     [rcx], di
0x1801bcf67  mov     [rsi+358h], r8
0x1801bcf6e  mov     [rsi+3F8h], rdi
0x1801bcf75  mov     dword ptr [rsi+400h], 1
0x1801bcf7f  lea     rcx, [rsi+408h]
0x1801bcf86  lea     rax, ??_7?$CTComObjHMap@V?$TLMString@$0CA@$0CA@$0EAA@@@VCVariantObject@@VCLMSubStr@@@@6B@; const CTComObjHMap<TLMString<32,32,1024>,CVariantObject,CLMSubStr>::`vftable'
0x1801bcf8d  mov     [rcx], rax
0x1801bcf90  lea     r13, ?HashCStringHashKey@@YAKPEBVCStringHashKey@@@Z; HashCStringHashKey(CStringHashKey const *)
0x1801bcf97  mov     [rcx+8], r13
0x1801bcf9b  mov     [rcx+10h], r13
0x1801bcf9f  mov     dword ptr [rcx+20h], 11h
0x1801bcfa6  mov     dword ptr [rcx+28h], 3
0x1801bcfad  mov     dword ptr [rcx+2Ch], 0Bh
0x1801bcfb4  call    ?Init@?$CTComObjHMap@KVCStartPage@@K@@AEAAXXZ; CTComObjHMap<ulong,CStartPage,ulong>::Init(void)
0x1801bcfb9  nop
0x1801bcfba  lea     rcx, [rsi+440h]
0x1801bcfc1  lea     rax, [rcx+8]
0x1801bcfc5  mov     [rax], rax
0x1801bcfc8  mov     [rcx], rax
0x1801bcfcb  mov     [rcx+10h], rcx
0x1801bcfcf  mov     [rcx+18h], edi
0x1801bcfd2  mov     [rsi+460h], edi
0x1801bcfd8  lea     rcx, [rsi+470h]
0x1801bcfdf  lea     rax, [rcx+8]
0x1801bcfe3  mov     [rax], rax
0x1801bcfe6  mov     [rcx], rax
0x1801bcfe9  mov     [rcx+10h], rcx
0x1801bcfed  mov     [rcx+18h], edi
0x1801bcff0  lea     rax, ??_7?$CTLnkList@VCProtocolAccessType@@@@6B@; const CTLnkList<CProtocolAccessType>::`vftable'
0x1801bcff7  mov     [rsi+468h], rax
0x1801bcffe  or      eax, 0FFFFFFFFh
0x1801bd001  mov     [rsi+490h], eax
0x1801bd007  lea     ecx, [rdi+1]
0x1801bd00a  mov     [rsi+494h], rcx
0x1801bd011  mov     [rsi+49Ch], rdi
0x1801bd018  mov     [rsi+4A4h], rdi
0x1801bd01f  mov     [rsi+4ACh], rdi
0x1801bd026  mov     [rsi+4B4h], edi
0x1801bd02c  mov     [rsi+4B8h], rcx
0x1801bd033  mov     [rsi+4C0h], edi
0x1801bd039  mov     [rsi+4C4h], ecx
0x1801bd03f  lea     edi, [rcx+3]
0x1801bd042  mov     [rsi+4D4h], edi
0x1801bd048  mov     [rsi+4D8h], eax
0x1801bd04e  mov     [rsi+4DCh], eax
0x1801bd054  xor     eax, eax
0x1801bd056  mov     [rsi+4E0h], rax
0x1801bd05d  mov     [rsi+4E8h], eax
0x1801bd063  mov     [rsi+4ECh], ecx
0x1801bd069  lea     rbx, [rsi+4F8h]
0x1801bd070  mov     [rbx+28h], al
0x1801bd073  mov     rcx, rbx; lpCriticalSection
0x1801bd076  call    cs:__imp_InitializeCriticalSection
0x1801bd07c  mov     [rbx+30h], rdi
0x1801bd080  xor     edi, edi
0x1801bd082  mov     [rbx+38h], edi
0x1801bd085  mov     [rsi+538h], rdi
0x1801bd08c  mov     [rsi+540h], rdi
0x1801bd093  lea     rcx, [rsi+548h]; lpCriticalSection
0x1801bd09a  mov     [rcx+28h], dil
0x1801bd09e  call    cs:__imp_InitializeCriticalSection
0x1801bd0a4  nop
0x1801bd0a5  mov     [rsi+578h], rdi
0x1801bd0ac  mov     [rsi+580h], rdi
0x1801bd0b3  mov     [rsi+588h], rdi
0x1801bd0ba  mov     [rsi+598h], rdi
0x1801bd0c1  mov     [rsi+5A0h], rdi
0x1801bd0c8  mov     [rsi+5A8h], rdi
0x1801bd0cf  mov     [rsi+5D8h], edi
0x1801bd0d5  mov     [rsi+5E0h], rdi
0x1801bd0dc  mov     [rsi+5E8h], rdi
0x1801bd0e3  mov     [rsi+5F0h], rdi
0x1801bd0ea  mov     [rsi+5F8h], rdi
0x1801bd0f1  lea     rcx, [rsi+600h]; this
0x1801bd0f8  call    ??0CSyncReadWrite@@QEAA@H@Z; CSyncReadWrite::CSyncReadWrite(int)
0x1801bd0fd  nop
0x1801bd0fe  mov     [rsi+670h], rdi
0x1801bd105  mov     [rsi+678h], rdi
0x1801bd10c  mov     [rsi+680h], rdi
0x1801bd113  mov     [rsi+688h], edi
0x1801bd119  mov     dword ptr [rsi+68Ch], 1
0x1801bd123  mov     qword ptr [rsi+690h], 1
0x1801bd12e  mov     [rsi+698h], edi
0x1801bd134  lea     rcx, [rsi+6B8h]
0x1801bd13b  mov     [rsi+6A8h], rcx
0x1801bd142  mov     qword ptr [rsi+6B0h], 21h ; '!'
0x1801bd14d  mov     [rcx], di
0x1801bd150  mov     [rsi+6A0h], r14
0x1801bd157  mov     [rsi+700h], rdi
0x1801bd15e  mov     eax, 15180h
0x1801bd163  mov     [rsi+70Ch], eax
0x1801bd169  mov     [rsi+710h], eax
0x1801bd16f  lea     rcx, [rsi+730h]
0x1801bd176  mov     [rsi+720h], rcx
0x1801bd17d  mov     qword ptr [rsi+728h], 21h ; '!'
0x1801bd188  mov     [rcx], di
0x1801bd18b  mov     [rsi+718h], r14
0x1801bd192  lea     rcx, [rsi+790h]
0x1801bd199  mov     [rsi+780h], rcx
0x1801bd1a0  mov     qword ptr [rsi+788h], 21h ; '!'
0x1801bd1ab  mov     [rcx], di
0x1801bd1ae  mov     [rsi+778h], r14
0x1801bd1b5  mov     [rsi+7DCh], edi
0x1801bd1bb  lea     rbx, [rsi+7E0h]
0x1801bd1c2  mov     rcx, rbx; this
0x1801bd1c5  call    ??0CSiteRestrCollection@@QEAA@XZ; CSiteRestrCollection::CSiteRestrCollection(void)
0x1801bd1ca  lea     rax, ??_7?$CComContainedNoOuterQI@VCSiteRestrCollection@@@@6B?$IDispatchImpl@UISiteRestrictions3@@$1?_GUID_13ceca1c_85e3_48f1_8b96_6c2335ff122a@@3U__s_GUID@@B$1?LIBID_MSSITLB@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const CComContainedNoOuterQI<CSiteRestrCollection>::`vftable'{for `ATL::IDispatchImpl<ISiteRestrictions3,&__s_GUID const _GUID_13ceca1c_85e3_48f1_8b96_6c2335ff122a,&_GUID const LIBID_MSSITLB,1,0,ATL::CComTypeInfoHolder>'}
0x1801bd1d1  mov     [rbx], rax
0x1801bd1d4  lea     rax, ??_7?$CComContainedNoOuterQI@VCSiteRestrCollection@@@@6B?$ISupportErrorInfoImpl@$1?_GUID_13ceca1c_85e3_48f1_8b96_6c2335ff122a@@3U__s_GUID@@B@ATL@@@; const CComContainedNoOuterQI<CSiteRestrCollection>::`vftable'{for `ATL::ISupportErrorInfoImpl<&__s_GUID const _GUID_13ceca1c_85e3_48f1_8b96_6c2335ff122a>'}
0x1801bd1db  mov     [rbx+8], rax
0x1801bd1df  lea     rax, ??_7?$CComContainedNoOuterQI@VCSiteRestrCollection@@@@6B@; const CComContainedNoOuterQI<CSiteRestrCollection>::`vftable'
0x1801bd1e6  mov     [rbx+38h], rax
0x1801bd1ea  mov     [rbx+10h], rsi
0x1801bd1ee  lea     rbx, [rsi+8D0h]
0x1801bd1f5  mov     rcx, rbx; this
0x1801bd1f8  call    ??0CExtCll@@QEAA@XZ; CExtCll::CExtCll(void)
0x1801bd1fd  lea     rax, ??_7?$CComContainedNoOuterQI@VCExtCll@@@@6B?$IDispatchImpl@UIExtensions@@$1?_GUID_9d0876ca_02dc_453a_95d9_f2194a656442@@3U__s_GUID@@B$1?LIBID_MSSITLB@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const CComContainedNoOuterQI<CExtCll>::`vftable'{for `ATL::IDispatchImpl<IExtensions,&__s_GUID const _GUID_9d0876ca_02dc_453a_95d9_f2194a656442,&_GUID const LIBID_MSSITLB,1,0,ATL::CComTypeInfoHolder>'}
0x1801bd204  mov     [rbx], rax
0x1801bd207  lea     rax, ??_7?$CComContainedNoOuterQI@VCExtCll@@@@6B?$ISupportErrorInfoImpl@$1?_GUID_9d0876ca_02dc_453a_95d9_f2194a656442@@3U__s_GUID@@B@ATL@@@; const CComContainedNoOuterQI<CExtCll>::`vftable'{for `ATL::ISupportErrorInfoImpl<&__s_GUID const _GUID_9d0876ca_02dc_453a_95d9_f2194a656442>'}
0x1801bd20e  mov     [rbx+8], rax
0x1801bd212  lea     rax, ??_7?$CComContainedNoOuterQI@VCExtCll@@@@6B@; const CComContainedNoOuterQI<CExtCll>::`vftable'
0x1801bd219  mov     [rbx+38h], rax
0x1801bd21d  mov     [rbx+10h], rsi
0x1801bd221  lea     rbx, [rsi+9C8h]
0x1801bd228  mov     rcx, rbx; this
0x1801bd22b  call    ??0CStartPageCollection@@QEAA@XZ; CStartPageCollection::CStartPageCollection(void)
0x1801bd230  lea     rax, ??_7?$CComContainedNoOuterQI@VCStartPageCollection@@@@6B?$IDispatchImpl@UIStartAddresses4@@$1?_GUID_3155ef53_8bdd_484b_86a1_b82b77e803ab@@3U__s_GUID@@B$1?LIBID_MSSITLB@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const CComContainedNoOuterQI<CStartPageCollection>::`vftable'{for `ATL::IDispatchImpl<IStartAddresses4,&__s_GUID const _GUID_3155ef53_8bdd_484b_86a1_b82b77e803ab,&_GUID const LIBID_MSSITLB,1,0,ATL::CComTypeInfoHolder>'}
0x1801bd237  mov     [rbx], rax
0x1801bd23a  lea     rax, ??_7?$CComContainedNoOuterQI@VCStartPageCollection@@@@6B?$ISupportErrorInfoImpl@$1?_GUID_3155ef53_8bdd_484b_86a1_b82b77e803ab@@3U__s_GUID@@B@ATL@@@; const CComContainedNoOuterQI<CStartPageCollection>::`vftable'{for `ATL::ISupportErrorInfoImpl<&__s_GUID const _GUID_3155ef53_8bdd_484b_86a1_b82b77e803ab>'}
0x1801bd241  mov     [rbx+8], rax
0x1801bd245  lea     rax, ??_7?$CComContainedNoOuterQI@VCStartPageCollection@@@@6B@; const CComContainedNoOuterQI<CStartPageCollection>::`vftable'
0x1801bd24c  mov     [rbx+38h], rax
0x1801bd250  mov     [rbx+10h], rsi
0x1801bd254  lea     rbx, [rsi+0B70h]
0x1801bd25b  mov     rcx, rbx; this
0x1801bd25e  call    ??0CUMapCll@@QEAA@XZ; CUMapCll::CUMapCll(void)
0x1801bd263  lea     rax, ??_7?$CComContainedNoOuterQI@VCUMapCll@@@@6B?$IDispatchImpl@UIMappings@@$1?_GUID_b05651d3_9b10_425e_b616_1fcd828db3b1@@3U__s_GUID@@B$1?LIBID_MSSITLB@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const CComContainedNoOuterQI<CUMapCll>::`vftable'{for `ATL::IDispatchImpl<IMappings,&__s_GUID const _GUID_b05651d3_9b10_425e_b616_1fcd828db3b1,&_GUID const LIBID_MSSITLB,1,0,ATL::CComTypeInfoHolder>'}
0x1801bd26a  mov     [rbx], rax
0x1801bd26d  lea     rax, ??_7?$CComContainedNoOuterQI@VCUMapCll@@@@6B?$ISupportErrorInfoImpl@$1?_GUID_b05651d3_9b10_425e_b616_1fcd828db3b1@@3U__s_GUID@@B@ATL@@@; const CComContainedNoOuterQI<CUMapCll>::`vftable'{for `ATL::ISupportErrorInfoImpl<&__s_GUID const _GUID_b05651d3_9b10_425e_b616_1fcd828db3b1>'}
0x1801bd274  mov     [rbx+8], rax
0x1801bd278  lea     rax, ??_7?$CComContainedNoOuterQI@VCUMapCll@@@@6B@; const CComContainedNoOuterQI<CUMapCll>::`vftable'
0x1801bd27f  mov     [rbx+38h], rax
0x1801bd283  mov     [rbx+10h], rsi
0x1801bd287  lea     rbx, [rsi+0CA0h]
0x1801bd28e  mov     rcx, rbx; this
0x1801bd291  call    ??0CProtocolCollection@@QEAA@XZ; CProtocolCollection::CProtocolCollection(void)
0x1801bd296  lea     rax, ??_7?$CComContainedNoOuterQI@VCProtocolCollection@@@@6B?$IDispatchImpl@UIProtocols@@$1?_GUID_b05651d5_9b10_425e_b616_1fcd828db3b1@@3U__s_GUID@@B$1?LIBID_MSSITLB@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const CComContainedNoOuterQI<CProtocolCollection>::`vftable'{for `ATL::IDispatchImpl<IProtocols,&__s_GUID const _GUID_b05651d5_9b10_425e_b616_1fcd828db3b1,&_GUID const LIBID_MSSITLB,1,0,ATL::CComTypeInfoHolder>'}
0x1801bd29d  mov     [rbx], rax
0x1801bd2a0  lea     rax, ??_7?$CComContainedNoOuterQI@VCProtocolCollection@@@@6B?$ISupportErrorInfoImpl@$1?_GUID_b05651d5_9b10_425e_b616_1fcd828db3b1@@3U__s_GUID@@B@ATL@@@; const CComContainedNoOuterQI<CProtocolCollection>::`vftable'{for `ATL::ISupportErrorInfoImpl<&__s_GUID const _GUID_b05651d5_9b10_425e_b616_1fcd828db3b1>'}
0x1801bd2a7  mov     [rbx+8], rax
0x1801bd2ab  lea     rax, ??_7?$CComContainedNoOuterQI@VCProtocolCollection@@@@6B@; const CComContainedNoOuterQI<CProtocolCollection>::`vftable'
0x1801bd2b2  mov     [rbx+38h], rax
0x1801bd2b6  mov     [rbx+10h], rsi
0x1801bd2ba  mov     [rsi+0DE8h], rdi
0x1801bd2c1  mov     [rsi+0DF0h], rdi
0x1801bd2c8  mov     [rsi+0DF8h], edi
0x1801bd2ce  lea     rdi, [rsi+0E00h]
0x1801bd2d5  xor     edx, edx
0x1801bd2d7  mov     [rdi], rdx
0x1801bd2da  mov     [rsi+0E08h], edx
0x1801bd2e0  mov     [rsi+0E10h], rdx
0x1801bd2e7  lea     rcx, [rsi+0E30h]
0x1801bd2ee  mov     [rsi+0E20h], rcx
0x1801bd2f5  mov     qword ptr [rsi+0E28h], 0C1h
0x1801bd300  mov     [rcx], dx
0x1801bd303  lea     r14, ??_7?$TLMString@$0MA@$0EA@$0HPPP@@@6B@; const TLMString<192,64,32767>::`vftable'
0x1801bd30a  mov     [rsi+0E18h], r14
0x1801bd311  lea     rcx, [rsi+0FB8h]; lpCriticalSection
0x1801bd318  mov     [rcx+28h], dl
0x1801bd31b  call    cs:__imp_InitializeCriticalSection
0x1801bd321  nop
0x1801bd322  lea     rbx, [rsi+0FE8h]
0x1801bd329  mov     rcx, rbx
0x1801bd32c  call    ??0?$CTPtrHashTable@V?$TLMString@$0MA@$0EA@$0HPPP@@@@@QEAA@P6AKPEBV?$TLMString@$0MA@$0EA@$0HPPP@@@@ZK@Z; CTPtrHashTable<TLMString<192,64,32767>>::CTPtrHashTable<TLMString<192,64,32767>>(ulong (*)(TLMString<192,64,32767> const *),ulong)
0x1801bd331  lea     rax, ??_7?$CTPtrHTblContainer@V?$TLMString@$0MA@$0EA@$0HPPP@@@@@6B@; const CTPtrHTblContainer<TLMString<192,64,32767>>::`vftable'
0x1801bd338  mov     [rbx], rax
0x1801bd33b  xor     ebx, ebx
0x1801bd33d  mov     [rsi+1020h], rbx
0x1801bd344  mov     [rsi+1028h], rbx
0x1801bd34b  mov     [rsi+1030h], rbx
0x1801bd352  mov     [rsi+1038h], rbx
0x1801bd359  mov     [rsi+1040h], ebx
0x1801bd35f  call    cs:__imp_GetTickCount
0x1801bd365  mov     [rsi+1044h], eax
0x1801bd36b  mov     [rsi+1048h], rbx
0x1801bd372  lea     rcx, [rsi+1070h]; lpCriticalSection
0x1801bd379  mov     [rcx+28h], bl
0x1801bd37c  call    cs:__imp_InitializeCriticalSection
0x1801bd382  nop
0x1801bd383  lea     rcx, [rsi+10A0h]
0x1801bd38a  lea     rax, ??_7?$CTComObjHMap@V?$TLMString@$0CA@$0CA@$0EAA@@@VCVariantObject@@VCLMSubStr@@@@6B@; const CTComObjHMap<TLMString<32,32,1024>,CVariantObject,CLMSubStr>::`vftable'
0x1801bd391  mov     [rcx], rax
0x1801bd394  mov     [rcx+8], r13
0x1801bd398  mov     [rcx+10h], r13
0x1801bd39c  mov     dword ptr [rcx+20h], 11h
  ... truncated ...
```
