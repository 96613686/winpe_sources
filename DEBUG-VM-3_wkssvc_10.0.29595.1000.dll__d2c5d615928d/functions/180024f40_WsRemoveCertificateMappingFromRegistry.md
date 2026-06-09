# WsRemoveCertificateMappingFromRegistry

- ea: `0x180024f40`
- end: `0x180024fe1`
- name: `WsRemoveCertificateMappingFromRegistry`
- size: `161`
- prototype: `__int64 __fastcall(PCWSTR ValueName)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800206ec`
- `0x180020d14`
- `0x180021ff0`

## callees

- `0x180008950`
- `0x1800089d0`
- `0x180022c10`
- `0x180024f40`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180024fb6`
- `ntdll!RtlNtStatusToDosError` at `0x180024fb6`
- `ntdll!RtlDeleteRegistryValue` at `0x180024f75`
- `ntdll!RtlDeleteRegistryValue` at `0x180024f75`

## string_xrefs

- `0x180024f57`: `WsRemoveCertificateMappingFromRegistry`
- `0x180024fc3`: `WsRemoveCertificateMappingFromRegistry`

## pseudocode

```c
__int64 __fastcall WsRemoveCertificateMappingFromRegistry(PCWSTR ValueName)
{
  ULONG v2; // ebx
  int v3; // edi
  int v4; // r8d

  v2 = WsImpersonateClient2("WsRemoveCertificateMappingFromRegistry", 233);
  if ( !v2 )
  {
    v3 = RtlDeleteRegistryValue(0, &Path, ValueName);
    if ( v3 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_LS(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v4, v3, (__int64)ValueName);
      }
      v2 = RtlNtStatusToDosError(v3);
    }
    WsRevertToSelf2("WsRemoveCertificateMappingFromRegistry", 261);
  }
  return v2;
}

```

## disassembly

```asm
0x180024f40  mov     [rsp+arg_0], rbx
0x180024f45  mov     [rsp+arg_8], rsi
0x180024f4a  push    rdi
0x180024f4b  sub     rsp, 30h
0x180024f4f  mov     rsi, rcx
0x180024f52  mov     edx, 0E9h
0x180024f57  lea     rcx, aWsremovecertif; "WsRemoveCertificateMappingFromRegistry"
0x180024f5e  call    WsImpersonateClient2
0x180024f63  mov     ebx, eax
0x180024f65  test    eax, eax
0x180024f67  jnz     short loc_180024FCF
0x180024f69  mov     r8, rsi; ValueName
0x180024f6c  lea     rdx, Path; Path
0x180024f73  xor     ecx, ecx; RelativeTo
0x180024f75  call    cs:__imp_RtlDeleteRegistryValue
0x180024f7b  mov     edi, eax
0x180024f7d  test    eax, eax
0x180024f7f  jns     short loc_180024FBE
0x180024f81  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180024f88  lea     rax, WPP_GLOBAL_Control
0x180024f8f  cmp     rcx, rax
0x180024f92  jz      short loc_180024FB4
0x180024f94  test    byte ptr [rcx+1Ch], 2
0x180024f98  jz      short loc_180024FB4
0x180024f9a  cmp     byte ptr [rcx+19h], 1
0x180024f9e  jb      short loc_180024FB4
0x180024fa0  mov     rcx, [rcx+10h]
0x180024fa4  lea     edx, [rbx+0Ah]
0x180024fa7  mov     r9d, edi
0x180024faa  mov     [rsp+38h+var_18], rsi
0x180024faf  call    WPP_SF_LS
0x180024fb4  mov     ecx, edi; Status
0x180024fb6  call    cs:__imp_RtlNtStatusToDosError
0x180024fbc  mov     ebx, eax
0x180024fbe  mov     edx, 105h
0x180024fc3  lea     rcx, aWsremovecertif; "WsRemoveCertificateMappingFromRegistry"
0x180024fca  call    WsRevertToSelf2
0x180024fcf  mov     rsi, [rsp+38h+arg_8]
0x180024fd4  mov     eax, ebx
0x180024fd6  mov     rbx, [rsp+38h+arg_0]
0x180024fdb  add     rsp, 30h
0x180024fdf  pop     rdi
0x180024fe0  retn
```
