# Windows::Compat::Inventory::CacheUtilities::HiveCache::ClearProvider(ushort const *)

- ea: `0x14000f130`
- end: `0x14000f180`
- name: `?ClearProvider@HiveCache@CacheUtilities@Inventory@Compat@Windows@@UEAAXPEBG@Z`
- size: `80`
- prototype: `void __fastcall(Windows::Compat::Inventory::CacheUtilities::HiveCache *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000f130`
- `0x140010d70`
- `0x140019258`
- `0x14001a8a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x14000f167`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x14000f167`

## pseudocode

```c
void __fastcall Windows::Compat::Inventory::CacheUtilities::HiveCache::ClearProvider(
        Windows::Compat::Inventory::CacheUtilities::HiveCache *this,
        const unsigned __int16 *a2)
{
  __int64 v3; // rdx
  int v4; // eax
  PVOID v5; // rbx
  PVOID P; // [rsp+40h] [rbp+18h] BYREF

  if ( Windows::Compat::Inventory::CacheUtilities::AmiCache::ProviderExists(this, a2) )
  {
    P = 0;
    v4 = AmiProviderInit(&P, v3, a2);
    v5 = P;
    if ( !v4 )
      RegDeleteTreeW(*((HKEY *)P + 1), 0);
    if ( v5 )
      AmiStoreClose(v5);
  }
}

```

## disassembly

```asm
0x14000f130  push    rbx
0x14000f132  sub     rsp, 20h
0x14000f136  mov     rbx, rdx
0x14000f139  call    ?ProviderExists@AmiCache@CacheUtilities@Inventory@Compat@Windows@@UEAA_NPEBG@Z; Windows::Compat::Inventory::CacheUtilities::AmiCache::ProviderExists(ushort const *)
0x14000f13e  test    al, al
0x14000f140  jz      short loc_14000F17A
0x14000f142  mov     r8, rbx
0x14000f145  mov     [rsp+28h+P], 0
0x14000f14e  lea     rcx, [rsp+28h+P]
0x14000f153  call    AmiProviderInit
0x14000f158  mov     rbx, [rsp+28h+P]
0x14000f15d  test    eax, eax
0x14000f15f  jnz     short loc_14000F16D
0x14000f161  mov     rcx, [rbx+8]; hKey
0x14000f165  xor     edx, edx; lpSubKey
0x14000f167  call    cs:__imp_RegDeleteTreeW
0x14000f16d  test    rbx, rbx
0x14000f170  jz      short loc_14000F17A
0x14000f172  mov     rcx, rbx; P
0x14000f175  call    AmiStoreClose
0x14000f17a  add     rsp, 20h
0x14000f17e  pop     rbx
0x14000f17f  retn
```
