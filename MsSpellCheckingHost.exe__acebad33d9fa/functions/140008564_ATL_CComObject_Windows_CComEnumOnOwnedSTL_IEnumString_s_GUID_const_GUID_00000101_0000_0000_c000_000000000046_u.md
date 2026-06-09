# ATL::CComObject<Windows::CComEnumOnOwnedSTL<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,ushort *,Windows::CopyFromPairWstringToLpolestr,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,ATL::CComMultiThreadModel>>::~CComObject<Windows::CComEnumOnOwnedSTL<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,ushort *,Windows::CopyFromPairWstringToLpolestr,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,ATL::CComMultiThreadModel>>(void)

- ea: `0x140008564`
- end: `0x1400085e7`
- name: `??1?$CComObject@V?$CComEnumOnOwnedSTL@UIEnumString@@$1?_GUID_00000101_0000_0000_c000_000000000046@@3U__s_GUID@@BPEAGVCopyFromPairWstringToLpolestr@Windows@@V?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@VCComMultiThreadModel@ATL@@@Windows@@@ATL@@UEAA@XZ`
- size: `131`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140008fb0`

## callees

- `0x140008564`
- `0x14000ec30`
- `0x140013010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400085da`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400085da`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000859f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000859f`

## pseudocode

```c
void __fastcall ATL::CComObject<Windows::CComEnumOnOwnedSTL<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,unsigned short *,Windows::CopyFromPairWstringToLpolestr,std::map<std::wstring const,std::wstring>,ATL::CComMultiThreadModel>>::~CComObject<Windows::CComEnumOnOwnedSTL<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,unsigned short *,Windows::CopyFromPairWstringToLpolestr,std::map<std::wstring const,std::wstring>,ATL::CComMultiThreadModel>>(
        __int64 a1)
{
  *(_QWORD *)a1 = &ATL::CComObject<Windows::CComEnumOnOwnedSTL<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,unsigned short *,Windows::CopyFromPairWstringToLpolestr,std::map<std::wstring const,std::wstring>,ATL::CComMultiThreadModel>>::`vftable';
  *(_DWORD *)(a1 + 32) = -1073741823;
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( *(_BYTE *)(a1 + 80) )
  {
    *(_BYTE *)(a1 + 80) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
  }
  std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Erase(
    a1 + 8,
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL));
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) = *(_QWORD *)(a1 + 8);
  **(_QWORD **)(a1 + 8) = *(_QWORD *)(a1 + 8);
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL) = *(_QWORD *)(a1 + 8);
  *(_QWORD *)(a1 + 16) = 0;
  operator delete(*(void **)(a1 + 8));
}

```

## disassembly

```asm
0x140008564  push    rbx
0x140008566  sub     rsp, 20h
0x14000856a  mov     rbx, rcx
0x14000856d  lea     rax, ??_7?$CComObject@V?$CComEnumOnOwnedSTL@UIEnumString@@$1?_GUID_00000101_0000_0000_c000_000000000046@@3U__s_GUID@@BPEAGVCopyFromPairWstringToLpolestr@Windows@@V?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@VCComMultiThreadModel@ATL@@@Windows@@@ATL@@6B@; const ATL::CComObject<Windows::CComEnumOnOwnedSTL<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,ushort *,Windows::CopyFromPairWstringToLpolestr,std::map<std::wstring const,std::wstring>,ATL::CComMultiThreadModel>>::`vftable'
0x140008574  mov     [rcx], rax
0x140008577  mov     dword ptr [rcx+20h], 0C0000001h
0x14000857e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140008585  mov     rax, [rcx]
0x140008588  mov     rax, [rax+10h]
0x14000858c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008591  lea     rcx, [rbx+28h]; lpCriticalSection
0x140008595  cmp     byte ptr [rcx+28h], 0
0x140008599  jz      short loc_1400085A6
0x14000859b  mov     byte ptr [rcx+28h], 0
0x14000859f  call    cs:__imp_DeleteCriticalSection
0x1400085a5  nop
0x1400085a6  mov     rdx, [rbx+8]
0x1400085aa  mov     rdx, [rdx+8]
0x1400085ae  lea     rcx, [rbx+8]
0x1400085b2  call    ?_Erase@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Erase(std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x1400085b7  mov     rax, [rbx+8]
0x1400085bb  mov     [rax+8], rax
0x1400085bf  mov     rax, [rbx+8]
0x1400085c3  mov     [rax], rax
0x1400085c6  mov     rax, [rbx+8]
0x1400085ca  mov     [rax+10h], rax
0x1400085ce  mov     qword ptr [rbx+10h], 0
0x1400085d6  mov     rcx, [rbx+8]
0x1400085da  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400085e0  nop
0x1400085e1  add     rsp, 20h
0x1400085e5  pop     rbx
0x1400085e6  retn
```
