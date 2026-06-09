# NotificationAvailableWork::CheckNotificationHandlerSettingsEnabledForParent(INotificationHandler *,ushort const *,bool,PolicyLevel *,NOTIFICATION_POLICY_REASON *)

- ea: `0x18007ed94`
- end: `0x18007f04f`
- name: `?CheckNotificationHandlerSettingsEnabledForParent@NotificationAvailableWork@@AEAAJPEAUINotificationHandler@@PEBG_NPEAW4PolicyLevel@@PEAW4NOTIFICATION_POLICY_REASON@@@Z`
- size: `699`
- prototype: `int(NotificationAvailableWork *__hidden this, struct INotificationHandler *, const unsigned __int16 *, bool, enum PolicyLevel *, enum NOTIFICATION_POLICY_REASON *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180054a78`
- `0x180056420`

## callees

- `0x180004e38`
- `0x180011618`
- `0x18001bf30`
- `0x180024890`
- `0x180054160`
- `0x18007ed94`
- `0x180118010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007ee5a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18007ee5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007edf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f009`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f03a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007edf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f009`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f03a`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall NotificationAvailableWork::CheckNotificationHandlerSettingsEnabledForParent(
        NotificationAvailableWork *this,
        struct INotificationHandler *a2,
        const unsigned __int16 *a3,
        bool a4,
        enum PolicyLevel *a5,
        enum NOTIFICATION_POLICY_REASON *a6)
{
  int v10; // eax
  unsigned int v11; // ebx
  void *v13; // rcx
  int v14; // eax
  int v15; // edi
  __int64 v16; // rbx
  __int64 v17; // rbx
  __int64 (__fastcall *v18)(__int64, LPVOID, struct INotificationHandler **); // rdi
  int v19; // eax
  CtaManager **v20; // rbx
  WpnDatabaseHelpers *PackageFullName; // rax
  int v22; // eax
  struct INotificationHandler *v23; // rcx
  __int64 v24; // rcx
  int v25; // [rsp+20h] [rbp-48h]
  int v26; // [rsp+20h] [rbp-48h]
  LPVOID pv; // [rsp+40h] [rbp-28h] BYREF
  struct INotificationHandler *v28; // [rsp+48h] [rbp-20h] BYREF
  LPVOID v29[3]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]
  __int64 v31; // [rsp+A8h] [rbp+40h] BYREF

  pv = 0;
  v10 = (*(__int64 (__fastcall **)(struct INotificationHandler *, LPVOID *))(*(_QWORD *)a2 + 40LL))(a2, &pv);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4E0,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\notificationavailablework.cpp",
      (const char *)(unsigned int)v10,
      v25);
LABEL_3:
    if ( pv )
      CoTaskMemFree(pv);
    return v11;
  }
  v13 = pv;
  if ( pv && *(_WORD *)pv )
  {
    v29[0] = 0;
    v14 = (*(__int64 (__fastcall **)(struct INotificationHandler *, LPVOID *))(*(_QWORD *)a2 + 24LL))(a2, v29);
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4E5,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\notificationavailablework.cpp",
        (const char *)(unsigned int)v14,
        v25);
LABEL_19:
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v29);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
      return (unsigned int)v15;
    }
    if ( (unsigned int)_o__wcsicmp(pv, v29[0]) )
    {
      v31 = 0;
      v16 = *((_QWORD *)this + 23);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
      v15 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v16 + 144))(
              *(_QWORD *)(v16 + 144),
              &GUID_145e48ec_626a_4302_9000_36e8172c6d29,
              &v31);
      v17 = v31;
      if ( v15 < 0 )
      {
LABEL_15:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4EB,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\notificationavailablework.cpp",
          (const char *)(unsigned int)v15,
          v25);
LABEL_18:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
        goto LABEL_19;
      }
      if ( !v31 )
      {
        v15 = -2143420155;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x400,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
          (const char *)0x803E0105LL,
          v25);
        goto LABEL_15;
      }
      v28 = 0;
      v18 = *(__int64 (__fastcall **)(__int64, LPVOID, struct INotificationHandler **))(*(_QWORD *)v31 + 192LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
      v19 = v18(v17, pv, &v28);
      v15 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4EE,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\notificationavailablework.cpp",
          (const char *)(unsigned int)v19,
          v25);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
        goto LABEL_18;
      }
      v20 = (CtaManager **)*((_QWORD *)this + 23);
      PackageFullName = (WpnDatabaseHelpers *)NotificationDeliveryTransaction::get_PackageFullName(*((NotificationDeliveryTransaction **)this + 22));
      v22 = NotificationPlatform::CheckNotificationHandlerSettingsEnabled(v20, v28, PackageFullName, a3, a4, a6, a5);
      v11 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4F6,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\notificationavailablework.cpp",
          (const char *)(unsigned int)v22,
          v26);
        v23 = v28;
        if ( v28 )
        {
          v28 = 0;
          (*(void (__fastcall **)(struct INotificationHandler *))(*(_QWORD *)v23 + 16LL))(v23);
        }
        v24 = v31;
        if ( v31 )
        {
          v31 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        }
        if ( v29[0] )
          CoTaskMemFree(v29[0]);
        goto LABEL_3;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v29);
    v13 = pv;
  }
  if ( v13 )
    CoTaskMemFree(v13);
  return 0;
}

```

## disassembly

```asm
0x18007ed94  push    rbp
0x18007ed96  push    rbx
0x18007ed97  push    rsi
0x18007ed98  push    rdi
0x18007ed99  push    r14
0x18007ed9b  push    r15
0x18007ed9d  mov     rbp, rsp
0x18007eda0  sub     rsp, 68h
0x18007eda4  mov     r14b, r9b
0x18007eda7  mov     r15, r8
0x18007edaa  mov     rdi, rdx
0x18007edad  mov     rsi, rcx
0x18007edb0  mov     [rbp+pv], 0
0x18007edb8  mov     rax, [rdx]
0x18007edbb  lea     rdx, [rbp+pv]
0x18007edbf  mov     rcx, rdi
0x18007edc2  mov     rax, [rax+28h]
0x18007edc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007edcb  mov     ebx, eax
0x18007edcd  test    eax, eax
0x18007edcf  jns     short loc_18007EE00
0x18007edd1  mov     rcx, [rbp+30h]; this
0x18007edd5  mov     r9d, eax; char *
0x18007edd8  lea     r8, aOnecoreuapBase_80; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18007eddf  mov     edx, 4E0h; void *
0x18007ede4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ede9  nop
0x18007edea  mov     rcx, [rbp+pv]; pv
0x18007edee  test    rcx, rcx
0x18007edf1  jz      short loc_18007EDF9
0x18007edf3  call    cs:__imp_CoTaskMemFree
0x18007edf9  mov     eax, ebx
0x18007edfb  jmp     loc_18007F042
0x18007ee00  mov     rcx, [rbp+pv]
0x18007ee04  test    rcx, rcx
0x18007ee07  jz      loc_18007F035
0x18007ee0d  xor     eax, eax
0x18007ee0f  cmp     ax, [rcx]
0x18007ee12  jz      loc_18007F035
0x18007ee18  mov     [rbp+var_18], rax
0x18007ee1c  mov     rax, [rdi]
0x18007ee1f  lea     rdx, [rbp+var_18]
0x18007ee23  mov     rcx, rdi
0x18007ee26  mov     rax, [rax+18h]
0x18007ee2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ee2f  mov     edi, eax
0x18007ee31  test    eax, eax
0x18007ee33  jns     short loc_18007EE52
0x18007ee35  mov     rcx, [rbp+30h]; this
0x18007ee39  mov     r9d, eax; char *
0x18007ee3c  lea     r8, aOnecoreuapBase_80; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18007ee43  mov     edx, 4E5h; void *
0x18007ee48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ee4d  jmp     loc_18007EF4B
0x18007ee52  mov     rdx, [rbp+var_18]
0x18007ee56  mov     rcx, [rbp+pv]
0x18007ee5a  call    cs:__imp__o__wcsicmp
0x18007ee60  test    eax, eax
0x18007ee62  jz      loc_18007F028
0x18007ee68  mov     [rbp+arg_8], 0
0x18007ee70  mov     rbx, [rsi+0B8h]
0x18007ee77  lea     rcx, [rbp+arg_8]
0x18007ee7b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007ee80  nop
0x18007ee81  mov     rcx, [rbx+90h]
0x18007ee88  mov     rax, [rcx]
0x18007ee8b  lea     r8, [rbp+arg_8]
0x18007ee8f  lea     rdx, _GUID_145e48ec_626a_4302_9000_36e8172c6d29
0x18007ee96  mov     rax, [rax]
0x18007ee99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ee9e  mov     edi, eax
0x18007eea0  mov     rbx, [rbp+arg_8]
0x18007eea4  test    eax, eax
0x18007eea6  js      short loc_18007EED0
0x18007eea8  test    rbx, rbx
0x18007eeab  jnz     short loc_18007EECC
0x18007eead  mov     rcx, [rbp+30h]; this
0x18007eeb1  mov     edi, 803E0105h
0x18007eeb6  mov     r9d, edi; char *
0x18007eeb9  lea     r8, aOnecoreuapBase_161; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18007eec0  mov     edx, 400h; void *
0x18007eec5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007eeca  jmp     short loc_18007EED0
0x18007eecc  test    eax, eax
0x18007eece  jns     short loc_18007EEEA
0x18007eed0  mov     rcx, [rbp+30h]; this
0x18007eed4  mov     r9d, edi; char *
0x18007eed7  lea     r8, aOnecoreuapBase_80; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18007eede  mov     edx, 4EBh; void *
0x18007eee3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007eee8  jmp     short loc_18007EF41
0x18007eeea  mov     [rbp+var_20], 0
0x18007eef2  mov     rax, [rbx]
0x18007eef5  mov     rdi, [rax+0C0h]
0x18007eefc  lea     rcx, [rbp+var_20]
0x18007ef00  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007ef05  lea     r8, [rbp+var_20]
0x18007ef09  mov     rdx, [rbp+pv]
0x18007ef0d  mov     rcx, rbx
0x18007ef10  mov     rax, rdi
0x18007ef13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ef18  mov     edi, eax
0x18007ef1a  test    eax, eax
0x18007ef1c  jns     short loc_18007EF65
0x18007ef1e  mov     rcx, [rbp+30h]; this
0x18007ef22  mov     r9d, eax; char *
0x18007ef25  lea     r8, aOnecoreuapBase_80; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18007ef2c  mov     edx, 4EEh; void *
0x18007ef31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ef36  nop
0x18007ef37  lea     rcx, [rbp+var_20]
0x18007ef3b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007ef40  nop
0x18007ef41  lea     rcx, [rbp+arg_8]
0x18007ef45  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007ef4a  nop
0x18007ef4b  lea     rcx, [rbp+var_18]
0x18007ef4f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007ef54  nop
0x18007ef55  lea     rcx, [rbp+pv]
0x18007ef59  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007ef5e  mov     eax, edi
0x18007ef60  jmp     loc_18007F042
0x18007ef65  mov     rbx, [rsi+0B8h]
0x18007ef6c  mov     rcx, [rsi+0B0h]; this
0x18007ef73  call    ?get_PackageFullName@NotificationDeliveryTransaction@@QEAAPEBGXZ; NotificationDeliveryTransaction::get_PackageFullName(void)
0x18007ef78  mov     r8, [rbp+arg_20]
0x18007ef7c  mov     [rsp+68h+var_38], r8; enum PolicyLevel *
0x18007ef81  mov     r8, [rbp+arg_28]
0x18007ef85  mov     [rsp+68h+var_40], r8; enum NOTIFICATION_POLICY_REASON *
0x18007ef8a  mov     [rsp+68h+var_48], r14b; int
0x18007ef8f  mov     r9, r15; unsigned __int16 *
0x18007ef92  mov     r8, rax; unsigned __int16 *
0x18007ef95  mov     rdx, [rbp+var_20]; struct INotificationHandler *
0x18007ef99  mov     rcx, rbx; this
0x18007ef9c  call    ?CheckNotificationHandlerSettingsEnabled@NotificationPlatform@@QEAAJPEAUINotificationHandler@@PEBG1_NPEAW4NOTIFICATION_POLICY_REASON@@PEAW4PolicyLevel@@@Z; NotificationPlatform::CheckNotificationHandlerSettingsEnabled(INotificationHandler *,ushort const *,ushort const *,bool,NOTIFICATION_POLICY_REASON *,PolicyLevel *)
0x18007efa1  mov     ebx, eax
0x18007efa3  test    eax, eax
0x18007efa5  jns     short loc_18007F014
0x18007efa7  mov     rcx, [rbp+30h]; this
0x18007efab  mov     r9d, eax; char *
0x18007efae  lea     r8, aOnecoreuapBase_80; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18007efb5  mov     edx, 4F6h; void *
0x18007efba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007efbf  nop
0x18007efc0  mov     rcx, [rbp+var_20]
0x18007efc4  test    rcx, rcx
0x18007efc7  jz      short loc_18007EFDE
0x18007efc9  mov     [rbp+var_20], 0
0x18007efd1  mov     rax, [rcx]
0x18007efd4  mov     rax, [rax+10h]
0x18007efd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007efdd  nop
0x18007efde  mov     rcx, [rbp+arg_8]
0x18007efe2  test    rcx, rcx
0x18007efe5  jz      short loc_18007EFFC
0x18007efe7  mov     [rbp+arg_8], 0
0x18007efef  mov     rax, [rcx]
0x18007eff2  mov     rax, [rax+10h]
0x18007eff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007effb  nop
0x18007effc  mov     rcx, [rbp+var_18]; pv
0x18007f000  test    rcx, rcx
0x18007f003  jz      loc_18007EDEA
0x18007f009  call    cs:__imp_CoTaskMemFree
0x18007f00f  jmp     loc_18007EDEA
0x18007f014  lea     rcx, [rbp+var_20]
0x18007f018  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007f01d  nop
0x18007f01e  lea     rcx, [rbp+arg_8]
0x18007f022  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007f027  nop
0x18007f028  lea     rcx, [rbp+var_18]
0x18007f02c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007f031  mov     rcx, [rbp+pv]; pv
0x18007f035  test    rcx, rcx
0x18007f038  jz      short loc_18007F040
0x18007f03a  call    cs:__imp_CoTaskMemFree
0x18007f040  xor     eax, eax
0x18007f042  add     rsp, 68h
0x18007f046  pop     r15
0x18007f048  pop     r14
0x18007f04a  pop     rdi
0x18007f04b  pop     rsi
0x18007f04c  pop     rbx
0x18007f04d  pop     rbp
0x18007f04e  retn
```
