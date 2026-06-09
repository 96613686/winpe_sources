# SystemSettings::PenSettings::DevicesPenHandwritingFontSwitcher::GetValue(IInspectable * *)

- ea: `0x180015000`
- end: `0x18001511e`
- name: `?GetValue@DevicesPenHandwritingFontSwitcher@PenSettings@SystemSettings@@UEAAJPEAPEAUIInspectable@@@Z`
- size: `286`
- prototype: `int(SystemSettings::PenSettings::DevicesPenHandwritingFontSwitcher *__hidden this, struct IInspectable **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000a2bc`
- `0x180012814`
- `0x180012868`
- `0x180015000`
- `0x18001684c`
- `0x180019a40`
- `0x180019b90`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001504e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001504e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015027`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001510d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015027`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001510d`

## string_xrefs

- `0x18001507d`: `shellcommon\shell\settingshandlers\pen\lib\mischandlers.cpp`
- `0x1800150c7`: `shellcommon\shell\settingshandlers\pen\lib\mischandlers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::PenSettings::DevicesPenHandwritingFontSwitcher::GetValue(
        SystemSettings::PenSettings::DevicesPenHandwritingFontSwitcher *this,
        struct IInspectable **a2)
{
  __int64 v3; // rdi
  int (__fastcall *v4)(__int64, HSTRING *); // rbx
  const WCHAR *StringRawBuffer; // rax
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  __int64 v9; // rdx
  unsigned __int16 *v11[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  HSTRING string; // [rsp+70h] [rbp+28h] BYREF

  string = 0;
  v3 = *((_QWORD *)this + 26);
  v4 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v3 + 72LL);
  WindowsDeleteString(0);
  string = 0;
  if ( v4(v3, &string) < 0
    || (StringRawBuffer = WindowsGetStringRawBuffer(string, 0),
        !(unsigned __int8)SystemSettings::PenSettings::_anonymous_namespace_::IsFontSupported(StringRawBuffer)) )
  {
    memset(v11, 0, 24);
    v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
           v11,
           L"Ink Free",
           -1);
    v7 = v8;
    if ( v8 >= 0 )
    {
      v8 = SystemSettings::DataModel::PropValueHelper::CreateString(v11[0], a2);
      v7 = v8;
      if ( v8 >= 0 )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v11);
        goto LABEL_11;
      }
      v9 = 269;
    }
    else
    {
      v9 = 268;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\mischandlers.cpp",
      (const char *)(unsigned int)v8,
      (int)v11[0]);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v11);
    goto LABEL_12;
  }
  v6 = SystemSettings::DataModel::PropValueHelper::CreateString(string, a2);
  v7 = v6;
  if ( v6 >= 0 )
  {
LABEL_11:
    v7 = 0;
    goto LABEL_12;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x107,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\mischandlers.cpp",
    (const char *)(unsigned int)v6,
    (int)v11[0]);
LABEL_12:
  WindowsDeleteString(string);
  return v7;
}

```

## disassembly

```asm
0x180015000  push    rbp
0x180015002  push    rbx
0x180015003  push    rsi
0x180015004  push    rdi
0x180015005  mov     rbp, rsp
0x180015008  sub     rsp, 48h
0x18001500c  mov     rsi, rdx
0x18001500f  mov     [rbp+string], 0
0x180015017  mov     rdi, [rcx+0D0h]
0x18001501e  mov     rax, [rdi]
0x180015021  mov     rbx, [rax+48h]
0x180015025  xor     ecx, ecx; string
0x180015027  call    cs:__imp_WindowsDeleteString
0x18001502d  mov     [rbp+string], 0
0x180015035  lea     rdx, [rbp+string]
0x180015039  mov     rcx, rdi
0x18001503c  mov     rax, rbx
0x18001503f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015044  test    eax, eax
0x180015046  js      short loc_180015090
0x180015048  xor     edx, edx; length
0x18001504a  mov     rcx, [rbp+string]; string
0x18001504e  call    cs:__imp_WindowsGetStringRawBuffer
0x180015054  mov     rcx, rax; lpString2
0x180015057  call    SystemSettings__PenSettings___anonymous_namespace___IsFontSupported
0x18001505c  test    al, al
0x18001505e  jz      short loc_180015090
0x180015060  mov     rdx, rsi; struct IInspectable **
0x180015063  mov     rcx, [rbp+string]; HSTRING
0x180015067  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x18001506c  mov     ebx, eax
0x18001506e  test    eax, eax
0x180015070  jns     loc_180015107
0x180015076  mov     rcx, [rbp+20h]; this
0x18001507a  mov     r9d, eax; char *
0x18001507d  lea     r8, aShellcommonShe_5; "shellcommon\\shell\\settingshandlers\\p"...
0x180015084  mov     edx, 107h; void *
0x180015089  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001508e  jmp     short loc_180015109
0x180015090  mov     [rbp+var_28], 0
0x180015098  mov     [rbp+var_20], 0
0x1800150a0  mov     [rbp+var_18], 0
0x1800150a8  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800150ac  lea     rdx, aInkFree; "Ink Free"
0x1800150b3  lea     rcx, [rbp+var_28]
0x1800150b7  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800150bc  mov     ebx, eax
0x1800150be  test    eax, eax
0x1800150c0  jns     short loc_1800150E5
0x1800150c2  mov     edx, 10Ch; void *
0x1800150c7  lea     r8, aShellcommonShe_5; "shellcommon\\shell\\settingshandlers\\p"...
0x1800150ce  mov     r9d, eax; char *
0x1800150d1  mov     rcx, [rbp+20h]; this
0x1800150d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800150da  lea     rcx, [rbp+var_28]
0x1800150de  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800150e3  jmp     short loc_180015109
0x1800150e5  mov     rdx, rsi; struct IInspectable **
0x1800150e8  mov     rcx, [rbp+var_28]; unsigned __int16 *
0x1800150ec  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x1800150f1  mov     ebx, eax
0x1800150f3  test    eax, eax
0x1800150f5  jns     short loc_1800150FE
0x1800150f7  mov     edx, 10Dh
0x1800150fc  jmp     short loc_1800150C7
0x1800150fe  lea     rcx, [rbp+var_28]
0x180015102  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180015107  xor     ebx, ebx
0x180015109  mov     rcx, [rbp+string]; string
0x18001510d  call    cs:__imp_WindowsDeleteString
0x180015113  mov     eax, ebx
0x180015115  add     rsp, 48h
0x180015119  pop     rdi
0x18001511a  pop     rsi
0x18001511b  pop     rbx
0x18001511c  pop     rbp
0x18001511d  retn
```
