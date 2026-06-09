# DriverRecoveryManager::StartProcessing(void)

- ea: `0x180029a60`
- end: `0x180029df5`
- name: `?StartProcessing@DriverRecoveryManager@@QEAAJXZ`
- size: `917`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002beb4`

## callees

- `0x18000fa64`
- `0x18000fa98`
- `0x1800112a4`
- `0x1800112c8`
- `0x18001370c`
- `0x180014740`
- `0x180015404`
- `0x180015474`
- `0x180015494`
- `0x1800195b4`
- `0x18001af70`
- `0x180021fac`
- `0x18002541c`
- `0x180028cc8`
- `0x180029020`
- `0x1800299a0`
- `0x180029a60`
- `0x18002a138`
- `0x18002a458`
- `0x18003a9ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180029a8b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180029a8b`
- `drvstore!DriverStoreClose` at `0x180029ae4`
- `drvstore!DriverStoreClose` at `0x180029ae4`
- `drvstore!DriverStoreOpenW` at `0x180029ac5`
- `drvstore!DriverStoreOpenW` at `0x180029ac5`

## string_xrefs

- `0x180029b1f`: `onecoreuap\base\devices\setup\dsm\service\driverrecovery.cpp`
- `0x180029b57`: `onecoreuap\base\devices\setup\dsm\service\driverrecovery.cpp`
- `0x180029db4`: `onecoreuap\base\devices\setup\dsm\service\driverrecovery.cpp`

## pseudocode

```c
__int64 __fastcall DriverRecoveryManager::StartProcessing(RTL_SRWLOCK *this)
{
  __int64 v3; // rdx
  __int64 Ptr; // rbx
  const char *v5; // r9
  PVOID v6; // rdi
  const char *v7; // r9
  int v8; // eax
  unsigned int v9; // ebx
  __int64 **v10; // rdi
  __int64 **i; // rbx
  void **v12; // rax
  void *v13; // rcx
  void *v14; // rdx
  std::_Ref_count_base *v15; // rcx
  __int64 **v16; // rdi
  __int64 **j; // rbx
  __int64 *v18; // r8
  volatile signed __int32 *v19; // rax
  volatile signed __int32 *v20; // r14
  PVOID v21; // rax
  volatile signed __int32 *v22; // rdx
  std::_Ref_count_base *v23; // rcx
  int v24; // eax
  _QWORD *v25; // r9
  _QWORD *v26; // r14
  __int64 *v27; // r15
  int v28; // eax
  _QWORD *v29; // rax
  int v30; // [rsp+20h] [rbp-C8h]
  RTL_SRWLOCK *v31; // [rsp+30h] [rbp-B8h] BYREF
  char v32[8]; // [rsp+38h] [rbp-B0h] BYREF
  std::_Ref_count_base *v33; // [rsp+40h] [rbp-A8h]
  char v34[8]; // [rsp+48h] [rbp-A0h] BYREF
  _QWORD v35[14]; // [rsp+50h] [rbp-98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  AcquireSRWLockExclusive(this);
  v31 = this;
  if ( LOBYTE(this[1].Ptr) )
  {
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v31);
    return 0;
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v31);
    Ptr = (__int64)this[2].Ptr;
    if ( Ptr )
      goto LABEL_58;
    Ptr = DriverStoreOpenW(0, 0, 0, 0);
    v6 = this[2].Ptr;
    if ( v6 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v31);
      DriverStoreClose(v6);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v31);
    }
    this[2].Ptr = (PVOID)Ptr;
    if ( Ptr )
    {
LABEL_58:
      if ( (unsigned int)DrvRecoveryEnumRecoveryIds(
                           Ptr,
                           v3,
                           lambda_52777bd2daf192c34b8319eac59de991_::_lambda_invoker_cdecl_,
                           this) )
      {
        if ( this[5].Ptr
          && (v8 = DriverRecoveryManager::_EnableOnRebootTask((DriverRecoveryManager *)this, 0), v9 = v8, v8 < 0) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x104,
            (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\driverrecovery.cpp",
            (const char *)(unsigned int)v8,
            v30);
          return v9;
        }
        else
        {
          v10 = (__int64 **)this[4].Ptr;
          for ( i = (__int64 **)*v10; i != v10; i = (__int64 **)*i )
          {
            v26 = i + 2;
            v27 = (__int64 *)(i + 6);
            v28 = DriverRecoveryRecord::PerformAction((DriverRecoveryRecord *)i[6]);
            if ( v28 >= 0 )
            {
              if ( *(_DWORD *)(*v27 + 40) == 6 )
              {
                LOBYTE(this[22].Ptr) = 1;
              }
              else if ( *(_DWORD *)(*v27 + 40) == 8 )
              {
                v29 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<DriverRecoveryRecord>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<DriverRecoveryRecord>>>,0>>::_Try_emplace<std::wstring const &,>(
                                  &this[11],
                                  v32,
                                  i + 2);
                std::shared_ptr<DriverRecoveryRecord>::operator=(*v29 + 48LL, i + 6);
              }
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                   && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              if ( (unsigned __int64)i[5] > 7 )
                v26 = (_QWORD *)*v26;
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                11,
                (unsigned int)WPP_ab30234a52263744e5d3d91a9e86c909_Traceguids,
                (_DWORD)v26,
                v28);
            }
          }
          if ( this[13].Ptr )
          {
            if ( !this[21].Ptr )
            {
              v35[0] = off_180046C48;
              v35[1] = this;
              v35[13] = v35;
              wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(
                &this[21],
                v34);
              wistd::function<void (_DRIVER_RECOVERY_CONTEXT const &)>::~function<void (_DRIVER_RECOVERY_CONTEXT const &)>(v34);
            }
            if ( !this[19].Ptr )
            {
              v31 = this;
              v12 = (void **)std::make_shared_std::function_void___cdecl_unsigned_short_const___bool____lambda_40cf73d3f1a58b91f93b64488f1182e5___(
                               v32,
                               &v31);
              v13 = *v12;
              v14 = v12[1];
              *v12 = 0;
              v12[1] = 0;
              this[19].Ptr = v13;
              v15 = (std::_Ref_count_base *)this[20].Ptr;
              this[20].Ptr = v14;
              if ( v15 )
                std::_Ref_count_base::_Decref(v15);
              if ( v33 )
                std::_Ref_count_base::_Decref(v33);
            }
            v16 = (__int64 **)this[12].Ptr;
            for ( j = (__int64 **)*v16; j != v16; j = (__int64 **)*j )
            {
              v18 = j[6];
              v19 = (volatile signed __int32 *)this[20].Ptr;
              if ( v19 )
                _InterlockedIncrement(v19 + 2);
              v20 = (volatile signed __int32 *)this[20].Ptr;
              if ( v20 )
              {
                v21 = this[19].Ptr;
                _InterlockedIncrement(v20 + 3);
                v22 = v20;
              }
              else
              {
                v22 = 0;
                v21 = 0;
              }
              v18[16] = (__int64)v21;
              v23 = (std::_Ref_count_base *)v18[17];
              v18[17] = (__int64)v22;
              if ( v23 )
                std::_Ref_count_base::_Decwref(v23);
              if ( v20 )
                std::_Ref_count_base::_Decref((std::_Ref_count_base *)v20);
              v24 = DriverRecoveryRecord::PostJobsForBlockingDevices((DriverRecoveryRecord *)j[6]);
              if ( v24 < 0
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v25 = j + 2;
                if ( (unsigned __int64)j[5] > 7 )
                  v25 = (_QWORD *)*v25;
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  13,
                  (unsigned int)WPP_ab30234a52263744e5d3d91a9e86c909_Traceguids,
                  (_DWORD)v25,
                  v24);
              }
            }
          }
          else
          {
            DriverRecoveryManager::_FinishProcessing((DriverRecoveryManager *)this);
          }
          return 0;
        }
      }
      else
      {
        return wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0xFF,
                 (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\driverrecovery.cpp",
                 v7);
      }
    }
    else
    {
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0xD9,
               (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\driverrecovery.cpp",
               v5);
    }
  }
}

```

## disassembly

```asm
0x180029a60  mov     [rsp+arg_8], rbx
0x180029a65  mov     [rsp+arg_10], rsi
0x180029a6a  push    rdi
0x180029a6b  push    r14
0x180029a6d  push    r15
0x180029a6f  sub     rsp, 0D0h
0x180029a76  mov     rax, cs:__security_cookie
0x180029a7d  xor     rax, rsp
0x180029a80  mov     [rsp+0E8h+var_28], rax
0x180029a88  mov     rsi, rcx
0x180029a8b  call    cs:__imp_AcquireSRWLockExclusive
0x180029a91  mov     [rsp+0E8h+var_B8], rsi
0x180029a96  lea     rcx, [rsp+0E8h+var_B8]
0x180029a9b  cmp     byte ptr [rsi+8], 0
0x180029a9f  jz      short loc_180029AAD
0x180029aa1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180029aa6  xor     eax, eax
0x180029aa8  jmp     loc_180029DCB
0x180029aad  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180029ab2  mov     rbx, [rsi+10h]
0x180029ab6  test    rbx, rbx
0x180029ab9  jnz     short loc_180029B01
0x180029abb  xor     r9d, r9d
0x180029abe  xor     r8d, r8d
0x180029ac1  xor     edx, edx
0x180029ac3  xor     ecx, ecx
0x180029ac5  call    cs:__imp_DriverStoreOpenW
0x180029acb  mov     rbx, rax
0x180029ace  mov     rdi, [rsi+10h]
0x180029ad2  test    rdi, rdi
0x180029ad5  jz      short loc_180029AF4
0x180029ad7  lea     rcx, [rsp+0E8h+var_B8]; this
0x180029adc  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180029ae1  mov     rcx, rdi
0x180029ae4  call    cs:__imp_DriverStoreClose
0x180029aea  lea     rcx, [rsp+0E8h+var_B8]; this
0x180029aef  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180029af4  mov     [rsi+10h], rbx
0x180029af8  test    rbx, rbx
0x180029afb  jz      loc_180029DAC
0x180029b01  mov     r9, rsi
0x180029b04  lea     r8, _lambda_52777bd2daf192c34b8319eac59de991____lambda_invoker_cdecl_
0x180029b0b  mov     rcx, rbx
0x180029b0e  call    ?DrvRecoveryEnumRecoveryIds@@YAHPEAUHDRIVERSTORE__@@W4_DRVRECOVERY_ENUM_RECOVERY_ID_FLAG@@P6AH0PEBGW4_DRVRECOVERY_RECOVERY_ID_FLAG@@_J@Z4@Z; DrvRecoveryEnumRecoveryIds(HDRIVERSTORE__ *,_DRVRECOVERY_ENUM_RECOVERY_ID_FLAG,int (*)(HDRIVERSTORE__ *,ushort const *,_DRVRECOVERY_RECOVERY_ID_FLAG,__int64),__int64)
0x180029b13  test    eax, eax
0x180029b15  jnz     short loc_180029B35
0x180029b17  mov     rcx, [rsp+0E8h]; this
0x180029b1f  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180029b26  mov     edx, 0FFh; void *
0x180029b2b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180029b30  jmp     loc_180029DCB
0x180029b35  cmp     qword ptr [rsi+28h], 0
0x180029b3a  jz      short loc_180029B6F
0x180029b3c  xor     edx, edx; bool
0x180029b3e  mov     rcx, rsi; this
0x180029b41  call    ?_EnableOnRebootTask@DriverRecoveryManager@@AEAAJ_N@Z; DriverRecoveryManager::_EnableOnRebootTask(bool)
0x180029b46  mov     ebx, eax
0x180029b48  test    eax, eax
0x180029b4a  jns     short loc_180029B6F
0x180029b4c  mov     rcx, [rsp+0E8h]; this
0x180029b54  mov     r9d, eax; char *
0x180029b57  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180029b5e  mov     edx, 104h; void *
0x180029b63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029b68  mov     eax, ebx
0x180029b6a  jmp     loc_180029DCB
0x180029b6f  mov     rdi, [rsi+20h]
0x180029b73  mov     rbx, [rdi]
0x180029b76  lea     r15, WPP_GLOBAL_Control
0x180029b7d  cmp     rbx, rdi
0x180029b80  jnz     loc_180029D07
0x180029b86  cmp     qword ptr [rsi+68h], 0
0x180029b8b  jnz     short loc_180029B9A
0x180029b8d  mov     rcx, rsi; this
0x180029b90  call    ?_FinishProcessing@DriverRecoveryManager@@AEAAXXZ; DriverRecoveryManager::_FinishProcessing(void)
0x180029b95  jmp     loc_180029C48
0x180029b9a  lea     rcx, [rsi+0A8h]
0x180029ba1  cmp     qword ptr [rcx], 0
0x180029ba5  jnz     short loc_180029BDA
0x180029ba7  lea     rax, off_180046C48
0x180029bae  mov     [rsp+0E8h+var_98], rax
0x180029bb3  mov     [rsp+0E8h+var_90], rsi
0x180029bb8  lea     rax, [rsp+0E8h+var_98]
0x180029bbd  mov     [rsp+0E8h+var_30], rax
0x180029bc5  lea     rdx, [rsp+0E8h+var_A0]
0x180029bca  call    ?create@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAX$$QEAV?$function@$$A6AXXZ@wistd@@@Z; wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create(wistd::function<void (void)> &&)
0x180029bcf  nop
0x180029bd0  lea     rcx, [rsp+0E8h+var_A0]
0x180029bd5  call    ??1?$function@$$A6AXAEBU_DRIVER_RECOVERY_CONTEXT@@@Z@wistd@@QEAA@XZ; wistd::function<void (_DRIVER_RECOVERY_CONTEXT const &)>::~function<void (_DRIVER_RECOVERY_CONTEXT const &)>(void)
0x180029bda  cmp     qword ptr [rsi+98h], 0
0x180029be2  jnz     short loc_180029C3C
0x180029be4  mov     [rsp+0E8h+var_B8], rsi
0x180029be9  lea     rdx, [rsp+0E8h+var_B8]
0x180029bee  lea     rcx, [rsp+0E8h+var_B0]
0x180029bf3  call    std__make_shared_std__function_void___cdecl_unsigned_short_const___bool____lambda_40cf73d3f1a58b91f93b64488f1182e5___
0x180029bf8  mov     rcx, [rax]
0x180029bfb  mov     rdx, [rax+8]
0x180029bff  mov     qword ptr [rax], 0
0x180029c06  mov     qword ptr [rax+8], 0
0x180029c0e  mov     [rsi+98h], rcx
0x180029c15  mov     rcx, [rsi+0A0h]; this
0x180029c1c  mov     [rsi+0A0h], rdx
0x180029c23  test    rcx, rcx
0x180029c26  jz      short loc_180029C2D
0x180029c28  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180029c2d  mov     rcx, [rsp+0E8h+var_A8]; this
0x180029c32  test    rcx, rcx
0x180029c35  jz      short loc_180029C3C
0x180029c37  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180029c3c  mov     rdi, [rsi+60h]
0x180029c40  mov     rbx, [rdi]
0x180029c43  cmp     rbx, rdi
0x180029c46  jnz     short loc_180029C4F
0x180029c48  xor     eax, eax
0x180029c4a  jmp     loc_180029DCB
0x180029c4f  mov     r8, [rbx+30h]
0x180029c53  mov     rax, [rsi+0A0h]
0x180029c5a  test    rax, rax
0x180029c5d  jz      short loc_180029C63
0x180029c5f  lock inc dword ptr [rax+8]
0x180029c63  mov     r14, [rsi+0A0h]
0x180029c6a  test    r14, r14
0x180029c6d  jz      short loc_180029C80
0x180029c6f  mov     rax, [rsi+98h]
0x180029c76  lock inc dword ptr [r14+0Ch]
0x180029c7b  mov     rdx, r14
0x180029c7e  jmp     short loc_180029C84
0x180029c80  xor     edx, edx
0x180029c82  xor     eax, eax
0x180029c84  mov     [r8+80h], rax
0x180029c8b  mov     rcx, [r8+88h]; this
0x180029c92  mov     [r8+88h], rdx
0x180029c99  test    rcx, rcx
0x180029c9c  jz      short loc_180029CA3
0x180029c9e  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180029ca3  test    r14, r14
0x180029ca6  jz      short loc_180029CB0
0x180029ca8  mov     rcx, r14; this
0x180029cab  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180029cb0  mov     rcx, [rbx+30h]; this
0x180029cb4  call    ?PostJobsForBlockingDevices@DriverRecoveryRecord@@QEAAJXZ; DriverRecoveryRecord::PostJobsForBlockingDevices(void)
0x180029cb9  test    eax, eax
0x180029cbb  jns     short loc_180029CFF
0x180029cbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180029cc4  cmp     rcx, r15
0x180029cc7  jz      short loc_180029CFF
0x180029cc9  test    dword ptr [rcx+1Ch], 800h
0x180029cd0  jz      short loc_180029CFF
0x180029cd2  cmp     byte ptr [rcx+19h], 2
0x180029cd6  jb      short loc_180029CFF
0x180029cd8  lea     r9, [rbx+10h]
0x180029cdc  cmp     qword ptr [r9+18h], 7
0x180029ce1  jbe     short loc_180029CE6
0x180029ce3  mov     r9, [r9]
0x180029ce6  mov     edx, 0Dh
0x180029ceb  mov     [rsp+0E8h+var_C8], eax
0x180029cef  lea     r8, WPP_ab30234a52263744e5d3d91a9e86c909_Traceguids
0x180029cf6  mov     rcx, [rcx+10h]
0x180029cfa  call    WPP_SF_Sd
0x180029cff  mov     rbx, [rbx]
0x180029d02  jmp     loc_180029C43
0x180029d07  lea     r14, [rbx+10h]
0x180029d0b  lea     r15, [rbx+30h]
0x180029d0f  mov     rcx, [r15]; this
0x180029d12  call    ?PerformAction@DriverRecoveryRecord@@QEAAJXZ; DriverRecoveryRecord::PerformAction(void)
0x180029d17  test    eax, eax
0x180029d19  jns     short loc_180029D65
0x180029d1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180029d22  lea     r15, WPP_GLOBAL_Control
0x180029d29  cmp     rcx, r15
0x180029d2c  jz      short loc_180029DA4
0x180029d2e  test    dword ptr [rcx+1Ch], 800h
0x180029d35  jz      short loc_180029DA4
0x180029d37  cmp     byte ptr [rcx+19h], 2
0x180029d3b  jb      short loc_180029DA4
0x180029d3d  cmp     qword ptr [r14+18h], 7
0x180029d42  jbe     short loc_180029D47
0x180029d44  mov     r14, [r14]
0x180029d47  mov     edx, 0Bh
0x180029d4c  mov     [rsp+0E8h+var_C8], eax
0x180029d50  mov     r9, r14
0x180029d53  lea     r8, WPP_ab30234a52263744e5d3d91a9e86c909_Traceguids
0x180029d5a  mov     rcx, [rcx+10h]
0x180029d5e  call    WPP_SF_Sd
0x180029d63  jmp     short loc_180029DA4
0x180029d65  mov     rax, [r15]
0x180029d68  cmp     dword ptr [rax+28h], 6
0x180029d6c  jnz     short loc_180029D77
0x180029d6e  mov     byte ptr [rsi+0B0h], 1
0x180029d75  jmp     short loc_180029D9D
0x180029d77  cmp     dword ptr [rax+28h], 8
0x180029d7b  jnz     short loc_180029D9D
0x180029d7d  lea     rcx, [rsi+58h]
0x180029d81  mov     r8, r14
0x180029d84  lea     rdx, [rsp+0E8h+var_B0]
0x180029d89  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDriverRecoveryRecord@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDriverRecoveryRecord@@@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDriverRecoveryRecord@@@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::shared_ptr<DriverRecoveryRecord>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::shared_ptr<DriverRecoveryRecord>>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x180029d8e  mov     rcx, [rax]
0x180029d91  add     rcx, 30h ; '0'
0x180029d95  mov     rdx, r15
0x180029d98  call    ??4?$shared_ptr@VDriverRecoveryRecord@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<DriverRecoveryRecord>::operator=(std::shared_ptr<DriverRecoveryRecord> const &)
0x180029d9d  lea     r15, WPP_GLOBAL_Control
0x180029da4  mov     rbx, [rbx]
0x180029da7  jmp     loc_180029B7D
0x180029dac  mov     rcx, [rsp+0E8h]; this
0x180029db4  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180029dbb  mov     edx, 0D9h; void *
0x180029dc0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180029dc5  jmp     short loc_180029DCB
0x180029dc7  mov     eax, dword ptr [rsp+0E8h+var_B8]
0x180029dcb  mov     rcx, [rsp+0E8h+var_28]
0x180029dd3  xor     rcx, rsp; StackCookie
0x180029dd6  call    __security_check_cookie
0x180029ddb  lea     r11, [rsp+0E8h+var_18]
0x180029de3  mov     rbx, [r11+28h]
0x180029de7  mov     rsi, [r11+30h]
0x180029deb  mov     rsp, r11
0x180029dee  pop     r15
0x180029df0  pop     r14
0x180029df2  pop     rdi
0x180029df3  retn
```
