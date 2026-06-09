# DllGetClassObject

- ea: `0x180020380`
- end: `0x1800203f5`
- name: `DllGetClassObject`
- size: `117`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003df0`
- `0x18001d11c`
- `0x180020380`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x1800203df`
- `RPCRT4!NdrDllGetClassObject` at `0x1800203df`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  Microsoft::WRL::Details *v6; // rax
  HRESULT result; // eax

  v6 = (Microsoft::WRL::Details *)Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
  result = Microsoft::WRL::Details::GetClassObject<1>(v6, ppv);
  if ( result == -2147221231 )
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
0x180020380  mov     [rsp+arg_0], rbx
0x180020385  mov     [rsp+arg_8], rsi
0x18002038a  push    rdi
0x18002038b  sub     rsp, 30h
0x18002038f  mov     rbx, r8
0x180020392  mov     rdi, rdx
0x180020395  mov     rsi, rcx
0x180020398  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x18002039d  mov     r9, rdi
0x1800203a0  mov     [rsp+38h+pclsid], rbx; PVOID
0x1800203a5  mov     r8, rsi
0x1800203a8  mov     rcx, rax; this
0x1800203ab  call    ??$GetClassObject@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGAEBU_GUID@@2PEAPEAX@Z; Microsoft::WRL::Details::GetClassObject<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,_GUID const &,_GUID const &,void * *)
0x1800203b0  cmp     eax, 80040111h
0x1800203b5  jnz     short loc_1800203E5
0x1800203b7  lea     rax, gPFactory
0x1800203be  mov     r8, rbx; ppv
0x1800203c1  mov     [rsp+38h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x1800203c6  lea     r9, aProxyFileList; pProxyFileList
0x1800203cd  lea     rax, CLSID_PSFactoryBuffer
0x1800203d4  mov     rdx, rdi; riid
0x1800203d7  mov     rcx, rsi; rclsid
0x1800203da  mov     [rsp+38h+pclsid], rax; pclsid
0x1800203df  call    cs:__imp_NdrDllGetClassObject
0x1800203e5  mov     rbx, [rsp+38h+arg_0]
0x1800203ea  mov     rsi, [rsp+38h+arg_8]
0x1800203ef  add     rsp, 30h
0x1800203f3  pop     rdi
0x1800203f4  retn
```
