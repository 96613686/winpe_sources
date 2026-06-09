# CRmsInterface::ProvisionForCurrentUser(void)

- ea: `0x18006e29c`
- end: `0x18006e4ad`
- name: `?ProvisionForCurrentUser@CRmsInterface@@QEAAJXZ`
- size: `529`
- prototype: `__int64 __fastcall(CRmsInterface *__hidden this)`
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180040964`
- `0x18006d1a0`
- `0x18006d5f4`

## callees

- `0x18000dc8c`
- `0x18000f13c`
- `0x1800617c0`
- `0x180061bb4`
- `0x18006b1a8`
- `0x18006ba48`
- `0x18006bcf8`
- `0x18006c008`
- `0x18006c764`
- `0x18006db58`
- `0x18006dddc`
- `0x18006e29c`
- `0x18006ef94`
- `0x18006f0b4`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18006e2de`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x18006e2de`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18006e478`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18006e478`
- `winmsipc!__imp_IpcFreeMemory` at `0x18006e430`
- `winmsipc!__imp_IpcFreeMemory` at `0x18006e440`
- `winmsipc!__imp_IpcFreeMemory` at `0x18006e450`
- `winmsipc!__imp_IpcFreeMemory` at `0x18006e430`
- `winmsipc!__imp_IpcFreeMemory` at `0x18006e440`
- `winmsipc!__imp_IpcFreeMemory` at `0x18006e450`
- `winmsipc!__imp_IpcGetTemplateList` at `0x18006e410`
- `winmsipc!__imp_IpcGetTemplateList` at `0x18006e410`
- `winmsipc!__imp_IpcpBootstrapUser` at `0x18006e3cb`
- `winmsipc!__imp_IpcpBootstrapUser` at `0x18006e3cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRmsInterface::ProvisionForCurrentUser(CRmsInterface *this)
{
  int v1; // ebx
  CRmsInterface *v2; // rcx
  signed int RmsOwnerEmailId; // edi
  char v4; // cl
  const unsigned __int16 *v5; // rcx
  signed int TemplateList; // eax
  __int64 v7; // rdx
  signed int v9; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v10; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v11; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v12; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v13; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v14; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v15[24]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v16[72]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v17[16]; // [rsp+E0h] [rbp-20h] BYREF
  int v18; // [rsp+F0h] [rbp-10h]
  _QWORD v19[42]; // [rsp+110h] [rbp+10h] BYREF

  RmsPromptContext::RmsPromptContext((RmsPromptContext *)v15);
  v12 = 0;
  v1 = RoInitialize(1);
  wil::ActivityBase<EfsTraceLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<EfsTraceLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v19,
    "RmsProvisionForCurrentUser");
  v19[0] = &EfsTelemetry::RmsProvisionForCurrentUser::`vftable';
  EfsTelemetry::RmsProvisionForCurrentUser::StartActivity((EfsTelemetry::RmsProvisionForCurrentUser *)v19);
  v13 = 0;
  v11 = 0;
  v14 = 0;
  v10 = 0;
  if ( g_RmsInterface || (RmsOwnerEmailId = CRmsInterface::LoadRmsMsIpc(v2), v9 = RmsOwnerEmailId, RmsOwnerEmailId >= 0) )
  {
    CheckAndClearTempRmsAccess();
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v10,
      0);
    RmsOwnerEmailId = EfsConfig_GetRmsOwnerEmailId(&v10);
    v9 = RmsOwnerEmailId;
    if ( RmsOwnerEmailId >= 0 )
    {
      if ( v10 )
      {
        v4 = 1;
        LODWORD(v14) = 1;
        *((_QWORD *)&v14 + 1) = v10;
      }
      else
      {
        v4 = 0;
      }
      v18 &= ~2u;
      if ( (int)IpcpBootstrapUser(0, (unsigned __int64)&v14 & -(__int64)(v4 != 0), 0, v17, 0, &v13, &v11) >= 0
        && *(_DWORD *)v11 == 1
        && (v5 = *(const unsigned __int16 **)(v11 + 8)) != 0 )
      {
        TemplateList = EfsConfig_SetRmsOwnerEmail(v5);
      }
      else
      {
        v18 &= ~2u;
        TemplateList = IpcGetTemplateList(0, 0, 0, v17, 0, &v12);
      }
      v9 = TemplateList;
      RmsOwnerEmailId = TemplateList;
    }
  }
  EfsTelemetry::RmsProvisionForCurrentUser::LogRmsProvisionForCurrentUser<long &>(&v9);
  if ( v12 )
    IpcFreeMemory();
  if ( v13 )
    IpcFreeMemory();
  if ( v11 )
    IpcFreeMemory();
  wil::ActivityBase<EfsTraceLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v19);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(
    &v10,
    v7);
  EfsTelemetry::RmsProvisionForCurrentUser::~RmsProvisionForCurrentUser((EfsTelemetry::RmsProvisionForCurrentUser *)v19);
  if ( v1 >= 0 )
    RoUninitialize();
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v16);
  return (unsigned int)RmsOwnerEmailId;
}

```

## disassembly

```asm
0x18006e29c  mov     [rsp-8+arg_0], rbx
0x18006e2a1  mov     [rsp-8+arg_8], rdi
0x18006e2a6  push    rbp
0x18006e2a7  lea     rbp, [rsp-170h]
0x18006e2af  sub     rsp, 270h
0x18006e2b6  mov     rax, cs:__security_cookie
0x18006e2bd  xor     rax, rsp
0x18006e2c0  mov     [rbp+170h+var_10], rax
0x18006e2c7  lea     rcx, [rbp+170h+var_1F0]; this
0x18006e2cb  call    ??0RmsPromptContext@@QEAA@XZ; RmsPromptContext::RmsPromptContext(void)
0x18006e2d0  mov     [rsp+270h+var_218], 0
0x18006e2d9  mov     ecx, 1
0x18006e2de  call    cs:__imp_RoInitialize
0x18006e2e4  mov     ebx, eax
0x18006e2e6  lea     rdx, aRmsprovisionfo; "RmsProvisionForCurrentUser"
0x18006e2ed  lea     rcx, [rbp+170h+var_160]
0x18006e2f1  call    ??0?$ActivityBase@VEfsTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<EfsTraceLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<EfsTraceLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18006e2f6  lea     rax, ??_7RmsProvisionForCurrentUser@EfsTelemetry@@6B@; const EfsTelemetry::RmsProvisionForCurrentUser::`vftable'
0x18006e2fd  mov     [rbp+170h+var_160], rax
0x18006e301  lea     rcx, [rbp+170h+var_160]; this
0x18006e305  call    ?StartActivity@RmsProvisionForCurrentUser@EfsTelemetry@@QEAAXXZ; EfsTelemetry::RmsProvisionForCurrentUser::StartActivity(void)
0x18006e30a  mov     [rsp+270h+var_210], 0
0x18006e313  mov     [rsp+270h+var_220], 0
0x18006e31c  xorps   xmm0, xmm0
0x18006e31f  movups  [rsp+270h+var_208], xmm0
0x18006e324  mov     [rsp+270h+var_228], 0
0x18006e32d  cmp     cs:?g_RmsInterface@@3VCRmsInterface@@A, 0; CRmsInterface g_RmsInterface
0x18006e335  jnz     short loc_18006E34A
0x18006e337  call    ?LoadRmsMsIpc@CRmsInterface@@AEAAJXZ; CRmsInterface::LoadRmsMsIpc(void)
0x18006e33c  mov     edi, eax
0x18006e33e  mov     [rsp+270h+var_230], eax
0x18006e342  test    eax, eax
0x18006e344  js      loc_18006E41C
0x18006e34a  call    CheckAndClearTempRmsAccess
0x18006e34f  xor     edx, edx
0x18006e351  lea     rcx, [rsp+270h+var_228]
0x18006e356  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18006e35b  lea     rcx, [rsp+270h+var_228]; unsigned __int16 **
0x18006e360  call    ?EfsConfig_GetRmsOwnerEmailId@@YAJPEAPEAG@Z; EfsConfig_GetRmsOwnerEmailId(ushort * *)
0x18006e365  mov     edi, eax
0x18006e367  mov     [rsp+270h+var_230], eax
0x18006e36b  test    eax, eax
0x18006e36d  js      loc_18006E41C
0x18006e373  mov     rax, [rsp+270h+var_228]
0x18006e378  test    rax, rax
0x18006e37b  jz      short loc_18006E38E
0x18006e37d  mov     cl, 1
0x18006e37f  mov     dword ptr [rsp+270h+var_208], 1
0x18006e387  mov     qword ptr [rsp+270h+var_208+8], rax
0x18006e38c  jmp     short loc_18006E390
0x18006e38e  xor     cl, cl
0x18006e390  mov     edi, 0FFFFFFFDh
0x18006e395  and     [rbp+170h+var_180], edi
0x18006e398  neg     cl
0x18006e39a  sbb     rdx, rdx
0x18006e39d  lea     rax, [rsp+270h+var_208]
0x18006e3a2  and     rdx, rax
0x18006e3a5  lea     rax, [rsp+270h+var_220]
0x18006e3aa  mov     [rsp+270h+var_240], rax
0x18006e3af  lea     rax, [rsp+270h+var_210]
0x18006e3b4  mov     [rsp+270h+var_248], rax
0x18006e3b9  mov     [rsp+270h+var_250], 0
0x18006e3c2  lea     r9, [rbp+170h+var_190]
0x18006e3c6  xor     r8d, r8d
0x18006e3c9  xor     ecx, ecx
0x18006e3cb  call    cs:__imp_IpcpBootstrapUser
0x18006e3d1  test    eax, eax
0x18006e3d3  js      short loc_18006E3EF
0x18006e3d5  mov     rax, [rsp+270h+var_220]
0x18006e3da  cmp     dword ptr [rax], 1
0x18006e3dd  jnz     short loc_18006E3EF
0x18006e3df  mov     rcx, [rax+8]; unsigned __int16 *
0x18006e3e3  test    rcx, rcx
0x18006e3e6  jz      short loc_18006E3EF
0x18006e3e8  call    ?EfsConfig_SetRmsOwnerEmail@@YAJPEBG@Z; EfsConfig_SetRmsOwnerEmail(ushort const *)
0x18006e3ed  jmp     short loc_18006E416
0x18006e3ef  and     [rbp+170h+var_180], edi
0x18006e3f2  lea     rax, [rsp+270h+var_218]
0x18006e3f7  mov     [rsp+270h+var_248], rax
0x18006e3fc  mov     [rsp+270h+var_250], 0
0x18006e405  lea     r9, [rbp+170h+var_190]
0x18006e409  xor     r8d, r8d
0x18006e40c  xor     edx, edx
0x18006e40e  xor     ecx, ecx
0x18006e410  call    cs:__imp_IpcGetTemplateList
0x18006e416  mov     [rsp+270h+var_230], eax
0x18006e41a  mov     edi, eax
0x18006e41c  lea     rcx, [rsp+270h+var_230]
0x18006e421  call    ??$LogRmsProvisionForCurrentUser@AEAJ@RmsProvisionForCurrentUser@EfsTelemetry@@SAXAEAJ@Z; EfsTelemetry::RmsProvisionForCurrentUser::LogRmsProvisionForCurrentUser<long &>(long &)
0x18006e426  mov     rcx, [rsp+270h+var_218]
0x18006e42b  test    rcx, rcx
0x18006e42e  jz      short loc_18006E436
0x18006e430  call    cs:__imp_IpcFreeMemory
0x18006e436  mov     rcx, [rsp+270h+var_210]
0x18006e43b  test    rcx, rcx
0x18006e43e  jz      short loc_18006E446
0x18006e440  call    cs:__imp_IpcFreeMemory
0x18006e446  mov     rcx, [rsp+270h+var_220]
0x18006e44b  test    rcx, rcx
0x18006e44e  jz      short loc_18006E456
0x18006e450  call    cs:__imp_IpcFreeMemory
0x18006e456  lea     rcx, [rbp+170h+var_160]
0x18006e45a  call    ?Stop@?$ActivityBase@VEfsTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<EfsTraceLoggingProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18006e45f  nop
0x18006e460  lea     rcx, [rsp+270h+var_228]
0x18006e465  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006e46a  nop
0x18006e46b  lea     rcx, [rbp+170h+var_160]; this
0x18006e46f  call    ??1RmsProvisionForCurrentUser@EfsTelemetry@@QEAA@XZ; EfsTelemetry::RmsProvisionForCurrentUser::~RmsProvisionForCurrentUser(void)
0x18006e474  test    ebx, ebx
0x18006e476  js      short loc_18006E47E
0x18006e478  call    cs:__imp_RoUninitialize
0x18006e47e  lea     rcx, [rbp+170h+var_1D8]
0x18006e482  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006e487  mov     eax, edi
0x18006e489  mov     rcx, [rbp+170h+var_10]
0x18006e490  xor     rcx, rsp; StackCookie
0x18006e493  call    __security_check_cookie
0x18006e498  lea     r11, [rsp+270h+var_s0]
0x18006e4a0  mov     rbx, [r11+10h]
0x18006e4a4  mov     rdi, [r11+18h]
0x18006e4a8  mov     rsp, r11
0x18006e4ab  pop     rbp
0x18006e4ac  retn
```
