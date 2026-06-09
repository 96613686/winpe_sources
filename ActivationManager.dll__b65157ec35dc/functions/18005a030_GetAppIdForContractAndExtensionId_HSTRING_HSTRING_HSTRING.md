# GetAppIdForContractAndExtensionId(HSTRING__ *,HSTRING__ *,HSTRING__ * *)

- ea: `0x18005a030`
- end: `0x18005a250`
- name: `?GetAppIdForContractAndExtensionId@@YAJPEAUHSTRING__@@0PEAPEAU1@@Z`
- size: `544`
- prototype: `__int64 __fastcall(HSTRING string, HSTRING, HSTRING *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006ce40`

## callees

- `0x18000b5c0`
- `0x180038c70`
- `0x1800445ac`
- `0x18005a030`
- `0x18005a258`
- `0x18005ae90`
- `0x18005ba40`
- `0x1800690ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18005a0b2`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18005a0c9`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18005a0b2`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18005a0c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a1fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a216`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a1fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005a216`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005a075`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005a173`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005a075`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005a173`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!GetExtensionApplicationUserModelId` at `0x18005a194`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!GetExtensionApplicationUserModelId` at `0x18005a194`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x18005a130`
- `api-ms-win-appmodel-runtime-l1-1-1!FindPackagesByPackageFamily` at `0x18005a130`

## string_xrefs

- `0x18005a141`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionhelpers.cpp`
- `0x18005a1af`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionhelpers.cpp`
- `0x18005a1e2`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionhelpers.cpp`

## pseudocode

```c
__int64 __fastcall GetAppIdForContractAndExtensionId(HSTRING string, HSTRING a2, HSTRING *a3)
{
  char *StringRawBuffer; // rax
  const char *v6; // r9
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r9
  wchar_t *v10; // rbx
  wchar_t *v11; // rax
  wchar_t *v12; // r14
  unsigned int PackagesByPackageFamily; // eax
  PCWSTR v14; // rax
  int ExtensionApplicationUserModelId; // eax
  int v16; // eax
  int *bufferLength; // [rsp+20h] [rbp-E0h]
  unsigned int bufferLengtha; // [rsp+20h] [rbp-E0h]
  HSTRING stringa; // [rsp+40h] [rbp-C0h] BYREF
  UINT32 v21; // [rsp+48h] [rbp-B8h] BYREF
  UINT32 count; // [rsp+4Ch] [rbp-B4h] BYREF
  wchar_t *Context; // [rsp+50h] [rbp-B0h] BYREF
  PWSTR packageFullNames; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *String[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v26[68]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR buffer[128]; // [rsp+180h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  *a3 = 0;
  Context = 0;
  StringRawBuffer = (char *)WindowsGetStringRawBuffer(a2, 0);
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    String,
    StringRawBuffer,
    0xFFFFFFFFFFFFFFFFuLL,
    v6);
  if ( !String[0] )
  {
    v7 = -2147024882;
    v8 = 77;
    v9 = 2147942414LL;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionhelpers.cpp",
      (const char *)v9,
      (int)bufferLength);
    goto LABEL_12;
  }
  v10 = wcstok_s(String[0], L":", &Context);
  v11 = wcstok_s(0, L":", &Context);
  count = 1;
  packageFullNames = 0;
  v12 = v11;
  memset_0(buffer, 0, sizeof(buffer));
  v21 = 128;
  PackagesByPackageFamily = FindPackagesByPackageFamily(v10, 0x10u, &count, &packageFullNames, &v21, buffer, 0);
  if ( PackagesByPackageFamily )
  {
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x56,
           (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionhelpers.cpp",
           (const char *)PackagesByPackageFamily,
           bufferLengtha);
  }
  else
  {
    memset_0(v26, 0, 0x106u);
    v14 = WindowsGetStringRawBuffer(string, 0);
    bufferLength = v26;
    ExtensionApplicationUserModelId = GetExtensionApplicationUserModelId(packageFullNames, v14, v12, 131);
    v7 = ExtensionApplicationUserModelId;
    if ( ExtensionApplicationUserModelId < 0 )
    {
      v9 = (unsigned int)ExtensionApplicationUserModelId;
      v8 = 90;
      goto LABEL_7;
    }
    stringa = 0;
    v16 = Microsoft::WRL::Wrappers::HString::Set<131>((Microsoft::WRL::Wrappers::HString *)&stringa);
    v7 = v16;
    if ( v16 >= 0 )
    {
      *a3 = stringa;
      stringa = 0;
      WindowsDeleteString(0);
      v7 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5D,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionhelpers.cpp",
        (const char *)(unsigned int)v16,
        (int)v26);
      WindowsDeleteString(stringa);
    }
    stringa = 0;
  }
LABEL_12:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(String);
  return v7;
}

```

## disassembly

```asm
0x18005a030  push    rbp
0x18005a032  push    rbx
0x18005a033  push    rsi
0x18005a034  push    rdi
0x18005a035  push    r14
0x18005a037  lea     rbp, [rsp-190h]
0x18005a03f  sub     rsp, 290h
0x18005a046  mov     rax, cs:__security_cookie
0x18005a04d  xor     rax, rsp
0x18005a050  mov     [rbp+1B0h+var_30], rax
0x18005a057  mov     rax, rdx
0x18005a05a  mov     qword ptr [r8], 0
0x18005a061  mov     rsi, rcx
0x18005a064  mov     [rsp+2B0h+Context], 0
0x18005a06d  mov     rcx, rax; string
0x18005a070  xor     edx, edx; length
0x18005a072  mov     rdi, r8
0x18005a075  call    cs:__imp_WindowsGetStringRawBuffer
0x18005a07b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005a07f  lea     rcx, [rsp+2B0h+String]
0x18005a084  mov     rdx, rax
0x18005a087  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18005a08c  mov     rcx, [rsp+2B0h+String]; String
0x18005a091  test    rcx, rcx
0x18005a094  jnz     short loc_18005A0A6
0x18005a096  mov     ebx, 8007000Eh
0x18005a09b  lea     edx, [rcx+4Dh]
0x18005a09e  mov     r9d, ebx
0x18005a0a1  jmp     loc_18005A1A8
0x18005a0a6  lea     r8, [rsp+2B0h+Context]; Context
0x18005a0ab  lea     rdx, Delimiter; ":"
0x18005a0b2  call    cs:__imp_wcstok_s
0x18005a0b8  lea     r8, [rsp+2B0h+Context]; Context
0x18005a0bd  xor     ecx, ecx; String
0x18005a0bf  lea     rdx, Delimiter; ":"
0x18005a0c6  mov     rbx, rax
0x18005a0c9  call    cs:__imp_wcstok_s
0x18005a0cf  xor     edx, edx; Val
0x18005a0d1  mov     [rsp+2B0h+count], 1
0x18005a0d9  mov     r8d, 100h; Size
0x18005a0df  mov     [rsp+2B0h+packageFullNames], 0
0x18005a0e8  lea     rcx, [rbp+1B0h+var_130]; void *
0x18005a0ef  mov     r14, rax
0x18005a0f2  call    memset_0
0x18005a0f7  lea     rax, [rbp+1B0h+var_130]
0x18005a0fe  mov     [rsp+2B0h+packageProperties], 0; packageProperties
0x18005a107  mov     [rsp+2B0h+buffer], rax; buffer
0x18005a10c  lea     r9, [rsp+2B0h+packageFullNames]; packageFullNames
0x18005a111  lea     rax, [rsp+2B0h+var_268]
0x18005a116  mov     [rsp+2B0h+var_268], 80h
0x18005a11e  lea     r8, [rsp+2B0h+count]; count
0x18005a123  mov     [rsp+2B0h+bufferLength], rax; unsigned int
0x18005a128  mov     edx, 10h; packageFilters
0x18005a12d  mov     rcx, rbx; packageFamilyName
0x18005a130  call    cs:__imp_FindPackagesByPackageFamily
0x18005a136  test    eax, eax
0x18005a138  jz      short loc_18005A15C
0x18005a13a  mov     rcx, [rbp+1B8h]; this
0x18005a141  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18005a148  mov     r9d, eax; char *
0x18005a14b  mov     edx, 56h ; 'V'; void *
0x18005a150  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005a155  mov     ebx, eax
0x18005a157  jmp     loc_18005A227
0x18005a15c  xor     edx, edx; Val
0x18005a15e  lea     rcx, [rsp+2B0h+var_240]; void *
0x18005a163  mov     r8d, 106h; Size
0x18005a169  call    memset_0
0x18005a16e  xor     edx, edx; length
0x18005a170  mov     rcx, rsi; string
0x18005a173  call    cs:__imp_WindowsGetStringRawBuffer
0x18005a179  lea     rcx, [rsp+2B0h+var_240]
0x18005a17e  mov     r9d, 83h
0x18005a184  mov     [rsp+2B0h+bufferLength], rcx; int
0x18005a189  mov     r8, r14
0x18005a18c  mov     rcx, [rsp+2B0h+packageFullNames]
0x18005a191  mov     rdx, rax
0x18005a194  call    cs:__imp_GetExtensionApplicationUserModelId
0x18005a19a  mov     ebx, eax
0x18005a19c  test    eax, eax
0x18005a19e  jns     short loc_18005A1BD
0x18005a1a0  mov     r9d, eax; char *
0x18005a1a3  mov     edx, 5Ah ; 'Z'; void *
0x18005a1a8  mov     rcx, [rbp+1B8h]; this
0x18005a1af  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18005a1b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a1bb  jmp     short loc_18005A227
0x18005a1bd  lea     rdx, [rsp+2B0h+var_240]
0x18005a1c2  mov     [rsp+2B0h+string], 0
0x18005a1cb  lea     rcx, [rsp+2B0h+string]; this
0x18005a1d0  call    ??$Set@$0ID@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0ID@G@Z; Microsoft::WRL::Wrappers::HString::Set<131>(ushort (&)[131])
0x18005a1d5  mov     ebx, eax
0x18005a1d7  test    eax, eax
0x18005a1d9  jns     short loc_18005A203
0x18005a1db  mov     rcx, [rbp+1B8h]; this
0x18005a1e2  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18005a1e9  mov     r9d, eax; char *
0x18005a1ec  mov     edx, 5Dh ; ']'; void *
0x18005a1f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a1f6  mov     rcx, [rsp+2B0h+string]; string
0x18005a1fb  call    cs:__imp_WindowsDeleteString
0x18005a201  jmp     short loc_18005A21E
0x18005a203  mov     rax, [rsp+2B0h+string]
0x18005a208  xor     ecx, ecx; string
0x18005a20a  mov     [rdi], rax
0x18005a20d  mov     [rsp+2B0h+string], 0
0x18005a216  call    cs:__imp_WindowsDeleteString
0x18005a21c  xor     ebx, ebx
0x18005a21e  mov     [rsp+2B0h+string], 0
0x18005a227  lea     rcx, [rsp+2B0h+String]
0x18005a22c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18005a231  mov     eax, ebx
0x18005a233  mov     rcx, [rbp+1B0h+var_30]
0x18005a23a  xor     rcx, rsp; StackCookie
0x18005a23d  call    __security_check_cookie
0x18005a242  add     rsp, 290h
0x18005a249  pop     r14
0x18005a24b  pop     rdi
0x18005a24c  pop     rsi
0x18005a24d  pop     rbx
0x18005a24e  pop     rbp
0x18005a24f  retn
```
