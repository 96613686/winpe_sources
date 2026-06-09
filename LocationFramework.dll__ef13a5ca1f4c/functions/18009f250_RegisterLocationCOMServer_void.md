# RegisterLocationCOMServer(void)

- ea: `0x18009f250`
- end: `0x18009f36c`
- name: `?RegisterLocationCOMServer@@YAJXZ`
- size: `284`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180012194`
- `0x1800123c0`
- `0x18001be08`
- `0x18009c310`
- `0x18009f250`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18009f25a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18009f25a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18009f2de`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18009f2de`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18009f35e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18009f35e`

## string_xrefs

- `0x18009f27b`: `RegisterLocationCOMServer`
- `0x18009f33a`: `RegisterLocationCOMServer`
- `0x18009f26f`: `CoInitializeEx(nullptr, COINIT_MULTITHREADED)`

## pseudocode

```c
__int64 RegisterLocationCOMServer(void)
{
  HRESULT v0; // eax
  HRESULT Instance; // ebx
  int v2; // eax
  wil::details *v4; // [rsp+28h] [rbp-30h]
  wil::details *v5; // [rsp+28h] [rbp-30h]
  int v6; // [rsp+30h] [rbp-28h]
  _BYTE v7[24]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+58h] [rbp+0h]

  v0 = CoInitializeEx(0, 0);
  Instance = v0;
  if ( v0 >= 0 )
  {
    Instance = 0;
    ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
      v7,
      qword_1801E4250);
    if ( !ppv )
    {
      Instance = CoCreateInstance(&CLSID_ContextSwitcher, 0, 1u, &GUID_000001da_0000_0000_c000_000000000046, &ppv);
      if ( Instance >= 0 )
      {
        v2 = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall *)(struct tagComCallData *), _QWORD, GUID *, int, _QWORD))(*(_QWORD *)ppv + 24LL))(
               ppv,
               RegisterServerInContext,
               0,
               &IID_IContextCallback,
               5,
               0);
        Instance = v2;
        if ( v2 < 0 )
        {
          LODWORD(v5) = v2;
          wil::details::in1diag5::_Log_Hr(
            retaddr,
            (void *)0x96,
            (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\svclocationserver.cpp",
            "RegisterLocationCOMServer",
            "g_pLocServerContext->ContextCallback( RegisterServerInContext, nullptr, IID_IContextCallback, g_contextCallb"
            "ackFunctionIndex, nullptr)",
            (const char *)v5,
            v6);
        }
      }
    }
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v7);
    CoUninitialize();
  }
  else
  {
    LODWORD(v4) = v0;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\framework\\svclocationserver.cpp",
      "RegisterLocationCOMServer",
      "CoInitializeEx(nullptr, COINIT_MULTITHREADED)",
      v4,
      v6);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18009f250  push    rbx
0x18009f252  sub     rsp, 50h
0x18009f256  xor     edx, edx; dwCoInit
0x18009f258  xor     ecx, ecx; pvReserved
0x18009f25a  call    cs:__imp_CoInitializeEx
0x18009f260  mov     ebx, eax
0x18009f262  test    eax, eax
0x18009f264  jns     short loc_18009F298
0x18009f266  mov     rcx, [rsp+58h]; this
0x18009f26b  mov     dword ptr [rsp+58h+var_30], eax; wil::details *
0x18009f26f  lea     rax, aCoinitializeex_0; "CoInitializeEx(nullptr, COINIT_MULTITHR"...
0x18009f276  mov     [rsp+58h+ppv], rax; char *
0x18009f27b  lea     r9, aRegisterlocati_0; "RegisterLocationCOMServer"
0x18009f282  lea     r8, aOnecoreuapDriv_80; "onecoreuap\\drivers\\mobilepc\\location"...
0x18009f289  mov     edx, 8Bh; void *
0x18009f28e  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18009f293  jmp     loc_18009F364
0x18009f298  xor     ebx, ebx
0x18009f29a  mov     [rsp+58h+arg_0], 1
0x18009f29f  lea     rdx, qword_1801E4250
0x18009f2a6  lea     rcx, [rsp+58h+var_18]
0x18009f2ab  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x18009f2b0  nop
0x18009f2b1  cmp     cs:ppv, rbx
0x18009f2b8  jnz     loc_18009F353
0x18009f2be  lea     rax, ppv
0x18009f2c5  mov     [rsp+58h+ppv], rax; ppv
0x18009f2ca  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x18009f2d1  xor     edx, edx; pUnkOuter
0x18009f2d3  lea     r8d, [rbx+1]; dwClsContext
0x18009f2d7  lea     rcx, CLSID_ContextSwitcher; rclsid
0x18009f2de  call    cs:__imp_CoCreateInstance
0x18009f2e4  mov     ebx, eax
0x18009f2e6  test    eax, eax
0x18009f2e8  js      short loc_18009F353
0x18009f2ea  mov     rcx, cs:ppv
0x18009f2f1  mov     rax, [rcx]
0x18009f2f4  mov     [rsp+58h+var_30], 0
0x18009f2fd  mov     dword ptr [rsp+58h+ppv], 5
0x18009f305  lea     r9, IID_IContextCallback
0x18009f30c  xor     r8d, r8d
0x18009f30f  lea     rdx, ?RegisterServerInContext@@YAJPEAUtagComCallData@@@Z; RegisterServerInContext(tagComCallData *)
0x18009f316  mov     rax, [rax+18h]
0x18009f31a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f31f  mov     ebx, eax
0x18009f321  mov     rcx, [rsp+58h]; this
0x18009f326  test    eax, eax
0x18009f328  jns     short loc_18009F353
0x18009f32a  mov     dword ptr [rsp+58h+var_30], eax; char *
0x18009f32e  lea     rax, aGPlocservercon_0; "g_pLocServerContext->ContextCallback( R"...
0x18009f335  mov     [rsp+58h+ppv], rax; char *
0x18009f33a  lea     r9, aRegisterlocati_0; "RegisterLocationCOMServer"
0x18009f341  lea     r8, aOnecoreuapDriv_80; "onecoreuap\\drivers\\mobilepc\\location"...
0x18009f348  mov     edx, 96h; void *
0x18009f34d  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18009f352  nop
0x18009f353  lea     rcx, [rsp+58h+var_18]
0x18009f358  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18009f35d  nop
0x18009f35e  call    cs:__imp_CoUninitialize
0x18009f364  mov     eax, ebx
0x18009f366  add     rsp, 50h
0x18009f36a  pop     rbx
0x18009f36b  retn
```
