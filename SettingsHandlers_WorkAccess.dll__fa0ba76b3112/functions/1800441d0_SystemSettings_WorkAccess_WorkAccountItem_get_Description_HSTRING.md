# SystemSettings::WorkAccess::WorkAccountItem::get_Description(HSTRING__ * *)

- ea: `0x1800441d0`
- end: `0x180044452`
- name: `?get_Description@WorkAccountItem@WorkAccess@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `642`
- prototype: `int(SystemSettings::WorkAccess::WorkAccountItem *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800076ac`
- `0x1800096ec`
- `0x180017744`
- `0x18001ce98`
- `0x18001efe0`
- `0x180020584`
- `0x180042c88`
- `0x1800441d0`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800443b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800443b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004437d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800443df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044401`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004437d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800443df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044401`

## string_xrefs

- `0x18004425c`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountitem.cpp`
- `0x1800442c8`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountitem.cpp`
- `0x180044356`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountitem.cpp`
- `0x1800443ca`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountitem.cpp`
- `0x18004443c`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountitem.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SystemSettings::WorkAccess::WorkAccountItem::get_Description(
        SystemSettings::WorkAccess::WorkAccountItem *this,
        HSTRING *a2,
        HSTRING *a3)
{
  int v4; // eax
  unsigned __int16 **v5; // r8
  int CloudDomainInfo; // eax
  __int64 v7; // rdx
  unsigned int v8; // ebx
  __int64 v9; // r9
  __int64 v10; // rdx
  int v11; // eax
  HSTRING *v12; // r8
  __int64 v13; // rdx
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64 *); // rbx
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rbx
  HRESULT v20; // eax
  __int64 v21; // rdx
  int v22; // eax
  __int64 v23; // [rsp+20h] [rbp-30h] BYREF
  __int64 v24; // [rsp+28h] [rbp-28h]
  __int64 v25; // [rsp+30h] [rbp-20h]
  SystemSettings::DataModel *v26[3]; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  HSTRING string; // [rsp+70h] [rbp+20h] BYREF
  __int64 v29; // [rsp+78h] [rbp+28h] BYREF

  *a2 = 0;
  if ( *((_BYTE *)this + 304) )
  {
    v4 = *((_DWORD *)this + 62);
    if ( v4 == 1 )
    {
      v23 = 0;
      v24 = 0;
      v25 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v23);
      v24 = -1;
      v25 = -1;
      CloudDomainInfo = SystemSettings::WorkAccess::GetCloudDomainInfo((SystemSettings::WorkAccess *)&v23, 0, v5);
      v8 = CloudDomainInfo;
      if ( CloudDomainInfo < 0 )
      {
        v9 = (unsigned int)CloudDomainInfo;
        v10 = 193;
LABEL_7:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v10,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountitem.cpp",
          (const char *)v9,
          v23);
LABEL_13:
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v23);
        return v8;
      }
      if ( !v23 )
      {
        v8 = -2147467259;
        v9 = 2147500037LL;
        v10 = 194;
        goto LABEL_7;
      }
      memset(v26, 0, sizeof(v26));
      LOBYTE(v7) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADToMicrosoftEntra>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_AADToMicrosoftEntra>::GetImpl'::`2'::impl,
        v7);
      v11 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeResMessage(
              v26,
              &_ImageBase,
              128);
      v8 = v11;
      if ( v11 < 0 )
      {
        v13 = 200;
LABEL_12:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v13,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountitem.cpp",
          (const char *)(unsigned int)v11,
          v23);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v26);
        goto LABEL_13;
      }
      v11 = SystemSettings::DataModel::WindowsCreateString(v26[0], (const unsigned __int16 *)a2, v12);
      v8 = v11;
      if ( v11 < 0 )
      {
        v13 = 208;
        goto LABEL_12;
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v26);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v23);
    }
    else if ( !v4 )
    {
      v29 = 0;
      v15 = *((_QWORD *)this + 27);
      v16 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
      v17 = v16(v15, &v29);
      v8 = v17;
      if ( v17 >= 0 )
      {
        string = 0;
        v18 = v29;
        v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v29 + 56LL);
        WindowsDeleteString(0);
        string = 0;
        v20 = v19(v18, &string);
        v8 = v20;
        if ( v20 >= 0 )
        {
          v20 = WindowsDuplicateString(string, a2);
          v8 = v20;
          if ( v20 >= 0 )
          {
            WindowsDeleteString(string);
            string = 0;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
            return 0;
          }
          v21 = 217;
        }
        else
        {
          v21 = 216;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v21,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountitem.cpp",
          (const char *)(unsigned int)v20,
          v23);
        WindowsDeleteString(string);
        string = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD5,
          (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountitem.cpp",
          (const char *)(unsigned int)v17,
          v23);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
      return v8;
    }
  }
  else
  {
    v22 = SystemSettings::DataModel::WindowsCreateString(
            *((SystemSettings::DataModel **)this + 32),
            (const unsigned __int16 *)a2,
            a3);
    v8 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountitem.cpp",
        (const char *)(unsigned int)v22,
        v23);
      return v8;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800441d0  mov     [rsp-18h+arg_10], rbx
0x1800441d5  mov     [rsp-18h+arg_18], rsi
0x1800441da  push    rbp
0x1800441db  push    rdi
0x1800441dc  push    r14
0x1800441de  mov     rbp, rsp
0x1800441e1  sub     rsp, 50h
0x1800441e5  mov     rsi, rdx
0x1800441e8  xor     r14d, r14d
0x1800441eb  mov     [rdx], r14
0x1800441ee  cmp     [rcx+130h], r14b
0x1800441f5  jz      loc_18004441F
0x1800441fb  mov     eax, [rcx+0F8h]
0x180044201  cmp     eax, 1
0x180044204  jnz     loc_18004431B
0x18004420a  mov     [rbp+var_30], r14
0x18004420e  mov     [rbp+var_28], r14
0x180044212  mov     [rbp+var_20], r14
0x180044216  lea     rcx, [rbp+var_30]
0x18004421a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004421f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180044223  mov     [rbp+var_28], rax
0x180044227  mov     [rbp+var_20], rax
0x18004422b  xor     edx, edx; unsigned __int16 **
0x18004422d  lea     rcx, [rbp+var_30]; this
0x180044231  call    ?GetCloudDomainInfo@WorkAccess@SystemSettings@@YAJPEAPEAG0@Z; SystemSettings::WorkAccess::GetCloudDomainInfo(ushort * *,ushort * *)
0x180044236  mov     ebx, eax
0x180044238  test    eax, eax
0x18004423a  jns     short loc_180044246
0x18004423c  mov     r9d, eax
0x18004423f  mov     edx, 0C1h
0x180044244  jmp     short loc_18004425C
0x180044246  mov     rbx, [rbp+var_30]
0x18004424a  test    rbx, rbx
0x18004424d  jnz     short loc_18004426E
0x18004424f  mov     ebx, 80004005h
0x180044254  mov     r9d, ebx; char *
0x180044257  mov     edx, 0C2h; void *
0x18004425c  lea     r8, aShellcommonShe_6; "shellcommon\\shell\\settingshandlers\\w"...
0x180044263  mov     rcx, [rbp+18h]; this
0x180044267  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004426c  jmp     short loc_1800442E3
0x18004426e  mov     [rbp+var_18], r14
0x180044272  mov     [rbp+var_10], r14
0x180044276  mov     [rbp+var_8], r14
0x18004427a  mov     dl, 1
0x18004427c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AADToMicrosoftEntra@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AADToMicrosoftEntra@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADToMicrosoftEntra> `wil::Feature<__WilFeatureTraits_Feature_AADToMicrosoftEntra>::GetImpl(void)'::`2'::impl
0x180044283  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AADToMicrosoftEntra@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADToMicrosoftEntra>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180044288  mov     r9, rbx
0x18004428b  mov     r8d, 80h
0x180044291  lea     rdx, __ImageBase
0x180044298  lea     rcx, [rbp+var_18]
0x18004429c  call    ?InitializeResMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@HZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeResMessage(HINSTANCE__ *,int,...)
0x1800442a1  mov     ebx, eax
0x1800442a3  test    eax, eax
0x1800442a5  jns     short loc_1800442AE
0x1800442a7  mov     edx, 0C8h
0x1800442ac  jmp     short loc_1800442C5
0x1800442ae  mov     rdx, rsi; unsigned __int16 *
0x1800442b1  mov     rcx, [rbp+var_18]; this
0x1800442b5  call    ?WindowsCreateString@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::WindowsCreateString(ushort const *,HSTRING__ * *)
0x1800442ba  mov     ebx, eax
0x1800442bc  test    eax, eax
0x1800442be  jns     short loc_1800442F0
0x1800442c0  mov     edx, 0D0h; void *
0x1800442c5  mov     r9d, eax; char *
0x1800442c8  lea     r8, aShellcommonShe_6; "shellcommon\\shell\\settingshandlers\\w"...
0x1800442cf  mov     rcx, [rbp+18h]; this
0x1800442d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800442d8  nop
0x1800442d9  lea     rcx, [rbp+var_18]
0x1800442dd  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800442e2  nop
0x1800442e3  lea     rcx, [rbp+var_30]
0x1800442e7  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800442ec  mov     eax, ebx
0x1800442ee  jmp     short loc_180044305
0x1800442f0  lea     rcx, [rbp+var_18]
0x1800442f4  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800442f9  nop
0x1800442fa  lea     rcx, [rbp+var_30]
0x1800442fe  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180044303  xor     eax, eax
0x180044305  lea     r11, [rsp+50h+var_s0]
0x18004430a  mov     rbx, [r11+30h]
0x18004430e  mov     rsi, [r11+38h]
0x180044312  mov     rsp, r11
0x180044315  pop     r14
0x180044317  pop     rdi
0x180044318  pop     rbp
0x180044319  retn
0x18004431b  test    eax, eax
0x18004431d  jnz     short loc_180044303
0x18004431f  mov     [rbp+arg_8], r14
0x180044323  mov     rdi, [rcx+0D8h]
0x18004432a  mov     rax, [rdi]
0x18004432d  mov     rbx, [rax+30h]
0x180044331  lea     rcx, [rbp+arg_8]
0x180044335  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004433a  lea     rdx, [rbp+arg_8]
0x18004433e  mov     rcx, rdi
0x180044341  mov     rax, rbx
0x180044344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044349  mov     ebx, eax
0x18004434b  test    eax, eax
0x18004434d  jns     short loc_18004436C
0x18004434f  mov     rcx, [rbp+18h]; this
0x180044353  mov     r9d, eax; char *
0x180044356  lea     r8, aShellcommonShe_6; "shellcommon\\shell\\settingshandlers\\w"...
0x18004435d  mov     edx, 0D5h; void *
0x180044362  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044367  jmp     loc_1800443EF
0x18004436c  mov     [rbp+string], r14
0x180044370  mov     rdi, [rbp+arg_8]
0x180044374  mov     rax, [rdi]
0x180044377  mov     rbx, [rax+38h]
0x18004437b  xor     ecx, ecx; string
0x18004437d  call    cs:__imp_WindowsDeleteString
0x180044384  nop     dword ptr [rax+rax+00h]
0x180044389  mov     [rbp+string], r14
0x18004438d  lea     rdx, [rbp+string]
0x180044391  mov     rcx, rdi
0x180044394  mov     rax, rbx
0x180044397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004439c  mov     ebx, eax
0x18004439e  test    eax, eax
0x1800443a0  jns     short loc_1800443A9
0x1800443a2  mov     edx, 0D8h
0x1800443a7  jmp     short loc_1800443C7
0x1800443a9  mov     rdx, rsi; newString
0x1800443ac  mov     rcx, [rbp+string]; string
0x1800443b0  call    cs:__imp_WindowsDuplicateString
0x1800443b7  nop     dword ptr [rax+rax+00h]
0x1800443bc  mov     ebx, eax
0x1800443be  test    eax, eax
0x1800443c0  jns     short loc_1800443FD
0x1800443c2  mov     edx, 0D9h; void *
0x1800443c7  mov     r9d, eax; char *
0x1800443ca  lea     r8, aShellcommonShe_6; "shellcommon\\shell\\settingshandlers\\w"...
0x1800443d1  mov     rcx, [rbp+18h]; this
0x1800443d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800443da  nop
0x1800443db  mov     rcx, [rbp+string]; string
0x1800443df  call    cs:__imp_WindowsDeleteString
0x1800443e6  nop     dword ptr [rax+rax+00h]
0x1800443eb  mov     [rbp+string], r14
0x1800443ef  lea     rcx, [rbp+arg_8]
0x1800443f3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800443f8  jmp     loc_1800442EC
0x1800443fd  mov     rcx, [rbp+string]; string
0x180044401  call    cs:__imp_WindowsDeleteString
0x180044408  nop     dword ptr [rax+rax+00h]
0x18004440d  mov     [rbp+string], r14
0x180044411  lea     rcx, [rbp+arg_8]
0x180044415  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004441a  jmp     loc_180044303
0x18004441f  mov     rcx, [rcx+100h]; this
0x180044426  call    ?WindowsCreateString@DataModel@SystemSettings@@YAJPEBGPEAPEAUHSTRING__@@@Z; SystemSettings::DataModel::WindowsCreateString(ushort const *,HSTRING__ * *)
0x18004442b  mov     ebx, eax
0x18004442d  test    eax, eax
0x18004442f  jns     loc_180044303
0x180044435  mov     rcx, [rbp+18h]; this
0x180044439  mov     r9d, eax; char *
0x18004443c  lea     r8, aShellcommonShe_6; "shellcommon\\shell\\settingshandlers\\w"...
0x180044443  mov     edx, 0DEh; void *
0x180044448  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004444d  jmp     loc_1800442EC
```
