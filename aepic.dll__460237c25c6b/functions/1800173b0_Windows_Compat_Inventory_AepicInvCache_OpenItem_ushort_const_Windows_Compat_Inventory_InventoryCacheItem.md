# Windows::Compat::Inventory::AepicInvCache::OpenItem(ushort const *,Windows::Compat::Inventory::InventoryCacheItem * &)

- ea: `0x1800173b0`
- end: `0x180017535`
- name: `?OpenItem@AepicInvCache@Inventory@Compat@Windows@@UEBAJPEBGAEAPEAVInventoryCacheItem@234@@Z`
- size: `389`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::AepicInvCache *__hidden this, const unsigned __int16 *, struct Windows::Compat::Inventory::InventoryCacheItem **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005d6c`
- `0x1800173b0`
- `0x180028990`
- `0x1800295dc`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180017479`
- `ntdll!RtlAllocateHeap` at `0x180017479`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001741e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001741e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017498`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017498`

## string_xrefs

- `0x180017518`: `Windows::Compat::Inventory::AepicInvCache::OpenItem`
- `0x180017507`: `InvCacheOpenItem failed [%#x]`
- `0x180017450`: `InvCacheOpenItem`
- `0x18001743f`: `RegOpenKeyEx failed [%#x]`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::AepicInvCache::OpenItem(
        Windows::Compat::Inventory::AepicInvCache *this,
        const unsigned __int16 *a2,
        HKEY *a3)
{
  __int64 v3; // r9
  __int64 v5; // rax
  HKEY v6; // rcx
  LSTATUS v7; // eax
  signed int v8; // ebx
  _QWORD *Heap; // rax
  _QWORD *v10; // rsi
  unsigned int v11; // edi
  HKEY v12; // rax
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  v3 = *((_QWORD *)this + 1);
  hKey = 0;
  if ( !v3 || *(_DWORD *)v3 != 1 || !a2 || !*a2 || (v5 = *(_QWORD *)(v3 + 8)) == 0 || (v6 = *(HKEY *)(v5 + 8)) == 0 )
  {
    v11 = -2147024809;
    v8 = -2147024809;
LABEL_25:
    AslLogCallPrintf(1, "Windows::Compat::Inventory::AepicInvCache::OpenItem", 196, "InvCacheOpenItem failed [%#x]", v8);
    return v11;
  }
  v7 = RegOpenKeyExW(v6, a2, 0, 0xF003Fu, &hKey);
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  if ( v8 >= 0 )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x10u);
    v10 = Heap;
    if ( Heap )
    {
      *(_DWORD *)Heap = 2;
      v11 = 0;
      Heap[1] = hKey;
      v12 = (HKEY)operator new(0x10u, (const struct std::nothrow_t *)std::nothrow);
      hKey = v12;
      if ( v12 )
      {
        *((_QWORD *)v12 + 1) = v10;
        *(_QWORD *)v12 = &Windows::Compat::Inventory::AepicInvCacheItem::`vftable';
        *a3 = v12;
      }
      else
      {
        v11 = -2147024882;
        if ( v10 )
          InvCacheCloseHandle(0);
      }
      return v11;
    }
    v8 = -2147024882;
  }
  else if ( v8 != -2147024894 )
  {
    AslLogCallPrintf(1, "InvCacheOpenItem", 177, "RegOpenKeyEx failed [%#x]", v8);
  }
  if ( hKey )
    RegCloseKey(hKey);
  v11 = v8;
  if ( v8 != -2147024894 )
    goto LABEL_25;
  return v11;
}

```

## disassembly

```asm
0x1800173b0  push    rbx
0x1800173b2  push    rsi
0x1800173b3  push    rdi
0x1800173b4  push    r14
0x1800173b6  sub     rsp, 38h
0x1800173ba  mov     r9, [rcx+8]
0x1800173be  mov     r14, r8
0x1800173c1  mov     [rsp+58h+hKey], 0
0x1800173ca  test    r9, r9
0x1800173cd  jz      loc_180017500
0x1800173d3  cmp     dword ptr [r9], 1
0x1800173d7  jnz     loc_180017500
0x1800173dd  test    rdx, rdx
0x1800173e0  jz      loc_180017500
0x1800173e6  xor     eax, eax
0x1800173e8  cmp     ax, [rdx]
0x1800173eb  jz      loc_180017500
0x1800173f1  mov     rax, [r9+8]
0x1800173f5  test    rax, rax
0x1800173f8  jz      loc_180017500
0x1800173fe  mov     rcx, [rax+8]; hKey
0x180017402  test    rcx, rcx
0x180017405  jz      loc_180017500
0x18001740b  lea     rax, [rsp+58h+hKey]
0x180017410  mov     r9d, 0F003Fh; samDesired
0x180017416  xor     r8d, r8d; ulOptions
0x180017419  mov     [rsp+58h+phkResult], rax; phkResult
0x18001741e  call    cs:__imp_RegOpenKeyExW
0x180017424  mov     ebx, eax
0x180017426  test    eax, eax
0x180017428  jle     short loc_180017433
0x18001742a  movzx   ebx, ax
0x18001742d  or      ebx, 80070000h
0x180017433  test    ebx, ebx
0x180017435  jns     short loc_180017463
0x180017437  cmp     ebx, 80070002h
0x18001743d  jz      short loc_18001748C
0x18001743f  lea     r9, aRegopenkeyexFa_0; "RegOpenKeyEx failed [%#x]"
0x180017446  mov     dword ptr [rsp+58h+phkResult], ebx
0x18001744a  mov     r8d, 0B1h
0x180017450  lea     rdx, aInvcacheopenit_0; "InvCacheOpenItem"
0x180017457  mov     ecx, 1
0x18001745c  call    AslLogCallPrintf
0x180017461  jmp     short loc_18001748C
0x180017463  mov     rcx, gs:60h
0x18001746c  mov     edx, 8; Flags
0x180017471  mov     rcx, [rcx+30h]; HeapHandle
0x180017475  lea     r8d, [rdx+8]; Size
0x180017479  call    cs:__imp_RtlAllocateHeap
0x18001747f  mov     rsi, rax
0x180017482  test    rax, rax
0x180017485  jnz     short loc_1800174AE
0x180017487  mov     ebx, 8007000Eh
0x18001748c  mov     rcx, [rsp+58h+hKey]; hKey
0x180017491  xor     esi, esi
0x180017493  test    rcx, rcx
0x180017496  jz      short loc_18001749E
0x180017498  call    cs:__imp_RegCloseKey
0x18001749e  mov     edi, ebx
0x1800174a0  test    ebx, ebx
0x1800174a2  jns     short loc_1800174BF
0x1800174a4  cmp     ebx, 80070002h
0x1800174aa  jz      short loc_180017529
0x1800174ac  jmp     short loc_180017507
0x1800174ae  mov     dword ptr [rax], 2
0x1800174b4  xor     edi, edi
0x1800174b6  mov     rax, [rsp+58h+hKey]
0x1800174bb  mov     [rsi+8], rax
0x1800174bf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800174c6  mov     ecx, 10h; unsigned __int64
0x1800174cb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800174d0  mov     [rsp+58h+hKey], rax
0x1800174d5  test    rax, rax
0x1800174d8  jz      short loc_1800174ED
0x1800174da  lea     rcx, ??_7AepicInvCacheItem@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::AepicInvCacheItem::`vftable'
0x1800174e1  mov     [rax+8], rsi
0x1800174e5  mov     [rax], rcx
0x1800174e8  mov     [r14], rax
0x1800174eb  jmp     short loc_180017529
0x1800174ed  mov     edi, 8007000Eh
0x1800174f2  test    rsi, rsi
0x1800174f5  jz      short loc_180017529
0x1800174f7  xor     ecx, ecx; P
0x1800174f9  call    InvCacheCloseHandle
0x1800174fe  jmp     short loc_180017529
0x180017500  mov     edi, 80070057h
0x180017505  mov     ebx, edi
0x180017507  lea     r9, aInvcacheopenit; "InvCacheOpenItem failed [%#x]"
0x18001750e  mov     dword ptr [rsp+58h+phkResult], ebx
0x180017512  mov     r8d, 0C4h
0x180017518  lea     rdx, aWindowsCompatI_9; "Windows::Compat::Inventory::AepicInvCac"...
0x18001751f  mov     ecx, 1
0x180017524  call    AslLogCallPrintf
0x180017529  mov     eax, edi
0x18001752b  add     rsp, 38h
0x18001752f  pop     r14
0x180017531  pop     rdi
0x180017532  pop     rsi
0x180017533  pop     rbx
0x180017534  retn
```
