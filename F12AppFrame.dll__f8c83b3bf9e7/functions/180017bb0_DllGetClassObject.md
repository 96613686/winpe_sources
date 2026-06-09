# DllGetClassObject

- ea: `0x180017bb0`
- end: `0x180017c24`
- name: `DllGetClassObject`
- size: `116`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800144bc`
- `0x180017bb0`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180017bed`
- `RPCRT4!NdrDllGetClassObject` at `0x180017bed`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT result; // eax
  ATL::CComModule *v7; // rcx

  *ppv = 0;
  result = NdrDllGetClassObject(
             rclsid,
             riid,
             ppv,
             (const ProxyFileInfo **)&aProxyFileList,
             &CLSID_PSFactoryBuffer,
             &gPFactory);
  v7 = (ATL::CComModule *)(result + 0x80000000);
  if ( (int)v7 >= 0 && result != -2147467262 )
    return ATL::CComModule::GetClassObject(v7, rclsid, riid, ppv);
  return result;
}

```

## disassembly

```asm
0x180017bb0  mov     r11, rsp
0x180017bb3  mov     [r11+8], rbx
0x180017bb7  mov     [r11+10h], rsi
0x180017bbb  push    rdi
0x180017bbc  sub     rsp, 30h
0x180017bc0  lea     rax, gPFactory
0x180017bc7  mov     qword ptr [r8], 0
0x180017bce  mov     [r11-10h], rax
0x180017bd2  lea     r9, aProxyFileList; pProxyFileList
0x180017bd9  lea     rax, CLSID_PSFactoryBuffer
0x180017be0  mov     rbx, r8
0x180017be3  mov     [r11-18h], rax
0x180017be7  mov     rdi, rdx
0x180017bea  mov     rsi, rcx
0x180017bed  call    cs:__imp_NdrDllGetClassObject
0x180017bf3  mov     edx, 80000000h
0x180017bf8  lea     ecx, [rax+rdx]; this
0x180017bfb  test    edx, ecx
0x180017bfd  jnz     short loc_180017C14
0x180017bff  cmp     eax, 80004002h
0x180017c04  jz      short loc_180017C14
0x180017c06  mov     r9, rbx; void **
0x180017c09  mov     r8, rdi; struct _GUID *
0x180017c0c  mov     rdx, rsi; struct _GUID *
0x180017c0f  call    ?GetClassObject@CComModule@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z; ATL::CComModule::GetClassObject(_GUID const &,_GUID const &,void * *)
0x180017c14  mov     rbx, [rsp+38h+arg_0]
0x180017c19  mov     rsi, [rsp+38h+arg_8]
0x180017c1e  add     rsp, 30h
0x180017c22  pop     rdi
0x180017c23  retn
```
