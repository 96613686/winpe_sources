# winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::GetCurrent(void)

- ea: `0x180005200`
- end: `0x1800053e5`
- name: `?GetCurrent@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@SA?AU134567@XZ`
- size: `485`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180008ff0`

## callees

- `0x180003840`
- `0x180003ee0`
- `0x180004e80`
- `0x180005200`
- `0x18000ac20`
- `0x18000bb30`
- `0x18000f410`
- `0x18000f430`
- `0x18000f5d0`
- `0x1800181b0`
- `0x1800181fc`
- `0x18001cdf0`
- `0x18001d600`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x180005242`
- `KERNEL32!InitOnceBeginInitialize` at `0x180005242`
- `KERNEL32!InitOnceComplete` at `0x18000531f`
- `KERNEL32!InitOnceComplete` at `0x18000531f`

## string_xrefs

- `0x1800053d3`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.2.142\inc\wil\opensource\wil\win32_helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::GetCurrent(
        _QWORD *a1)
{
  const char *v2; // r9
  volatile signed __int64 *v3; // rbx
  signed __int64 v4; // rax
  signed __int64 v5; // rtt
  void *v6; // rdx
  char v7; // bl
  unsigned int v8; // r8d
  __int64 v9; // rcx
  int v11; // eax
  int v12[4]; // [rsp+20h] [rbp-48h] BYREF
  union _RTL_RUN_ONCE *v13; // [rsp+30h] [rbp-38h]
  int v14; // [rsp+38h] [rbp-30h]
  __int64 interface; // [rsp+40h] [rbp-28h] BYREF
  BOOL fPending[2]; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *(_QWORD *)v12 = a1;
  fPending[0] = 0;
  if ( !InitOnceBeginInitialize(&InitOnce, 0, fPending, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x372,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.2.142\\inc\\wil\\opensource\\wil\\win32_helpers.h",
      v2);
  if ( fPending[0] )
  {
    v13 = &InitOnce;
    v14 = 4;
    v3 = (volatile signed __int64 *)operator new(0x120u);
    memset((void *)v3, 0, 0x120u);
    winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::ModelCacheManager((winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *)v3);
    *v3 = (volatile signed __int64)&winrt::impl::heap_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager>::`vftable';
    *(_QWORD *)v12 = v3;
    interface = winrt::implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::find_interface(
                  (__int64)v3,
                  &winrt::impl::guid_v<winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager>);
    if ( interface )
    {
      v4 = *((_QWORD *)v3 + 1);
      if ( v4 < 0 )
      {
LABEL_7:
        _InterlockedIncrement((volatile signed __int32 *)(2 * v4 + 24));
      }
      else
      {
        while ( 1 )
        {
          v5 = v4;
          v4 = _InterlockedCompareExchange64(v3 + 1, v4 + 1, v4);
          if ( v5 == v4 )
            break;
          if ( v4 < 0 )
            goto LABEL_7;
        }
      }
    }
    else
    {
      v11 = winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Foundation::IAsyncInfo>::query_interface_common(
              v3,
              &winrt::impl::guid_v<winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager>,
              &interface);
      if ( v11 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v11);
      }
    }
    if ( winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::s_instance )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::s_instance);
    winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::s_instance = interface;
    winrt::com_ptr<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager>::unconditional_release_ref(v12);
    InitOnceComplete(&InitOnce, 0, 0);
  }
  *(_QWORD *)fPending = 0;
  v7 = winrt::Windows::Foundation::operator==(
         &winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::s_instance,
         fPending);
  if ( *(_QWORD *)fPending )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(fPending);
  if ( v7 )
    wil::details::in1diag3::_Throw_Hr(retaddr, v6, v8, (const char *)0x8000FFFFLL, v12[0]);
  v9 = winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::s_instance;
  *a1 = winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::s_instance;
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
  return a1;
}

```

## disassembly

```asm
0x180005200  mov     [rsp+arg_8], rbx
0x180005205  mov     [rsp+arg_10], rsi
0x18000520a  push    rdi
0x18000520b  sub     rsp, 60h
0x18000520f  mov     rax, cs:__security_cookie
0x180005216  xor     rax, rsp
0x180005219  mov     [rsp+68h+var_18], rax
0x18000521e  mov     rdi, rcx
0x180005221  mov     qword ptr [rsp+68h+var_48], rcx
0x180005226  mov     [rsp+68h+fPending], 0
0x18000522e  xor     r9d, r9d; lpContext
0x180005231  lea     r8, [rsp+68h+fPending]; fPending
0x180005236  xor     edx, edx; dwFlags
0x180005238  lea     rsi, InitOnce
0x18000523f  mov     rcx, rsi; lpInitOnce
0x180005242  call    cs:__imp_InitOnceBeginInitialize
0x180005248  mov     rcx, [rsp+68h]; this
0x18000524d  test    eax, eax
0x18000524f  jz      loc_1800053D3
0x180005255  cmp     [rsp+68h+fPending], 0
0x18000525a  jz      loc_180005325
0x180005260  mov     [rsp+68h+var_38], rsi
0x180005265  mov     [rsp+68h+var_30], 4
0x18000526d  mov     ecx, 120h; Size
0x180005272  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005277  mov     rbx, rax
0x18000527a  mov     qword ptr [rsp+68h+var_48], rax
0x18000527f  xor     edx, edx; Val
0x180005281  mov     r8d, 120h; Size
0x180005287  mov     rcx, rax; void *
0x18000528a  call    memset
0x18000528f  mov     rcx, rbx; this
0x180005292  call    ??0ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::ModelCacheManager(void)
0x180005297  lea     rax, ??_7?$heap_implements@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager>::`vftable'
0x18000529e  mov     [rbx], rax
0x1800052a1  mov     qword ptr [rsp+68h+var_48], rbx; int
0x1800052a6  lea     rdx, ??$guid_v@UIModelCacheManager@CacheManagement@Private@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager>
0x1800052ad  mov     rcx, rbx
0x1800052b0  mov     rax, cs:off_180025950
0x1800052b7  call    cs:__guard_dispatch_icall_fptr
0x1800052bd  mov     [rsp+68h+var_28], rax
0x1800052c2  test    rax, rax
0x1800052c5  jz      loc_18000539C
0x1800052cb  mov     rax, [rbx+8]
0x1800052cf  test    rax, rax
0x1800052d2  js      short loc_1800052E5
0x1800052d4  lea     rcx, [rax+1]
0x1800052d8  lock cmpxchg [rbx+8], rcx
0x1800052de  jz      short loc_1800052EA
0x1800052e0  test    rax, rax
0x1800052e3  jns     short loc_1800052D4
0x1800052e5  lock inc dword ptr [rax+rax+18h]
0x1800052ea  cmp     cs:?s_instance@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@0U134567@A, 0; winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::s_instance
0x1800052f2  jz      short loc_180005300
0x1800052f4  lea     rcx, ?s_instance@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@0U134567@A; winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::s_instance
0x1800052fb  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180005300  mov     rax, [rsp+68h+var_28]
0x180005305  mov     cs:?s_instance@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@0U134567@A, rax; winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::s_instance
0x18000530c  lea     rcx, [rsp+68h+var_48]
0x180005311  call    ?unconditional_release_ref@?$com_ptr@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager>::unconditional_release_ref(void)
0x180005316  nop
0x180005317  xor     r8d, r8d; lpContext
0x18000531a  xor     edx, edx; dwFlags
0x18000531c  mov     rcx, rsi; lpInitOnce
0x18000531f  call    cs:__imp_InitOnceComplete
0x180005325  mov     rsi, [rsp+68h]
0x18000532a  mov     qword ptr [rsp+68h+fPending], 0
0x180005333  lea     rdx, [rsp+68h+fPending]
0x180005338  lea     rcx, ?s_instance@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@0U134567@A; winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::s_instance
0x18000533f  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180005344  movzx   ebx, al
0x180005347  cmp     qword ptr [rsp+68h+fPending], 0
0x18000534d  jz      short loc_180005359
0x18000534f  lea     rcx, [rsp+68h+fPending]
0x180005354  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180005359  test    bl, bl
0x18000535b  jnz     short loc_1800053B9
0x18000535d  mov     rcx, cs:?s_instance@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@0U134567@A; winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::s_instance
0x180005364  mov     [rdi], rcx
0x180005367  test    rcx, rcx
0x18000536a  jz      short loc_180005379
0x18000536c  mov     rdx, [rcx]
0x18000536f  mov     rax, [rdx+8]
0x180005373  call    cs:__guard_dispatch_icall_fptr
0x180005379  mov     rax, rdi
0x18000537c  mov     rcx, [rsp+68h+var_18]
0x180005381  xor     rcx, rsp; StackCookie
0x180005384  call    __security_check_cookie
0x180005389  mov     rbx, [rsp+68h+arg_8]
0x18000538e  mov     rsi, [rsp+68h+arg_10]
0x180005396  add     rsp, 60h
0x18000539a  pop     rdi
0x18000539b  retn
0x18000539c  lea     r8, [rsp+68h+var_28]
0x1800053a1  lea     rdx, ??$guid_v@UIModelCacheManager@CacheManagement@Private@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager>
0x1800053a8  mov     rcx, rbx
0x1800053ab  call    ?query_interface_common@?$root_implements@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAUModelCacheManager@implementation@CacheManagement@Private@3Microsoft@4@Uhstring@4@Uhstring@4@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@UIAsyncInfo@678@@impl@winrt@@AEAAHAEBUguid@3@PEAPEAX@Z; winrt::impl::root_implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncAction,winrt::Windows::Foundation::IAsyncInfo>::query_interface_common(winrt::guid const &,void * *)
0x1800053b0  test    eax, eax
0x1800053b2  js      short loc_1800053C8
0x1800053b4  jmp     loc_1800052EA
0x1800053b9  mov     r9d, 8000FFFFh; char *
0x1800053bf  mov     rcx, rsi; this
0x1800053c2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800053c8  lfence
0x1800053cb  mov     ecx, eax
0x1800053cd  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x1800053d3  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800053da  mov     edx, 372h; void *
0x1800053df  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
