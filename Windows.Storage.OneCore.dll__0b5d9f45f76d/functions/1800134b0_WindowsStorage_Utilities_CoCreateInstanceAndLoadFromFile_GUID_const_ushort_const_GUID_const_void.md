# WindowsStorage::Utilities::CoCreateInstanceAndLoadFromFile(_GUID const &,ushort const *,_GUID const &,void * *)

- ea: `0x1800134b0`
- end: `0x18001353a`
- name: `?CoCreateInstanceAndLoadFromFile@Utilities@WindowsStorage@@YAJAEBU_GUID@@PEBG0PEAPEAX@Z`
- size: `138`
- prototype: `int(WindowsStorage::Utilities *__hidden this, const struct _GUID *, const unsigned __int16 *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800120c0`
- `0x1800123a0`

## callees

- `0x1800134b0`
- `0x1800141b4`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800134f7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800134f7`

## pseudocode

```c
__int64 __fastcall WindowsStorage::Utilities::CoCreateInstanceAndLoadFromFile(
        WindowsStorage::Utilities *this,
        struct IUnknown *a2,
        const unsigned __int16 *a3,
        const struct _GUID *a4)
{
  HRESULT Instance; // ebx
  const unsigned __int16 *v7; // r8
  unsigned int v8; // r9d
  void **v10; // [rsp+28h] [rbp-10h]
  WindowsStorage::Utilities *v11; // [rsp+50h] [rbp+18h] BYREF

  *(_QWORD *)&a4->Data1 = 0;
  v11 = 0;
  Instance = CoCreateInstance(
               &CLSID_PersistentZoneIdentifier,
               0,
               0x4001u,
               &GUID_eb5e760c_09ef_45c0_b510_70830ce31e6a,
               (LPVOID *)&v11);
  if ( Instance >= 0 )
  {
    Instance = WindowsStorage::Utilities::_AndLoadFromFile(v11, a2, v7, v8, a4, v10);
    (*(void (__fastcall **)(WindowsStorage::Utilities *))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800134b0  mov     r11, rsp
0x1800134b3  mov     [r11+8], rbx
0x1800134b7  mov     [r11+10h], rsi
0x1800134bb  mov     [r11+18h], r8
0x1800134bf  push    rdi
0x1800134c0  sub     rsp, 30h
0x1800134c4  mov     rdi, r9
0x1800134c7  mov     qword ptr [r9], 0
0x1800134ce  mov     rsi, rdx
0x1800134d1  mov     qword ptr [r11+18h], 0
0x1800134d9  lea     rax, [r11+18h]
0x1800134dd  xor     edx, edx; pUnkOuter
0x1800134df  lea     r9, _GUID_eb5e760c_09ef_45c0_b510_70830ce31e6a; riid
0x1800134e6  mov     [r11-18h], rax
0x1800134ea  mov     r8d, 4001h; dwClsContext
0x1800134f0  lea     rcx, CLSID_PersistentZoneIdentifier; rclsid
0x1800134f7  call    cs:__imp_CoCreateInstance
0x1800134fd  mov     ebx, eax
0x1800134ff  test    eax, eax
0x180013501  js      short loc_180013528
0x180013503  mov     rcx, [rsp+38h+arg_10]; this
0x180013508  mov     rdx, rsi; struct IUnknown *
0x18001350b  mov     [rsp+38h+var_18], rdi; struct _GUID *
0x180013510  call    ?_AndLoadFromFile@Utilities@WindowsStorage@@YAJPEAUIUnknown@@PEBGKAEBU_GUID@@PEAPEAX@Z; WindowsStorage::Utilities::_AndLoadFromFile(IUnknown *,ushort const *,ulong,_GUID const &,void * *)
0x180013515  mov     rcx, [rsp+38h+arg_10]
0x18001351a  mov     ebx, eax
0x18001351c  mov     rax, [rcx]
0x18001351f  mov     rax, [rax+10h]
0x180013523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013528  mov     rsi, [rsp+38h+arg_8]
0x18001352d  mov     eax, ebx
0x18001352f  mov     rbx, [rsp+38h+arg_0]
0x180013534  add     rsp, 30h
0x180013538  pop     rdi
0x180013539  retn
```
