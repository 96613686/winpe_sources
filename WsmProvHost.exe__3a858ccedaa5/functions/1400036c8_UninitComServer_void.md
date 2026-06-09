# UninitComServer(void)

- ea: `0x1400036c8`
- end: `0x14000370d`
- name: `?UninitComServer@@YAJXZ`
- size: `69`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140003ab8`

## callees

- `0x1400036c8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140003700`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140003700`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1400036d6`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1400036f0`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1400036d6`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1400036f0`

## pseudocode

```c
__int64 UninitComServer(void)
{
  if ( g_HostRegisterProfile )
  {
    CoRevokeClassObject(g_HostRegisterProfile);
    g_HostRegisterProfile = 0;
  }
  if ( g_HostRegisterNoProfile )
  {
    CoRevokeClassObject(g_HostRegisterNoProfile);
    g_HostRegisterNoProfile = 0;
  }
  CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x1400036c8  sub     rsp, 28h
0x1400036cc  mov     ecx, cs:?g_HostRegisterProfile@@3KA; dwRegister
0x1400036d2  test    ecx, ecx
0x1400036d4  jz      short loc_1400036E6
0x1400036d6  call    cs:__imp_CoRevokeClassObject
0x1400036dc  mov     cs:?g_HostRegisterProfile@@3KA, 0; ulong g_HostRegisterProfile
0x1400036e6  mov     ecx, cs:?g_HostRegisterNoProfile@@3KA; dwRegister
0x1400036ec  test    ecx, ecx
0x1400036ee  jz      short loc_140003700
0x1400036f0  call    cs:__imp_CoRevokeClassObject
0x1400036f6  mov     cs:?g_HostRegisterNoProfile@@3KA, 0; ulong g_HostRegisterNoProfile
0x140003700  call    cs:__imp_CoUninitialize
0x140003706  xor     eax, eax
0x140003708  add     rsp, 28h
0x14000370c  retn
```
