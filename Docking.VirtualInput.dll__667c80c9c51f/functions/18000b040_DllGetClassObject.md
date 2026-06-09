# DllGetClassObject

- ea: `0x18000b040`
- end: `0x18000b0a8`
- name: `DllGetClassObject`
- size: `104`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000797c`
- `0x18000832c`
- `0x18000b040`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x18000b082`
- `RPCRT4!NdrDllGetClassObject` at `0x18000b082`

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
0x18000b040  push    rbx
0x18000b042  push    rbp
0x18000b043  push    rsi
0x18000b044  push    rdi
0x18000b045  sub     rsp, 38h
0x18000b049  mov     rbx, r8
0x18000b04c  mov     rdi, rdx
0x18000b04f  mov     rsi, rcx
0x18000b052  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x18000b057  mov     rbp, rax
0x18000b05a  lea     r9, aProxyFileList; pProxyFileList
0x18000b061  lea     rax, gPFactory
0x18000b068  mov     r8, rbx; ppv
0x18000b06b  mov     [rsp+58h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x18000b070  mov     rdx, rdi; riid
0x18000b073  lea     rax, CLSID_PSFactoryBuffer
0x18000b07a  mov     rcx, rsi; rclsid
0x18000b07d  mov     [rsp+58h+pclsid], rax; pclsid
0x18000b082  call    cs:__imp_NdrDllGetClassObject
0x18000b088  test    eax, eax
0x18000b08a  jns     short loc_18000B09F
0x18000b08c  mov     r9, rdi
0x18000b08f  mov     [rsp+58h+pclsid], rbx; PVOID
0x18000b094  mov     r8, rsi
0x18000b097  mov     rcx, rbp; this
0x18000b09a  call    ??$GetClassObject@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGAEBU_GUID@@2PEAPEAX@Z; Microsoft::WRL::Details::GetClassObject<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,_GUID const &,_GUID const &,void * *)
0x18000b09f  add     rsp, 38h
0x18000b0a3  pop     rdi
0x18000b0a4  pop     rsi
0x18000b0a5  pop     rbp
0x18000b0a6  pop     rbx
0x18000b0a7  retn
```
