# Windows::Compat::Ids::IdsTlsModel::ParseTlsAction(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>)

- ea: `0x1800c2d04`
- end: `0x1800c2f13`
- name: `?ParseTlsAction@IdsTlsModel@Ids@Compat@Windows@@AEAAKV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z`
- size: `527`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c23d8`

## callees

- `0x180012920`
- `0x18007a6e8`
- `0x18008cd3c`
- `0x180096f34`
- `0x1800bed5c`
- `0x1800c1994`
- `0x1800c2d04`
- `0x1800dcb5c`
- `0x1800f1f10`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c2e7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c2e89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c2e7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c2e89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2d50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2db7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2ec5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2ed7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2d50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2db7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2ec5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2ed7`

## string_xrefs

- `0x1800c2e12`: `Windows::Compat::Ids::IdsTlsModel::ParseTlsAction`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
__int64 __fastcall Windows::Compat::Ids::IdsTlsModel::ParseTlsAction(__int64 a1, __int64 *a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, __int64, HSTRING *); // rbx
  int v6; // ebx
  const char *v7; // r9
  int v8; // r8d
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64, HSTRING *); // rbx
  Windows::Compat::Ids::IdsActionItem *v11; // rax
  Windows::Compat::Ids::IdsActionItem *v12; // rdi
  const unsigned __int16 *StringRawBuffer; // rbx
  const unsigned __int16 *v14; // rax
  unsigned int v15; // edx
  HSTRING string; // [rsp+30h] [rbp-50h] BYREF
  HSTRING v18; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v19[2]; // [rsp+40h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  __int64 v21; // [rsp+68h] [rbp-18h]

  v19[1] = a2;
  v18 = 0;
  string = 0;
  v4 = *a2;
  v5 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)*a2 + 80LL);
  WindowsDeleteString(0);
  v18 = 0;
  v21 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"TYPE", 5u, 4u);
  v6 = v5(v4, v21, &v18);
  if ( v6 >= 0 )
  {
    v9 = *a2;
    v10 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)*a2 + 80LL);
    WindowsDeleteString(string);
    string = 0;
    v21 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"PARAM", 6u, 5u);
    v6 = v10(v9, v21, &string);
    if ( v6 >= 0 )
    {
      v11 = (Windows::Compat::Ids::IdsActionItem *)operator new(0x10u, (const struct std::nothrow_t *)std::nothrow);
      v12 = v11;
      v19[0] = v11;
      if ( v11 )
      {
        *((_QWORD *)v11 + 1) = 0;
        *(_QWORD *)v11 = 0;
        v19[0] = v11;
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        v14 = WindowsGetStringRawBuffer(v18, 0);
        v6 = Windows::Compat::Ids::IdsActionItem::Initialize(v12, v14, StringRawBuffer);
        if ( v6 )
          Windows::Compat::Ids::IdsActionItem::`scalar deleting destructor'(v12, v15);
        else
          std::vector<Windows::Compat::Ids::IdsModel *>::push_back(a1 + 72, v19);
      }
      else
      {
        v6 = 8;
      }
      goto LABEL_12;
    }
    v7 = "Failed to get the action parameter [%x]";
    v8 = 67;
  }
  else
  {
    v7 = "Failed to get the action type [%x]";
    v8 = 61;
  }
  AslLogCallPrintf(1, (unsigned int)"Windows::Compat::Ids::IdsTlsModel::ParseTlsAction", v8, (_DWORD)v7, v6);
  if ( (v6 & 0x1FFF0000) == 0x70000 )
    v6 = (unsigned __int16)v6;
LABEL_12:
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v18);
  v18 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(a2);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800c2d04  mov     [rsp-18h+arg_10], rbx
0x1800c2d09  mov     [rsp-18h+arg_18], rsi
0x1800c2d0e  push    rbp
0x1800c2d0f  push    rdi
0x1800c2d10  push    r14
0x1800c2d12  mov     rbp, rsp
0x1800c2d15  sub     rsp, 80h
0x1800c2d1c  mov     rax, cs:__security_cookie
0x1800c2d23  xor     rax, rsp
0x1800c2d26  mov     [rbp+var_10], rax
0x1800c2d2a  mov     rsi, rdx
0x1800c2d2d  mov     r14, rcx
0x1800c2d30  mov     [rbp+var_38], rdx
0x1800c2d34  mov     [rbp+var_48], 0
0x1800c2d3c  mov     [rbp+string], 0
0x1800c2d44  mov     rdi, [rdx]
0x1800c2d47  mov     rax, [rdi]
0x1800c2d4a  mov     rbx, [rax+50h]
0x1800c2d4e  xor     ecx, ecx; string
0x1800c2d50  call    cs:__imp_WindowsDeleteString
0x1800c2d56  mov     [rbp+var_48], 0
0x1800c2d5e  mov     [rbp+var_18], 0
0x1800c2d66  mov     r9d, 4; unsigned int
0x1800c2d6c  lea     r8d, [r9+1]; unsigned int
0x1800c2d70  lea     rdx, aType; "TYPE"
0x1800c2d77  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800c2d7b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800c2d80  nop
0x1800c2d81  lea     r8, [rbp+var_48]
0x1800c2d85  mov     rdx, [rbp+var_18]
0x1800c2d89  mov     rcx, rdi
0x1800c2d8c  mov     rax, rbx
0x1800c2d8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2d94  mov     ebx, eax
0x1800c2d96  test    eax, eax
0x1800c2d98  jns     short loc_1800C2DA9
0x1800c2d9a  lea     r9, aFailedToGetThe_43; "Failed to get the action type [%x]"
0x1800c2da1  mov     r8d, 3Dh ; '='
0x1800c2da7  jmp     short loc_1800C2E0E
0x1800c2da9  mov     rdi, [rsi]
0x1800c2dac  mov     rax, [rdi]
0x1800c2daf  mov     rbx, [rax+50h]
0x1800c2db3  mov     rcx, [rbp+string]; string
0x1800c2db7  call    cs:__imp_WindowsDeleteString
0x1800c2dbd  mov     [rbp+string], 0
0x1800c2dc5  mov     [rbp+var_18], 0
0x1800c2dcd  mov     r9d, 5; unsigned int
0x1800c2dd3  lea     r8d, [r9+1]; unsigned int
0x1800c2dd7  lea     rdx, aParam; "PARAM"
0x1800c2dde  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800c2de2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800c2de7  nop
0x1800c2de8  lea     r8, [rbp+string]
0x1800c2dec  mov     rdx, [rbp+var_18]
0x1800c2df0  mov     rcx, rdi
0x1800c2df3  mov     rax, rbx
0x1800c2df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2dfb  mov     ebx, eax
0x1800c2dfd  test    eax, eax
0x1800c2dff  jns     short loc_1800C2E3F
0x1800c2e01  lea     r9, aFailedToGetThe_19; "Failed to get the action parameter [%x]"
0x1800c2e08  mov     r8d, 43h ; 'C'
0x1800c2e0e  mov     [rsp+80h+var_60], ebx
0x1800c2e12  lea     rdx, aWindowsCompatI_76; "Windows::Compat::Ids::IdsTlsModel::Pars"...
0x1800c2e19  mov     ecx, 1
0x1800c2e1e  call    AslLogCallPrintf
0x1800c2e23  mov     ecx, ebx
0x1800c2e25  and     ecx, 1FFF0000h
0x1800c2e2b  cmp     ecx, 70000h
0x1800c2e31  jnz     loc_1800C2EC1
0x1800c2e37  movzx   ebx, bx
0x1800c2e3a  jmp     loc_1800C2EC1
0x1800c2e3f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800c2e46  mov     ecx, 10h; unsigned __int64
0x1800c2e4b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800c2e50  mov     rdi, rax
0x1800c2e53  mov     [rbp+var_40], rax
0x1800c2e57  test    rax, rax
0x1800c2e5a  jz      short loc_1800C2EBC
0x1800c2e5c  mov     qword ptr [rax+8], 0
0x1800c2e64  mov     qword ptr [rax], 0
0x1800c2e6b  mov     [rbp+var_40], rax
0x1800c2e6f  test    rax, rax
0x1800c2e72  jz      short loc_1800C2EBC
0x1800c2e74  xor     edx, edx; length
0x1800c2e76  mov     rcx, [rbp+string]; string
0x1800c2e7a  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c2e80  mov     rbx, rax
0x1800c2e83  xor     edx, edx; length
0x1800c2e85  mov     rcx, [rbp+var_48]; string
0x1800c2e89  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c2e8f  mov     r8, rbx; unsigned __int16 *
0x1800c2e92  mov     rdx, rax; unsigned __int16 *
0x1800c2e95  mov     rcx, rdi; this
0x1800c2e98  call    ?Initialize@IdsActionItem@Ids@Compat@Windows@@QEAAKPEBG0@Z; Windows::Compat::Ids::IdsActionItem::Initialize(ushort const *,ushort const *)
0x1800c2e9d  mov     ebx, eax
0x1800c2e9f  test    eax, eax
0x1800c2ea1  jnz     short loc_1800C2EB2
0x1800c2ea3  lea     rcx, [r14+48h]
0x1800c2ea7  lea     rdx, [rbp+var_40]
0x1800c2eab  call    ?push_back@?$vector@PEAVIdsModel@Ids@Compat@Windows@@V?$allocator@PEAVIdsModel@Ids@Compat@Windows@@@std@@@std@@QEAAXAEBQEAVIdsModel@Ids@Compat@Windows@@@Z; std::vector<Windows::Compat::Ids::IdsModel *>::push_back(Windows::Compat::Ids::IdsModel * const &)
0x1800c2eb0  jmp     short loc_1800C2EC1
0x1800c2eb2  mov     rcx, rdi; this
0x1800c2eb5  call    ??_GIdsActionItem@Ids@Compat@Windows@@QEAAPEAXI@Z; Windows::Compat::Ids::IdsActionItem::`scalar deleting destructor'(uint)
0x1800c2eba  jmp     short loc_1800C2EC1
0x1800c2ebc  mov     ebx, 8
0x1800c2ec1  mov     rcx, [rbp+string]; string
0x1800c2ec5  call    cs:__imp_WindowsDeleteString
0x1800c2ecb  mov     [rbp+string], 0
0x1800c2ed3  mov     rcx, [rbp+var_48]; string
0x1800c2ed7  call    cs:__imp_WindowsDeleteString
0x1800c2edd  mov     [rbp+var_48], 0
0x1800c2ee5  mov     rcx, rsi
0x1800c2ee8  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVPackageUserInformation@Deployment@Management@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(void)
0x1800c2eed  mov     eax, ebx
0x1800c2eef  mov     rcx, [rbp+var_10]
0x1800c2ef3  xor     rcx, rsp; StackCookie
0x1800c2ef6  call    __security_check_cookie
0x1800c2efb  lea     r11, [rsp+80h+var_s0]
0x1800c2f03  mov     rbx, [r11+30h]
0x1800c2f07  mov     rsi, [r11+38h]
0x1800c2f0b  mov     rsp, r11
0x1800c2f0e  pop     r14
0x1800c2f10  pop     rdi
0x1800c2f11  pop     rbp
0x1800c2f12  retn
```
