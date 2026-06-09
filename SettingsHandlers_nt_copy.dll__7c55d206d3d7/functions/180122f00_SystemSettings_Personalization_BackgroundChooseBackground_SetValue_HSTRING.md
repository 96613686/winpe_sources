# SystemSettings::Personalization::BackgroundChooseBackground::SetValue(HSTRING__ *)

- ea: `0x180122f00`
- end: `0x18012310d`
- name: `?SetValue@BackgroundChooseBackground@Personalization@SystemSettings@@UEAAJPEAUHSTRING__@@@Z`
- size: `525`
- prototype: `__int64 __fastcall(SystemSettings::Personalization::BackgroundChooseBackground *__hidden this, HSTRING)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180011d7c`
- `0x180019a20`
- `0x1800212b0`
- `0x180021640`
- `0x18004d1ac`
- `0x18005a74c`
- `0x1801159d4`
- `0x180115c00`
- `0x18011846c`
- `0x18011918c`
- `0x18011aec0`
- `0x18011ff3c`
- `0x180122790`
- `0x180122f00`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180122fe2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180122fe2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180122f5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180122fa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801230dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801230f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180122f5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180122fa8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801230dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801230f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180122f3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180122fc2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180122f3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180122fc2`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SystemSettings::Personalization::BackgroundChooseBackground::SetValue(
        SystemSettings::Personalization::BackgroundChooseBackground *this,
        HSTRING a2)
{
  int ResourceStringById; // eax
  unsigned int v4; // edi
  __int64 v5; // rdx
  const WCHAR *StringRawBuffer; // rsi
  HSTRING *v7; // r8
  const WCHAR *v9; // rax
  int v10; // eax
  const char *v11; // r9
  _BYTE *v12; // rdi
  __int64 v13; // rax
  __int64 v14; // rdx
  int bIgnoreCase; // [rsp+20h] [rbp-68h]
  HSTRING string; // [rsp+30h] [rbp-58h] BYREF
  char v17; // [rsp+38h] [rbp-50h]
  _BYTE v18[72]; // [rsp+40h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  HSTRING v20; // [rsp+98h] [rbp+10h] BYREF
  SystemSettings::Personalization::BackgroundChooseBackground *v21; // [rsp+A0h] [rbp+18h] BYREF
  const WCHAR *v22; // [rsp+A8h] [rbp+20h] BYREF

  v20 = a2;
  string = 0;
  v17 = 0;
  ResourceStringById = Microsoft::WRL::Wrappers::HString::Set(&string, &v20);
  v4 = ResourceStringById;
  if ( ResourceStringById < 0 )
  {
    v5 = 419;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\background.cpp",
      (const char *)(unsigned int)ResourceStringById,
      bIgnoreCase);
    WindowsDeleteString(string);
    return v4;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v22 = StringRawBuffer;
  WindowsDeleteString(string);
  string = 0;
  ResourceStringById = SystemSettings::DataModel::GetResourceStringById(off_18038E430, &string, v7);
  v4 = ResourceStringById;
  if ( ResourceStringById < 0 )
  {
    v5 = 422;
    goto LABEL_5;
  }
  v9 = WindowsGetStringRawBuffer(string, 0);
  v10 = CompareStringOrdinal(v9, -1, StringRawBuffer, -1, 1);
  try
  {
    if ( v10 != 2 && IsStickerEditorAppEnabled() && AreStickersOnCurrentWallpaper() )
    {
      v12 = (char *)this + 240;
      *((_BYTE *)this + 240) = 1;
      SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_18030ACF8);
      v13 = _lambda_000a8bc96ba055f799892084a5a64564_::_lambda_000a8bc96ba055f799892084a5a64564_(&v21, this);
      std::function_void___cdecl_void__::operator___lambda_dfcf4b058bef382caaf29b5b3b08e894__0_((char *)this + 312, v13);
    }
    else
    {
      v12 = (char *)this + 240;
      if ( *((_BYTE *)this + 240) )
      {
        *v12 = 0;
        SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_18030ACF8);
      }
    }
  }
  catch ( ... )
  {
    LODWORD(v21) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x1BD,
                     (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\background.cpp",
                     v11);
    WindowsDeleteString(string);
    return (unsigned int)v21;
  }
  v21 = this;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v21);
  v14 = lambda_1023df8925408e7f033a4f0cf7060f7f_::_lambda_1023df8925408e7f033a4f0cf7060f7f_(
          (unsigned int)v18,
          (_DWORD)this,
          (unsigned int)&v22,
          (unsigned int)&v21,
          (__int64)&string);
  std::function_void___cdecl_void__::operator___lambda_1023df8925408e7f033a4f0cf7060f7f__0_((char *)this + 248, v14);
  lambda_1023df8925408e7f033a4f0cf7060f7f_::__lambda_1023df8925408e7f033a4f0cf7060f7f_(v18);
  if ( !*v12 )
    std::_Func_class<void,>::operator()((char *)this + 248);
  (*(void (__fastcall **)(SystemSettings::Personalization::BackgroundChooseBackground *))(*(_QWORD *)this + 16LL))(this);
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x180122f00  mov     rax, rsp
0x180122f03  mov     [rax+10h], rdx
0x180122f07  push    rbx
0x180122f08  push    rsi
0x180122f09  push    rdi
0x180122f0a  sub     rsp, 70h
0x180122f0e  mov     rbx, rcx
0x180122f11  mov     qword ptr [rax-58h], 0
0x180122f19  mov     byte ptr [rax-50h], 0
0x180122f1d  lea     rdx, [rax+10h]; HSTRING *
0x180122f21  lea     rcx, [rax-58h]; newString
0x180122f25  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180122f2a  mov     edi, eax
0x180122f2c  test    eax, eax
0x180122f2e  jns     short loc_180122F37
0x180122f30  mov     edx, 1A3h
0x180122f35  jmp     short loc_180122F8B
0x180122f37  xor     edx, edx; length
0x180122f39  mov     rcx, [rsp+88h+string]; string
0x180122f3e  call    cs:__imp_WindowsGetStringRawBuffer
0x180122f45  nop     dword ptr [rax+rax+00h]
0x180122f4a  mov     rsi, rax
0x180122f4d  mov     [rsp+88h+arg_18], rax
0x180122f55  mov     rcx, [rsp+88h+string]; string
0x180122f5a  call    cs:__imp_WindowsDeleteString
0x180122f61  nop     dword ptr [rax+rax+00h]
0x180122f66  mov     [rsp+88h+string], 0
0x180122f6f  lea     rdx, [rsp+88h+string]; HSTRING *
0x180122f74  mov     rcx, cs:off_18038E430; this
0x180122f7b  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x180122f80  mov     edi, eax
0x180122f82  test    eax, eax
0x180122f84  jns     short loc_180122FBB
0x180122f86  mov     edx, 1A6h; void *
0x180122f8b  mov     r9d, eax; char *
0x180122f8e  lea     r8, aShellSystemset_24; "shell\\systemsettingsthreshold\\handler"...
0x180122f95  mov     rcx, [rsp+88h]; this
0x180122f9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180122fa2  nop
0x180122fa3  mov     rcx, [rsp+88h+string]; string
0x180122fa8  call    cs:__imp_WindowsDeleteString
0x180122faf  nop     dword ptr [rax+rax+00h]
0x180122fb4  mov     eax, edi
0x180122fb6  jmp     loc_180123104
0x180122fbb  xor     edx, edx; length
0x180122fbd  mov     rcx, [rsp+88h+string]; string
0x180122fc2  call    cs:__imp_WindowsGetStringRawBuffer
0x180122fc9  nop     dword ptr [rax+rax+00h]
0x180122fce  mov     [rsp+88h+bIgnoreCase], 1; bIgnoreCase
0x180122fd6  or      edx, 0FFFFFFFFh; cchCount1
0x180122fd9  mov     r9d, edx; cchCount2
0x180122fdc  mov     r8, rsi; lpString2
0x180122fdf  mov     rcx, rax; lpString1
0x180122fe2  call    cs:__imp_CompareStringOrdinal
0x180122fe9  nop     dword ptr [rax+rax+00h]
0x180122fee  cmp     eax, 2
0x180122ff1  jz      short loc_18012303F
0x180122ff3  call    ?IsStickerEditorAppEnabled@@YA_NXZ; IsStickerEditorAppEnabled(void)
0x180122ff8  test    al, al
0x180122ffa  jz      short loc_18012303F
0x180122ffc  call    ?AreStickersOnCurrentWallpaper@@YA_NXZ; AreStickersOnCurrentWallpaper(void)
0x180123001  test    al, al
0x180123003  jz      short loc_18012303F
0x180123005  lea     rdi, [rbx+0F0h]
0x18012300c  mov     byte ptr [rdi], 1
0x18012300f  lea     rdx, stru_18030ACF8; unsigned __int16 *
0x180123016  mov     rcx, rbx; this
0x180123019  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18012301e  mov     rdx, rbx
0x180123021  lea     rcx, [rsp+88h+arg_10]
0x180123029  call    ??0_lambda_000a8bc96ba055f799892084a5a64564_@@QEAA@PEAU?$_Task_impl@V?$cloud_store_data@UMultiTaskOthers@MultiTasking@Settings@Data@Windows@@@wil@@@details@Concurrency@@@Z; _lambda_000a8bc96ba055f799892084a5a64564_::_lambda_000a8bc96ba055f799892084a5a64564_(Concurrency::details::_Task_impl<wil::cloud_store_data<Windows::Data::Settings::MultiTasking::MultiTaskOthers>> *)
0x18012302e  mov     rdx, rax
0x180123031  lea     rcx, [rbx+138h]
0x180123038  call    std__function_void___cdecl_void____operator___lambda_dfcf4b058bef382caaf29b5b3b08e894__0_
0x18012303d  jmp     short loc_18012305E
0x18012303f  lea     rdi, [rbx+0F0h]
0x180123046  cmp     byte ptr [rdi], 0
0x180123049  jz      short loc_18012305E
0x18012304b  mov     byte ptr [rdi], 0
0x18012304e  lea     rdx, stru_18030ACF8; unsigned __int16 *
0x180123055  mov     rcx, rbx; this
0x180123058  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18012305d  nop
0x18012305e  mov     [rsp+88h+arg_10], rbx
0x180123066  lea     rcx, [rsp+88h+arg_10]
0x18012306e  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180123073  nop
0x180123074  lea     rax, [rsp+88h+string]
0x180123079  mov     qword ptr [rsp+88h+bIgnoreCase], rax
0x18012307e  lea     r9, [rsp+88h+arg_10]
0x180123086  lea     r8, [rsp+88h+arg_18]
0x18012308e  mov     rdx, rbx
0x180123091  lea     rcx, [rsp+88h+var_48]
0x180123096  call    _lambda_1023df8925408e7f033a4f0cf7060f7f____lambda_1023df8925408e7f033a4f0cf7060f7f_
0x18012309b  nop
0x18012309c  lea     rsi, [rbx+0F8h]
0x1801230a3  mov     rdx, rax
0x1801230a6  mov     rcx, rsi
0x1801230a9  call    std__function_void___cdecl_void____operator___lambda_1023df8925408e7f033a4f0cf7060f7f__0_
0x1801230ae  nop
0x1801230af  lea     rcx, [rsp+88h+var_48]
0x1801230b4  call    _lambda_1023df8925408e7f033a4f0cf7060f7f_____lambda_1023df8925408e7f033a4f0cf7060f7f_
0x1801230b9  cmp     byte ptr [rdi], 0
0x1801230bc  jnz     short loc_1801230C7
0x1801230be  mov     rcx, rsi
0x1801230c1  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x1801230c6  nop
0x1801230c7  mov     rax, [rbx]
0x1801230ca  mov     rcx, rbx
0x1801230cd  mov     rax, [rax+10h]
0x1801230d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801230d6  nop
0x1801230d7  mov     rcx, [rsp+88h+string]; string
0x1801230dc  call    cs:__imp_WindowsDeleteString
0x1801230e3  nop     dword ptr [rax+rax+00h]
0x1801230e8  xor     eax, eax
0x1801230ea  jmp     short loc_180123104
0x1801230ec  mov     rcx, [rsp+88h+string]; string
0x1801230f1  call    cs:__imp_WindowsDeleteString
0x1801230f8  nop     dword ptr [rax+rax+00h]
0x1801230fd  mov     eax, dword ptr [rsp+88h+arg_10]
0x180123104  add     rsp, 70h
0x180123108  pop     rdi
0x180123109  pop     rsi
0x18012310a  pop     rbx
0x18012310b  retn
```
