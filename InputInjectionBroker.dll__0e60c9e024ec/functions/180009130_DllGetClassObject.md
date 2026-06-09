# DllGetClassObject

- ea: `0x180009130`
- end: `0x18000922f`
- name: `DllGetClassObject`
- size: `255`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008dc4`
- `0x180009130`
- `0x180012010`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x1800091fc`
- `RPCRT4!NdrDllGetClassObject` at `0x1800091fc`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180009156`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180009156`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const struct _GUID **v6; // rbx
  unsigned __int64 v7; // rdx
  const struct _GUID *v8; // r9
  _QWORD *v9; // rax
  HRESULT result; // eax
  int v11; // [rsp+70h] [rbp+18h] BYREF

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_180022C18 = 1;
  *ppv = 0;
  v6 = (const struct _GUID **)((*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                                 + 32LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
                             + 8);
  v7 = (*(__int64 (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                         + 40LL))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
  if ( (unsigned __int64)v6 >= v7 )
  {
LABEL_6:
    result = -2147221231;
  }
  else
  {
    while ( 1 )
    {
      v8 = *v6;
      if ( *v6 )
      {
        v9 = *(_QWORD **)v8->Data4;
        if ( *v9 == *(_QWORD *)&rclsid->Data1 && v9[1] == *(_QWORD *)rclsid->Data4 )
          break;
      }
      if ( (unsigned __int64)++v6 >= v7 )
        goto LABEL_6;
    }
    v11 = 1;
    result = Microsoft::WRL::Details::GetCacheEntry(
               (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
               (struct Microsoft::WRL::Details::ModuleBase *)&v11,
               &riid->Data1,
               v8,
               ppv);
  }
  if ( result < 0 )
    return NdrDllGetClassObject(
             rclsid,
             riid,
             ppv,
             (const ProxyFileInfo **)&aProxyFileList,
             &CLSID_PSFactoryBuffer,
             &gPFactory);
  return result;
}

```

## disassembly

```asm
0x180009130  push    rbx
0x180009132  push    rbp
0x180009133  push    rsi
0x180009134  push    rdi
0x180009135  sub     rsp, 38h
0x180009139  mov     rsi, r8
0x18000913c  mov     rbp, rdx
0x18000913f  mov     rdi, rcx
0x180009142  xor     r9d, r9d; Context
0x180009145  xor     r8d, r8d; Parameter
0x180009148  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000914f  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180009156  call    cs:__imp_InitOnceExecuteOnce
0x18000915c  mov     cs:byte_180022C18, 1
0x180009163  mov     qword ptr [rsi], 0
0x18000916a  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180009171  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180009178  mov     rax, [rax+20h]
0x18000917c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009181  lea     rbx, [rax+8]
0x180009185  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000918c  mov     rax, [rcx+28h]
0x180009190  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180009197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000919c  mov     rdx, rax
0x18000919f  cmp     rbx, rax
0x1800091a2  jnb     short loc_1800091CB
0x1800091a4  mov     r9, [rbx]; struct _GUID *
0x1800091a7  test    r9, r9
0x1800091aa  jz      short loc_1800091C2
0x1800091ac  mov     rax, [r9+8]
0x1800091b0  mov     rcx, [rax]
0x1800091b3  cmp     rcx, [rdi]
0x1800091b6  jnz     short loc_1800091C2
0x1800091b8  mov     rax, [rax+8]
0x1800091bc  cmp     rax, [rdi+8]
0x1800091c0  jz      short loc_18000920B
0x1800091c2  add     rbx, 8
0x1800091c6  cmp     rbx, rdx
0x1800091c9  jb      short loc_1800091A4
0x1800091cb  mov     eax, 80040111h
0x1800091d0  test    eax, eax
0x1800091d2  jns     short loc_180009202
0x1800091d4  lea     rax, gPFactory
0x1800091db  mov     [rsp+58h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x1800091e0  lea     rax, CLSID_PSFactoryBuffer
0x1800091e7  mov     [rsp+58h+pclsid], rax; pclsid
0x1800091ec  lea     r9, aProxyFileList; pProxyFileList
0x1800091f3  mov     r8, rsi; ppv
0x1800091f6  mov     rdx, rbp; riid
0x1800091f9  mov     rcx, rdi; rclsid
0x1800091fc  call    cs:__imp_NdrDllGetClassObject
0x180009202  add     rsp, 38h
0x180009206  pop     rdi
0x180009207  pop     rsi
0x180009208  pop     rbp
0x180009209  pop     rbx
0x18000920a  retn
0x18000920b  mov     [rsp+58h+arg_10], 1
0x180009213  mov     [rsp+58h+pclsid], rsi; Ptr
0x180009218  mov     r8, rbp; unsigned int *
0x18000921b  lea     rdx, [rsp+58h+arg_10]; struct Microsoft::WRL::Details::ModuleBase *
0x180009220  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x180009227  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x18000922c  jmp     short loc_1800091D0
```
