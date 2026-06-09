# std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](ushort const * const &)

- ea: `0x18000d560`
- end: `0x18000d5ff`
- name: `??A?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@AEBQEBG@Z`
- size: `159`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800093c0`
- `0x180009704`

## callees

- `0x18000d560`
- `0x18000e058`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000d58c`
- `msvcrt!_wcsicmp` at `0x18000d5b5`
- `msvcrt!_wcsicmp` at `0x18000d58c`
- `msvcrt!_wcsicmp` at `0x18000d5b5`

## pseudocode

```c
__int64 __fastcall std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>::operator[](
        __int64 a1,
        const wchar_t **a2)
{
  __int64 v2; // rbx
  __int64 v5; // rdi
  const wchar_t *v6; // rax
  const wchar_t *v8[3]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v9; // [rsp+40h] [rbp+8h] BYREF

  v2 = *(_QWORD *)(a1 + 8);
  v5 = *(_QWORD *)(v2 + 8);
  while ( !*(_BYTE *)(v5 + 41) )
  {
    if ( _wcsicmp(*(const wchar_t **)(v5 + 24), *a2) >= 0 )
    {
      v2 = v5;
      v5 = *(_QWORD *)v5;
    }
    else
    {
      v5 = *(_QWORD *)(v5 + 16);
    }
  }
  if ( v2 == *(_QWORD *)(a1 + 8) || _wcsicmp(*a2, *(const wchar_t **)(v2 + 24)) < 0 )
  {
    v6 = *a2;
    v8[1] = 0;
    v8[0] = v6;
    v2 = *std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::insert(
            a1,
            &v9,
            (__int64 *)v2,
            v8);
  }
  return v2 + 32;
}

```

## disassembly

```asm
0x18000d560  mov     [rsp+arg_8], rbx
0x18000d565  mov     [rsp+arg_10], rsi
0x18000d56a  mov     [rsp+arg_18], rdi
0x18000d56f  push    r14
0x18000d571  sub     rsp, 30h
0x18000d575  mov     rbx, [rcx+8]
0x18000d579  mov     r14, rdx
0x18000d57c  mov     rsi, rcx
0x18000d57f  mov     rdi, [rbx+8]
0x18000d583  jmp     short loc_18000D5A2
0x18000d585  mov     rdx, [r14]; String2
0x18000d588  mov     rcx, [rdi+18h]; String1
0x18000d58c  call    cs:__imp__wcsicmp
0x18000d592  test    eax, eax
0x18000d594  jns     short loc_18000D59C
0x18000d596  mov     rdi, [rdi+10h]
0x18000d59a  jmp     short loc_18000D5A2
0x18000d59c  mov     rbx, rdi
0x18000d59f  mov     rdi, [rdi]
0x18000d5a2  cmp     byte ptr [rdi+29h], 0
0x18000d5a6  jz      short loc_18000D585
0x18000d5a8  cmp     rbx, [rsi+8]
0x18000d5ac  jz      short loc_18000D5BF
0x18000d5ae  mov     rdx, [rbx+18h]; String2
0x18000d5b2  mov     rcx, [r14]; String1
0x18000d5b5  call    cs:__imp__wcsicmp
0x18000d5bb  test    eax, eax
0x18000d5bd  jns     short loc_18000D5E5
0x18000d5bf  mov     rax, [r14]
0x18000d5c2  lea     r9, [rsp+38h+var_18]
0x18000d5c7  and     [rsp+38h+var_10], 0
0x18000d5cd  lea     rdx, [rsp+38h+arg_0]
0x18000d5d2  mov     r8, rbx
0x18000d5d5  mov     [rsp+38h+var_18], rax
0x18000d5da  mov     rcx, rsi
0x18000d5dd  call    ?insert@?$_Tree@V?$_Tmap_traits@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAA?AViterator@12@V312@AEBU?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@2@@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::insert(std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>,0>>::iterator,std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *> const &)
0x18000d5e2  mov     rbx, [rax]
0x18000d5e5  mov     rsi, [rsp+38h+arg_10]
0x18000d5ea  lea     rax, [rbx+20h]
0x18000d5ee  mov     rbx, [rsp+38h+arg_8]
0x18000d5f3  mov     rdi, [rsp+38h+arg_18]
0x18000d5f8  add     rsp, 30h
0x18000d5fc  pop     r14
0x18000d5fe  retn
```
