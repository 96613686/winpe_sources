# CommonUtil::CUniqueHandle<ShieldProvider::CAutoShieldForceFieldProviderInfoFree>::~CUniqueHandle<ShieldProvider::CAutoShieldForceFieldProviderInfoFree>(void)

- ea: `0x1800be4d4`
- end: `0x1800be50f`
- name: `??1?$CUniqueHandle@UCAutoShieldForceFieldProviderInfoFree@ShieldProvider@@@CommonUtil@@QEAA@XZ`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800e6012`

## callees

- `0x1800be4d4`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800be4e6`
- `ole32!CoTaskMemFree` at `0x1800be4f0`
- `ole32!CoTaskMemFree` at `0x1800be4fa`
- `ole32!CoTaskMemFree` at `0x1800be503`
- `ole32!CoTaskMemFree` at `0x1800be4e6`
- `ole32!CoTaskMemFree` at `0x1800be4f0`
- `ole32!CoTaskMemFree` at `0x1800be4fa`
- `ole32!CoTaskMemFree` at `0x1800be503`

## pseudocode

```c
void __fastcall CommonUtil::CUniqueHandle<ShieldProvider::CAutoShieldForceFieldProviderInfoFree>::~CUniqueHandle<ShieldProvider::CAutoShieldForceFieldProviderInfoFree>(
        LPVOID **a1)
{
  LPVOID *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    CoTaskMemFree(v1[2]);
    CoTaskMemFree(v1[3]);
    CoTaskMemFree(v1[4]);
    CoTaskMemFree(v1);
  }
}

```

## disassembly

```asm
0x1800be4d4  push    rbx
0x1800be4d6  sub     rsp, 20h
0x1800be4da  mov     rbx, [rcx]
0x1800be4dd  test    rbx, rbx
0x1800be4e0  jz      short loc_1800BE509
0x1800be4e2  mov     rcx, [rbx+10h]; pv
0x1800be4e6  call    cs:__imp_CoTaskMemFree
0x1800be4ec  mov     rcx, [rbx+18h]; pv
0x1800be4f0  call    cs:__imp_CoTaskMemFree
0x1800be4f6  mov     rcx, [rbx+20h]; pv
0x1800be4fa  call    cs:__imp_CoTaskMemFree
0x1800be500  mov     rcx, rbx; pv
0x1800be503  call    cs:__imp_CoTaskMemFree
0x1800be509  add     rsp, 20h
0x1800be50d  pop     rbx
0x1800be50e  retn
```
