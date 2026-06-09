# CSetImageFeedDialog::_PresentDialog(bool *)

- ea: `0x1800ceecc`
- end: `0x1800cf053`
- name: `?_PresentDialog@CSetImageFeedDialog@@AEAAJPEA_N@Z`
- size: `391`
- prototype: `__int64 __fastcall(CSetImageFeedDialog *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800cd160`

## callees

- `0x18003217c`
- `0x180034db4`
- `0x18004d208`
- `0x180050ba0`
- `0x1800cdfe0`
- `0x1800ceecc`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cef35`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cef35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cef1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cef1c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800cef5a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800cef5a`
- `DUI70!UnInitProcessPriv` at `0x1800cf020`
- `DUI70!UnInitProcessPriv` at `0x1800cf020`
- `DUI70!UnInitThread` at `0x1800cf013`
- `DUI70!UnInitThread` at `0x1800cf013`
- `DUI70!StartMessagePump` at `0x1800cf003`
- `DUI70!StartMessagePump` at `0x1800cf003`
- `DUI70!InitThread` at `0x1800cefdb`
- `DUI70!InitThread` at `0x1800cefdb`
- `DUI70!InitProcessPriv` at `0x1800cefaf`
- `DUI70!InitProcessPriv` at `0x1800cefaf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSetImageFeedDialog::_PresentDialog(CSetImageFeedDialog *this, bool *a2)
{
  HSTRING v4; // rbx
  __int64 v5; // r8
  unsigned int v6; // ebx
  int inited; // eax
  __int64 v8; // rdx
  int v10; // [rsp+20h] [rbp-58h]
  _BYTE v11[8]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v12; // [rsp+38h] [rbp-40h] BYREF
  HSTRING string; // [rsp+40h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( a2 )
    *a2 = 0;
  v11[0] = 0;
  v12 = 0;
  if ( WindowsCreateStringReference(L"Windows.Graphics.Holographic.HolographicSpace", 0x2Du, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v4 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
  if ( (int)RoGetActivationFactory(v4, &GUID_0e777088_75fc_48af_8758_0652f6f07c59, &v12) >= 0
    && (*(int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v12 + 56LL))(v12, v11) >= 0
    && v11[0] )
  {
    v6 = CSetImageFeedDialog::CreateAndShowMessageDialog(this, a2);
    goto LABEL_19;
  }
  LOBYTE(v10) = 1;
  LOBYTE(v5) = 1;
  inited = InitProcessPriv(14, &_ImageBase, v5);
  v6 = inited;
  if ( inited < 0 )
  {
    v8 = 293;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\setimagefeeddialog.cpp",
      (const char *)(unsigned int)inited,
      v10);
    goto LABEL_19;
  }
  inited = InitThread(65538);
  v6 = inited;
  if ( inited < 0 )
  {
    v8 = 294;
    goto LABEL_11;
  }
  inited = CSetImageFeedDialog::CreateAndShow(this);
  v6 = inited;
  if ( inited < 0 )
  {
    v8 = 295;
    goto LABEL_11;
  }
  StartMessagePump();
  if ( a2 )
    *a2 = *((_BYTE *)this + 40);
  UnInitThread();
  UnInitProcessPriv(&_ImageBase);
  v6 = 0;
LABEL_19:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
  return v6;
}

```

## disassembly

```asm
0x1800ceecc  mov     [rsp+arg_10], rbx
0x1800ceed1  mov     [rsp+arg_18], rsi
0x1800ceed6  push    rdi
0x1800ceed7  sub     rsp, 70h
0x1800ceedb  mov     rax, cs:__security_cookie
0x1800ceee2  xor     rax, rsp
0x1800ceee5  mov     [rsp+78h+var_18], rax
0x1800ceeea  mov     rdi, rdx
0x1800ceeed  mov     rsi, rcx
0x1800ceef0  test    rdx, rdx
0x1800ceef3  jz      short loc_1800CEEF8
0x1800ceef5  mov     byte ptr [rdx], 0
0x1800ceef8  mov     [rsp+78h+var_48], 0
0x1800ceefd  mov     [rsp+78h+var_40], 0
0x1800cef06  lea     r9, [rsp+78h+string]; string
0x1800cef0b  lea     r8, [rsp+78h+hstringHeader]; hstringHeader
0x1800cef10  mov     edx, 2Dh ; '-'; length
0x1800cef15  lea     rcx, ?RuntimeClass_Windows_Graphics_Holographic_HolographicSpace@@3QBGB; "Windows.Graphics.Holographic.Holographi"...
0x1800cef1c  call    cs:__imp_WindowsCreateStringReference
0x1800cef22  test    eax, eax
0x1800cef24  jns     short loc_1800CEF3C
0x1800cef26  xor     r9d, r9d; lpArguments
0x1800cef29  xor     r8d, r8d; nNumberOfArguments
0x1800cef2c  lea     edx, [r9+1]; dwExceptionFlags
0x1800cef30  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800cef35  call    cs:__imp_RaiseException
0x1800cef3b  nop
0x1800cef3c  mov     rbx, [rsp+78h+string]
0x1800cef41  lea     rcx, [rsp+78h+var_40]
0x1800cef46  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cef4b  lea     r8, [rsp+78h+var_40]
0x1800cef50  lea     rdx, _GUID_0e777088_75fc_48af_8758_0652f6f07c59
0x1800cef57  mov     rcx, rbx
0x1800cef5a  call    cs:__imp_RoGetActivationFactory
0x1800cef60  nop
0x1800cef61  test    eax, eax
0x1800cef63  js      short loc_1800CEF98
0x1800cef65  mov     rcx, [rsp+78h+var_40]
0x1800cef6a  mov     rax, [rcx]
0x1800cef6d  lea     rdx, [rsp+78h+var_48]
0x1800cef72  mov     rax, [rax+38h]
0x1800cef76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cef7b  test    eax, eax
0x1800cef7d  js      short loc_1800CEF98
0x1800cef7f  cmp     [rsp+78h+var_48], 0
0x1800cef84  jz      short loc_1800CEF98
0x1800cef86  mov     rdx, rdi; bool *
0x1800cef89  mov     rcx, rsi; this
0x1800cef8c  call    ?CreateAndShowMessageDialog@CSetImageFeedDialog@@QEAAJPEA_N@Z; CSetImageFeedDialog::CreateAndShowMessageDialog(bool *)
0x1800cef91  mov     ebx, eax
0x1800cef93  jmp     loc_1800CF028
0x1800cef98  mov     byte ptr [rsp+78h+var_58], 1; int
0x1800cef9d  mov     r9b, 1
0x1800cefa0  mov     r8b, r9b
0x1800cefa3  lea     rdx, __ImageBase
0x1800cefaa  mov     ecx, 0Eh
0x1800cefaf  call    cs:__imp_InitProcessPriv
0x1800cefb5  mov     ebx, eax
0x1800cefb7  test    eax, eax
0x1800cefb9  jns     short loc_1800CEFD6
0x1800cefbb  mov     edx, 125h; void *
0x1800cefc0  mov     rcx, [rsp+78h]; this
0x1800cefc5  mov     r9d, eax; char *
0x1800cefc8  lea     r8, aShellWindowsui_1; "shell\\windowsuiimmersive\\userinfo\\se"...
0x1800cefcf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cefd4  jmp     short loc_1800CF028
0x1800cefd6  mov     ecx, 10002h
0x1800cefdb  call    cs:__imp_InitThread
0x1800cefe1  mov     ebx, eax
0x1800cefe3  test    eax, eax
0x1800cefe5  jns     short loc_1800CEFEE
0x1800cefe7  mov     edx, 126h
0x1800cefec  jmp     short loc_1800CEFC0
0x1800cefee  mov     rcx, rsi; this
0x1800ceff1  call    ?CreateAndShow@CSetImageFeedDialog@@QEAAJXZ; CSetImageFeedDialog::CreateAndShow(void)
0x1800ceff6  mov     ebx, eax
0x1800ceff8  test    eax, eax
0x1800ceffa  jns     short loc_1800CF003
0x1800ceffc  mov     edx, 127h
0x1800cf001  jmp     short loc_1800CEFC0
0x1800cf003  call    cs:__imp_StartMessagePump
0x1800cf009  test    rdi, rdi
0x1800cf00c  jz      short loc_1800CF013
0x1800cf00e  mov     al, [rsi+28h]
0x1800cf011  mov     [rdi], al
0x1800cf013  call    cs:__imp_UnInitThread
0x1800cf019  lea     rcx, __ImageBase
0x1800cf020  call    cs:__imp_UnInitProcessPriv
0x1800cf026  xor     ebx, ebx
0x1800cf028  lea     rcx, [rsp+78h+var_40]
0x1800cf02d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cf032  mov     eax, ebx
0x1800cf034  mov     rcx, [rsp+78h+var_18]
0x1800cf039  xor     rcx, rsp; StackCookie
0x1800cf03c  call    __security_check_cookie
0x1800cf041  lea     r11, [rsp+78h+var_8]
0x1800cf046  mov     rbx, [r11+20h]
0x1800cf04a  mov     rsi, [r11+28h]
0x1800cf04e  mov     rsp, r11
0x1800cf051  pop     rdi
0x1800cf052  retn
```
