# CServiceModule::OnSessionLogon(ulong)

- ea: `0x180023f54`
- end: `0x180024258`
- name: `?OnSessionLogon@CServiceModule@@QEAAXK@Z`
- size: `772`
- prototype: `void __fastcall(CServiceModule *Context, ULONG)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x18000fa00`

## callees

- `0x180001bd8`
- `0x180002134`
- `0x180012560`
- `0x180013950`
- `0x1800141d4`
- `0x18001506c`
- `0x180015630`
- `0x1800186a0`
- `0x1800186c0`
- `0x18001a570`
- `0x18001a610`
- `0x18001a760`
- `0x18001bbe0`
- `0x18002296c`
- `0x180023f54`
- `0x1800286b0`
- `0x180028964`
- `0x18002b3a8`
- `0x18002b404`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024006`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024006`
- `WTSAPI32!WTSQueryUserToken` at `0x180023fe7`
- `WTSAPI32!WTSQueryUserToken` at `0x180023fe7`

## string_xrefs

- `0x180023f9d`: `PENSERVICE_CServiceModule::OnSessionLogon`
- `0x1800241c0`: `PENSERVICE_CServiceModule::OnSessionLogon`
- `0x18002421e`: `PENSERVICE_CServiceModule::OnSessionLogon`
- `0x18002404a`: `Failed to get logon SID`
- `0x180024061`: `Failed to get user token`

## pseudocode

```c
void __fastcall CServiceModule::OnSessionLogon(CServiceModule *Context, ULONG a2)
{
  struct CPenSession *PenSession; // rax
  char v5; // r14
  const WCHAR *v6; // rbx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rcx
  struct CPenSession *v10; // rax
  struct CPenSession *v11; // rbx
  int v12; // [rsp+20h] [rbp-59h]
  char v13[8]; // [rsp+40h] [rbp-39h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-31h] BYREF
  void *phToken; // [rsp+50h] [rbp-29h] BYREF
  const WCHAR *v16; // [rsp+58h] [rbp-21h] BYREF
  char v17[32]; // [rsp+60h] [rbp-19h] BYREF
  HLOCAL *p_hMem; // [rsp+80h] [rbp+7h]
  __int64 v19; // [rsp+88h] [rbp+Fh]
  char *v20; // [rsp+90h] [rbp+17h]
  __int64 v21; // [rsp+98h] [rbp+1Fh]

  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      98,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::OnSessionLogon");
  PenSession = CServiceModule::GetPenSession(Context, a2);
  if ( PenSession && *((_BYTE *)PenSession + 9) )
  {
    hMem = 0;
    phToken = 0;
    if ( WTSQueryUserToken(a2, &phToken) )
    {
      hMem = 0;
      GetLogonSessionSid(phToken, (LPWSTR *)&hMem);
    }
    v5 = IsWizardOnlyAccount((const unsigned __int16 *)hMem);
    if ( v5 )
    {
      v6 = L"IsWizardOnlyAccount is true";
    }
    else if ( hMem )
    {
      v6 = &Data;
      if ( (char *)phToken - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
        v6 = L"Failed to get user token";
    }
    else
    {
      v6 = L"Failed to get logon SID";
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phToken);
  }
  else
  {
    v5 = 1;
    v6 = L"No session";
    if ( PenSession )
      v6 = L"System text input process not requested";
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch>::GetImpl'::`2'::impl) )
  {
    if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
    {
      LODWORD(phToken) = *((_DWORD *)Context + 17);
      v16 = v6;
      v13[0] = v5;
      LODWORD(hMem) = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v9,
        (int)byte_18003A875,
        v7,
        v8,
        (__int64)&hMem,
        (__int64)v13,
        &v16,
        (__int64)&phToken);
    }
    if ( *((_DWORD *)Context + 17) )
      CServiceModule::_StopOobeProcesses((struct _GUID *)Context, a2, v7, v8);
  }
  else if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
  {
    v13[0] = v5;
    LODWORD(hMem) = a2;
    v20 = v13;
    v21 = 1;
    p_hMem = &hMem;
    v19 = 4;
    tlgWriteTransfer_EtwEventWriteTransfer(
      (unsigned int)&dword_1800411A8,
      (unsigned int)byte_1800394B5,
      0,
      0,
      4,
      (__int64)v17);
  }
  if ( v5 )
  {
    v10 = CServiceModule::EnsurePenSession(Context, a2);
    v11 = v10;
    if ( v10 && *((_BYTE *)v10 + 9) )
    {
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
        WPP_SF_sd(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          99,
          (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
          (unsigned int)"PENSERVICE_CServiceModule::OnSessionLogon",
          a2);
      CServiceModule::_RemovePenProcessesWorker(Context, 1, 0x28u, a2);
      *((_BYTE *)v11 + 9) = 0;
    }
    CServiceModule::_StartPenProcessesWorker(Context, a2, 0, 0, v12, 0);
  }
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      100,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::OnSessionLogon");
}

```

## disassembly

```asm
0x180023f54  mov     [rsp-8+arg_10], rbx
0x180023f59  push    rbp
0x180023f5a  push    rsi
0x180023f5b  push    rdi
0x180023f5c  push    r13
0x180023f5e  push    r14
0x180023f60  lea     rbp, [rsp-37h]
0x180023f65  sub     rsp, 0B0h
0x180023f6c  mov     rax, cs:__security_cookie
0x180023f73  xor     rax, rsp
0x180023f76  mov     [rbp+57h+var_30], rax
0x180023f7a  mov     edi, edx
0x180023f7c  mov     rsi, rcx
0x180023f7f  lea     r13, WPP_GLOBAL_Control
0x180023f86  mov     rcx, cs:WPP_GLOBAL_Control
0x180023f8d  cmp     rcx, r13
0x180023f90  jz      short loc_180023FB4
0x180023f92  test    byte ptr [rcx+1Ch], 10h
0x180023f96  jz      short loc_180023FB4
0x180023f98  mov     edx, 62h ; 'b'
0x180023f9d  lea     r9, aPenserviceCser_11; "PENSERVICE_CServiceModule::OnSessionLog"...
0x180023fa4  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180023fab  mov     rcx, [rcx+10h]
0x180023faf  call    WPP_SF_s
0x180023fb4  mov     edx, edi; unsigned int
0x180023fb6  mov     rcx, rsi; this
0x180023fb9  call    ?GetPenSession@CServiceModule@@QEAAPEAVCPenSession@@K@Z; CServiceModule::GetPenSession(ulong)
0x180023fbe  test    rax, rax
0x180023fc1  jz      loc_180024085
0x180023fc7  cmp     byte ptr [rax+9], 0
0x180023fcb  jz      loc_180024085
0x180023fd1  mov     [rbp+57h+hMem], 0
0x180023fd9  mov     [rbp+57h+phToken], 0
0x180023fe1  lea     rdx, [rbp+57h+phToken]; phToken
0x180023fe5  mov     ecx, edi; SessionId
0x180023fe7  call    cs:__imp_WTSQueryUserToken
0x180023fed  test    eax, eax
0x180023fef  jz      short loc_18002402A
0x180023ff1  mov     rbx, [rbp+57h+hMem]
0x180023ff5  test    rbx, rbx
0x180023ff8  jz      short loc_180024015
0x180023ffa  lea     rcx, [rbp+57h+var_78]; this
0x180023ffe  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180024003  mov     rcx, rbx; hMem
0x180024006  call    cs:__imp_LocalFree
0x18002400c  lea     rcx, [rbp+57h+var_78]; this
0x180024010  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180024015  mov     [rbp+57h+hMem], 0
0x18002401d  lea     rdx, [rbp+57h+hMem]; StringSid
0x180024021  mov     rcx, [rbp+57h+phToken]; TokenHandle
0x180024025  call    ?GetLogonSessionSid@@YAJPEAXPEAPEAG@Z; GetLogonSessionSid(void *,ushort * *)
0x18002402a  mov     rcx, [rbp+57h+hMem]; unsigned __int16 *
0x18002402e  call    ?IsWizardOnlyAccount@@YA_NPEBG@Z; IsWizardOnlyAccount(ushort const *)
0x180024033  mov     r14b, al
0x180024036  test    al, al
0x180024038  jz      short loc_180024043
0x18002403a  lea     rbx, aIswizardonlyac; "IsWizardOnlyAccount is true"
0x180024041  jmp     short loc_180024070
0x180024043  cmp     [rbp+57h+hMem], 0
0x180024048  jnz     short loc_180024053
0x18002404a  lea     rbx, aFailedToGetLog; "Failed to get logon SID"
0x180024051  jmp     short loc_180024070
0x180024053  mov     rax, [rbp+57h+phToken]
0x180024057  dec     rax
0x18002405a  lea     rbx, Data
0x180024061  lea     rcx, aFailedToGetUse; "Failed to get user token"
0x180024068  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002406c  cmova   rbx, rcx
0x180024070  lea     rcx, [rbp+57h+hMem]
0x180024074  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180024079  nop
0x18002407a  lea     rcx, [rbp+57h+phToken]
0x18002407e  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180024083  jmp     short loc_18002409D
0x180024085  mov     r14b, 1
0x180024088  lea     rbx, aNoSession; "No session"
0x18002408f  lea     rcx, aSystemTextInpu; "System text input process not requested"
0x180024096  test    rax, rax
0x180024099  cmovnz  rbx, rcx
0x18002409d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch> `wil::Feature<__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch>::GetImpl(void)'::`2'::impl
0x1800240a4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch>::__private_IsEnabled(void)
0x1800240a9  test    al, al
0x1800240ab  mov     eax, cs:dword_1800411A8
0x1800240b1  jz      short loc_180024120
0x1800240b3  cmp     eax, 5
0x1800240b6  jbe     short loc_18002410E
0x1800240b8  mov     edx, 4000000h
0x1800240bd  lea     rcx, dword_1800411A8
0x1800240c4  call    _tlgKeywordOn
0x1800240c9  test    al, al
0x1800240cb  jz      short loc_18002410E
0x1800240cd  mov     eax, [rsi+44h]
0x1800240d0  mov     dword ptr [rbp+57h+phToken], eax
0x1800240d3  mov     [rbp+57h+var_78], rbx
0x1800240d7  mov     [rbp+57h+var_90], r14b
0x1800240db  mov     dword ptr [rbp+57h+hMem], edi
0x1800240de  lea     rax, [rbp+57h+phToken]
0x1800240e2  mov     [rsp+0D0h+var_98], rax
0x1800240e7  lea     rax, [rbp+57h+var_78]
0x1800240eb  mov     [rsp+0D0h+var_A0], rax
0x1800240f0  lea     rax, [rbp+57h+var_90]
0x1800240f4  mov     qword ptr [rsp+0D0h+var_A8], rax
0x1800240f9  lea     rax, [rbp+57h+hMem]
0x1800240fd  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180024102  lea     rdx, byte_18003A875
0x180024109  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18002410e  cmp     dword ptr [rsi+44h], 0
0x180024112  jz      short loc_180024188
0x180024114  mov     edx, edi; unsigned int
0x180024116  mov     rcx, rsi; this
0x180024119  call    ?_StopOobeProcesses@CServiceModule@@AEAAXK@Z; CServiceModule::_StopOobeProcesses(ulong)
0x18002411e  jmp     short loc_180024188
0x180024120  cmp     eax, 5
0x180024123  jbe     short loc_180024188
0x180024125  mov     edx, 4000000h
0x18002412a  lea     rcx, dword_1800411A8
0x180024131  call    _tlgKeywordOn
0x180024136  test    al, al
0x180024138  jz      short loc_180024188
0x18002413a  mov     [rbp+57h+var_90], r14b
0x18002413e  mov     dword ptr [rbp+57h+hMem], edi
0x180024141  lea     rax, [rbp+57h+var_90]
0x180024145  mov     [rbp+57h+var_40], rax
0x180024149  mov     [rbp+57h+var_38], 1
0x180024151  lea     rax, [rbp+57h+hMem]
0x180024155  mov     [rbp+57h+var_50], rax
0x180024159  mov     ecx, 4
0x18002415e  mov     [rbp+57h+var_48], rcx
0x180024162  lea     rax, [rbp+57h+var_70]
0x180024166  mov     qword ptr [rsp+0D0h+var_A8], rax
0x18002416b  mov     [rsp+0D0h+var_B0], ecx
0x18002416f  xor     r9d, r9d
0x180024172  xor     r8d, r8d
0x180024175  lea     rdx, byte_1800394B5
0x18002417c  lea     rcx, dword_1800411A8
0x180024183  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180024188  test    r14b, r14b
0x18002418b  jz      short loc_180024207
0x18002418d  mov     edx, edi; unsigned int
0x18002418f  mov     rcx, rsi; this
0x180024192  call    ?EnsurePenSession@CServiceModule@@QEAAPEAVCPenSession@@K@Z; CServiceModule::EnsurePenSession(ulong)
0x180024197  mov     rbx, rax
0x18002419a  test    rax, rax
0x18002419d  jz      short loc_1800241EF
0x18002419f  cmp     byte ptr [rax+9], 0
0x1800241a3  jz      short loc_1800241EF
0x1800241a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800241ac  cmp     rcx, r13
0x1800241af  jz      short loc_1800241D7
0x1800241b1  test    byte ptr [rcx+1Ch], 10h
0x1800241b5  jz      short loc_1800241D7
0x1800241b7  mov     edx, 63h ; 'c'
0x1800241bc  mov     [rsp+0D0h+var_B0], edi; int
0x1800241c0  lea     r9, aPenserviceCser_11; "PENSERVICE_CServiceModule::OnSessionLog"...
0x1800241c7  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x1800241ce  mov     rcx, [rcx+10h]
0x1800241d2  call    WPP_SF_sd
0x1800241d7  mov     r9d, edi; unsigned int
0x1800241da  mov     edx, 1; unsigned int
0x1800241df  lea     r8d, [rdx+27h]; unsigned int
0x1800241e3  mov     rcx, rsi; this
0x1800241e6  call    ?_RemovePenProcessesWorker@CServiceModule@@AEAAXKKK@Z; CServiceModule::_RemovePenProcessesWorker(ulong,ulong,ulong)
0x1800241eb  mov     byte ptr [rbx+9], 0
0x1800241ef  mov     [rsp+0D0h+var_A8], 0; int
0x1800241f7  xor     r9d, r9d; int
0x1800241fa  xor     r8d, r8d; enum _WTS_CONNECTSTATE_CLASS
0x1800241fd  mov     edx, edi; unsigned int
0x1800241ff  mov     rcx, rsi; Context
0x180024202  call    ?_StartPenProcessesWorker@CServiceModule@@AEAAXKW4_WTS_CONNECTSTATE_CLASS@@HHHH@Z; CServiceModule::_StartPenProcessesWorker(ulong,_WTS_CONNECTSTATE_CLASS,int,int,int,int)
0x180024207  mov     rcx, cs:WPP_GLOBAL_Control
0x18002420e  cmp     rcx, r13
0x180024211  jz      short loc_180024235
0x180024213  test    byte ptr [rcx+1Ch], 10h
0x180024217  jz      short loc_180024235
0x180024219  mov     edx, 64h ; 'd'
0x18002421e  lea     r9, aPenserviceCser_11; "PENSERVICE_CServiceModule::OnSessionLog"...
0x180024225  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18002422c  mov     rcx, [rcx+10h]
0x180024230  call    WPP_SF_s
0x180024235  mov     rcx, [rbp+57h+var_30]
0x180024239  xor     rcx, rsp; StackCookie
0x18002423c  call    __security_check_cookie
0x180024241  mov     rbx, [rsp+0D0h+arg_10]
0x180024249  add     rsp, 0B0h
0x180024250  pop     r14
0x180024252  pop     r13
0x180024254  pop     rdi
0x180024255  pop     rsi
0x180024256  pop     rbp
0x180024257  retn
```
