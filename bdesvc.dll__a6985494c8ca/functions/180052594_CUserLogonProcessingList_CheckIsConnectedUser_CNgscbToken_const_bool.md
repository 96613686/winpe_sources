# CUserLogonProcessingList::CheckIsConnectedUser(CNgscbToken const &,bool *)

- ea: `0x180052594`
- end: `0x180052806`
- name: `?CheckIsConnectedUser@CUserLogonProcessingList@@IEBAJAEBVCNgscbToken@@PEA_N@Z`
- size: `626`
- prototype: `__int64 __fastcall(CUserLogonProcessingList *__hidden this, const struct CNgscbToken *, bool *)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021048`
- `0x18005280c`
- `0x180055c18`

## callees

- `0x180009f60`
- `0x18001d09c`
- `0x180020430`
- `0x180021d18`
- `0x180026190`
- `0x18002b6ac`
- `0x180034070`
- `0x180052594`
- `0x180054e28`
- `0x180058dac`
- `0x18007e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180052668`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180052668`

## string_xrefs

- `0x180052615`: `ImpersonateUser`
- `0x1800526a7`: `CoCreateInstance`

## pseudocode

```c
__int64 __fastcall CUserLogonProcessingList::CheckIsConnectedUser(
        CUserLogonProcessingList *this,
        const struct CNgscbToken *a2,
        bool *a3)
{
  HRESULT v5; // ebx
  const char *v6; // rax
  __int64 v7; // rdx
  unsigned __int64 v8; // r9
  bool v9; // di
  int DomainInfo; // esi
  bool v11; // cl
  const char *v13; // [rsp+28h] [rbp-28h]
  bool v14; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v15[3]; // [rsp+31h] [rbp-1Fh] BYREF
  int v16; // [rsp+34h] [rbp-1Ch] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  v16 = 0;
  ppv = 0;
  v15[0] = 0;
  v14 = 0;
  v5 = CScopedImpersonation::ImpersonateUser((CScopedImpersonation *)v15, a2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      262,
      &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids,
      (unsigned int)v5);
  if ( v5 < 0 )
  {
    v6 = "ImpersonateUser";
    v7 = 3715;
LABEL_6:
    v8 = (unsigned int)v5;
LABEL_7:
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)v7,
      (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
      (const char *)v8,
      (int)v6,
      v13);
    goto LABEL_38;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  v9 = 1;
  v5 = CoCreateInstance(
         &GUID_30d49246_d217_465f_b00b_ac9ddd652eb7,
         0,
         1u,
         &GUID_7c0c01e3_b1d3_4823_8441_c39e08bf02fa,
         &ppv);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      263,
      &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids,
      (unsigned int)v5);
  if ( v5 < 0 )
  {
    v6 = "CoCreateInstance";
    v7 = 3724;
    goto LABEL_6;
  }
  v5 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 48LL))(ppv, &v16);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      264,
      &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids,
      (unsigned int)v5);
  if ( v5 < 0 )
  {
    v6 = "GetUserConnectType";
    v7 = 3726;
    goto LABEL_6;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_DeviceEncryption_AssociatedMSA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BitLocker_DeviceEncryption_AssociatedMSA>::GetImpl'::`2'::impl) )
  {
    DomainInfo = FveDomain::GetDomainInfo(&v14, 0);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        265,
        &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids,
        (unsigned int)DomainInfo);
    if ( DomainInfo < 0 )
    {
      v6 = "CheckIsMachineDomainJoined";
      v8 = (unsigned int)DomainInfo;
      v7 = 3740;
      goto LABEL_7;
    }
    if ( !(unsigned __int8)udk::CopilotPlusDetection::IsCopilotPlusCapablePC() || v14 )
      v11 = v16 == 2 || v16 == 1 && *((_BYTE *)this + 136);
    else
      v11 = (unsigned int)(v16 - 1) <= 1;
    *a3 = v11;
  }
  else
  {
    if ( v16 != 2 && (v16 != 1 || !*((_BYTE *)this + 136)) )
      v9 = 0;
    *a3 = v9;
  }
LABEL_38:
  CScopedImpersonation::Revert((CScopedImpersonation *)v15);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180052594  mov     [rsp-28h+arg_0], rbx
0x180052599  push    rbp
0x18005259a  push    rsi
0x18005259b  push    rdi
0x18005259c  push    r14
0x18005259e  push    r15
0x1800525a0  mov     rbp, rsp
0x1800525a3  sub     rsp, 50h
0x1800525a7  mov     rax, cs:__security_cookie
0x1800525ae  xor     rax, rsp
0x1800525b1  mov     [rbp+var_10], rax
0x1800525b5  mov     r15, r8
0x1800525b8  mov     r14, rcx
0x1800525bb  mov     [rbp+var_1C], 0
0x1800525c2  mov     [rbp+var_18], 0
0x1800525ca  mov     [rbp+var_1F], 0
0x1800525ce  mov     [rbp+var_20], 0
0x1800525d2  lea     rcx, [rbp+var_1F]; this
0x1800525d6  call    ?ImpersonateUser@CScopedImpersonation@@QEAAJAEBVCNgscbToken@@@Z; CScopedImpersonation::ImpersonateUser(CNgscbToken const &)
0x1800525db  mov     ebx, eax
0x1800525dd  lea     rax, WPP_GLOBAL_Control
0x1800525e4  lea     rsi, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x1800525eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800525f2  cmp     rcx, rax
0x1800525f5  jz      short loc_180052611
0x1800525f7  test    byte ptr [rcx+1Ch], 40h
0x1800525fb  jz      short loc_180052611
0x1800525fd  mov     edx, 106h
0x180052602  mov     r9d, ebx
0x180052605  mov     r8, rsi
0x180052608  mov     rcx, [rcx+10h]
0x18005260c  call    WPP_SF_d
0x180052611  test    ebx, ebx
0x180052613  jns     short loc_18005263E
0x180052615  lea     rax, aImpersonateuse; "ImpersonateUser"
0x18005261c  mov     edx, 0E83h; void *
0x180052621  mov     r9d, ebx; char *
0x180052624  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\bdesvc\\svc\\"...
0x18005262b  mov     [rsp+50h+ppv], rax; int
0x180052630  mov     rcx, [rbp+28h]; this
0x180052634  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180052639  jmp     loc_1800527D0
0x18005263e  lea     rcx, [rbp+var_18]
0x180052642  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180052647  lea     rax, [rbp+var_18]
0x18005264b  mov     [rsp+50h+ppv], rax; ppv
0x180052650  lea     r9, _GUID_7c0c01e3_b1d3_4823_8441_c39e08bf02fa; riid
0x180052657  mov     edi, 1
0x18005265c  mov     r8d, edi; dwClsContext
0x18005265f  xor     edx, edx; pUnkOuter
0x180052661  lea     rcx, _GUID_30d49246_d217_465f_b00b_ac9ddd652eb7; rclsid
0x180052668  call    cs:__imp_CoCreateInstance
0x18005266f  nop     dword ptr [rax+rax+00h]
0x180052674  mov     ebx, eax
0x180052676  mov     rcx, cs:WPP_GLOBAL_Control
0x18005267d  lea     rax, WPP_GLOBAL_Control
0x180052684  cmp     rcx, rax
0x180052687  jz      short loc_1800526A3
0x180052689  test    byte ptr [rcx+1Ch], 40h
0x18005268d  jz      short loc_1800526A3
0x18005268f  mov     edx, 107h
0x180052694  mov     r9d, ebx
0x180052697  mov     r8, rsi
0x18005269a  mov     rcx, [rcx+10h]
0x18005269e  call    WPP_SF_d
0x1800526a3  test    ebx, ebx
0x1800526a5  jns     short loc_1800526B8
0x1800526a7  lea     rax, aCocreateinstan; "CoCreateInstance"
0x1800526ae  mov     edx, 0E8Ch
0x1800526b3  jmp     loc_180052621
0x1800526b8  mov     rcx, [rbp+var_18]
0x1800526bc  mov     rax, [rcx]
0x1800526bf  lea     rdx, [rbp+var_1C]
0x1800526c3  mov     rax, [rax+30h]
0x1800526c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800526cc  mov     ebx, eax
0x1800526ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800526d5  lea     rax, WPP_GLOBAL_Control
0x1800526dc  cmp     rcx, rax
0x1800526df  jz      short loc_1800526FB
0x1800526e1  test    byte ptr [rcx+1Ch], 40h
0x1800526e5  jz      short loc_1800526FB
0x1800526e7  mov     edx, 108h
0x1800526ec  mov     r9d, ebx
0x1800526ef  mov     r8, rsi
0x1800526f2  mov     rcx, [rcx+10h]
0x1800526f6  call    WPP_SF_d
0x1800526fb  test    ebx, ebx
0x1800526fd  jns     short loc_180052710
0x1800526ff  lea     rax, aGetuserconnect; "GetUserConnectType"
0x180052706  mov     edx, 0E8Eh
0x18005270b  jmp     loc_180052621
0x180052710  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BitLocker_DeviceEncryption_AssociatedMSA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BitLocker_DeviceEncryption_AssociatedMSA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_DeviceEncryption_AssociatedMSA> `wil::Feature<__WilFeatureTraits_Feature_BitLocker_DeviceEncryption_AssociatedMSA>::GetImpl(void)'::`2'::impl
0x180052717  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BitLocker_DeviceEncryption_AssociatedMSA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_DeviceEncryption_AssociatedMSA>::__private_IsEnabled(void)
0x18005271c  test    al, al
0x18005271e  jz      loc_1800527B5
0x180052724  xor     edx, edx; struct _GUID *
0x180052726  lea     rcx, [rbp+var_20]; bool *
0x18005272a  call    ?GetDomainInfo@FveDomain@@SAJPEA_NPEAU_GUID@@@Z; FveDomain::GetDomainInfo(bool *,_GUID *)
0x18005272f  mov     esi, eax
0x180052731  mov     rcx, cs:WPP_GLOBAL_Control
0x180052738  lea     rax, WPP_GLOBAL_Control
0x18005273f  cmp     rcx, rax
0x180052742  jz      short loc_180052762
0x180052744  test    byte ptr [rcx+1Ch], 40h
0x180052748  jz      short loc_180052762
0x18005274a  mov     edx, 109h
0x18005274f  mov     r9d, esi
0x180052752  lea     r8, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x180052759  mov     rcx, [rcx+10h]
0x18005275d  call    WPP_SF_d
0x180052762  test    esi, esi
0x180052764  jns     short loc_18005277A
0x180052766  lea     rax, aCheckismachine; "CheckIsMachineDomainJoined"
0x18005276d  mov     r9d, esi
0x180052770  mov     edx, 0E9Ch
0x180052775  jmp     loc_180052624
0x18005277a  call    ?IsCopilotPlusCapablePC@CopilotPlusDetection@udk@@YA_NW4HardwareRequirementOption@Profile@System@WindowsUdk@winrt@@@Z; udk::CopilotPlusDetection::IsCopilotPlusCapablePC(winrt::WindowsUdk::System::Profile::HardwareRequirementOption)
0x18005277f  test    al, al
0x180052781  jz      short loc_180052795
0x180052783  cmp     [rbp+var_20], 0
0x180052787  jnz     short loc_180052795
0x180052789  mov     eax, [rbp+var_1C]
0x18005278c  dec     eax
0x18005278e  cmp     eax, edi
0x180052790  setbe   cl
0x180052793  jmp     short loc_1800527B0
0x180052795  cmp     [rbp+var_1C], 2
0x180052799  jz      short loc_1800527AE
0x18005279b  cmp     [rbp+var_1C], edi
0x18005279e  jnz     short loc_1800527AA
0x1800527a0  cmp     byte ptr [r14+88h], 0
0x1800527a8  jnz     short loc_1800527AE
0x1800527aa  xor     ecx, ecx
0x1800527ac  jmp     short loc_1800527B0
0x1800527ae  mov     ecx, edi
0x1800527b0  mov     [r15], cl
0x1800527b3  jmp     short loc_1800527D0
0x1800527b5  cmp     [rbp+var_1C], 2
0x1800527b9  jz      short loc_1800527CD
0x1800527bb  cmp     [rbp+var_1C], edi
0x1800527be  jnz     short loc_1800527CA
0x1800527c0  cmp     byte ptr [r14+88h], 0
0x1800527c8  jnz     short loc_1800527CD
0x1800527ca  xor     dil, dil
0x1800527cd  mov     [r15], dil
0x1800527d0  lea     rcx, [rbp+var_1F]; this
0x1800527d4  call    ?Revert@CScopedImpersonation@@QEAAJXZ; CScopedImpersonation::Revert(void)
0x1800527d9  nop
0x1800527da  lea     rcx, [rbp+var_18]
0x1800527de  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800527e3  mov     eax, ebx
0x1800527e5  mov     rcx, [rbp+var_10]
0x1800527e9  xor     rcx, rsp; StackCookie
0x1800527ec  call    __security_check_cookie
0x1800527f1  mov     rbx, [rsp+50h+arg_0]
0x1800527f9  add     rsp, 50h
0x1800527fd  pop     r15
0x1800527ff  pop     r14
0x180052801  pop     rdi
0x180052802  pop     rsi
0x180052803  pop     rbp
0x180052804  retn
```
