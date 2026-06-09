# StartTrustlet(void)

- ea: `0x180023a88`
- end: `0x180023bef`
- name: `?StartTrustlet@@YAJXZ`
- size: `359`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180022b70`
- `0x180023e64`
- `0x180033f24`

## callees

- `0x180023278`
- `0x180023a88`
- `0x180023bf8`
- `0x180023c8c`
- `0x180023da4`
- `0x180029980`
- `0x18002a0a0`
- `0x18002c640`
- `0x180039298`
- `0x18003b114`
- `0x18003be9c`
- `0x180055e5c`
- `0x18005a124`
- `0x18007753c`

## import_xrefs

- `NgcIsoCtnr!NgcIsoCtnrInitialize` at `0x180023ba1`
- `NgcIsoCtnr!NgcIsoCtnrInitialize` at `0x180023ba1`

## string_xrefs

- `0x180023af9`: `onecore\ds\security\ngc\ctnrsvc\service\service.cpp`
- `0x180023b93`: `onecore\ds\security\ngc\ctnrsvc\service\service.cpp`
- `0x180023b72`: `onecore\ds\security\trustlet\utils\vtl0\lib\trustletcontrol.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 StartTrustlet(void)
{
  bool *v1; // rdx
  int IsVsmAvailable; // eax
  NgcUtils *v3; // rcx
  NgcUtils *v4; // rcx
  __int64 v5; // rdx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // r9
  __int64 v9; // rdx
  int v10; // eax
  int v11[4]; // [rsp+20h] [rbp-178h] BYREF
  _QWORD v12[42]; // [rsp+30h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  if ( (char *)ProcessHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    return 0;
  wil::ActivityBase<NgcCtnrSvcLogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NgcCtnrSvcLogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v12);
  v12[0] = &NgcCtnrSvcLogProvider::StartTrustlet::`vftable';
  NgcCtnrSvcLogProvider::StartTrustlet::StartActivity((NgcCtnrSvcLogProvider::StartTrustlet *)v12);
  LOBYTE(v11[0]) = 0;
  IsVsmAvailable = VsmUtils::IsVsmAvailable((VsmUtils *)v11, v1);
  v3 = retaddr;
  if ( IsVsmAvailable < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x56C,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\service.cpp",
      (const char *)(unsigned int)IsVsmAvailable,
      v11[0]);
  if ( LOBYTE(v11[0]) && (NgcUtils::IsSecureBioEnabled(v3) || NgcUtils::IsNgcInVsmEnabled(v4)) )
  {
    v5 = 1;
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v3);
    v5 = 0;
  }
  v6 = VsmUtils::TrustletProcess::Start((VsmUtils::TrustletProcess *)&g_trustlet, (bool *)v5);
  v7 = v6;
  if ( v6 >= 0 )
  {
    if ( (unsigned __int8)_wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NKH_Z(
                            &qword_1800C0CD8,
                            10000) )
    {
      v10 = NgcIsoCtnrInitialize();
      v7 = v10;
      if ( v10 >= 0 )
      {
        wil::ActivityBase<NgcCtnrSvcLogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v12);
        v7 = 0;
        goto LABEL_18;
      }
      v8 = (unsigned int)v10;
      v9 = 1403;
    }
    else
    {
      v7 = -2147023436;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB1,
        (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl0\\lib\\trustletcontrol.cpp",
        (const char *)0x800705B4LL,
        v11[0]);
      v8 = 2147943860LL;
      v9 = 1402;
    }
  }
  else
  {
    v8 = (unsigned int)v6;
    v9 = 1400;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\service\\service.cpp",
    (const char *)v8,
    v11[0]);
LABEL_18:
  NgcCtnrSvcLogProvider::StartTrustlet::~StartTrustlet((NgcCtnrSvcLogProvider::StartTrustlet *)v12);
  return v7;
}

```

## disassembly

```asm
0x180023a88  push    rbx
0x180023a8a  sub     rsp, 190h
0x180023a91  mov     rax, cs:__security_cookie
0x180023a98  xor     rax, rsp
0x180023a9b  mov     [rsp+198h+var_18], rax
0x180023aa3  mov     rax, cs:ProcessHandle
0x180023aaa  dec     rax
0x180023aad  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180023ab1  ja      short loc_180023ABA
0x180023ab3  xor     eax, eax
0x180023ab5  jmp     loc_180023BD5
0x180023aba  lea     rcx, [rsp+198h+var_168]; struct wil::details::IFailureCallback *
0x180023abf  call    ??0?$ActivityBase@VNgcCtnrSvcLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<NgcCtnrSvcLogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NgcCtnrSvcLogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180023ac4  lea     rax, ??_7StartTrustlet@NgcCtnrSvcLogProvider@@6B@; const NgcCtnrSvcLogProvider::StartTrustlet::`vftable'
0x180023acb  mov     [rsp+198h+var_168], rax
0x180023ad0  lea     rcx, [rsp+198h+var_168]; this
0x180023ad5  call    ?StartActivity@StartTrustlet@NgcCtnrSvcLogProvider@@QEAAXXZ; NgcCtnrSvcLogProvider::StartTrustlet::StartActivity(void)
0x180023ada  nop
0x180023adb  mov     byte ptr [rsp+198h+var_178], 0; int
0x180023ae0  lea     rcx, [rsp+198h+var_178]; this
0x180023ae5  call    ?IsVsmAvailable@VsmUtils@@YAJPEA_N@Z; VsmUtils::IsVsmAvailable(bool *)
0x180023aea  mov     rcx, [rsp+198h]; this
0x180023af2  test    eax, eax
0x180023af4  jns     short loc_180023B0A
0x180023af6  mov     r9d, eax; char *
0x180023af9  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\ngc\\ctnrsvc\\se"...
0x180023b00  mov     edx, 56Ch; void *
0x180023b05  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180023b0a  cmp     byte ptr [rsp+198h+var_178], 0
0x180023b0f  jz      short loc_180023B2A
0x180023b11  call    ?IsSecureBioEnabled@NgcUtils@@YA_NXZ; NgcUtils::IsSecureBioEnabled(void)
0x180023b16  test    al, al
0x180023b18  jnz     short loc_180023B23
0x180023b1a  call    ?IsNgcInVsmEnabled@NgcUtils@@YA_NXZ; NgcUtils::IsNgcInVsmEnabled(void)
0x180023b1f  test    al, al
0x180023b21  jz      short loc_180023B2A
0x180023b23  mov     edx, 1
0x180023b28  jmp     short loc_180023B31
0x180023b2a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180023b2f  xor     edx, edx; enum TrustLevel
0x180023b31  lea     rcx, ?g_trustlet@@3VTrustletProcess@NgcIsoTrustlet@@A; this
0x180023b38  call    ?Start@TrustletProcess@VsmUtils@@UEAAJW4TrustLevel@2@@Z; VsmUtils::TrustletProcess::Start(VsmUtils::TrustLevel)
0x180023b3d  mov     ebx, eax
0x180023b3f  test    eax, eax
0x180023b41  jns     short loc_180023B4D
0x180023b43  mov     r9d, eax
0x180023b46  mov     edx, 578h
0x180023b4b  jmp     short loc_180023B8B
0x180023b4d  mov     edx, 2710h
0x180023b52  lea     rcx, qword_1800C0CD8
0x180023b59  call    ?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA_NKH@Z
0x180023b5e  test    al, al
0x180023b60  jnz     short loc_180023BA1
0x180023b62  mov     rcx, [rsp+198h]; this
0x180023b6a  mov     ebx, 800705B4h
0x180023b6f  mov     r9d, ebx; char *
0x180023b72  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\trustlet\\utils"...
0x180023b79  mov     edx, 0B1h; void *
0x180023b7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023b83  mov     r9d, ebx; char *
0x180023b86  mov     edx, 57Ah; void *
0x180023b8b  mov     rcx, [rsp+198h]; this
0x180023b93  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\ngc\\ctnrsvc\\se"...
0x180023b9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023b9f  jmp     short loc_180023BC9
0x180023ba1  call    cs:__imp_NgcIsoCtnrInitialize
0x180023ba8  nop     dword ptr [rax+rax+00h]
0x180023bad  mov     ebx, eax
0x180023baf  test    eax, eax
0x180023bb1  jns     short loc_180023BBD
0x180023bb3  mov     r9d, eax
0x180023bb6  mov     edx, 57Bh
0x180023bbb  jmp     short loc_180023B8B
0x180023bbd  lea     rcx, [rsp+198h+var_168]
0x180023bc2  call    ?Stop@?$ActivityBase@VNgcCtnrSvcLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<NgcCtnrSvcLogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180023bc7  xor     ebx, ebx
0x180023bc9  lea     rcx, [rsp+198h+var_168]; this
0x180023bce  call    ??1StartTrustlet@NgcCtnrSvcLogProvider@@QEAA@XZ; NgcCtnrSvcLogProvider::StartTrustlet::~StartTrustlet(void)
0x180023bd3  mov     eax, ebx
0x180023bd5  mov     rcx, [rsp+198h+var_18]
0x180023bdd  xor     rcx, rsp; StackCookie
0x180023be0  call    __security_check_cookie
0x180023be5  add     rsp, 190h
0x180023bec  pop     rbx
0x180023bed  retn
```
