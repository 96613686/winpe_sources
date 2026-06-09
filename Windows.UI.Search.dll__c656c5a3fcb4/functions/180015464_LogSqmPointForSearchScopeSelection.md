# LogSqmPointForSearchScopeSelection

- ea: `0x180015464`
- end: `0x1800156f9`
- name: `LogSqmPointForSearchScopeSelection`
- size: `661`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000ffc0`
- `0x1800111b0`
- `0x180038c1c`
- `0x180064d20`

## callees

- `0x1800030b6`
- `0x180007b3c`
- `0x1800120dc`
- `0x180014e3c`
- `0x180014f58`
- `0x180014fe0`
- `0x1800150a8`
- `0x180015464`
- `0x18003f0f0`
- `0x180076c50`

## import_xrefs

- `ntdll!WinSqmIsOptedIn` at `0x18001549b`
- `ntdll!WinSqmIsOptedIn` at `0x18001549b`
- `ntdll!WinSqmAddToStream` at `0x1800156b7`
- `ntdll!WinSqmAddToStream` at `0x1800156b7`
- `SHELL32!SHCreateItemInKnownFolder` at `0x1800155b7`
- `SHELL32!SHCreateItemInKnownFolder` at `0x1800155b7`

## pseudocode

```c
void __fastcall LogSqmPointForSearchScopeSelection(int a1, const WCHAR *a2, const unsigned __int16 *a3, int a4, int a5)
{
  int v9; // ebx
  struct IPropertyStore *v10; // rdx
  __int64 v11; // r8
  int v12; // [rsp+30h] [rbp-D0h] BYREF
  void *ppv; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v14[8]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v15; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v16; // [rsp+50h] [rbp-B0h]
  __int64 v17; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v18; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v19; // [rsp+68h] [rbp-98h]
  __int64 v20; // [rsp+70h] [rbp-90h]
  __int128 v21; // [rsp+80h] [rbp-80h] BYREF
  int v22; // [rsp+90h] [rbp-70h]
  _DWORD v23[4]; // [rsp+A0h] [rbp-60h] BYREF
  int v24; // [rsp+B0h] [rbp-50h] BYREF
  const wchar_t *v25; // [rsp+B8h] [rbp-48h]
  int v26; // [rsp+C0h] [rbp-40h] BYREF
  const wchar_t *v27; // [rsp+C8h] [rbp-38h]
  int v28; // [rsp+D0h] [rbp-30h]
  int v29; // [rsp+D8h] [rbp-28h]
  int v30; // [rsp+E0h] [rbp-20h] BYREF
  const wchar_t *v31; // [rsp+E8h] [rbp-18h]
  int v32; // [rsp+F0h] [rbp-10h]
  int v33; // [rsp+F8h] [rbp-8h]
  int v34; // [rsp+100h] [rbp+0h]
  int v35; // [rsp+108h] [rbp+8h]
  int v36; // [rsp+110h] [rbp+10h] BYREF
  const wchar_t *v37; // [rsp+118h] [rbp+18h]

  if ( (unsigned int)WinSqmIsOptedIn() )
  {
    memset_0(v23, 0, 0x80u);
    v23[2] = a1;
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v15 = 0;
    v16 = 0;
    v17 = 0;
    v23[0] = 1;
    if ( a2 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v18);
      v19 = -1;
      v20 = -1;
      GetPackageFullNameFromAppId(a2, &v18);
      WinSqmCreateStringStreamEntry((struct _SQM_STREAM_ENTRY *)&v24, v18);
      WinSqmCreateStringStreamEntry((struct _SQM_STREAM_ENTRY *)&v26, a2);
    }
    else
    {
      v25 = L"(null)";
      v24 = 2;
      v27 = L"(null)";
      v26 = 2;
    }
    v33 = a5;
    v29 = a4;
    v28 = 1;
    v32 = 1;
    if ( a3 )
    {
      WinSqmCreateStringStreamEntry((struct _SQM_STREAM_ENTRY *)&v30, a3);
      v9 = 0;
      ppv = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
      if ( SHCreateItemInKnownFolder(
             &FOLDERID_AppsFolder,
             0x4000u,
             a3,
             &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
             &ppv) >= 0 )
      {
        wil::PropertyStoreHelper::PropertyStoreHelper((wil::PropertyStoreHelper *)v14, v10);
        v12 = 0;
        *(_QWORD *)&v21 = 0x456CC6140DED77B3LL;
        *((_QWORD *)&v21 + 1) = 0x1BB0D7385B285BAELL;
        v22 = 6;
        if ( (int)wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(v14, ppv, v11, &v21) >= 0 )
        {
          v22 = 6;
          v21 = PKEY_Launcher_ViewID;
          if ( (int)wil::PropertyStoreHelperBase<IPropertyStore>::GetUInt32<_tagpropertykey>(v14, &v21, &v12) >= 0
            && !v12 )
          {
            v9 = 2;
          }
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(v14);
      }
      v35 = v9;
      v34 = 1;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v15);
      v16 = -1;
      v17 = -1;
      GetPackageFullNameFromAppId(a3, &v15);
      WinSqmCreateStringStreamEntry((struct _SQM_STREAM_ENTRY *)&v36, v15);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
    }
    else
    {
      v31 = L"(null)";
      v30 = 2;
      v35 = 0;
      v34 = 1;
      v37 = L"(null)";
      v36 = 2;
    }
    WinSqmAddToStream(0, 9199, 8, v23);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v15);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)&v18);
  }
}

```

## disassembly

```asm
0x180015464  mov     [rsp-8+arg_0], rbx
0x180015469  mov     [rsp-8+arg_18], rsi
0x18001546e  push    rbp
0x18001546f  push    rdi
0x180015470  push    r12
0x180015472  push    r13
0x180015474  push    r14
0x180015476  lea     rbp, [rsp-30h]
0x18001547b  sub     rsp, 130h
0x180015482  mov     rax, cs:__security_cookie
0x180015489  xor     rax, rsp
0x18001548c  mov     [rbp+50h+var_30], rax
0x180015490  mov     r14d, r9d
0x180015493  mov     rdi, r8
0x180015496  mov     rbx, rdx
0x180015499  mov     esi, ecx
0x18001549b  call    cs:__imp_WinSqmIsOptedIn
0x1800154a1  test    eax, eax
0x1800154a3  jz      loc_1800156D1
0x1800154a9  xor     edx, edx; Val
0x1800154ab  lea     rcx, [rbp+50h+var_B0]; void *
0x1800154af  mov     r8d, 80h; Size
0x1800154b5  call    memset_0
0x1800154ba  mov     [rbp+50h+var_A8], esi
0x1800154bd  mov     r13d, 1
0x1800154c3  mov     [rsp+150h+var_F0], 0
0x1800154cc  lea     r12, aNull; "(null)"
0x1800154d3  mov     [rsp+150h+var_E8], 0
0x1800154dc  mov     [rsp+150h+var_E0], 0
0x1800154e5  mov     [rsp+150h+var_108], 0
0x1800154ee  lea     esi, [r13+1]
0x1800154f2  mov     [rsp+150h+var_100], 0
0x1800154fb  mov     [rsp+150h+var_F8], 0
0x180015504  mov     [rbp+50h+var_B0], r13d
0x180015508  test    rbx, rbx
0x18001550b  jz      short loc_18001554E
0x18001550d  lea     rcx, [rsp+150h+var_F0]
0x180015512  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180015517  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001551b  lea     rdx, [rsp+150h+var_F0]; unsigned __int16 **
0x180015520  mov     rcx, rbx; pszItem
0x180015523  mov     [rsp+150h+var_E8], rax
0x180015528  mov     [rsp+150h+var_E0], rax
0x18001552d  call    ?GetPackageFullNameFromAppId@@YAJPEBGPEAPEAG@Z; GetPackageFullNameFromAppId(ushort const *,ushort * *)
0x180015532  mov     rdx, [rsp+150h+var_F0]; unsigned __int16 *
0x180015537  lea     rcx, [rbp+50h+var_A0]; struct _SQM_STREAM_ENTRY *
0x18001553b  call    ?WinSqmCreateStringStreamEntry@@YAXPEAU_SQM_STREAM_ENTRY@@PEBG@Z; WinSqmCreateStringStreamEntry(_SQM_STREAM_ENTRY *,ushort const *)
0x180015540  mov     rdx, rbx; unsigned __int16 *
0x180015543  lea     rcx, [rbp+50h+var_90]; struct _SQM_STREAM_ENTRY *
0x180015547  call    ?WinSqmCreateStringStreamEntry@@YAXPEAU_SQM_STREAM_ENTRY@@PEBG@Z; WinSqmCreateStringStreamEntry(_SQM_STREAM_ENTRY *,ushort const *)
0x18001554c  jmp     short loc_18001555C
0x18001554e  mov     [rbp+50h+var_98], r12
0x180015552  mov     [rbp+50h+var_A0], esi
0x180015555  mov     [rbp+50h+var_88], r12
0x180015559  mov     [rbp+50h+var_90], esi
0x18001555c  mov     eax, [rbp+50h+arg_20]
0x180015562  mov     [rbp+50h+var_58], eax
0x180015565  mov     [rbp+50h+var_78], r14d
0x180015569  mov     [rbp+50h+var_80], r13d
0x18001556d  mov     [rbp+50h+var_60], r13d
0x180015571  test    rdi, rdi
0x180015574  jz      loc_18001568F
0x18001557a  mov     rdx, rdi; unsigned __int16 *
0x18001557d  lea     rcx, [rbp+50h+var_70]; struct _SQM_STREAM_ENTRY *
0x180015581  call    ?WinSqmCreateStringStreamEntry@@YAXPEAU_SQM_STREAM_ENTRY@@PEBG@Z; WinSqmCreateStringStreamEntry(_SQM_STREAM_ENTRY *,ushort const *)
0x180015586  xor     ebx, ebx
0x180015588  lea     rcx, [rsp+150h+var_118]
0x18001558d  mov     [rsp+150h+var_118], rbx
0x180015592  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180015597  lea     rax, [rsp+150h+var_118]
0x18001559c  mov     r8, rdi; pszItem
0x18001559f  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800155a6  mov     [rsp+150h+ppv], rax; ppv
0x1800155ab  mov     edx, 4000h; dwKFFlags
0x1800155b0  lea     rcx, FOLDERID_AppsFolder; kfid
0x1800155b7  call    cs:__imp_SHCreateItemInKnownFolder
0x1800155bd  test    eax, eax
0x1800155bf  js      loc_180015649
0x1800155c5  lea     rcx, [rsp+150h+var_110]; this
0x1800155ca  call    ??0PropertyStoreHelper@wil@@QEAA@PEAUIPropertyStore@@@Z; wil::PropertyStoreHelper::PropertyStoreHelper(IPropertyStore *)
0x1800155cf  mov     rdx, [rsp+150h+var_118]
0x1800155d4  lea     r9, [rbp+50h+var_D0]
0x1800155d8  lea     rcx, [rsp+150h+var_110]
0x1800155dd  mov     [rsp+150h+var_120], ebx
0x1800155e1  mov     dword ptr [rbp+50h+var_D0], 0DED77B3h
0x1800155e8  mov     dword ptr [rbp+50h+var_D0+4], 456CC614h
0x1800155ef  mov     dword ptr [rbp+50h+var_D0+8], 5B285BAEh
0x1800155f6  mov     dword ptr [rbp+50h+var_D0+0Ch], 1BB0D738h
0x1800155fd  mov     [rbp+50h+var_C0], 6
0x180015604  call    ?InitFromItem@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEAAJPEAUIUnknown@@W4GETPROPERTYSTOREFLAGS@@PEBU_tagpropertykey@@I@Z; wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(IUnknown *,GETPROPERTYSTOREFLAGS,_tagpropertykey const *,uint)
0x180015609  test    eax, eax
0x18001560b  js      short loc_18001563F
0x18001560d  movups  xmm0, cs:PKEY_Launcher_ViewID
0x180015614  mov     eax, cs:dword_18008A698
0x18001561a  lea     r8, [rsp+150h+var_120]
0x18001561f  lea     rdx, [rbp+50h+var_D0]
0x180015623  mov     [rbp+50h+var_C0], eax
0x180015626  lea     rcx, [rsp+150h+var_110]
0x18001562b  movaps  [rbp+50h+var_D0], xmm0
0x18001562f  call    ??$GetUInt32@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEAK@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetUInt32<_tagpropertykey>(_tagpropertykey,ulong *)
0x180015634  test    eax, eax
0x180015636  js      short loc_18001563F
0x180015638  cmp     [rsp+150h+var_120], ebx
0x18001563c  cmovz   ebx, esi
0x18001563f  lea     rcx, [rsp+150h+var_110]
0x180015644  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180015649  lea     rcx, [rsp+150h+var_108]
0x18001564e  mov     [rbp+50h+var_48], ebx
0x180015651  mov     [rbp+50h+var_50], r13d
0x180015655  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001565a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001565e  lea     rdx, [rsp+150h+var_108]; unsigned __int16 **
0x180015663  mov     rcx, rdi; pszItem
0x180015666  mov     [rsp+150h+var_100], rax
0x18001566b  mov     [rsp+150h+var_F8], rax
0x180015670  call    ?GetPackageFullNameFromAppId@@YAJPEBGPEAPEAG@Z; GetPackageFullNameFromAppId(ushort const *,ushort * *)
0x180015675  mov     rdx, [rsp+150h+var_108]; unsigned __int16 *
0x18001567a  lea     rcx, [rbp+50h+var_40]; struct _SQM_STREAM_ENTRY *
0x18001567e  call    ?WinSqmCreateStringStreamEntry@@YAXPEAU_SQM_STREAM_ENTRY@@PEBG@Z; WinSqmCreateStringStreamEntry(_SQM_STREAM_ENTRY *,ushort const *)
0x180015683  lea     rcx, [rsp+150h+var_118]
0x180015688  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18001568d  jmp     short loc_1800156A8
0x18001568f  mov     [rbp+50h+var_68], r12
0x180015693  mov     [rbp+50h+var_70], esi
0x180015696  mov     [rbp+50h+var_48], 0
0x18001569d  mov     [rbp+50h+var_50], r13d
0x1800156a1  mov     [rbp+50h+var_38], r12
0x1800156a5  mov     [rbp+50h+var_40], esi
0x1800156a8  xor     ecx, ecx
0x1800156aa  lea     r9, [rbp+50h+var_B0]
0x1800156ae  mov     edx, 23EFh
0x1800156b3  lea     r8d, [rcx+8]
0x1800156b7  call    cs:__imp_WinSqmAddToStream
0x1800156bd  lea     rcx, [rsp+150h+var_108]
0x1800156c2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800156c7  lea     rcx, [rsp+150h+var_F0]
0x1800156cc  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800156d1  mov     rcx, [rbp+50h+var_30]
0x1800156d5  xor     rcx, rsp; StackCookie
0x1800156d8  call    __security_check_cookie
0x1800156dd  lea     r11, [rsp+150h+var_20]
0x1800156e5  mov     rbx, [r11+30h]
0x1800156e9  mov     rsi, [r11+48h]
0x1800156ed  mov     rsp, r11
0x1800156f0  pop     r14
0x1800156f2  pop     r13
0x1800156f4  pop     r12
0x1800156f6  pop     rdi
0x1800156f7  pop     rbp
0x1800156f8  retn
```
