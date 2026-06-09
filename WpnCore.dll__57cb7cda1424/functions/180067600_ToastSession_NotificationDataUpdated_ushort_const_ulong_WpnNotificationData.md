# ToastSession::NotificationDataUpdated(ushort const *,ulong,WpnNotificationData *)

- ea: `0x180067600`
- end: `0x180067cd3`
- name: `?NotificationDataUpdated@ToastSession@@UEAAJPEBGKPEAVWpnNotificationData@@@Z`
- size: `1747`
- prototype: `int(ToastSession *__hidden this, const unsigned __int16 *, unsigned int, struct WpnNotificationData *)`
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180004e38`
- `0x18000522c`
- `0x180011618`
- `0x180013360`
- `0x18001bf30`
- `0x180029b44`
- `0x18002fae0`
- `0x180049644`
- `0x1800542a8`
- `0x180067600`
- `0x180067cdc`
- `0x180067d20`
- `0x180067d58`
- `0x180067de0`
- `0x180067e28`
- `0x180094814`
- `0x180094854`
- `0x18009487c`
- `0x1800a1f10`
- `0x1800a23b4`
- `0x1800bc54d`
- `0x180104628`
- `0x180104a30`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006763e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006763e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800676e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067c50`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800676e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180067c50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800678f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800678f7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800677b7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180067859`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800677b7`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180067859`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
__int64 __fastcall ToastSession::NotificationDataUpdated(
        ToastSession *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        struct WpnNotificationData *a4)
{
  ToastSession *v5; // r12
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  __int64 v7; // r15
  __int64 (__fastcall *v8)(__int64, _QWORD, GUID *, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)); // rdi
  int v9; // eax
  unsigned int v10; // edi
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v13)(_QWORD, GUID *, __int64 *); // rdi
  int v14; // eax
  unsigned int v15; // ebx
  unsigned __int64 count; // rdi
  signed __int64 v17; // rbx
  size_t size_of; // rax
  char *v19; // r12
  unsigned __int64 v20; // rcx
  __int64 v21; // r8
  _QWORD *i; // rbx
  const unsigned __int16 *v23; // rcx
  int v24; // eax
  unsigned int v25; // esi
  __int64 v26; // rcx
  __int64 (__fastcall ***v27)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v28; // r8
  const unsigned __int16 *v29; // rcx
  int v30; // eax
  unsigned int v31; // edi
  LPVOID v32; // rdi
  unsigned __int16 *v33; // rsi
  unsigned int v34; // eax
  int v35; // [rsp+20h] [rbp-D8h]
  int v36; // [rsp+20h] [rbp-D8h]
  LPVOID pv; // [rsp+40h] [rbp-B8h] BYREF
  __int64 v38; // [rsp+48h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v39)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-A8h] BYREF
  void *Src[2]; // [rsp+58h] [rbp-A0h] BYREF
  char *v41; // [rsp+68h] [rbp-90h]
  __int128 v42; // [rsp+70h] [rbp-88h] BYREF
  __int64 v43; // [rsp+80h] [rbp-78h]
  unsigned __int16 *v44; // [rsp+88h] [rbp-70h] BYREF
  _QWORD *v45; // [rsp+90h] [rbp-68h] BYREF
  _QWORD v46[2]; // [rsp+98h] [rbp-60h] BYREF
  _QWORD v47[10]; // [rsp+A8h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v5 = this;
  v39 = 0;
  v38 = 0;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  pv = v6;
  if ( *((_DWORD *)v5 + 3) && (v7 = *((_QWORD *)v5 + 3)) != 0 )
  {
    v8 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)))(*(_QWORD *)v7 + 40LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
    v9 = v8(
           v7,
           *((unsigned int *)v5 + 3),
           &GUID_904a654e_bee8_4654_bbba_e78766776239,
           (__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))&v39);
    v10 = v9;
    if ( v9 >= 0 )
    {
      if ( v6 )
        LeaveCriticalSection(v6);
      v12 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v39;
      v13 = **v39;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
      v14 = v13(v12, &GUID_2c3dc443_633b_4c3d_b456_6dd36c6d223d, &v38);
      v15 = v14;
      if ( v14 >= 0 )
      {
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<TileSession>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<TileSession>>>>>>>(&v42);
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<TileSession>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,std::shared_ptr<TileSession>>>>>>>(Src);
        if ( a4 && WpnNotificationData::get_count(a4) )
        {
          count = WpnNotificationData::get_count(a4);
          if ( count > (v41 - (char *)Src[0]) >> 4 )
          {
            if ( count > 0xFFFFFFFFFFFFFFFLL )
              std::_Xlength_error("vector too long");
            v17 = (char *)Src[1] - (char *)Src[0];
            size_of = std::_Get_size_of_n<16>(count);
            v19 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
            memmove_0(v19, Src[0], (char *)Src[1] - (char *)Src[0]);
            if ( Src[0] )
              std::_Deallocate<16>(Src[0], (v41 - (char *)Src[0]) & 0xFFFFFFFFFFFFFFF0uLL);
            Src[0] = v19;
            Src[1] = &v19[v17 & 0xFFFFFFFFFFFFFFF0uLL];
            v41 = &v19[16 * count];
          }
          v20 = WpnNotificationData::get_count(a4);
          pv = (LPVOID)v20;
          if ( v20 > (v43 - (__int64)v42) >> 4 )
          {
            if ( v20 > 0xFFFFFFFFFFFFFFFLL )
              std::_Xlength_error("vector too long");
            std::vector<std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>::_Reallocate<0>(
              &v42,
              &pv);
          }
          WpnNotificationData::begin(a4, &pv);
          WpnNotificationData::end(a4, &v45);
          for ( i = pv; ; i = (_QWORD *)*i )
          {
            if ( i == v45 )
            {
              v5 = this;
              goto LABEL_48;
            }
            v44 = 0;
            pv = 0;
            if ( i[5] <= 7u )
              v23 = (const unsigned __int16 *)(i + 2);
            else
              v23 = (const unsigned __int16 *)i[2];
            v24 = WpnCoTaskStrCpy(v23, (unsigned __int16 **)&pv, v21);
            v25 = v24;
            if ( v24 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1B3,
                (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
                (const char *)(unsigned int)v24,
                v35);
              if ( pv )
                CoTaskMemFree(pv);
              if ( Src[0] )
              {
                std::_Deallocate<16>(Src[0], (v41 - (char *)Src[0]) & 0xFFFFFFFFFFFFFFF0uLL);
                *(_OWORD *)Src = 0;
                v41 = 0;
              }
              if ( (_QWORD)v42 )
              {
                std::_Destroy_range<std::allocator<std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>>(
                  v42,
                  *((__int64 *)&v42 + 1));
                std::_Deallocate<16>((void *)v42, (v43 - v42) & 0xFFFFFFFFFFFFFFF0uLL);
                v42 = 0;
                v43 = 0;
              }
              v26 = v38;
              if ( v38 )
              {
                v38 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
              }
              v27 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v39;
              if ( v39 )
              {
                v39 = 0;
                ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v27)[2])(v27);
              }
              return v25;
            }
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &v44,
              0);
            v29 = (const unsigned __int16 *)(i + 6);
            if ( i[9] > 7u )
              v29 = *(const unsigned __int16 **)v29;
            v30 = WpnCoTaskStrCpy(v29, &v44, v28);
            v31 = v30;
            if ( v30 < 0 )
              break;
            v32 = pv;
            v47[0] = pv;
            v33 = v44;
            v47[1] = v44;
            std::vector<_WPN_NOTIFICATION_METADATA_PAIR>::push_back(Src, v47);
            v46[0] = v32;
            pv = 0;
            v46[1] = v33;
            v44 = 0;
            std::vector<std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>::push_back(
              &v42,
              v46);
            std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(v46);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v44);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1B4,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
            (const char *)(unsigned int)v30,
            v35);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v44);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
          if ( Src[0] )
          {
            std::_Deallocate<16>(Src[0], (v41 - (char *)Src[0]) & 0xFFFFFFFFFFFFFFF0uLL);
            *(_OWORD *)Src = 0;
            v41 = 0;
          }
          if ( (_QWORD)v42 )
          {
            std::_Destroy_range<std::allocator<std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>>(
              v42,
              *((__int64 *)&v42 + 1));
            std::_Deallocate<16>((void *)v42, (v43 - v42) & 0xFFFFFFFFFFFFFFF0uLL);
            v42 = 0;
            v43 = 0;
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
          return v31;
        }
        else
        {
LABEL_48:
          CRPCTimeout::CRPCTimeout((CRPCTimeout *)v47, 0x2710u);
          v36 = ((char *)Src[1] - (char *)Src[0]) >> 4;
          v34 = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *, _QWORD))(*(_QWORD *)v38 + 24LL))(
                  v38,
                  *((unsigned int *)v5 + 2),
                  a2,
                  a3);
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0x1C5,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
            (const char *)v34,
            v36);
          CBaseRPCTimeout::Disarm((CBaseRPCTimeout *)v47);
          if ( Src[0] )
          {
            std::_Deallocate<16>(Src[0], (v41 - (char *)Src[0]) & 0xFFFFFFFFFFFFFFF0uLL);
            *(_OWORD *)Src = 0;
            v41 = 0;
          }
          if ( (_QWORD)v42 )
          {
            std::_Destroy_range<std::allocator<std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>>(
              v42,
              *((__int64 *)&v42 + 1));
            std::_Deallocate<16>((void *)v42, (v43 - v42) & 0xFFFFFFFFFFFFFFF0uLL);
            v42 = 0;
            v43 = 0;
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
          return 0;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A4,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
          (const char *)(unsigned int)v14,
          v35);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
        return v15;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A1,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
        (const char *)(unsigned int)v9,
        v35);
      Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&pv);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
      return v10;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\ui\\toastsession.cpp",
      (const char *)0x80004005LL,
      v35);
    if ( v6 )
      LeaveCriticalSection(v6);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x180067600  mov     [rsp+arg_10], r8d
0x180067605  mov     [rsp+arg_8], rdx
0x18006760a  mov     [rsp+arg_0], rcx
0x18006760f  push    rbx
0x180067610  push    rsi
0x180067611  push    rdi
0x180067612  push    r12
0x180067614  push    r13
0x180067616  push    r14
0x180067618  push    r15
0x18006761a  sub     rsp, 0C0h
0x180067621  mov     rsi, r9
0x180067624  mov     r12, rcx
0x180067627  xor     r14d, r14d
0x18006762a  mov     r13d, r14d
0x18006762d  mov     [rsp+0F8h+var_A8], r14
0x180067632  mov     [rsp+0F8h+var_B0], r14
0x180067637  lea     rbx, [rcx+58h]
0x18006763b  mov     rcx, rbx; lpCriticalSection
0x18006763e  call    cs:__imp_EnterCriticalSection
0x180067644  mov     [rsp+0F8h+pv], rbx
0x180067649  cmp     [r12+0Ch], r14d
0x18006764e  jz      loc_180067C26
0x180067654  mov     r15, [r12+18h]
0x180067659  test    r15, r15
0x18006765c  jz      loc_180067C26
0x180067662  mov     rax, [r15]
0x180067665  mov     rdi, [rax+28h]
0x180067669  lea     rcx, [rsp+0F8h+var_A8]
0x18006766e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180067673  lea     r9, [rsp+0F8h+var_A8]
0x180067678  lea     r8, _GUID_904a654e_bee8_4654_bbba_e78766776239
0x18006767f  mov     edx, [r12+0Ch]
0x180067684  mov     rcx, r15
0x180067687  mov     rax, rdi
0x18006768a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006768f  mov     edi, eax
0x180067691  test    eax, eax
0x180067693  jns     short loc_1800676D9
0x180067695  mov     rcx, [rsp+0F8h]; this
0x18006769d  mov     r9d, eax; char *
0x1800676a0  lea     r8, aOnecoreuapBase_46; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800676a7  mov     edx, 1A1h; void *
0x1800676ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800676b1  nop
0x1800676b2  lea     rcx, [rsp+0F8h+pv]; this
0x1800676b7  call    ??1SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(void)
0x1800676bc  nop
0x1800676bd  lea     rcx, [rsp+0F8h+var_B0]
0x1800676c2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800676c7  nop
0x1800676c8  lea     rcx, [rsp+0F8h+var_A8]
0x1800676cd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800676d2  mov     eax, edi
0x1800676d4  jmp     loc_180067CBF
0x1800676d9  test    rbx, rbx
0x1800676dc  jz      short loc_1800676E8
0x1800676de  mov     rcx, rbx; lpCriticalSection
0x1800676e1  call    cs:__imp_LeaveCriticalSection
0x1800676e7  nop
0x1800676e8  mov     rbx, [rsp+0F8h+var_A8]
0x1800676ed  mov     rax, [rbx]
0x1800676f0  mov     rdi, [rax]
0x1800676f3  lea     rcx, [rsp+0F8h+var_B0]
0x1800676f8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800676fd  lea     r8, [rsp+0F8h+var_B0]
0x180067702  lea     rdx, _GUID_2c3dc443_633b_4c3d_b456_6dd36c6d223d
0x180067709  mov     rcx, rbx
0x18006770c  mov     rax, rdi
0x18006770f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067714  mov     ebx, eax
0x180067716  test    eax, eax
0x180067718  jns     short loc_180067753
0x18006771a  mov     rcx, [rsp+0F8h]; this
0x180067722  mov     r9d, eax; char *
0x180067725  lea     r8, aOnecoreuapBase_46; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006772c  mov     edx, 1A4h; void *
0x180067731  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180067736  nop
0x180067737  lea     rcx, [rsp+0F8h+var_B0]
0x18006773c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180067741  nop
0x180067742  lea     rcx, [rsp+0F8h+var_A8]
0x180067747  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006774c  mov     eax, ebx
0x18006774e  jmp     loc_180067CBF
0x180067753  lea     rcx, [rsp+0F8h+var_88]
0x180067758  call    ??$?0AEBV?$allocator@U?$pair@$$CBKV?$shared_ptr@VTileSession@@@std@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@VTileSession@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBKV?$shared_ptr@VTileSession@@@std@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<TileSession>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<TileSession>>>>>>>(std::allocator<std::pair<ulong const,std::shared_ptr<TileSession>>> const &)
0x18006775d  nop
0x18006775e  lea     rcx, [rsp+0F8h+Src]
0x180067763  call    ??$?0AEBV?$allocator@U?$pair@$$CBKV?$shared_ptr@VTileSession@@@std@@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKV?$shared_ptr@VTileSession@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBKV?$shared_ptr@VTileSession@@@std@@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<TileSession>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,std::shared_ptr<TileSession>>>>>>>(std::allocator<std::pair<ulong const,std::shared_ptr<TileSession>>> const &)
0x180067768  nop
0x180067769  test    rsi, rsi
0x18006776c  jz      loc_180067B26
0x180067772  mov     rcx, rsi; this
0x180067775  call    ?get_count@WpnNotificationData@@QEAA_KXZ; WpnNotificationData::get_count(void)
0x18006777a  test    rax, rax
0x18006777d  jz      loc_180067B26
0x180067783  mov     rcx, rsi; this
0x180067786  call    ?get_count@WpnNotificationData@@QEAA_KXZ; WpnNotificationData::get_count(void)
0x18006778b  mov     rdi, rax
0x18006778e  mov     rax, [rsp+0F8h+var_90]
0x180067793  sub     rax, [rsp+0F8h+Src]
0x180067798  sar     rax, 4
0x18006779c  mov     r15, 0FFFFFFFFFFFFFFFh
0x1800677a6  cmp     rdi, rax
0x1800677a9  jbe     short loc_180067827
0x1800677ab  cmp     rdi, r15
0x1800677ae  jbe     short loc_1800677BD
0x1800677b0  lea     rcx, aVectorTooLong; "vector too long"
0x1800677b7  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800677bd  mov     rbx, [rsp+0F8h+Src+8]
0x1800677c2  sub     rbx, [rsp+0F8h+Src]
0x1800677c7  mov     rcx, rdi
0x1800677ca  call    ??$_Get_size_of_n@$0BA@@std@@YA_K_K@Z; std::_Get_size_of_n<16>(unsigned __int64)
0x1800677cf  mov     rcx, rax
0x1800677d2  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800677d7  mov     r12, rax
0x1800677da  mov     rdx, [rsp+0F8h+Src]; Src
0x1800677df  mov     r8, [rsp+0F8h+Src+8]
0x1800677e4  sub     r8, rdx; Size
0x1800677e7  mov     rcx, rax; void *
0x1800677ea  call    memmove_0
0x1800677ef  mov     rcx, [rsp+0F8h+Src]
0x1800677f4  test    rcx, rcx
0x1800677f7  jz      short loc_18006780A
0x1800677f9  mov     rdx, [rsp+0F8h+var_90]
0x1800677fe  sub     rdx, rcx
0x180067801  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180067805  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18006780a  mov     [rsp+0F8h+Src], r12
0x18006780f  and     rbx, 0FFFFFFFFFFFFFFF0h
0x180067813  add     rbx, r12
0x180067816  mov     [rsp+0F8h+Src+8], rbx
0x18006781b  shl     rdi, 4
0x18006781f  add     rdi, r12
0x180067822  mov     [rsp+0F8h+var_90], rdi
0x180067827  mov     rcx, rsi; this
0x18006782a  call    ?get_count@WpnNotificationData@@QEAA_KXZ; WpnNotificationData::get_count(void)
0x18006782f  mov     rcx, rax
0x180067832  mov     [rsp+0F8h+pv], rax
0x180067837  mov     rax, [rsp+0F8h+var_78]
0x18006783f  sub     rax, qword ptr [rsp+0F8h+var_88]
0x180067844  sar     rax, 4
0x180067848  cmp     rcx, rax
0x18006784b  jbe     short loc_18006786E
0x18006784d  cmp     rcx, r15
0x180067850  jbe     short loc_18006785F
0x180067852  lea     rcx, aVectorTooLong; "vector too long"
0x180067859  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18006785f  lea     rdx, [rsp+0F8h+pv]
0x180067864  lea     rcx, [rsp+0F8h+var_88]
0x180067869  call    ??$_Reallocate@$0A@@?$vector@U?$pair@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V12@@std@@V?$allocator@U?$pair@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V12@@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>::_Reallocate<0>(unsigned __int64 &)
0x18006786e  lea     rdx, [rsp+0F8h+pv]
0x180067873  mov     rcx, rsi
0x180067876  call    ?begin@WpnNotificationData@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@XZ; WpnNotificationData::begin(void)
0x18006787b  lea     rdx, [rsp+0F8h+var_68]
0x180067883  mov     rcx, rsi
0x180067886  call    ?end@WpnNotificationData@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@XZ; WpnNotificationData::end(void)
0x18006788b  mov     rbx, [rsp+0F8h+pv]
0x180067890  cmp     rbx, [rsp+0F8h+var_68]
0x180067898  jz      loc_180067B1E
0x18006789e  mov     [rsp+0F8h+var_70], r14
0x1800678a6  mov     [rsp+0F8h+pv], r14
0x1800678ab  cmp     qword ptr [rbx+28h], 7
0x1800678b0  jbe     short loc_1800678B8
0x1800678b2  mov     rcx, [rbx+10h]
0x1800678b6  jmp     short loc_1800678BC
0x1800678b8  lea     rcx, [rbx+10h]; unsigned __int16 *
0x1800678bc  lea     rdx, [rsp+0F8h+pv]; unsigned __int16 **
0x1800678c1  call    ?WpnCoTaskStrCpy@@YAJPEBGPEAPEAG@Z; WpnCoTaskStrCpy(ushort const *,ushort * *)
0x1800678c6  mov     esi, eax
0x1800678c8  test    eax, eax
0x1800678ca  jns     loc_1800679A4
0x1800678d0  mov     rcx, [rsp+0F8h]; this
0x1800678d8  mov     r9d, eax; char *
0x1800678db  lea     r8, aOnecoreuapBase_46; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800678e2  mov     edx, 1B3h; void *
0x1800678e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800678ec  nop
0x1800678ed  mov     rcx, [rsp+0F8h+pv]; pv
0x1800678f2  test    rcx, rcx
0x1800678f5  jz      short loc_1800678FE
0x1800678f7  call    cs:__imp_CoTaskMemFree
0x1800678fd  nop
0x1800678fe  mov     rcx, [rsp+0F8h+Src]
0x180067903  test    rcx, rcx
0x180067906  jz      short loc_180067927
0x180067908  mov     rdx, [rsp+0F8h+var_90]
0x18006790d  sub     rdx, rcx
0x180067910  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180067914  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180067919  xorps   xmm0, xmm0
0x18006791c  movdqu  xmmword ptr [rsp+0F8h+Src], xmm0
0x180067922  mov     [rsp+0F8h+var_90], r14
0x180067927  mov     rcx, qword ptr [rsp+0F8h+var_88]
0x18006792c  test    rcx, rcx
0x18006792f  jz      short loc_180067965
0x180067931  mov     rdx, qword ptr [rsp+0F8h+var_88+8]
0x180067936  call    ??$_Destroy_range@V?$allocator@U?$pair@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V12@@std@@@std@@@std@@YAXPEAU?$pair@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V12@@0@QEAU10@AEAV?$allocator@U?$pair@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V12@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>>(std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>> *,std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>> * const,std::allocator<std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>> &)
0x18006793b  mov     rcx, qword ptr [rsp+0F8h+var_88]
0x180067940  mov     rdx, [rsp+0F8h+var_78]
0x180067948  sub     rdx, rcx
0x18006794b  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18006794f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180067954  xorps   xmm0, xmm0
0x180067957  movdqu  [rsp+0F8h+var_88], xmm0
0x18006795d  mov     [rsp+0F8h+var_78], r14
0x180067965  mov     rcx, [rsp+0F8h+var_B0]
0x18006796a  test    rcx, rcx
0x18006796d  jz      short loc_180067981
0x18006796f  mov     [rsp+0F8h+var_B0], r14
0x180067974  mov     rax, [rcx]
0x180067977  mov     rax, [rax+10h]
0x18006797b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067980  nop
0x180067981  mov     rcx, [rsp+0F8h+var_A8]
0x180067986  test    rcx, rcx
0x180067989  jz      short loc_18006799D
0x18006798b  mov     [rsp+0F8h+var_A8], r14
0x180067990  mov     rax, [rcx]
0x180067993  mov     rax, [rax+10h]
0x180067997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006799c  nop
0x18006799d  mov     eax, esi
0x18006799f  jmp     loc_180067CBF
0x1800679a4  xor     edx, edx
0x1800679a6  lea     rcx, [rsp+0F8h+var_70]
0x1800679ae  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800679b3  lea     rcx, [rbx+30h]
0x1800679b7  cmp     qword ptr [rbx+48h], 7
0x1800679bc  jbe     short loc_1800679C1
0x1800679be  mov     rcx, [rcx]; unsigned __int16 *
0x1800679c1  lea     rdx, [rsp+0F8h+var_70]; unsigned __int16 **
0x1800679c9  call    ?WpnCoTaskStrCpy@@YAJPEBGPEAPEAG@Z; WpnCoTaskStrCpy(ushort const *,ushort * *)
0x1800679ce  mov     edi, eax
0x1800679d0  test    eax, eax
0x1800679d2  jns     loc_180067A91
0x1800679d8  mov     rcx, [rsp+0F8h]; this
0x1800679e0  mov     r9d, eax; char *
0x1800679e3  lea     r8, aOnecoreuapBase_46; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800679ea  mov     edx, 1B4h; void *
0x1800679ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800679f4  nop
0x1800679f5  lea     rcx, [rsp+0F8h+var_70]
0x1800679fd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180067a02  nop
0x180067a03  lea     rcx, [rsp+0F8h+pv]
0x180067a08  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180067a0d  nop
0x180067a0e  mov     rcx, [rsp+0F8h+Src]
0x180067a13  test    rcx, rcx
0x180067a16  jz      short loc_180067A37
0x180067a18  mov     rdx, [rsp+0F8h+var_90]
0x180067a1d  sub     rdx, rcx
0x180067a20  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180067a24  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180067a29  xorps   xmm0, xmm0
0x180067a2c  movdqu  xmmword ptr [rsp+0F8h+Src], xmm0
0x180067a32  mov     [rsp+0F8h+var_90], r14
0x180067a37  mov     rcx, qword ptr [rsp+0F8h+var_88]
0x180067a3c  test    rcx, rcx
0x180067a3f  jz      short loc_180067A75
0x180067a41  mov     rdx, qword ptr [rsp+0F8h+var_88+8]
0x180067a46  call    ??$_Destroy_range@V?$allocator@U?$pair@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V12@@std@@@std@@@std@@YAXPEAU?$pair@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V12@@0@QEAU10@AEAV?$allocator@U?$pair@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V12@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>>(std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>> *,std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>> * const,std::allocator<std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>> &)
0x180067a4b  mov     rcx, qword ptr [rsp+0F8h+var_88]
0x180067a50  mov     rdx, [rsp+0F8h+var_78]
0x180067a58  sub     rdx, rcx
0x180067a5b  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180067a5f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180067a64  xorps   xmm0, xmm0
0x180067a67  movdqu  [rsp+0F8h+var_88], xmm0
0x180067a6d  mov     [rsp+0F8h+var_78], r14
0x180067a75  lea     rcx, [rsp+0F8h+var_B0]
0x180067a7a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180067a7f  nop
0x180067a80  lea     rcx, [rsp+0F8h+var_A8]
0x180067a85  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180067a8a  mov     eax, edi
0x180067a8c  jmp     loc_180067CBF
0x180067a91  mov     rdi, [rsp+0F8h+pv]
0x180067a96  mov     [rsp+0F8h+var_50], rdi
0x180067a9e  mov     rsi, [rsp+0F8h+var_70]
0x180067aa6  mov     [rsp+0F8h+var_48], rsi
0x180067aae  lea     rdx, [rsp+0F8h+var_50]
0x180067ab6  lea     rcx, [rsp+0F8h+Src]
0x180067abb  call    ?push_back@?$vector@U_WPN_NOTIFICATION_METADATA_PAIR@@V?$allocator@U_WPN_NOTIFICATION_METADATA_PAIR@@@std@@@std@@QEAAX$$QEAU_WPN_NOTIFICATION_METADATA_PAIR@@@Z; std::vector<_WPN_NOTIFICATION_METADATA_PAIR>::push_back(_WPN_NOTIFICATION_METADATA_PAIR &&)
0x180067ac0  mov     [rsp+0F8h+var_60], rdi
0x180067ac8  mov     [rsp+0F8h+pv], r14
0x180067acd  mov     [rsp+0F8h+var_58], rsi
0x180067ad5  mov     [rsp+0F8h+var_70], r14
0x180067add  lea     rdx, [rsp+0F8h+var_60]
0x180067ae5  lea     rcx, [rsp+0F8h+var_88]
0x180067aea  call    ?push_back@?$vector@U?$pair@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V12@@std@@V?$allocator@U?$pair@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V12@@std@@@2@@std@@QEAAX$$QEAU?$pair@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V12@@2@@Z; std::vector<std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>::push_back(std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>> &&)
0x180067aef  nop
0x180067af0  lea     rcx, [rsp+0F8h+var_60]
0x180067af8  call    ??1?$pair@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V12@@std@@QEAA@XZ; std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180067afd  nop
0x180067afe  lea     rcx, [rsp+0F8h+var_70]
0x180067b06  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
  ... truncated ...
```
