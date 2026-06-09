# RadioManager::Initialize(void)

- ea: `0x18001eea8`
- end: `0x18001f083`
- name: `?Initialize@RadioManager@@QEAAJXZ`
- size: `475`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *pv)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180002770`

## callees

- `0x1800042b0`
- `0x180006a0c`
- `0x1800089d0`
- `0x180009184`
- `0x18000a6a0`
- `0x18000b744`
- `0x18000c010`
- `0x18000c104`
- `0x18000c2a4`
- `0x18000d2a0`
- `0x18001eea8`
- `0x18002056c`
- `0x180020940`
- `0x180022c54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001eede`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001eede`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef1c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001ef00`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001ef00`

## string_xrefs

- `0x18001ef40`: `CreateThreadpoolTimer failed`

## pseudocode

```c
__int64 __fastcall RadioManager::Initialize(struct _RTL_CRITICAL_SECTION *pv)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  PTP_TIMER ThreadpoolTimer; // rax
  signed int v4; // ebx
  signed int LastError; // eax
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  __int64 PersistentRegPathRMRoot; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  wil *v12; // rcx
  signed int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  signed int v17; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v18; // [rsp+38h] [rbp-D0h] BYREF
  const char *v19; // [rsp+40h] [rbp-C8h] BYREF
  const char *v20; // [rsp+48h] [rbp-C0h] BYREF
  struct _RTL_CRITICAL_SECTION *v21; // [rsp+50h] [rbp-B8h]
  __int64 v22; // [rsp+58h] [rbp-B0h] BYREF
  __m128i si128; // [rsp+68h] [rbp-A0h]
  char v24[8]; // [rsp+78h] [rbp-90h] BYREF
  _QWORD v25[14]; // [rsp+80h] [rbp-88h] BYREF
  struct _RTL_CRITICAL_SECTION *v26; // [rsp+F0h] [rbp-18h] BYREF

  v1 = pv;
  v21 = pv;
  v2 = pv + 6;
  EnterCriticalSection(pv + 6);
  v26 = v2;
  ThreadpoolTimer = CreateThreadpoolTimer(SetSystemRadioStateTimerCallback, v1, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    &v1[10].OwningThread,
    ThreadpoolTimer);
  if ( v1[10].OwningThread )
  {
    v4 = 0;
LABEL_21:
    try
    {
      RadioManager::_CreateAllRadioManagers((RadioManager *)v1);
      v25[0] = off_180029B68;
      v25[1] = v1;
      v25[13] = v25;
      PersistentRegPathRMRoot = RMAPI::GetPersistentRegPathRMRoot(&v22);
      v10 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(PersistentRegPathRMRoot);
      v18 = 0;
      wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create(
        &v18,
        v11,
        v10);
      if ( &v1[18] != (struct _RTL_CRITICAL_SECTION *)&v18 )
      {
        wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(
          &v1[18],
          v18);
        v18 = 0;
      }
      wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(&v18);
      if ( si128.m128i_i64[1] > 7uLL )
        std::_Deallocate<16>(v22, 2 * si128.m128i_i64[1] + 2);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v22) = 0;
      wistd::function<void (enum wil::RegistryChangeKind)>::~function<void (enum wil::RegistryChangeKind)>(v24);
    }
    catch ( ... )
    {
      v14 = wil::ResultFromCaughtException(v12);
      LODWORD(v19) = v14;
      if ( (unsigned int)dword_180037050 > 2 )
      {
        v17 = v14;
        v20 = "Exception thrown when creating all MediaRadioManagers";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v14,
          (unsigned int)byte_1800300BD,
          v15,
          v16,
          (__int64)&v20,
          (__int64)&v17);
      }
      v4 = (int)v19;
      v1 = v21;
      goto LABEL_14;
    }
    goto LABEL_14;
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( (unsigned int)dword_180037050 > 2 )
  {
    v17 = v4;
    v19 = "CreateThreadpoolTimer failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v6,
      (unsigned int)byte_1800300FB,
      v7,
      v8,
      (__int64)&v19,
      (__int64)&v17);
  }
  if ( v4 >= 0 )
    goto LABEL_21;
LABEL_14:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v26);
  if ( v4 < 0 )
    RadioManager::_Cleanup((RadioManager *)v1);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001eea8  mov     [rsp+arg_8], rbx
0x18001eead  mov     [rsp+arg_10], rsi
0x18001eeb2  push    rdi
0x18001eeb3  sub     rsp, 100h
0x18001eeba  mov     rax, cs:__security_cookie
0x18001eec1  xor     rax, rsp
0x18001eec4  mov     [rsp+108h+var_10], rax
0x18001eecc  mov     rsi, rcx
0x18001eecf  mov     [rsp+108h+var_B8], rcx
0x18001eed4  lea     rbx, [rcx+0F0h]
0x18001eedb  mov     rcx, rbx; lpCriticalSection
0x18001eede  call    cs:__imp_EnterCriticalSection
0x18001eee4  mov     [rsp+108h+var_18], rbx
0x18001eeec  lea     rbx, [rsi+1A0h]
0x18001eef3  xor     r8d, r8d; pcbe
0x18001eef6  mov     rdx, rsi; pv
0x18001eef9  lea     rcx, ?SetSystemRadioStateTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001ef00  call    cs:__imp_CreateThreadpoolTimer
0x18001ef06  mov     rdx, rax
0x18001ef09  mov     rcx, rbx
0x18001ef0c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001ef11  xor     edi, edi
0x18001ef13  cmp     [rbx], rdi
0x18001ef16  jz      short loc_18001EF1C
0x18001ef18  mov     ebx, edi
0x18001ef1a  jmp     short loc_18001EF74
0x18001ef1c  call    cs:__imp_GetLastError
0x18001ef22  mov     ebx, eax
0x18001ef24  test    eax, eax
0x18001ef26  jle     short loc_18001EF31
0x18001ef28  movzx   ebx, ax
0x18001ef2b  or      ebx, 80070000h
0x18001ef31  mov     eax, cs:dword_180037050
0x18001ef37  cmp     eax, 2
0x18001ef3a  jbe     short loc_18001EF6C
0x18001ef3c  mov     [rsp+108h+var_D8], ebx
0x18001ef40  lea     rax, aCreatethreadpo_0; "CreateThreadpoolTimer failed"
0x18001ef47  mov     [rsp+108h+var_C8], rax
0x18001ef4c  lea     rax, [rsp+108h+var_D8]
0x18001ef51  mov     [rsp+108h+var_E0], rax
0x18001ef56  lea     rax, [rsp+108h+var_C8]
0x18001ef5b  mov     [rsp+108h+var_E8], rax
0x18001ef60  lea     rdx, byte_1800300FB
0x18001ef67  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001ef6c  test    ebx, ebx
0x18001ef6e  js      loc_18001F043
0x18001ef74  mov     rcx, rsi; this
0x18001ef77  call    ?_CreateAllRadioManagers@RadioManager@@AEAAXXZ; RadioManager::_CreateAllRadioManagers(void)
0x18001ef7c  lea     rax, off_180029B68
0x18001ef83  mov     [rsp+108h+var_88], rax
0x18001ef8b  mov     [rsp+108h+var_80], rsi
0x18001ef93  lea     rax, [rsp+108h+var_88]
0x18001ef9b  mov     [rsp+108h+var_20], rax
0x18001efa3  lea     rcx, [rsp+108h+var_B0]
0x18001efa8  call    ?GetPersistentRegPathRMRoot@RMAPI@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; RMAPI::GetPersistentRegPathRMRoot(void)
0x18001efad  mov     rcx, rax
0x18001efb0  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001efb5  nop
0x18001efb6  mov     [rsp+108h+var_D0], rdi
0x18001efbb  lea     rcx, [rsp+108h+var_90]
0x18001efc0  mov     [rsp+108h+var_E8], rcx
0x18001efc5  mov     r8, rax
0x18001efc8  lea     rcx, [rsp+108h+var_D0]
0x18001efcd  call    ?create@?$registry_watcher_t@V?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJPEAUHKEY__@@PEB_W_N$$QEAV?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@@Z; wil::registry_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>,wil::err_returncode_policy>::create(HKEY__ *,wchar_t const *,bool,wistd::function<void (wil::RegistryChangeKind)> &&)
0x18001efd2  nop
0x18001efd3  lea     rcx, [rsi+2D0h]
0x18001efda  lea     rax, [rsp+108h+var_D0]
0x18001efdf  cmp     rcx, rax
0x18001efe2  jz      short loc_18001EFF3
0x18001efe4  mov     rdx, [rsp+108h+var_D0]
0x18001efe9  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x18001efee  mov     [rsp+108h+var_D0], rdi
0x18001eff3  lea     rcx, [rsp+108h+var_D0]
0x18001eff8  call    ??1?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>(void)
0x18001effd  mov     rdx, [rsp+108h+var_98]
0x18001f002  cmp     rdx, 7
0x18001f006  jbe     short loc_18001F01A
0x18001f008  lea     rdx, ds:2[rdx*2]
0x18001f010  mov     rcx, [rsp+108h+var_B0]
0x18001f015  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001f01a  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18001f022  movdqu  xmmword ptr [rsp+68h], xmm0
0x18001f028  mov     word ptr [rsp+108h+var_B0], di
0x18001f02d  lea     rcx, [rsp+108h+var_90]
0x18001f032  call    ??1?$function@$$A6AXW4RegistryChangeKind@wil@@@Z@wistd@@QEAA@XZ; wistd::function<void (wil::RegistryChangeKind)>::~function<void (wil::RegistryChangeKind)>(void)
0x18001f037  nop
0x18001f038  jmp     short loc_18001F043
0x18001f03a  mov     ebx, dword ptr [rsp+108h+var_C8]
0x18001f03e  mov     rsi, [rsp+108h+var_B8]
0x18001f043  lea     rcx, [rsp+108h+var_18]
0x18001f04b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001f050  test    ebx, ebx
0x18001f052  jns     short loc_18001F05C
0x18001f054  mov     rcx, rsi; this
0x18001f057  call    ?_Cleanup@RadioManager@@AEAAXXZ; RadioManager::_Cleanup(void)
0x18001f05c  mov     eax, ebx
0x18001f05e  mov     rcx, [rsp+108h+var_10]
0x18001f066  xor     rcx, rsp; StackCookie
0x18001f069  call    __security_check_cookie
0x18001f06e  lea     r11, [rsp+108h+var_8]
0x18001f076  mov     rbx, [r11+18h]
0x18001f07a  mov     rsi, [r11+20h]
0x18001f07e  mov     rsp, r11
0x18001f081  pop     rdi
0x18001f082  retn
```
