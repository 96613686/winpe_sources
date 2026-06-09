# _RunServer(void)

- ea: `0x140008fdc`
- end: `0x140009233`
- name: `?_RunServer@@YAJXZ`
- size: `599`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400093a4`

## callees

- `0x14000330c`
- `0x140004340`
- `0x140004d74`
- `0x1400069fc`
- `0x1400079f4`
- `0x140008d1c`
- `0x140008fac`
- `0x140008fdc`
- `0x14000925c`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400091f9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400091f9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140009049`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140009049`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140008ff2`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140008ff2`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140009103`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140009103`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140009210`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140009210`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1400091df`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1400091df`

## string_xrefs

- `0x140009005`: `shellcommon\shell\cloudexperiencehost\onecore\exe\cloudexperiencehostbroker.cpp`
- `0x140009083`: `shellcommon\shell\cloudexperiencehost\onecore\exe\cloudexperiencehostbroker.cpp`
- `0x1400090b8`: `shellcommon\shell\cloudexperiencehost\onecore\exe\cloudexperiencehostbroker.cpp`
- `0x140009114`: `shellcommon\shell\cloudexperiencehost\onecore\exe\cloudexperiencehostbroker.cpp`
- `0x140009177`: `shellcommon\shell\cloudexperiencehost\onecore\exe\cloudexperiencehostbroker.cpp`
- `0x1400091b0`: `shellcommon\shell\cloudexperiencehost\onecore\exe\cloudexperiencehostbroker.cpp`

## pseudocode

```c
__int64 _RunServer(void)
{
  HRESULT v0; // eax
  unsigned int v1; // edi
  HRESULT v2; // eax
  __int64 v3; // rdx
  int v4; // eax
  int v5; // eax
  Microsoft::WRL::Details *v6; // rdi
  int v7; // eax
  int v8; // esi
  __int64 v9; // rdx
  struct Microsoft::WRL::Details::ModuleBase *v10; // rdx
  const unsigned __int16 *v11; // r8
  struct Microsoft::WRL::Details::ModuleBase *v12; // rdx
  const unsigned __int16 *v13; // r8
  int ppv; // [rsp+20h] [rbp-30h]
  int ppva; // [rsp+20h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  HANDLE hHandle; // [rsp+60h] [rbp+10h] BYREF
  LPVOID v19; // [rsp+68h] [rbp+18h] BYREF

  v0 = CoInitializeEx(0, 0);
  v1 = v0;
  if ( v0 >= 0 )
  {
    v19 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
    v2 = CoCreateInstance(&CLSID_GlobalOptions, 0, 3u, &GUID_0000015b_0000_0000_c000_000000000046, &v19);
    v1 = v2;
    if ( v2 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v19 + 24LL))(v19, 4, 24);
      if ( v4 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x58,
          (unsigned int)"shellcommon\\shell\\cloudexperiencehost\\onecore\\exe\\cloudexperiencehostbroker.cpp",
          (const char *)(unsigned int)v4,
          ppva);
      v5 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v19 + 24LL))(v19, 5, 1);
      if ( v5 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x59,
          (unsigned int)"shellcommon\\shell\\cloudexperiencehost\\onecore\\exe\\cloudexperiencehostbroker.cpp",
          (const char *)(unsigned int)v5,
          ppva);
      v2 = CoInitializeSecurity(&GUID_efe2d6d8_a81b_41e7_ae77_e5244ab80522, -1, 0, 0, 0, 0, 0, 0x1048u, 0);
      v1 = v2;
      if ( v2 >= 0 )
      {
        v6 = (Microsoft::WRL::Details *)Microsoft::WRL::Details::OutOfProcModuleBase<MultipleUseOutOfProcModule>::Create();
        if ( !*((_QWORD *)v6 + 1) )
        {
          byte_140011A60 = 1;
          byte_140011A50 = 0;
          qword_140011A48 = (__int64)off_14000BE60;
          *((_QWORD *)v6 + 1) = &qword_140011A48;
        }
        v7 = Microsoft::WRL::Details::RegisterObjects<2>(v6);
        v8 = v7;
        if ( v7 >= 0 )
        {
          hHandle = 0;
          v8 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
                 &hHandle,
                 1);
          if ( v8 >= 0 )
          {
            v8 = CoRegisterServerShutdownDelay(hHandle, 300000);
            if ( v8 >= 0 )
            {
              WaitForSingleObject(hHandle, 0xFFFFFFFF);
              __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
              Microsoft::WRL::Details::UnregisterObjects(v6, v12, v13);
              CoUninitialize();
              v1 = 0;
              goto LABEL_23;
            }
            v9 = 113;
          }
          else
          {
            v9 = 112;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v9,
            (unsigned int)"shellcommon\\shell\\cloudexperiencehost\\onecore\\exe\\cloudexperiencehostbroker.cpp",
            (const char *)(unsigned int)v8,
            ppva);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hHandle);
          Microsoft::WRL::Details::UnregisterObjects(v6, v10, v11);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x67,
            (unsigned int)"shellcommon\\shell\\cloudexperiencehost\\onecore\\exe\\cloudexperiencehostbroker.cpp",
            (const char *)(unsigned int)v7,
            ppva);
        }
        v1 = v8;
LABEL_23:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
        return v1;
      }
      v3 = 98;
    }
    else
    {
      v3 = 87;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"shellcommon\\shell\\cloudexperiencehost\\onecore\\exe\\cloudexperiencehostbroker.cpp",
      (const char *)(unsigned int)v2,
      ppva);
    goto LABEL_23;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x53,
    (unsigned int)"shellcommon\\shell\\cloudexperiencehost\\onecore\\exe\\cloudexperiencehostbroker.cpp",
    (const char *)(unsigned int)v0,
    ppv);
  return v1;
}

```

## disassembly

```asm
0x140008fdc  mov     [rsp-8+arg_10], rsi
0x140008fe1  mov     [rsp-8+arg_18], rdi
0x140008fe6  push    rbp
0x140008fe7  mov     rbp, rsp
0x140008fea  sub     rsp, 50h
0x140008fee  xor     edx, edx; dwCoInit
0x140008ff0  xor     ecx, ecx; pvReserved
0x140008ff2  call    cs:__imp_CoInitializeEx
0x140008ff8  mov     edi, eax
0x140008ffa  test    eax, eax
0x140008ffc  jns     short loc_14000901B
0x140008ffe  mov     rcx, [rbp+8]; this
0x140009002  mov     r9d, eax; char *
0x140009005  lea     r8, aShellcommonShe; "shellcommon\\shell\\cloudexperiencehost"...
0x14000900c  mov     edx, 53h ; 'S'; void *
0x140009011  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009016  jmp     loc_140009221
0x14000901b  mov     [rbp+arg_8], 0
0x140009023  lea     rcx, [rbp+arg_8]
0x140009027  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000902c  lea     rax, [rbp+arg_8]
0x140009030  mov     [rsp+50h+ppv], rax; int
0x140009035  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x14000903c  xor     edx, edx; pUnkOuter
0x14000903e  lea     r8d, [rdx+3]; dwClsContext
0x140009042  lea     rcx, CLSID_GlobalOptions; rclsid
0x140009049  call    cs:__imp_CoCreateInstance
0x14000904f  mov     edi, eax
0x140009051  test    eax, eax
0x140009053  jns     short loc_14000905F
0x140009055  mov     edx, 57h ; 'W'
0x14000905a  jmp     loc_140009114
0x14000905f  mov     rcx, [rbp+arg_8]
0x140009063  mov     rax, [rcx]
0x140009066  mov     edx, 4
0x14000906b  lea     r8d, [rdx+14h]
0x14000906f  mov     rax, [rax+18h]
0x140009073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009078  mov     rcx, [rbp+8]; this
0x14000907c  test    eax, eax
0x14000907e  jns     short loc_140009094
0x140009080  mov     r9d, eax; char *
0x140009083  lea     r8, aShellcommonShe; "shellcommon\\shell\\cloudexperiencehost"...
0x14000908a  mov     edx, 58h ; 'X'; void *
0x14000908f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140009094  mov     rcx, [rbp+arg_8]
0x140009098  mov     rax, [rcx]
0x14000909b  mov     edx, 5
0x1400090a0  lea     r8d, [rdx-4]
0x1400090a4  mov     rax, [rax+18h]
0x1400090a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400090ad  mov     rcx, [rbp+8]; this
0x1400090b1  test    eax, eax
0x1400090b3  jns     short loc_1400090C9
0x1400090b5  mov     r9d, eax; char *
0x1400090b8  lea     r8, aShellcommonShe; "shellcommon\\shell\\cloudexperiencehost"...
0x1400090bf  mov     edx, 59h ; 'Y'; void *
0x1400090c4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400090c9  mov     [rsp+50h+pReserved3], 0; pReserved3
0x1400090d2  mov     [rsp+50h+dwCapabilities], 1048h; dwCapabilities
0x1400090da  mov     [rsp+50h+pAuthList], 0; pAuthList
0x1400090e3  mov     [rsp+50h+dwImpLevel], 0; dwImpLevel
0x1400090eb  mov     dword ptr [rsp+50h+ppv], 0; int
0x1400090f3  xor     r9d, r9d; pReserved1
0x1400090f6  xor     r8d, r8d; asAuthSvc
0x1400090f9  or      edx, 0FFFFFFFFh; cAuthSvc
0x1400090fc  lea     rcx, _GUID_efe2d6d8_a81b_41e7_ae77_e5244ab80522; pSecDesc
0x140009103  call    cs:__imp_CoInitializeSecurity
0x140009109  mov     edi, eax
0x14000910b  test    eax, eax
0x14000910d  jns     short loc_14000912C
0x14000910f  mov     edx, 62h ; 'b'; void *
0x140009114  lea     r8, aShellcommonShe; "shellcommon\\shell\\cloudexperiencehost"...
0x14000911b  mov     r9d, eax; char *
0x14000911e  mov     rcx, [rbp+8]; this
0x140009122  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009127  jmp     loc_140009218
0x14000912c  call    ?Create@?$OutOfProcModuleBase@VMultipleUseOutOfProcModule@@@Details@WRL@Microsoft@@SAAEAVMultipleUseOutOfProcModule@@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<MultipleUseOutOfProcModule>::Create(void)
0x140009131  mov     rdi, rax
0x140009134  cmp     qword ptr [rax+8], 0
0x140009139  jnz     short loc_140009162
0x14000913b  mov     cs:byte_140011A60, 1
0x140009142  mov     cs:byte_140011A50, 0
0x140009149  lea     rax, off_14000BE60
0x140009150  mov     cs:qword_140011A48, rax
0x140009157  lea     rax, qword_140011A48
0x14000915e  mov     [rdi+8], rax
0x140009162  mov     rcx, rdi
0x140009165  call    ??$RegisterObjects@$01@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBG@Z; Microsoft::WRL::Details::RegisterObjects<2>(Microsoft::WRL::Details::ModuleBase *,ushort const *)
0x14000916a  mov     esi, eax
0x14000916c  test    eax, eax
0x14000916e  jns     short loc_14000918F
0x140009170  mov     rcx, [rbp+8]; this
0x140009174  mov     r9d, eax; char *
0x140009177  lea     r8, aShellcommonShe; "shellcommon\\shell\\cloudexperiencehost"...
0x14000917e  mov     edx, 67h ; 'g'; void *
0x140009183  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140009188  mov     edi, esi
0x14000918a  jmp     loc_140009218
0x14000918f  mov     [rbp+hHandle], 0
0x140009197  mov     edx, 1
0x14000919c  lea     rcx, [rbp+hHandle]
0x1400091a0  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x1400091a5  mov     esi, eax
0x1400091a7  test    eax, eax
0x1400091a9  jns     short loc_1400091D6
0x1400091ab  mov     edx, 70h ; 'p'; void *
0x1400091b0  lea     r8, aShellcommonShe; "shellcommon\\shell\\cloudexperiencehost"...
0x1400091b7  mov     r9d, esi; char *
0x1400091ba  mov     rcx, [rbp+8]; this
0x1400091be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400091c3  lea     rcx, [rbp+hHandle]
0x1400091c7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400091cc  mov     rcx, rdi; this
0x1400091cf  call    ?UnregisterObjects@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEBG@Z; Microsoft::WRL::Details::UnregisterObjects(Microsoft::WRL::Details::ModuleBase *,ushort const *)
0x1400091d4  jmp     short loc_140009188
0x1400091d6  mov     edx, 493E0h
0x1400091db  mov     rcx, [rbp+hHandle]
0x1400091df  call    cs:__imp_CoRegisterServerShutdownDelay
0x1400091e5  mov     esi, eax
0x1400091e7  test    eax, eax
0x1400091e9  jns     short loc_1400091F2
0x1400091eb  mov     edx, 71h ; 'q'
0x1400091f0  jmp     short loc_1400091B0
0x1400091f2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400091f5  mov     rcx, [rbp+hHandle]; hHandle
0x1400091f9  call    cs:__imp_WaitForSingleObject
0x1400091ff  lea     rcx, [rbp+hHandle]
0x140009203  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140009208  mov     rcx, rdi; this
0x14000920b  call    ?UnregisterObjects@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEBG@Z; Microsoft::WRL::Details::UnregisterObjects(Microsoft::WRL::Details::ModuleBase *,ushort const *)
0x140009210  call    cs:__imp_CoUninitialize
0x140009216  xor     edi, edi
0x140009218  lea     rcx, [rbp+arg_8]
0x14000921c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140009221  mov     eax, edi
0x140009223  mov     rsi, [rsp+50h+arg_10]
0x140009228  mov     rdi, [rsp+50h+arg_18]
0x14000922d  add     rsp, 50h
0x140009231  pop     rbp
0x140009232  retn
```
