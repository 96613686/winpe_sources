# Windows::Compat::Inventory::CacheUtilities::HiveCache::SaveProvider(ushort const *,ushort const *)

- ea: `0x140010df0`
- end: `0x140010e7f`
- name: `?SaveProvider@HiveCache@CacheUtilities@Inventory@Compat@Windows@@UEAAXPEBG0@Z`
- size: `143`
- prototype: `void __fastcall(Windows::Compat::Inventory::CacheUtilities::HiveCache *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140010d70`
- `0x140010df0`
- `0x140018c3c`
- `0x140019258`
- `0x14001a8a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSaveKeyExW` at `0x140010e54`
- `api-ms-win-core-registry-l1-1-0!RegSaveKeyExW` at `0x140010e54`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140010e37`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140010e61`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140010e37`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140010e61`

## pseudocode

```c
void __fastcall Windows::Compat::Inventory::CacheUtilities::HiveCache::SaveProvider(
        Windows::Compat::Inventory::CacheUtilities::HiveCache *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v5; // rdx
  int v6; // eax
  HKEY *v7; // rbx
  PVOID P; // [rsp+48h] [rbp+20h] BYREF

  if ( Windows::Compat::Inventory::CacheUtilities::AmiCache::ProviderExists(this, a2) )
  {
    P = 0;
    v6 = AmiProviderInit(&P, v5, a2);
    v7 = (HKEY *)P;
    if ( !v6
      && !(unsigned int)AmiUtilitySetPrivilege(0x11u)
      && (DeleteFileW(a3) & 0xFFFFFFFD) == 0
      && RegSaveKeyExW(v7[1], a3, 0, 2u) )
    {
      DeleteFileW(a3);
    }
    if ( v7 )
      AmiStoreClose(v7);
  }
}

```

## disassembly

```asm
0x140010df0  mov     [rsp+arg_0], rbx
0x140010df5  push    rdi
0x140010df6  sub     rsp, 20h
0x140010dfa  mov     rdi, r8
0x140010dfd  mov     rbx, rdx
0x140010e00  call    ?ProviderExists@AmiCache@CacheUtilities@Inventory@Compat@Windows@@UEAA_NPEBG@Z; Windows::Compat::Inventory::CacheUtilities::AmiCache::ProviderExists(ushort const *)
0x140010e05  test    al, al
0x140010e07  jz      short loc_140010E74
0x140010e09  mov     r8, rbx
0x140010e0c  mov     [rsp+28h+P], 0
0x140010e15  lea     rcx, [rsp+28h+P]
0x140010e1a  call    AmiProviderInit
0x140010e1f  mov     rbx, [rsp+28h+P]
0x140010e24  test    eax, eax
0x140010e26  jnz     short loc_140010E67
0x140010e28  lea     ecx, [rax+11h]; unsigned int
0x140010e2b  call    ?AmiUtilitySetPrivilege@@YAKKE@Z; AmiUtilitySetPrivilege(ulong,uchar)
0x140010e30  test    eax, eax
0x140010e32  jnz     short loc_140010E67
0x140010e34  mov     rcx, rdi; lpFileName
0x140010e37  call    cs:__imp_DeleteFileW
0x140010e3d  test    eax, 0FFFFFFFDh
0x140010e42  jnz     short loc_140010E67
0x140010e44  mov     rcx, [rbx+8]; hKey
0x140010e48  mov     r9d, 2; Flags
0x140010e4e  xor     r8d, r8d; lpSecurityAttributes
0x140010e51  mov     rdx, rdi; lpFile
0x140010e54  call    cs:__imp_RegSaveKeyExW
0x140010e5a  test    eax, eax
0x140010e5c  jz      short loc_140010E67
0x140010e5e  mov     rcx, rdi; lpFileName
0x140010e61  call    cs:__imp_DeleteFileW
0x140010e67  test    rbx, rbx
0x140010e6a  jz      short loc_140010E74
0x140010e6c  mov     rcx, rbx; P
0x140010e6f  call    AmiStoreClose
0x140010e74  mov     rbx, [rsp+28h+arg_0]
0x140010e79  add     rsp, 20h
0x140010e7d  pop     rdi
0x140010e7e  retn
```
