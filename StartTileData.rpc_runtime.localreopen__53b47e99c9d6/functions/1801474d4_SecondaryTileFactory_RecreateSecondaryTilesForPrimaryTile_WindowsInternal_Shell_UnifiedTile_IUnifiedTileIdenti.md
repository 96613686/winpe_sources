# SecondaryTileFactory::RecreateSecondaryTilesForPrimaryTile(WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::shared_ptr<DataStoreCache::PlaceholderTileTransformer::PlaceholderTile>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::shared_ptr<DataStoreCache::PlaceholderTileTransformer::PlaceholderTile>>>> *)

- ea: `0x1801474d4`
- end: `0x1801478fe`
- name: `?RecreateSecondaryTilesForPrimaryTile@SecondaryTileFactory@@QEAAJPEAUIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@PEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VPlaceholderTile@PlaceholderTileTransformer@DataStoreCache@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VPlaceholderTile@PlaceholderTileTransformer@DataStoreCache@@@2@@std@@@2@@std@@@Z`
- size: `1066`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800104ec`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x18001dac0`
- `0x18002dde0`
- `0x180040d88`
- `0x18004fd50`
- `0x1801014cc`
- `0x1801014fc`
- `0x18011cf80`
- `0x180128bd4`
- `0x1801474d4`
- `0x180147be8`
- `0x18015e870`
- `0x180161204`
- `0x180369b2c`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180147737`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180147737`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014766d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801476be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014775c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801477dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801477e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801477f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014766d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801476be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18014775c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801477dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801477e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801477f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180147701`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014771e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180147701`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18014771e`

## string_xrefs

- `0x18014755f`: `shellcommon\shell\datastorecache\transformers\placeholdertiletransformer\lib\secondarytilefactory.cpp`
- `0x180147699`: `shellcommon\shell\datastorecache\transformers\placeholdertiletransformer\lib\secondarytilefactory.cpp`
- `0x180147786`: `shellcommon\shell\datastorecache\transformers\placeholdertiletransformer\lib\secondarytilefactory.cpp`
- `0x1801477c5`: `shellcommon\shell\datastorecache\transformers\placeholdertiletransformer\lib\secondarytilefactory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall SecondaryTileFactory::RecreateSecondaryTilesForPrimaryTile(
        SecondaryTileFactory *a1,
        struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *a2,
        __int128 *a3)
{
  int v6; // r12d
  int (**v7)(void); // rax
  int (*v8)(void); // rax
  const char *v9; // r9
  int v10; // eax
  unsigned int v11; // ebx
  __int64 result; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 *v15; // rbx
  __int64 v16; // rsi
  __int64 (__fastcall *v17)(__int64, HSTRING *); // rdi
  int v18; // eax
  wil::details::in1diag3 *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rsi
  __int64 (__fastcall *v22)(__int64, HSTRING *); // rdi
  UINT32 v23; // r14d
  const WCHAR *StringRawBuffer; // rdi
  UINT32 v25; // esi
  const WCHAR *v26; // rax
  __int64 v27; // rsi
  __int64 (__fastcall *v28)(__int64, HSTRING *); // rdi
  int v29; // eax
  int v30; // eax
  __int64 **v31; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  int bIgnoreCase; // [rsp+20h] [rbp-88h]
  HSTRING string; // [rsp+30h] [rbp-78h] BYREF
  __int64 v36; // [rsp+38h] [rbp-70h] BYREF
  __int64 v37; // [rsp+40h] [rbp-68h] BYREF
  __int64 v38; // [rsp+48h] [rbp-60h] BYREF
  HSTRING v39; // [rsp+50h] [rbp-58h] BYREF
  HSTRING v40; // [rsp+58h] [rbp-50h] BYREF
  __int128 v41; // [rsp+60h] [rbp-48h] BYREF
  _QWORD v42[7]; // [rsp+70h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  UINT32 length; // [rsp+B8h] [rbp+10h] BYREF
  UINT32 v46; // [rsp+C8h] [rbp+20h] BYREF

  v6 = 0;
  length = 0;
  v7 = *(int (***)(void))a2;
  v38 = 0;
  v8 = *v7;
  try
  {
    if ( v8() >= 0 && WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::IsPrimaryTile(v38) )
    {
      v36 = 0;
      v10 = Microsoft::WRL::WeakRef::As<DataStoreCache::PlaceholderTileTransformer::IPlaceholderTileTransformer>(
              a1,
              &v36);
      v11 = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x31,
          (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\placeholdertiletransformer\\lib\\secondarytilefactory.cpp",
          (const char *)(unsigned int)v10,
          bIgnoreCase);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
        wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v38);
        return v11;
      }
      v13 = v36;
      if ( v36 )
      {
        v41 = 0;
        std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<DataStoreCache::PlaceholderTileTransformer::PlaceholderTile>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<DataStoreCache::PlaceholderTileTransformer::PlaceholderTile>>>,0>>::_Alloc_sentinel_and_proxy(&v41);
        if ( !a3 )
        {
          v14 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v36 + 168LL))(v36, v42);
          std::map<std::wstring,std::shared_ptr<DataStoreCache::PlaceholderTileTransformer::PlaceholderTile>>::operator=(
            &v41,
            v14);
          std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<DataStoreCache::PlaceholderTileTransformer::PlaceholderTile>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<DataStoreCache::PlaceholderTileTransformer::PlaceholderTile>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<DataStoreCache::PlaceholderTileTransformer::PlaceholderTile>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<DataStoreCache::PlaceholderTileTransformer::PlaceholderTile>>>,0>>(v42);
          a3 = &v41;
        }
        v15 = **(__int64 ***)a3;
        while ( 1 )
        {
          if ( *((_BYTE *)v15 + 25) )
          {
            std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<DataStoreCache::PlaceholderTileTransformer::PlaceholderTile>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<DataStoreCache::PlaceholderTileTransformer::PlaceholderTile>>,void *>>>(
              &v41,
              &v41,
              *(_QWORD *)(v41 + 8));
            std::_Deallocate<16>(v41, 80);
            v13 = v36;
            goto LABEL_39;
          }
          DataStoreCache::PlaceholderTileTransformer::PlaceholderTileImpl::GetTileIdentifier(*(_QWORD *)v15[8], v42);
          v37 = 0;
          if ( (**(int (__fastcall ***)(_QWORD, GUID *, __int64 *))v42[0])(
                 v42[0],
                 &GUID_a7668288_cc23_4b67_be8b_6c10455986b8,
                 &v37) >= 0
            && !WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::IsPrimaryTile(v37) )
          {
            break;
          }
LABEL_25:
          v6 |= 1u;
          if ( v37 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
          if ( v42[0] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v42[0] + 16LL))(v42[0]);
          v31 = (__int64 **)v15[2];
          if ( *((_BYTE *)v31 + 25) )
          {
            for ( i = (__int64 *)v15[1]; !*((_BYTE *)i + 25) && v15 == (__int64 *)i[2]; i = (__int64 *)i[1] )
              v15 = i;
            v15 = i;
          }
          else
          {
            v15 = (__int64 *)v15[2];
            for ( j = *v31; !*((_BYTE *)j + 25); j = (__int64 *)*j )
              v15 = j;
          }
        }
        v40 = 0;
        string = 0;
        v46 = 0;
        length = 0;
        v16 = v38;
        v17 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v38 + 48LL);
        WindowsDeleteString(0);
        v40 = 0;
        v18 = v17(v16, &v40);
        v19 = retaddr;
        if ( v18 >= 0 )
        {
          v21 = v37;
          v22 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v37 + 48LL);
          WindowsDeleteString(string);
          string = 0;
          v18 = v22(v21, &string);
          v19 = retaddr;
          if ( v18 >= 0 )
          {
            v23 = length;
            StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
            v25 = v46;
            v26 = WindowsGetStringRawBuffer(v40, &v46);
            if ( CompareStringOrdinal(v26, v25, StringRawBuffer, v23, 1) == 2 )
            {
              v39 = 0;
              v27 = v37;
              v28 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v37 + 56LL);
              WindowsDeleteString(0);
              v39 = 0;
              v29 = v28(v27, &v39);
              if ( v29 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x55,
                  (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\placeholdertiletransformer\\lib\\secon"
                                "darytilefactory.cpp",
                  (const char *)(unsigned int)v29,
                  bIgnoreCase);
              v30 = SecondaryTileFactory::RecreateSecondaryTile(
                      a1,
                      (struct DataStoreCache::PlaceholderTileTransformer::PlaceholderTile *)v15[8],
                      string,
                      v39,
                      a2);
              if ( v30 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x57,
                  (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\placeholdertiletransformer\\lib\\secon"
                                "darytilefactory.cpp",
                  (const char *)(unsigned int)v30,
                  bIgnoreCase);
              WindowsDeleteString(v39);
            }
            goto LABEL_24;
          }
          v20 = 80;
        }
        else
        {
          v20 = 79;
        }
        wil::details::in1diag3::_Log_Hr(
          v19,
          (void *)v20,
          (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\placeholdertiletransformer\\lib\\secondarytilefactory.cpp",
          (const char *)(unsigned int)v18,
          bIgnoreCase);
LABEL_24:
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v40);
        goto LABEL_25;
      }
LABEL_39:
      if ( v13 )
      {
        v36 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
    }
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x5E,
                           (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\placeholdertiletransformer\\l"
                                         "ib\\secondarytilefactory.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x1801474d4  mov     r11, rsp
0x1801474d7  mov     [r11+18h], rbx
0x1801474db  mov     [r11+8], rcx
0x1801474df  push    rsi
0x1801474e0  push    rdi
0x1801474e1  push    r12
0x1801474e3  push    r13
0x1801474e5  push    r14
0x1801474e7  sub     rsp, 80h
0x1801474ee  mov     rdi, r8
0x1801474f1  mov     r13, rdx
0x1801474f4  mov     rbx, rcx
0x1801474f7  xor     r14d, r14d
0x1801474fa  mov     r12d, r14d
0x1801474fd  mov     [rsp+0A8h+length], r14d
0x180147505  mov     rax, [rdx]
0x180147508  mov     [r11-60h], r14
0x18014750c  lea     r8, [r11-60h]
0x180147510  lea     rdx, _GUID_a7668288_cc23_4b67_be8b_6c10455986b8
0x180147517  mov     rcx, r13
0x18014751a  mov     rax, [rax]
0x18014751d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180147522  test    eax, eax
0x180147524  js      loc_1801478C3
0x18014752a  mov     rcx, [rsp+0A8h+var_60]
0x18014752f  call    WindowsInternal__Shell__UnifiedTile__CuratedTileCollections__IsPrimaryTile
0x180147534  test    al, al
0x180147536  jz      loc_1801478C3
0x18014753c  mov     [rsp+0A8h+var_70], r14
0x180147541  lea     rdx, [rsp+0A8h+var_70]
0x180147546  mov     rcx, rbx
0x180147549  call    ??$As@UIPlaceholderTileTransformer@PlaceholderTileTransformer@DataStoreCache@@@WeakRef@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPlaceholderTileTransformer@PlaceholderTileTransformer@DataStoreCache@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::WeakRef::As<DataStoreCache::PlaceholderTileTransformer::IPlaceholderTileTransformer>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<DataStoreCache::PlaceholderTileTransformer::IPlaceholderTileTransformer>>)
0x18014754e  mov     ebx, eax
0x180147550  test    eax, eax
0x180147552  jns     short loc_18014758C
0x180147554  mov     rcx, [rsp+0A8h]; this
0x18014755c  mov     r9d, eax; char *
0x18014755f  lea     r8, aShellcommonShe_110; "shellcommon\\shell\\datastorecache\\tra"...
0x180147566  lea     edx, [r14+31h]; void *
0x18014756a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014756f  nop
0x180147570  lea     rcx, [rsp+0A8h+var_70]
0x180147575  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18014757a  nop
0x18014757b  lea     rcx, [rsp+0A8h+var_60]; void *
0x180147580  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180147585  mov     eax, ebx
0x180147587  jmp     loc_1801478E5
0x18014758c  mov     rcx, [rsp+0A8h+var_70]
0x180147591  test    rcx, rcx
0x180147594  jz      loc_1801478AC
0x18014759a  xorps   xmm0, xmm0
0x18014759d  movdqu  [rsp+0A8h+var_48], xmm0
0x1801475a3  lea     rcx, [rsp+0A8h+var_48]
0x1801475a8  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VPlaceholderTile@PlaceholderTileTransformer@DataStoreCache@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VPlaceholderTile@PlaceholderTileTransformer@DataStoreCache@@@2@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<DataStoreCache::PlaceholderTileTransformer::PlaceholderTile>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<DataStoreCache::PlaceholderTileTransformer::PlaceholderTile>>>,0>>::_Alloc_sentinel_and_proxy(void)
0x1801475ad  nop
0x1801475ae  test    rdi, rdi
0x1801475b1  jnz     short loc_1801475E8
0x1801475b3  mov     rcx, [rsp+0A8h+var_70]
0x1801475b8  mov     rax, [rcx]
0x1801475bb  lea     rdx, [rsp+0A8h+var_38]
0x1801475c0  mov     rax, [rax+0A8h]
0x1801475c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801475cc  mov     rdx, rax
0x1801475cf  lea     rcx, [rsp+0A8h+var_48]
0x1801475d4  call    ??4?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VPlaceholderTile@PlaceholderTileTransformer@DataStoreCache@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VPlaceholderTile@PlaceholderTileTransformer@DataStoreCache@@@2@@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::map<std::wstring,std::shared_ptr<DataStoreCache::PlaceholderTileTransformer::PlaceholderTile>>::operator=(std::map<std::wstring,std::shared_ptr<DataStoreCache::PlaceholderTileTransformer::PlaceholderTile>> &&)
0x1801475d9  lea     rcx, [rsp+0A8h+var_38]
0x1801475de  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VPlaceholderTile@PlaceholderTileTransformer@DataStoreCache@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VPlaceholderTile@PlaceholderTileTransformer@DataStoreCache@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<DataStoreCache::PlaceholderTileTransformer::PlaceholderTile>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<DataStoreCache::PlaceholderTileTransformer::PlaceholderTile>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<DataStoreCache::PlaceholderTileTransformer::PlaceholderTile>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<DataStoreCache::PlaceholderTileTransformer::PlaceholderTile>>>,0>>(void)
0x1801475e3  lea     rdi, [rsp+0A8h+var_48]
0x1801475e8  mov     rbx, [rdi]
0x1801475eb  mov     rbx, [rbx]
0x1801475ee  cmp     [rbx+19h], r14b
0x1801475f2  jnz     loc_180147880
0x1801475f8  mov     rcx, [rbx+40h]
0x1801475fc  lea     rdx, [rsp+0A8h+var_38]
0x180147601  mov     rcx, [rcx]
0x180147604  call    ?GetTileIdentifier@PlaceholderTileImpl@PlaceholderTileTransformer@DataStoreCache@@QEAA?AV?$com_ptr_t@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@Uerr_exception_policy@wil@@@wil@@XZ; DataStoreCache::PlaceholderTileTransformer::PlaceholderTileImpl::GetTileIdentifier(void)
0x180147609  nop
0x18014760a  mov     [rsp+0A8h+var_68], r14
0x18014760f  mov     rcx, [rsp+0A8h+var_38]
0x180147614  mov     rax, [rcx]
0x180147617  lea     r8, [rsp+0A8h+var_68]
0x18014761c  lea     rdx, _GUID_a7668288_cc23_4b67_be8b_6c10455986b8
0x180147623  mov     rax, [rax]
0x180147626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014762b  test    eax, eax
0x18014762d  js      loc_1801477FF
0x180147633  mov     rcx, [rsp+0A8h+var_68]
0x180147638  call    WindowsInternal__Shell__UnifiedTile__CuratedTileCollections__IsPrimaryTile
0x18014763d  test    al, al
0x18014763f  jnz     loc_1801477FF
0x180147645  mov     [rsp+0A8h+var_50], r14
0x18014764a  mov     [rsp+0A8h+string], r14
0x18014764f  mov     [rsp+0A8h+arg_18], r14d
0x180147657  mov     [rsp+0A8h+length], r14d
0x18014765f  mov     rsi, [rsp+0A8h+var_60]
0x180147664  mov     rax, [rsi]
0x180147667  mov     rdi, [rax+30h]
0x18014766b  xor     ecx, ecx; string
0x18014766d  call    cs:__imp_WindowsDeleteString
0x180147673  mov     [rsp+0A8h+var_50], r14
0x180147678  lea     rdx, [rsp+0A8h+var_50]
0x18014767d  mov     rcx, rsi
0x180147680  mov     rax, rdi
0x180147683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180147688  mov     rcx, [rsp+0A8h]; this
0x180147690  test    eax, eax
0x180147692  jns     short loc_1801476AD
0x180147694  mov     edx, 4Fh ; 'O'; void *
0x180147699  lea     r8, aShellcommonShe_110; "shellcommon\\shell\\datastorecache\\tra"...
0x1801476a0  mov     r9d, eax; char *
0x1801476a3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1801476a8  jmp     loc_1801477E3
0x1801476ad  mov     rsi, [rsp+0A8h+var_68]
0x1801476b2  mov     rax, [rsi]
0x1801476b5  mov     rdi, [rax+30h]
0x1801476b9  mov     rcx, [rsp+0A8h+string]; string
0x1801476be  call    cs:__imp_WindowsDeleteString
0x1801476c4  mov     [rsp+0A8h+string], r14
0x1801476c9  lea     rdx, [rsp+0A8h+string]
0x1801476ce  mov     rcx, rsi
0x1801476d1  mov     rax, rdi
0x1801476d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801476d9  mov     rcx, [rsp+0A8h]
0x1801476e1  test    eax, eax
0x1801476e3  jns     short loc_1801476EC
0x1801476e5  mov     edx, 50h ; 'P'
0x1801476ea  jmp     short loc_180147699
0x1801476ec  mov     r14d, [rsp+0A8h+length]
0x1801476f4  lea     rdx, [rsp+0A8h+length]; length
0x1801476fc  mov     rcx, [rsp+0A8h+string]; string
0x180147701  call    cs:__imp_WindowsGetStringRawBuffer
0x180147707  mov     rdi, rax
0x18014770a  mov     esi, [rsp+0A8h+arg_18]
0x180147711  lea     rdx, [rsp+0A8h+arg_18]; length
0x180147719  mov     rcx, [rsp+0A8h+var_50]; string
0x18014771e  call    cs:__imp_WindowsGetStringRawBuffer
0x180147724  mov     [rsp+0A8h+bIgnoreCase], 1; int
0x18014772c  mov     r9d, r14d; cchCount2
0x18014772f  mov     r8, rdi; lpString2
0x180147732  mov     edx, esi; cchCount1
0x180147734  mov     rcx, rax; lpString1
0x180147737  call    cs:__imp_CompareStringOrdinal
0x18014773d  xor     r14d, r14d
0x180147740  cmp     eax, 2
0x180147743  jnz     loc_1801477E3
0x180147749  mov     [rsp+0A8h+var_58], r14
0x18014774e  mov     rsi, [rsp+0A8h+var_68]
0x180147753  mov     rax, [rsi]
0x180147756  mov     rdi, [rax+38h]
0x18014775a  xor     ecx, ecx; string
0x18014775c  call    cs:__imp_WindowsDeleteString
0x180147762  mov     [rsp+0A8h+var_58], r14
0x180147767  lea     rdx, [rsp+0A8h+var_58]
0x18014776c  mov     rcx, rsi
0x18014776f  mov     rax, rdi
0x180147772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180147777  mov     rcx, [rsp+0A8h]; this
0x18014777f  test    eax, eax
0x180147781  jns     short loc_180147796
0x180147783  mov     r9d, eax; char *
0x180147786  lea     r8, aShellcommonShe_110; "shellcommon\\shell\\datastorecache\\tra"...
0x18014778d  lea     edx, [r14+55h]; void *
0x180147791  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180147796  mov     qword ptr [rsp+0A8h+bIgnoreCase], r13; int
0x18014779b  mov     r9, [rsp+0A8h+var_58]; HSTRING
0x1801477a0  mov     r8, [rsp+0A8h+string]; HSTRING
0x1801477a5  mov     rdx, [rbx+40h]; struct DataStoreCache::PlaceholderTileTransformer::PlaceholderTile *
0x1801477a9  mov     rcx, [rsp+0A8h+arg_0]; this
0x1801477b1  call    ?RecreateSecondaryTile@SecondaryTileFactory@@AEAAJPEAVPlaceholderTile@PlaceholderTileTransformer@DataStoreCache@@PEAUHSTRING__@@1PEAUIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@Z; SecondaryTileFactory::RecreateSecondaryTile(DataStoreCache::PlaceholderTileTransformer::PlaceholderTile *,HSTRING__ *,HSTRING__ *,WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *)
0x1801477b6  mov     rcx, [rsp+0A8h]; this
0x1801477be  test    eax, eax
0x1801477c0  jns     short loc_1801477D7
0x1801477c2  mov     r9d, eax; char *
0x1801477c5  lea     r8, aShellcommonShe_110; "shellcommon\\shell\\datastorecache\\tra"...
0x1801477cc  mov     edx, 57h ; 'W'; void *
0x1801477d1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801477d7  mov     rcx, [rsp+0A8h+var_58]; string
0x1801477dc  call    cs:__imp_WindowsDeleteString
0x1801477e2  nop
0x1801477e3  mov     rcx, [rsp+0A8h+string]; string
0x1801477e8  call    cs:__imp_WindowsDeleteString
0x1801477ee  mov     [rsp+0A8h+string], r14
0x1801477f3  mov     rcx, [rsp+0A8h+var_50]; string
0x1801477f8  call    cs:__imp_WindowsDeleteString
0x1801477fe  nop
0x1801477ff  or      r12d, 1
0x180147803  mov     rcx, [rsp+0A8h+var_68]
0x180147808  test    rcx, rcx
0x18014780b  jz      short loc_18014781A
0x18014780d  mov     rax, [rcx]
0x180147810  mov     rax, [rax+10h]
0x180147814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180147819  nop
0x18014781a  mov     rcx, [rsp+0A8h+var_38]
0x18014781f  test    rcx, rcx
0x180147822  jz      short loc_180147831
0x180147824  mov     rax, [rcx]
0x180147827  mov     rax, [rax+10h]
0x18014782b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180147830  nop
0x180147831  mov     rcx, [rbx+10h]
0x180147835  cmp     [rcx+19h], r14b
0x180147839  jz      short loc_18014785C
0x18014783b  mov     rax, [rbx+8]
0x18014783f  jmp     short loc_18014784E
0x180147841  cmp     rbx, [rax+10h]
0x180147845  jnz     short loc_180147854
0x180147847  mov     rbx, rax
0x18014784a  mov     rax, [rax+8]
0x18014784e  cmp     [rax+19h], r14b
0x180147852  jz      short loc_180147841
0x180147854  mov     rbx, rax
0x180147857  jmp     loc_1801475EE
0x18014785c  mov     rbx, rcx
0x18014785f  mov     rcx, [rcx]
0x180147862  cmp     [rcx+19h], r14b
0x180147866  jnz     loc_1801475EE
0x18014786c  mov     rbx, rcx
0x18014786f  mov     rax, [rcx]
0x180147872  mov     rcx, rax
0x180147875  cmp     [rax+19h], r14b
0x180147879  jz      short loc_18014786C
0x18014787b  jmp     loc_1801475EE
0x180147880  mov     r8, qword ptr [rsp+0A8h+var_48]
0x180147885  mov     r8, [r8+8]
0x180147889  lea     rdx, [rsp+0A8h+var_48]
0x18014788e  lea     rcx, [rsp+0A8h+var_48]
0x180147893  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VPlaceholderTile@PlaceholderTileTransformer@DataStoreCache@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VPlaceholderTile@PlaceholderTileTransformer@DataStoreCache@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VPlaceholderTile@PlaceholderTileTransformer@DataStoreCache@@@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VPlaceholderTile@PlaceholderTileTransformer@DataStoreCache@@@2@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<DataStoreCache::PlaceholderTileTransformer::PlaceholderTile>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<DataStoreCache::PlaceholderTileTransformer::PlaceholderTile>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<DataStoreCache::PlaceholderTileTransformer::PlaceholderTile>>,void *>> &,std::_Tree_node<std::pair<std::wstring const,std::shared_ptr<DataStoreCache::PlaceholderTileTransformer::PlaceholderTile>>,void *> *)
0x180147898  mov     edx, 50h ; 'P'
0x18014789d  mov     rcx, qword ptr [rsp+0A8h+var_48]
0x1801478a2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801478a7  mov     rcx, [rsp+0A8h+var_70]
0x1801478ac  test    rcx, rcx
0x1801478af  jz      short loc_1801478C3
0x1801478b1  mov     [rsp+0A8h+var_70], r14
0x1801478b6  mov     rax, [rcx]
0x1801478b9  mov     rax, [rax+10h]
0x1801478bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801478c2  nop
0x1801478c3  mov     rcx, [rsp+0A8h+var_60]
0x1801478c8  test    rcx, rcx
0x1801478cb  jz      short loc_1801478DA
0x1801478cd  mov     rax, [rcx]
0x1801478d0  mov     rax, [rax+10h]
0x1801478d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801478d9  nop
0x1801478da  xor     eax, eax
0x1801478dc  jmp     short loc_1801478E5
0x1801478de  mov     eax, [rsp+0A8h+length]
0x1801478e5  mov     rbx, [rsp+0A8h+arg_10]
0x1801478ed  add     rsp, 80h
0x1801478f4  pop     r14
0x1801478f6  pop     r13
0x1801478f8  pop     r12
0x1801478fa  pop     rdi
0x1801478fb  pop     rsi
0x1801478fc  retn
```
