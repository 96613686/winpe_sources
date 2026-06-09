# DllGetClassObject

- ea: `0x1800014a0`
- end: `0x180001501`
- name: `DllGetClassObject`
- size: `97`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800014a0`
- `0x180001798`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x1800014d6`
- `RPCRT4!NdrDllGetClassObject` at `0x1800014d6`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT result; // eax
  __int64 v7; // rcx

  result = NdrDllGetClassObject(
             rclsid,
             riid,
             ppv,
             (const ProxyFileInfo **)&aProxyFileList,
             &IID_IPimcContext2,
             &gPFactory);
  if ( result == -2147221231 )
    return ATL::CAtlDllModuleT<CPenImcModule>::DllGetClassObject(v7, rclsid, riid, ppv);
  return result;
}

```

## disassembly

```asm
0x1800014a0  mov     r11, rsp
0x1800014a3  mov     [r11+8], rbx
0x1800014a7  mov     [r11+10h], rsi
0x1800014ab  push    rdi
0x1800014ac  sub     rsp, 30h
0x1800014b0  lea     rax, gPFactory
0x1800014b7  mov     rbx, r8
0x1800014ba  mov     [r11-10h], rax
0x1800014be  lea     r9, aProxyFileList; pProxyFileList
0x1800014c5  lea     rax, IID_IPimcContext2
0x1800014cc  mov     rdi, rdx
0x1800014cf  mov     [r11-18h], rax
0x1800014d3  mov     rsi, rcx
0x1800014d6  call    cs:__imp_NdrDllGetClassObject
0x1800014dc  cmp     eax, 80040111h
0x1800014e1  jnz     short loc_1800014F1
0x1800014e3  mov     r9, rbx
0x1800014e6  mov     r8, rdi
0x1800014e9  mov     rdx, rsi
0x1800014ec  call    ?DllGetClassObject@?$CAtlDllModuleT@VCPenImcModule@@@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z; ATL::CAtlDllModuleT<CPenImcModule>::DllGetClassObject(_GUID const &,_GUID const &,void * *)
0x1800014f1  mov     rbx, [rsp+38h+arg_0]
0x1800014f6  mov     rsi, [rsp+38h+arg_8]
0x1800014fb  add     rsp, 30h
0x1800014ff  pop     rdi
0x180001500  retn
```
