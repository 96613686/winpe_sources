# ServiceManager::SerializeOperationState(void)

- ea: `0x18001ba6c`
- end: `0x18001bb6f`
- name: `?SerializeOperationState@ServiceManager@@AEAAJXZ`
- size: `259`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `5`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x180015200`
- `0x18001ac90`
- `0x18001aea4`
- `0x18001b1a4`
- `0x18001d224`

## callees

- `0x18001ba6c`
- `0x1800203f0`
- `0x180020ec8`
- `0x180020f6c`
- `0x180021010`
- `0x18002110c`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001baa8`

## string_xrefs

- `0x18001bab6`: `AutoUpdateInProgress`
- `0x18001bb16`: `AutoUpdateInProgress`
- `0x18001ba9a`: `ServiceManager::SerializeOperationState`

## pseudocode

```c
int __fastcall ServiceManager::SerializeOperationState(ServiceManager *this)
{
  __int64 v1; // r8
  int v3; // eax
  __int64 v4; // rcx
  __int64 v5; // r8
  int v6; // r8d
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx

  v1 = *((unsigned int *)this + 880);
  if ( (_DWORD)v1 )
  {
    v3 = RegUtils::SetMapsPersistedRegDword(this, L"CurrentOperation", v1);
    if ( v3 < 0 )
    {
      v6 = 1234;
      return ZTraceReportOrigination(v3, "ServiceManager::SerializeOperationState", v6, this);
    }
    LOBYTE(v5) = *((_BYTE *)this + 4314);
    v3 = RegUtils::SetMapsPersistedRegBoolean(v4, L"AutoUpdateInProgress", v5);
    if ( v3 < 0 )
    {
      v6 = 1235;
      return ZTraceReportOrigination(v3, "ServiceManager::SerializeOperationState", v6, this);
    }
    v3 = RegUtils::SetMapsPersistedRegFileTime(v9, v8, *(_QWORD *)((char *)this + 4332));
    if ( v3 < 0 )
    {
      v6 = 1236;
      return ZTraceReportOrigination(v3, "ServiceManager::SerializeOperationState", v6, this);
    }
    v3 = RegUtils::SetMapsPersistedRegQword(v10, L"CurrentOperationActiveTime", *((_QWORD *)this + 543));
    if ( v3 < 0 )
    {
      v6 = 1237;
      return ZTraceReportOrigination(v3, "ServiceManager::SerializeOperationState", v6, this);
    }
  }
  else
  {
    v3 = RegUtils::DeleteMapsPersistedRegValue((__int64)this, L"CurrentOperation");
    if ( v3 < 0 )
    {
      v6 = 1241;
      return ZTraceReportOrigination(v3, "ServiceManager::SerializeOperationState", v6, this);
    }
    v3 = RegUtils::DeleteMapsPersistedRegValue(v11, L"AutoUpdateInProgress");
    if ( v3 < 0 )
    {
      v6 = 1242;
      return ZTraceReportOrigination(v3, "ServiceManager::SerializeOperationState", v6, this);
    }
    v3 = RegUtils::DeleteMapsPersistedRegValue(v12, L"CurrentOperationStartTime");
    if ( v3 < 0 )
    {
      v6 = 1243;
      return ZTraceReportOrigination(v3, "ServiceManager::SerializeOperationState", v6, this);
    }
    v3 = RegUtils::DeleteMapsPersistedRegValue(v13, L"CurrentOperationActiveTime");
    if ( v3 < 0 )
    {
      v6 = 1244;
      return ZTraceReportOrigination(v3, "ServiceManager::SerializeOperationState", v6, this);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001ba6c  push    rbx
0x18001ba6e  sub     rsp, 20h
0x18001ba72  mov     r8d, [rcx+0DC0h]
0x18001ba79  lea     rdx, aCurrentoperati_0; "CurrentOperation"
0x18001ba80  mov     rbx, rcx
0x18001ba83  test    r8d, r8d
0x18001ba86  jz      short loc_18001BB05
0x18001ba88  call    ?SetMapsPersistedRegDword@RegUtils@@SAJW4MapsRegKeys@@PEBGK@Z; RegUtils::SetMapsPersistedRegDword(MapsRegKeys,ushort const *,ulong)
0x18001ba8d  test    eax, eax
0x18001ba8f  jns     short loc_18001BAAF
0x18001ba91  mov     r8d, 4D2h
0x18001ba97  mov     r9, rbx
0x18001ba9a  lea     rdx, aServicemanager_42; "ServiceManager::SerializeOperationState"
0x18001baa1  mov     ecx, eax
0x18001baa3  add     rsp, 20h
0x18001baa7  pop     rbx
0x18001baa8  jmp     cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18001baaf  mov     r8b, [rbx+10DAh]
0x18001bab6  lea     rdx, aAutoupdateinpr; "AutoUpdateInProgress"
0x18001babd  call    ?SetMapsPersistedRegBoolean@RegUtils@@SAJW4MapsRegKeys@@PEBG_N@Z; RegUtils::SetMapsPersistedRegBoolean(MapsRegKeys,ushort const *,bool)
0x18001bac2  test    eax, eax
0x18001bac4  jns     short loc_18001BACE
0x18001bac6  mov     r8d, 4D3h
0x18001bacc  jmp     short loc_18001BA97
0x18001bace  mov     r8, [rbx+10ECh]
0x18001bad5  call    ?SetMapsPersistedRegFileTime@RegUtils@@SAJW4MapsRegKeys@@PEBGU_FILETIME@@@Z; RegUtils::SetMapsPersistedRegFileTime(MapsRegKeys,ushort const *,_FILETIME)
0x18001bada  test    eax, eax
0x18001badc  jns     short loc_18001BAE6
0x18001bade  mov     r8d, 4D4h
0x18001bae4  jmp     short loc_18001BA97
0x18001bae6  mov     r8, [rbx+10F8h]
0x18001baed  lea     rdx, aCurrentoperati; "CurrentOperationActiveTime"
0x18001baf4  call    ?SetMapsPersistedRegQword@RegUtils@@SAJW4MapsRegKeys@@PEBG_K@Z; RegUtils::SetMapsPersistedRegQword(MapsRegKeys,ushort const *,unsigned __int64)
0x18001baf9  test    eax, eax
0x18001bafb  jns     short loc_18001BB67
0x18001bafd  mov     r8d, 4D5h
0x18001bb03  jmp     short loc_18001BA97
0x18001bb05  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x18001bb0a  test    eax, eax
0x18001bb0c  jns     short loc_18001BB16
0x18001bb0e  mov     r8d, 4D9h
0x18001bb14  jmp     short loc_18001BA97
0x18001bb16  lea     rdx, aAutoupdateinpr; "AutoUpdateInProgress"
0x18001bb1d  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x18001bb22  test    eax, eax
0x18001bb24  jns     short loc_18001BB31
0x18001bb26  mov     r8d, 4DAh
0x18001bb2c  jmp     loc_18001BA97
0x18001bb31  lea     rdx, ValueName; "CurrentOperationStartTime"
0x18001bb38  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x18001bb3d  test    eax, eax
0x18001bb3f  jns     short loc_18001BB4C
0x18001bb41  mov     r8d, 4DBh
0x18001bb47  jmp     loc_18001BA97
0x18001bb4c  lea     rdx, aCurrentoperati; "CurrentOperationActiveTime"
0x18001bb53  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x18001bb58  test    eax, eax
0x18001bb5a  jns     short loc_18001BB67
0x18001bb5c  mov     r8d, 4DCh
0x18001bb62  jmp     loc_18001BA97
0x18001bb67  xor     eax, eax
0x18001bb69  add     rsp, 20h
0x18001bb6d  pop     rbx
0x18001bb6e  retn
```
