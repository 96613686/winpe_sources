# Windows::Networking::UX::Internal::WlanInterface::s_WnfUIEventCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)

- ea: `0x1800508d0`
- end: `0x180050cc5`
- name: `?s_WnfUIEventCallback@WlanInterface@Internal@UX@Networking@Windows@@KAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z`
- size: `1013`
- prototype: `static int(struct _WNF_STATE_NAME, unsigned int, struct _WNF_TYPE_ID *, void *, const void *, unsigned int)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000de4c`
- `0x180012228`
- `0x18001b230`
- `0x18001be60`
- `0x18001d4d4`
- `0x1800240b0`
- `0x180025628`
- `0x180028b40`
- `0x18003522c`
- `0x18003a070`
- `0x180048ee4`
- `0x18004b650`
- `0x18004c0f4`
- `0x18004f788`
- `0x1800508d0`
- `0x18007a4e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050c0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050c0e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Networking::UX::Internal::WlanInterface::s_WnfUIEventCallback(
        struct _WNF_STATE_NAME a1,
        __int64 a2,
        struct _WNF_TYPE_ID *a3,
        char *a4,
        char *a5,
        unsigned int a6)
{
  unsigned int v7; // edi
  char *v8; // rsi
  __int64 v9; // rax
  __int64 v10; // rax
  PVOID *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // eax
  int v16; // eax
  struct _L2_UI_REQUEST *v17; // r8
  void *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // r10
  int v21; // eax
  const char *v22; // r9
  int v24; // [rsp+20h] [rbp-A8h]
  _QWORD v25[2]; // [rsp+30h] [rbp-98h] BYREF
  struct _GUID v26; // [rsp+40h] [rbp-88h] BYREF
  char v27; // [rsp+50h] [rbp-78h]
  char v28[104]; // [rsp+60h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  LPVOID pv; // [rsp+E8h] [rbp+20h] BYREF

  v7 = a6;
  v8 = a5;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 249, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
  try
  {
    if ( !a4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCA9,
        (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
        (const char *)0x80070057LL,
        v24);
    if ( !v8 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCAA,
        (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
        (const char *)0x80070057LL,
        v24);
    if ( !v7 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCAB,
        (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
        (const char *)0x80070057LL,
        v24);
    if ( v7 < 0x2C )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCAC,
        (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
        (const char *)0x80070057LL,
        v24);
    Windows::Networking::UX::Internal::WlanMediaManager::ImpersonateCurrentUser(*((_QWORD *)a4 + 2), v25);
    v9 = *(_QWORD *)(v8 + 20) - 0x4024CB90348C9CFFLL;
    if ( *(_QWORD *)(v8 + 20) == 0x4024CB90348C9CFFLL )
      v9 = *(_QWORD *)(v8 + 28) - 0x4B93A35972F122AELL;
    if ( v9 )
      MicrosoftTelemetryAssertTriggeredNoArgs(0x4B93A35972F122AELL);
    v10 = *(_QWORD *)(v8 + 20) - 0x4024CB90348C9CFFLL;
    if ( *(_QWORD *)(v8 + 20) == 0x4024CB90348C9CFFLL )
      v10 = *(_QWORD *)(v8 + 28) - 0x4B93A35972F122AELL;
    if ( !v10 )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v24 = *((_DWORD *)v8 + 9);
        WPP_SF__guid_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          250,
          &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids,
          v8 + 4);
        v11 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( *((_DWORD *)v8 + 9) < (unsigned int)(*((_DWORD *)v8 + 27) + 88) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xCBD,
          (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
          (const char *)0x80070057LL,
          v24);
      v12 = *((_QWORD *)v8 + 7) - *(_QWORD *)&GUID_NULL.Data1;
      if ( !v12 )
        v12 = *((_QWORD *)v8 + 8) - *(_QWORD *)GUID_NULL.Data4;
      if ( !v12 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xCBE,
          (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
          (const char *)0x80070057LL,
          v24);
      v13 = *((_QWORD *)v8 + 7) - *(_QWORD *)(a4 + 1204);
      if ( !v13 )
        v13 = *((_QWORD *)v8 + 8) - *(_QWORD *)(a4 + 1212);
      if ( !v13 )
        goto LABEL_37;
      v14 = *((_QWORD *)v8 + 7) - *(_QWORD *)(a4 + 1188);
      if ( !v14 )
        v14 = *((_QWORD *)v8 + 8) - *(_QWORD *)(a4 + 1196);
      if ( v14 )
      {
        if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 8) != 0 )
          WPP_SF_(v11[2], 251, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
      }
      else
      {
LABEL_37:
        v26 = *(struct _GUID *)(v8 + 4);
        v15 = Windows::Networking::UX::Internal::WlanInterface::_SetInitialUIRequest(
                (struct _GUID *)a4,
                (const struct _L2_UI_REQUEST *)(v8 + 40),
                &v26);
        if ( v15 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xCC3,
            (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
            (const char *)(unsigned int)v15,
            v24);
        if ( a4[34] )
        {
          pv = 0;
          *(_QWORD *)&v26.Data1 = &pv;
          *(_QWORD *)v26.Data4 = 0;
          v27 = 1;
          v16 = Windows::Networking::UX::Internal::WlanInterface::_CopyUIRequest(
                  (const struct _L2_UI_REQUEST *)(v8 + 40),
                  (struct _L2_UI_REQUEST **)v26.Data4);
          if ( v16 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xCC7,
              (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
              (const char *)(unsigned int)v16,
              v24);
          wil::details::out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&v26);
          v17 = (struct _L2_UI_REQUEST *)pv;
          pv = 0;
          Windows::Networking::UX::Internal::WlanInterface::_ProcessUIRequest(
            (Windows::Networking::UX::Internal::WlanInterface *)a4,
            (const struct _GUID *)(v8 + 4),
            v17);
          v18 = pv;
          pv = 0;
          if ( v18 )
            CoTaskMemFree(v18);
        }
        else if ( a4[32] )
        {
          if ( (unsigned __int8)std::_Atomic_storage<bool,1>::load(a4 + 33) )
          {
            v19 = std::function_void___cdecl_Windows::Networking::UX::Internal::WlanInterface___Windows::Networking::UX::Internal::WlanMediaManager____::function_void___cdecl_Windows::Networking::UX::Internal::WlanInterface___Windows::Networking::UX::Internal::WlanMediaManager______Windows::Networking::UX::Internal::WlanInterface::s_WnfUIEventCallback_::_16_::_lambda_1__0_(v28);
            v26 = *(struct _GUID *)(a4 + 1204);
            v21 = Windows::Networking::UX::Internal::WlanMediaManager::RunComTaskWithInterface(
                    v20,
                    (__int64)&v26,
                    0,
                    v19);
            if ( v21 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0xCD1,
                (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
                (const char *)(unsigned int)v21,
                v24);
          }
        }
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v25);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xCDA,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
      v22);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 252, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x1800508d0  push    rbx
0x1800508d2  push    rsi
0x1800508d3  push    rdi
0x1800508d4  push    r14
0x1800508d6  sub     rsp, 0A8h
0x1800508dd  mov     rbx, r9
0x1800508e0  mov     edi, [rsp+0C8h+arg_28]
0x1800508e7  mov     rsi, [rsp+0C8h+arg_20]
0x1800508ef  lea     r14, WPP_GLOBAL_Control
0x1800508f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800508fd  cmp     rcx, r14
0x180050900  jz      short loc_18005091E
0x180050902  test    byte ptr [rcx+1Ch], 40h
0x180050906  jz      short loc_18005091E
0x180050908  mov     edx, 0F9h
0x18005090d  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x180050914  mov     rcx, [rcx+10h]
0x180050918  call    WPP_SF_
0x18005091d  nop
0x18005091e  mov     rcx, [rsp+0C8h]; this
0x180050926  test    rbx, rbx
0x180050929  jnz     short loc_180050942
0x18005092b  mov     r9d, 80070057h; char *
0x180050931  lea     r8, aOnecoreuapNetU_20; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180050938  mov     edx, 0CA9h; void *
0x18005093d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180050942  mov     rcx, [rsp+0C8h]; this
0x18005094a  test    rsi, rsi
0x18005094d  jnz     short loc_180050966
0x18005094f  mov     r9d, 80070057h; char *
0x180050955  lea     r8, aOnecoreuapNetU_20; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18005095c  mov     edx, 0CAAh; void *
0x180050961  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180050966  mov     rcx, [rsp+0C8h]; this
0x18005096e  test    edi, edi
0x180050970  jnz     short loc_180050989
0x180050972  mov     r9d, 80070057h; char *
0x180050978  lea     r8, aOnecoreuapNetU_20; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x18005097f  mov     edx, 0CABh; void *
0x180050984  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180050989  mov     rcx, [rsp+0C8h]; this
0x180050991  cmp     edi, 2Ch ; ','
0x180050994  jnb     short loc_1800509AD
0x180050996  mov     r9d, 80070057h; char *
0x18005099c  lea     r8, aOnecoreuapNetU_20; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x1800509a3  mov     edx, 0CACh; void *
0x1800509a8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800509ad  lea     rdx, [rsp+0C8h+var_98]
0x1800509b2  mov     rcx, [rbx+10h]
0x1800509b6  call    ?ImpersonateCurrentUser@WlanMediaManager@Internal@UX@Networking@Windows@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@XZ; Windows::Networking::UX::Internal::WlanMediaManager::ImpersonateCurrentUser(void)
0x1800509bb  nop
0x1800509bc  mov     rax, [rsi+14h]
0x1800509c0  mov     rdx, cs:qword_18009F8F0
0x1800509c7  sub     rax, rdx
0x1800509ca  mov     rcx, cs:qword_18009F8F8
0x1800509d1  jnz     short loc_1800509DA
0x1800509d3  mov     rax, [rsi+1Ch]
0x1800509d7  sub     rax, rcx
0x1800509da  test    rax, rax
0x1800509dd  jz      short loc_1800509F2
0x1800509df  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800509e4  mov     rcx, cs:qword_18009F8F8
0x1800509eb  mov     rdx, cs:qword_18009F8F0
0x1800509f2  mov     rax, [rsi+14h]
0x1800509f6  sub     rax, rdx
0x1800509f9  jnz     short loc_180050A02
0x1800509fb  mov     rax, [rsi+1Ch]
0x1800509ff  sub     rax, rcx
0x180050a02  test    rax, rax
0x180050a05  jnz     loc_180050C78
0x180050a0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180050a12  cmp     rcx, r14
0x180050a15  jz      short loc_180050A57
0x180050a17  test    byte ptr [rcx+1Ch], 8
0x180050a1b  jz      short loc_180050A57
0x180050a1d  mov     r8d, [rsi+24h]
0x180050a21  cmp     r8d, 58h ; 'X'
0x180050a25  jb      short loc_180050A2C
0x180050a27  mov     eax, [rsi+6Ch]
0x180050a2a  jmp     short loc_180050A2E
0x180050a2c  xor     eax, eax
0x180050a2e  lea     r9, [rsi+4]
0x180050a32  mov     edx, 0FAh
0x180050a37  mov     [rsp+0C8h+var_A0], eax
0x180050a3b  mov     [rsp+0C8h+var_A8], r8d; int
0x180050a40  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x180050a47  mov     rcx, [rcx+10h]
0x180050a4b  call    WPP_SF__guid_dd
0x180050a50  mov     rcx, cs:WPP_GLOBAL_Control
0x180050a57  mov     r10, [rsp+0C8h]
0x180050a5f  mov     eax, [rsi+6Ch]
0x180050a62  add     eax, 58h ; 'X'
0x180050a65  cmp     [rsi+24h], eax
0x180050a68  jnb     short loc_180050A84
0x180050a6a  mov     r9d, 80070057h; char *
0x180050a70  lea     r8, aOnecoreuapNetU_20; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180050a77  mov     edx, 0CBDh; void *
0x180050a7c  mov     rcx, r10; this
0x180050a7f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180050a84  mov     rax, [rsi+38h]
0x180050a88  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180050a8f  jnz     short loc_180050A9C
0x180050a91  mov     rax, [rsi+40h]
0x180050a95  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180050a9c  test    rax, rax
0x180050a9f  setz    al
0x180050aa2  mov     r10, [rsp+0C8h]
0x180050aaa  test    al, al
0x180050aac  jz      short loc_180050AC8
0x180050aae  mov     r9d, 80070057h; char *
0x180050ab4  lea     r8, aOnecoreuapNetU_20; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180050abb  mov     edx, 0CBEh; void *
0x180050ac0  mov     rcx, r10; this
0x180050ac3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180050ac8  mov     rax, [rsi+38h]
0x180050acc  sub     rax, [rbx+4B4h]
0x180050ad3  jnz     short loc_180050AE0
0x180050ad5  mov     rax, [rsi+40h]
0x180050ad9  sub     rax, [rbx+4BCh]
0x180050ae0  test    rax, rax
0x180050ae3  jz      short loc_180050B2F
0x180050ae5  mov     rax, [rsi+38h]
0x180050ae9  sub     rax, [rbx+4A4h]
0x180050af0  jnz     short loc_180050AFD
0x180050af2  mov     rax, [rsi+40h]
0x180050af6  sub     rax, [rbx+4ACh]
0x180050afd  test    rax, rax
0x180050b00  jz      short loc_180050B2F
0x180050b02  cmp     rcx, r14
0x180050b05  jz      loc_180050C78
0x180050b0b  test    byte ptr [rcx+1Ch], 8
0x180050b0f  jz      loc_180050C78
0x180050b15  mov     edx, 0FBh
0x180050b1a  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x180050b21  mov     rcx, [rcx+10h]
0x180050b25  call    WPP_SF_
0x180050b2a  jmp     loc_180050C78
0x180050b2f  movups  xmm0, xmmword ptr [rsi+4]
0x180050b33  movdqu  xmmword ptr [rsp+0C8h+var_88.Data1], xmm0
0x180050b39  lea     r8, [rsp+0C8h+var_88]; struct _GUID
0x180050b3e  lea     rdx, [rsi+28h]; struct _L2_UI_REQUEST *
0x180050b42  mov     rcx, rbx; this
0x180050b45  call    ?_SetInitialUIRequest@WlanInterface@Internal@UX@Networking@Windows@@IEAAJAEBU_L2_UI_REQUEST@@U_GUID@@@Z; Windows::Networking::UX::Internal::WlanInterface::_SetInitialUIRequest(_L2_UI_REQUEST const &,_GUID)
0x180050b4a  mov     rcx, [rsp+0C8h]; this
0x180050b52  test    eax, eax
0x180050b54  jns     short loc_180050B6A
0x180050b56  mov     r9d, eax; char *
0x180050b59  lea     r8, aOnecoreuapNetU_20; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180050b60  mov     edx, 0CC3h; void *
0x180050b65  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180050b6a  cmp     byte ptr [rbx+22h], 0
0x180050b6e  jz      loc_180050C16
0x180050b74  mov     [rsp+0C8h+pv], 0
0x180050b80  lea     rax, [rsp+0C8h+pv]
0x180050b88  mov     qword ptr [rsp+0C8h+var_88.Data1], rax
0x180050b8d  mov     qword ptr [rsp+0C8h+var_88.Data4], 0
0x180050b96  mov     [rsp+0C8h+var_78], 1
0x180050b9b  lea     rdx, [rsp+0C8h+var_88.Data4]; struct _L2_UI_REQUEST **
0x180050ba0  lea     rcx, [rsi+28h]; Src
0x180050ba4  call    ?_CopyUIRequest@WlanInterface@Internal@UX@Networking@Windows@@KAJAEBU_L2_UI_REQUEST@@PEAPEAU6@@Z; Windows::Networking::UX::Internal::WlanInterface::_CopyUIRequest(_L2_UI_REQUEST const &,_L2_UI_REQUEST * *)
0x180050ba9  mov     rcx, [rsp+0C8h]; this
0x180050bb1  test    eax, eax
0x180050bb3  jns     short loc_180050BCA
0x180050bb5  mov     r9d, eax; char *
0x180050bb8  lea     r8, aOnecoreuapNetU_20; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180050bbf  mov     edx, 0CC7h; void *
0x180050bc4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180050bca  lea     rcx, [rsp+0C8h+var_88]
0x180050bcf  call    ??1?$out_param_t@V?$unique_ptr@U_L2_UI_RESPONSE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180050bd4  mov     r8, [rsp+0C8h+pv]; struct _L2_UI_REQUEST *
0x180050bdc  mov     [rsp+0C8h+pv], 0
0x180050be8  lea     rdx, [rsi+4]; struct _GUID *
0x180050bec  mov     rcx, rbx; this
0x180050bef  call    ?_ProcessUIRequest@WlanInterface@Internal@UX@Networking@Windows@@IEAAXAEBU_GUID@@PEAU_L2_UI_REQUEST@@@Z; Windows::Networking::UX::Internal::WlanInterface::_ProcessUIRequest(_GUID const &,_L2_UI_REQUEST *)
0x180050bf4  nop
0x180050bf5  mov     rcx, [rsp+0C8h+pv]; pv
0x180050bfd  mov     [rsp+0C8h+pv], 0
0x180050c09  test    rcx, rcx
0x180050c0c  jz      short loc_180050C78
0x180050c0e  call    cs:__imp_CoTaskMemFree
0x180050c14  jmp     short loc_180050C78
0x180050c16  cmp     byte ptr [rbx+20h], 0
0x180050c1a  jz      short loc_180050C78
0x180050c1c  lea     rcx, [rbx+21h]
0x180050c20  call    ?load@?$_Atomic_storage@_N$00@std@@QEBA_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::load(std::memory_order)
0x180050c25  test    al, al
0x180050c27  jz      short loc_180050C78
0x180050c29  mov     r10, [rbx+10h]
0x180050c2d  lea     rcx, [rsp+0C8h+var_68]
0x180050c32  call    std__function_void___cdecl_Windows__Networking__UX__Internal__WlanInterface___Windows__Networking__UX__Internal__WlanMediaManager______function_void___cdecl_Windows__Networking__UX__Internal__WlanInterface___Windows__Networking__UX__Internal__WlanMediaManager______Windows__Networking__UX__Internal__WlanInterface__s_WnfUIEventCallback____16____lambda_1__0_
0x180050c37  movups  xmm0, xmmword ptr [rbx+4B4h]
0x180050c3e  movdqu  xmmword ptr [rsp+0C8h+var_88.Data1], xmm0
0x180050c44  mov     r9, rax
0x180050c47  xor     r8d, r8d
0x180050c4a  lea     rdx, [rsp+0C8h+var_88]
0x180050c4f  mov     rcx, r10
0x180050c52  call    ?RunComTaskWithInterface@WlanMediaManager@Internal@UX@Networking@Windows@@QEAAJU_GUID@@_NV?$function@$$A6AXPEAVWlanInterface@Internal@UX@Networking@Windows@@PEAVWlanMediaManager@2345@@Z@std@@@Z; Windows::Networking::UX::Internal::WlanMediaManager::RunComTaskWithInterface(_GUID,bool,std::function<void (Windows::Networking::UX::Internal::WlanInterface *,Windows::Networking::UX::Internal::WlanMediaManager *)>)
0x180050c57  mov     rcx, [rsp+0C8h]; this
0x180050c5f  test    eax, eax
0x180050c61  jns     short loc_180050C78
0x180050c63  mov     r9d, eax; char *
0x180050c66  lea     r8, aOnecoreuapNetU_20; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180050c6d  mov     edx, 0CD1h; void *
0x180050c72  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180050c77  nop
0x180050c78  lea     rcx, [rsp+0C8h+var_98]
0x180050c7d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180050c82  nop
0x180050c83  jmp     short loc_180050C8C
0x180050c85  lea     r14, WPP_GLOBAL_Control
0x180050c8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180050c93  cmp     rcx, r14
0x180050c96  jz      short loc_180050CB6
0x180050c98  test    byte ptr [rcx+1Ch], 40h
0x180050c9c  jz      short loc_180050CB6
0x180050c9e  mov     edx, 0FCh
0x180050ca3  xor     r9d, r9d
0x180050ca6  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x180050cad  mov     rcx, [rcx+10h]
0x180050cb1  call    WPP_SF_d
0x180050cb6  xor     eax, eax
0x180050cb8  add     rsp, 0A8h
0x180050cbf  pop     r14
0x180050cc1  pop     rdi
0x180050cc2  pop     rsi
0x180050cc3  pop     rbx
0x180050cc4  retn
```
