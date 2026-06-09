# _dynamic_initializer_for__gc_wszRegMultivariant__

- ea: `0x180001870`
- end: `0x1800018ee`
- name: `_dynamic_initializer_for__gc_wszRegMultivariant__`
- size: `126`
- prototype: `const WCHAR *()`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001870`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800018a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800018a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800018bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800018bb`

## pseudocode

```c
const WCHAR *dynamic_initializer_for__gc_wszRegMultivariant__()
{
  const WCHAR *result; // rax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  if ( !`MVIsStateSeparationEnabled'::`2'::s_HasRun )
  {
    hKey = 0;
    `MVIsStateSeparationEnabled'::`2'::s_Redirection = RegOpenKeyExW(
                                                         HKEY_LOCAL_MACHINE,
                                                         L"Software\\Microsoft\\Provisioning\\StateSeparationMode",
                                                         0,
                                                         0x20119u,
                                                         &hKey) == 0;
    RegCloseKey(hKey);
    `MVIsStateSeparationEnabled'::`2'::s_HasRun = 1;
  }
  result = L"OSData\\Software\\Microsoft\\Multivariant";
  if ( !`MVIsStateSeparationEnabled'::`2'::s_Redirection )
    result = L"Software\\Microsoft\\Multivariant";
  gc_wszRegMultivariant = result;
  return result;
}

```

## disassembly

```asm
0x180001870  sub     rsp, 38h
0x180001874  cmp     cs:?s_HasRun@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA, 0; bool `MVIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x18000187b  jnz     short loc_1800018C8
0x18000187d  lea     rax, [rsp+38h+hKey]
0x180001882  mov     [rsp+38h+hKey], 0
0x18000188b  mov     r9d, 20119h; samDesired
0x180001891  mov     [rsp+38h+phkResult], rax; phkResult
0x180001896  xor     r8d, r8d; ulOptions
0x180001899  lea     rdx, SubKey; "Software\\Microsoft\\Provisioning\\Stat"...
0x1800018a0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800018a7  call    cs:__imp_RegOpenKeyExW
0x1800018ad  mov     rcx, [rsp+38h+hKey]; hKey
0x1800018b2  test    eax, eax
0x1800018b4  setz    cs:?s_Redirection@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `MVIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x1800018bb  call    cs:__imp_RegCloseKey
0x1800018c1  mov     cs:?s_HasRun@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `MVIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x1800018c8  mov     cl, cs:?s_Redirection@?1??MVIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `MVIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x1800018ce  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Multivariant"
0x1800018d5  test    cl, cl
0x1800018d7  lea     rax, aOsdataSoftware; "OSData\\Software\\Microsoft\\Multivaria"...
0x1800018de  cmovz   rax, rdx
0x1800018e2  mov     cs:?gc_wszRegMultivariant@@3PEBGEB, rax; ushort const * const gc_wszRegMultivariant
0x1800018e9  add     rsp, 38h
0x1800018ed  retn
```
