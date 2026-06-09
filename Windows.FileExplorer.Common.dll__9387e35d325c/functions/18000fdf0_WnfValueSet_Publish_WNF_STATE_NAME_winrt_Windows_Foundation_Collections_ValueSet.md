# WnfValueSet::Publish(_WNF_STATE_NAME,winrt::Windows::Foundation::Collections::ValueSet)

- ea: `0x18000fdf0`
- end: `0x18000ff00`
- name: `?Publish@WnfValueSet@@YAXU_WNF_STATE_NAME@@UValueSet@Collections@Foundation@Windows@winrt@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800165bc`

## callees

- `0x18000fdf0`
- `0x18000ff08`
- `0x180010958`
- `0x180010bac`
- `0x180010da0`
- `0x180010f88`
- `0x180011054`
- `0x1800348e8`
- `0x180089010`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x18000fe70`
- `ntdll!RtlPublishWnfStateData` at `0x18000fe70`
- `api-ms-win-ro-typeresolution-l1-1-1!RoCreatePropertySetSerializer` at `0x18000fe10`
- `api-ms-win-ro-typeresolution-l1-1-1!RoCreatePropertySetSerializer` at `0x18000fe10`

## string_xrefs

- `0x18000fed1`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\WnfValueSet.h`
- `0x18000fee6`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\WnfValueSet.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WnfValueSet::Publish(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  int PropertySetSerializer; // eax
  unsigned int v5; // esi
  __int64 v6; // rax
  int v7; // eax
  const char *v8; // r9
  int v10; // [rsp+20h] [rbp-38h]
  _QWORD v11[5]; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v15; // [rsp+70h] [rbp+18h] BYREF
  __int64 v16; // [rsp+78h] [rbp+20h] BYREF

  v2 = a2;
  v11[0] = 0;
  PropertySetSerializer = RoCreatePropertySetSerializer(v11);
  try
  {
    if ( PropertySetSerializer < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x15,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\WnfValueSet.h",
        (const char *)(unsigned int)PropertySetSerializer,
        v10);
    wil::convert_from_abi<winrt::Windows::Storage::Streams::IPropertySetSerializer>(&v16, v11[0]);
    winrt::impl::consume_WindowsUdk_Storage_Provider_IMicrosoftGraphRecentItemsManagerExtensionStatics<winrt::WindowsUdk::Storage::Provider::IMicrosoftGraphRecentItemsManagerExtensionStatics>::GetDefault(
      &v16,
      &v15,
      v2);
    v5 = winrt::impl::consume_Windows_Internal_IMicrosoftGraphRecentItemInfo<winrt::Windows::Internal::IMicrosoftGraphRecentItemInfo>::LocationOrigin(&v15);
    v6 = winrt::impl::consume_Windows_Storage_Streams_IBuffer<winrt::Windows::Storage::Streams::IBuffer>::data(&v15);
    v7 = RtlPublishWnfStateData(a1, 0, v6, v5) | 0x10000000;
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1F,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\WnfValueSet.h",
        (const char *)(unsigned int)v7,
        0);
    if ( v15 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v15);
    if ( v16 )
      winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v16);
    if ( v11[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v11[0] + 16LL))(v11[0]);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x27,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\WnfValueSet.h",
      v8);
    v2 = a2;
  }
  return winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(v2);
}

```

## disassembly

```asm
0x18000fdf0  mov     [rsp+arg_8], rdx
0x18000fdf5  push    rbx
0x18000fdf6  push    rsi
0x18000fdf7  push    rdi
0x18000fdf8  sub     rsp, 40h
0x18000fdfc  mov     rdi, rdx
0x18000fdff  mov     rbx, rcx
0x18000fe02  mov     [rsp+58h+var_28], 0
0x18000fe0b  lea     rcx, [rsp+58h+var_28]
0x18000fe10  call    cs:__imp_RoCreatePropertySetSerializer
0x18000fe16  mov     rcx, [rsp+58h]; this
0x18000fe1b  test    eax, eax
0x18000fe1d  js      loc_18000FECE
0x18000fe23  mov     rdx, [rsp+58h+var_28]
0x18000fe28  lea     rcx, [rsp+58h+arg_18]
0x18000fe2d  call    ??$convert_from_abi@UIPropertySetSerializer@Streams@Storage@Windows@winrt@@@wil@@YA?AUIPropertySetSerializer@Streams@Storage@Windows@winrt@@PEAUIUnknown@@@Z; wil::convert_from_abi<winrt::Windows::Storage::Streams::IPropertySetSerializer>(IUnknown *)
0x18000fe32  nop
0x18000fe33  mov     r8, rdi
0x18000fe36  lea     rdx, [rsp+58h+arg_10]
0x18000fe3b  lea     rcx, [rsp+58h+arg_18]
0x18000fe40  call    ?GetDefault@?$consume_WindowsUdk_Storage_Provider_IMicrosoftGraphRecentItemsManagerExtensionStatics@UIMicrosoftGraphRecentItemsManagerExtensionStatics@Provider@Storage@WindowsUdk@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_WindowsUdk_Storage_Provider_IMicrosoftGraphRecentItemsManagerExtensionStatics<winrt::WindowsUdk::Storage::Provider::IMicrosoftGraphRecentItemsManagerExtensionStatics>::GetDefault(winrt::param::hstring const &)
0x18000fe45  nop
0x18000fe46  lea     rcx, [rsp+58h+arg_10]
0x18000fe4b  call    ?LocationOrigin@?$consume_Windows_Internal_IMicrosoftGraphRecentItemInfo@UIMicrosoftGraphRecentItemInfo@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_IMicrosoftGraphRecentItemInfo<winrt::Windows::Internal::IMicrosoftGraphRecentItemInfo>::LocationOrigin(void)
0x18000fe50  mov     esi, eax
0x18000fe52  lea     rcx, [rsp+58h+arg_10]
0x18000fe57  call    ?data@?$consume_Windows_Storage_Streams_IBuffer@UIBuffer@Streams@Storage@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Storage_Streams_IBuffer<winrt::Windows::Storage::Streams::IBuffer>::data(void)
0x18000fe5c  mov     qword ptr [rsp+58h+var_38], 0; int
0x18000fe65  mov     r9d, esi
0x18000fe68  mov     r8, rax
0x18000fe6b  xor     edx, edx
0x18000fe6d  mov     rcx, rbx
0x18000fe70  call    cs:__imp_RtlPublishWnfStateData
0x18000fe76  or      eax, 10000000h
0x18000fe7b  mov     rcx, [rsp+58h]; this
0x18000fe80  jl      short loc_18000FEE3
0x18000fe82  cmp     [rsp+58h+arg_10], 0
0x18000fe88  jz      short loc_18000FE95
0x18000fe8a  lea     rcx, [rsp+58h+arg_10]
0x18000fe8f  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18000fe94  nop
0x18000fe95  cmp     [rsp+58h+arg_18], 0
0x18000fe9b  jz      short loc_18000FEA8
0x18000fe9d  lea     rcx, [rsp+58h+arg_18]
0x18000fea2  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18000fea7  nop
0x18000fea8  mov     rcx, [rsp+58h+var_28]
0x18000fead  test    rcx, rcx
0x18000feb0  jz      short loc_18000FEBF
0x18000feb2  mov     rax, [rcx]
0x18000feb5  mov     rax, [rax+10h]
0x18000feb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000febe  nop
0x18000febf  mov     rcx, rdi
0x18000fec2  add     rsp, 40h
0x18000fec6  pop     rdi
0x18000fec7  pop     rsi
0x18000fec8  pop     rbx
0x18000fec9  jmp     ??1?$IIterator@UPerFolderRootInfo@Storage@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>::~IIterator<winrt::Windows::Internal::Storage::PerFolderRootInfo>(void)
0x18000fece  mov     r9d, eax; char *
0x18000fed1  lea     r8, aShellcommonShe_3; "shellcommon\\shell\\fileexplorer\\windo"...
0x18000fed8  mov     edx, 15h; void *
0x18000fedd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000fee3  mov     r9d, eax; char *
0x18000fee6  lea     r8, aShellcommonShe_3; "shellcommon\\shell\\fileexplorer\\windo"...
0x18000feed  mov     edx, 1Fh; void *
0x18000fef2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000fef8  mov     rdi, [rsp+58h+arg_8]
0x18000fefd  jmp     short loc_18000FEBF
```
