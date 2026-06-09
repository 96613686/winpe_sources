# SystemSettings::StorageSenseHandlers::CPackageSizeSetting::get_SearchCriteria(HSTRING__ * *)

- ea: `0x18004b9b0`
- end: `0x18004bbc3`
- name: `?get_SearchCriteria@CPackageSizeSetting@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z`
- size: `531`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CPackageSizeSetting *__hidden this, HSTRING *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180049d8c`

## callees

- `0x18000c964`
- `0x18000e6cc`
- `0x18003d3ac`
- `0x18003fe74`
- `0x18004b9b0`
- `0x1800a8fc8`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18004bae9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18004bae9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ba00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ba24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bab4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bad5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bb2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bb5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bb7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bb8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bb99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bba7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ba00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ba24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bab4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bad5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bb2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bb5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bb7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bb8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bb99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004bba7`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SystemSettings::StorageSenseHandlers::CPackageSizeSetting::get_SearchCriteria(
        SystemSettings::StorageSenseHandlers::CAppTileData **this,
        HSTRING *a2)
{
  unsigned int v4; // ebx
  void (__fastcall *v5)(SystemSettings::StorageSenseHandlers::CAppTileData **, HSTRING *); // rbx
  SystemSettings::StorageSenseHandlers::CAppTileData *v6; // rbx
  unsigned int i; // esi
  __int64 v8; // rdi
  int (__fastcall *v9)(__int64, _QWORD, _QWORD *); // rbx
  __int64 v10; // rdi
  int (__fastcall *v11)(__int64, HSTRING *); // rbx
  int v12; // eax
  __int64 v13; // rdx
  HSTRING newString; // [rsp+20h] [rbp-30h] BYREF
  __int64 v16; // [rsp+28h] [rbp-28h] BYREF
  HSTRING v17; // [rsp+30h] [rbp-20h] BYREF
  HSTRING string; // [rsp+38h] [rbp-18h] BYREF
  _QWORD v19[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  unsigned int v21; // [rsp+88h] [rbp+38h] BYREF
  HSTRING v22; // [rsp+90h] [rbp+40h] BYREF
  HSTRING string2; // [rsp+98h] [rbp+48h] BYREF

  string = 0;
  v17 = 0;
  newString = 0;
  string2 = 0;
  v16 = 0;
  v19[0] = 0;
  v21 = 0;
  if ( a2 )
  {
    v5 = (void (__fastcall *)(SystemSettings::StorageSenseHandlers::CAppTileData **, HSTRING *))*((_QWORD *)*this + 11);
    WindowsDeleteString(0);
    v17 = 0;
    v5(this, &v17);
    v6 = this[30];
    WindowsDeleteString(string);
    string = 0;
    SystemSettings::StorageSenseHandlers::CAppTileData::GetPublisher(v6, &string);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v16);
    if ( (int)SystemSettings::StorageSenseHandlers::CPackageSizeSetting::GetDependents(this, &v16) >= 0
      && (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v16 + 56LL))(v16, &v21) >= 0 )
    {
      for ( i = 0; i < v21; ++i )
      {
        v8 = v16;
        v9 = *(int (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v16 + 48LL);
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v19);
        if ( v9(v8, i, v19) >= 0 )
        {
          v10 = v19[0];
          v11 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19[0] + 48LL);
          WindowsDeleteString(string2);
          string2 = 0;
          if ( v11(v10, &string2) >= 0 )
          {
            WindowsDeleteString(newString);
            newString = 0;
            WindowsConcatString(0, string2, &newString);
          }
        }
      }
    }
    v22 = 0;
    v12 = Microsoft::WRL::Wrappers::HString::Concat(
            (Microsoft::WRL::Wrappers::HString *)&v17,
            (const struct Microsoft::WRL::Wrappers::HString *)&string,
            (struct Microsoft::WRL::Wrappers::HString *)&v22);
    v4 = v12;
    if ( v12 >= 0 )
    {
      v12 = Microsoft::WRL::Wrappers::HString::Concat(
              (Microsoft::WRL::Wrappers::HString *)&v22,
              (const struct Microsoft::WRL::Wrappers::HString *)&newString,
              (struct Microsoft::WRL::Wrappers::HString *)&v22);
      v4 = v12;
      if ( v12 >= 0 )
      {
        *a2 = v22;
        WindowsDeleteString(0);
        v4 = 0;
        goto LABEL_16;
      }
      v13 = 2842;
    }
    else
    {
      v13 = 2841;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
      (const char *)(unsigned int)v12,
      (int)newString);
    WindowsDeleteString(v22);
  }
  else
  {
    v4 = -2147024809;
  }
LABEL_16:
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(v19);
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v16);
  WindowsDeleteString(string2);
  string2 = 0;
  WindowsDeleteString(newString);
  newString = 0;
  WindowsDeleteString(v17);
  v17 = 0;
  WindowsDeleteString(string);
  return v4;
}

```

## disassembly

```asm
0x18004b9b0  mov     [rsp-28h+arg_0], rbx
0x18004b9b5  push    rbp
0x18004b9b6  push    rsi
0x18004b9b7  push    rdi
0x18004b9b8  push    r14
0x18004b9ba  push    r15
0x18004b9bc  mov     rbp, rsp
0x18004b9bf  sub     rsp, 50h
0x18004b9c3  mov     r14, rdx
0x18004b9c6  mov     rdi, rcx
0x18004b9c9  xor     r15d, r15d
0x18004b9cc  mov     [rbp+string], r15
0x18004b9d0  mov     [rbp+var_20], r15
0x18004b9d4  mov     [rbp+newString], r15
0x18004b9d8  mov     [rbp+string2], r15
0x18004b9dc  mov     [rbp+var_28], r15
0x18004b9e0  mov     [rbp+var_10], r15
0x18004b9e4  mov     [rbp+arg_8], r15d
0x18004b9e8  test    rdx, rdx
0x18004b9eb  jnz     short loc_18004B9F7
0x18004b9ed  mov     ebx, 80070057h
0x18004b9f2  jmp     loc_18004BB65
0x18004b9f7  mov     rax, [rcx]
0x18004b9fa  mov     rbx, [rax+58h]
0x18004b9fe  xor     ecx, ecx; string
0x18004ba00  call    cs:__imp_WindowsDeleteString
0x18004ba06  mov     [rbp+var_20], r15
0x18004ba0a  lea     rdx, [rbp+var_20]
0x18004ba0e  mov     rcx, rdi
0x18004ba11  mov     rax, rbx
0x18004ba14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ba19  mov     rbx, [rdi+0F0h]
0x18004ba20  mov     rcx, [rbp+string]; string
0x18004ba24  call    cs:__imp_WindowsDeleteString
0x18004ba2a  mov     [rbp+string], r15
0x18004ba2e  lea     rdx, [rbp+string]; HSTRING *
0x18004ba32  mov     rcx, rbx; this
0x18004ba35  call    ?GetPublisher@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetPublisher(HSTRING__ * *)
0x18004ba3a  lea     rcx, [rbp+var_28]
0x18004ba3e  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18004ba43  lea     rdx, [rbp+var_28]
0x18004ba47  mov     rcx, rdi
0x18004ba4a  call    ?GetDependents@CPackageSizeSetting@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAU?$IVectorView@PEAUIPackageInfo@StorageSense@DataModel@SystemSettings@@@Collections@Foundation@Windows@@@Z; SystemSettings::StorageSenseHandlers::CPackageSizeSetting::GetDependents(Windows::Foundation::Collections::IVectorView<SystemSettings::DataModel::StorageSense::IPackageInfo *> * *)
0x18004ba4f  test    eax, eax
0x18004ba51  js      loc_18004BAF6
0x18004ba57  mov     rcx, [rbp+var_28]
0x18004ba5b  mov     rax, [rcx]
0x18004ba5e  lea     rdx, [rbp+arg_8]
0x18004ba62  mov     rax, [rax+38h]
0x18004ba66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ba6b  test    eax, eax
0x18004ba6d  js      loc_18004BAF6
0x18004ba73  mov     esi, r15d
0x18004ba76  cmp     [rbp+arg_8], r15d
0x18004ba7a  jbe     short loc_18004BAF6
0x18004ba7c  mov     rdi, [rbp+var_28]
0x18004ba80  mov     rax, [rdi]
0x18004ba83  mov     rbx, [rax+30h]
0x18004ba87  lea     rcx, [rbp+var_10]
0x18004ba8b  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18004ba90  lea     r8, [rbp+var_10]
0x18004ba94  mov     edx, esi
0x18004ba96  mov     rcx, rdi
0x18004ba99  mov     rax, rbx
0x18004ba9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004baa1  test    eax, eax
0x18004baa3  js      short loc_18004BAEF
0x18004baa5  mov     rdi, [rbp+var_10]
0x18004baa9  mov     rax, [rdi]
0x18004baac  mov     rbx, [rax+30h]
0x18004bab0  mov     rcx, [rbp+string2]; string
0x18004bab4  call    cs:__imp_WindowsDeleteString
0x18004baba  mov     [rbp+string2], r15
0x18004babe  lea     rdx, [rbp+string2]
0x18004bac2  mov     rcx, rdi
0x18004bac5  mov     rax, rbx
0x18004bac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bacd  test    eax, eax
0x18004bacf  js      short loc_18004BAEF
0x18004bad1  mov     rcx, [rbp+newString]; string
0x18004bad5  call    cs:__imp_WindowsDeleteString
0x18004badb  mov     [rbp+newString], r15
0x18004badf  lea     r8, [rbp+newString]; newString
0x18004bae3  mov     rdx, [rbp+string2]; string2
0x18004bae7  xor     ecx, ecx; string1
0x18004bae9  call    cs:__imp_WindowsConcatString
0x18004baef  inc     esi
0x18004baf1  cmp     esi, [rbp+arg_8]
0x18004baf4  jb      short loc_18004BA7C
0x18004baf6  mov     [rbp+arg_10], r15
0x18004bafa  lea     r8, [rbp+arg_10]; struct Microsoft::WRL::Wrappers::HString *
0x18004bafe  lea     rdx, [rbp+string]; struct Microsoft::WRL::Wrappers::HString *
0x18004bb02  lea     rcx, [rbp+var_20]; this
0x18004bb06  call    ?Concat@HString@Wrappers@WRL@Microsoft@@QEBAJAEBV1234@AEAV1234@@Z; Microsoft::WRL::Wrappers::HString::Concat(Microsoft::WRL::Wrappers::HString const &,Microsoft::WRL::Wrappers::HString &)
0x18004bb0b  mov     ebx, eax
0x18004bb0d  test    eax, eax
0x18004bb0f  jns     short loc_18004BB35
0x18004bb11  mov     edx, 0B19h; void *
0x18004bb16  lea     r8, aOnecoreuapShel_29; "onecoreuap\\shell\\coresettinghandlers"...
0x18004bb1d  mov     r9d, eax; char *
0x18004bb20  mov     rcx, [rbp+28h]; this
0x18004bb24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004bb29  mov     rcx, [rbp+arg_10]; string
0x18004bb2d  call    cs:__imp_WindowsDeleteString
0x18004bb33  jmp     short loc_18004BB65
0x18004bb35  lea     r8, [rbp+arg_10]; struct Microsoft::WRL::Wrappers::HString *
0x18004bb39  lea     rdx, [rbp+newString]; struct Microsoft::WRL::Wrappers::HString *
0x18004bb3d  lea     rcx, [rbp+arg_10]; this
0x18004bb41  call    ?Concat@HString@Wrappers@WRL@Microsoft@@QEBAJAEBV1234@AEAV1234@@Z; Microsoft::WRL::Wrappers::HString::Concat(Microsoft::WRL::Wrappers::HString const &,Microsoft::WRL::Wrappers::HString &)
0x18004bb46  mov     ebx, eax
0x18004bb48  test    eax, eax
0x18004bb4a  jns     short loc_18004BB53
0x18004bb4c  mov     edx, 0B1Ah
0x18004bb51  jmp     short loc_18004BB16
0x18004bb53  mov     rax, [rbp+arg_10]
0x18004bb57  mov     [r14], rax
0x18004bb5a  xor     ecx, ecx; string
0x18004bb5c  call    cs:__imp_WindowsDeleteString
0x18004bb62  mov     ebx, r15d
0x18004bb65  lea     rcx, [rbp+var_10]
0x18004bb69  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18004bb6e  nop
0x18004bb6f  lea     rcx, [rbp+var_28]
0x18004bb73  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x18004bb78  nop
0x18004bb79  mov     rcx, [rbp+string2]; string
0x18004bb7d  call    cs:__imp_WindowsDeleteString
0x18004bb83  mov     [rbp+string2], r15
0x18004bb87  mov     rcx, [rbp+newString]; string
0x18004bb8b  call    cs:__imp_WindowsDeleteString
0x18004bb91  mov     [rbp+newString], r15
0x18004bb95  mov     rcx, [rbp+var_20]; string
0x18004bb99  call    cs:__imp_WindowsDeleteString
0x18004bb9f  mov     [rbp+var_20], r15
0x18004bba3  mov     rcx, [rbp+string]; string
0x18004bba7  call    cs:__imp_WindowsDeleteString
0x18004bbad  mov     eax, ebx
0x18004bbaf  mov     rbx, [rsp+50h+arg_0]
0x18004bbb7  add     rsp, 50h
0x18004bbbb  pop     r15
0x18004bbbd  pop     r14
0x18004bbbf  pop     rdi
0x18004bbc0  pop     rsi
0x18004bbc1  pop     rbp
0x18004bbc2  retn
```
