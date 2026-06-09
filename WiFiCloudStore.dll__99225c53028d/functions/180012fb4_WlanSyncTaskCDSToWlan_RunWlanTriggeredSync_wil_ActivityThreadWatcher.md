# WlanSyncTaskCDSToWlan::RunWlanTriggeredSync(wil::ActivityThreadWatcher &)

- ea: `0x180012fb4`
- end: `0x180013144`
- name: `?RunWlanTriggeredSync@WlanSyncTaskCDSToWlan@@AEAAXAEAVActivityThreadWatcher@wil@@@Z`
- size: `400`
- prototype: `void __fastcall(WlanSyncTaskCDSToWlan *__hidden this, struct wil::ActivityThreadWatcher *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180012594`

## callees

- `0x180012fb4`
- `0x18001314c`
- `0x180013a94`
- `0x180013b00`
- `0x180013bc0`
- `0x180013c40`
- `0x180013c74`
- `0x180013ef0`
- `0x180013f18`
- `0x18001402c`
- `0x180014088`
- `0x1800140a4`
- `0x18002072c`
- `0x180028748`
- `0x18002a030`
- `0x18002e2d0`
- `0x180032254`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800130e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800130e6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180012ff6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180012ff6`

## string_xrefs

- `0x18001310f`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcdstowlan.cpp`
- `0x180013132`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcdstowlan.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall WlanSyncTaskCDSToWlan::RunWlanTriggeredSync(
        WlanSyncTaskCDSToWlan *this,
        struct wil::ActivityThreadWatcher *a2)
{
  struct _TOKEN_USER *CurrentUserToken; // rax
  const char *v4; // r9
  const unsigned __int16 *v5; // rbx
  int v6; // eax
  unsigned int v7; // eax
  __int64 v8; // rcx
  int v9[2]; // [rsp+20h] [rbp-E0h] BYREF
  LPWSTR StringSid; // [rsp+28h] [rbp-D8h] BYREF
  struct _FILETIME system_time; // [rsp+30h] [rbp-D0h] BYREF
  void **v12; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v13[272]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v14[8]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v15[24]; // [rsp+160h] [rbp+60h] BYREF
  int v16; // [rsp+178h] [rbp+78h]
  wil::filetime *retaddr; // [rsp+1B8h] [rbp+B8h]

  StringSid = 0;
  CurrentUserToken = WlanSyncTaskCDSToWlan::GetCurrentUserToken(this);
  if ( !ConvertSidToStringSidW(CurrentUserToken->User.Sid, &StringSid) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x27B,
      (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
      v4);
  system_time = wil::filetime::get_system_time(retaddr);
  v5 = StringSid;
  wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)&v12);
  v12 = &WiFiCloudStoreTelemetry::WlanTriggeredSync::`vftable';
  WiFiCloudStoreTelemetry::WlanTriggeredSync::StartActivity(
    (WiFiCloudStoreTelemetry::WlanTriggeredSync *)&v12,
    v5,
    L"cds",
    &system_time);
  if ( v16 )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)v15);
  *(_QWORD *)v9 = 0;
  v6 = Microsoft::WRL::Details::MakeAndInitialize<WlanSyncTaskWlanToCDS,WlanSyncTaskWlanToCDS,>(v9);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x283,
      (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcdstowlan.cpp",
      (const char *)(unsigned int)v6,
      v9[0]);
  v7 = WlanSyncTaskWlanToCDS::DoWork((__int64)retaddr, (struct WiFiCloudStoreTelemetry::WlanTriggeredSync *)&v12, a2);
  WiFiCloudStoreTelemetry::WlanTriggeredSync::Stop(&v12, v7);
  v8 = *(_QWORD *)v9;
  if ( *(_QWORD *)v9 )
  {
    *(_QWORD *)v9 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase>::Release(v8);
  }
  v12 = &WiFiCloudStoreTelemetry::WlanTriggeredSync::`vftable';
  wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v12);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v15);
  wil::details::shared_object<wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WiFiCloudStoreTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(v14);
  wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WiFiCloudStoreTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<WiFiCloudStoreTelemetry,_TlgReflectorTag_Param0IsProviderType>(v13);
  if ( StringSid )
    LocalFree(StringSid);
}

```

## disassembly

```asm
0x180012fb4  mov     [rsp-8+arg_10], rbx
0x180012fb9  push    rbp
0x180012fba  push    rdi
0x180012fbb  push    r14
0x180012fbd  lea     rbp, [rsp-0A0h]
0x180012fc5  sub     rsp, 1A0h
0x180012fcc  mov     rax, cs:__security_cookie
0x180012fd3  xor     rax, rsp
0x180012fd6  mov     [rbp+0B0h+var_20], rax
0x180012fdd  mov     rdi, rdx
0x180012fe0  mov     [rsp+1B0h+StringSid], 0
0x180012fe9  call    ?GetCurrentUserToken@WlanSyncTaskCDSToWlan@@AEAAPEAU_TOKEN_USER@@XZ; WlanSyncTaskCDSToWlan::GetCurrentUserToken(void)
0x180012fee  lea     rdx, [rsp+1B0h+StringSid]; StringSid
0x180012ff3  mov     rcx, [rax]; Sid
0x180012ff6  call    cs:__imp_ConvertSidToStringSidW
0x180012ffc  mov     rcx, [rbp+0B8h]; this
0x180013003  test    eax, eax
0x180013005  jz      loc_18001310F
0x18001300b  call    ?get_system_time@filetime@wil@@YA?AU_FILETIME@@XZ; wil::filetime::get_system_time(void)
0x180013010  mov     qword ptr [rsp+1B0h+var_180.dwLowDateTime], rax
0x180013015  mov     rbx, [rsp+1B0h+StringSid]
0x18001301a  lea     rdx, aWlantriggereds; "WlanTriggeredSync"
0x180013021  lea     rcx, [rsp+1B0h+var_170]; struct wil::details::IFailureCallback *
0x180013026  call    ??0?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001302b  lea     r14, ??_7WlanTriggeredSync@WiFiCloudStoreTelemetry@@6B@; const WiFiCloudStoreTelemetry::WlanTriggeredSync::`vftable'
0x180013032  mov     [rsp+1B0h+var_170], r14
0x180013037  lea     r9, [rsp+1B0h+var_180]; struct _FILETIME *
0x18001303c  lea     r8, aCds; "cds"
0x180013043  mov     rdx, rbx; unsigned __int16 *
0x180013046  lea     rcx, [rsp+1B0h+var_170]; this
0x18001304b  call    ?StartActivity@WlanTriggeredSync@WiFiCloudStoreTelemetry@@QEAAXPEBG0AEBU_FILETIME@@@Z; WiFiCloudStoreTelemetry::WlanTriggeredSync::StartActivity(ushort const *,ushort const *,_FILETIME const &)
0x180013050  nop
0x180013051  cmp     [rbp+0B0h+var_38], 0
0x180013055  jnz     loc_180013121
0x18001305b  mov     qword ptr [rsp+1B0h+var_190], 0; int
0x180013064  lea     rcx, [rsp+1B0h+var_190]
0x180013069  call    ??$MakeAndInitialize@VWlanSyncTaskWlanToCDS@@V1@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VWlanSyncTaskWlanToCDS@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<WlanSyncTaskWlanToCDS,WlanSyncTaskWlanToCDS,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WlanSyncTaskWlanToCDS>>)
0x18001306e  mov     rcx, [rbp+0B8h]; this
0x180013075  test    eax, eax
0x180013077  js      loc_18001312F
0x18001307d  mov     r8, rdi
0x180013080  lea     rdx, [rsp+1B0h+var_170]
0x180013085  call    ?DoWork@WlanSyncTaskWlanToCDS@@QEBA?AW4WiFiCloudStoreTelemetryResult@@AEAVWlanTriggeredSync@WiFiCloudStoreTelemetry@@AEAVActivityThreadWatcher@wil@@@Z; WlanSyncTaskWlanToCDS::DoWork(WiFiCloudStoreTelemetry::WlanTriggeredSync &,wil::ActivityThreadWatcher &)
0x18001308a  mov     edx, eax
0x18001308c  lea     rcx, [rsp+1B0h+var_170]
0x180013091  call    ?Stop@WlanTriggeredSync@WiFiCloudStoreTelemetry@@QEAAXW4WiFiCloudStoreTelemetryResult@@@Z; WiFiCloudStoreTelemetry::WlanTriggeredSync::Stop(WiFiCloudStoreTelemetryResult)
0x180013096  nop
0x180013097  mov     rcx, qword ptr [rsp+1B0h+var_190]
0x18001309c  test    rcx, rcx
0x18001309f  jz      short loc_1800130B0
0x1800130a1  mov     qword ptr [rsp+1B0h+var_190], 0
0x1800130aa  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase>::Release(void)
0x1800130af  nop
0x1800130b0  mov     [rsp+1B0h+var_170], r14
0x1800130b5  lea     rcx, [rsp+1B0h+var_170]
0x1800130ba  call    ?Destroy@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800130bf  lea     rcx, [rbp+0B0h+var_50]; this
0x1800130c3  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800130c8  lea     rcx, [rbp+0B0h+var_58]
0x1800130cc  call    ?reset@?$shared_object@V?$ActivityData@VWiFiCloudStoreTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WiFiCloudStoreTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x1800130d1  lea     rcx, [rsp+1B0h+var_168]
0x1800130d6  call    ??1?$ActivityData@VWiFiCloudStoreTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WiFiCloudStoreTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<WiFiCloudStoreTelemetry,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800130db  nop
0x1800130dc  mov     rcx, [rsp+1B0h+StringSid]; hMem
0x1800130e1  test    rcx, rcx
0x1800130e4  jz      short loc_1800130EC
0x1800130e6  call    cs:__imp_LocalFree
0x1800130ec  mov     rcx, [rbp+0B0h+var_20]
0x1800130f3  xor     rcx, rsp; StackCookie
0x1800130f6  call    __security_check_cookie
0x1800130fb  mov     rbx, [rsp+1B0h+arg_10]
0x180013103  add     rsp, 1A0h
0x18001310a  pop     r14
0x18001310c  pop     rdi
0x18001310d  pop     rbp
0x18001310e  retn
0x18001310f  lea     r8, aOnecoreuapNetW_1; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180013116  mov     edx, 27Bh; void *
0x18001311b  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180013121  lea     rcx, [rbp+0B0h+var_50]; this
0x180013125  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18001312a  jmp     loc_18001305B
0x18001312f  mov     r9d, eax; char *
0x180013132  lea     r8, aOnecoreuapNetW_1; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180013139  mov     edx, 283h; void *
0x18001313e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
