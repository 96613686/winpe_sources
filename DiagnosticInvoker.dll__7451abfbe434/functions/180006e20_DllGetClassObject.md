# DllGetClassObject

- ea: `0x180006e20`
- end: `0x180006f1f`
- name: `DllGetClassObject`
- size: `255`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180006a64`
- `0x180006e20`
- `0x180011010`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180006eec`
- `RPCRT4!NdrDllGetClassObject` at `0x180006eec`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180006e46`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180006e46`

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
  byte_18001D5D8 = 1;
  *ppv = 0;
  v6 = (const struct _GUID **)((*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                                                    + 32))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_)
                             + 8);
  v7 = (*(__int64 (__fastcall **)(__int64 *))(Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
                                            + 40))(&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_);
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
0x180006e20  push    rbx
0x180006e22  push    rbp
0x180006e23  push    rsi
0x180006e24  push    rdi
0x180006e25  sub     rsp, 38h
0x180006e29  mov     rsi, r8
0x180006e2c  mov     rbp, rdx
0x180006e2f  mov     rdi, rcx
0x180006e32  xor     r9d, r9d; Context
0x180006e35  xor     r8d, r8d; Parameter
0x180006e38  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180006e3f  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x180006e46  call    cs:__imp_InitOnceExecuteOnce
0x180006e4c  mov     cs:byte_18001D5D8, 1
0x180006e53  mov     qword ptr [rsi], 0
0x180006e5a  mov     rax, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180006e61  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180006e68  mov     rax, [rax+20h]
0x180006e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e71  lea     rbx, [rax+8]
0x180006e75  mov     rcx, cs:?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180006e7c  mov     rax, [rcx+28h]
0x180006e80  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int> Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_
0x180006e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e8c  mov     rdx, rax
0x180006e8f  cmp     rbx, rax
0x180006e92  jnb     short loc_180006EBB
0x180006e94  mov     r9, [rbx]; struct _GUID *
0x180006e97  test    r9, r9
0x180006e9a  jz      short loc_180006EB2
0x180006e9c  mov     rax, [r9+8]
0x180006ea0  mov     rcx, [rax]
0x180006ea3  cmp     rcx, [rdi]
0x180006ea6  jnz     short loc_180006EB2
0x180006ea8  mov     rax, [rax+8]
0x180006eac  cmp     rax, [rdi+8]
0x180006eb0  jz      short loc_180006EFB
0x180006eb2  add     rbx, 8
0x180006eb6  cmp     rbx, rdx
0x180006eb9  jb      short loc_180006E94
0x180006ebb  mov     eax, 80040111h
0x180006ec0  test    eax, eax
0x180006ec2  jns     short loc_180006EF2
0x180006ec4  lea     rax, gPFactory
0x180006ecb  mov     [rsp+58h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180006ed0  lea     rax, CLSID_PSFactoryBuffer
0x180006ed7  mov     [rsp+58h+pclsid], rax; pclsid
0x180006edc  lea     r9, aProxyFileList; pProxyFileList
0x180006ee3  mov     r8, rsi; ppv
0x180006ee6  mov     rdx, rbp; riid
0x180006ee9  mov     rcx, rdi; rclsid
0x180006eec  call    cs:__imp_NdrDllGetClassObject
0x180006ef2  add     rsp, 38h
0x180006ef6  pop     rdi
0x180006ef7  pop     rsi
0x180006ef8  pop     rbp
0x180006ef9  pop     rbx
0x180006efa  retn
0x180006efb  mov     [rsp+58h+arg_10], 1
0x180006f03  mov     [rsp+58h+pclsid], rsi; Ptr
0x180006f08  mov     r8, rbp; unsigned int *
0x180006f0b  lea     rdx, [rsp+58h+arg_10]; struct Microsoft::WRL::Details::ModuleBase *
0x180006f10  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x180006f17  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180006f1c  jmp     short loc_180006EC0
```
