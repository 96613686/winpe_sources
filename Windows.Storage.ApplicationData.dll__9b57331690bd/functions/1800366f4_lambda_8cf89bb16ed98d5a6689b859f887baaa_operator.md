# _lambda_8cf89bb16ed98d5a6689b859f887baaa_::operator()

- ea: `0x1800366f4`
- end: `0x18003695c`
- name: `_lambda_8cf89bb16ed98d5a6689b859f887baaa_::operator()`
- size: `616`
- prototype: `HRESULT __fastcall()`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18001af48`

## callees

- `0x1800022b0`
- `0x180009778`
- `0x18000c260`
- `0x180021efc`
- `0x180024fc4`
- `0x180025004`
- `0x1800366f4`
- `0x180038c4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003677b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003677b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800368a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800368fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800368a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800368fb`
- `api-ms-win-storage-exports-external-l1-1-0!STORAGE_CreateStorageItemFromShellItem_FullTrustCaller_ForPackage` at `0x1800368c3`
- `api-ms-win-storage-exports-external-l1-1-0!STORAGE_CreateStorageItemFromShellItem_FullTrustCaller_ForPackage` at `0x18003691c`
- `api-ms-win-storage-exports-external-l1-1-0!STORAGE_CreateStorageItemFromShellItem_FullTrustCaller_ForPackage` at `0x1800368c3`
- `api-ms-win-storage-exports-external-l1-1-0!STORAGE_CreateStorageItemFromShellItem_FullTrustCaller_ForPackage` at `0x18003691c`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetStateFolder` at `0x180036742`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetStateFolder` at `0x18003681a`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetStateFolder` at `0x180036742`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetStateFolder` at `0x18003681a`

## string_xrefs

- `0x1800368cf`: `STORAGE_CreateStorageItemFromShellItem_FullTrustCaller_ForPackage %ws`
- `0x180036928`: `STORAGE_CreateStorageItemFromShellItem_FullTrustCaller_ForPackage %ws`

## pseudocode

```c
__int64 __fastcall lambda_8cf89bb16ed98d5a6689b859f887baaa_::operator()(__int64 a1)
{
  __int64 v2; // rcx
  unsigned int LastErrorMsg; // ebx
  unsigned int v4; // edx
  signed int LastError; // eax
  wchar_t *v6; // rax
  wchar_t *v7; // rsi
  HRESULT FolderItemWithJunctionSkipping; // eax
  bool IsEnabled; // al
  __int64 v10; // rbx
  HSTRING v11; // rcx
  PCWSTR StringRawBuffer; // rax
  HRESULT StorageItemFromShellItem_FullTrustCaller_ForPackage; // eax
  PCWSTR v14; // rax
  HRESULT v15; // eax
  void *retaddr; // [rsp+38h] [rbp+0h]

  v2 = *(_QWORD *)(*(_QWORD *)a1 + 88LL);
  if ( !v2 )
  {
    LastErrorMsg = -2147483629;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x56Fu,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
      -2147483629);
    return LastErrorMsg;
  }
  if ( (unsigned int)GetStateFolder(v2, **(unsigned int **)(a1 + 8), 0, *(_QWORD *)(a1 + 16)) )
  {
    LastErrorMsg = -2147418113;
    v4 = 1395;
LABEL_5:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      v4,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
      LastErrorMsg,
      "GetStateFolder");
    return LastErrorMsg;
  }
  LastError = GetLastError();
  LastErrorMsg = LastError;
  if ( LastError == 122 )
  {
    v6 = (wchar_t *)operator new(saturated_mul(**(unsigned int **)(a1 + 16), 2u));
    v7 = v6;
    if ( !v6 )
    {
      LastErrorMsg = -2147024882;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x57Au,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
        -2147024882,
        "new %u",
        **(_DWORD **)(a1 + 16));
      return LastErrorMsg;
    }
    if ( (unsigned int)GetStateFolder(
                         *(_QWORD *)(*(_QWORD *)a1 + 88LL),
                         **(unsigned int **)(a1 + 8),
                         v6,
                         *(_QWORD *)(a1 + 16)) )
    {
      FolderItemWithJunctionSkipping = Windows::Storage::ApplicationDataServer::CreateFolderItemWithJunctionSkipping(
                                         v7,
                                         *(Microsoft::WRL::ComPtr<Windows::ApplicationModel::Core::ICoreApplicationPrivate> **)(a1 + 24));
      LastErrorMsg = FolderItemWithJunctionSkipping;
      if ( FolderItemWithJunctionSkipping >= 0 )
      {
        IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ApplicationDataApiPerf>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_ApplicationDataApiPerf>::GetImpl'::`2'::impl);
        v10 = **(_QWORD **)(a1 + 32);
        v11 = *(HSTRING *)(*(_QWORD *)a1 + 96LL);
        if ( IsEnabled )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(v11, 0);
          StorageItemFromShellItem_FullTrustCaller_ForPackage = STORAGE_CreateStorageItemFromShellItem_FullTrustCaller_ForPackage(
                                                                  **(_QWORD **)(a1 + 24),
                                                                  133,
                                                                  StringRawBuffer,
                                                                  &GUID_72d1cb78_b3ef_4f75_a80b_6fd9dae2944b,
                                                                  v10);
          LastErrorMsg = StorageItemFromShellItem_FullTrustCaller_ForPackage;
          if ( StorageItemFromShellItem_FullTrustCaller_ForPackage < 0 )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              0x58Au,
              "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
              StorageItemFromShellItem_FullTrustCaller_ForPackage,
              "STORAGE_CreateStorageItemFromShellItem_FullTrustCaller_ForPackage %ws",
              v7);
            goto LABEL_23;
          }
        }
        else
        {
          v14 = WindowsGetStringRawBuffer(v11, 0);
          v15 = STORAGE_CreateStorageItemFromShellItem_FullTrustCaller_ForPackage(
                  **(_QWORD **)(a1 + 24),
                  129,
                  v14,
                  &GUID_72d1cb78_b3ef_4f75_a80b_6fd9dae2944b,
                  v10);
          LastErrorMsg = v15;
          if ( v15 < 0 )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              0x594u,
              "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
              v15,
              "STORAGE_CreateStorageItemFromShellItem_FullTrustCaller_ForPackage %ws",
              v7);
            goto LABEL_23;
          }
        }
        LastErrorMsg = 0;
        goto LABEL_23;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        0x580u,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
        FolderItemWithJunctionSkipping);
    }
    else
    {
      LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                       retaddr,
                       0x57Eu,
                       "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
                       "GetStateFolder %u",
                       **(_DWORD **)(a1 + 16));
    }
LABEL_23:
    operator delete(v7);
    return LastErrorMsg;
  }
  if ( LastError > 0 )
    LastErrorMsg = (unsigned __int16)LastError | 0x80070000;
  if ( (LastErrorMsg & 0x80000000) != 0 )
  {
    v4 = 1398;
    goto LABEL_5;
  }
  return LastErrorMsg;
}

```

## disassembly

```asm
0x1800366f4  mov     [rsp+arg_0], rbx
0x1800366f9  mov     [rsp+arg_8], rsi
0x1800366fe  push    rdi
0x1800366ff  sub     rsp, 30h
0x180036703  mov     rax, [this]
0x180036706  mov     rdi, this
0x180036709  mov     this, [rax+58h]
0x18003670d  test    this, this
0x180036710  jnz     short loc_180036735
0x180036712  mov     this, [rsp+38h]; callerReturnAddress
0x180036717  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003671e  mov     ebx, 80000013h
0x180036723  mov     edx, 56Fh; lineNumber
0x180036728  mov     r9d, ebx; hr
0x18003672b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036730  jmp     loc_18003694A
0x180036735  mov     rdx, [rdi+8]
0x180036739  xor     r8d, r8d
0x18003673c  mov     r9, [rdi+10h]
0x180036740  mov     edx, [rdx]
0x180036742  call    cs:__imp_GetStateFolder
0x180036748  test    eax, eax
0x18003674a  jz      short loc_18003677B
0x18003674c  mov     ebx, 8000FFFFh
0x180036751  mov     edx, 573h; lineNumber
0x180036756  mov     this, [rsp+38h]; callerReturnAddress
0x18003675b  lea     rax, aGetstatefolder_0; "GetStateFolder"
0x180036762  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\statemanage"...
0x180036769  mov     [rsp+38h+formatString], rax; formatString
0x18003676e  mov     r9d, ebx; hr
0x180036771  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180036776  jmp     loc_18003694A
0x18003677b  call    cs:__imp_GetLastError
0x180036781  mov     ebx, eax
0x180036783  cmp     eax, 7Ah ; 'z'
0x180036786  jz      short loc_1800367A4
0x180036788  test    eax, eax
0x18003678a  jle     short loc_180036795
0x18003678c  movzx   ebx, ax
0x18003678f  or      ebx, 80070000h
0x180036795  test    ebx, ebx
0x180036797  jns     loc_18003694A
0x18003679d  mov     edx, 576h
0x1800367a2  jmp     short loc_180036756
0x1800367a4  mov     rax, [rdi+10h]
0x1800367a8  mov     ecx, [rax]
0x1800367aa  mov     eax, 2
0x1800367af  mul     this
0x1800367b2  mov     this, 0FFFFFFFFFFFFFFFFh
0x1800367b9  cmovb   rax, this
0x1800367bd  mov     this, rax; cb
0x1800367c0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800367c5  mov     rsi, rax
0x1800367c8  test    rax, rax
0x1800367cb  jnz     short loc_180036806
0x1800367cd  mov     rax, [rdi+10h]
0x1800367d1  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\statemanage"...
0x1800367d8  mov     this, [rsp+38h]; callerReturnAddress
0x1800367dd  mov     ebx, 8007000Eh
0x1800367e2  mov     r9d, ebx; hr
0x1800367e5  mov     edx, 57Ah; lineNumber
0x1800367ea  mov     eax, [rax]
0x1800367ec  mov     dword ptr [rsp+38h+var_10], eax
0x1800367f0  lea     rax, aNewU; "new %u"
0x1800367f7  mov     [rsp+38h+formatString], rax; formatString
0x1800367fc  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180036801  jmp     loc_18003694A
0x180036806  mov     rdx, [rdi+8]
0x18003680a  mov     r8, rsi
0x18003680d  mov     this, [rdi]
0x180036810  mov     r9, [rdi+10h]
0x180036814  mov     edx, [rdx]
0x180036816  mov     this, [this+58h]
0x18003681a  call    cs:__imp_GetStateFolder
0x180036820  test    eax, eax
0x180036822  jnz     short loc_180036852
0x180036824  mov     rax, [rdi+10h]
0x180036828  lea     r9, aGetstatefolder_1; "GetStateFolder %u"
0x18003682f  mov     this, [rsp+38h]; callerReturnAddress
0x180036834  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003683b  mov     edx, 57Eh; lineNumber
0x180036840  mov     eax, [rax]
0x180036842  mov     dword ptr [rsp+38h+formatString], eax
0x180036846  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18003684b  mov     ebx, eax
0x18003684d  jmp     loc_180036942
0x180036852  mov     rdx, [rdi+18h]; shellItem
0x180036856  mov     this, rsi; folderPath
0x180036859  call    ?CreateFolderItemWithJunctionSkipping@ApplicationDataServer@Storage@Windows@@CAJPEBGAEAV?$ComPtr@UIShellItem@@@WRL@Microsoft@@@Z; Windows::Storage::ApplicationDataServer::CreateFolderItemWithJunctionSkipping(ushort const *,Microsoft::WRL::ComPtr<IShellItem> &)
0x18003685e  mov     ebx, eax
0x180036860  test    eax, eax
0x180036862  jns     short loc_180036882
0x180036864  mov     this, [rsp+38h]; callerReturnAddress
0x180036869  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\statemanage"...
0x180036870  mov     r9d, eax; hr
0x180036873  mov     edx, 580h; lineNumber
0x180036878  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003687d  jmp     loc_180036942
0x180036882  lea     this, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ApplicationDataApiPerf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ApplicationDataApiPerf@@@details@3@XZ@4V453@A; __annotation("WILSTG:|59783591|Feature_ApplicationDataApiPerf|EnabledByDefault")
0x180036889  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ApplicationDataApiPerf@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ApplicationDataApiPerf>::__private_IsEnabled(void)
0x18003688e  mov     this, [rdi+20h]
0x180036892  xor     edx, edx; length
0x180036894  mov     rbx, [this]
0x180036897  mov     this, [rdi]
0x18003689a  mov     this, [this+60h]; string
0x18003689e  test    al, al
0x1800368a0  jz      short loc_1800368FB
0x1800368a2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800368a8  mov     this, [rdi+18h]
0x1800368ac  lea     r9, _GUID_72d1cb78_b3ef_4f75_a80b_6fd9dae2944b
0x1800368b3  mov     r8, rax
0x1800368b6  mov     [rsp+38h+formatString], rbx
0x1800368bb  mov     edx, 85h
0x1800368c0  mov     this, [this]
0x1800368c3  call    cs:__imp_STORAGE_CreateStorageItemFromShellItem_FullTrustCaller_ForPackage
0x1800368c9  mov     ebx, eax
0x1800368cb  test    eax, eax
0x1800368cd  jns     short loc_180036940
0x1800368cf  lea     rdx, aStorageCreates_0; "STORAGE_CreateStorageItemFromShellItem_"...
0x1800368d6  mov     [rsp+38h+var_10], rsi
0x1800368db  mov     [rsp+38h+formatString], rdx; formatString
0x1800368e0  mov     edx, 58Ah; lineNumber
0x1800368e5  mov     this, [rsp+38h]; callerReturnAddress
0x1800368ea  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\statemanage"...
0x1800368f1  mov     r9d, eax; hr
0x1800368f4  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800368f9  jmp     short loc_180036942
0x1800368fb  call    cs:__imp_WindowsGetStringRawBuffer
0x180036901  mov     this, [rdi+18h]
0x180036905  lea     r9, _GUID_72d1cb78_b3ef_4f75_a80b_6fd9dae2944b
0x18003690c  mov     r8, rax
0x18003690f  mov     [rsp+38h+formatString], rbx
0x180036914  mov     edx, 81h
0x180036919  mov     this, [this]
0x18003691c  call    cs:__imp_STORAGE_CreateStorageItemFromShellItem_FullTrustCaller_ForPackage
0x180036922  mov     ebx, eax
0x180036924  test    eax, eax
0x180036926  jns     short loc_180036940
0x180036928  lea     rdx, aStorageCreates_0; "STORAGE_CreateStorageItemFromShellItem_"...
0x18003692f  mov     [rsp+38h+var_10], rsi
0x180036934  mov     [rsp+38h+formatString], rdx
0x180036939  mov     edx, 594h
0x18003693e  jmp     short loc_1800368E5
0x180036940  xor     ebx, ebx
0x180036942  mov     this, rsi; p
0x180036945  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003694a  mov     rsi, [rsp+38h+arg_8]
0x18003694f  mov     eax, ebx
0x180036951  mov     rbx, [rsp+38h+arg_0]
0x180036956  add     rsp, 30h
0x18003695a  pop     rdi
0x18003695b  retn
```
