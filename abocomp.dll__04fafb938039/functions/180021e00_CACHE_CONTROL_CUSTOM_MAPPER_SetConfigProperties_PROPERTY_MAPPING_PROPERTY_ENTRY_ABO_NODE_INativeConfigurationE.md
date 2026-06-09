# CACHE_CONTROL_CUSTOM_MAPPER::SetConfigProperties(PROPERTY_MAPPING *,PROPERTY_ENTRY *,ABO_NODE *,INativeConfigurationElement *)

- ea: `0x180021e00`
- end: `0x180021e6b`
- name: `?SetConfigProperties@CACHE_CONTROL_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVPROPERTY_ENTRY@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z`
- size: `107`
- prototype: `__int64 __fastcall(CACHE_CONTROL_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct PROPERTY_ENTRY *, struct ABO_NODE *, struct INativeConfigurationElement *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180021e00`
- `0x18002c010`

## import_xrefs

- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180021e29`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180021e29`

## string_xrefs

- `0x180021e3f`: `cacheControlMode`

## pseudocode

```c
__int64 __fastcall CACHE_CONTROL_CUSTOM_MAPPER::SetConfigProperties(
        CACHE_CONTROL_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct PROPERTY_ENTRY *a3,
        struct ABO_NODE *a4,
        struct INativeConfigurationElement *a5)
{
  unsigned int v5; // ebx

  if ( a2 && a3 && a4 && a5 )
  {
    v5 = 0;
    if ( **((_DWORD **)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a3 + 16)) + 3) == 1 )
      return (*(unsigned int (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, __int64, _QWORD))(*(_QWORD *)a5 + 112LL))(
               a5,
               L"cacheControlMode",
               1,
               0);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v5;
}

```

## disassembly

```asm
0x180021e00  mov     [rsp+arg_0], rbx
0x180021e05  push    rdi
0x180021e06  sub     rsp, 30h
0x180021e0a  test    rdx, rdx
0x180021e0d  jz      short loc_180021E59
0x180021e0f  test    r8, r8
0x180021e12  jz      short loc_180021E59
0x180021e14  test    r9, r9
0x180021e17  jz      short loc_180021E59
0x180021e19  mov     rdi, [rsp+38h+arg_20]
0x180021e1e  test    rdi, rdi
0x180021e21  jz      short loc_180021E59
0x180021e23  lea     rcx, [r8+10h]
0x180021e27  xor     ebx, ebx
0x180021e29  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180021e2f  lea     r8d, [rbx+1]
0x180021e33  mov     rdx, [rax+18h]
0x180021e37  cmp     [rdx], r8d
0x180021e3a  jnz     short loc_180021E5E
0x180021e3c  mov     rax, [rdi]
0x180021e3f  lea     rdx, aCachecontrolmo; "cacheControlMode"
0x180021e46  xor     r9d, r9d
0x180021e49  mov     rcx, rdi
0x180021e4c  mov     rax, [rax+70h]
0x180021e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e55  mov     ebx, eax
0x180021e57  jmp     short loc_180021E5E
0x180021e59  mov     ebx, 80070057h
0x180021e5e  mov     eax, ebx
0x180021e60  mov     rbx, [rsp+38h+arg_0]
0x180021e65  add     rsp, 30h
0x180021e69  pop     rdi
0x180021e6a  retn
```
