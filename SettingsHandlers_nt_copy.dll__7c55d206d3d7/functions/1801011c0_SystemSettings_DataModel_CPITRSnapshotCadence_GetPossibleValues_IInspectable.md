# SystemSettings::DataModel::CPITRSnapshotCadence::GetPossibleValues(IInspectable * *)

- ea: `0x1801011c0`
- end: `0x18010162e`
- name: `?GetPossibleValues@CPITRSnapshotCadence@DataModel@SystemSettings@@UEAAJPEAPEAUIInspectable@@@Z`
- size: `1134`
- prototype: `__int64 __fastcall(SystemSettings::DataModel::CPITRSnapshotCadence *__hidden this, struct IInspectable **)`
- caller_count: `0`
- callee_count: `14`
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
- `0x18004d218`
- `0x1801011c0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010128c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101370`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101397`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801014b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101508`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010153c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010128c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101370`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101397`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801014b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180101508`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010153c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801012d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801013f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801012d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801013f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SystemSettings::DataModel::CPITRSnapshotCadence::GetPossibleValues(
        SystemSettings::DataModel::CPITRSnapshotCadence *this,
        struct IInspectable **a2)
{
  int v4; // r12d
  HSTRING v5; // rax
  __int64 v6; // rdi
  int v7; // ebx
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  char v10; // r14
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
  __int64 v26; // r9
  struct IInspectable **v27; // r8
  int ResourceStringValue; // eax
  int v29; // eax
  HSTRING string; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v32; // [rsp+28h] [rbp-D8h] BYREF
  struct IInspectable *v33; // [rsp+30h] [rbp-D0h] BYREF
  struct IInspectable *v34; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v35[264]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v36[264]; // [rsp+250h] [rbp+150h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4A8h] [rbp+3A8h]

  v4 = 0;
  *a2 = 0;
  v32 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(&v32);
  v32 = 0;
  v5 = (HSTRING)operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
  string = v5;
  v6 = 0;
  if ( v5 )
  {
    v6 = Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>(v5);
    string = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<SystemSettings::Accessibility::CBrailleTableLanguageOutputSetting>::~MakeAllocator<SystemSettings::Accessibility::CBrailleTableLanguageOutputSetting>(&string);
  if ( v6 )
  {
    v7 = 0;
    v32 = v6;
  }
  else
  {
    v7 = -2147024882;
  }
  if ( v7 < 0 )
  {
    v8 = (unsigned int)v7;
    v9 = 669;
LABEL_34:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\pointintimerestore.cpp",
      (const char *)v8,
      (int)string);
    goto LABEL_36;
  }
  if ( *(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 11) + 24LL) + 232LL) )
  {
    v10 = 0;
    while ( 1 )
    {
      WindowsDeleteString(0);
      string = 0;
      ResourceStringById = SystemSettings::DataModel::GetResourceStringById(
                             (SystemSettings::DataModel *)L"SystemSettings_Misc_PointInTimeRestore_SnapshotCadence_HourlyValue",
                             &string,
                             v11);
      v7 = ResourceStringById;
      if ( ResourceStringById < 0 )
        break;
      v13 = dword_180306120[v4];
      v14 = string;
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v16 = StringCchPrintfW(v35, 0x104u, StringRawBuffer, v13);
      v17 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2AC,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\pointintimerestore.cpp",
          (const char *)(unsigned int)v16,
          (int)string);
        goto LABEL_26;
      }
      v34 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
      v18 = SystemSettings::DataModel::PropValueHelper::CreateString(v35, &v34);
      v17 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2B0,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\pointintimerestore.cpp",
          (const char *)(unsigned int)v18,
          (int)string);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
        goto LABEL_26;
      }
      LOBYTE(v19) = 1;
      Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(
        v32,
        0,
        v34,
        v19);
      if ( *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 24LL) + 236LL) == 60 * dword_180306120[v4] )
        v10 = 1;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
      WindowsDeleteString(v14);
      if ( (unsigned int)++v4 >= 5 )
      {
        if ( v10 )
          goto LABEL_32;
        WindowsDeleteString(0);
        string = 0;
        v21 = SystemSettings::DataModel::GetResourceStringById(
                (SystemSettings::DataModel *)L"SystemSettings_Misc_PointInTimeRestore_SnapshotCadence_CustomValue",
                &string,
                v20);
        v7 = v21;
        if ( v21 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2C2,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\pointintimerestore.cpp",
            (const char *)(unsigned int)v21,
            (int)string);
          goto LABEL_28;
        }
        v22 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 11) + 24LL) + 236LL);
        v14 = string;
        v23 = WindowsGetStringRawBuffer(string, 0);
        v24 = StringCchPrintfW(v36, 0x104u, v23, v22);
        v17 = v24;
        if ( v24 >= 0 )
        {
          v33 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
          v25 = SystemSettings::DataModel::PropValueHelper::CreateString(v36, &v33);
          v17 = v25;
          if ( v25 >= 0 )
          {
            LOBYTE(v26) = 1;
            Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(
              v32,
              0,
              v33,
              v26);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
            WindowsDeleteString(v14);
            goto LABEL_32;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2CA,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\pointintimerestore.cpp",
            (const char *)(unsigned int)v25,
            (int)string);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2C6,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\pointintimerestore.cpp",
            (const char *)(unsigned int)v24,
            (int)string);
        }
LABEL_26:
        WindowsDeleteString(v14);
        v7 = v17;
        goto LABEL_36;
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A8,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\pointintimerestore.cpp",
      (const char *)(unsigned int)ResourceStringById,
      (int)string);
LABEL_28:
    WindowsDeleteString(string);
  }
  else
  {
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
    ResourceStringValue = SystemSettings::DataModel::GetResourceStringValue(
                            (SystemSettings::DataModel *)L"SystemSettings_Misc_PointInTimeRestore_SnapshotCadence_DisabledValue",
                            (struct IInspectable **)&string,
                            v27);
    v7 = ResourceStringValue;
    if ( ResourceStringValue >= 0 )
    {
      Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(
        v32,
        0,
        string,
        1);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
LABEL_32:
      v29 = Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>>(
              v32,
              &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
              a2);
      v7 = v29;
      if ( v29 >= 0 )
      {
        v7 = 0;
        goto LABEL_36;
      }
      v8 = (unsigned int)v29;
      v9 = 729;
      goto LABEL_34;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D4,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\restore\\pointintimerestore.cpp",
      (const char *)(unsigned int)ResourceStringValue,
      (int)string);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
  }
LABEL_36:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(&v32);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1801011c0  mov     [rsp-8+arg_10], rbx
0x1801011c5  push    rbp
0x1801011c6  push    rsi
0x1801011c7  push    rdi
0x1801011c8  push    r12
0x1801011ca  push    r13
0x1801011cc  push    r14
0x1801011ce  push    r15
0x1801011d0  lea     rbp, [rsp-370h]
0x1801011d8  sub     rsp, 470h
0x1801011df  mov     rax, cs:__security_cookie
0x1801011e6  xor     rax, rsp
0x1801011e9  mov     [rbp+3A0h+var_40], rax
0x1801011f0  mov     r13, rdx
0x1801011f3  mov     r15, rcx
0x1801011f6  xor     r12d, r12d
0x1801011f9  mov     [rdx], r12
0x1801011fc  mov     [rsp+4A0h+var_478], r12
0x180101201  lea     rcx, [rsp+4A0h+var_478]
0x180101206  call    ?InternalRelease@?$ComPtr@V?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(void)
0x18010120b  mov     [rsp+4A0h+var_478], r12
0x180101210  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180101217  mov     ecx, 0B8h; unsigned __int64
0x18010121c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180101221  mov     [rsp+4A0h+string], rax
0x180101226  mov     edi, r12d
0x180101229  test    rax, rax
0x18010122c  jz      short loc_18010123E
0x18010122e  mov     rcx, rax
0x180101231  call    ??0?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@QEAA@AEBU?$DefaultEqualityPredicate@PEAUIInspectable@@@1234@Upermission@01234@@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>(Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *> const &,Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::permission)
0x180101236  mov     rdi, rax
0x180101239  mov     [rsp+4A0h+string], r12
0x18010123e  lea     rcx, [rsp+4A0h+string]
0x180101243  call    ??1?$MakeAllocator@VCBrailleTableLanguageOutputSetting@Accessibility@SystemSettings@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<SystemSettings::Accessibility::CBrailleTableLanguageOutputSetting>::~MakeAllocator<SystemSettings::Accessibility::CBrailleTableLanguageOutputSetting>(void)
0x180101248  test    rdi, rdi
0x18010124b  jnz     short loc_180101254
0x18010124d  mov     ebx, 8007000Eh
0x180101252  jmp     short loc_18010125C
0x180101254  mov     ebx, r12d
0x180101257  mov     [rsp+4A0h+var_478], rdi
0x18010125c  test    ebx, ebx
0x18010125e  jns     short loc_18010126D
0x180101260  mov     r9d, ebx
0x180101263  mov     edx, 29Dh
0x180101268  jmp     loc_1801015DF
0x18010126d  mov     rax, [r15+58h]
0x180101271  mov     rcx, [rax+18h]
0x180101275  cmp     [rcx+0E8h], r12b
0x18010127c  jz      loc_18010154D
0x180101282  mov     r14b, r12b
0x180101285  mov     esi, 1
0x18010128a  xor     ecx, ecx; string
0x18010128c  call    cs:__imp_WindowsDeleteString
0x180101293  nop     dword ptr [rax+rax+00h]
0x180101298  mov     [rsp+4A0h+string], 0; int
0x1801012a1  lea     rdx, [rsp+4A0h+string]; HSTRING *
0x1801012a6  lea     rcx, aSystemsettings_1072; "SystemSettings_Misc_PointInTimeRestore_"...
0x1801012ad  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x1801012b2  mov     ebx, eax
0x1801012b4  test    eax, eax
0x1801012b6  js      loc_18010151B
0x1801012bc  movsxd  rax, r12d
0x1801012bf  lea     rcx, dword_180306120
0x1801012c6  mov     edi, [rcx+rax*4]
0x1801012c9  xor     edx, edx; length
0x1801012cb  mov     rbx, [rsp+4A0h+string]
0x1801012d0  mov     rcx, rbx; string
0x1801012d3  call    cs:__imp_WindowsGetStringRawBuffer
0x1801012da  nop     dword ptr [rax+rax+00h]
0x1801012df  mov     r9d, edi
0x1801012e2  mov     r8, rax; unsigned __int16 *
0x1801012e5  mov     edx, 104h; unsigned __int64
0x1801012ea  lea     rcx, [rsp+4A0h+var_460]; unsigned __int16 *
0x1801012ef  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801012f4  mov     edi, eax
0x1801012f6  test    eax, eax
0x1801012f8  js      loc_1801014E9
0x1801012fe  mov     [rsp+4A0h+var_468], 0
0x180101307  lea     rcx, [rsp+4A0h+var_468]
0x18010130c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180101311  lea     rdx, [rsp+4A0h+var_468]; struct IInspectable **
0x180101316  lea     rcx, [rsp+4A0h+var_460]; unsigned __int16 *
0x18010131b  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180101320  mov     edi, eax
0x180101322  test    eax, eax
0x180101324  js      loc_1801014C2
0x18010132a  mov     r9b, sil
0x18010132d  mov     r8, [rsp+4A0h+var_468]
0x180101332  xor     edx, edx
0x180101334  mov     rcx, [rsp+4A0h+var_478]
0x180101339  call    ?InsertAtInternal@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUIInspectable@@_N@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(uint,IInspectable *,bool)
0x18010133e  movsxd  rax, r12d
0x180101341  lea     rcx, dword_180306120
0x180101348  imul    edx, [rcx+rax*4], 3Ch ; '<'
0x18010134c  mov     rax, [r15+58h]
0x180101350  mov     rcx, [rax+18h]
0x180101354  movzx   r14d, r14b
0x180101358  cmp     [rcx+0ECh], edx
0x18010135e  cmovz   r14d, esi
0x180101362  lea     rcx, [rsp+4A0h+var_468]
0x180101367  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010136c  nop
0x18010136d  mov     rcx, rbx; string
0x180101370  call    cs:__imp_WindowsDeleteString
0x180101377  nop     dword ptr [rax+rax+00h]
0x18010137c  add     r12d, esi
0x18010137f  cmp     r12d, 5
0x180101383  jb      loc_18010128A
0x180101389  xor     r12d, r12d
0x18010138c  test    r14b, r14b
0x18010138f  jnz     loc_1801015BD
0x180101395  xor     ecx, ecx; string
0x180101397  call    cs:__imp_WindowsDeleteString
0x18010139e  nop     dword ptr [rax+rax+00h]
0x1801013a3  mov     [rsp+4A0h+string], r12; int
0x1801013a8  lea     rdx, [rsp+4A0h+string]; HSTRING *
0x1801013ad  lea     rcx, aSystemsettings_733; "SystemSettings_Misc_PointInTimeRestore_"...
0x1801013b4  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x1801013b9  mov     ebx, eax
0x1801013bb  test    eax, eax
0x1801013bd  jns     short loc_1801013E0
0x1801013bf  mov     rcx, [rbp+3A8h]; this
0x1801013c6  mov     r9d, eax; char *
0x1801013c9  lea     r8, aShellSystemset_19; "shell\\systemsettingsthreshold\\handler"...
0x1801013d0  mov     edx, 2C2h; void *
0x1801013d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801013da  nop
0x1801013db  jmp     loc_180101537
0x1801013e0  mov     rax, [r15+58h]
0x1801013e4  mov     rcx, [rax+18h]
0x1801013e8  mov     edi, [rcx+0ECh]
0x1801013ee  xor     edx, edx; length
0x1801013f0  mov     rbx, [rsp+4A0h+string]
0x1801013f5  mov     rcx, rbx; string
0x1801013f8  call    cs:__imp_WindowsGetStringRawBuffer
0x1801013ff  nop     dword ptr [rax+rax+00h]
0x180101404  mov     r9d, edi
0x180101407  mov     r8, rax; unsigned __int16 *
0x18010140a  mov     edx, 104h; unsigned __int64
0x18010140f  lea     rcx, [rbp+3A0h+var_250]; unsigned __int16 *
0x180101416  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18010141b  mov     edi, eax
0x18010141d  test    eax, eax
0x18010141f  jns     short loc_180101442
0x180101421  mov     rcx, [rbp+3A8h]; this
0x180101428  mov     r9d, eax; char *
0x18010142b  lea     r8, aShellSystemset_19; "shell\\systemsettingsthreshold\\handler"...
0x180101432  mov     edx, 2C6h; void *
0x180101437  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010143c  nop
0x18010143d  jmp     loc_180101505
0x180101442  mov     [rsp+4A0h+var_470], r12
0x180101447  lea     rcx, [rsp+4A0h+var_470]
0x18010144c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180101451  lea     rdx, [rsp+4A0h+var_470]; struct IInspectable **
0x180101456  lea     rcx, [rbp+3A0h+var_250]; unsigned __int16 *
0x18010145d  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x180101462  mov     edi, eax
0x180101464  test    eax, eax
0x180101466  jns     short loc_18010148F
0x180101468  mov     rcx, [rbp+3A8h]; this
0x18010146f  mov     r9d, eax; char *
0x180101472  lea     r8, aShellSystemset_19; "shell\\systemsettingsthreshold\\handler"...
0x180101479  mov     edx, 2CAh; void *
0x18010147e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101483  lea     rcx, [rsp+4A0h+var_470]
0x180101488  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010148d  jmp     short loc_18010143D
0x18010148f  mov     r9b, sil
0x180101492  mov     r8, [rsp+4A0h+var_470]
0x180101497  xor     edx, edx
0x180101499  mov     rcx, [rsp+4A0h+var_478]
0x18010149e  call    ?InsertAtInternal@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUIInspectable@@_N@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(uint,IInspectable *,bool)
0x1801014a3  lea     rcx, [rsp+4A0h+var_470]
0x1801014a8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801014ad  nop
0x1801014ae  mov     rcx, rbx; string
0x1801014b1  call    cs:__imp_WindowsDeleteString
0x1801014b8  nop     dword ptr [rax+rax+00h]
0x1801014bd  jmp     loc_1801015BD
0x1801014c2  mov     rcx, [rbp+3A8h]; this
0x1801014c9  mov     r9d, edi; char *
0x1801014cc  lea     r8, aShellSystemset_19; "shell\\systemsettingsthreshold\\handler"...
0x1801014d3  mov     edx, 2B0h; void *
0x1801014d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801014dd  lea     rcx, [rsp+4A0h+var_468]
0x1801014e2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801014e7  jmp     short loc_180101505
0x1801014e9  mov     rcx, [rbp+3A8h]; this
0x1801014f0  mov     r9d, edi; char *
0x1801014f3  lea     r8, aShellSystemset_19; "shell\\systemsettingsthreshold\\handler"...
0x1801014fa  mov     edx, 2ACh; void *
0x1801014ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101504  nop
0x180101505  mov     rcx, rbx; string
0x180101508  call    cs:__imp_WindowsDeleteString
0x18010150f  nop     dword ptr [rax+rax+00h]
0x180101514  mov     ebx, edi
0x180101516  jmp     loc_1801015F7
0x18010151b  mov     rcx, [rbp+3A8h]; this
0x180101522  mov     r9d, eax; char *
0x180101525  lea     r8, aShellSystemset_19; "shell\\systemsettingsthreshold\\handler"...
0x18010152c  mov     edx, 2A8h; void *
0x180101531  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101536  nop
0x180101537  mov     rcx, [rsp+4A0h+string]; string
0x18010153c  call    cs:__imp_WindowsDeleteString
0x180101543  nop     dword ptr [rax+rax+00h]
0x180101548  jmp     loc_1801015F7
0x18010154d  mov     [rsp+4A0h+string], r12; int
0x180101552  lea     rcx, [rsp+4A0h+string]
0x180101557  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010155c  lea     rdx, [rsp+4A0h+string]; struct IInspectable **
0x180101561  lea     rcx, aSystemsettings_322; "SystemSettings_Misc_PointInTimeRestore_"...
0x180101568  call    ?GetResourceStringValue@DataModel@SystemSettings@@YAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::GetResourceStringValue(ushort const *,IInspectable * *)
0x18010156d  mov     ebx, eax
0x18010156f  test    eax, eax
0x180101571  jns     short loc_18010159B
0x180101573  mov     rcx, [rbp+3A8h]; this
0x18010157a  mov     r9d, eax; char *
0x18010157d  lea     r8, aShellSystemset_19; "shell\\systemsettingsthreshold\\handler"...
0x180101584  mov     edx, 2D4h; void *
0x180101589  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010158e  nop
0x18010158f  lea     rcx, [rsp+4A0h+string]
0x180101594  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180101599  jmp     short loc_1801015F7
0x18010159b  mov     r9d, 1
0x1801015a1  mov     r8, [rsp+4A0h+string]
0x1801015a6  xor     edx, edx
0x1801015a8  mov     rcx, [rsp+4A0h+var_478]
0x1801015ad  call    ?InsertAtInternal@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUIInspectable@@_N@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::InsertAtInternal(uint,IInspectable *,bool)
0x1801015b2  nop
0x1801015b3  lea     rcx, [rsp+4A0h+string]
0x1801015b8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801015bd  mov     r8, r13
0x1801015c0  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x1801015c7  mov     rcx, [rsp+4A0h+var_478]
0x1801015cc  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAUIInspectable@@@234@U?$IObservableVector@PEAUIInspectable@@@234@@23@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@U?$IIterable@PEAUIInspectable@@@234@U?$IObservableVector@PEAUIInspectable@@@234@@23@U?$CloakedIid@UIVersionedVector@Internal@Collections@Foundation@Windows@@@23@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Windows::Foundation::Collections::IVector<IInspectable *>,Windows::Foundation::Collections::IIterable<IInspectable *>,Windows::Foundation::Collections::IObservableVector<IInspectable *>>,Microsoft::WRL::CloakedIid<Windows::Foundation::Collections::Internal::IVersionedVector>,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x1801015d1  mov     ebx, eax
0x1801015d3  test    eax, eax
0x1801015d5  jns     short loc_1801015F4
0x1801015d7  mov     r9d, eax; char *
0x1801015da  mov     edx, 2D9h; void *
0x1801015df  lea     r8, aShellSystemset_19; "shell\\systemsettingsthreshold\\handler"...
0x1801015e6  mov     rcx, [rbp+3A8h]; this
0x1801015ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801015f2  jmp     short loc_1801015F7
0x1801015f4  mov     ebx, r12d
0x1801015f7  lea     rcx, [rsp+4A0h+var_478]
0x1801015fc  call    ?InternalRelease@?$ComPtr@V?$AgileObservableVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileObservableVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>>>::InternalRelease(void)
0x180101601  mov     eax, ebx
0x180101603  mov     rcx, [rbp+3A0h+var_40]
0x18010160a  xor     rcx, rsp; StackCookie
0x18010160d  call    __security_check_cookie
0x180101612  mov     rbx, [rsp+4A0h+arg_10]
0x18010161a  add     rsp, 470h
0x180101621  pop     r15
0x180101623  pop     r14
0x180101625  pop     r13
0x180101627  pop     r12
0x180101629  pop     rdi
0x18010162a  pop     rsi
0x18010162b  pop     rbp
0x18010162c  retn
```
