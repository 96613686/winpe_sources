# DllGetClassObject

- ea: `0x18000b030`
- end: `0x18000b10a`
- name: `DllGetClassObject`
- size: `218`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007244`
- `0x18000b030`
- `0x18002c010`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x18000b0db`
- `RPCRT4!NdrDllGetClassObject` at `0x18000b0db`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const struct _GUID **v6; // rbx
  unsigned __int64 v7; // rdx
  const struct _GUID *v8; // r9
  __int64 v9; // rax
  Microsoft::WRL::Details *v10; // rcx
  int CacheEntry; // eax
  struct IUnknown **pPSFactoryBuffer; // [rsp+28h] [rbp-30h]
  int v14; // [rsp+70h] [rbp+18h] BYREF

  *ppv = 0;
  v6 = (const struct _GUID **)((*(__int64 (__fastcall **)(void *))(WpcDesktop::OTS::ManagerDLL::InProcComServerModule
                                                                 + 32LL))(&WpcDesktop::OTS::ManagerDLL::InProcComServerModule)
                             + 8);
  v7 = (*(__int64 (__fastcall **)(void *))(WpcDesktop::OTS::ManagerDLL::InProcComServerModule + 40LL))(&WpcDesktop::OTS::ManagerDLL::InProcComServerModule);
  if ( (unsigned __int64)v6 >= v7 )
  {
LABEL_6:
    CacheEntry = -2147221231;
  }
  else
  {
    while ( 1 )
    {
      v8 = *v6;
      if ( *v6 )
      {
        v9 = *(_QWORD *)v8->Data4;
        v10 = *(Microsoft::WRL::Details **)v9;
        if ( *(_QWORD *)v9 == *(_QWORD *)&rclsid->Data1 && *(_QWORD *)(v9 + 8) == *(_QWORD *)rclsid->Data4 )
          break;
      }
      if ( (unsigned __int64)++v6 >= v7 )
        goto LABEL_6;
    }
    v14 = 1;
    CacheEntry = Microsoft::WRL::Details::GetCacheEntry(
                   v10,
                   (struct Microsoft::WRL::Details::ModuleBase *)&v14,
                   &riid->Data1,
                   v8,
                   (const struct Microsoft::WRL::Details::CreatorMap *)ppv,
                   pPSFactoryBuffer);
  }
  if ( CacheEntry )
    return NdrDllGetClassObject(
             rclsid,
             riid,
             ppv,
             (const ProxyFileInfo **)&aProxyFileList,
             &CLSID_PSFactoryBuffer,
             &gPFactory);
  else
    return 0;
}

```

## disassembly

```asm
0x18000b030  push    rbx
0x18000b032  push    rbp
0x18000b033  push    rsi
0x18000b034  push    rdi
0x18000b035  sub     rsp, 38h
0x18000b039  mov     rsi, r8
0x18000b03c  mov     rbp, rdx
0x18000b03f  mov     rdi, rcx
0x18000b042  mov     qword ptr [r8], 0
0x18000b049  mov     rax, cs:?InProcComServerModule@ManagerDLL@OTS@WpcDesktop@@3VWrlModule@WpcBase@@A; WpcBase::WrlModule WpcDesktop::OTS::ManagerDLL::InProcComServerModule
0x18000b050  lea     rcx, ?InProcComServerModule@ManagerDLL@OTS@WpcDesktop@@3VWrlModule@WpcBase@@A; WpcBase::WrlModule WpcDesktop::OTS::ManagerDLL::InProcComServerModule
0x18000b057  mov     rax, [rax+20h]
0x18000b05b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b060  lea     rbx, [rax+8]
0x18000b064  mov     rdx, cs:?InProcComServerModule@ManagerDLL@OTS@WpcDesktop@@3VWrlModule@WpcBase@@A; WpcBase::WrlModule WpcDesktop::OTS::ManagerDLL::InProcComServerModule
0x18000b06b  lea     rcx, ?InProcComServerModule@ManagerDLL@OTS@WpcDesktop@@3VWrlModule@WpcBase@@A; WpcBase::WrlModule WpcDesktop::OTS::ManagerDLL::InProcComServerModule
0x18000b072  mov     rax, [rdx+28h]
0x18000b076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b07b  mov     rdx, rax
0x18000b07e  cmp     rbx, rax
0x18000b081  jnb     short loc_18000B0AA
0x18000b083  mov     r9, [rbx]; struct _GUID *
0x18000b086  test    r9, r9
0x18000b089  jz      short loc_18000B0A1
0x18000b08b  mov     rax, [r9+8]
0x18000b08f  mov     rcx, [rax]; this
0x18000b092  cmp     rcx, [rdi]
0x18000b095  jnz     short loc_18000B0A1
0x18000b097  mov     rax, [rax+8]
0x18000b09b  cmp     rax, [rdi+8]
0x18000b09f  jz      short loc_18000B0E3
0x18000b0a1  add     rbx, 8
0x18000b0a5  cmp     rbx, rdx
0x18000b0a8  jb      short loc_18000B083
0x18000b0aa  mov     eax, 80040111h
0x18000b0af  test    eax, eax
0x18000b0b1  jz      short loc_18000B0FF
0x18000b0b3  lea     rax, gPFactory
0x18000b0ba  mov     [rsp+58h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x18000b0bf  lea     rax, CLSID_PSFactoryBuffer
0x18000b0c6  mov     [rsp+58h+pclsid], rax; pclsid
0x18000b0cb  lea     r9, aProxyFileList; pProxyFileList
0x18000b0d2  mov     r8, rsi; ppv
0x18000b0d5  mov     rdx, rbp; riid
0x18000b0d8  mov     rcx, rdi; rclsid
0x18000b0db  call    cs:__imp_NdrDllGetClassObject
0x18000b0e1  jmp     short loc_18000B101
0x18000b0e3  mov     [rsp+58h+arg_10], 1
0x18000b0eb  mov     [rsp+58h+pclsid], rsi; struct Microsoft::WRL::Details::CreatorMap *
0x18000b0f0  mov     r8, rbp; unsigned int *
0x18000b0f3  lea     rdx, [rsp+58h+arg_10]; struct Microsoft::WRL::Details::ModuleBase *
0x18000b0f8  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x18000b0fd  jmp     short loc_18000B0AF
0x18000b0ff  xor     eax, eax
0x18000b101  add     rsp, 38h
0x18000b105  pop     rdi
0x18000b106  pop     rsi
0x18000b107  pop     rbp
0x18000b108  pop     rbx
0x18000b109  retn
```
