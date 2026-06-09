# DIRECTORY_BROWSING_CUSTOM_MAPPER::DeleteConfigProperties(PROPERTY_MAPPING *,PROPERTY_ENTRY *,ABO_NODE *,INativeConfigurationElement *)

- ea: `0x18001c520`
- end: `0x18001c5b8`
- name: `?DeleteConfigProperties@DIRECTORY_BROWSING_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVPROPERTY_ENTRY@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(DIRECTORY_BROWSING_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct PROPERTY_ENTRY *, struct ABO_NODE *, struct INativeConfigurationElement *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180003426`
- `0x18001c520`
- `0x18002c010`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001c551`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001c551`

## string_xrefs

- `0x18001c55a`: `system.webServer/directoryBrowse`
- `0x18001c579`: `system.webServer/directoryBrowse`

## pseudocode

```c
__int64 __fastcall DIRECTORY_BROWSING_CUSTOM_MAPPER::DeleteConfigProperties(
        DIRECTORY_BROWSING_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct PROPERTY_ENTRY *a3,
        struct ABO_NODE *a4,
        struct INativeConfigurationElement *a5)
{
  unsigned int v6; // edi
  const wchar_t *Str; // rax
  __int64 v8; // rcx

  if ( a2 && a3 && a4 && a5 )
  {
    v6 = 0;
    Str = STRU::QueryStr((struct PROPERTY_MAPPING *)((char *)a2 + 32));
    if ( !wcscmp_0(Str, L"system.webServer/directoryBrowse") )
    {
      v8 = *((_QWORD *)a4 + 29);
      if ( v8 )
        (*(void (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v8 + 56LL))(
          v8,
          L"system.webServer/directoryBrowse");
    }
    else
    {
      (*(void (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *))(*(_QWORD *)a5 + 184LL))(
        a5,
        L"enabled");
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x18001c520  mov     [rsp+arg_0], rbx
0x18001c525  mov     [rsp+arg_8], rsi
0x18001c52a  push    rdi
0x18001c52b  sub     rsp, 20h
0x18001c52f  mov     rsi, r9
0x18001c532  test    rdx, rdx
0x18001c535  jz      short loc_18001C5A1
0x18001c537  test    r8, r8
0x18001c53a  jz      short loc_18001C5A1
0x18001c53c  test    r9, r9
0x18001c53f  jz      short loc_18001C5A1
0x18001c541  mov     rbx, [rsp+28h+arg_20]
0x18001c546  test    rbx, rbx
0x18001c549  jz      short loc_18001C5A1
0x18001c54b  lea     rcx, [rdx+20h]
0x18001c54f  xor     edi, edi
0x18001c551  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18001c557  mov     rcx, rax; String1
0x18001c55a  lea     rdx, aSystemWebserve_5; "system.webServer/directoryBrowse"
0x18001c561  call    wcscmp_0
0x18001c566  test    eax, eax
0x18001c568  jnz     short loc_18001C586
0x18001c56a  mov     rcx, [rsi+0E8h]
0x18001c571  test    rcx, rcx
0x18001c574  jz      short loc_18001C5A6
0x18001c576  mov     rax, [rcx]
0x18001c579  lea     rdx, aSystemWebserve_5; "system.webServer/directoryBrowse"
0x18001c580  mov     rax, [rax+38h]
0x18001c584  jmp     short loc_18001C59A
0x18001c586  mov     rax, [rbx]
0x18001c589  lea     rdx, aEnabled; "enabled"
0x18001c590  mov     rcx, rbx
0x18001c593  mov     rax, [rax+0B8h]
0x18001c59a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c59f  jmp     short loc_18001C5A6
0x18001c5a1  mov     edi, 80070057h
0x18001c5a6  mov     rbx, [rsp+28h+arg_0]
0x18001c5ab  mov     eax, edi
0x18001c5ad  mov     rsi, [rsp+28h+arg_8]
0x18001c5b2  add     rsp, 20h
0x18001c5b6  pop     rdi
0x18001c5b7  retn
```
