# RegistryRegRow::PutValue(uint,tagPROPVARIANT *)

- ea: `0x18003b550`
- end: `0x18003b664`
- name: `?PutValue@RegistryRegRow@@UEAAJIPEAUtagPROPVARIANT@@@Z`
- size: `276`
- prototype: `int(RegistryRegRow *__hidden this, unsigned int, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180028630`
- `0x180028938`
- `0x18002c234`
- `0x18003b550`
- `0x18003bfa4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b60e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b60e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b635`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b635`

## pseudocode

```c
__int64 __fastcall RegistryRegRow::PutValue(RegistryRegRow *this, unsigned int a2, struct tagPROPVARIANT *a3)
{
  __int64 v5; // rax
  __int64 v7; // rsi
  __int64 v8; // r14
  int KeyIfNeccessary; // ebx
  const WCHAR *v10; // rdx
  HKEY v11; // rcx
  LSTATUS v12; // eax
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF

  if ( !a3 )
    return 2147942487LL;
  v5 = *((_QWORD *)this + 7);
  if ( !v5 )
    return 2147807233LL;
  if ( a2 >= *(_DWORD *)(v5 + 544) )
    return 2147942487LL;
  v7 = a2;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow>::GetImpl'::`2'::impl) )
    std::_Atomic_store_4(*((_QWORD *)this + 10) + 4 * v7, 0, 3);
  else
    *(_DWORD *)(*((_QWORD *)this + 9) + 4 * v7) = 0;
  v8 = *(_QWORD *)(*((_QWORD *)this + 7) + 552LL);
  KeyIfNeccessary = CreateKeyIfNeccessary(*((HKEY *)this + 16), *((LPCWSTR *)this + 15), *((LPCWSTR *)this + 14));
  if ( KeyIfNeccessary >= 0 )
  {
    v10 = (const WCHAR *)*((_QWORD *)this + 15);
    v11 = (HKEY)*((_QWORD *)this + 16);
    hKey = 0;
    v12 = RegOpenKeyExW(v11, v10, 0, 0x20006u, &hKey);
    KeyIfNeccessary = v12;
    if ( v12 )
    {
      if ( v12 > 0 )
        return (unsigned __int16)v12 | 0x80070000;
    }
    else
    {
      KeyIfNeccessary = WriteField(hKey, (const struct tagFieldInfo *)(v8 + 16 * v7), a3);
      RegCloseKey(hKey);
    }
  }
  return (unsigned int)KeyIfNeccessary;
}

```

## disassembly

```asm
0x18003b550  mov     [rsp+arg_0], rbx
0x18003b555  mov     [rsp+arg_8], rbp
0x18003b55a  push    rsi
0x18003b55b  push    rdi
0x18003b55c  push    r14
0x18003b55e  sub     rsp, 30h
0x18003b562  mov     rbp, r8
0x18003b565  mov     rdi, rcx
0x18003b568  test    r8, r8
0x18003b56b  jz      loc_18003B64C
0x18003b571  mov     rax, [rcx+38h]
0x18003b575  test    rax, rax
0x18003b578  jnz     short loc_18003B584
0x18003b57a  mov     eax, 8004F001h
0x18003b57f  jmp     loc_18003B651
0x18003b584  cmp     edx, [rax+220h]
0x18003b58a  jnb     loc_18003B64C
0x18003b590  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow> `wil::Feature<__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow>::GetImpl(void)'::`2'::impl
0x18003b597  mov     esi, edx
0x18003b599  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixNonAtomicAccessInRegistryRegRow>::__private_IsEnabled(void)
0x18003b59e  test    al, al
0x18003b5a0  jz      short loc_18003B5B7
0x18003b5a2  mov     rax, [rdi+50h]
0x18003b5a6  xor     edx, edx
0x18003b5a8  lea     rcx, [rax+rsi*4]
0x18003b5ac  lea     r8d, [rdx+3]
0x18003b5b0  call    ?_Atomic_store_4@std@@YAXPECKKW4memory_order@1@@Z; std::_Atomic_store_4(ulong volatile *,ulong,std::memory_order)
0x18003b5b5  jmp     short loc_18003B5C2
0x18003b5b7  mov     rax, [rdi+48h]
0x18003b5bb  mov     dword ptr [rax+rsi*4], 0
0x18003b5c2  mov     rax, [rdi+38h]
0x18003b5c6  mov     r8, [rdi+70h]; StringSecurityDescriptor
0x18003b5ca  mov     rdx, [rdi+78h]; lpSubKey
0x18003b5ce  mov     rcx, [rdi+80h]; hKey
0x18003b5d5  mov     r14, [rax+228h]
0x18003b5dc  call    ?CreateKeyIfNeccessary@@YAJPEAUHKEY__@@PEBG1@Z; CreateKeyIfNeccessary(HKEY__ *,ushort const *,ushort const *)
0x18003b5e1  mov     ebx, eax
0x18003b5e3  test    eax, eax
0x18003b5e5  js      short loc_18003B648
0x18003b5e7  mov     rdx, [rdi+78h]; lpSubKey
0x18003b5eb  lea     rax, [rsp+48h+hKey]
0x18003b5f0  mov     rcx, [rdi+80h]; hKey
0x18003b5f7  mov     r9d, 20006h; samDesired
0x18003b5fd  xor     r8d, r8d; ulOptions
0x18003b600  mov     [rsp+48h+phkResult], rax; phkResult
0x18003b605  mov     [rsp+48h+hKey], 0
0x18003b60e  call    cs:__imp_RegOpenKeyExW
0x18003b614  mov     ebx, eax
0x18003b616  test    eax, eax
0x18003b618  jnz     short loc_18003B63D
0x18003b61a  mov     rcx, [rsp+48h+hKey]; hKey
0x18003b61f  add     rsi, rsi
0x18003b622  mov     r8, rbp; struct tagPROPVARIANT *
0x18003b625  lea     rdx, [r14+rsi*8]; struct tagFieldInfo *
0x18003b629  call    ?WriteField@@YAJPEAUHKEY__@@AEBUtagFieldInfo@@AEAUtagPROPVARIANT@@@Z; WriteField(HKEY__ *,tagFieldInfo const &,tagPROPVARIANT &)
0x18003b62e  mov     rcx, [rsp+48h+hKey]; hKey
0x18003b633  mov     ebx, eax
0x18003b635  call    cs:__imp_RegCloseKey
0x18003b63b  jmp     short loc_18003B648
0x18003b63d  jle     short loc_18003B648
0x18003b63f  movzx   ebx, ax
0x18003b642  or      ebx, 80070000h
0x18003b648  mov     eax, ebx
0x18003b64a  jmp     short loc_18003B651
0x18003b64c  mov     eax, 80070057h
0x18003b651  mov     rbx, [rsp+48h+arg_0]
0x18003b656  mov     rbp, [rsp+48h+arg_8]
0x18003b65b  add     rsp, 30h
0x18003b65f  pop     r14
0x18003b661  pop     rdi
0x18003b662  pop     rsi
0x18003b663  retn
```
