# DllGetClassObject

- ea: `0x180004110`
- end: `0x180004209`
- name: `DllGetClassObject`
- size: `249`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003a00`
- `0x180004110`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180004136`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180004136`
- `RPCRT4!NdrDllGetClassObject` at `0x1800041fa`
- `RPCRT4!NdrDllGetClassObject` at `0x1800041fa`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const struct _GUID **v6; // rbx
  unsigned __int64 v7; // rdx
  const struct _GUID *v8; // r9
  _QWORD *v9; // rax
  HRESULT result; // eax
  struct IUnknown **pPSFactoryBuffer; // [rsp+28h] [rbp-30h]
  int v12; // [rsp+70h] [rbp+18h] BYREF

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  byte_18000C8B8 = 1;
  *ppv = 0;
  v6 = (const struct _GUID **)((*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                                    + 32))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
                             + 8);
  v7 = (*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                            + 40))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
  if ( (unsigned __int64)v6 >= v7 )
    return NdrDllGetClassObject(
             rclsid,
             riid,
             ppv,
             (const ProxyFileInfo **)&aProxyFileList,
             &CLSID_PSFactoryBuffer,
             &gPFactory);
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
      return NdrDllGetClassObject(
               rclsid,
               riid,
               ppv,
               (const ProxyFileInfo **)&aProxyFileList,
               &CLSID_PSFactoryBuffer,
               &gPFactory);
  }
  v12 = 1;
  result = Microsoft::WRL::Details::GetCacheEntry(
             (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
             (struct Microsoft::WRL::Details::ModuleBase *)&v12,
             &riid->Data1,
             v8,
             ppv,
             pPSFactoryBuffer);
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
0x180004110  push    rbx
0x180004112  push    rbp
0x180004113  push    rsi
0x180004114  push    rdi
0x180004115  sub     rsp, 38h
0x180004119  mov     rsi, r8
0x18000411c  mov     rbp, rdx
0x18000411f  mov     rdi, rcx
0x180004122  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180004129  xor     r8d, r8d; Parameter
0x18000412c  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180004133  xor     r9d, r9d; Context
0x180004136  call    cs:__imp_InitOnceExecuteOnce
0x18000413c  mov     cs:byte_18000C8B8, 1
0x180004143  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x18000414a  mov     qword ptr [rsi], 0
0x180004151  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180004158  mov     rax, [rax+20h]
0x18000415c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004161  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180004168  lea     rbx, [rax+8]
0x18000416c  mov     rax, [rcx+28h]
0x180004170  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180004177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000417c  mov     rdx, rax
0x18000417f  cmp     rbx, rax
0x180004182  jnb     short loc_1800041D2
0x180004184  mov     r9, [rbx]; struct _GUID *
0x180004187  test    r9, r9
0x18000418a  jz      short loc_1800041A2
0x18000418c  mov     rax, [r9+8]
0x180004190  mov     rcx, [rax]
0x180004193  cmp     rcx, [rdi]
0x180004196  jnz     short loc_1800041A2
0x180004198  mov     rax, [rax+8]
0x18000419c  cmp     rax, [rdi+8]
0x1800041a0  jz      short loc_1800041AD
0x1800041a2  add     rbx, 8
0x1800041a6  cmp     rbx, rdx
0x1800041a9  jb      short loc_180004184
0x1800041ab  jmp     short loc_1800041D2
0x1800041ad  mov     r8, rbp; unsigned int *
0x1800041b0  mov     [rsp+58h+arg_10], 1
0x1800041b8  lea     rdx, [rsp+58h+arg_10]; struct Microsoft::WRL::Details::ModuleBase *
0x1800041bd  mov     [rsp+58h+pclsid], rsi; Ptr
0x1800041c2  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x1800041c9  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x1800041ce  test    eax, eax
0x1800041d0  jns     short loc_180004200
0x1800041d2  lea     rax, gPFactory
0x1800041d9  mov     r8, rsi; ppv
0x1800041dc  mov     [rsp+58h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x1800041e1  lea     r9, aProxyFileList; pProxyFileList
0x1800041e8  lea     rax, CLSID_PSFactoryBuffer
0x1800041ef  mov     rdx, rbp; riid
0x1800041f2  mov     rcx, rdi; rclsid
0x1800041f5  mov     [rsp+58h+pclsid], rax; pclsid
0x1800041fa  call    cs:__imp_NdrDllGetClassObject
0x180004200  add     rsp, 38h
0x180004204  pop     rdi
0x180004205  pop     rsi
0x180004206  pop     rbp
0x180004207  pop     rbx
0x180004208  retn
```
