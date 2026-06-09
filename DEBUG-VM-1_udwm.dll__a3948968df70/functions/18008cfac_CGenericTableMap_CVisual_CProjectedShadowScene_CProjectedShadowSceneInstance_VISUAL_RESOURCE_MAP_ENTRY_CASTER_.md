# CGenericTableMap<CVisual *,CProjectedShadowScene::CProjectedShadowSceneInstance::VISUAL_RESOURCE_MAP_ENTRY_CASTER>::RemoveElement(CProjectedShadowScene::CProjectedShadowSceneInstance::VISUAL_RESOURCE_MAP_ENTRY_CASTER *)

- ea: `0x18008cfac`
- end: `0x18008cfe3`
- name: `?RemoveElement@?$CGenericTableMap@PEAVCVisual@@UVISUAL_RESOURCE_MAP_ENTRY_CASTER@CProjectedShadowSceneInstance@CProjectedShadowScene@@@@QEAAXPEAUVISUAL_RESOURCE_MAP_ENTRY_CASTER@CProjectedShadowSceneInstance@CProjectedShadowScene@@@Z`
- size: `55`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180049000`
- `0x1800c0048`

## callees

- `0x18008cfac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18008cfd8`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18008cfd8`
- `ntdll!RtlDeleteElementGenericTable` at `0x18008cfc6`
- `ntdll!RtlDeleteElementGenericTable` at `0x18008cfc6`

## pseudocode

```c
void __fastcall CGenericTableMap<CVisual *,CProjectedShadowScene::CProjectedShadowSceneInstance::VISUAL_RESOURCE_MAP_ENTRY_CASTER>::RemoveElement(
        struct _RTL_GENERIC_TABLE *a1,
        _QWORD *a2)
{
  _QWORD Buffer[3]; // [rsp+20h] [rbp-18h] BYREF

  Buffer[0] = *a2;
  Buffer[1] = 0;
  if ( !RtlDeleteElementGenericTable(a1, Buffer) )
    RaiseFailFastException(0, 0, 1u);
}

```

## disassembly

```asm
0x18008cfac  sub     rsp, 38h
0x18008cfb0  mov     rax, [rdx]
0x18008cfb3  lea     rdx, [rsp+38h+Buffer]; Buffer
0x18008cfb8  mov     [rsp+38h+Buffer], rax
0x18008cfbd  mov     [rsp+38h+var_10], 0
0x18008cfc6  call    cs:__imp_RtlDeleteElementGenericTable
0x18008cfcc  test    al, al
0x18008cfce  jnz     short loc_18008CFDE
0x18008cfd0  xor     edx, edx; pContextRecord
0x18008cfd2  xor     ecx, ecx; pExceptionRecord
0x18008cfd4  lea     r8d, [rdx+1]; dwFlags
0x18008cfd8  call    cs:__imp_RaiseFailFastException
0x18008cfde  add     rsp, 38h
0x18008cfe2  retn
```
