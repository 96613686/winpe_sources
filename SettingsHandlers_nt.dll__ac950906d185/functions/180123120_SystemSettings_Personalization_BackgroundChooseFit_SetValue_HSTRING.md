# SystemSettings::Personalization::BackgroundChooseFit::SetValue(HSTRING__ *)

- ea: `0x180123120`
- end: `0x18012334d`
- name: `?SetValue@BackgroundChooseFit@Personalization@SystemSettings@@UEAAJPEAUHSTRING__@@@Z`
- size: `557`
- prototype: `__int64 __fastcall(SystemSettings::Personalization::BackgroundChooseFit *__hidden this, HSTRING)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000c840`
- `0x180011d7c`
- `0x180019a20`
- `0x180021640`
- `0x18004d1ac`
- `0x18005a74c`
- `0x180115a98`
- `0x180115b5c`
- `0x1801184bc`
- `0x1801191d8`
- `0x18011aec0`
- `0x18011ff3c`
- `0x180122790`
- `0x180123120`
- `0x1801992e4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18012321b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18012321b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180123193`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801231e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180123302`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180123317`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180123193`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801231e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180123302`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180123317`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012317a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801231fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012317a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801231fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::Personalization::BackgroundChooseFit::SetValue(
        SystemSettings::Personalization::BackgroundChooseFit *this,
        const WCHAR *a2)
{
  int ResourceStringById; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  const WCHAR *StringRawBuffer; // rsi
  HSTRING *v7; // r8
  const WCHAR *v9; // rax
  int v10; // eax
  struct SystemSettings::DataModel::ISettingItemTelemetry *v11; // r8
  const char *v12; // r9
  _BYTE *v13; // rbx
  __int64 v14; // rax
  __int64 v15; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-78h]
  const WCHAR *v17; // [rsp+30h] [rbp-68h] BYREF
  HSTRING string; // [rsp+38h] [rbp-60h] BYREF
  char v19; // [rsp+40h] [rbp-58h]
  __int128 v20; // [rsp+48h] [rbp-50h] BYREF
  _BYTE v21[40]; // [rsp+58h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v17 = a2;
  string = 0;
  v19 = 0;
  ResourceStringById = Microsoft::WRL::Wrappers::HString::Set(&string, (HSTRING *)&v17);
  v4 = ResourceStringById;
  if ( ResourceStringById < 0 )
  {
    v5 = 947;
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
  v17 = StringRawBuffer;
  WindowsDeleteString(string);
  string = 0;
  ResourceStringById = SystemSettings::DataModel::GetResourceStringById(off_18038E450, &string, v7);
  v4 = ResourceStringById;
  if ( ResourceStringById < 0 )
  {
    v5 = 950;
    goto LABEL_5;
  }
  v9 = WindowsGetStringRawBuffer(string, 0);
  v10 = CompareStringOrdinal(v9, -1, StringRawBuffer, -1, 1);
  try
  {
    if ( v10 != 2 && IsStickerEditorAppEnabled() && AreStickersOnCurrentWallpaper() )
    {
      v13 = (char *)this + 240;
      *((_BYTE *)this + 240) = 1;
      SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_18030ACF8);
      v14 = _lambda_000a8bc96ba055f799892084a5a64564_::_lambda_000a8bc96ba055f799892084a5a64564_(&v20, this);
      std::function_void___cdecl_void__::operator___lambda_a8fdb30c570873ae4409f38d66ea330f__0_((char *)this + 312, v14);
    }
    else
    {
      v13 = (char *)this + 240;
      if ( *((_BYTE *)this + 240) )
      {
        *v13 = 0;
        SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_18030ACF8);
      }
    }
  }
  catch ( ... )
  {
    LODWORD(v17) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x3CD,
                     (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\personalize\\lib\\background.cpp",
                     v12);
    WindowsDeleteString(string);
    return (unsigned int)v17;
  }
  v20 = (__int128)*SystemSettings::Personalization::GetPageSessionId(
                     (SystemSettings::Personalization *)&v20,
                     (struct _GUID *)(((unsigned __int64)this + 16)
                                    & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
                     v11);
  v15 = lambda_6e1d961013e2be11a7e77b87fb390a17_::_lambda_6e1d961013e2be11a7e77b87fb390a17_(v21, &v17, &string, &v20);
  std::function_void___cdecl_void__::operator___lambda_6e1d961013e2be11a7e77b87fb390a17__0_((char *)this + 248, v15);
  lambda_6e1d961013e2be11a7e77b87fb390a17_::__lambda_6e1d961013e2be11a7e77b87fb390a17_(v21);
  if ( !*v13 )
    std::_Func_class<void,>::operator()((char *)this + 248);
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x180123120  mov     r11, rsp
0x180123123  mov     [r11+18h], rbx
0x180123127  mov     [r11+20h], rsi
0x18012312b  push    rdi
0x18012312c  sub     rsp, 90h
0x180123133  mov     rax, cs:__security_cookie
0x18012313a  xor     rax, rsp
0x18012313d  mov     [rsp+98h+var_18], rax
0x180123145  mov     rdi, rcx
0x180123148  mov     [r11-68h], rdx
0x18012314c  mov     qword ptr [r11-60h], 0
0x180123154  mov     [rsp+98h+var_58], 0
0x180123159  lea     rdx, [r11-68h]; HSTRING *
0x18012315d  lea     rcx, [r11-60h]; newString
0x180123161  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180123166  mov     ebx, eax
0x180123168  test    eax, eax
0x18012316a  jns     short loc_180123173
0x18012316c  mov     edx, 3B3h
0x180123171  jmp     short loc_1801231C4
0x180123173  xor     edx, edx; length
0x180123175  mov     rcx, [rsp+98h+string]; string
0x18012317a  call    cs:__imp_WindowsGetStringRawBuffer
0x180123181  nop     dword ptr [rax+rax+00h]
0x180123186  mov     rsi, rax
0x180123189  mov     [rsp+98h+var_68], rax
0x18012318e  mov     rcx, [rsp+98h+string]; string
0x180123193  call    cs:__imp_WindowsDeleteString
0x18012319a  nop     dword ptr [rax+rax+00h]
0x18012319f  mov     [rsp+98h+string], 0
0x1801231a8  lea     rdx, [rsp+98h+string]; HSTRING *
0x1801231ad  mov     rcx, cs:off_18038E450; this
0x1801231b4  call    ?GetResourceStringById@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::GetResourceStringById(ushort const *,HSTRING__ * *)
0x1801231b9  mov     ebx, eax
0x1801231bb  test    eax, eax
0x1801231bd  jns     short loc_1801231F4
0x1801231bf  mov     edx, 3B6h; void *
0x1801231c4  mov     r9d, eax; char *
0x1801231c7  lea     r8, aShellSystemset_24; "shell\\systemsettingsthreshold\\handler"...
0x1801231ce  mov     rcx, [rsp+98h]; this
0x1801231d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801231db  nop
0x1801231dc  mov     rcx, [rsp+98h+string]; string
0x1801231e1  call    cs:__imp_WindowsDeleteString
0x1801231e8  nop     dword ptr [rax+rax+00h]
0x1801231ed  mov     eax, ebx
0x1801231ef  jmp     loc_180123327
0x1801231f4  xor     edx, edx; length
0x1801231f6  mov     rcx, [rsp+98h+string]; string
0x1801231fb  call    cs:__imp_WindowsGetStringRawBuffer
0x180123202  nop     dword ptr [rax+rax+00h]
0x180123207  mov     [rsp+98h+bIgnoreCase], 1; bIgnoreCase
0x18012320f  or      edx, 0FFFFFFFFh; cchCount1
0x180123212  mov     r9d, edx; cchCount2
0x180123215  mov     r8, rsi; lpString2
0x180123218  mov     rcx, rax; lpString1
0x18012321b  call    cs:__imp_CompareStringOrdinal
0x180123222  nop     dword ptr [rax+rax+00h]
0x180123227  cmp     eax, 2
0x18012322a  jz      short loc_180123275
0x18012322c  call    ?IsStickerEditorAppEnabled@@YA_NXZ; IsStickerEditorAppEnabled(void)
0x180123231  test    al, al
0x180123233  jz      short loc_180123275
0x180123235  call    ?AreStickersOnCurrentWallpaper@@YA_NXZ; AreStickersOnCurrentWallpaper(void)
0x18012323a  test    al, al
0x18012323c  jz      short loc_180123275
0x18012323e  lea     rbx, [rdi+0F0h]
0x180123245  mov     byte ptr [rbx], 1
0x180123248  lea     rdx, stru_18030ACF8; unsigned __int16 *
0x18012324f  mov     rcx, rdi; this
0x180123252  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180123257  mov     rdx, rdi
0x18012325a  lea     rcx, [rsp+98h+var_50]
0x18012325f  call    ??0_lambda_000a8bc96ba055f799892084a5a64564_@@QEAA@PEAU?$_Task_impl@V?$cloud_store_data@UMultiTaskOthers@MultiTasking@Settings@Data@Windows@@@wil@@@details@Concurrency@@@Z; _lambda_000a8bc96ba055f799892084a5a64564_::_lambda_000a8bc96ba055f799892084a5a64564_(Concurrency::details::_Task_impl<wil::cloud_store_data<Windows::Data::Settings::MultiTasking::MultiTaskOthers>> *)
0x180123264  mov     rdx, rax
0x180123267  lea     rcx, [rdi+138h]
0x18012326e  call    std__function_void___cdecl_void____operator___lambda_a8fdb30c570873ae4409f38d66ea330f__0_
0x180123273  jmp     short loc_180123294
0x180123275  lea     rbx, [rdi+0F0h]
0x18012327c  cmp     byte ptr [rbx], 0
0x18012327f  jz      short loc_180123294
0x180123281  mov     byte ptr [rbx], 0
0x180123284  lea     rdx, stru_18030ACF8; unsigned __int16 *
0x18012328b  mov     rcx, rdi; this
0x18012328e  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180123293  nop
0x180123294  mov     rax, rdi
0x180123297  lea     rcx, [rdi+10h]
0x18012329b  neg     rax
0x18012329e  sbb     rdx, rdx
0x1801232a1  and     rdx, rcx; retstr
0x1801232a4  lea     rcx, [rsp+98h+var_50]; this
0x1801232a9  call    ?GetPageSessionId@Personalization@SystemSettings@@YA?AU_GUID@@PEAUISettingItemTelemetry@DataModel@2@@Z; SystemSettings::Personalization::GetPageSessionId(SystemSettings::DataModel::ISettingItemTelemetry *)
0x1801232ae  movups  xmm0, xmmword ptr [rax]
0x1801232b1  movdqu  [rsp+98h+var_50], xmm0
0x1801232b7  lea     r9, [rsp+98h+var_50]
0x1801232bc  lea     r8, [rsp+98h+string]
0x1801232c1  lea     rdx, [rsp+98h+var_68]
0x1801232c6  lea     rcx, [rsp+98h+var_40]
0x1801232cb  call    _lambda_6e1d961013e2be11a7e77b87fb390a17____lambda_6e1d961013e2be11a7e77b87fb390a17_
0x1801232d0  nop
0x1801232d1  mov     rdx, rax
0x1801232d4  lea     rcx, [rdi+0F8h]
0x1801232db  call    std__function_void___cdecl_void____operator___lambda_6e1d961013e2be11a7e77b87fb390a17__0_
0x1801232e0  nop
0x1801232e1  lea     rcx, [rsp+98h+var_40]
0x1801232e6  call    _lambda_6e1d961013e2be11a7e77b87fb390a17_____lambda_6e1d961013e2be11a7e77b87fb390a17_
0x1801232eb  cmp     byte ptr [rbx], 0
0x1801232ee  jnz     short loc_1801232FD
0x1801232f0  lea     rcx, [rdi+0F8h]
0x1801232f7  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x1801232fc  nop
0x1801232fd  mov     rcx, [rsp+98h+string]; string
0x180123302  call    cs:__imp_WindowsDeleteString
0x180123309  nop     dword ptr [rax+rax+00h]
0x18012330e  xor     eax, eax
0x180123310  jmp     short loc_180123327
0x180123312  mov     rcx, [rsp+98h+string]; string
0x180123317  call    cs:__imp_WindowsDeleteString
0x18012331e  nop     dword ptr [rax+rax+00h]
0x180123323  mov     eax, dword ptr [rsp+98h+var_68]
0x180123327  mov     rcx, [rsp+98h+var_18]
0x18012332f  xor     rcx, rsp; StackCookie
0x180123332  call    __security_check_cookie
0x180123337  lea     r11, [rsp+98h+var_8]
0x18012333f  mov     rbx, [r11+20h]
0x180123343  mov     rsi, [r11+28h]
0x180123347  mov     rsp, r11
0x18012334a  pop     rdi
0x18012334b  retn
```
