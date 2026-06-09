# RadioManager::_SetInstanceRadio(Microsoft::WRL::ComPtr<IRadioInstance> const &,Microsoft::WRL::ComPtr<IUIRadioInstanceInternal> const &,bool)

- ea: `0x18002214c`
- end: `0x1800222c7`
- name: `?_SetInstanceRadio@RadioManager@@AEAAXAEBV?$ComPtr@UIRadioInstance@@@WRL@Microsoft@@AEBV?$ComPtr@UIUIRadioInstanceInternal@@@34@_N@Z`
- size: `379`
- prototype: `__int64 __fastcall(__int64, __int64 *, _QWORD *, char)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001f090`

## callees

- `0x180005ef0`
- `0x180006b98`
- `0x180008640`
- `0x18000b180`
- `0x18000c2a4`
- `0x18000d2a0`
- `0x1800197e0`
- `0x18001bc0c`
- `0x18002214c`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022201`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022201`

## string_xrefs

- `0x18002219f`: `IUIRadioInstanceInternal::GetMediaRMSignature`
- `0x1800221ae`: `onecoreuap\net\mobility\radiomanagement\dll\radiomanagementapi.cpp`

## pseudocode

```c
__int64 __fastcall RadioManager::_SetInstanceRadio(__int64 a1, __int64 *a2, _QWORD *a3, char a4)
{
  unsigned int v8; // eax
  __int64 v9; // rbx
  __int64 result; // rax
  wil *v11; // rcx
  __int64 *i; // rax
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  const char *v16; // [rsp+28h] [rbp-B0h]
  __int64 v17; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE v18[4]; // [rsp+38h] [rbp-A0h] BYREF
  __int128 v19; // [rsp+3Ch] [rbp-9Ch]
  __int64 v20; // [rsp+50h] [rbp-88h] BYREF
  __int64 v21; // [rsp+58h] [rbp-80h] BYREF
  _BYTE v22[56]; // [rsp+60h] [rbp-78h] BYREF
  __int64 v23; // [rsp+98h] [rbp-40h]
  __int128 v24; // [rsp+A0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  try
  {
    v24 = 0;
    v8 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*a3 + 48LL))(*a3, &v24);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x6C9,
      (unsigned int)"onecoreuap\\net\\mobility\\radiomanagement\\dll\\radiomanagementapi.cpp",
      (const char *)v8,
      (int)"IUIRadioInstanceInternal::GetMediaRMSignature",
      v16);
    v18[0] = a4;
    v19 = v24;
    v20 = *a2;
    Microsoft::WRL::ComPtr<IUIRadioInstanceInternal>::InternalAddRef(&v20);
    v21 = *a3;
    Microsoft::WRL::ComPtr<IUIRadioInstanceInternal>::InternalAddRef(&v21);
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 240));
    v17 = a1 + 240;
    for ( i = *(__int64 **)(a1 + 280); i != *(__int64 **)(a1 + 288); ++i )
    {
      v9 = *i;
      if ( *(_OWORD *)(*i + 8) == v24 )
      {
        v23 = 0;
        v23 = std::_Func_impl_no_alloc__RadioManager::_SetInstanceRadio_::_3_::_lambda_1__void_::_Func_impl_no_alloc__RadioManager::_SetInstanceRadio_::_3_::_lambda_1__void___RadioManager::_SetInstanceRadio_::_3_::_lambda_1__0_(
                v22,
                v18,
                v24);
        WcmCommon::ThreadPoolProcessLatestWorkItem<2>::SubmitWork<std::function<void (void)>>((LPCRITICAL_SECTION)(v9 + 24));
        std::_Func_class<void,>::~_Func_class<void,>(v22);
        break;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v17);
    result = RadioManager::_SetInstanceRadio_::_3_::_lambda_1_::__lambda_1_(v18);
  }
  catch ( ... )
  {
    result = (unsigned int)dword_180037050;
    if ( (unsigned int)dword_180037050 > 2 )
    {
      LODWORD(v17) = wil::ResultFromCaughtException(v11);
      *(_QWORD *)&v24 = "Exception thrown trying to queue a work item";
      return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
               v13,
               (unsigned int)&unk_18002EB18,
               v14,
               v15,
               (__int64)&v24,
               (__int64)&v17);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002214c  mov     r11, rsp
0x18002214f  mov     [r11+10h], rbx
0x180022153  push    rsi
0x180022154  push    rdi
0x180022155  push    r14
0x180022157  sub     rsp, 0C0h
0x18002215e  mov     rax, cs:__security_cookie
0x180022165  xor     rax, rsp
0x180022168  mov     [rsp+0D8h+var_28], rax
0x180022170  mov     sil, r9b
0x180022173  mov     rbx, r8
0x180022176  mov     r14, rdx
0x180022179  mov     rdi, rcx
0x18002217c  xorps   xmm0, xmm0
0x18002217f  movups  xmmword ptr [r11-38h], xmm0
0x180022184  mov     rcx, [r8]
0x180022187  mov     rax, [rcx]
0x18002218a  lea     rdx, [r11-38h]
0x18002218e  mov     rax, [rax+30h]
0x180022192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022197  mov     rcx, [rsp+0D8h]; this
0x18002219f  lea     rdx, aIuiradioinstan; "IUIRadioInstanceInternal::GetMediaRMSig"...
0x1800221a6  mov     qword ptr [rsp+0D8h+var_B8], rdx; int
0x1800221ab  mov     r9d, eax; char *
0x1800221ae  lea     r8, aOnecoreuapNetM_4; "onecoreuap\\net\\mobility\\radiomanagem"...
0x1800221b5  mov     edx, 6C9h; void *
0x1800221ba  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800221bf  mov     [rsp+0D8h+var_A0], sil
0x1800221c4  movups  xmm0, [rsp+0D8h+var_38]
0x1800221cc  movdqu  [rsp+0D8h+var_9C], xmm0
0x1800221d2  mov     rax, [r14]
0x1800221d5  mov     [rsp+0D8h+var_88], rax
0x1800221da  lea     rcx, [rsp+0D8h+var_88]
0x1800221df  call    ?InternalAddRef@?$ComPtr@UIUIRadioInstanceInternal@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IUIRadioInstanceInternal>::InternalAddRef(void)
0x1800221e4  mov     rax, [rbx]
0x1800221e7  mov     [rsp+0D8h+var_80], rax
0x1800221ec  lea     rcx, [rsp+0D8h+var_80]
0x1800221f1  call    ?InternalAddRef@?$ComPtr@UIUIRadioInstanceInternal@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IUIRadioInstanceInternal>::InternalAddRef(void)
0x1800221f6  nop
0x1800221f7  lea     rbx, [rdi+0F0h]
0x1800221fe  mov     rcx, rbx; lpCriticalSection
0x180022201  call    cs:__imp_EnterCriticalSection
0x180022207  mov     [rsp+0D8h+var_A8], rbx
0x18002220c  mov     rax, [rdi+118h]
0x180022213  mov     rcx, [rdi+120h]
0x18002221a  mov     rdx, qword ptr [rsp+0D8h+var_38+8]
0x180022222  mov     r8, qword ptr [rsp+0D8h+var_38]
0x18002222a  cmp     rax, rcx
0x18002222d  jz      short loc_180022282
0x18002222f  mov     rbx, [rax]
0x180022232  cmp     [rbx+8], r8
0x180022236  jnz     loc_1800222BC
0x18002223c  cmp     [rbx+10h], rdx
0x180022240  jnz     short loc_1800222BC
0x180022242  mov     [rsp+0D8h+var_40], 0
0x18002224e  lea     rdx, [rsp+0D8h+var_A0]
0x180022253  lea     rcx, [rsp+0D8h+var_78]
0x180022258  call    std___Func_impl_no_alloc__RadioManager___SetInstanceRadio____3____lambda_1__void____Func_impl_no_alloc__RadioManager___SetInstanceRadio____3____lambda_1__void___RadioManager___SetInstanceRadio____3____lambda_1__0_
0x18002225d  mov     [rsp+0D8h+var_40], rax
0x180022265  lea     rcx, [rbx+18h]; lpCriticalSection
0x180022269  xor     r8d, r8d
0x18002226c  lea     rdx, [rsp+0D8h+var_78]
0x180022271  call    ??$SubmitWork@V?$function@$$A6AXXZ@std@@@?$ThreadPoolProcessLatestWorkItem@$01@WcmCommon@@QEAAX$$QEAV?$function@$$A6AXXZ@std@@K@Z; WcmCommon::ThreadPoolProcessLatestWorkItem<2>::SubmitWork<std::function<void (void)>>(std::function<void (void)> &&,ulong)
0x180022276  nop
0x180022277  lea     rcx, [rsp+0D8h+var_78]
0x18002227c  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x180022281  nop
0x180022282  lea     rcx, [rsp+0D8h+var_A8]
0x180022287  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002228c  nop
0x18002228d  lea     rcx, [rsp+0D8h+var_A0]
0x180022292  call    _RadioManager___SetInstanceRadio____3____lambda_1_____lambda_1_
0x180022297  nop
0x180022298  mov     rcx, [rsp+0D8h+var_28]
0x1800222a0  xor     rcx, rsp; StackCookie
0x1800222a3  call    __security_check_cookie
0x1800222a8  mov     rbx, [rsp+0D8h+arg_8]
0x1800222b0  add     rsp, 0C0h
0x1800222b7  pop     r14
0x1800222b9  pop     rdi
0x1800222ba  pop     rsi
0x1800222bb  retn
0x1800222bc  add     rax, 8
0x1800222c0  jmp     loc_18002222A
```
