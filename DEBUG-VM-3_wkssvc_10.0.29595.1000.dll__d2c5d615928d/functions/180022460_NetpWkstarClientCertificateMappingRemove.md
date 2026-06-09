# NetpWkstarClientCertificateMappingRemove

- ea: `0x180022460`
- end: `0x1800224e1`
- name: `NetpWkstarClientCertificateMappingRemove`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x180009a40`
- `0x1800206ec`
- `0x180022460`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x1800224af`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800224af`
- `ntdll!RtlReleaseResource` at `0x1800224ce`
- `ntdll!RtlReleaseResource` at `0x1800224ce`

## string_xrefs

- `0x180022488`: `WkstaConfigurationInfo`

## pseudocode

```c
__int64 __fastcall NetpWkstarClientCertificateMappingRemove(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v4; // edi
  unsigned int v6; // ebx

  v4 = a2;
  if ( NetpAccessCheckAndAuditEx((__int64)&WsConfigInfoMapping, a2, L"WkstaConfigurationInfo") )
    return 5;
  RtlAcquireResourceExclusive(&stru_18004EB90, 1u);
  v6 = ClientCertificateMappingActionImpl(a3, v4, 1);
  RtlReleaseResource(&stru_18004EB90);
  return v6;
}

```

## disassembly

```asm
0x180022460  mov     [rsp+arg_0], rbx
0x180022465  push    rdi
0x180022466  sub     rsp, 40h
0x18002246a  mov     rax, cs:ConfigurationInfoSd
0x180022471  lea     rcx, WsConfigInfoMapping
0x180022478  mov     [rsp+48h+var_18], rcx
0x18002247d  mov     rbx, r8
0x180022480  mov     [rsp+48h+var_20], 8
0x180022488  lea     r8, aWkstaconfigura; "WkstaConfigurationInfo"
0x18002248f  mov     [rsp+48h+var_28], rax
0x180022494  mov     edi, edx
0x180022496  call    NetpAccessCheckAndAuditEx
0x18002249b  test    eax, eax
0x18002249d  jz      short loc_1800224A6
0x18002249f  mov     eax, 5
0x1800224a4  jmp     short loc_1800224D6
0x1800224a6  mov     dl, 1; Wait
0x1800224a8  lea     rcx, stru_18004EB90; Resource
0x1800224af  call    cs:__imp_RtlAcquireResourceExclusive
0x1800224b5  mov     r8d, 1
0x1800224bb  mov     edx, edi
0x1800224bd  mov     rcx, rbx
0x1800224c0  call    ClientCertificateMappingActionImpl
0x1800224c5  lea     rcx, stru_18004EB90; Resource
0x1800224cc  mov     ebx, eax
0x1800224ce  call    cs:__imp_RtlReleaseResource
0x1800224d4  mov     eax, ebx
0x1800224d6  mov     rbx, [rsp+48h+arg_0]
0x1800224db  add     rsp, 40h
0x1800224df  pop     rdi
0x1800224e0  retn
```
