# SystemSettings::DataModel::CPITRSnapshotRetention::GetPossibleValues(IInspectable * *)

- ea: `0x180101640`
- end: `0x180101a38`
- name: `?GetPossibleValues@CPITRSnapshotRetention@DataModel@SystemSettings@@UEAAJPEAPEAUIInspectable@@@Z`
- size: `1016`
- prototype: `__int64 __fastcall(SystemSettings::DataModel::CPITRSnapshotRetention *__hidden this, struct IInspectable **)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000c840`
- `0x18001098c`
- `0x180011bb0`
- `0x180019a20`
- `0x18001a64c`
- `0x18001f3c8`
- `0x1800201c4`
- `0x1800251ec`
- `0x18002b5f0`
- `0x18003cdf0`
- `0x18003d280`
- `0x18004d1ac`
- `0x180101640`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801016fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801017dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101801`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101926`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801019c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801019f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801016fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801017dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101801`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101926`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801019c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801019f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010173e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180101866`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010173e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180101866`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::DataModel::CPITRSnapshotRetention::GetPossibleValues(
        SystemSettings::DataModel::CPITRSnapshotRetention *this,
        struct IInspectable **a2)
{
  HSTRING v4; // rax
  __int64 v5; // rdi
  int v6; // ebx
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  char v9; // si
  signed int i; // r14d
  HSTRING *v11; // r8
  int ResourceStringById; // eax
  unsigned int v13; // edi
  HSTRING v14; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  int v16; // eax
  int v17; // edi
  int v18; // eax
  __int64 v19; // r9
  HSTRING *v20; // r8
  int v21; // eax
  unsigned int v22; // edi
  const unsigned __int16 *v23; // rax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  HSTRING string; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v29; // [rsp+28h] [rbp-D8h] BYREF
  struct IInspectable *v30; // [rsp+30h] [rbp-D0h] BYREF
  struct IInspectable *v31; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v32[264]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v33[264]; // [rsp+250h] [rbp+150h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4A8h] [rbp+3A8h]

  *a2 = 0;
  v29 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(&v29);
  v29 = 0;
  v4 = (HSTRING)operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
  string = v4;
  v5 = 0;
  if ( v4 )
  {
    v5 = Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>(v4);
    string = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<SystemSettings::Accessibility::CBrailleTableLanguageOutputSetting>::~MakeAllocator<SystemSettings::Accessibility::CBrailleTableLanguageOutputSetting>(&string);
  if ( v5 )
  {
    v6 = 0;
    v29 = v5;
  }
  else
  {
    v6 = -2147024882;
  }
  if ( v6 >= 0 )
  {
    v9 = 0;
    for ( i = 0; (unsigned int)i < 5; ++i )
    {
      WindowsDeleteString(0);
      string = 0;
      ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                             (SystemSettings::DataModel *)L"SystemSettings_Misc_PointInTimeRestore_SnapshotRetention_HourlyValue",
                             &string,
                             v11);
      v6 = ResourceStringById;
      if ( ResourceStringById < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3B7,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\pointintimerestore.cpp",
          (const char *)(unsigned int)ResourceStringById,
          (int)string);
LABEL_31:
        WindowsDeleteString(string);
        goto LABEL_32;
      }
      v13 = dword_180306138[i];
      v14 = string;
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v16 = StringCchPrintfW(v32, 0x104u, StringRawBuffer, v13);
      v17 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3BB,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\pointintimerestore.cpp",
          (const char *)(unsigned int)v16,
          (int)string);
        goto LABEL_29;
      }
      v31 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
      v18 = SystemSettings::DataModel::PropValueHelper::CreateString(v32, &v31);
      v17 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3BF,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\pointintimerestore.cpp",
          (const char *)(unsigned int)v18,
          (int)string);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
        goto LABEL_29;
      }
      LOBYTE(v19) = 1;
      Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(
        v29,
        0,
        v31,
        v19);
      if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 24LL) + 244LL) == 60 * dword_180306138[i] )
        v9 = 1;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
      WindowsDeleteString(v14);
    }
    if ( !v9 )
    {
      WindowsDeleteString(0);
      string = 0;
      v21 = SystemSettings::DataModel::GetResourceStringById(
              (SystemSettings::DataModel *)L"SystemSettings_Misc_PointInTimeRestore_SnapshotRetention_DisabledValue",
              &string,
              v20);
      v6 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3D1,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\pointintimerestore.cpp",
          (const char *)(unsigned int)v21,
          (int)string);
        goto LABEL_31;
      }
      v22 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 24LL) + 244LL);
      v14 = string;
      v23 = WindowsGetStringRawBuffer(string, 0);
      v24 = StringCchPrintfW(v33, 0x104u, v23, v22);
      v17 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3D5,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\pointintimerestore.cpp",
          (const char *)(unsigned int)v24,
          (int)string);
LABEL_29:
        WindowsDeleteString(v14);
        v6 = v17;
        goto LABEL_32;
      }
      v30 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
      v25 = SystemSettings::DataModel::PropValueHelper::CreateString(v33, &v30);
      v17 = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3D9,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\pointintimerestore.cpp",
          (const char *)(unsigned int)v25,
          (int)string);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
        goto LABEL_29;
      }
      Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(
        v29,
        0,
        v30,
        1);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
      WindowsDeleteString(v14);
    }
    v26 = Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>>(
            v29,
            &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
            a2);
    v6 = v26;
    if ( v26 < 0 )
    {
      v7 = (unsigned int)v26;
      v8 = 992;
      goto LABEL_25;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(&v29);
    return 0;
  }
  else
  {
    v7 = (unsigned int)v6;
    v8 = 942;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\pointintimerestore.cpp",
      (const char *)v7,
      (int)string);
LABEL_32:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(&v29);
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x180101640  mov     [rsp-8+arg_10], rbx
0x180101645  push    rbp
0x180101646  push    rsi
0x180101647  push    rdi
0x180101648  push    r12
0x18010164a  push    r13
0x18010164c  push    r14
0x18010164e  push    r15
0x180101650  lea     rbp, [rsp-370h]
0x180101658  sub     rsp, 470h
0x18010165f  mov     rax, cs:__security_cookie
0x180101666  xor     rax, rsp
0x180101669  mov     [rbp+3A0h+var_40], rax
0x180101670  mov     r15, rdx
0x180101673  mov     r13, rcx
0x180101676  xor     r12d, r12d
0x180101679  mov     [rdx], r12
0x18010167c  mov     [rsp+4A0h+var_478], r12
0x180101681  lea     rcx, [rsp+4A0h+var_478]
0x180101686  call    ?InternalRelease@?$ComPtr@V?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(void)
0x18010168b  mov     [rsp+4A0h+var_478], r12
0x180101690  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180101697  mov     ecx, 0B8h; unsigned __int64
0x18010169c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1801016a1  mov     [rsp+4A0h+string], rax
0x1801016a6  mov     edi, r12d
0x1801016a9  test    rax, rax
0x1801016ac  jz      short loc_1801016BE
0x1801016ae  mov     rcx, rax
0x1801016b1  call    ??0?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@QEAA@AEBU?$DefaultEqualityPredicate@PEAUIInspectable@@@1234@Upermission@01234@@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>(Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *> const &,Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::permission)
0x1801016b6  mov     rdi, rax
0x1801016b9  mov     [rsp+4A0h+string], r12
0x1801016be  lea     rcx, [rsp+4A0h+string]
0x1801016c3  call    ??1?$MakeAllocator@VCBrailleTableLanguageOutputSetting@Accessibility@SystemSettings@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<SystemSettings::Accessibility::CBrailleTableLanguageOutputSetting>::~MakeAllocator<SystemSettings::Accessibility::CBrailleTableLanguageOutputSetting>(void)
0x1801016c8  test    rdi, rdi
0x1801016cb  jnz     short loc_1801016D4
0x1801016cd  mov     ebx, 8007000Eh
0x1801016d2  jmp     short loc_1801016DC
0x1801016d4  mov     ebx, r12d
0x1801016d7  mov     [rsp+4A0h+var_478], rdi
0x1801016dc  test    ebx, ebx
0x1801016de  jns     short loc_1801016ED
0x1801016e0  mov     r9d, ebx
0x1801016e3  mov     edx, 3AEh
0x1801016e8  jmp     loc_180101954
0x1801016ed  mov     sil, r12b
0x1801016f0  mov     r14d, r12d
0x1801016f3  jmp     short loc_1801016F8
0x1801016f5  xor     r12d, r12d
0x1801016f8  xor     ecx, ecx; string
0x1801016fa  call    cs:__imp_WindowsDeleteString
0x180101701  nop     dword ptr [rax+rax+00h]
0x180101706  mov     [rsp+4A0h+string], r12; int
0x18010170b  lea     rdx, [rsp+4A0h+string]; HSTRING *
0x180101710  lea     rcx, aSystemsettings_1241; "SystemSettings_Misc_PointInTimeRestore_"...
0x180101717  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x18010171c  mov     ebx, eax
0x18010171e  test    eax, eax
0x180101720  js      loc_1801019D3
0x180101726  movsxd  r12, r14d
0x180101729  lea     rax, dword_180306138
0x180101730  mov     edi, [rax+r12*4]
0x180101734  xor     edx, edx; length
0x180101736  mov     rbx, [rsp+4A0h+string]
0x18010173b  mov     rcx, rbx; string
0x18010173e  call    cs:__imp_WindowsGetStringRawBuffer
0x180101745  nop     dword ptr [rax+rax+00h]
0x18010174a  mov     r9d, edi
0x18010174d  mov     r8, rax; unsigned __int16 *
0x180101750  mov     edx, 104h; unsigned __int64
0x180101755  lea     rcx, [rsp+4A0h+var_460]; unsigned __int16 *
0x18010175a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18010175f  mov     edi, eax
0x180101761  test    eax, eax
0x180101763  js      loc_1801019A4
0x180101769  mov     [rsp+4A0h+var_468], 0
0x180101772  lea     rcx, [rsp+4A0h+var_468]
0x180101777  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010177c  lea     rdx, [rsp+4A0h+var_468]; struct IInspectable **
0x180101781  lea     rcx, [rsp+4A0h+var_460]; unsigned __int16 *
0x180101786  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x18010178b  mov     edi, eax
0x18010178d  test    eax, eax
0x18010178f  js      loc_18010197D
0x180101795  mov     edi, 1
0x18010179a  mov     r9b, dil
0x18010179d  mov     r8, [rsp+4A0h+var_468]
0x1801017a2  xor     edx, edx
0x1801017a4  mov     rcx, [rsp+4A0h+var_478]
0x1801017a9  call    ?InsertAtInternal@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUIInspectable@@_N@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(uint,IInspectable *,bool)
0x1801017ae  lea     rax, dword_180306138
0x1801017b5  imul    edx, [rax+r12*4], 3Ch ; '<'
0x1801017ba  mov     rax, [r13+58h]
0x1801017be  mov     rcx, [rax+18h]
0x1801017c2  movzx   esi, sil
0x1801017c6  cmp     [rcx+0F4h], edx
0x1801017cc  cmovz   esi, edi
0x1801017cf  lea     rcx, [rsp+4A0h+var_468]
0x1801017d4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801017d9  nop
0x1801017da  mov     rcx, rbx; string
0x1801017dd  call    cs:__imp_WindowsDeleteString
0x1801017e4  nop     dword ptr [rax+rax+00h]
0x1801017e9  add     r14d, edi
0x1801017ec  cmp     r14d, 5
0x1801017f0  jb      loc_1801016F5
0x1801017f6  test    sil, sil
0x1801017f9  jnz     loc_180101932
0x1801017ff  xor     ecx, ecx; string
0x180101801  call    cs:__imp_WindowsDeleteString
0x180101808  nop     dword ptr [rax+rax+00h]
0x18010180d  mov     [rsp+4A0h+string], 0; int
0x180101816  lea     rdx, [rsp+4A0h+string]; HSTRING *
0x18010181b  lea     rcx, aSystemsettings_1182; "SystemSettings_Misc_PointInTimeRestore_"...
0x180101822  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180101827  mov     ebx, eax
0x180101829  test    eax, eax
0x18010182b  jns     short loc_18010184E
0x18010182d  mov     rcx, [rbp+3A8h]; this
0x180101834  mov     r9d, eax; char *
0x180101837  lea     r8, aShellSystemset_19; "shell\\systemsettingsthreshold\\handler"...
0x18010183e  mov     edx, 3D1h; void *
0x180101843  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101848  nop
0x180101849  jmp     loc_1801019EF
0x18010184e  mov     rax, [r13+58h]
0x180101852  mov     rcx, [rax+18h]
0x180101856  mov     edi, [rcx+0F4h]
0x18010185c  xor     edx, edx; length
0x18010185e  mov     rbx, [rsp+4A0h+string]
0x180101863  mov     rcx, rbx; string
0x180101866  call    cs:__imp_WindowsGetStringRawBuffer
0x18010186d  nop     dword ptr [rax+rax+00h]
0x180101872  mov     r9d, edi
0x180101875  mov     r8, rax; unsigned __int16 *
0x180101878  mov     edx, 104h; unsigned __int64
0x18010187d  lea     rcx, [rbp+3A0h+var_250]; unsigned __int16 *
0x180101884  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180101889  mov     edi, eax
0x18010188b  test    eax, eax
0x18010188d  jns     short loc_1801018B0
0x18010188f  mov     rcx, [rbp+3A8h]; this
0x180101896  mov     r9d, eax; char *
0x180101899  lea     r8, aShellSystemset_19; "shell\\systemsettingsthreshold\\handler"...
0x1801018a0  mov     edx, 3D5h; void *
0x1801018a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801018aa  nop
0x1801018ab  jmp     loc_1801019C0
0x1801018b0  mov     [rsp+4A0h+var_470], 0
0x1801018b9  lea     rcx, [rsp+4A0h+var_470]
0x1801018be  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801018c3  lea     rdx, [rsp+4A0h+var_470]; struct IInspectable **
0x1801018c8  lea     rcx, [rbp+3A0h+var_250]; unsigned __int16 *
0x1801018cf  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x1801018d4  mov     edi, eax
0x1801018d6  test    eax, eax
0x1801018d8  jns     short loc_180101901
0x1801018da  mov     rcx, [rbp+3A8h]; this
0x1801018e1  mov     r9d, eax; char *
0x1801018e4  lea     r8, aShellSystemset_19; "shell\\systemsettingsthreshold\\handler"...
0x1801018eb  mov     edx, 3D9h; void *
0x1801018f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801018f5  lea     rcx, [rsp+4A0h+var_470]
0x1801018fa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801018ff  jmp     short loc_1801018AB
0x180101901  mov     r9d, 1
0x180101907  mov     r8, [rsp+4A0h+var_470]
0x18010190c  xor     edx, edx
0x18010190e  mov     rcx, [rsp+4A0h+var_478]
0x180101913  call    ?InsertAtInternal@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUIInspectable@@_N@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(uint,IInspectable *,bool)
0x180101918  lea     rcx, [rsp+4A0h+var_470]
0x18010191d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180101922  nop
0x180101923  mov     rcx, rbx; string
0x180101926  call    cs:__imp_WindowsDeleteString
0x18010192d  nop     dword ptr [rax+rax+00h]
0x180101932  mov     r8, r15
0x180101935  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x18010193c  mov     rcx, [rsp+4A0h+var_478]
0x180101941  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAUIInspectable@@@234@U?$IObservableVector@PEAUIInspectable@@@234@@23@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAUIInspectable@@@234@U?$IObservableVector@PEAUIInspectable@@@234@@23@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x180101946  mov     ebx, eax
0x180101948  test    eax, eax
0x18010194a  jns     short loc_18010196C
0x18010194c  mov     r9d, eax; char *
0x18010194f  mov     edx, 3E0h; void *
0x180101954  lea     r8, aShellSystemset_19; "shell\\systemsettingsthreshold\\handler"...
0x18010195b  mov     rcx, [rbp+3A8h]; this
0x180101962  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101967  jmp     loc_180101A01
0x18010196c  lea     rcx, [rsp+4A0h+var_478]
0x180101971  call    ?InternalRelease@?$ComPtr@V?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(void)
0x180101976  xor     eax, eax
0x180101978  jmp     loc_180101A0D
0x18010197d  mov     rcx, [rbp+3A8h]; this
0x180101984  mov     r9d, edi; char *
0x180101987  lea     r8, aShellSystemset_19; "shell\\systemsettingsthreshold\\handler"...
0x18010198e  mov     edx, 3BFh; void *
0x180101993  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101998  lea     rcx, [rsp+4A0h+var_468]
0x18010199d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801019a2  jmp     short loc_1801019C0
0x1801019a4  mov     rcx, [rbp+3A8h]; this
0x1801019ab  mov     r9d, edi; char *
0x1801019ae  lea     r8, aShellSystemset_19; "shell\\systemsettingsthreshold\\handler"...
0x1801019b5  mov     edx, 3BBh; void *
0x1801019ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801019bf  nop
0x1801019c0  mov     rcx, rbx; string
0x1801019c3  call    cs:__imp_WindowsDeleteString
0x1801019ca  nop     dword ptr [rax+rax+00h]
0x1801019cf  mov     ebx, edi
0x1801019d1  jmp     short loc_180101A01
0x1801019d3  mov     rcx, [rbp+3A8h]; this
0x1801019da  mov     r9d, ebx; char *
0x1801019dd  lea     r8, aShellSystemset_19; "shell\\systemsettingsthreshold\\handler"...
0x1801019e4  mov     edx, 3B7h; void *
0x1801019e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801019ee  nop
0x1801019ef  mov     rcx, [rsp+4A0h+string]; string
0x1801019f4  call    cs:__imp_WindowsDeleteString
0x1801019fb  nop     dword ptr [rax+rax+00h]
0x180101a00  nop
0x180101a01  lea     rcx, [rsp+4A0h+var_478]
0x180101a06  call    ?InternalRelease@?$ComPtr@V?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(void)
0x180101a0b  mov     eax, ebx
0x180101a0d  mov     rcx, [rbp+3A0h+var_40]
0x180101a14  xor     rcx, rsp; StackCookie
0x180101a17  call    __security_check_cookie
0x180101a1c  mov     rbx, [rsp+4A0h+arg_10]
0x180101a24  add     rsp, 470h
0x180101a2b  pop     r15
0x180101a2d  pop     r14
0x180101a2f  pop     r13
0x180101a31  pop     r12
0x180101a33  pop     rdi
0x180101a34  pop     rsi
0x180101a35  pop     rbp
0x180101a36  retn
```
