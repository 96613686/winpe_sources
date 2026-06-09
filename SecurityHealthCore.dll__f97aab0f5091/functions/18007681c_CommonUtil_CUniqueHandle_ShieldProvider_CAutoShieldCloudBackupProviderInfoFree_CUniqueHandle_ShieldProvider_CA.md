# CommonUtil::CUniqueHandle<ShieldProvider::CAutoShieldCloudBackupProviderInfoFree>::~CUniqueHandle<ShieldProvider::CAutoShieldCloudBackupProviderInfoFree>(void)

- ea: `0x18007681c`
- end: `0x18007686b`
- name: `??1?$CUniqueHandle@UCAutoShieldCloudBackupProviderInfoFree@ShieldProvider@@@CommonUtil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800e58ee`

## callees

- `0x18007681c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18007682e`
- `ole32!CoTaskMemFree` at `0x180076838`
- `ole32!CoTaskMemFree` at `0x180076842`
- `ole32!CoTaskMemFree` at `0x18007684c`
- `ole32!CoTaskMemFree` at `0x180076856`
- `ole32!CoTaskMemFree` at `0x18007685f`
- `ole32!CoTaskMemFree` at `0x18007682e`
- `ole32!CoTaskMemFree` at `0x180076838`
- `ole32!CoTaskMemFree` at `0x180076842`
- `ole32!CoTaskMemFree` at `0x18007684c`
- `ole32!CoTaskMemFree` at `0x180076856`
- `ole32!CoTaskMemFree` at `0x18007685f`

## pseudocode

```c
void __fastcall CommonUtil::CUniqueHandle<ShieldProvider::CAutoShieldCloudBackupProviderInfoFree>::~CUniqueHandle<ShieldProvider::CAutoShieldCloudBackupProviderInfoFree>(
        LPVOID **a1)
{
  LPVOID *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    CoTaskMemFree(v1[3]);
    CoTaskMemFree(v1[4]);
    CoTaskMemFree(v1[5]);
    CoTaskMemFree(v1[6]);
    CoTaskMemFree(v1[7]);
    CoTaskMemFree(v1);
  }
}

```

## disassembly

```asm
0x18007681c  push    rbx
0x18007681e  sub     rsp, 20h
0x180076822  mov     rbx, [rcx]
0x180076825  test    rbx, rbx
0x180076828  jz      short loc_180076865
0x18007682a  mov     rcx, [rbx+18h]; pv
0x18007682e  call    cs:__imp_CoTaskMemFree
0x180076834  mov     rcx, [rbx+20h]; pv
0x180076838  call    cs:__imp_CoTaskMemFree
0x18007683e  mov     rcx, [rbx+28h]; pv
0x180076842  call    cs:__imp_CoTaskMemFree
0x180076848  mov     rcx, [rbx+30h]; pv
0x18007684c  call    cs:__imp_CoTaskMemFree
0x180076852  mov     rcx, [rbx+38h]; pv
0x180076856  call    cs:__imp_CoTaskMemFree
0x18007685c  mov     rcx, rbx; pv
0x18007685f  call    cs:__imp_CoTaskMemFree
0x180076865  add     rsp, 20h
0x180076869  pop     rbx
0x18007686a  retn
```
