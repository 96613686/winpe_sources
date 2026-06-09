# RadioManager::_AlignRadioInstanceWithToggleSwitch(Microsoft::WRL::ComPtr<IUIRadioInstanceInternal> const &,_DEVICE_RADIO_STATE)

- ea: `0x1800201ac`
- end: `0x18002032e`
- name: `?_AlignRadioInstanceWithToggleSwitch@RadioManager@@AEAAXAEBV?$ComPtr@UIUIRadioInstanceInternal@@@WRL@Microsoft@@W4_DEVICE_RADIO_STATE@@@Z`
- size: `386`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020d50`
- `0x1800219ec`

## callees

- `0x180005ef0`
- `0x180006200`
- `0x180006b98`
- `0x18000b180`
- `0x18000b814`
- `0x18000c2a4`
- `0x18000d2a0`
- `0x18001983c`
- `0x1800201ac`
- `0x180023308`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002026d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002026d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall RadioManager::_AlignRadioInstanceWithToggleSwitch(__int64 a1, _QWORD *a2, char a3)
{
  __int64 result; // rax
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 *v10; // rax
  __int64 *v11; // rcx
  __int64 v12; // rdi
  const wchar_t *v13; // rbx
  const wchar_t *v14; // [rsp+40h] [rbp-39h] BYREF
  const wchar_t *v15[2]; // [rsp+48h] [rbp-31h] BYREF
  struct _GUID *v16; // [rsp+58h] [rbp-21h] BYREF
  _BYTE v17[56]; // [rsp+60h] [rbp-19h] BYREF
  __int64 v18; // [rsp+98h] [rbp+1Fh]
  struct _GUID v19; // [rsp+A0h] [rbp+27h] BYREF

  result = ProtectedSystemState::GetSystemState(a1 + 48, v15);
  if ( HIDWORD(v15[0]) == 2 && (a3 & 3) == 0 )
  {
    v19 = 0;
    (*(void (__fastcall **)(_QWORD, struct _GUID *))(*(_QWORD *)*a2 + 48LL))(*a2, &v19);
    if ( (unsigned int)dword_180037050 > 4 )
    {
      v14 = (const wchar_t *)RmGuidToMediaTypeString(&v19);
      v16 = &v19;
      v15[0] = (const wchar_t *)"Queuing to MediaRadioManager to turn off the radio instance since it was added with a de"
                                "vice radio state ON, while the Hardware Switch was OFF";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
        v7,
        (unsigned __int8 *)word_18002F4CA,
        v8,
        v9,
        v15,
        (__int64 *)&v16,
        &v14);
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 240));
    v15[0] = (const wchar_t *)(a1 + 240);
    v10 = *(__int64 **)(a1 + 280);
    v11 = *(__int64 **)(a1 + 288);
    if ( v10 != v11 )
    {
      while ( 1 )
      {
        v12 = *v10;
        if ( *(_QWORD *)(*v10 + 8) == *(_QWORD *)&v19.Data1 && *(_QWORD *)(v12 + 16) == *(_QWORD *)v19.Data4 )
          break;
        if ( ++v10 == v11 )
          return wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v15);
      }
      v14 = (const wchar_t *)*a2;
      v13 = v14;
      Microsoft::WRL::ComPtr<IUIRadioInstanceInternal>::InternalAddRef((__int64 *)&v14);
      v18 = 0;
      v18 = std::_Func_impl_no_alloc__RadioManager::_AlignRadioInstanceWithToggleSwitch_::_19_::_lambda_1__void_::_Func_impl_no_alloc__RadioManager::_AlignRadioInstanceWithToggleSwitch_::_19_::_lambda_1__void___RadioManager::_AlignRadioInstanceWithToggleSwitch_::_19_::_lambda_1__0_(
              v17,
              &v14);
      WcmCommon::ThreadPoolProcessLatestWorkItem<2>::SubmitWork<std::function<void (void)>>(
        (LPCRITICAL_SECTION)(v12 + 24),
        (__int64)v17,
        0);
      std::_Func_class<void,>::~_Func_class<void,>(v17);
      if ( v13 )
        (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v15);
  }
  return result;
}

```

## disassembly

```asm
0x1800201ac  mov     [rsp-8+arg_10], rbx
0x1800201b1  push    rbp
0x1800201b2  push    rsi
0x1800201b3  push    rdi
0x1800201b4  lea     rbp, [rsp-47h]
0x1800201b9  sub     rsp, 0C0h
0x1800201c0  mov     rax, cs:__security_cookie
0x1800201c7  xor     rax, rsp
0x1800201ca  mov     [rbp+57h+var_20], rax
0x1800201ce  mov     ebx, r8d
0x1800201d1  mov     rsi, rdx
0x1800201d4  mov     rdi, rcx
0x1800201d7  add     rcx, 30h ; '0'
0x1800201db  lea     rdx, [rbp+57h+var_88]
0x1800201df  call    ?GetSystemState@ProtectedSystemState@@QEBA?AUSystemState@@XZ; ProtectedSystemState::GetSystemState(void)
0x1800201e4  cmp     dword ptr [rbp+57h+var_88+4], 2
0x1800201e8  jnz     loc_18002030F
0x1800201ee  test    bl, 3
0x1800201f1  jnz     loc_18002030F
0x1800201f7  xorps   xmm0, xmm0
0x1800201fa  movups  xmmword ptr [rbp+57h+var_30.Data1], xmm0
0x1800201fe  mov     rcx, [rsi]
0x180020201  mov     rax, [rcx]
0x180020204  lea     rdx, [rbp+57h+var_30]
0x180020208  mov     rax, [rax+30h]
0x18002020c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020211  mov     eax, cs:dword_180037050
0x180020217  cmp     eax, 4
0x18002021a  jbe     short loc_180020263
0x18002021c  lea     rcx, [rbp+57h+var_30]; struct _GUID *
0x180020220  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x180020225  mov     [rbp+57h+var_90], rax
0x180020229  lea     rax, [rbp+57h+var_30]
0x18002022d  mov     [rbp+57h+var_78], rax
0x180020231  lea     rax, aQueuingToMedia; "Queuing to MediaRadioManager to turn of"...
0x180020238  mov     [rbp+57h+var_88], rax
0x18002023c  lea     rax, [rbp+57h+var_90]
0x180020240  mov     [rsp+0D0h+var_A0], rax
0x180020245  lea     rax, [rbp+57h+var_78]
0x180020249  mov     [rsp+0D0h+var_A8], rax
0x18002024e  lea     rax, [rbp+57h+var_88]
0x180020252  mov     [rsp+0D0h+var_B0], rax
0x180020257  lea     rdx, word_18002F4CA
0x18002025e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x180020263  lea     rbx, [rdi+0F0h]
0x18002026a  mov     rcx, rbx; lpCriticalSection
0x18002026d  call    cs:__imp_EnterCriticalSection
0x180020273  mov     [rbp+57h+var_88], rbx
0x180020277  mov     rax, [rdi+118h]
0x18002027e  mov     rcx, [rdi+120h]
0x180020285  cmp     rax, rcx
0x180020288  jz      short loc_180020306
0x18002028a  mov     rdx, qword ptr [rbp+57h+var_30.Data4]
0x18002028e  mov     r8, qword ptr [rbp+57h+var_30.Data1]
0x180020292  mov     rdi, [rax]
0x180020295  cmp     [rdi+8], r8
0x180020299  jnz     short loc_1800202A1
0x18002029b  cmp     [rdi+10h], rdx
0x18002029f  jz      short loc_1800202AC
0x1800202a1  add     rax, 8
0x1800202a5  cmp     rax, rcx
0x1800202a8  jnz     short loc_180020292
0x1800202aa  jmp     short loc_180020306
0x1800202ac  mov     rbx, [rsi]
0x1800202af  mov     [rbp+57h+var_90], rbx
0x1800202b3  lea     rcx, [rbp+57h+var_90]
0x1800202b7  call    ?InternalAddRef@?$ComPtr@UIUIRadioInstanceInternal@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IUIRadioInstanceInternal>::InternalAddRef(void)
0x1800202bc  nop
0x1800202bd  mov     [rbp+57h+var_38], 0
0x1800202c5  lea     rdx, [rbp+57h+var_90]
0x1800202c9  lea     rcx, [rbp+57h+var_70]
0x1800202cd  call    std___Func_impl_no_alloc__RadioManager___AlignRadioInstanceWithToggleSwitch____19____lambda_1__void____Func_impl_no_alloc__RadioManager___AlignRadioInstanceWithToggleSwitch____19____lambda_1__void___RadioManager___AlignRadioInstanceWithToggleSwitch____19____lambda_1__0_
0x1800202d2  mov     [rbp+57h+var_38], rax
0x1800202d6  lea     rcx, [rdi+18h]; lpCriticalSection
0x1800202da  xor     r8d, r8d
0x1800202dd  lea     rdx, [rbp+57h+var_70]
0x1800202e1  call    ??$SubmitWork@V?$function@$$A6AXXZ@std@@@?$ThreadPoolProcessLatestWorkItem@$01@WcmCommon@@QEAAX$$QEAV?$function@$$A6AXXZ@std@@K@Z; WcmCommon::ThreadPoolProcessLatestWorkItem<2>::SubmitWork<std::function<void (void)>>(std::function<void (void)> &&,ulong)
0x1800202e6  nop
0x1800202e7  lea     rcx, [rbp+57h+var_70]
0x1800202eb  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x1800202f0  nop
0x1800202f1  test    rbx, rbx
0x1800202f4  jz      short loc_180020306
0x1800202f6  mov     rax, [rbx]
0x1800202f9  mov     rcx, rbx
0x1800202fc  mov     rax, [rax+10h]
0x180020300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020305  nop
0x180020306  lea     rcx, [rbp+57h+var_88]
0x18002030a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002030f  mov     rcx, [rbp+57h+var_20]
0x180020313  xor     rcx, rsp; StackCookie
0x180020316  call    __security_check_cookie
0x18002031b  mov     rbx, [rsp+0D0h+arg_10]
0x180020323  add     rsp, 0C0h
0x18002032a  pop     rdi
0x18002032b  pop     rsi
0x18002032c  pop     rbp
0x18002032d  retn
```
