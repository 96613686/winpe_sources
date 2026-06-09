# ServiceManager::SetUpdateAvailability(__MIDL_odmlapi_0005)

- ea: `0x18001bce4`
- end: `0x18001bd4a`
- name: `?SetUpdateAvailability@ServiceManager@@AEAAJW4__MIDL_odmlapi_0005@@@Z`
- size: `102`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x1800142c4`
- `0x180014744`

## callees

- `0x18001bce4`
- `0x1800203f0`
- `0x180020f6c`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001bd18`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001bd18`

## string_xrefs

- `0x18001bd25`: `LastMapUpdateNotification`
- `0x18001bcf3`: `MapUpdate`
- `0x18001bd0f`: `ServiceManager::SetUpdateAvailability`

## pseudocode

```c
int __fastcall ServiceManager::SetUpdateAvailability(const void *a1, unsigned int a2)
{
  int v4; // eax
  __int64 v5; // rcx
  int v6; // r8d

  v4 = RegUtils::SetMapsPersistedRegDword(a1, L"MapUpdate", a2);
  if ( v4 < 0 )
  {
    v6 = 3114;
    return ZTraceReportPropagation(v4, "ServiceManager::SetUpdateAvailability", v6, a1);
  }
  if ( a2 == 1 )
  {
    v4 = RegUtils::DeleteMapsPersistedRegValue(v5, L"LastMapUpdateNotification");
    if ( v4 < 0 )
    {
      v6 = 3118;
      return ZTraceReportPropagation(v4, "ServiceManager::SetUpdateAvailability", v6, a1);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001bce4  mov     [rsp+arg_0], rbx
0x18001bce9  push    rdi
0x18001bcea  sub     rsp, 20h
0x18001bcee  mov     ebx, edx
0x18001bcf0  mov     r8d, edx
0x18001bcf3  lea     rdx, aMapupdate; "MapUpdate"
0x18001bcfa  mov     rdi, rcx
0x18001bcfd  call    ?SetMapsPersistedRegDword@RegUtils@@SAJW4MapsRegKeys@@PEBGK@Z; RegUtils::SetMapsPersistedRegDword(MapsRegKeys,ushort const *,ulong)
0x18001bd02  test    eax, eax
0x18001bd04  jns     short loc_18001BD20
0x18001bd06  mov     r8d, 0C2Ah
0x18001bd0c  mov     r9, rdi
0x18001bd0f  lea     rdx, aServicemanager_24; "ServiceManager::SetUpdateAvailability"
0x18001bd16  mov     ecx, eax
0x18001bd18  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001bd1e  jmp     short loc_18001BD3F
0x18001bd20  cmp     ebx, 1
0x18001bd23  jnz     short loc_18001BD3D
0x18001bd25  lea     rdx, aLastmapupdaten; "LastMapUpdateNotification"
0x18001bd2c  call    ?DeleteMapsPersistedRegValue@RegUtils@@SAJW4MapsRegKeys@@PEBG@Z; RegUtils::DeleteMapsPersistedRegValue(MapsRegKeys,ushort const *)
0x18001bd31  test    eax, eax
0x18001bd33  jns     short loc_18001BD3D
0x18001bd35  mov     r8d, 0C2Eh
0x18001bd3b  jmp     short loc_18001BD0C
0x18001bd3d  xor     eax, eax
0x18001bd3f  mov     rbx, [rsp+28h+arg_0]
0x18001bd44  add     rsp, 20h
0x18001bd48  pop     rdi
0x18001bd49  retn
```
