# KsNotifications_ServiceStart(void)

- ea: `0x18005f2ec`
- end: `0x18005f466`
- name: `?KsNotifications_ServiceStart@@YAJXZ`
- size: `378`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180047240`

## callees

- `0x180006b0c`
- `0x180021060`
- `0x1800236b4`
- `0x180025fe0`
- `0x18005f2ec`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005f319`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005f319`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f411`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f41b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f411`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f41b`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 KsNotifications_ServiceStart(void)
{
  unsigned int i; // ebx
  __int64 v1; // rcx
  const unsigned __int16 *v2; // r8
  __int64 v4; // [rsp+20h] [rbp-28h] BYREF
  LPVOID v5; // [rsp+28h] [rbp-20h] BYREF
  __int64 v6; // [rsp+30h] [rbp-18h] BYREF
  struct _RTL_CRITICAL_SECTION *v7; // [rsp+38h] [rbp-10h] BYREF
  unsigned int v8; // [rsp+60h] [rbp+18h] BYREF
  struct IMMDevice *v9; // [rsp+68h] [rbp+20h] BYREF
  __int64 v10; // [rsp+70h] [rbp+28h] BYREF
  LPVOID pv; // [rsp+78h] [rbp+30h] BYREF

  ATL::CComQIPtr<IPnpDeviceEnumerator,&__s_GUID const _GUID_3e52272f_3c89_45f8_be26_cb3b91ab42a0>::CComQIPtr<IPnpDeviceEnumerator,&__s_GUID const _GUID_3e52272f_3c89_45f8_be26_cb3b91ab42a0>(&v6);
  v10 = 0;
  v8 = 0;
  EnterCriticalSection(&g_csKsNotificationMonitors);
  v7 = &g_csKsNotificationMonitors;
  if ( (*(int (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v6 + 32LL))(
         v6,
         &GUID_6994ad04_93ef_11d0_a3cc_00a0c9223196,
         &v10) >= 0
    && (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v10 + 24LL))(v10, &v8) >= 0 )
  {
    for ( i = 0; i < v8; ++i )
    {
      v9 = 0;
      if ( (*(int (__fastcall **)(__int64, _QWORD, struct IMMDevice **))(*(_QWORD *)v10 + 32LL))(v10, i, &v9) >= 0 )
      {
        v5 = 0;
        if ( ((int (__fastcall *)(struct IMMDevice *, LPVOID *))v9->lpVtbl->GetId)(v9, &v5) >= 0 )
        {
          v1 = 0;
          v4 = 0;
          if ( v9 )
          {
            ((void (__fastcall *)(struct IMMDevice *, GUID *, __int64 *))v9->lpVtbl->QueryInterface)(
              v9,
              &GUID_3ade56af_4375_4413_9c91_4c652595ab07,
              &v4);
            v1 = v4;
          }
          pv = 0;
          if ( v1 && (*(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v1 + 32LL))(v1, &pv) >= 0 )
          {
            KsNotifications_ProcessPnpInterface(v9, (const unsigned __int16 *)pv, v2);
            CoTaskMemFree(pv);
          }
          CoTaskMemFree(v5);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v4);
        }
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v9);
    }
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v7);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v10);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v6);
  return 0;
}

```

## disassembly

```asm
0x18005f2ec  push    rbp
0x18005f2ee  push    rbx
0x18005f2ef  mov     rbp, rsp
0x18005f2f2  sub     rsp, 48h
0x18005f2f6  lea     rcx, [rbp+var_18]
0x18005f2fa  call    ??0?$CComQIPtr@UIPnpDeviceEnumerator@@$1?_GUID_3e52272f_3c89_45f8_be26_cb3b91ab42a0@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IPnpDeviceEnumerator,&__s_GUID const _GUID_3e52272f_3c89_45f8_be26_cb3b91ab42a0>::CComQIPtr<IPnpDeviceEnumerator,&__s_GUID const _GUID_3e52272f_3c89_45f8_be26_cb3b91ab42a0>(IUnknown *)
0x18005f2ff  nop
0x18005f300  mov     [rbp+arg_10], 0
0x18005f308  mov     [rbp+arg_0], 0
0x18005f30f  lea     rbx, ?g_csKsNotificationMonitors@@3Vcritical_section@wil@@A; wil::critical_section g_csKsNotificationMonitors
0x18005f316  mov     rcx, rbx; lpCriticalSection
0x18005f319  call    cs:__imp_EnterCriticalSection
0x18005f31f  mov     [rbp+var_10], rbx
0x18005f323  mov     rcx, [rbp+var_18]
0x18005f327  mov     rax, [rcx]
0x18005f32a  lea     r8, [rbp+arg_10]
0x18005f32e  lea     rdx, _GUID_6994ad04_93ef_11d0_a3cc_00a0c9223196
0x18005f335  mov     rax, [rax+20h]
0x18005f339  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f33e  test    eax, eax
0x18005f340  js      loc_18005F440
0x18005f346  mov     rcx, [rbp+arg_10]
0x18005f34a  mov     rax, [rcx]
0x18005f34d  lea     rdx, [rbp+arg_0]
0x18005f351  mov     rax, [rax+18h]
0x18005f355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f35a  test    eax, eax
0x18005f35c  js      loc_18005F440
0x18005f362  xor     ebx, ebx
0x18005f364  cmp     [rbp+arg_0], ebx
0x18005f367  jbe     loc_18005F440
0x18005f36d  mov     [rbp+arg_8], 0
0x18005f375  mov     rcx, [rbp+arg_10]
0x18005f379  mov     rax, [rcx]
0x18005f37c  lea     r8, [rbp+arg_8]
0x18005f380  mov     edx, ebx
0x18005f382  mov     rax, [rax+20h]
0x18005f386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f38b  test    eax, eax
0x18005f38d  js      loc_18005F42C
0x18005f393  mov     [rbp+var_20], 0
0x18005f39b  mov     rcx, [rbp+arg_8]
0x18005f39f  mov     rax, [rcx]
0x18005f3a2  lea     rdx, [rbp+var_20]
0x18005f3a6  mov     rax, [rax+28h]
0x18005f3aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f3af  test    eax, eax
0x18005f3b1  js      short loc_18005F42C
0x18005f3b3  mov     r9, [rbp+arg_8]
0x18005f3b7  xor     ecx, ecx
0x18005f3b9  mov     [rbp+var_28], rcx
0x18005f3bd  test    r9, r9
0x18005f3c0  jz      short loc_18005F3DF
0x18005f3c2  mov     rax, [r9]
0x18005f3c5  lea     r8, [rbp+var_28]
0x18005f3c9  lea     rdx, _GUID_3ade56af_4375_4413_9c91_4c652595ab07
0x18005f3d0  mov     rcx, r9
0x18005f3d3  mov     rax, [rax]
0x18005f3d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f3db  mov     rcx, [rbp+var_28]
0x18005f3df  mov     [rbp+pv], 0
0x18005f3e7  test    rcx, rcx
0x18005f3ea  jz      short loc_18005F417
0x18005f3ec  mov     rax, [rcx]
0x18005f3ef  lea     rdx, [rbp+pv]
0x18005f3f3  mov     rax, [rax+20h]
0x18005f3f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f3fc  test    eax, eax
0x18005f3fe  js      short loc_18005F417
0x18005f400  mov     rdx, [rbp+pv]; unsigned __int16 *
0x18005f404  mov     rcx, [rbp+arg_8]; struct IMMDevice *
0x18005f408  call    ?KsNotifications_ProcessPnpInterface@@YAXPEAUIMMDevice@@PEBG1@Z; KsNotifications_ProcessPnpInterface(IMMDevice *,ushort const *,ushort const *)
0x18005f40d  mov     rcx, [rbp+pv]; pv
0x18005f411  call    cs:__imp_CoTaskMemFree
0x18005f417  mov     rcx, [rbp+var_20]; pv
0x18005f41b  call    cs:__imp_CoTaskMemFree
0x18005f421  nop
0x18005f422  lea     rcx, [rbp+var_28]
0x18005f426  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005f42b  nop
0x18005f42c  lea     rcx, [rbp+arg_8]
0x18005f430  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005f435  inc     ebx
0x18005f437  cmp     ebx, [rbp+arg_0]
0x18005f43a  jb      loc_18005F36D
0x18005f440  lea     rcx, [rbp+var_10]
0x18005f444  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x18005f449  nop
0x18005f44a  lea     rcx, [rbp+arg_10]
0x18005f44e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005f453  nop
0x18005f454  lea     rcx, [rbp+var_18]
0x18005f458  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005f45d  xor     eax, eax
0x18005f45f  add     rsp, 48h
0x18005f463  pop     rbx
0x18005f464  pop     rbp
0x18005f465  retn
```
