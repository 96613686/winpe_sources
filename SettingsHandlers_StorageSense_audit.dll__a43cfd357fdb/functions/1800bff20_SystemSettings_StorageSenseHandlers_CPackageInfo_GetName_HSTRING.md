# SystemSettings::StorageSenseHandlers::CPackageInfo::GetName(HSTRING__ * *)

- ea: `0x1800bff20`
- end: `0x1800c0219`
- name: `?GetName@CPackageInfo@StorageSenseHandlers@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `761`
- prototype: `int(SystemSettings::StorageSenseHandlers::CPackageInfo *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180006e50`
- `0x18000c964`
- `0x18000e6cc`
- `0x180036c38`
- `0x1800a01b0`
- `0x1800be1a8`
- `0x1800be3d4`
- `0x1800bff20`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c01de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800c01de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0052`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0135`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c019b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c01d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0052`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c0135`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c019b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c01d2`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SystemSettings::StorageSenseHandlers::CPackageInfo::GetName(
        SystemSettings::StorageSenseHandlers::CPackageInfo *this,
        HSTRING *a2)
{
  HRESULT v4; // ebx
  __int64 v5; // rdx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, __int64 *); // rbx
  int v9; // eax
  HSTRING *v10; // rsi
  __int64 (__fastcall *v11)(SystemSettings::StorageSenseHandlers::CPackageInfo *, HSTRING *); // rbx
  int v12; // eax
  const unsigned __int16 *v13; // rdx
  __int64 v14; // rdx
  _QWORD *v15; // rax
  const unsigned __int16 *v16; // rdx
  _QWORD *v17; // rax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, _QWORD, HSTRING, __int64 *); // rbx
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, char *); // rbx
  int v22; // [rsp+20h] [rbp-39h]
  __int64 v23; // [rsp+30h] [rbp-29h] BYREF
  int v24; // [rsp+38h] [rbp-21h] BYREF
  HSTRING string; // [rsp+40h] [rbp-19h] BYREF
  __int64 v26; // [rsp+48h] [rbp-11h] BYREF
  __int64 v27; // [rsp+50h] [rbp-9h] BYREF
  __int64 v28; // [rsp+58h] [rbp-1h] BYREF
  HSTRING v29[4]; // [rsp+60h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  *a2 = 0;
  v24 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 4) + 56LL))(*((_QWORD *)this + 4), &v24);
  if ( v4 < 0 )
  {
    v5 = 309;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appinfo.cpp",
      (const char *)(unsigned int)v4,
      v22);
    return (unsigned int)v4;
  }
  if ( v24 == 1 )
  {
    v23 = 0;
    v7 = *((_QWORD *)this + 4);
    v8 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v7 + 48LL);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v23);
    v9 = v8(v7, 0, &v23);
    v4 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13B,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appinfo.cpp",
        (const char *)(unsigned int)v9,
        v22);
LABEL_10:
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v23);
      return (unsigned int)v4;
    }
    if ( (*(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v23 + 48LL))(v23, a2) >= 0 )
    {
      v4 = 0;
      goto LABEL_10;
    }
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v23);
  }
  v10 = (HSTRING *)((char *)this + 40);
  if ( !*((_QWORD *)this + 5) )
  {
    string = 0;
    v28 = 0;
    v23 = 0;
    v27 = 0;
    v26 = 0;
    v11 = *(__int64 (__fastcall **)(SystemSettings::StorageSenseHandlers::CPackageInfo *, HSTRING *))(*(_QWORD *)this + 80LL);
    WindowsDeleteString(0);
    string = 0;
    v12 = v11(this, &string);
    v4 = v12;
    if ( v12 < 0 )
    {
      v14 = 331;
LABEL_25:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appinfo.cpp",
        (const char *)(unsigned int)v12,
        v22);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v26);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v27);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v23);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v28);
      WindowsDeleteString(string);
      return (unsigned int)v4;
    }
    v15 = (_QWORD *)Windows::Internal::StringReference::StringReference(v29, (const unsigned __int16 (*)[41])v13);
    v12 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(
            *v15,
            &v28);
    v4 = v12;
    if ( v12 < 0 )
    {
      v14 = 333;
      goto LABEL_25;
    }
    v17 = (_QWORD *)Windows::Internal::StringReference::StringReference(v29, (const unsigned __int16 (*)[57])v16);
    v12 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageResourceResolverStatics>>(
            *v17,
            &v27);
    v4 = v12;
    if ( v12 < 0 )
    {
      v14 = 334;
      goto LABEL_25;
    }
    v18 = v28;
    v19 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, __int64 *))(*(_QWORD *)v28 + 368LL);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v23);
    v12 = v19(v18, 0, string, &v23);
    v4 = v12;
    if ( v12 < 0 )
    {
      v14 = 336;
      goto LABEL_25;
    }
    v12 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v27 + 48LL))(v27, v23, &v26);
    v4 = v12;
    if ( v12 < 0 )
    {
      v14 = 338;
      goto LABEL_25;
    }
    v20 = v26;
    v21 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v26 + 48LL);
    WindowsDeleteString(*v10);
    *v10 = 0;
    v12 = v21(v20, (char *)this + 40);
    v4 = v12;
    if ( v12 < 0 )
    {
      v14 = 339;
      goto LABEL_25;
    }
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v26);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v27);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v23);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v28);
    WindowsDeleteString(string);
  }
  v4 = WindowsDuplicateString(*v10, a2);
  if ( v4 < 0 )
  {
    v5 = 342;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x1800bff20  mov     [rsp-8+arg_10], rbx
0x1800bff25  push    rbp
0x1800bff26  push    rsi
0x1800bff27  push    rdi
0x1800bff28  push    r14
0x1800bff2a  push    r15
0x1800bff2c  lea     rbp, [rsp-37h]
0x1800bff31  sub     rsp, 90h
0x1800bff38  mov     rax, cs:__security_cookie
0x1800bff3f  xor     rax, rsp
0x1800bff42  mov     [rbp+57h+var_30], rax
0x1800bff46  mov     r15, rdx
0x1800bff49  mov     r14, rcx
0x1800bff4c  mov     qword ptr [rdx], 0
0x1800bff53  mov     [rbp+57h+var_78], 0
0x1800bff5a  mov     rcx, [rcx+20h]
0x1800bff5e  mov     rax, [rcx]
0x1800bff61  lea     rdx, [rbp+57h+var_78]
0x1800bff65  mov     rax, [rax+38h]
0x1800bff69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bff6e  mov     ebx, eax
0x1800bff70  test    eax, eax
0x1800bff72  jns     short loc_1800BFF93
0x1800bff74  mov     edx, 135h; void *
0x1800bff79  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\coresettinghandlers"...
0x1800bff80  mov     r9d, ebx; char *
0x1800bff83  mov     rcx, [rbp+5Fh]; this
0x1800bff87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bff8c  mov     eax, ebx
0x1800bff8e  jmp     loc_1800C01F6
0x1800bff93  cmp     [rbp+57h+var_78], 1
0x1800bff97  jnz     short loc_1800C0013
0x1800bff99  mov     [rbp+57h+var_80], 0
0x1800bffa1  mov     rdi, [r14+20h]
0x1800bffa5  mov     rax, [rdi]
0x1800bffa8  mov     rbx, [rax+30h]
0x1800bffac  lea     rcx, [rbp+57h+var_80]
0x1800bffb0  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800bffb5  lea     r8, [rbp+57h+var_80]
0x1800bffb9  xor     edx, edx
0x1800bffbb  mov     rcx, rdi
0x1800bffbe  mov     rax, rbx
0x1800bffc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bffc6  mov     ebx, eax
0x1800bffc8  test    eax, eax
0x1800bffca  jns     short loc_1800BFFE6
0x1800bffcc  mov     rcx, [rbp+5Fh]; this
0x1800bffd0  mov     r9d, eax; char *
0x1800bffd3  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\coresettinghandlers"...
0x1800bffda  mov     edx, 13Bh; void *
0x1800bffdf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bffe4  jmp     short loc_1800BFFFF
0x1800bffe6  mov     rcx, [rbp+57h+var_80]
0x1800bffea  mov     rax, [rcx]
0x1800bffed  mov     rdx, r15
0x1800bfff0  mov     rax, [rax+30h]
0x1800bfff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfff9  test    eax, eax
0x1800bfffb  js      short loc_1800C000A
0x1800bfffd  xor     ebx, ebx
0x1800bffff  lea     rcx, [rbp+57h+var_80]
0x1800c0003  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800c0008  jmp     short loc_1800BFF8C
0x1800c000a  lea     rcx, [rbp+57h+var_80]
0x1800c000e  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800c0013  lea     rsi, [r14+28h]
0x1800c0017  cmp     qword ptr [rsi], 0
0x1800c001b  jnz     loc_1800C01D8
0x1800c0021  mov     [rbp+57h+string], 0
0x1800c0029  mov     [rbp+57h+var_58], 0
0x1800c0031  mov     [rbp+57h+var_80], 0
0x1800c0039  mov     [rbp+57h+var_60], 0
0x1800c0041  mov     [rbp+57h+var_68], 0
0x1800c0049  mov     rax, [r14]
0x1800c004c  mov     rbx, [rax+50h]
0x1800c0050  xor     ecx, ecx; string
0x1800c0052  call    cs:__imp_WindowsDeleteString
0x1800c0058  mov     [rbp+57h+string], 0
0x1800c0060  lea     rdx, [rbp+57h+string]
0x1800c0064  mov     rcx, r14
0x1800c0067  mov     rax, rbx
0x1800c006a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c006f  mov     ebx, eax
0x1800c0071  test    eax, eax
0x1800c0073  jns     short loc_1800C007F
0x1800c0075  mov     edx, 14Bh
0x1800c007a  jmp     loc_1800C015B
0x1800c007f  lea     rcx, [rbp+57h+var_50]; string
0x1800c0083  call    ??$?0$0CJ@@StringReference@Internal@Windows@@QEAA@AEAY0CJ@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[41])
0x1800c0088  lea     rdx, [rbp+57h+var_58]
0x1800c008c  mov     rcx, [rax]
0x1800c008f  call    ??$GetActivationFactory@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>)
0x1800c0094  mov     ebx, eax
0x1800c0096  test    eax, eax
0x1800c0098  jns     short loc_1800C00A4
0x1800c009a  mov     edx, 14Dh
0x1800c009f  jmp     loc_1800C015B
0x1800c00a4  lea     rcx, [rbp+57h+var_50]; string
0x1800c00a8  call    ??$?0$0DJ@@StringReference@Internal@Windows@@QEAA@AEAY0DJ@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[57])
0x1800c00ad  lea     rdx, [rbp+57h+var_60]
0x1800c00b1  mov     rcx, [rax]
0x1800c00b4  call    ??$GetActivationFactory@V?$ComPtr@UIPackageResourceResolverStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageResourceResolverStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageResourceResolverStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageResourceResolverStatics>>)
0x1800c00b9  mov     ebx, eax
0x1800c00bb  test    eax, eax
0x1800c00bd  jns     short loc_1800C00C9
0x1800c00bf  mov     edx, 14Eh
0x1800c00c4  jmp     loc_1800C015B
0x1800c00c9  mov     rdi, [rbp+57h+var_58]
0x1800c00cd  mov     rax, [rdi]
0x1800c00d0  mov     rbx, [rax+170h]
0x1800c00d7  lea     rcx, [rbp+57h+var_80]
0x1800c00db  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800c00e0  lea     r9, [rbp+57h+var_80]
0x1800c00e4  mov     r8, [rbp+57h+string]
0x1800c00e8  xor     edx, edx
0x1800c00ea  mov     rcx, rdi
0x1800c00ed  mov     rax, rbx
0x1800c00f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c00f5  mov     ebx, eax
0x1800c00f7  test    eax, eax
0x1800c00f9  jns     short loc_1800C0102
0x1800c00fb  mov     edx, 150h
0x1800c0100  jmp     short loc_1800C015B
0x1800c0102  mov     rcx, [rbp+57h+var_60]
0x1800c0106  mov     rax, [rcx]
0x1800c0109  lea     r8, [rbp+57h+var_68]
0x1800c010d  mov     rdx, [rbp+57h+var_80]
0x1800c0111  mov     rax, [rax+30h]
0x1800c0115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c011a  mov     ebx, eax
0x1800c011c  test    eax, eax
0x1800c011e  jns     short loc_1800C0127
0x1800c0120  mov     edx, 152h
0x1800c0125  jmp     short loc_1800C015B
0x1800c0127  mov     rdi, [rbp+57h+var_68]
0x1800c012b  mov     rax, [rdi]
0x1800c012e  mov     rbx, [rax+30h]
0x1800c0132  mov     rcx, [rsi]; string
0x1800c0135  call    cs:__imp_WindowsDeleteString
0x1800c013b  mov     qword ptr [rsi], 0
0x1800c0142  mov     rdx, rsi
0x1800c0145  mov     rcx, rdi
0x1800c0148  mov     rax, rbx
0x1800c014b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0150  mov     ebx, eax
0x1800c0152  test    eax, eax
0x1800c0154  jns     short loc_1800C01A6
0x1800c0156  mov     edx, 153h; void *
0x1800c015b  mov     r9d, eax; char *
0x1800c015e  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\coresettinghandlers"...
0x1800c0165  mov     rcx, [rbp+5Fh]; this
0x1800c0169  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c016e  nop
0x1800c016f  lea     rcx, [rbp+57h+var_68]
0x1800c0173  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800c0178  nop
0x1800c0179  lea     rcx, [rbp+57h+var_60]
0x1800c017d  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800c0182  nop
0x1800c0183  lea     rcx, [rbp+57h+var_80]
0x1800c0187  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800c018c  nop
0x1800c018d  lea     rcx, [rbp+57h+var_58]
0x1800c0191  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800c0196  nop
0x1800c0197  mov     rcx, [rbp+57h+string]; string
0x1800c019b  call    cs:__imp_WindowsDeleteString
0x1800c01a1  jmp     loc_1800BFF8C
0x1800c01a6  lea     rcx, [rbp+57h+var_68]
0x1800c01aa  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800c01af  nop
0x1800c01b0  lea     rcx, [rbp+57h+var_60]
0x1800c01b4  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800c01b9  nop
0x1800c01ba  lea     rcx, [rbp+57h+var_80]
0x1800c01be  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800c01c3  nop
0x1800c01c4  lea     rcx, [rbp+57h+var_58]
0x1800c01c8  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800c01cd  nop
0x1800c01ce  mov     rcx, [rbp+57h+string]; string
0x1800c01d2  call    cs:__imp_WindowsDeleteString
0x1800c01d8  mov     rdx, r15; newString
0x1800c01db  mov     rcx, [rsi]; string
0x1800c01de  call    cs:__imp_WindowsDuplicateString
0x1800c01e4  mov     ebx, eax
0x1800c01e6  test    eax, eax
0x1800c01e8  jns     short loc_1800C01F4
0x1800c01ea  mov     edx, 156h
0x1800c01ef  jmp     loc_1800BFF79
0x1800c01f4  xor     eax, eax
0x1800c01f6  mov     rcx, [rbp+57h+var_30]
0x1800c01fa  xor     rcx, rsp; StackCookie
0x1800c01fd  call    __security_check_cookie
0x1800c0202  mov     rbx, [rsp+0B0h+arg_10]
0x1800c020a  add     rsp, 90h
0x1800c0211  pop     r15
0x1800c0213  pop     r14
0x1800c0215  pop     rdi
0x1800c0216  pop     rsi
0x1800c0217  pop     rbp
0x1800c0218  retn
```
