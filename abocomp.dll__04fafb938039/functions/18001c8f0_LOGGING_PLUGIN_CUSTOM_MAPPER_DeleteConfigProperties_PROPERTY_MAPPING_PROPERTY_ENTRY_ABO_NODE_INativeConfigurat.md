# LOGGING_PLUGIN_CUSTOM_MAPPER::DeleteConfigProperties(PROPERTY_MAPPING *,PROPERTY_ENTRY *,ABO_NODE *,INativeConfigurationElement *)

- ea: `0x18001c8f0`
- end: `0x18001c96a`
- name: `?DeleteConfigProperties@LOGGING_PLUGIN_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVPROPERTY_ENTRY@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z`
- size: `122`
- prototype: `__int64 __fastcall(LOGGING_PLUGIN_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct PROPERTY_ENTRY *, struct ABO_NODE *, struct INativeConfigurationElement *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001c8f0`
- `0x18002c010`

## string_xrefs

- `0x18001c93e`: `customLogPluginClsid`

## pseudocode

```c
__int64 __fastcall LOGGING_PLUGIN_CUSTOM_MAPPER::DeleteConfigProperties(
        LOGGING_PLUGIN_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct PROPERTY_ENTRY *a3,
        struct ABO_NODE *a4,
        struct INativeConfigurationElement *a5)
{
  __int64 result; // rax

  if ( !a2 || !a3 || !a4 || !a5 )
    return 2147942487LL;
  result = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *))(*(_QWORD *)a5 + 184LL))(
             a5,
             L"logFormat");
  if ( (int)(result + 0x80000000) < 0 || (_DWORD)result == -2147024894 )
  {
    result = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *))(*(_QWORD *)a5 + 184LL))(
               a5,
               L"customLogPluginClsid");
    if ( (_DWORD)result == -2147024894 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001c8f0  push    rbx
0x18001c8f2  sub     rsp, 20h
0x18001c8f6  test    rdx, rdx
0x18001c8f9  jz      short loc_18001C95F
0x18001c8fb  test    r8, r8
0x18001c8fe  jz      short loc_18001C95F
0x18001c900  test    r9, r9
0x18001c903  jz      short loc_18001C95F
0x18001c905  mov     rbx, [rsp+28h+arg_20]
0x18001c90a  test    rbx, rbx
0x18001c90d  jz      short loc_18001C95F
0x18001c90f  mov     rax, [rbx]
0x18001c912  lea     rdx, aLogformat; "logFormat"
0x18001c919  mov     rcx, rbx
0x18001c91c  mov     rax, [rax+0B8h]
0x18001c923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c928  mov     ecx, 80000000h
0x18001c92d  lea     edx, [rax+rcx]
0x18001c930  test    ecx, edx
0x18001c932  jnz     short loc_18001C93B
0x18001c934  cmp     eax, 80070002h
0x18001c939  jnz     short loc_18001C964
0x18001c93b  mov     rax, [rbx]
0x18001c93e  lea     rdx, aCustomlogplugi; "customLogPluginClsid"
0x18001c945  mov     rcx, rbx
0x18001c948  mov     rax, [rax+0B8h]
0x18001c94f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c954  cmp     eax, 80070002h
0x18001c959  jnz     short loc_18001C964
0x18001c95b  xor     eax, eax
0x18001c95d  jmp     short loc_18001C964
0x18001c95f  mov     eax, 80070057h
0x18001c964  add     rsp, 20h
0x18001c968  pop     rbx
0x18001c969  retn
```
