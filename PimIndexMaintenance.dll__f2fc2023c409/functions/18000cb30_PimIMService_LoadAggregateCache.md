# PimIMService_LoadAggregateCache

- ea: `0x18000cb30`
- end: `0x18000cba0`
- name: `PimIMService_LoadAggregateCache`
- size: `112`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180002da8`
- `0x1800089c4`
- `0x18000ba6c`
- `0x18000cb30`

## string_xrefs

- `0x18000cb4e`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000cb7d`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 PimIMService_LoadAggregateCache()
{
  int v0; // ebx
  __int64 v1; // r9
  int AggregateCacheFromFile; // eax

  v0 = PimIMService::OnLoad((struct _RTL_CRITICAL_SECTION *)&myService);
  if ( v0 < 0 )
  {
    v1 = 3758;
LABEL_3:
    Log_HREvent(
      (unsigned int)v0,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      v1);
    return (unsigned int)v0;
  }
  AggregateCacheFromFile = PimIMService::_LoadAggregateCacheFromFile((PimIMService *)&myService);
  v0 = AggregateCacheFromFile;
  if ( AggregateCacheFromFile < 0 )
  {
    Log_HREvent(
      (unsigned int)AggregateCacheFromFile,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      3498);
    v1 = 3760;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x18000cb30  push    rbx
0x18000cb32  sub     rsp, 30h
0x18000cb36  lea     rcx, ?myService@@3VPimIMService@@A; pv
0x18000cb3d  call    ?OnLoad@PimIMService@@QEAAJXZ; PimIMService::OnLoad(void)
0x18000cb42  mov     ebx, eax
0x18000cb44  test    eax, eax
0x18000cb46  jns     short loc_18000CB65
0x18000cb48  mov     r9d, 0EAEh
0x18000cb4e  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000cb55  mov     edx, 1
0x18000cb5a  mov     ecx, ebx
0x18000cb5c  call    Log_HREvent
0x18000cb61  mov     eax, ebx
0x18000cb63  jmp     short loc_18000CB9A
0x18000cb65  lea     rcx, ?myService@@3VPimIMService@@A; this
0x18000cb6c  call    ?_LoadAggregateCacheFromFile@PimIMService@@AEAAJXZ; PimIMService::_LoadAggregateCacheFromFile(void)
0x18000cb71  mov     ebx, eax
0x18000cb73  test    eax, eax
0x18000cb75  jns     short loc_18000CB98
0x18000cb77  mov     r9d, 0DAAh
0x18000cb7d  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000cb84  mov     edx, 1
0x18000cb89  mov     ecx, eax
0x18000cb8b  call    Log_HREvent
0x18000cb90  mov     r9d, 0EB0h
0x18000cb96  jmp     short loc_18000CB4E
0x18000cb98  xor     eax, eax
0x18000cb9a  add     rsp, 30h
0x18000cb9e  pop     rbx
0x18000cb9f  retn
```
