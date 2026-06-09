# ServiceManager::SetAutoUpdateEnabledSetting(int)

- ea: `0x18001bb80`
- end: `0x18001bbc5`
- name: `?SetAutoUpdateEnabledSetting@ServiceManager@@UEAAJH@Z`
- size: `69`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update`

## callees

- `0x18001bb80`
- `0x180020ec8`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001bbb6`

## string_xrefs

- `0x18001bb8b`: `AutoUpdateEnabled`
- `0x18001bba2`: `ServiceManager::SetAutoUpdateEnabledSetting`

## pseudocode

```c
int __fastcall ServiceManager::SetAutoUpdateEnabledSetting(ServiceManager *this, int a2, __int64 a3)
{
  int v4; // eax

  LOBYTE(a3) = a2 != 0;
  v4 = RegUtils::SetMapsPersistedRegBoolean(this, L"AutoUpdateEnabled", a3);
  if ( v4 >= 0 )
    return 0;
  else
    return ZTraceReportPropagation(v4, "ServiceManager::SetAutoUpdateEnabledSetting", 2990, this);
}

```

## disassembly

```asm
0x18001bb80  push    rbx
0x18001bb82  sub     rsp, 20h
0x18001bb86  test    edx, edx
0x18001bb88  mov     rbx, rcx
0x18001bb8b  lea     rdx, aAutoupdateenab; "AutoUpdateEnabled"
0x18001bb92  setnz   r8b
0x18001bb96  call    ?SetMapsPersistedRegBoolean@RegUtils@@SAJW4MapsRegKeys@@PEBG_N@Z; RegUtils::SetMapsPersistedRegBoolean(MapsRegKeys,ushort const *,bool)
0x18001bb9b  test    eax, eax
0x18001bb9d  jns     short loc_18001BBBD
0x18001bb9f  mov     r9, rbx
0x18001bba2  lea     rdx, aServicemanager_21; "ServiceManager::SetAutoUpdateEnabledSet"...
0x18001bba9  mov     r8d, 0BAEh
0x18001bbaf  mov     ecx, eax
0x18001bbb1  add     rsp, 20h
0x18001bbb5  pop     rbx
0x18001bbb6  jmp     cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001bbbd  xor     eax, eax
0x18001bbbf  add     rsp, 20h
0x18001bbc3  pop     rbx
0x18001bbc4  retn
```
