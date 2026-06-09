# Windows::ApplicationModel::Contacts::Internal::ContactActionControlItemBase::_CreateActionItem(HSTRING__ *)

- ea: `0x1801da298`
- end: `0x1801da59e`
- name: `?_CreateActionItem@ContactActionControlItemBase@Internal@Contacts@ApplicationModel@Windows@@IEAAXPEAUHSTRING__@@@Z`
- size: `774`
- prototype: `void __fastcall(Windows::ApplicationModel::Contacts::Internal::ContactActionControlItemBase *__hidden this, HSTRING)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801d5974`
- `0x1801da5a4`

## callees

- `0x180009dd0`
- `0x18000aa70`
- `0x18000f23c`
- `0x18002bcbc`
- `0x180041f54`
- `0x18006f0ec`
- `0x18008d328`
- `0x18015f0a0`
- `0x1801d6c20`
- `0x1801d8d3c`
- `0x1801da298`
- `0x180381f30`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801da309`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801da432`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801da309`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801da432`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801da3ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801da565`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801da3ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801da565`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801da2c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801da3ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801da45c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801da49e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801da4b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801da4dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801da2c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801da3ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801da45c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801da49e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801da4b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801da4dc`

## pseudocode

```c
void __fastcall Windows::ApplicationModel::Contacts::Internal::ContactActionControlItemBase::_CreateActionItem(
        Windows::ApplicationModel::Contacts::Internal::ContactActionControlItemBase *this,
        HSTRING a2)
{
  AgileGitPtr *v2; // r13
  PCWSTR StringRawBuffer; // rax
  bool v5; // cl
  unsigned int v6; // ebx
  const WCHAR *v7; // rdi
  int v8; // eax
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // r8
  int (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // rdi
  int (__fastcall *v13)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v14; // rdi
  int (__fastcall *v15)(__int64, HSTRING *); // rbx
  HSTRING v16; // rcx
  const WCHAR *v17; // rax
  char v18; // r12
  unsigned __int64 i; // r15
  HSTRING v20; // rcx
  const unsigned __int16 *v21; // rsi
  const unsigned __int16 *v22; // rdi
  const unsigned __int16 *v23; // rbx
  HSTRING v24; // r8
  int v25; // eax
  const unsigned __int16 *v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rdx
  HSTRING string; // [rsp+30h] [rbp-48h] BYREF
  __int64 v30; // [rsp+38h] [rbp-40h] BYREF
  __int64 v31; // [rsp+40h] [rbp-38h] BYREF
  const WCHAR *v32; // [rsp+48h] [rbp-30h]
  unsigned __int16 *v33[5]; // [rsp+50h] [rbp-28h] BYREF
  UINT32 length; // [rsp+C0h] [rbp+48h] BYREF
  HSTRING v35; // [rsp+C8h] [rbp+50h]
  struct IShellItem *v36; // [rsp+D0h] [rbp+58h] BYREF
  struct IShellItem *v37; // [rsp+D8h] [rbp+60h] BYREF

  v35 = a2;
  v2 = (Windows::ApplicationModel::Contacts::Internal::ContactActionControlItemBase *)((char *)this + 72);
  if ( *((_QWORD *)this + 9) )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 12), 0);
    v5 = 0;
    v6 = 0;
    v7 = StringRawBuffer;
    while ( !v5 )
    {
      v8 = CompareStringOrdinal(v7, -1, off_1803F9748[v6++], -1, 1);
      v5 = v8 == 2;
      if ( v6 >= 2 )
      {
        if ( v8 != 2 )
        {
          v37 = 0;
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v37);
          if ( (int)AgileGitPtr::CopyLocal(v2, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, (void **)&v37) >= 0 )
          {
            v31 = 0;
            v9 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IImmersiveMonitor>>(&v31);
            if ( (int)HiddenProperties_GetPropStoreFromItem(v10, v37, v11, v9) < 0 )
            {
              v12 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 8);
              v30 = 0;
              v13 = **v12;
              Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v30);
              if ( v13(v12, &GUID_811233d1_3151_4e14_83da_ad47404c0b41, &v30) >= 0 )
              {
                v14 = v30;
                string = 0;
                v15 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v30 + 72LL);
                WindowsDeleteString(0);
                string = 0;
                if ( v15(v14, &string) >= 0 )
                {
                  v16 = (HSTRING)*((_QWORD *)this + 12);
                  length = 0;
                  v17 = WindowsGetStringRawBuffer(v16, &length);
                  v32 = v17;
                  v18 = 0;
                  for ( i = 0; i < 6; ++i )
                  {
                    if ( v18 )
                      break;
                    if ( CompareStringOrdinal(v17, length, (&off_1803F9760)[2 * i], -1, 1) == 2 )
                    {
                      v20 = (HSTRING)*((_QWORD *)this + 14);
                      v18 = 1;
                      memset(v33, 0, 24);
                      WindowsGetStringRawBuffer(v20, 0);
                      if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
                                  v33,
                                  &_ImageBase,
                                  (unsigned int)dword_1803F976C[4 * i]) >= 0 )
                      {
                        v36 = 0;
                        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v36);
                        v21 = v33[0];
                        v22 = WindowsGetStringRawBuffer(string, 0);
                        v23 = WindowsGetStringRawBuffer(v35, 0);
                        v25 = Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                                *((Microsoft::WRL::Wrappers::Details **)this + 13),
                                0,
                                v24);
                        v26 = WindowsGetStringRawBuffer(*(HSTRING *)((char *)this + (v25 != 0 ? 8 : 0) + 96), 0);
                        if ( (int)CreateShellItemWithActionInformation(v37, v26, v23, v22, v21, &v36) >= 0 )
                        {
                          LOBYTE(v27) = 1;
                          wil::details::FeatureImpl<__WilFeatureTraits_Feature_KeepWin8SearchPane>::ReportUsage(
                            `wil::Feature<__WilFeatureTraits_Feature_KeepWin8SearchPane>::GetImpl'::`2'::impl,
                            v27);
                          StoreItemInHistory(v36);
                          AgileGitPtr::Initialize(v2, v28, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, v36);
                        }
                        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v36);
                      }
                      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v33);
                    }
                    else
                    {
                      v18 = 0;
                    }
                    v17 = v32;
                  }
                }
                WindowsDeleteString(string);
              }
              Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v30);
            }
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v31);
          }
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v37);
        }
        return;
      }
    }
  }
}

```

## disassembly

```asm
0x1801da298  mov     [rsp-40h+arg_8], rdx
0x1801da29d  push    rbp
0x1801da29e  push    rbx
0x1801da29f  push    rsi
0x1801da2a0  push    rdi
0x1801da2a1  push    r12
0x1801da2a3  push    r13
0x1801da2a5  push    r14
0x1801da2a7  push    r15
0x1801da2a9  mov     rbp, rsp
0x1801da2ac  sub     rsp, 78h
0x1801da2b0  lea     r13, [rcx+48h]
0x1801da2b4  xor     esi, esi
0x1801da2b6  mov     r14, rcx
0x1801da2b9  cmp     [r13+0], rsi
0x1801da2bd  jz      loc_1801DA58C
0x1801da2c3  mov     rcx, [rcx+60h]; string
0x1801da2c7  xor     edx, edx; length
0x1801da2c9  call    cs:__imp_WindowsGetStringRawBuffer
0x1801da2d0  nop     dword ptr [rax+rax+00h]
0x1801da2d5  mov     cl, sil
0x1801da2d8  mov     ebx, esi
0x1801da2da  mov     rdi, rax
0x1801da2dd  lea     rax, __ImageBase
0x1801da2e4  test    cl, cl
0x1801da2e6  jnz     loc_1801DA58C
0x1801da2ec  or      r9d, 0FFFFFFFFh; cchCount2
0x1801da2f0  movsxd  r8, ebx
0x1801da2f3  or      edx, r9d; cchCount1
0x1801da2f6  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x1801da2fe  mov     rcx, rdi; lpString1
0x1801da301  mov     r8, ds:rva off_1803F9748[rax+r8*8]; lpString2
0x1801da309  call    cs:__imp_CompareStringOrdinal
0x1801da310  nop     dword ptr [rax+rax+00h]
0x1801da315  inc     ebx
0x1801da317  cmp     eax, 2
0x1801da31a  setz    cl
0x1801da31d  cmp     ebx, 2
0x1801da320  jb      short loc_1801DA2DD
0x1801da322  cmp     eax, 2
0x1801da325  jz      loc_1801DA58C
0x1801da32b  lea     rcx, [rbp+arg_18]
0x1801da32f  mov     [rbp+arg_18], rsi
0x1801da333  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801da338  lea     r8, [rbp+arg_18]; void **
0x1801da33c  mov     rcx, r13; this
0x1801da33f  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; struct _GUID *
0x1801da346  call    ?CopyLocal@AgileGitPtr@@QEBAJAEBU_GUID@@PEAPEAX@Z; AgileGitPtr::CopyLocal(_GUID const &,void * *)
0x1801da34b  test    eax, eax
0x1801da34d  js      loc_1801DA583
0x1801da353  lea     rcx, [rbp+var_38]
0x1801da357  mov     [rbp+var_38], rsi
0x1801da35b  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIImmersiveMonitor@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIImmersiveMonitor@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IImmersiveMonitor>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IImmersiveMonitor>>)
0x1801da360  mov     rdx, [rbp+arg_18]
0x1801da364  mov     r9, rax
0x1801da367  call    ?HiddenProperties_GetPropStoreFromItem@@YAJW4IDLHID@@PEAUIShellItem@@AEBU_GUID@@PEAPEAX@Z; HiddenProperties_GetPropStoreFromItem(IDLHID,IShellItem *,_GUID const &,void * *)
0x1801da36c  test    eax, eax
0x1801da36e  jns     loc_1801DA57A
0x1801da374  mov     rdi, [r14+40h]
0x1801da378  lea     rcx, [rbp+var_40]
0x1801da37c  mov     [rbp+var_40], rsi
0x1801da380  mov     rax, [rdi]
0x1801da383  mov     rbx, [rax]
0x1801da386  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801da38b  lea     r8, [rbp+var_40]
0x1801da38f  mov     rcx, rdi
0x1801da392  lea     rdx, _GUID_811233d1_3151_4e14_83da_ad47404c0b41
0x1801da399  mov     rax, rbx
0x1801da39c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801da3a1  test    eax, eax
0x1801da3a3  js      loc_1801DA571
0x1801da3a9  mov     rdi, [rbp+var_40]
0x1801da3ad  xor     ecx, ecx; string
0x1801da3af  mov     [rbp+string], rsi
0x1801da3b3  mov     rax, [rdi]
0x1801da3b6  mov     rbx, [rax+48h]
0x1801da3ba  call    cs:__imp_WindowsDeleteString
0x1801da3c1  nop     dword ptr [rax+rax+00h]
0x1801da3c6  lea     rdx, [rbp+string]
0x1801da3ca  mov     [rbp+string], rsi
0x1801da3ce  mov     rcx, rdi
0x1801da3d1  mov     rax, rbx
0x1801da3d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801da3d9  test    eax, eax
0x1801da3db  js      loc_1801DA561
0x1801da3e1  mov     rcx, [r14+60h]; string
0x1801da3e5  lea     rdx, [rbp+length]; length
0x1801da3e9  mov     [rbp+length], esi
0x1801da3ec  call    cs:__imp_WindowsGetStringRawBuffer
0x1801da3f3  nop     dword ptr [rax+rax+00h]
0x1801da3f8  mov     [rbp+var_30], rax
0x1801da3fc  mov     r12b, sil
0x1801da3ff  mov     r15, rsi
0x1801da402  test    r12b, r12b
0x1801da405  jnz     loc_1801DA561
0x1801da40b  mov     edx, [rbp+length]; cchCount1
0x1801da40e  lea     rdi, __ImageBase
0x1801da415  mov     rbx, r15
0x1801da418  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x1801da420  add     rbx, rbx
0x1801da423  or      r9d, 0FFFFFFFFh; cchCount2
0x1801da427  mov     rcx, rax; lpString1
0x1801da42a  mov     r8, ds:rva off_1803F9760[rdi+rbx*8]; lpString2
0x1801da432  call    cs:__imp_CompareStringOrdinal
0x1801da439  nop     dword ptr [rax+rax+00h]
0x1801da43e  cmp     eax, 2
0x1801da441  jnz     loc_1801DA54D
0x1801da447  mov     rcx, [r14+70h]; string
0x1801da44b  xor     edx, edx; length
0x1801da44d  mov     r12b, 1
0x1801da450  mov     [rbp+var_28], rsi
0x1801da454  mov     [rbp+var_20], rsi
0x1801da458  mov     [rbp+var_18], rsi
0x1801da45c  call    cs:__imp_WindowsGetStringRawBuffer
0x1801da463  nop     dword ptr [rax+rax+00h]
0x1801da468  mov     r8d, ds:rva dword_1803F976C[rdi+rbx*8]
0x1801da470  lea     rcx, [rbp+var_28]
0x1801da474  mov     r9, rax
0x1801da477  mov     rdx, rdi
0x1801da47a  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x1801da47f  test    eax, eax
0x1801da481  js      loc_1801DA542
0x1801da487  lea     rcx, [rbp+arg_10]
0x1801da48b  mov     [rbp+arg_10], rsi
0x1801da48f  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801da494  mov     rcx, [rbp+string]; string
0x1801da498  xor     edx, edx; length
0x1801da49a  mov     rsi, [rbp+var_28]
0x1801da49e  call    cs:__imp_WindowsGetStringRawBuffer
0x1801da4a5  nop     dword ptr [rax+rax+00h]
0x1801da4aa  mov     rcx, [rbp+arg_8]; string
0x1801da4ae  xor     edx, edx; length
0x1801da4b0  mov     rdi, rax
0x1801da4b3  call    cs:__imp_WindowsGetStringRawBuffer
0x1801da4ba  nop     dword ptr [rax+rax+00h]
0x1801da4bf  mov     rcx, [r14+68h]; this
0x1801da4c3  xor     edx, edx; HSTRING
0x1801da4c5  mov     rbx, rax
0x1801da4c8  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x1801da4cd  neg     eax
0x1801da4cf  sbb     rcx, rcx
0x1801da4d2  xor     edx, edx; length
0x1801da4d4  and     ecx, 8
0x1801da4d7  mov     rcx, [rcx+r14+60h]; string
0x1801da4dc  call    cs:__imp_WindowsGetStringRawBuffer
0x1801da4e3  nop     dword ptr [rax+rax+00h]
0x1801da4e8  lea     rcx, [rbp+arg_10]
0x1801da4ec  mov     r9, rdi; unsigned __int16 *
0x1801da4ef  mov     [rsp+78h+var_50], rcx; struct IShellItem **
0x1801da4f4  mov     r8, rbx; unsigned __int16 *
0x1801da4f7  mov     rcx, [rbp+arg_18]; struct IShellItem *
0x1801da4fb  mov     rdx, rax; unsigned __int16 *
0x1801da4fe  mov     qword ptr [rsp+78h+bIgnoreCase], rsi; unsigned __int16 *
0x1801da503  call    ?CreateShellItemWithActionInformation@@YAJPEAUIShellItem@@PEBG111PEAPEAU1@@Z; CreateShellItemWithActionInformation(IShellItem *,ushort const *,ushort const *,ushort const *,ushort const *,IShellItem * *)
0x1801da508  xor     esi, esi
0x1801da50a  test    eax, eax
0x1801da50c  js      short loc_1801DA539
0x1801da50e  mov     dl, r12b
0x1801da511  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_KeepWin8SearchPane@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_KeepWin8SearchPane@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KeepWin8SearchPane> `wil::Feature<__WilFeatureTraits_Feature_KeepWin8SearchPane>::GetImpl(void)'::`2'::impl
0x1801da518  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_KeepWin8SearchPane@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_KeepWin8SearchPane>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1801da51d  mov     rcx, [rbp+arg_10]; struct IShellItem *
0x1801da521  call    ?StoreItemInHistory@@YAJPEAUIShellItem@@@Z; StoreItemInHistory(IShellItem *)
0x1801da526  mov     r9, [rbp+arg_10]
0x1801da52a  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x1801da531  mov     rcx, r13
0x1801da534  call    ?Initialize@AgileGitPtr@@QEAAJW4AgileReferenceOptions@@AEBU_GUID@@PEAUIUnknown@@@Z; AgileGitPtr::Initialize(AgileReferenceOptions,_GUID const &,IUnknown *)
0x1801da539  lea     rcx, [rbp+arg_10]
0x1801da53d  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801da542  lea     rcx, [rbp+var_28]
0x1801da546  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801da54b  jmp     short loc_1801DA550
0x1801da54d  mov     r12b, sil
0x1801da550  mov     rax, [rbp+var_30]
0x1801da554  inc     r15
0x1801da557  cmp     r15, 6
0x1801da55b  jb      loc_1801DA402
0x1801da561  mov     rcx, [rbp+string]; string
0x1801da565  call    cs:__imp_WindowsDeleteString
0x1801da56c  nop     dword ptr [rax+rax+00h]
0x1801da571  lea     rcx, [rbp+var_40]
0x1801da575  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801da57a  lea     rcx, [rbp+var_38]
0x1801da57e  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801da583  lea     rcx, [rbp+arg_18]
0x1801da587  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801da58c  add     rsp, 78h
0x1801da590  pop     r15
0x1801da592  pop     r14
0x1801da594  pop     r13
0x1801da596  pop     r12
0x1801da598  pop     rdi
0x1801da599  pop     rsi
0x1801da59a  pop     rbx
0x1801da59b  pop     rbp
0x1801da59c  retn
```
