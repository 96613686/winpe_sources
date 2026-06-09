# DllGetClassObject

- ea: `0x1800092f0`
- end: `0x1800092fe`
- name: `DllGetClassObject`
- size: `14`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004444`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  return CWinTaskModuleT<CPlutonTasksHandler,&_GUID const CLSID_PlutonTasks>::DllGetClassObject(
           (__int64)rclsid,
           rclsid,
           (__int64)riid,
           ppv);
}

```

## disassembly

```asm
0x1800092f0  mov     r9, r8
0x1800092f3  mov     r8, rdx
0x1800092f6  mov     rdx, rcx
0x1800092f9  jmp     ?DllGetClassObject@?$CWinTaskModuleT@VCPlutonTasksHandler@@$1?CLSID_PlutonTasks@@3U_GUID@@B@@QEAAJAEBU_GUID@@0PEAPEAX@Z; CWinTaskModuleT<CPlutonTasksHandler,&_GUID const CLSID_PlutonTasks>::DllGetClassObject(_GUID const &,_GUID const &,void * *)
```
