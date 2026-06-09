# Windows::Compat::Inventory::AepicInvCache::CreateItem(ushort const *,Windows::Compat::Inventory::InventoryCacheItem * &)

- ea: `0x1800116e0`
- end: `0x1800118a7`
- name: `?CreateItem@AepicInvCache@Inventory@Compat@Windows@@UEAAJPEBGAEAPEAVInventoryCacheItem@234@@Z`
- size: `455`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::AepicInvCache *__hidden this, const unsigned __int16 *, struct Windows::Compat::Inventory::InventoryCacheItem **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005d6c`
- `0x1800116e0`
- `0x180028990`
- `0x1800295dc`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800117e8`
- `ntdll!RtlAllocateHeap` at `0x1800117e8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011775`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011775`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001180a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001180a`

## string_xrefs

- `0x180011875`: `InvCacheOpenItem failed [%#x]`
- `0x180011886`: `Windows::Compat::Inventory::AepicInvCache::CreateItem`
- `0x18001178e`: `RegCreateKeyEx failed [%#x]`
- `0x1800117a0`: `InvCacheOpenItem`
- `0x1800117be`: `Item already exists and CREATE_NEW_CACHE_ITEM specified [%#x]`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::AepicInvCache::CreateItem(
        Windows::Compat::Inventory::AepicInvCache *this,
        const unsigned __int16 *a2,
        struct Windows::Compat::Inventory::InventoryCacheItem **a3)
{
  __int64 v3; // r9
  __int64 v5; // rax
  HKEY v6; // rcx
  LSTATUS v7; // eax
  signed int v8; // ebx
  const char *v9; // r9
  __int64 v10; // r8
  __int64 v11; // rcx
  _DWORD *Heap; // rax
  void *v13; // rsi
  unsigned int v14; // edi
  struct Windows::Compat::Inventory::InventoryCacheItem *v15; // rax
  __int64 dwOptions; // [rsp+20h] [rbp-48h]
  struct Windows::Compat::Inventory::InventoryCacheItem *v18; // [rsp+70h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+20h] BYREF

  v3 = *((_QWORD *)this + 1);
  hKey = 0;
  if ( !v3 || *(_DWORD *)v3 != 1 || !a2 || !*a2 || (v5 = *(_QWORD *)(v3 + 8)) == 0 || (v6 = *(HKEY *)(v5 + 8)) == 0 )
  {
    v14 = -2147024809;
    v8 = -2147024809;
LABEL_26:
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::AepicInvCache::CreateItem",
      235,
      "InvCacheOpenItem failed [%#x]",
      v8);
    return v14;
  }
  LODWORD(v18) = 0;
  v7 = RegCreateKeyExW(v6, a2, 0, 0, 0, 0xF003Fu, 0, &hKey, (LPDWORD)&v18);
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  if ( v8 < 0 )
  {
    v9 = "RegCreateKeyEx failed [%#x]";
    v10 = 159;
    v11 = 1;
LABEL_11:
    LODWORD(dwOptions) = v8;
    AslLogCallPrintf(v11, "InvCacheOpenItem", v10, v9, dwOptions);
LABEL_16:
    if ( hKey )
      RegCloseKey(hKey);
    v14 = v8;
    goto LABEL_26;
  }
  if ( (_DWORD)v18 == 2 )
  {
    v8 = -2147024198;
    v9 = "Item already exists and CREATE_NEW_CACHE_ITEM specified [%#x]";
    v10 = 166;
    v11 = 3;
    goto LABEL_11;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x10u);
  v13 = Heap;
  if ( !Heap )
  {
    v8 = -2147024882;
    goto LABEL_16;
  }
  *Heap = 2;
  v14 = 0;
  *((_QWORD *)Heap + 1) = hKey;
  v15 = (struct Windows::Compat::Inventory::InventoryCacheItem *)operator new(
                                                                   0x10u,
                                                                   (const struct std::nothrow_t *)std::nothrow);
  v18 = v15;
  if ( v15 )
  {
    *((_QWORD *)v15 + 1) = v13;
    *(_QWORD *)v15 = &Windows::Compat::Inventory::AepicInvCacheItem::`vftable';
    *a3 = v15;
  }
  else
  {
    v14 = -2147024882;
    if ( v13 )
      InvCacheCloseHandle(v13);
  }
  return v14;
}

```

## disassembly

```asm
0x1800116e0  mov     r11, rsp
0x1800116e3  mov     [r11+10h], rbx
0x1800116e7  push    rsi
0x1800116e8  push    rdi
0x1800116e9  push    r14
0x1800116eb  sub     rsp, 50h
0x1800116ef  mov     r9, [rcx+8]
0x1800116f3  mov     r14, r8
0x1800116f6  mov     qword ptr [r11+20h], 0
0x1800116fe  test    r9, r9
0x180011701  jz      loc_18001186E
0x180011707  cmp     dword ptr [r9], 1
0x18001170b  jnz     loc_18001186E
0x180011711  test    rdx, rdx
0x180011714  jz      loc_18001186E
0x18001171a  xor     eax, eax
0x18001171c  cmp     ax, [rdx]
0x18001171f  jz      loc_18001186E
0x180011725  mov     rax, [r9+8]
0x180011729  test    rax, rax
0x18001172c  jz      loc_18001186E
0x180011732  mov     rcx, [rax+8]; hKey
0x180011736  test    rcx, rcx
0x180011739  jz      loc_18001186E
0x18001173f  lea     rax, [r11+8]
0x180011743  mov     dword ptr [rsp+68h+arg_0], 0
0x18001174b  mov     [r11-28h], rax
0x18001174f  xor     r9d, r9d; lpClass
0x180011752  lea     rax, [r11+20h]
0x180011756  xor     r8d, r8d; Reserved
0x180011759  mov     [r11-30h], rax
0x18001175d  mov     qword ptr [r11-38h], 0
0x180011765  mov     [rsp+68h+samDesired], 0F003Fh; samDesired
0x18001176d  mov     dword ptr [rsp+68h+dwOptions], 0; dwOptions
0x180011775  call    cs:__imp_RegCreateKeyExW
0x18001177b  mov     ebx, eax
0x18001177d  test    eax, eax
0x18001177f  jle     short loc_18001178A
0x180011781  movzx   ebx, ax
0x180011784  or      ebx, 80070000h
0x18001178a  test    ebx, ebx
0x18001178c  jns     short loc_1800117B2
0x18001178e  lea     r9, aRegcreatekeyex_0; "RegCreateKeyEx failed [%#x]"
0x180011795  mov     r8d, 9Fh
0x18001179b  mov     ecx, 1
0x1800117a0  lea     rdx, aInvcacheopenit_0; "InvCacheOpenItem"
0x1800117a7  mov     dword ptr [rsp+68h+dwOptions], ebx
0x1800117ab  call    AslLogCallPrintf
0x1800117b0  jmp     short loc_1800117FB
0x1800117b2  cmp     dword ptr [rsp+68h+arg_0], 2
0x1800117b7  jnz     short loc_1800117D2
0x1800117b9  mov     ebx, 800702BAh
0x1800117be  lea     r9, aItemAlreadyExi; "Item already exists and CREATE_NEW_CACH"...
0x1800117c5  mov     r8d, 0A6h
0x1800117cb  mov     ecx, 3
0x1800117d0  jmp     short loc_1800117A0
0x1800117d2  mov     rcx, gs:60h
0x1800117db  mov     edx, 8; Flags
0x1800117e0  mov     rcx, [rcx+30h]; HeapHandle
0x1800117e4  lea     r8d, [rdx+8]; Size
0x1800117e8  call    cs:__imp_RtlAllocateHeap
0x1800117ee  mov     rsi, rax
0x1800117f1  test    rax, rax
0x1800117f4  jnz     short loc_180011818
0x1800117f6  mov     ebx, 8007000Eh
0x1800117fb  mov     rcx, [rsp+68h+hKey]; hKey
0x180011803  xor     esi, esi
0x180011805  test    rcx, rcx
0x180011808  jz      short loc_180011810
0x18001180a  call    cs:__imp_RegCloseKey
0x180011810  mov     edi, ebx
0x180011812  test    ebx, ebx
0x180011814  jns     short loc_18001182C
0x180011816  jmp     short loc_180011875
0x180011818  mov     dword ptr [rax], 2
0x18001181e  xor     edi, edi
0x180011820  mov     rax, [rsp+68h+hKey]
0x180011828  mov     [rsi+8], rax
0x18001182c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011833  mov     ecx, 10h; unsigned __int64
0x180011838  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001183d  mov     [rsp+68h+arg_0], rax
0x180011842  test    rax, rax
0x180011845  jz      short loc_18001185A
0x180011847  lea     rcx, ??_7AepicInvCacheItem@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::AepicInvCacheItem::`vftable'
0x18001184e  mov     [rax+8], rsi
0x180011852  mov     [rax], rcx
0x180011855  mov     [r14], rax
0x180011858  jmp     short loc_180011897
0x18001185a  mov     edi, 8007000Eh
0x18001185f  test    rsi, rsi
0x180011862  jz      short loc_180011897
0x180011864  mov     rcx, rsi; P
0x180011867  call    InvCacheCloseHandle
0x18001186c  jmp     short loc_180011897
0x18001186e  mov     edi, 80070057h
0x180011873  mov     ebx, edi
0x180011875  lea     r9, aInvcacheopenit; "InvCacheOpenItem failed [%#x]"
0x18001187c  mov     dword ptr [rsp+68h+dwOptions], ebx
0x180011880  mov     r8d, 0EBh
0x180011886  lea     rdx, aWindowsCompatI_21; "Windows::Compat::Inventory::AepicInvCac"...
0x18001188d  mov     ecx, 1
0x180011892  call    AslLogCallPrintf
0x180011897  mov     rbx, [rsp+68h+arg_8]
0x18001189c  mov     eax, edi
0x18001189e  add     rsp, 50h
0x1800118a2  pop     r14
0x1800118a4  pop     rdi
0x1800118a5  pop     rsi
0x1800118a6  retn
```
