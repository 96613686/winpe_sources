# RadioManager::_AddInstance(IRadioInstance *)

- ea: `0x1800200dc`
- end: `0x1800201a6`
- name: `?_AddInstance@RadioManager@@AEAAXPEAUIRadioInstance@@@Z`
- size: `202`
- prototype: `void __fastcall(RadioManager *__hidden this, struct IRadioInstance *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f090`

## callees

- `0x180003fa0`
- `0x180006b98`
- `0x18000c2a4`
- `0x18001b324`
- `0x18001b3d4`
- `0x1800200dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020122`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020122`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002017e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002017e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall RadioManager::_AddInstance(RadioManager *this, const wchar_t *a2)
{
  wil *v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  char *v8; // [rsp+30h] [rbp-28h] BYREF
  const wchar_t *v9; // [rsp+38h] [rbp-20h] BYREF
  __int128 v10; // [rsp+40h] [rbp-18h] BYREF

  v9 = a2;
  Microsoft::WRL::ComPtr<IUIRadioInstanceInternal>::InternalAddRef(&v9);
  v10 = (unsigned __int64)a2;
  Microsoft::WRL::ComPtr<IUIRadioInstanceInternal>::InternalAddRef(&v10);
  *((_QWORD *)&v10 + 1) = this;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 448));
  try
  {
    v8 = (char *)this + 448;
    if ( *((_BYTE *)this + 712) )
    {
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v8);
    }
    else
    {
      if ( *((_DWORD *)this + 110) == 1 )
        std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__RadioManager::_AddInstance_::_3_::_lambda_1___(
          (char *)this + 592,
          &v10);
      else
        std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__RadioManager::_AddInstance_::_3_::_lambda_1___(
          (char *)this + 672,
          &v10);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v8);
      _InterlockedIncrement64((volatile signed __int64 *)this + 72);
      SubmitThreadpoolWork(*((PTP_WORK *)this + 71));
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
  }
  catch ( ... )
  {
    if ( (unsigned int)dword_180037050 > 2 )
    {
      LODWORD(v8) = wil::ResultFromCaughtException(v4);
      v9 = (const wchar_t *)"std::exception thrown trying to submit a workitem";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v5,
        (unsigned __int8 *)&unk_18002F270,
        v6,
        v7,
        &v9,
        (__int64)&v8);
    }
  }
}

```

## disassembly

```asm
0x1800200dc  mov     [rsp+arg_8], rbx
0x1800200e1  push    rdi
0x1800200e2  sub     rsp, 50h
0x1800200e6  mov     rbx, rdx
0x1800200e9  mov     rdi, rcx
0x1800200ec  mov     [rsp+58h+var_20], rdx
0x1800200f1  lea     rcx, [rsp+58h+var_20]
0x1800200f6  call    ?InternalAddRef@?$ComPtr@UIUIRadioInstanceInternal@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IUIRadioInstanceInternal>::InternalAddRef(void)
0x1800200fb  nop
0x1800200fc  xorps   xmm0, xmm0
0x1800200ff  movups  [rsp+58h+var_18], xmm0
0x180020104  mov     qword ptr [rsp+58h+var_18], rbx
0x180020109  lea     rcx, [rsp+58h+var_18]
0x18002010e  call    ?InternalAddRef@?$ComPtr@UIUIRadioInstanceInternal@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IUIRadioInstanceInternal>::InternalAddRef(void)
0x180020113  mov     qword ptr [rsp+58h+var_18+8], rdi
0x180020118  lea     rbx, [rdi+1C0h]
0x18002011f  mov     rcx, rbx; lpCriticalSection
0x180020122  call    cs:__imp_EnterCriticalSection
0x180020128  mov     [rsp+58h+var_28], rbx
0x18002012d  lea     rcx, [rdi+250h]
0x180020134  cmp     byte ptr [rcx+78h], 0
0x180020138  jz      short loc_180020146
0x18002013a  lea     rcx, [rsp+58h+var_28]
0x18002013f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180020144  jmp     short loc_180020185
0x180020146  lea     rdx, [rsp+58h+var_18]
0x18002014b  cmp     dword ptr [rdi+1B8h], 1
0x180020152  jnz     short loc_18002015B
0x180020154  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__RadioManager___AddInstance____3____lambda_1___
0x180020159  jmp     short loc_180020165
0x18002015b  add     rcx, 50h ; 'P'
0x18002015f  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__RadioManager___AddInstance____3____lambda_1___
0x180020164  nop
0x180020165  lea     rcx, [rsp+58h+var_28]
0x18002016a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002016f  lock inc qword ptr [rdi+240h]
0x180020177  mov     rcx, [rdi+238h]; pwk
0x18002017e  call    cs:__imp_SubmitThreadpoolWork
0x180020184  nop
0x180020185  lea     rcx, [rsp+58h+var_18]
0x18002018a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002018f  nop
0x180020190  lea     rcx, [rsp+58h+var_20]
0x180020195  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002019a  nop
0x18002019b  mov     rbx, [rsp+58h+arg_8]
0x1800201a0  add     rsp, 50h
0x1800201a4  pop     rdi
0x1800201a5  retn
```
