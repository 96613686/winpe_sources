# GetFavoritesOrderStream(_ITEMIDLIST const *,ulong,ushort const *)

- ea: `0x180015774`
- end: `0x1800157e2`
- name: `?GetFavoritesOrderStream@@YAPEAUIStream@@PEFBU_ITEMIDLIST@@KPEBG@Z`
- size: `110`
- prototype: `struct IStream *(const struct _ITEMIDLIST *, unsigned int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180015544`
- `0x180016fa8`

## callees

- `0x180015774`
- `0x180015948`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l2-1-0!SHOpenRegStream2W` at `0x1800157bb`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHOpenRegStream2W` at `0x1800157bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800157c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800157c9`

## pseudocode

```c
struct IStream *__fastcall GetFavoritesOrderStream(const struct _ITEMIDLIST *a1, DWORD a2, const unsigned __int16 *a3)
{
  IStream *v4; // rbx
  HKEY hkey; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  if ( a1 )
  {
    if ( a1->mkid.cb )
    {
      hkey = 0;
      if ( OpenFavoritesFolderOrderKeyX(a1, &hkey, a3) >= 0 )
      {
        v4 = SHOpenRegStream2W(hkey, &pszSubkey, L"Order", a2);
        RegCloseKey(hkey);
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180015774  mov     rax, rsp
0x180015777  mov     [rax+10h], rbx
0x18001577b  mov     [rax+18h], rsi
0x18001577f  push    rdi
0x180015780  sub     rsp, 20h
0x180015784  xor     esi, esi
0x180015786  mov     edi, edx
0x180015788  mov     ebx, esi
0x18001578a  test    rcx, rcx
0x18001578d  jz      short loc_1800157CF
0x18001578f  cmp     [rcx], si
0x180015792  jz      short loc_1800157CF
0x180015794  lea     rdx, [rax+8]; phkResult
0x180015798  mov     [rax+8], rsi
0x18001579c  call    ?OpenFavoritesFolderOrderKeyX@@YAJPEFBU_ITEMIDLIST@@PEAPEAUHKEY__@@PEBG@Z; OpenFavoritesFolderOrderKeyX(_ITEMIDLIST const *,HKEY__ * *,ushort const *)
0x1800157a1  test    eax, eax
0x1800157a3  js      short loc_1800157CF
0x1800157a5  mov     rcx, [rsp+28h+hkey]; hkey
0x1800157aa  lea     r8, pszValue; "Order"
0x1800157b1  mov     r9d, edi; grfMode
0x1800157b4  lea     rdx, pszSubkey; pszSubkey
0x1800157bb  call    cs:__imp_SHOpenRegStream2W
0x1800157c1  mov     rcx, [rsp+28h+hkey]; hKey
0x1800157c6  mov     rbx, rax
0x1800157c9  call    cs:__imp_RegCloseKey
0x1800157cf  mov     rsi, [rsp+28h+arg_10]
0x1800157d4  mov     rax, rbx
0x1800157d7  mov     rbx, [rsp+28h+arg_8]
0x1800157dc  add     rsp, 20h
0x1800157e0  pop     rdi
0x1800157e1  retn
```
