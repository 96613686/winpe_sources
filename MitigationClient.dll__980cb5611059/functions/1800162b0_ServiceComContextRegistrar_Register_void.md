# ServiceComContextRegistrar::Register(void)

- ea: `0x1800162b0`
- end: `0x1800163bf`
- name: `?Register@ServiceComContextRegistrar@@QEAAJXZ`
- size: `271`
- prototype: `__int64 __fastcall(ServiceComContextRegistrar *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800164a4`

## callees

- `0x18001055c`
- `0x18001208c`
- `0x1800162b0`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800162eb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800162eb`

## string_xrefs

- `0x180016353`: `onecore\base\diagnosis\mitigation\client\dll\ServiceComContextRegistrar.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ServiceComContextRegistrar::Register(ServiceComContextRegistrar *this)
{
  HRESULT v1; // eax
  unsigned int v2; // ebx
  __int64 v3; // rdx
  __int64 v4; // rax
  LPVOID v5; // rbx
  int ppv; // [rsp+20h] [rbp-38h]
  _QWORD v8[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  LPVOID v10; // [rsp+60h] [rbp+8h] BYREF
  __int64 v11; // [rsp+68h] [rbp+10h] BYREF

  v10 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v10);
  v1 = CoCreateInstance(&CLSID_ContextSwitcher, 0, 1u, &GUID_000001da_0000_0000_c000_000000000046, &v10);
  v2 = v1;
  if ( v1 < 0 )
  {
    v3 = 34;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\dll\\ServiceComContextRegistrar.h",
      (const char *)(unsigned int)v1,
      ppv);
    goto LABEL_11;
  }
  v8[0] = 0;
  v8[1] = &g_comContext;
  ppv = 5;
  v1 = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall *)(struct tagComCallData *), _QWORD *, GUID *))(*(_QWORD *)v10 + 24LL))(
         v10,
         _lambda_d7ce99473317898eb18c6690ecaed21a_::_lambda_invoker_cdecl_,
         v8,
         &IID_IContextCallback);
  v2 = v1;
  if ( v1 < 0 )
  {
    v3 = 64;
    goto LABEL_5;
  }
  v4 = g_comContext;
  v5 = v10;
  if ( (LPVOID)g_comContext != v10 )
  {
    if ( v10 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 8LL))(v10);
      v4 = g_comContext;
    }
    v11 = v4;
    g_comContext = v5;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v11);
  }
  v2 = 0;
LABEL_11:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v10);
  return v2;
}

```

## disassembly

```asm
0x1800162b0  mov     [rsp+arg_0], rcx
0x1800162b5  push    rbx
0x1800162b6  sub     rsp, 50h
0x1800162ba  mov     [rsp+58h+arg_0], 0
0x1800162c3  lea     rcx, [rsp+58h+arg_0]
0x1800162c8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800162cd  lea     rax, [rsp+58h+arg_0]
0x1800162d2  mov     [rsp+58h+ppv], rax; ppv
0x1800162d7  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x1800162de  xor     edx, edx; pUnkOuter
0x1800162e0  lea     r8d, [rdx+1]; dwClsContext
0x1800162e4  lea     rcx, CLSID_ContextSwitcher; rclsid
0x1800162eb  call    cs:__imp_CoCreateInstance
0x1800162f1  mov     ebx, eax
0x1800162f3  test    eax, eax
0x1800162f5  jns     short loc_1800162FE
0x1800162f7  mov     edx, 22h ; '"'
0x1800162fc  jmp     short loc_180016353
0x1800162fe  mov     [rsp+58h+var_18], 0
0x180016307  lea     rax, ?g_comContext@@3VServiceComContextRegistrar@@A; ServiceComContextRegistrar g_comContext
0x18001630e  mov     [rsp+58h+var_10], rax
0x180016313  mov     rcx, [rsp+58h+arg_0]
0x180016318  mov     rax, [rcx]
0x18001631b  mov     [rsp+58h+var_30], 0
0x180016324  mov     dword ptr [rsp+58h+ppv], 5; int
0x18001632c  lea     r9, IID_IContextCallback
0x180016333  lea     r8, [rsp+58h+var_18]
0x180016338  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_d7ce99473317898eb18c6690ecaed21a_@@CA@PEAUtagComCallData@@@Z; _lambda_d7ce99473317898eb18c6690ecaed21a_::_lambda_invoker_cdecl_(tagComCallData *)
0x18001633f  mov     rax, [rax+18h]
0x180016343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016348  mov     ebx, eax
0x18001634a  test    eax, eax
0x18001634c  jns     short loc_180016369
0x18001634e  mov     edx, 40h ; '@'; void *
0x180016353  lea     r8, aOnecoreBaseDia_21; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001635a  mov     r9d, eax; char *
0x18001635d  mov     rcx, [rsp+58h]; this
0x180016362  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016367  jmp     short loc_1800163AD
0x180016369  mov     rax, cs:?g_comContext@@3VServiceComContextRegistrar@@A; ServiceComContextRegistrar g_comContext
0x180016370  mov     rbx, [rsp+58h+arg_0]
0x180016375  cmp     rax, rbx
0x180016378  jz      short loc_1800163AB
0x18001637a  test    rbx, rbx
0x18001637d  jz      short loc_180016395
0x18001637f  mov     rax, [rbx]
0x180016382  mov     rcx, rbx
0x180016385  mov     rax, [rax+8]
0x180016389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001638e  mov     rax, cs:?g_comContext@@3VServiceComContextRegistrar@@A; ServiceComContextRegistrar g_comContext
0x180016395  mov     [rsp+58h+arg_8], rax
0x18001639a  mov     cs:?g_comContext@@3VServiceComContextRegistrar@@A, rbx; ServiceComContextRegistrar g_comContext
0x1800163a1  lea     rcx, [rsp+58h+arg_8]
0x1800163a6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800163ab  xor     ebx, ebx
0x1800163ad  lea     rcx, [rsp+58h+arg_0]
0x1800163b2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800163b7  mov     eax, ebx
0x1800163b9  add     rsp, 50h
0x1800163bd  pop     rbx
0x1800163be  retn
```
