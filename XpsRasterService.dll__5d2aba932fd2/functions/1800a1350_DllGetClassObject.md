# DllGetClassObject

- ea: `0x1800a1350`
- end: `0x1800a13b8`
- name: `DllGetClassObject`
- size: `104`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800a0498`
- `0x1800a0a18`
- `0x1800a1350`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x1800a1386`
- `RPCRT4!NdrDllGetClassObject` at `0x1800a1386`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT result; // eax
  Microsoft::WRL::Details *v5; // rax

  result = NdrDllGetClassObject(
             rclsid,
             riid,
             ppv,
             (const ProxyFileInfo **)&aProxyFileList,
             &CLSID_PSFactoryBuffer,
             (CStdPSFactoryBuffer *)gPFactory);
  if ( result < 0 )
  {
    v5 = (Microsoft::WRL::Details *)Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
    return Microsoft::WRL::Details::GetClassObject<1>(v5, ppv);
  }
  return result;
}

```

## disassembly

```asm
0x1800a1350  mov     r11, rsp
0x1800a1353  mov     [r11+8], rbx
0x1800a1357  mov     [r11+10h], rsi
0x1800a135b  push    rdi
0x1800a135c  sub     rsp, 30h
0x1800a1360  lea     rax, gPFactory
0x1800a1367  mov     rbx, r8
0x1800a136a  mov     [r11-10h], rax
0x1800a136e  lea     r9, aProxyFileList; pProxyFileList
0x1800a1375  lea     rax, CLSID_PSFactoryBuffer
0x1800a137c  mov     rdi, rdx
0x1800a137f  mov     [r11-18h], rax
0x1800a1383  mov     rsi, rcx
0x1800a1386  call    cs:__imp_NdrDllGetClassObject
0x1800a138c  test    eax, eax
0x1800a138e  jns     short loc_1800A13A8
0x1800a1390  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x1800a1395  mov     r9, rdi
0x1800a1398  mov     [rsp+38h+var_18], rbx; PVOID
0x1800a139d  mov     r8, rsi
0x1800a13a0  mov     rcx, rax; this
0x1800a13a3  call    ??$GetClassObject@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEB_WAEBU_GUID@@2PEAPEAX@Z; Microsoft::WRL::Details::GetClassObject<1>(Microsoft::WRL::Details::ModuleBase *,wchar_t const *,_GUID const &,_GUID const &,void * *)
0x1800a13a8  mov     rbx, [rsp+38h+arg_0]
0x1800a13ad  mov     rsi, [rsp+38h+arg_8]
0x1800a13b2  add     rsp, 30h
0x1800a13b6  pop     rdi
0x1800a13b7  retn
```
