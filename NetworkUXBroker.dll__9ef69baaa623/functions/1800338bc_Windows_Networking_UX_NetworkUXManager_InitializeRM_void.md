# Windows::Networking::UX::NetworkUXManager::_InitializeRM(void)

- ea: `0x1800338bc`
- end: `0x180033a1b`
- name: `?_InitializeRM@NetworkUXManager@UX@Networking@Windows@@AEAAJXZ`
- size: `351`
- prototype: `__int64 __fastcall(Windows::Networking::UX::NetworkUXManager *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001b5c0`
- `0x1800333f8`

## callees

- `0x180002520`
- `0x180009e50`
- `0x18000c768`
- `0x18000e768`
- `0x18002271c`
- `0x180023998`
- `0x1800338bc`
- `0x180033b70`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003395e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003395e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800338ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800338ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800339cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800339ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800339cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800339ee`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18003397e`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18003397e`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::NetworkUXManager::_InitializeRM(
        Windows::Networking::UX::NetworkUXManager *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  __int64 *v3; // rax
  __int64 v4; // rsi
  __int64 v5; // rcx
  DWORD CurrentThreadId; // eax
  int v7; // edi
  __int64 v8; // rdx
  int v10; // [rsp+30h] [rbp-68h] BYREF
  __int64 v11; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v12[64]; // [rsp+40h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 104);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  if ( !*((_BYTE *)this + 330) )
  {
    *((_BYTE *)this + 330) = 1;
    `winrt::Windows::Data::Json::JsonValue::CreateNumberValue'::`2'::_lambda_1_::_lambda_1_(&v11, (__int64)this);
    v10 = 0;
    std::function_long___cdecl_void__::function_long___cdecl_void____Windows::Networking::UX::NetworkUXManager::_InitializeRM_::_5_::_lambda_1__const___0_(
      v12,
      &v11);
    v3 = Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CResultTaskWrapper<std::function<long (void)>>,long &,std::function<long (void)>>(
           &v11,
           (__int64)&v10,
           (__int64)v12);
    v4 = *v3;
    *v3 = 0;
    v5 = v11;
    if ( v11 )
    {
      v11 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(v5);
    }
    CurrentThreadId = GetCurrentThreadId();
    v7 = SHTaskPoolQueueTask(0, 32, CurrentThreadId);
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    std::_Func_class<long,>::_Tidy(v12);
    if ( v7 < 0 )
    {
      v8 = 820;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\networkuxmanager.cpp",
        (const char *)(unsigned int)v7,
        v4);
      if ( v2 )
        LeaveCriticalSection(v2);
      return (unsigned int)v7;
    }
    v7 = v10;
    if ( v10 < 0 )
    {
      v8 = 821;
      goto LABEL_8;
    }
  }
  if ( v2 )
    LeaveCriticalSection(v2);
  return 0;
}

```

## disassembly

```asm
0x1800338bc  mov     [rsp+arg_8], rbx
0x1800338c1  mov     [rsp+arg_10], rsi
0x1800338c6  push    rdi
0x1800338c7  sub     rsp, 90h
0x1800338ce  mov     rax, cs:__security_cookie
0x1800338d5  xor     rax, rsp
0x1800338d8  mov     [rsp+98h+var_18], rax
0x1800338e0  mov     rdi, rcx
0x1800338e3  lea     rbx, [rcx+68h]
0x1800338e7  mov     rcx, rbx; lpCriticalSection
0x1800338ea  call    cs:__imp_EnterCriticalSection
0x1800338f0  cmp     byte ptr [rdi+14Ah], 0
0x1800338f7  jnz     loc_1800339E6
0x1800338fd  mov     byte ptr [rdi+14Ah], 1
0x180033904  mov     rdx, rdi
0x180033907  lea     rcx, [rsp+98h+var_60]
0x18003390c  call    ??0_lambda_1_@?1??CreateNumberValue@JsonValue@Json@Data@Windows@winrt@@SA@N@Z@QEAA@AEAN@Z; `winrt::Windows::Data::Json::JsonValue::CreateNumberValue(double)'::`2'::_lambda_1_::_lambda_1_(double &)
0x180033911  mov     [rsp+98h+var_68], 0
0x180033919  lea     rdx, [rsp+98h+var_60]
0x18003391e  lea     rcx, [rsp+98h+var_58]
0x180033923  call    std__function_long___cdecl_void____function_long___cdecl_void____Windows__Networking__UX__NetworkUXManager___InitializeRM____5____lambda_1__const___0_
0x180033928  lea     r8, [rsp+98h+var_58]
0x18003392d  lea     rdx, [rsp+98h+var_68]
0x180033932  lea     rcx, [rsp+98h+var_60]
0x180033937  call    ??$Make@V?$CResultTaskWrapper@V?$function@$$A6AJXZ@std@@@ComTaskPool@Internal@Windows@@AEAJV?$function@$$A6AJXZ@std@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CResultTaskWrapper@V?$function@$$A6AJXZ@std@@@ComTaskPool@Internal@Windows@@@12@AEAJ$$QEAV?$function@$$A6AJXZ@std@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CResultTaskWrapper<std::function<long (void)>>,long &,std::function<long (void)>>(long &,std::function<long (void)> &&)
0x18003393c  mov     rsi, [rax]
0x18003393f  mov     qword ptr [rax], 0
0x180033946  mov     rcx, [rsp+98h+var_60]
0x18003394b  test    rcx, rcx
0x18003394e  jz      short loc_18003395E
0x180033950  mov     [rsp+98h+var_60], 0
0x180033959  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18003395e  call    cs:__imp_GetCurrentThreadId
0x180033964  mov     [rsp+98h+var_70], 0
0x18003396d  mov     qword ptr [rsp+98h+var_78], rsi; int
0x180033972  xor     r9d, r9d
0x180033975  mov     r8d, eax
0x180033978  lea     edx, [r9+20h]
0x18003397c  xor     ecx, ecx
0x18003397e  call    cs:__imp_SHTaskPoolQueueTask
0x180033984  mov     edi, eax
0x180033986  test    rsi, rsi
0x180033989  jz      short loc_18003399B
0x18003398b  mov     rcx, [rsi]
0x18003398e  mov     rax, [rcx+10h]
0x180033992  mov     rcx, rsi
0x180033995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003399a  nop
0x18003399b  lea     rcx, [rsp+98h+var_58]
0x1800339a0  call    ?_Tidy@?$_Func_class@J$$V@std@@IEAAXXZ; std::_Func_class<long,>::_Tidy(void)
0x1800339a5  test    edi, edi
0x1800339a7  jns     short loc_1800339D7
0x1800339a9  mov     edx, 334h; void *
0x1800339ae  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\uxmanager\\lib\\ne"...
0x1800339b5  mov     r9d, edi; char *
0x1800339b8  mov     rcx, [rsp+98h]; this
0x1800339c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800339c5  test    rbx, rbx
0x1800339c8  jz      short loc_1800339D3
0x1800339ca  mov     rcx, rbx; lpCriticalSection
0x1800339cd  call    cs:__imp_LeaveCriticalSection
0x1800339d3  mov     eax, edi
0x1800339d5  jmp     short loc_1800339F6
0x1800339d7  mov     edi, [rsp+98h+var_68]
0x1800339db  test    edi, edi
0x1800339dd  jns     short loc_1800339E6
0x1800339df  mov     edx, 335h
0x1800339e4  jmp     short loc_1800339AE
0x1800339e6  test    rbx, rbx
0x1800339e9  jz      short loc_1800339F4
0x1800339eb  mov     rcx, rbx; lpCriticalSection
0x1800339ee  call    cs:__imp_LeaveCriticalSection
0x1800339f4  xor     eax, eax
0x1800339f6  mov     rcx, [rsp+98h+var_18]
0x1800339fe  xor     rcx, rsp; StackCookie
0x180033a01  call    __security_check_cookie
0x180033a06  lea     r11, [rsp+98h+var_8]
0x180033a0e  mov     rbx, [r11+18h]
0x180033a12  mov     rsi, [r11+20h]
0x180033a16  mov     rsp, r11
0x180033a19  pop     rdi
0x180033a1a  retn
```
