# DllGetClassObject

- ea: `0x18000cf50`
- end: `0x18000cfb8`
- name: `DllGetClassObject`
- size: `104`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180006214`
- `0x18000a128`
- `0x18000cf50`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x18000cf92`
- `RPCRT4!NdrDllGetClassObject` at `0x18000cf92`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  Microsoft::WRL::Details *v6; // rbp
  HRESULT result; // eax

  v6 = (Microsoft::WRL::Details *)Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
  result = NdrDllGetClassObject(
             rclsid,
             riid,
             ppv,
             (const ProxyFileInfo **)&aProxyFileList,
             &CLSID_PSFactoryBuffer,
             &gPFactory);
  if ( result < 0 )
    return Microsoft::WRL::Details::GetClassObject<1>(v6, ppv);
  return result;
}

```

## disassembly

```asm
0x18000cf50  push    rbx
0x18000cf52  push    rbp
0x18000cf53  push    rsi
0x18000cf54  push    rdi
0x18000cf55  sub     rsp, 38h
0x18000cf59  mov     rbx, r8
0x18000cf5c  mov     rdi, rdx
0x18000cf5f  mov     rsi, rcx
0x18000cf62  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x18000cf67  mov     rbp, rax
0x18000cf6a  lea     r9, aProxyFileList; pProxyFileList
0x18000cf71  lea     rax, gPFactory
0x18000cf78  mov     r8, rbx; ppv
0x18000cf7b  mov     [rsp+58h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x18000cf80  mov     rdx, rdi; riid
0x18000cf83  lea     rax, CLSID_PSFactoryBuffer
0x18000cf8a  mov     rcx, rsi; rclsid
0x18000cf8d  mov     [rsp+58h+pclsid], rax; pclsid
0x18000cf92  call    cs:__imp_NdrDllGetClassObject
0x18000cf98  test    eax, eax
0x18000cf9a  jns     short loc_18000CFAF
0x18000cf9c  mov     r9, rdi
0x18000cf9f  mov     [rsp+58h+pclsid], rbx; PVOID
0x18000cfa4  mov     r8, rsi
0x18000cfa7  mov     rcx, rbp; this
0x18000cfaa  call    ??$GetClassObject@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGAEBU_GUID@@2PEAPEAX@Z; Microsoft::WRL::Details::GetClassObject<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,_GUID const &,_GUID const &,void * *)
0x18000cfaf  add     rsp, 38h
0x18000cfb3  pop     rdi
0x18000cfb4  pop     rsi
0x18000cfb5  pop     rbp
0x18000cfb6  pop     rbx
0x18000cfb7  retn
```
