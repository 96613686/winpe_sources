# DllGetClassObject

- ea: `0x18000f640`
- end: `0x18000f6b5`
- name: `DllGetClassObject`
- size: `117`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007edc`
- `0x18000bfac`
- `0x18000f640`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x18000f69f`
- `RPCRT4!NdrDllGetClassObject` at `0x18000f69f`

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
0x18000f640  mov     [rsp+arg_0], rbx
0x18000f645  mov     [rsp+arg_8], rsi
0x18000f64a  push    rdi
0x18000f64b  sub     rsp, 30h
0x18000f64f  mov     rbx, r8
0x18000f652  mov     rdi, rdx
0x18000f655  mov     rsi, rcx
0x18000f658  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x18000f65d  mov     r9, rdi
0x18000f660  mov     [rsp+38h+pclsid], rbx; PVOID
0x18000f665  mov     r8, rsi
0x18000f668  mov     rcx, rax; this
0x18000f66b  call    ??$GetClassObject@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGAEBU_GUID@@2PEAPEAX@Z; Microsoft::WRL::Details::GetClassObject<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,_GUID const &,_GUID const &,void * *)
0x18000f670  cmp     eax, 80040111h
0x18000f675  jnz     short loc_18000F6A5
0x18000f677  lea     rax, gPFactory
0x18000f67e  mov     r8, rbx; ppv
0x18000f681  mov     [rsp+38h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x18000f686  lea     r9, aProxyFileList; pProxyFileList
0x18000f68d  lea     rax, CLSID_PSFactoryBuffer
0x18000f694  mov     rdx, rdi; riid
0x18000f697  mov     rcx, rsi; rclsid
0x18000f69a  mov     [rsp+38h+pclsid], rax; pclsid
0x18000f69f  call    cs:__imp_NdrDllGetClassObject
0x18000f6a5  mov     rbx, [rsp+38h+arg_0]
0x18000f6aa  mov     rsi, [rsp+38h+arg_8]
0x18000f6af  add     rsp, 30h
0x18000f6b3  pop     rdi
0x18000f6b4  retn
```
