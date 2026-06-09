# CServiceModule::OnSystemTextInputProcessRequest(CPenSession *)

- ea: `0x18000f0fc`
- end: `0x18000f252`
- name: `?OnSystemTextInputProcessRequest@CServiceModule@@QEAAXPEAVCPenSession@@@Z`
- size: `342`
- prototype: `void __fastcall(const struct CPenProcessInfo **this, struct CPenSession *)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x18000ed70`
- `0x18001506c`

## callees

- `0x1800010f8`
- `0x18000f0fc`
- `0x180010fc0`
- `0x1800110e0`
- `0x180015630`
- `0x18002718c`
- `0x1800285c8`
- `0x18002b3a8`
- `0x18002b404`

## string_xrefs

- `0x18000f159`: `PENSERVICE_CServiceModule::OnSystemTextInputProcessRequest`
- `0x18000f22e`: `PENSERVICE_CServiceModule::OnSystemTextInputProcessRequest`

## pseudocode

```c
void __fastcall CServiceModule::OnSystemTextInputProcessRequest(
        const struct CPenProcessInfo **this,
        struct CPenSession *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r8
  unsigned int v7; // r9d
  char IsEnabled; // al
  CServiceModule *v9; // rcx
  const struct CPenProcessInfo *v10; // rdx
  bool v11; // zf
  int v12; // eax
  const struct CPenProcessInfo *v13; // rdx
  __int128 v14; // [rsp+30h] [rbp-30h] BYREF
  __int64 v15; // [rsp+40h] [rbp-20h]
  _QWORD v16[3]; // [rsp+48h] [rbp-18h] BYREF

  if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v4,
      (int)word_18003A262);
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_sd(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      112,
      (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      (unsigned int)"PENSERVICE_CServiceModule::OnSystemTextInputProcessRequest",
      *((_DWORD *)a2 + 1));
  CServiceModule::UpdateHardwarePresenceStatus((CServiceModule *)this);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(
                (wil::details *)`wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl'::`2'::impl,
                v5,
                v6,
                v7);
  if ( (*((_BYTE *)this + 64) || IsEnabled && *((_BYTE *)this + 65) || *((_BYTE *)a2 + 8))
    && !CServiceModule::_IsRailSession(v9, *((_DWORD *)a2 + 1)) )
  {
    v10 = this[72];
    v15 = 1;
    v14 = 0;
    v11 = *((_DWORD *)v10 + 3) == 0;
    v12 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 4));
    LODWORD(v14) = 1;
    DWORD2(v14) = 1;
    if ( v11 )
      v12 = 1;
    DWORD1(v14) = v12;
    CServiceModule::StartPenProcessAsSystem((CServiceModule *)this, v10, a2, (const struct CPenProcessStartInfo *)&v14);
  }
  v13 = this[74];
  v16[0] = 1;
  v16[1] = 1;
  v16[2] = 1;
  CServiceModule::StartPenProcessAsSystem((CServiceModule *)this, v13, a2, (const struct CPenProcessStartInfo *)v16);
  *((_BYTE *)a2 + 9) = 1;
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      113,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::OnSystemTextInputProcessRequest");
}

```

## disassembly

```asm
0x18000f0fc  push    rbp
0x18000f0fe  push    rbx
0x18000f0ff  push    rdi
0x18000f100  push    r14
0x18000f102  push    r15
0x18000f104  mov     rbp, rsp
0x18000f107  sub     rsp, 60h
0x18000f10b  mov     eax, cs:dword_1800411A8
0x18000f111  mov     rbx, rdx
0x18000f114  mov     rdi, rcx
0x18000f117  cmp     eax, 5
0x18000f11a  jbe     short loc_18000F13D
0x18000f11c  mov     edx, 4000000h
0x18000f121  lea     rcx, dword_1800411A8
0x18000f128  call    _tlgKeywordOn
0x18000f12d  test    al, al
0x18000f12f  jz      short loc_18000F13D
0x18000f131  lea     rdx, word_18003A262
0x18000f138  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18000f13d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f144  lea     r15, WPP_GLOBAL_Control
0x18000f14b  cmp     rcx, r15
0x18000f14e  jz      short loc_18000F179
0x18000f150  test    byte ptr [rcx+1Ch], 10h
0x18000f154  jz      short loc_18000F179
0x18000f156  mov     eax, [rbx+4]
0x18000f159  lea     r9, aPenserviceCser_8; "PENSERVICE_CServiceModule::OnSystemText"...
0x18000f160  mov     rcx, [rcx+10h]
0x18000f164  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18000f16b  mov     edx, 70h ; 'p'
0x18000f170  mov     [rsp+60h+var_40], eax
0x18000f174  call    WPP_SF_sd
0x18000f179  mov     rcx, rdi; this
0x18000f17c  call    ?UpdateHardwarePresenceStatus@CServiceModule@@QEAAXXZ; CServiceModule::UpdateHardwarePresenceStatus(void)
0x18000f181  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController> `wil::Feature<__WilFeatureTraits_Feature_TabsvcMonitorsController>::GetImpl(void)'::`2'::impl
0x18000f188  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TabsvcMonitorsController@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TabsvcMonitorsController>::__private_IsEnabled(void)
0x18000f18d  cmp     byte ptr [rdi+40h], 0
0x18000f191  mov     r14d, 1
0x18000f197  jnz     short loc_18000F1A9
0x18000f199  test    al, al
0x18000f19b  jz      short loc_18000F1A3
0x18000f19d  cmp     byte ptr [rdi+41h], 0
0x18000f1a1  jnz     short loc_18000F1A9
0x18000f1a3  cmp     byte ptr [rbx+8], 0
0x18000f1a7  jz      short loc_18000F1F2
0x18000f1a9  mov     edx, [rbx+4]; unsigned int
0x18000f1ac  call    ?_IsRailSession@CServiceModule@@AEAA_NK@Z; CServiceModule::_IsRailSession(ulong)
0x18000f1b1  test    al, al
0x18000f1b3  jnz     short loc_18000F1F2
0x18000f1b5  mov     rdx, [rdi+240h]; struct CPenProcessInfo *
0x18000f1bc  lea     r9, [rbp+var_30]; struct CPenProcessStartInfo *
0x18000f1c0  xorps   xmm0, xmm0
0x18000f1c3  mov     [rbp+var_20], r14
0x18000f1c7  movups  [rbp+var_30], xmm0
0x18000f1cb  mov     r8, rbx; struct CPenSession *
0x18000f1ce  mov     rcx, rdi; this
0x18000f1d1  psrldq  xmm0, 4
0x18000f1d6  cmp     dword ptr [rdx+0Ch], 0
0x18000f1da  movd    eax, xmm0
0x18000f1de  mov     dword ptr [rbp+var_30], r14d
0x18000f1e2  mov     dword ptr [rbp+var_30+8], r14d
0x18000f1e6  cmovz   eax, r14d
0x18000f1ea  mov     dword ptr [rbp+var_30+4], eax
0x18000f1ed  call    ?StartPenProcessAsSystem@CServiceModule@@QEAAXPEBVCPenProcessInfo@@PEAVCPenSession@@PEBUCPenProcessStartInfo@@@Z; CServiceModule::StartPenProcessAsSystem(CPenProcessInfo const *,CPenSession *,CPenProcessStartInfo const *)
0x18000f1f2  mov     rdx, [rdi+250h]; struct CPenProcessInfo *
0x18000f1f9  lea     r9, [rbp+var_18]; struct CPenProcessStartInfo *
0x18000f1fd  mov     r8, rbx; struct CPenSession *
0x18000f200  mov     [rbp+var_18], r14
0x18000f204  mov     rcx, rdi; this
0x18000f207  mov     [rbp+var_10], r14
0x18000f20b  mov     [rbp+var_8], r14
0x18000f20f  call    ?StartPenProcessAsSystem@CServiceModule@@QEAAXPEBVCPenProcessInfo@@PEAVCPenSession@@PEBUCPenProcessStartInfo@@@Z; CServiceModule::StartPenProcessAsSystem(CPenProcessInfo const *,CPenSession *,CPenProcessStartInfo const *)
0x18000f214  mov     [rbx+9], r14b
0x18000f218  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f21f  cmp     rcx, r15
0x18000f222  jz      short loc_18000F246
0x18000f224  test    byte ptr [rcx+1Ch], 10h
0x18000f228  jz      short loc_18000F246
0x18000f22a  mov     rcx, [rcx+10h]
0x18000f22e  lea     r9, aPenserviceCser_8; "PENSERVICE_CServiceModule::OnSystemText"...
0x18000f235  mov     edx, 71h ; 'q'
0x18000f23a  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18000f241  call    WPP_SF_s
0x18000f246  add     rsp, 60h
0x18000f24a  pop     r15
0x18000f24c  pop     r14
0x18000f24e  pop     rdi
0x18000f24f  pop     rbx
0x18000f250  pop     rbp
0x18000f251  retn
```
