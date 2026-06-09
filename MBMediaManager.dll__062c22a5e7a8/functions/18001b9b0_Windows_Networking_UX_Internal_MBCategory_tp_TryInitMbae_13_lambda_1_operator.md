# _Windows::Networking::UX::Internal::MBCategory::tp_TryInitMbae_::_13_::_lambda_1_::operator()

- ea: `0x18001b9b0`
- end: `0x18001ba8b`
- name: `_Windows::Networking::UX::Internal::MBCategory::tp_TryInitMbae_::_13_::_lambda_1_::operator()`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000ecbc`

## callees

- `0x180002150`
- `0x18001b9b0`
- `0x18001cb10`
- `0x18001f8c8`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x18001b9d6`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x18001b9d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ba06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ba06`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Networking::UX::Internal::MBCategory::tp_TryInitMbae_::_13_::_lambda_1_::operator()(
        __int64 *a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // rsi
  __int64 (__fastcall *v6)(__int64, LPVOID, __int64); // rdi
  __int64 v7; // rbx
  int v8; // eax
  unsigned int v9; // edi
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  LPVOID pv; // [rsp+30h] [rbp+8h] BYREF

  pv = 0;
  v2 = StringFromIID((const IID *const)(*a1 + 24), (LPOLESTR *)&pv);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v4 = *a1;
    v5 = *(_QWORD *)(*a1 + 272);
    v6 = *(__int64 (__fastcall **)(__int64, LPVOID, __int64))(*(_QWORD *)v5 + 24LL);
    v7 = v4 + 280;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v4 + 280);
    v8 = v6(v5, pv, v7);
    v9 = v8;
    if ( v8 >= 0 )
    {
      v3 = 0;
    }
    else
    {
      v3 = -2147023728;
      if ( v8 != -2147023728 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDA3,
          (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
          (const char *)(unsigned int)v8,
          v11);
        v3 = v9;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDA0,
      (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
      (const char *)(unsigned int)v2,
      v11);
    if ( pv )
      CoTaskMemFree(pv);
  }
  return v3;
}

```

## disassembly

```asm
0x18001b9b0  mov     rax, rsp
0x18001b9b3  mov     [rax+10h], rbx
0x18001b9b7  mov     [rax+18h], rsi
0x18001b9bb  push    rdi; int
0x18001b9bc  sub     rsp, 20h
0x18001b9c0  mov     rdi, rcx
0x18001b9c3  mov     qword ptr [rax+8], 0
0x18001b9cb  mov     rcx, [rcx]
0x18001b9ce  add     rcx, 18h; rclsid
0x18001b9d2  lea     rdx, [rax+8]; lplpsz
0x18001b9d6  call    cs:__imp_StringFromIID
0x18001b9dc  mov     ebx, eax
0x18001b9de  test    eax, eax
0x18001b9e0  jns     short loc_18001BA0E
0x18001b9e2  mov     rcx, [rsp+28h]; this
0x18001b9e7  mov     r9d, eax; char *
0x18001b9ea  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18001b9f1  mov     edx, 0DA0h; void *
0x18001b9f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b9fb  nop
0x18001b9fc  mov     rcx, [rsp+28h+pv]; pv
0x18001ba01  test    rcx, rcx
0x18001ba04  jz      short loc_18001BA79
0x18001ba06  call    cs:__imp_CoTaskMemFree
0x18001ba0c  jmp     short loc_18001BA79
0x18001ba0e  mov     rdx, [rdi]
0x18001ba11  mov     rsi, [rdx+110h]
0x18001ba18  mov     rax, [rsi]
0x18001ba1b  mov     rdi, [rax+18h]
0x18001ba1f  lea     rbx, [rdx+118h]
0x18001ba26  mov     rcx, rbx
0x18001ba29  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ba2e  mov     r8, rbx
0x18001ba31  mov     rdx, [rsp+28h+pv]
0x18001ba36  mov     rcx, rsi
0x18001ba39  mov     rax, rdi
0x18001ba3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba41  mov     edi, eax
0x18001ba43  test    eax, eax
0x18001ba45  jns     short loc_18001BA6D
0x18001ba47  mov     ebx, 80070490h
0x18001ba4c  cmp     eax, ebx
0x18001ba4e  jz      short loc_18001BA6F
0x18001ba50  mov     rcx, [rsp+28h]; this
0x18001ba55  mov     r9d, eax; char *
0x18001ba58  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18001ba5f  mov     edx, 0DA3h; void *
0x18001ba64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ba69  mov     ebx, edi
0x18001ba6b  jmp     short loc_18001BA6F
0x18001ba6d  xor     ebx, ebx
0x18001ba6f  lea     rcx, [rsp+28h+pv]
0x18001ba74  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001ba79  mov     eax, ebx
0x18001ba7b  mov     rbx, [rsp+28h+arg_8]
0x18001ba80  mov     rsi, [rsp+28h+arg_10]
0x18001ba85  add     rsp, 20h
0x18001ba89  pop     rdi
0x18001ba8a  retn
```
