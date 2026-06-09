# Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>(uchar,uchar,uchar,uchar,void *,ulong)

- ea: `0x1800050e4`
- end: `0x1800053bf`
- name: `??$Initialize@USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@34@@ServiceModuleBase@Internal@Windows@@QEAAJEEEEPEAXK@Z`
- size: `731`
- prototype: `__int64 __fastcall(_DWORD *, char, char, __int64, char, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180007980`

## callees

- `0x180004d1c`
- `0x1800050e4`
- `0x1800053c8`
- `0x180009fc0`
- `0x18000c4cc`
- `0x18000d58c`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800051c2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005314`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800051c2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005314`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180005126`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180005126`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1800052b9`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x1800052b9`

## string_xrefs

- `0x18000513c`: `onecore\internal\com\inc\comservicehelper.h`
- `0x180005178`: `onecore\internal\com\inc\comservicehelper.h`
- `0x1800051d5`: `onecore\internal\com\inc\comservicehelper.h`
- `0x180005225`: `onecore\internal\com\inc\comservicehelper.h`
- `0x180005274`: `onecore\internal\com\inc\comservicehelper.h`
- `0x1800052cc`: `onecore\internal\com\inc\comservicehelper.h`
- `0x180005327`: `onecore\internal\com\inc\comservicehelper.h`
- `0x180005385`: `onecore\internal\com\inc\comservicehelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Internal::ServiceModuleBase::Initialize<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>(
        _DWORD *a1,
        char a2,
        char a3,
        __int64 a4,
        char a5,
        __int64 a6,
        unsigned int a7)
{
  Windows::Internal::ServiceModuleBase *v10; // rbx
  int v11; // eax
  __int64 v12; // rcx
  unsigned int v13; // esi
  int v15; // eax
  HRESULT v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  HRESULT Instance; // eax
  int v21; // eax
  unsigned int v22; // edi
  int ppv; // [rsp+20h] [rbp-40h]
  int ppva; // [rsp+20h] [rbp-40h]
  _BYTE v25[8]; // [rsp+40h] [rbp-20h] BYREF
  Windows::Internal::ServiceModuleBase *v26; // [rsp+48h] [rbp-18h]
  char v27; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  LPVOID v29; // [rsp+90h] [rbp+30h] BYREF

  v10 = *(Windows::Internal::ServiceModuleBase **)_lambda_5b5155d6716aa02bd4bfa3a7051e2a37_::_lambda_5b5155d6716aa02bd4bfa3a7051e2a37_(
                                                    v25,
                                                    a1);
  v26 = v10;
  v27 = 1;
  v11 = RoInitialize(1);
  v13 = v11;
  a1[4] = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
      (const char *)(unsigned int)v11,
      ppv);
    Windows::Internal::ServiceModuleBase::Uninitialize(v10);
    return v13;
  }
  if ( a2 )
  {
    v15 = Windows::Internal::ServiceModuleBase::InitializeSecurity<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal>(v12);
    v13 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6C,
        (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
        (const char *)(unsigned int)v15,
        ppv);
      Windows::Internal::ServiceModuleBase::Uninitialize(v10);
      return v13;
    }
    v29 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
    v16 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &v29);
    v13 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x73,
        (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
        (const char *)(unsigned int)v16,
        ppv);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
      Windows::Internal::ServiceModuleBase::Uninitialize(v10);
      return v13;
    }
    v17 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v29 + 24LL))(v29, 1, 2);
    v13 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x74,
        (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
        (const char *)(unsigned int)v17,
        ppv);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
      Windows::Internal::ServiceModuleBase::Uninitialize(v10);
      return v13;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  }
  v18 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)a1 + 32LL))(a1);
  v13 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7B,
      (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
      (const char *)(unsigned int)v18,
      ppv);
    Windows::Internal::ServiceModuleBase::Uninitialize(v10);
    return v13;
  }
  if ( a3 )
  {
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)a1 + 16LL))(a1);
    *((_BYTE *)a1 + 20) = 1;
  }
  if ( a5 )
  {
    v19 = CoRegisterServerShutdownDelay(a6, a7);
    v13 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x89,
        (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
        (const char *)(unsigned int)v19,
        ppv);
      Windows::Internal::ServiceModuleBase::Uninitialize(v10);
      return v13;
    }
    *((_BYTE *)a1 + 21) = 1;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 6);
  Instance = CoCreateInstance(
               &CLSID_ContextSwitcher,
               0,
               1u,
               &GUID_000001da_0000_0000_c000_000000000046,
               (LPVOID *)a1 + 3);
  v13 = Instance;
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
      (const char *)(unsigned int)Instance,
      ppva);
    Windows::Internal::ServiceModuleBase::Uninitialize(v10);
    return v13;
  }
  v21 = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall *)(struct tagComCallData *), _DWORD *, GUID *))(**((_QWORD **)a1 + 3) + 24LL))(
          *((_QWORD *)a1 + 3),
          Windows::Internal::ServiceModuleBase::ConnectCallbackThunk,
          a1,
          &IID_IContextCallback);
  v22 = v21;
  if ( v21 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x90,
    (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
    (const char *)(unsigned int)v21,
    5);
  Windows::Internal::ServiceModuleBase::Uninitialize(v10);
  return v22;
}

```

## disassembly

```asm
0x1800050e4  mov     [rsp-28h+arg_8], rbx
0x1800050e9  mov     [rsp-28h+arg_10], rsi
0x1800050ee  push    rbp
0x1800050ef  push    rdi
0x1800050f0  push    r13
0x1800050f2  push    r14
0x1800050f4  push    r15
0x1800050f6  mov     rbp, rsp
0x1800050f9  sub     rsp, 60h
0x1800050fd  mov     r15b, r8b
0x180005100  mov     r14b, dl
0x180005103  mov     rdi, rcx
0x180005106  mov     rdx, rcx
0x180005109  lea     rcx, [rbp+var_20]
0x18000510d  call    ??0_lambda_5b5155d6716aa02bd4bfa3a7051e2a37_@@QEAA@PEAV?$Service@VMcpManagementService@@$01USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@Z; _lambda_5b5155d6716aa02bd4bfa3a7051e2a37_::_lambda_5b5155d6716aa02bd4bfa3a7051e2a37_(Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor> *)
0x180005112  mov     rbx, [rax]
0x180005115  mov     [rbp+var_18], rbx
0x180005119  mov     r13d, 1
0x18000511f  mov     [rbp+var_10], r13b
0x180005123  mov     ecx, r13d
0x180005126  call    cs:__imp_RoInitialize
0x18000512c  mov     esi, eax
0x18000512e  mov     [rdi+10h], eax
0x180005131  test    eax, eax
0x180005133  jns     short loc_18000515D
0x180005135  mov     rcx, [rbp+28h]; this
0x180005139  mov     r9d, eax; char *
0x18000513c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x180005143  lea     edx, [r13+62h]; void *
0x180005147  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000514c  nop
0x18000514d  mov     rcx, rbx; this
0x180005150  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x180005155  nop
0x180005156  mov     eax, esi
0x180005158  jmp     loc_1800053A6
0x18000515d  test    r14b, r14b
0x180005160  jz      loc_180005258
0x180005166  call    ??$InitializeSecurity@USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@@ServiceModuleBase@Internal@Windows@@IEAAJXZ; Windows::Internal::ServiceModuleBase::InitializeSecurity<Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal>(void)
0x18000516b  mov     esi, eax
0x18000516d  test    eax, eax
0x18000516f  jns     short loc_180005195
0x180005171  mov     rcx, [rbp+28h]; this
0x180005175  mov     r9d, eax; char *
0x180005178  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x18000517f  mov     edx, 6Ch ; 'l'; void *
0x180005184  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005189  nop
0x18000518a  mov     rcx, rbx; this
0x18000518d  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x180005192  nop
0x180005193  jmp     short loc_180005156
0x180005195  mov     [rbp+arg_0], 0
0x18000519d  lea     rcx, [rbp+arg_0]
0x1800051a1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800051a6  lea     rax, [rbp+arg_0]
0x1800051aa  mov     [rsp+60h+ppv], rax; int
0x1800051af  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1800051b6  mov     r8d, r13d; dwClsContext
0x1800051b9  xor     edx, edx; pUnkOuter
0x1800051bb  lea     rcx, CLSID_GlobalOptions; rclsid
0x1800051c2  call    cs:__imp_CoCreateInstance
0x1800051c8  mov     esi, eax
0x1800051ca  test    eax, eax
0x1800051cc  jns     short loc_1800051FF
0x1800051ce  mov     rcx, [rbp+28h]; this
0x1800051d2  mov     r9d, eax; char *
0x1800051d5  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x1800051dc  mov     edx, 73h ; 's'; void *
0x1800051e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800051e6  nop
0x1800051e7  lea     rcx, [rbp+arg_0]
0x1800051eb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800051f0  nop
0x1800051f1  mov     rcx, rbx; this
0x1800051f4  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x1800051f9  nop
0x1800051fa  jmp     loc_180005156
0x1800051ff  mov     rcx, [rbp+arg_0]
0x180005203  mov     rax, [rcx]
0x180005206  mov     r8d, 2
0x18000520c  mov     edx, r13d
0x18000520f  mov     rax, [rax+18h]
0x180005213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005218  mov     esi, eax
0x18000521a  test    eax, eax
0x18000521c  jns     short loc_18000524F
0x18000521e  mov     rcx, [rbp+28h]; this
0x180005222  mov     r9d, eax; char *
0x180005225  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x18000522c  mov     edx, 74h ; 't'; void *
0x180005231  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005236  nop
0x180005237  lea     rcx, [rbp+arg_0]
0x18000523b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180005240  nop
0x180005241  mov     rcx, rbx; this
0x180005244  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x180005249  nop
0x18000524a  jmp     loc_180005156
0x18000524f  lea     rcx, [rbp+arg_0]
0x180005253  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180005258  mov     rax, [rdi]
0x18000525b  mov     rcx, rdi
0x18000525e  mov     rax, [rax+20h]
0x180005262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005267  mov     esi, eax
0x180005269  test    eax, eax
0x18000526b  jns     short loc_180005294
0x18000526d  mov     rcx, [rbp+28h]; this
0x180005271  mov     r9d, eax; char *
0x180005274  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x18000527b  mov     edx, 7Bh ; '{'; void *
0x180005280  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005285  nop
0x180005286  mov     rcx, rbx; this
0x180005289  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x18000528e  nop
0x18000528f  jmp     loc_180005156
0x180005294  test    r15b, r15b
0x180005297  jz      short loc_1800052AC
0x180005299  mov     rax, [rdi]
0x18000529c  mov     rcx, rdi
0x18000529f  mov     rax, [rax+10h]
0x1800052a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052a8  mov     [rdi+14h], r13b
0x1800052ac  cmp     [rbp+arg_20], 0
0x1800052b0  jz      short loc_1800052F0
0x1800052b2  mov     edx, [rbp+arg_30]
0x1800052b5  mov     rcx, [rbp+arg_28]
0x1800052b9  call    cs:__imp_CoRegisterServerShutdownDelay
0x1800052bf  mov     esi, eax
0x1800052c1  test    eax, eax
0x1800052c3  jns     short loc_1800052EC
0x1800052c5  mov     rcx, [rbp+28h]; this
0x1800052c9  mov     r9d, eax; char *
0x1800052cc  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x1800052d3  mov     edx, 89h; void *
0x1800052d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800052dd  nop
0x1800052de  mov     rcx, rbx; this
0x1800052e1  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x1800052e6  nop
0x1800052e7  jmp     loc_180005156
0x1800052ec  mov     [rdi+15h], r13b
0x1800052f0  lea     r14, [rdi+18h]
0x1800052f4  mov     rcx, r14
0x1800052f7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800052fc  mov     [rsp+60h+ppv], r14; int
0x180005301  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x180005308  mov     r8d, r13d; dwClsContext
0x18000530b  xor     edx, edx; pUnkOuter
0x18000530d  lea     rcx, CLSID_ContextSwitcher; rclsid
0x180005314  call    cs:__imp_CoCreateInstance
0x18000531a  mov     esi, eax
0x18000531c  test    eax, eax
0x18000531e  jns     short loc_180005347
0x180005320  mov     rcx, [rbp+28h]; this
0x180005324  mov     r9d, eax; char *
0x180005327  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x18000532e  mov     edx, 8Dh; void *
0x180005333  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005338  nop
0x180005339  mov     rcx, rbx; this
0x18000533c  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x180005341  nop
0x180005342  jmp     loc_180005156
0x180005347  mov     rcx, [r14]
0x18000534a  mov     rax, [rcx]
0x18000534d  mov     [rsp+60h+var_38], 0
0x180005356  mov     dword ptr [rsp+60h+ppv], 5; int
0x18000535e  lea     r9, IID_IContextCallback
0x180005365  mov     r8, rdi
0x180005368  lea     rdx, ?ConnectCallbackThunk@ServiceModuleBase@Internal@Windows@@SAJPEAUtagComCallData@@@Z; Windows::Internal::ServiceModuleBase::ConnectCallbackThunk(tagComCallData *)
0x18000536f  mov     rax, [rax+18h]
0x180005373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005378  mov     edi, eax
0x18000537a  test    eax, eax
0x18000537c  jns     short loc_1800053A4
0x18000537e  mov     rcx, [rbp+28h]; this
0x180005382  mov     r9d, eax; char *
0x180005385  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x18000538c  mov     edx, 90h; void *
0x180005391  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005396  nop
0x180005397  mov     rcx, rbx; this
0x18000539a  call    ?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ; Windows::Internal::ServiceModuleBase::Uninitialize(void)
0x18000539f  nop
0x1800053a0  mov     eax, edi
0x1800053a2  jmp     short loc_1800053A6
0x1800053a4  xor     eax, eax
0x1800053a6  lea     r11, [rsp+60h+var_s0]
0x1800053ab  mov     rbx, [r11+38h]
0x1800053af  mov     rsi, [r11+40h]
0x1800053b3  mov     rsp, r11
0x1800053b6  pop     r15
0x1800053b8  pop     r14
0x1800053ba  pop     r13
0x1800053bc  pop     rdi
0x1800053bd  pop     rbp
0x1800053be  retn
```
