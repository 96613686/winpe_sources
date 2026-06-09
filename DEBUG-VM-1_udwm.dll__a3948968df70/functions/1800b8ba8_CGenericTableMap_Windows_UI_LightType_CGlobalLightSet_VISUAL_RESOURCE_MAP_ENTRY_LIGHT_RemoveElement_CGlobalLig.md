# CGenericTableMap<Windows::UI::LightType,CGlobalLightSet::VISUAL_RESOURCE_MAP_ENTRY_LIGHT>::RemoveElement(CGlobalLightSet::VISUAL_RESOURCE_MAP_ENTRY_LIGHT *)

- ea: `0x1800b8ba8`
- end: `0x1800b8bdc`
- name: `?RemoveElement@?$CGenericTableMap@W4LightType@UI@Windows@@UVISUAL_RESOURCE_MAP_ENTRY_LIGHT@CGlobalLightSet@@@@QEAAXPEAUVISUAL_RESOURCE_MAP_ENTRY_LIGHT@CGlobalLightSet@@@Z`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800b8a50`

## callees

- `0x1800b8ba8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800b8bd1`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800b8bd1`
- `ntdll!RtlDeleteElementGenericTable` at `0x1800b8bbf`
- `ntdll!RtlDeleteElementGenericTable` at `0x1800b8bbf`

## pseudocode

```c
void __fastcall CGenericTableMap<enum Windows::UI::LightType,CGlobalLightSet::VISUAL_RESOURCE_MAP_ENTRY_LIGHT>::RemoveElement(
        struct _RTL_GENERIC_TABLE *a1,
        int *a2)
{
  int v2; // eax
  __int128 Buffer; // [rsp+20h] [rbp-18h] BYREF

  v2 = *a2;
  Buffer = 0;
  LODWORD(Buffer) = v2;
  if ( !RtlDeleteElementGenericTable(a1, &Buffer) )
    RaiseFailFastException(0, 0, 1u);
}

```

## disassembly

```asm
0x1800b8ba8  sub     rsp, 38h
0x1800b8bac  mov     eax, [rdx]
0x1800b8bae  xorps   xmm0, xmm0
0x1800b8bb1  movups  [rsp+38h+Buffer], xmm0
0x1800b8bb6  lea     rdx, [rsp+38h+Buffer]; Buffer
0x1800b8bbb  mov     dword ptr [rsp+38h+Buffer], eax
0x1800b8bbf  call    cs:__imp_RtlDeleteElementGenericTable
0x1800b8bc5  test    al, al
0x1800b8bc7  jnz     short loc_1800B8BD7
0x1800b8bc9  xor     edx, edx; pContextRecord
0x1800b8bcb  xor     ecx, ecx; pExceptionRecord
0x1800b8bcd  lea     r8d, [rdx+1]; dwFlags
0x1800b8bd1  call    cs:__imp_RaiseFailFastException
0x1800b8bd7  add     rsp, 38h
0x1800b8bdb  retn
```
