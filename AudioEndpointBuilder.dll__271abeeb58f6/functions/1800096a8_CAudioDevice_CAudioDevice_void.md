# CAudioDevice::~CAudioDevice(void)

- ea: `0x1800096a8`
- end: `0x1800096fc`
- name: `??1CAudioDevice@@AEAA@XZ`
- size: `84`
- prototype: `void __fastcall(CAudioDevice *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009b94`

## callees

- `0x180006b0c`
- `0x1800096a8`
- `0x180009704`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800096ba`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800096ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800096d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800096e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800096ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800096d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800096e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800096ef`

## pseudocode

```c
void __fastcall CAudioDevice::~CAudioDevice(CAudioDevice *this)
{
  void *v2; // rcx
  void *v3; // rcx

  CAudioDevice::DisableSwDevice(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((char *)this + 40);
  v2 = (void *)*((_QWORD *)this + 2);
  if ( v2 )
    CoTaskMemFree(v2);
  v3 = (void *)*((_QWORD *)this + 1);
  if ( v3 )
    CoTaskMemFree(v3);
  if ( *(_QWORD *)this )
    CoTaskMemFree(*(LPVOID *)this);
}

```

## disassembly

```asm
0x1800096a8  push    rbx
0x1800096aa  sub     rsp, 20h
0x1800096ae  mov     rbx, rcx
0x1800096b1  call    ?DisableSwDevice@CAudioDevice@@AEAAXXZ; CAudioDevice::DisableSwDevice(void)
0x1800096b6  lea     rcx, [rbx+30h]; lpCriticalSection
0x1800096ba  call    cs:__imp_DeleteCriticalSection
0x1800096c0  lea     rcx, [rbx+28h]
0x1800096c4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800096c9  mov     rcx, [rbx+10h]; pv
0x1800096cd  test    rcx, rcx
0x1800096d0  jz      short loc_1800096D8
0x1800096d2  call    cs:__imp_CoTaskMemFree
0x1800096d8  mov     rcx, [rbx+8]; pv
0x1800096dc  test    rcx, rcx
0x1800096df  jz      short loc_1800096E7
0x1800096e1  call    cs:__imp_CoTaskMemFree
0x1800096e7  mov     rcx, [rbx]; pv
0x1800096ea  test    rcx, rcx
0x1800096ed  jz      short loc_1800096F6
0x1800096ef  call    cs:__imp_CoTaskMemFree
0x1800096f5  nop
0x1800096f6  add     rsp, 20h
0x1800096fa  pop     rbx
0x1800096fb  retn
```
