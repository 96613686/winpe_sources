# CommonUtil::CUniqueHandle<ShieldProvider::CAutoShieldPillarStatusExFree>::~CUniqueHandle<ShieldProvider::CAutoShieldPillarStatusExFree>(void)

- ea: `0x180037db8`
- end: `0x180037e03`
- name: `??1?$CUniqueHandle@UCAutoShieldPillarStatusExFree@ShieldProvider@@@CommonUtil@@QEAA@XZ`
- size: `75`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800e4ab4`
- `0x1800e5b0d`
- `0x1800e5b1f`

## callees

- `0x180037db8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180037dcf`
- `ole32!CoTaskMemFree` at `0x180037de6`
- `ole32!CoTaskMemFree` at `0x180037df7`
- `ole32!CoTaskMemFree` at `0x180037dcf`
- `ole32!CoTaskMemFree` at `0x180037de6`
- `ole32!CoTaskMemFree` at `0x180037df7`

## pseudocode

```c
void __fastcall CommonUtil::CUniqueHandle<ShieldProvider::CAutoShieldPillarStatusExFree>::~CUniqueHandle<ShieldProvider::CAutoShieldPillarStatusExFree>(
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
    {
      CoTaskMemFree(v2);
      v1[1] = 0;
    }
    v3 = (void *)v1[2];
    if ( v3 )
    {
      CoTaskMemFree(v3);
      v1[2] = 0;
    }
    CoTaskMemFree(v1);
  }
}

```

## disassembly

```asm
0x180037db8  push    rbx
0x180037dba  sub     rsp, 20h
0x180037dbe  mov     rbx, [rcx]
0x180037dc1  test    rbx, rbx
0x180037dc4  jz      short loc_180037DFD
0x180037dc6  mov     rcx, [rbx+8]; pv
0x180037dca  test    rcx, rcx
0x180037dcd  jz      short loc_180037DDD
0x180037dcf  call    cs:__imp_CoTaskMemFree
0x180037dd5  mov     qword ptr [rbx+8], 0
0x180037ddd  mov     rcx, [rbx+10h]; pv
0x180037de1  test    rcx, rcx
0x180037de4  jz      short loc_180037DF4
0x180037de6  call    cs:__imp_CoTaskMemFree
0x180037dec  mov     qword ptr [rbx+10h], 0
0x180037df4  mov     rcx, rbx; pv
0x180037df7  call    cs:__imp_CoTaskMemFree
0x180037dfd  add     rsp, 20h
0x180037e01  pop     rbx
0x180037e02  retn
```
