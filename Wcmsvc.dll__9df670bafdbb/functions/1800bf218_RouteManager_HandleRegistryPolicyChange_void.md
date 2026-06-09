# RouteManager::HandleRegistryPolicyChange(void)

- ea: `0x1800bf218`
- end: `0x1800bf2ed`
- name: `?HandleRegistryPolicyChange@RouteManager@@SAXXZ`
- size: `213`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002ec10`

## callees

- `0x180010080`
- `0x180027630`
- `0x180033638`
- `0x180084f50`
- `0x1800bcee8`
- `0x1800bcf9c`
- `0x1800bf218`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bf27e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bf2ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bf27e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bf2ac`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bf2c1`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800bf2c1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall RouteManager::HandleRegistryPolicyChange(__int64 a1)
{
  const char *v1; // r9
  std::_Ref_count_base *v2; // rbx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-38h] BYREF
  std::_Ref_count_base *v4; // [rsp+28h] [rbp-30h] BYREF
  std::_Ref_count_base *v5[2]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *(_OWORD *)v5 = 0;
  std::weak_ptr<RouteManager>::lock(a1, v5);
  try
  {
    v2 = v5[0];
    if ( v5[0] )
    {
      v4 = v5[0];
      lpCriticalSection = 0;
      wil::EnterCriticalSection(&lpCriticalSection, (char *)v5[0] + 88);
      if ( *((_BYTE *)v2 + 352) )
      {
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
      }
      else
      {
        if ( *((_DWORD *)v2 + 20) == 1 )
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__RouteManager::HandleRegistryPolicyChange_::_6_::_lambda_1___(
            (char *)v2 + 232,
            &v4);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__RouteManager::HandleRegistryPolicyChange_::_6_::_lambda_1___(
            (char *)v2 + 312,
            &v4);
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
        _InterlockedIncrement64((volatile signed __int64 *)v2 + 27);
        SubmitThreadpoolWork(*((PTP_WORK *)v2 + 26));
      }
    }
    if ( v5[1] )
      std::_Ref_count_base::_Decref(v5[1]);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x344,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\routemanager\\routemanager.cpp",
      v1);
  }
}

```

## disassembly

```asm
0x1800bf218  push    rbx
0x1800bf21a  sub     rsp, 50h
0x1800bf21e  mov     rax, cs:__security_cookie
0x1800bf225  xor     rax, rsp
0x1800bf228  mov     [rsp+58h+var_18], rax
0x1800bf22d  xorps   xmm0, xmm0
0x1800bf230  movups  xmmword ptr [rsp+58h+var_28], xmm0
0x1800bf235  lea     rdx, [rsp+58h+var_28]
0x1800bf23a  call    ?lock@?$weak_ptr@VRouteManager@@@std@@QEBA?AV?$shared_ptr@VRouteManager@@@2@XZ; std::weak_ptr<RouteManager>::lock(void)
0x1800bf23f  nop
0x1800bf240  mov     rbx, [rsp+58h+var_28]
0x1800bf245  test    rbx, rbx
0x1800bf248  jz      short loc_1800BF2C8
0x1800bf24a  mov     [rsp+58h+var_30], rbx
0x1800bf24f  mov     [rsp+58h+lpCriticalSection], 0
0x1800bf258  lea     rdx, [rbx+58h]
0x1800bf25c  lea     rcx, [rsp+58h+lpCriticalSection]
0x1800bf261  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800bf266  nop
0x1800bf267  lea     rcx, [rbx+0E8h]
0x1800bf26e  cmp     byte ptr [rcx+78h], 0
0x1800bf272  jz      short loc_1800BF286
0x1800bf274  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x1800bf279  test    rcx, rcx
0x1800bf27c  jz      short loc_1800BF2C8
0x1800bf27e  call    cs:__imp_LeaveCriticalSection
0x1800bf284  jmp     short loc_1800BF2C8
0x1800bf286  lea     rdx, [rsp+58h+var_30]
0x1800bf28b  cmp     dword ptr [rbx+50h], 1
0x1800bf28f  jnz     short loc_1800BF298
0x1800bf291  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__RouteManager__HandleRegistryPolicyChange____6____lambda_1___
0x1800bf296  jmp     short loc_1800BF2A2
0x1800bf298  add     rcx, 50h ; 'P'
0x1800bf29c  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__RouteManager__HandleRegistryPolicyChange____6____lambda_1___
0x1800bf2a1  nop
0x1800bf2a2  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x1800bf2a7  test    rcx, rcx
0x1800bf2aa  jz      short loc_1800BF2B2
0x1800bf2ac  call    cs:__imp_LeaveCriticalSection
0x1800bf2b2  lock inc qword ptr [rbx+0D8h]
0x1800bf2ba  mov     rcx, [rbx+0D0h]; pwk
0x1800bf2c1  call    cs:__imp_SubmitThreadpoolWork
0x1800bf2c7  nop
0x1800bf2c8  mov     rcx, [rsp+58h+var_28+8]; this
0x1800bf2cd  test    rcx, rcx
0x1800bf2d0  jz      short loc_1800BF2D8
0x1800bf2d2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bf2d7  nop
0x1800bf2d8  jmp     short $+2
0x1800bf2da  mov     rcx, [rsp+58h+var_18]
0x1800bf2df  xor     rcx, rsp; StackCookie
0x1800bf2e2  call    __security_check_cookie
0x1800bf2e7  add     rsp, 50h
0x1800bf2eb  pop     rbx
0x1800bf2ec  retn
```
