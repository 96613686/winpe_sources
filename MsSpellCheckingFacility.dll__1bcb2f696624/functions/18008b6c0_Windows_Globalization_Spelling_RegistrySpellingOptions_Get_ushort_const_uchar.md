# Windows::Globalization::Spelling::RegistrySpellingOptions::Get(ushort const *,uchar *)

- ea: `0x18008b6c0`
- end: `0x18008b7b8`
- name: `?Get@RegistrySpellingOptions@Spelling@Globalization@Windows@@UEAAJPEBGPEAE@Z`
- size: `248`
- prototype: `int(Windows::Globalization::Spelling::RegistrySpellingOptions *__hidden this, const unsigned __int16 *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180082b24`
- `0x18008b6c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008b78a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008b78a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008b76d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008b76d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008b71a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18008b71a`

## pseudocode

```c
__int64 __fastcall Windows::Globalization::Spelling::RegistrySpellingOptions::Get(
        Windows::Globalization::Spelling::RegistrySpellingOptions *this,
        const unsigned __int16 *a2,
        unsigned __int8 *a3)
{
  LSTATUS ValueW; // edi
  HKEY hkey; // [rsp+50h] [rbp-18h] BYREF
  unsigned int pvData; // [rsp+80h] [rbp+18h] BYREF
  DWORD pcbData; // [rsp+88h] [rbp+20h] BYREF

  *a3 = 0;
  hkey = 0;
  if ( RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Spelling\\Options", 0, 0, 0, 1u, 0, &hkey, 0) )
    return 1;
  pvData = 0;
  pcbData = 4;
  ValueW = RegGetValueW(hkey, 0, a2, 0x10u, 0, &pvData, &pcbData);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixMemoryLeakInRoamingDictionaryManager>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixMemoryLeakInRoamingDictionaryManager>::GetImpl'::`2'::impl) )
    RegCloseKey(hkey);
  if ( ValueW || pvData > 0xFF )
    return 1;
  *a3 = pvData;
  return 0;
}

```

## disassembly

```asm
0x18008b6c0  mov     r11, rsp
0x18008b6c3  mov     [r11+8], rbx
0x18008b6c7  push    rdi
0x18008b6c8  sub     rsp, 60h
0x18008b6cc  mov     qword ptr [r11-28h], 0
0x18008b6d4  lea     rax, [r11-18h]
0x18008b6d8  mov     [r11-30h], rax
0x18008b6dc  mov     rbx, r8
0x18008b6df  mov     qword ptr [r11-38h], 0
0x18008b6e7  mov     rdi, rdx
0x18008b6ea  mov     byte ptr [r8], 0
0x18008b6ee  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Spelling\\Options"
0x18008b6f5  mov     [rsp+68h+samDesired], 1; samDesired
0x18008b6fd  xor     r9d, r9d; lpClass
0x18008b700  xor     r8d, r8d; Reserved
0x18008b703  mov     [rsp+68h+dwOptions], 0; dwOptions
0x18008b70b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18008b712  mov     qword ptr [r11-18h], 0
0x18008b71a  call    cs:__imp_RegCreateKeyExW
0x18008b720  test    eax, eax
0x18008b722  jnz     loc_18008B7A8
0x18008b728  mov     rcx, [rsp+68h+hkey]; hkey
0x18008b72d  mov     r9d, 10h; dwFlags
0x18008b733  mov     [rsp+68h+pvData], eax
0x18008b73a  mov     r8, rdi; lpValue
0x18008b73d  lea     rax, [rsp+68h+arg_18]
0x18008b745  mov     [rsp+68h+arg_18], 4
0x18008b750  mov     [rsp+68h+pcbData], rax; pcbData
0x18008b755  xor     edx, edx; lpSubKey
0x18008b757  lea     rax, [rsp+68h+pvData]
0x18008b75f  mov     qword ptr [rsp+68h+samDesired], rax; pvData
0x18008b764  mov     qword ptr [rsp+68h+dwOptions], 0; pdwType
0x18008b76d  call    cs:__imp_RegGetValueW
0x18008b773  mov     edi, eax
0x18008b775  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixMemoryLeakInRoamingDictionaryManager@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixMemoryLeakInRoamingDictionaryManager@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixMemoryLeakInRoamingDictionaryManager> `wil::Feature<__WilFeatureTraits_Feature_FixMemoryLeakInRoamingDictionaryManager>::GetImpl(void)'::`2'::impl
0x18008b77c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixMemoryLeakInRoamingDictionaryManager@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixMemoryLeakInRoamingDictionaryManager>::__private_IsEnabled(void)
0x18008b781  test    al, al
0x18008b783  jz      short loc_18008B790
0x18008b785  mov     rcx, [rsp+68h+hkey]; hKey
0x18008b78a  call    cs:__imp_RegCloseKey
0x18008b790  test    edi, edi
0x18008b792  jnz     short loc_18008B7A8
0x18008b794  mov     eax, [rsp+68h+pvData]
0x18008b79b  cmp     eax, 0FFh
0x18008b7a0  ja      short loc_18008B7A8
0x18008b7a2  mov     [rbx], al
0x18008b7a4  xor     eax, eax
0x18008b7a6  jmp     short loc_18008B7AD
0x18008b7a8  mov     eax, 1
0x18008b7ad  mov     rbx, [rsp+68h+arg_0]
0x18008b7b2  add     rsp, 60h
0x18008b7b6  pop     rdi
0x18008b7b7  retn
```
