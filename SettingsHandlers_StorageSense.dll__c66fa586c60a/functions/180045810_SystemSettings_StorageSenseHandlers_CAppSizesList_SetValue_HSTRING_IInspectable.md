# SystemSettings::StorageSenseHandlers::CAppSizesList::SetValue(HSTRING__ *,IInspectable *)

- ea: `0x180045810`
- end: `0x180045981`
- name: `?SetValue@CAppSizesList@StorageSenseHandlers@SystemSettings@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@@Z`
- size: `369`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CAppSizesList *__hidden this, HSTRING, struct IInspectable *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000c964`
- `0x18000e6cc`
- `0x18001f688`
- `0x1800225e0`
- `0x180044d90`
- `0x180045810`
- `0x1800476ec`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800458a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045909`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045931`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800458a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045909`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045931`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppSizesList::SetValue(
        HSTRING *this,
        SystemSettings::DataModel *a2,
        struct IInspectable *a3)
{
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rbx
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  int v11; // eax
  __int64 v12; // rdx
  int v14; // eax
  __int64 v15; // [rsp+20h] [rbp-18h] BYREF
  HSTRING v16; // [rsp+28h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+20h]
  HSTRING string; // [rsp+78h] [rbp+40h] BYREF

  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_18010A0E0, (const unsigned __int16 *)a3) )
  {
    v15 = 0;
    QueryInterface = a3->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v15);
    v7 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, __int64 *))QueryInterface)(
           a3,
           &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62,
           &v15);
    v8 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCC5,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
        (const char *)(unsigned int)v7,
        v15);
LABEL_9:
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v15);
      return v8;
    }
    string = 0;
    v9 = v15;
    v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v15 + 152LL);
    WindowsDeleteString(0);
    string = 0;
    v11 = v10(v9, &string);
    v8 = v11;
    if ( v11 < 0 )
    {
      v12 = 3271;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
        (const char *)(unsigned int)v11,
        v15);
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_9;
    }
    v16 = string;
    v11 = Microsoft::WRL::Wrappers::HString::Set(this + 101, &v16);
    v8 = v11;
    if ( v11 < 0 )
    {
      v12 = 3272;
      goto LABEL_8;
    }
    SystemSettings::StorageSenseHandlers::CAppSizesList::_FilterList((SystemSettings::StorageSenseHandlers::CAppSizesList *)this);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v15);
  }
  else
  {
    v14 = SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::SetValue(
            this,
            a2,
            a3);
    v8 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCCD,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
        (const char *)(unsigned int)v14,
        v15);
      return v8;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180045810  push    rbp
0x180045812  push    rbx
0x180045813  push    rsi
0x180045814  push    rdi
0x180045815  mov     rbp, rsp
0x180045818  sub     rsp, 38h
0x18004581c  mov     rdi, r8
0x18004581f  mov     rbx, rdx
0x180045822  mov     rsi, rcx
0x180045825  lea     rdx, stru_18010A0E0; HSTRING
0x18004582c  mov     rcx, rbx; this
0x18004582f  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180045834  test    al, al
0x180045836  jz      loc_180045953
0x18004583c  mov     [rbp+var_18], 0
0x180045844  mov     rax, [rdi]
0x180045847  mov     rbx, [rax]
0x18004584a  lea     rcx, [rbp+var_18]
0x18004584e  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180045853  lea     r8, [rbp+var_18]
0x180045857  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x18004585e  mov     rcx, rdi
0x180045861  mov     rax, rbx
0x180045864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045869  mov     ebx, eax
0x18004586b  test    eax, eax
0x18004586d  jns     short loc_18004588C
0x18004586f  mov     rcx, [rbp+20h]; this
0x180045873  mov     r9d, eax; char *
0x180045876  lea     r8, aOnecoreuapShel_29; "onecoreuap\\shell\\coresettinghandlers"...
0x18004587d  mov     edx, 0CC5h; void *
0x180045882  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045887  jmp     loc_180045917
0x18004588c  mov     [rbp+string], 0
0x180045894  mov     rdi, [rbp+var_18]
0x180045898  mov     rax, [rdi]
0x18004589b  mov     rbx, [rax+98h]
0x1800458a2  xor     ecx, ecx; string
0x1800458a4  call    cs:__imp_WindowsDeleteString
0x1800458aa  mov     [rbp+string], 0
0x1800458b2  lea     rdx, [rbp+string]
0x1800458b6  mov     rcx, rdi
0x1800458b9  mov     rax, rbx
0x1800458bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800458c1  mov     ebx, eax
0x1800458c3  test    eax, eax
0x1800458c5  jns     short loc_1800458CE
0x1800458c7  mov     edx, 0CC7h
0x1800458cc  jmp     short loc_1800458F1
0x1800458ce  mov     rax, [rbp+string]
0x1800458d2  mov     [rbp+var_10], rax
0x1800458d6  lea     rcx, [rsi+328h]; newString
0x1800458dd  lea     rdx, [rbp+var_10]; HSTRING *
0x1800458e1  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800458e6  mov     ebx, eax
0x1800458e8  test    eax, eax
0x1800458ea  jns     short loc_180045924
0x1800458ec  mov     edx, 0CC8h; void *
0x1800458f1  mov     r9d, eax; char *
0x1800458f4  lea     r8, aOnecoreuapShel_29; "onecoreuap\\shell\\coresettinghandlers"...
0x1800458fb  mov     rcx, [rbp+20h]; this
0x1800458ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045904  nop
0x180045905  mov     rcx, [rbp+string]; string
0x180045909  call    cs:__imp_WindowsDeleteString
0x18004590f  mov     [rbp+string], 0
0x180045917  lea     rcx, [rbp+var_18]
0x18004591b  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180045920  mov     eax, ebx
0x180045922  jmp     short loc_18004594A
0x180045924  mov     rcx, rsi; this
0x180045927  call    ?_FilterList@CAppSizesList@StorageSenseHandlers@SystemSettings@@AEAAJXZ; SystemSettings::StorageSenseHandlers::CAppSizesList::_FilterList(void)
0x18004592c  nop
0x18004592d  mov     rcx, [rbp+string]; string
0x180045931  call    cs:__imp_WindowsDeleteString
0x180045937  mov     [rbp+string], 0
0x18004593f  lea     rcx, [rbp+var_18]
0x180045943  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180045948  xor     eax, eax
0x18004594a  add     rsp, 38h
0x18004594e  pop     rdi
0x18004594f  pop     rsi
0x180045950  pop     rbx
0x180045951  pop     rbp
0x180045952  retn
0x180045953  mov     r8, rdi
0x180045956  mov     rdx, rbx
0x180045959  mov     rcx, rsi
0x18004595c  call    ?SetValue@?$CDataSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@@Z; SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::SetValue(HSTRING__ *,IInspectable *)
0x180045961  mov     ebx, eax
0x180045963  test    eax, eax
0x180045965  jns     short loc_180045948
0x180045967  mov     rcx, [rbp+20h]; this
0x18004596b  mov     r9d, eax; char *
0x18004596e  lea     r8, aOnecoreuapShel_29; "onecoreuap\\shell\\coresettinghandlers"...
0x180045975  mov     edx, 0CCDh; void *
0x18004597a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004597f  jmp     short loc_180045920
```
