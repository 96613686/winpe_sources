# AccessListReadCache::_InsertCacheEntry(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<WindowsStorage::Utilities::NtObjectPath const,AccessListReadCache::CacheItem>>>> const &,ushort const *)

- ea: `0x1800102cc`
- end: `0x1800103d6`
- name: `?_InsertCacheEntry@AccessListReadCache@@AEAAXAEBV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVNtObjectPath@Utilities@WindowsStorage@@UCacheItem@AccessListReadCache@@@std@@@std@@@std@@@std@@PEBG@Z`
- size: `266`
- prototype: `HRESULT __fastcall(__int64, __int64 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f680`

## callees

- `0x18000af58`
- `0x18000d3b0`
- `0x18000e01c`
- `0x18000e20c`
- `0x18000e2fc`
- `0x1800102cc`
- `0x180010d40`
- `0x180021d6c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010342`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010342`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800103cf`

## pseudocode

```c
HRESULT __fastcall AccessListReadCache::_InsertCacheEntry(__int64 a1, __int64 *a2, const unsigned __int16 *a3)
{
  HSTRING *v6; // rax
  HSTRING v7; // rbx
  _QWORD *v8; // rdi
  __int64 v9; // r9
  __int64 v10; // rcx
  __int128 v12; // [rsp+20h] [rbp-39h] BYREF
  _BYTE v13[16]; // [rsp+30h] [rbp-29h] BYREF
  HSTRING v14; // [rsp+40h] [rbp-19h] BYREF
  HSTRING v15; // [rsp+48h] [rbp-11h]
  __int64 v16; // [rsp+50h] [rbp-9h]
  _BYTE v17[8]; // [rsp+58h] [rbp-1h] BYREF
  __int64 v18; // [rsp+60h] [rbp+7h]
  char v19; // [rsp+68h] [rbp+Fh]
  HSTRING v20[3]; // [rsp+70h] [rbp+17h] BYREF
  int v21; // [rsp+88h] [rbp+2Fh]
  HSTRING string; // [rsp+D8h] [rbp+7Fh] BYREF

  v14 = 0;
  v15 = 0;
  v16 = 0;
  if ( AccessListReadCache::CacheItem::Initialize((AccessListReadCache::CacheItem *)&v14, a3) < 0 )
  {
    v7 = v14;
  }
  else
  {
    v6 = (HSTRING *)WindowsStorage::Utilities::NtObjectPath::FromRegistry(&string, a3);
    v20[0] = *v6;
    *v6 = 0;
    v20[1] = v14;
    v7 = 0;
    v14 = 0;
    v20[2] = v15;
    v21 = v16;
    WindowsDeleteString(string);
    string = 0;
    v8 = (_QWORD *)(std::_Tree<std::_Tmap_traits<WindowsStorage::Utilities::NtObjectPath,AccessListReadCache::CacheItem,std::less<WindowsStorage::Utilities::NtObjectPath>,std::allocator<std::pair<WindowsStorage::Utilities::NtObjectPath const,AccessListReadCache::CacheItem>>,0>>::_Emplace_hint<std::pair<WindowsStorage::Utilities::NtObjectPath,AccessListReadCache::CacheItem>>(
                      (__int64 *)(a1 + 32),
                      *a2,
                      (__int64)v20)
                  + 40);
    v12 = *(_OWORD *)WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>::make_string_view(
                       v13,
                       *v8);
    LOBYTE(v9) = 1;
    ((void (__fastcall *)(__int64, _BYTE *, __int128 *, __int64))WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>::FindChildNode)(
      a1 + 48,
      v17,
      &v12,
      v9);
    if ( !v19 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v10 = v18;
    *(_QWORD *)(v18 + 40) = v8;
    *(_BYTE *)(v10 + 48) = 1;
    *(_DWORD *)(v10 + 49) = *(_DWORD *)((char *)&v12 + 9);
    *(_WORD *)(v10 + 53) = *(_WORD *)((char *)&v12 + 13);
    *(_BYTE *)(v10 + 55) = HIBYTE(v12);
    std::pair<WindowsStorage::Utilities::NtObjectPath,AccessListReadCache::CacheItem>::~pair<WindowsStorage::Utilities::NtObjectPath,AccessListReadCache::CacheItem>(v20);
  }
  return WindowsDeleteString(v7);
}

```

## disassembly

```asm
0x1800102cc  push    rbp
0x1800102ce  push    rbx
0x1800102cf  push    rsi
0x1800102d0  push    rdi
0x1800102d1  lea     rbp, [rsp-3Fh]
0x1800102d6  sub     rsp, 98h
0x1800102dd  mov     rbx, r8
0x1800102e0  mov     rdi, rdx
0x1800102e3  mov     rsi, rcx
0x1800102e6  xor     eax, eax
0x1800102e8  mov     [rbp+57h+var_70], rax
0x1800102ec  mov     [rbp+57h+var_68], rax
0x1800102f0  mov     [rbp+57h+var_60], rax
0x1800102f4  mov     rdx, r8; unsigned __int16 *
0x1800102f7  lea     rcx, [rbp+57h+var_70]; this
0x1800102fb  call    ?Initialize@CacheItem@AccessListReadCache@@QEAAJPEBG@Z; AccessListReadCache::CacheItem::Initialize(ushort const *)
0x180010300  test    eax, eax
0x180010302  js      loc_1800103BD
0x180010308  mov     rdx, rbx
0x18001030b  lea     rcx, [rbp+57h+string]
0x18001030f  call    ?FromRegistry@NtObjectPath@Utilities@WindowsStorage@@SA?AV123@PEBG@Z; WindowsStorage::Utilities::NtObjectPath::FromRegistry(ushort const *)
0x180010314  mov     rcx, [rax]
0x180010317  mov     [rbp+57h+var_40], rcx
0x18001031b  mov     qword ptr [rax], 0
0x180010322  mov     rax, [rbp+57h+var_70]
0x180010326  mov     [rbp+57h+var_38], rax
0x18001032a  xor     ebx, ebx
0x18001032c  mov     [rbp+57h+var_70], rbx
0x180010330  mov     rax, [rbp+57h+var_68]
0x180010334  mov     [rbp+57h+var_30], rax
0x180010338  mov     eax, dword ptr [rbp+57h+var_60]
0x18001033b  mov     [rbp+57h+var_28], eax
0x18001033e  mov     rcx, [rbp+57h+string]; string
0x180010342  call    cs:__imp_WindowsDeleteString
0x180010348  mov     [rbp+57h+string], rbx
0x18001034c  lea     rcx, [rsi+20h]
0x180010350  lea     r8, [rbp+57h+var_40]
0x180010354  mov     rdx, [rdi]
0x180010357  call    ??$_Emplace_hint@U?$pair@VNtObjectPath@Utilities@WindowsStorage@@UCacheItem@AccessListReadCache@@@std@@@?$_Tree@V?$_Tmap_traits@VNtObjectPath@Utilities@WindowsStorage@@UCacheItem@AccessListReadCache@@U?$less@VNtObjectPath@Utilities@WindowsStorage@@@std@@V?$allocator@U?$pair@$$CBVNtObjectPath@Utilities@WindowsStorage@@UCacheItem@AccessListReadCache@@@std@@@7@$0A@@std@@@std@@IEAAPEAU?$_Tree_node@U?$pair@$$CBVNtObjectPath@Utilities@WindowsStorage@@UCacheItem@AccessListReadCache@@@std@@PEAX@1@QEAU21@$$QEAU?$pair@VNtObjectPath@Utilities@WindowsStorage@@UCacheItem@AccessListReadCache@@@1@@Z; std::_Tree<std::_Tmap_traits<WindowsStorage::Utilities::NtObjectPath,AccessListReadCache::CacheItem,std::less<WindowsStorage::Utilities::NtObjectPath>,std::allocator<std::pair<WindowsStorage::Utilities::NtObjectPath const,AccessListReadCache::CacheItem>>,0>>::_Emplace_hint<std::pair<WindowsStorage::Utilities::NtObjectPath,AccessListReadCache::CacheItem>>(std::_Tree_node<std::pair<WindowsStorage::Utilities::NtObjectPath const,AccessListReadCache::CacheItem>,void *> * const,std::pair<WindowsStorage::Utilities::NtObjectPath,AccessListReadCache::CacheItem> &&)
0x18001035c  lea     rdi, [rax+28h]
0x180010360  mov     rdx, [rdi]
0x180010363  lea     rcx, [rbp+57h+var_80]
0x180010367  call    ?make_string_view@?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@CA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@PEAUHSTRING__@@@Z; WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>::make_string_view(HSTRING__ *)
0x18001036c  movups  xmm0, xmmword ptr [rax]
0x18001036f  movdqu  [rbp+57h+var_90], xmm0
0x180010374  lea     rcx, [rsi+30h]
0x180010378  mov     r9b, 1
0x18001037b  lea     r8, [rbp+57h+var_90]
0x18001037f  lea     rdx, [rbp+57h+var_58]
0x180010383  call    ?FindChildNode@?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@AEBA?AV?$tuple@_NV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@std@@@std@@@std@@@std@@V12@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@5@_N@Z; WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>::FindChildNode(std::basic_string_view<ushort>,bool)
0x180010388  cmp     [rbp+57h+var_48], bl
0x18001038b  jnz     short loc_180010392
0x18001038d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180010392  mov     rcx, [rbp+57h+var_50]
0x180010396  mov     [rcx+28h], rdi
0x18001039a  mov     byte ptr [rcx+30h], 1
0x18001039e  mov     eax, dword ptr [rbp+57h+var_90+9]
0x1800103a1  mov     [rcx+31h], eax
0x1800103a4  movzx   eax, word ptr [rbp+57h+var_90+0Dh]
0x1800103a8  mov     [rcx+35h], ax
0x1800103ac  mov     al, byte ptr [rbp+57h+var_90+0Fh]
0x1800103af  mov     [rcx+37h], al
0x1800103b2  lea     rcx, [rbp+57h+var_40]
0x1800103b6  call    ??1?$pair@VNtObjectPath@Utilities@WindowsStorage@@UCacheItem@AccessListReadCache@@@std@@QEAA@XZ; std::pair<WindowsStorage::Utilities::NtObjectPath,AccessListReadCache::CacheItem>::~pair<WindowsStorage::Utilities::NtObjectPath,AccessListReadCache::CacheItem>(void)
0x1800103bb  jmp     short loc_1800103C1
0x1800103bd  mov     rbx, [rbp+57h+var_70]
0x1800103c1  mov     rcx, rbx
0x1800103c4  add     rsp, 98h
0x1800103cb  pop     rdi
0x1800103cc  pop     rsi
0x1800103cd  pop     rbx
0x1800103ce  pop     rbp
0x1800103cf  jmp     cs:__imp_WindowsDeleteString
```
