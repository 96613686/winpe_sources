# LOGGING_PLUGIN_CUSTOM_MAPPER::SetConfigProperties(PROPERTY_MAPPING *,PROPERTY_ENTRY *,ABO_NODE *,INativeConfigurationElement *)

- ea: `0x180023bf0`
- end: `0x180023ce3`
- name: `?SetConfigProperties@LOGGING_PLUGIN_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVPROPERTY_ENTRY@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z`
- size: `243`
- prototype: `__int64 __fastcall(LOGGING_PLUGIN_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct PROPERTY_ENTRY *, struct ABO_NODE *, struct INativeConfigurationElement *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180023bf0`
- `0x18002c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180023c4e`
- `msvcrt!_wcsicmp` at `0x180023c66`
- `msvcrt!_wcsicmp` at `0x180023c7f`
- `msvcrt!_wcsicmp` at `0x180023c4e`
- `msvcrt!_wcsicmp` at `0x180023c66`
- `msvcrt!_wcsicmp` at `0x180023c7f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180023c2b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180023c2b`

## string_xrefs

- `0x180023cb7`: `customLogPluginClsid`

## pseudocode

```c
__int64 __fastcall LOGGING_PLUGIN_CUSTOM_MAPPER::SetConfigProperties(
        LOGGING_PLUGIN_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct PROPERTY_ENTRY *a3,
        struct ABO_NODE *a4,
        struct INativeConfigurationElement *a5)
{
  void *Ptr; // rax
  const wchar_t *v6; // rdi
  __int64 result; // rax
  unsigned int v8; // ebx

  if ( !a2 || !a3 || !a4 || !a5 )
    return 2147942487LL;
  Ptr = BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a3 + 16));
  v6 = (const wchar_t *)*((_QWORD *)Ptr + 3);
  if ( !*v6 )
    return 2147942402LL;
  if ( _wcsicmp(IIS_LOG_FORMAT_ID, *((const wchar_t **)Ptr + 3)) )
  {
    if ( _wcsicmp(NCSA_LOG_FORMAT_ID, v6) )
      v8 = (_wcsicmp(W3C_LOG_FORMAT_ID, v6) != 0) + 2;
    else
      v8 = 1;
  }
  else
  {
    v8 = 0;
  }
  result = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)a5 + 112LL))(
             a5,
             L"logFormat",
             v8,
             0);
  if ( (int)result >= 0 && v8 == 3 )
    return (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, const wchar_t *, _QWORD))(*(_QWORD *)a5 + 128LL))(
             a5,
             L"customLogPluginClsid",
             v6,
             0);
  return result;
}

```

## disassembly

```asm
0x180023bf0  push    rbx
0x180023bf2  push    rbp
0x180023bf3  push    rsi
0x180023bf4  push    rdi
0x180023bf5  sub     rsp, 38h
0x180023bf9  xor     ebp, ebp
0x180023bfb  test    rdx, rdx
0x180023bfe  jz      loc_180023CD5
0x180023c04  test    r8, r8
0x180023c07  jz      loc_180023CD5
0x180023c0d  test    r9, r9
0x180023c10  jz      loc_180023CD5
0x180023c16  mov     rsi, [rsp+58h+arg_20]
0x180023c1e  test    rsi, rsi
0x180023c21  jz      loc_180023CD5
0x180023c27  lea     rcx, [r8+10h]
0x180023c2b  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180023c31  mov     rdi, [rax+18h]
0x180023c35  cmp     [rdi], bp
0x180023c38  jnz     short loc_180023C44
0x180023c3a  mov     eax, 80070002h
0x180023c3f  jmp     loc_180023CDA
0x180023c44  mov     rdx, rdi; String2
0x180023c47  lea     rcx, ?IIS_LOG_FORMAT_ID@@3PAGA; "{FF160657-DE82-11CF-BC0A-00AA006111E0}"
0x180023c4e  call    cs:__imp__wcsicmp
0x180023c54  test    eax, eax
0x180023c56  jnz     short loc_180023C5C
0x180023c58  mov     ebx, ebp
0x180023c5a  jmp     short loc_180023C8F
0x180023c5c  mov     rdx, rdi; String2
0x180023c5f  lea     rcx, ?NCSA_LOG_FORMAT_ID@@3PAGA; "{FF16065F-DE82-11CF-BC0A-00AA006111E0}"
0x180023c66  call    cs:__imp__wcsicmp
0x180023c6c  test    eax, eax
0x180023c6e  jnz     short loc_180023C75
0x180023c70  lea     ebx, [rax+1]
0x180023c73  jmp     short loc_180023C8F
0x180023c75  mov     rdx, rdi; String2
0x180023c78  lea     rcx, ?W3C_LOG_FORMAT_ID@@3PAGA; "{FF160663-DE82-11CF-BC0A-00AA006111E0}"
0x180023c7f  call    cs:__imp__wcsicmp
0x180023c85  test    eax, eax
0x180023c87  mov     ebx, ebp
0x180023c89  setnz   bl
0x180023c8c  add     ebx, 2
0x180023c8f  mov     rax, [rsi]
0x180023c92  lea     rdx, aLogformat; "logFormat"
0x180023c99  xor     r9d, r9d
0x180023c9c  mov     r8d, ebx
0x180023c9f  mov     rcx, rsi
0x180023ca2  mov     rax, [rax+70h]
0x180023ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023cab  test    eax, eax
0x180023cad  js      short loc_180023CDA
0x180023caf  cmp     ebx, 3
0x180023cb2  jnz     short loc_180023CDA
0x180023cb4  mov     rax, [rsi]
0x180023cb7  lea     rdx, aCustomlogplugi; "customLogPluginClsid"
0x180023cbe  xor     r9d, r9d
0x180023cc1  mov     r8, rdi
0x180023cc4  mov     rcx, rsi
0x180023cc7  mov     rax, [rax+80h]
0x180023cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023cd3  jmp     short loc_180023CDA
0x180023cd5  mov     eax, 80070057h
0x180023cda  add     rsp, 38h
0x180023cde  pop     rdi
0x180023cdf  pop     rsi
0x180023ce0  pop     rbp
0x180023ce1  pop     rbx
0x180023ce2  retn
```
