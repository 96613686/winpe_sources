# SAFE_FREE_DISKPROP(_VDS_DISK_PROP *)

- ea: `0x180006b2c`
- end: `0x180006bb6`
- name: `?SAFE_FREE_DISKPROP@@YAXPEAU_VDS_DISK_PROP@@@Z`
- size: `138`
- prototype: `void __fastcall(struct _VDS_DISK_PROP *)`
- caller_count: `11`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800021b0`
- `0x180002be0`
- `0x180002d24`
- `0x180003010`
- `0x180003d00`
- `0x180003f68`
- `0x1800049d0`
- `0x180005578`
- `0x180005884`
- `0x180006934`
- `0x180007624`

## callees

- `0x180006b2c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180006b46`
- `ole32!CoTaskMemFree` at `0x180006b5d`
- `ole32!CoTaskMemFree` at `0x180006b74`
- `ole32!CoTaskMemFree` at `0x180006b8b`
- `ole32!CoTaskMemFree` at `0x180006ba2`
- `ole32!CoTaskMemFree` at `0x180006b46`
- `ole32!CoTaskMemFree` at `0x180006b5d`
- `ole32!CoTaskMemFree` at `0x180006b74`
- `ole32!CoTaskMemFree` at `0x180006b8b`
- `ole32!CoTaskMemFree` at `0x180006ba2`

## pseudocode

```c
void __fastcall SAFE_FREE_DISKPROP(struct _VDS_DISK_PROP *a1)
{
  LPWSTR pwszDiskAddress; // rcx
  LPWSTR pwszName; // rcx
  LPWSTR pwszFriendlyName; // rcx
  LPWSTR pwszAdaptorName; // rcx
  LPWSTR pwszDevicePath; // rcx

  if ( a1 )
  {
    pwszDiskAddress = a1->pwszDiskAddress;
    if ( pwszDiskAddress )
    {
      CoTaskMemFree(pwszDiskAddress);
      a1->pwszDiskAddress = 0;
    }
    pwszName = a1->pwszName;
    if ( pwszName )
    {
      CoTaskMemFree(pwszName);
      a1->pwszName = 0;
    }
    pwszFriendlyName = a1->pwszFriendlyName;
    if ( pwszFriendlyName )
    {
      CoTaskMemFree(pwszFriendlyName);
      a1->pwszFriendlyName = 0;
    }
    pwszAdaptorName = a1->pwszAdaptorName;
    if ( pwszAdaptorName )
    {
      CoTaskMemFree(pwszAdaptorName);
      a1->pwszAdaptorName = 0;
    }
    pwszDevicePath = a1->pwszDevicePath;
    if ( pwszDevicePath )
    {
      CoTaskMemFree(pwszDevicePath);
      a1->pwszDevicePath = 0;
    }
  }
}

```

## disassembly

```asm
0x180006b2c  test    rcx, rcx
0x180006b2f  jz      locret_180006BB5
0x180006b35  push    rbx
0x180006b36  sub     rsp, 20h
0x180006b3a  mov     rbx, rcx
0x180006b3d  mov     rcx, [rcx+58h]; pv
0x180006b41  test    rcx, rcx
0x180006b44  jz      short loc_180006B54
0x180006b46  call    cs:__imp_CoTaskMemFree
0x180006b4c  mov     qword ptr [rbx+58h], 0
0x180006b54  mov     rcx, [rbx+60h]; pv
0x180006b58  test    rcx, rcx
0x180006b5b  jz      short loc_180006B6B
0x180006b5d  call    cs:__imp_CoTaskMemFree
0x180006b63  mov     qword ptr [rbx+60h], 0
0x180006b6b  mov     rcx, [rbx+68h]; pv
0x180006b6f  test    rcx, rcx
0x180006b72  jz      short loc_180006B82
0x180006b74  call    cs:__imp_CoTaskMemFree
0x180006b7a  mov     qword ptr [rbx+68h], 0
0x180006b82  mov     rcx, [rbx+70h]; pv
0x180006b86  test    rcx, rcx
0x180006b89  jz      short loc_180006B99
0x180006b8b  call    cs:__imp_CoTaskMemFree
0x180006b91  mov     qword ptr [rbx+70h], 0
0x180006b99  mov     rcx, [rbx+78h]; pv
0x180006b9d  test    rcx, rcx
0x180006ba0  jz      short loc_180006BB0
0x180006ba2  call    cs:__imp_CoTaskMemFree
0x180006ba8  mov     qword ptr [rbx+78h], 0
0x180006bb0  add     rsp, 20h
0x180006bb4  pop     rbx
0x180006bb5  retn
```
