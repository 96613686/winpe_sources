# ServiceManager::FireOdmlStateChange(void)

- ea: `0x180015ed0`
- end: `0x180015f22`
- name: `?FireOdmlStateChange@ServiceManager@@AEAAXXZ`
- size: `82`
- prototype: `void __fastcall(ServiceManager *__hidden this)`
- caller_count: `15`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x180012f00`
- `0x180013870`
- `0x18001405c`
- `0x1800142c4`
- `0x180014744`
- `0x180014c00`
- `0x180015200`
- `0x180015898`
- `0x180016b60`
- `0x18001ac90`
- `0x18001b068`
- `0x18001cc50`
- `0x18001d070`
- `0x18001d224`
- `0x18001d870`

## callees

- `0x180015ed0`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x180015ef6`
- `ntdll!RtlPublishWnfStateData` at `0x180015ef6`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180015f16`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x180015f16`

## string_xrefs

- `0x180015f04`: `ServiceManager::FireOdmlStateChange`

## pseudocode

```c
void __fastcall ServiceManager::FireOdmlStateChange(ServiceManager *this)
{
  int v2; // eax

  v2 = RtlPublishWnfStateData(WNF_MAPS_MAPLOADER_STATUS_CHANGE, 0, (char *)this + 3536, 32, 0);
  if ( v2 < 0 )
    ZTraceReportIgnore(v2 | 0x10000000, "ServiceManager::FireOdmlStateChange", 2358, this);
}

```

## disassembly

```asm
0x180015ed0  push    rbx
0x180015ed2  sub     rsp, 30h
0x180015ed6  xor     edx, edx
0x180015ed8  mov     [rsp+38h+var_18], 0
0x180015ee1  mov     rbx, rcx
0x180015ee4  lea     r8, [rcx+0DD0h]
0x180015eeb  mov     rcx, cs:WNF_MAPS_MAPLOADER_STATUS_CHANGE
0x180015ef2  lea     r9d, [rdx+20h]
0x180015ef6  call    cs:__imp_RtlPublishWnfStateData
0x180015efc  test    eax, eax
0x180015efe  jns     short loc_180015F1C
0x180015f00  bts     eax, 1Ch
0x180015f04  lea     rdx, aServicemanager_17; "ServiceManager::FireOdmlStateChange"
0x180015f0b  mov     ecx, eax
0x180015f0d  mov     r9, rbx
0x180015f10  mov     r8d, 936h
0x180015f16  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x180015f1c  add     rsp, 30h
0x180015f20  pop     rbx
0x180015f21  retn
```
