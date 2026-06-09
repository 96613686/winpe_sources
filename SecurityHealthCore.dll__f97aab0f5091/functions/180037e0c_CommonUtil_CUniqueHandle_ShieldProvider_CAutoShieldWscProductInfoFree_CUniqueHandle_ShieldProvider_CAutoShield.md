# CommonUtil::CUniqueHandle<ShieldProvider::CAutoShieldWscProductInfoFree>::~CUniqueHandle<ShieldProvider::CAutoShieldWscProductInfoFree>(void)

- ea: `0x180037e0c`
- end: `0x180037e47`
- name: `??1?$CUniqueHandle@UCAutoShieldWscProductInfoFree@ShieldProvider@@@CommonUtil@@QEAA@XZ`
- size: `59`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800e4a5a`
- `0x1800e4a90`
- `0x1800e4bc2`

## callees

- `0x180037e0c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180037e23`
- `ole32!CoTaskMemFree` at `0x180037e32`
- `ole32!CoTaskMemFree` at `0x180037e3b`
- `ole32!CoTaskMemFree` at `0x180037e23`
- `ole32!CoTaskMemFree` at `0x180037e32`
- `ole32!CoTaskMemFree` at `0x180037e3b`

## pseudocode

```c
void __fastcall CommonUtil::CUniqueHandle<ShieldProvider::CAutoShieldWscProductInfoFree>::~CUniqueHandle<ShieldProvider::CAutoShieldWscProductInfoFree>(
        _QWORD **a1)
{
  _QWORD *v1; // rbx
  void *v2; // rcx
  void *v3; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    v2 = (void *)v1[1];
    if ( v2 )
      CoTaskMemFree(v2);
    v3 = (void *)v1[2];
    if ( v3 )
      CoTaskMemFree(v3);
    CoTaskMemFree(v1);
  }
}

```

## disassembly

```asm
0x180037e0c  push    rbx
0x180037e0e  sub     rsp, 20h
0x180037e12  mov     rbx, [rcx]
0x180037e15  test    rbx, rbx
0x180037e18  jz      short loc_180037E41
0x180037e1a  mov     rcx, [rbx+8]; pv
0x180037e1e  test    rcx, rcx
0x180037e21  jz      short loc_180037E29
0x180037e23  call    cs:__imp_CoTaskMemFree
0x180037e29  mov     rcx, [rbx+10h]; pv
0x180037e2d  test    rcx, rcx
0x180037e30  jz      short loc_180037E38
0x180037e32  call    cs:__imp_CoTaskMemFree
0x180037e38  mov     rcx, rbx; pv
0x180037e3b  call    cs:__imp_CoTaskMemFree
0x180037e41  add     rsp, 20h
0x180037e45  pop     rbx
0x180037e46  retn
```
