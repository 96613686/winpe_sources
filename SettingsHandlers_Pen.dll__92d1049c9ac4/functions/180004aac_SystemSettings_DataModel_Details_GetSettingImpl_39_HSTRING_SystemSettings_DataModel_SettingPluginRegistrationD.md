# SystemSettings::DataModel::Details::GetSettingImpl<39>(HSTRING__ *,SystemSettings::DataModel::SettingPluginRegistrationData const (&)[39],SystemSettings::DataModel::ISettingItem * *)

- ea: `0x180004aac`
- end: `0x180004c0c`
- name: `??$GetSettingImpl@$0CH@@Details@DataModel@SystemSettings@@YAJPEAUHSTRING__@@AEAY0CH@$$CBUSettingPluginRegistrationData@12@PEAPEAUISettingItem@12@@Z`
- size: `352`
- prototype: `__int64 __fastcall(HSTRING string)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c450`

## callees

- `0x180004aac`
- `0x180008128`
- `0x18000a2e0`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180004ad6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180004b67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180004bc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180004ad6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180004b67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180004bc8`

## string_xrefs

- `0x180004b86`: `onecoreuap\internal\shell\inc\SettingsDBCommonThreshold.h`
- `0x180004bec`: `onecoreuap\internal\shell\inc\SettingsDBCommonThreshold.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::DataModel::Details::GetSettingImpl<39>(HSTRING string, __int64 a2, _QWORD *a3)
{
  PCWSTR StringRawBuffer; // r10
  wchar_t **v6; // rdi
  wchar_t *v7; // r8
  _WORD *v8; // rcx
  wchar_t *v9; // rdx
  wchar_t *v10; // rdi
  __int64 (__fastcall *v11)(wchar_t *, __int64 *); // rbx
  int v12; // ebx
  const char *v13; // rax
  __int64 v14; // rax
  const char *v16; // rax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  UINT32 v18; // [rsp+58h] [rbp+10h] BYREF
  int v19; // [rsp+5Ch] [rbp+14h]
  __int64 v20; // [rsp+60h] [rbp+18h] BYREF

  v19 = HIDWORD(a2);
  *a3 = 0;
  v18 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, &v18);
  v6 = &off_18007B5D0;
  while ( 1 )
  {
    v7 = v6[1];
    if ( (wchar_t *)v18 == v7 )
      break;
LABEL_6:
    v6 += 3;
    if ( v6 == (wchar_t **)&wil::details::g_processLocalData )
      goto LABEL_7;
  }
  v8 = &StringRawBuffer[v18];
  v9 = &(*v6)[(_QWORD)v7];
  while ( v8 != StringRawBuffer )
  {
    if ( *--v8 != *--v9 )
      goto LABEL_6;
  }
LABEL_7:
  if ( v6 == (wchar_t **)&wil::details::g_processLocalData )
  {
    v16 = (const char *)WindowsGetStringRawBuffer(string, 0);
    v12 = -2147024809;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingsDBCommonThreshold.h",
      (const char *)0x80070057LL,
      (int)"%ls",
      v16);
  }
  else
  {
    v10 = v6[2];
    v20 = 0;
    v11 = *(__int64 (__fastcall **)(wchar_t *, __int64 *))(*((_QWORD *)v10 + 5) + 8LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    v12 = v11(v10, &v20);
    if ( v12 >= 0 )
    {
      v14 = v20;
      v20 = 0;
      *a3 = v14;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
      return 0;
    }
    v13 = (const char *)WindowsGetStringRawBuffer(string, 0);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xE1,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\SettingsDBCommonThreshold.h",
      (const char *)(unsigned int)v12,
      (int)"%ls",
      v13);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180004aac  mov     rax, rsp
0x180004aaf  mov     [rax+8], rbx
0x180004ab3  mov     [rax+10h], rdx
0x180004ab7  push    rbp
0x180004ab8  push    rsi
0x180004ab9  push    rdi
0x180004aba  sub     rsp, 30h
0x180004abe  mov     rsi, r8
0x180004ac1  mov     rbp, rcx
0x180004ac4  mov     qword ptr [r8], 0
0x180004acb  mov     dword ptr [rax+10h], 0
0x180004ad2  lea     rdx, [rax+10h]; length
0x180004ad6  call    cs:__imp_WindowsGetStringRawBuffer
0x180004adc  mov     r10, rax
0x180004adf  lea     rdi, off_18007B5D0; "SettingsGroupExpanderPenEnhancedSupport"...
0x180004ae6  mov     r9d, [rsp+48h+arg_8]
0x180004aeb  lea     r11, ?g_processLocalData@details@wil@@3V?$ProcessLocalStorage@UProcessLocalData@details_abi@wil@@@details_abi@2@A; wil::details_abi::ProcessLocalStorage<wil::details_abi::ProcessLocalData> wil::details::g_processLocalData
0x180004af2  mov     r8, [rdi+8]
0x180004af6  cmp     r9, r8
0x180004af9  jnz     short loc_180004B1B
0x180004afb  lea     rcx, [r10+r9*2]
0x180004aff  mov     rdx, [rdi]
0x180004b02  lea     rdx, [rdx+r8*2]
0x180004b06  cmp     rcx, r10
0x180004b09  jz      short loc_180004B24
0x180004b0b  add     rdx, 0FFFFFFFFFFFFFFFEh
0x180004b0f  add     rcx, 0FFFFFFFFFFFFFFFEh
0x180004b13  movzx   eax, word ptr [rdx]
0x180004b16  cmp     [rcx], ax
0x180004b19  jz      short loc_180004B06
0x180004b1b  add     rdi, 18h
0x180004b1f  cmp     rdi, r11
0x180004b22  jnz     short loc_180004AF2
0x180004b24  cmp     rdi, r11
0x180004b27  jz      loc_180004BC3
0x180004b2d  mov     rdi, [rdi+10h]
0x180004b31  mov     [rsp+48h+arg_10], 0
0x180004b3a  mov     rax, [rdi+28h]
0x180004b3e  mov     rbx, [rax+8]
0x180004b42  lea     rcx, [rsp+48h+arg_10]
0x180004b47  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180004b4c  lea     rdx, [rsp+48h+arg_10]
0x180004b51  mov     rcx, rdi
0x180004b54  mov     rax, rbx
0x180004b57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b5c  mov     ebx, eax
0x180004b5e  test    eax, eax
0x180004b60  jns     short loc_180004BA4
0x180004b62  xor     edx, edx; length
0x180004b64  mov     rcx, rbp; string
0x180004b67  call    cs:__imp_WindowsGetStringRawBuffer
0x180004b6d  mov     rcx, [rsp+48h]; this
0x180004b72  mov     [rsp+48h+var_20], rax; char *
0x180004b77  lea     rdx, aLs; "%ls"
0x180004b7e  mov     qword ptr [rsp+48h+var_28], rdx; int
0x180004b83  mov     r9d, ebx; char *
0x180004b86  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180004b8d  mov     edx, 0E1h; void *
0x180004b92  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180004b97  nop
0x180004b98  lea     rcx, [rsp+48h+arg_10]
0x180004b9d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180004ba2  jmp     short loc_180004BFD
0x180004ba4  mov     rax, [rsp+48h+arg_10]
0x180004ba9  mov     [rsp+48h+arg_10], 0
0x180004bb2  mov     [rsi], rax
0x180004bb5  lea     rcx, [rsp+48h+arg_10]
0x180004bba  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180004bbf  xor     eax, eax
0x180004bc1  jmp     short loc_180004BFF
0x180004bc3  xor     edx, edx; length
0x180004bc5  mov     rcx, rbp; string
0x180004bc8  call    cs:__imp_WindowsGetStringRawBuffer
0x180004bce  mov     rcx, [rsp+48h]; this
0x180004bd3  mov     [rsp+48h+var_20], rax; char *
0x180004bd8  lea     rdx, aLs; "%ls"
0x180004bdf  mov     qword ptr [rsp+48h+var_28], rdx; int
0x180004be4  mov     ebx, 80070057h
0x180004be9  mov     r9d, ebx; char *
0x180004bec  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Setti"...
0x180004bf3  mov     edx, 0DCh; void *
0x180004bf8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180004bfd  mov     eax, ebx
0x180004bff  mov     rbx, [rsp+48h+arg_0]
0x180004c04  add     rsp, 30h
0x180004c08  pop     rdi
0x180004c09  pop     rsi
0x180004c0a  pop     rbp
0x180004c0b  retn
```
