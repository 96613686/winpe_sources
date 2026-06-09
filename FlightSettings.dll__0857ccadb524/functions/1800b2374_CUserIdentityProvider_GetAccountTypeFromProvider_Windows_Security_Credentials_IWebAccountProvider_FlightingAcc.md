# CUserIdentityProvider::GetAccountTypeFromProvider(Windows::Security::Credentials::IWebAccountProvider *,FlightingAccountType *)

- ea: `0x1800b2374`
- end: `0x1800b24c6`
- name: `?GetAccountTypeFromProvider@CUserIdentityProvider@@AEAAJPEAUIWebAccountProvider@Credentials@Security@Windows@@PEAW4FlightingAccountType@@@Z`
- size: `338`
- prototype: `__int64 __fastcall(CUserIdentityProvider *__hidden this, struct Windows::Security::Credentials::IWebAccountProvider *, enum FlightingAccountType *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b3ebc`
- `0x1800b446c`
- `0x1800b483c`

## callees

- `0x18000b19c`
- `0x18000cc8c`
- `0x180010fe0`
- `0x1800b2374`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b2459`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b248c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b2459`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800b248c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b2438`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b2473`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b2438`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b2473`

## string_xrefs

- `0x1800b23d0`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b2413`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CUserIdentityProvider::GetAccountTypeFromProvider(
        CUserIdentityProvider *this,
        __int64 (__fastcall ***a2)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *),
        enum FlightingAccountType *a3)
{
  __int64 (__fastcall *v5)(struct Windows::Security::Credentials::IWebAccountProvider *, GUID *, __int64 *); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  const WCHAR *StringRawBuffer; // rax
  const WCHAR *v10; // rax
  int v11; // eax
  int v12; // ecx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  HSTRING string; // [rsp+50h] [rbp+8h] BYREF
  __int64 v17; // [rsp+58h] [rbp+10h] BYREF

  string = (HSTRING)this;
  *(_DWORD *)a3 = 0;
  v17 = 0;
  v5 = **a2;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
  v6 = v5(
         (struct Windows::Security::Credentials::IWebAccountProvider *)a2,
         &GUID_4a01eb05_4e42_41d4_b518_e008a5163614,
         &v17);
  v7 = v6;
  if ( v6 >= 0 )
  {
    string = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v17 + 56LL))(v17, &string);
    v7 = v8;
    if ( v8 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      if ( CompareStringOrdinal(StringRawBuffer, -1, L"consumers", -1, 1) == 2 )
      {
        *(_DWORD *)a3 = 1;
      }
      else
      {
        v10 = WindowsGetStringRawBuffer(string, 0);
        v11 = CompareStringOrdinal(v10, -1, L"organizations", -1, 1);
        v12 = 4;
        if ( v11 == 2 )
          v12 = 2;
        *(_DWORD *)a3 = v12;
      }
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      v7 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22E,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
        (const char *)(unsigned int)v8,
        bIgnoreCase);
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22B,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
      (const char *)(unsigned int)v6,
      bIgnoreCase);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
  return v7;
}

```

## disassembly

```asm
0x1800b2374  mov     r11, rsp
0x1800b2377  mov     [r11+18h], rbx
0x1800b237b  mov     [r11+8], rcx
0x1800b237f  push    rsi
0x1800b2380  push    rdi
0x1800b2381  push    r14
0x1800b2383  sub     rsp, 30h
0x1800b2387  mov     rsi, r8
0x1800b238a  mov     rdi, rdx
0x1800b238d  mov     dword ptr [r8], 0
0x1800b2394  mov     qword ptr [r11+10h], 0
0x1800b239c  mov     rax, [rdx]
0x1800b239f  mov     rbx, [rax]
0x1800b23a2  lea     rcx, [r11+10h]
0x1800b23a6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b23ab  lea     r8, [rsp+48h+arg_8]
0x1800b23b0  lea     rdx, _GUID_4a01eb05_4e42_41d4_b518_e008a5163614
0x1800b23b7  mov     rcx, rdi
0x1800b23ba  mov     rax, rbx
0x1800b23bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b23c2  mov     ebx, eax
0x1800b23c4  test    eax, eax
0x1800b23c6  jns     short loc_1800B23E6
0x1800b23c8  mov     rcx, [rsp+48h]; this
0x1800b23cd  mov     r9d, eax; char *
0x1800b23d0  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b23d7  mov     edx, 22Bh; void *
0x1800b23dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b23e1  jmp     loc_1800B24AC
0x1800b23e6  mov     [rsp+48h+string], 0
0x1800b23ef  mov     rcx, [rsp+48h+arg_8]
0x1800b23f4  mov     rax, [rcx]
0x1800b23f7  lea     rdx, [rsp+48h+string]
0x1800b23fc  mov     rax, [rax+38h]
0x1800b2400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2405  mov     ebx, eax
0x1800b2407  test    eax, eax
0x1800b2409  jns     short loc_1800B2431
0x1800b240b  mov     rcx, [rsp+48h]; this
0x1800b2410  mov     r9d, eax; char *
0x1800b2413  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b241a  mov     edx, 22Eh; void *
0x1800b241f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2424  nop
0x1800b2425  lea     rcx, [rsp+48h+string]; this
0x1800b242a  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800b242f  jmp     short loc_1800B24AC
0x1800b2431  xor     edx, edx; length
0x1800b2433  mov     rcx, [rsp+48h+string]; string
0x1800b2438  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b243e  mov     ebx, 1
0x1800b2443  mov     [rsp+48h+bIgnoreCase], ebx; bIgnoreCase
0x1800b2447  or      edi, 0FFFFFFFFh
0x1800b244a  mov     r9d, edi; cchCount2
0x1800b244d  lea     r8, aConsumers; "consumers"
0x1800b2454  mov     edx, edi; cchCount1
0x1800b2456  mov     rcx, rax; lpString1
0x1800b2459  call    cs:__imp_CompareStringOrdinal
0x1800b245f  lea     r14d, [rbx+1]
0x1800b2463  cmp     eax, r14d
0x1800b2466  jnz     short loc_1800B246C
0x1800b2468  mov     [rsi], ebx
0x1800b246a  jmp     short loc_1800B24A0
0x1800b246c  xor     edx, edx; length
0x1800b246e  mov     rcx, [rsp+48h+string]; string
0x1800b2473  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b2479  mov     [rsp+48h+bIgnoreCase], ebx; bIgnoreCase
0x1800b247d  mov     r9d, edi; cchCount2
0x1800b2480  lea     r8, aOrganizations; "organizations"
0x1800b2487  mov     edx, edi; cchCount1
0x1800b2489  mov     rcx, rax; lpString1
0x1800b248c  call    cs:__imp_CompareStringOrdinal
0x1800b2492  mov     ecx, 4
0x1800b2497  cmp     eax, r14d
0x1800b249a  cmovz   ecx, r14d
0x1800b249e  mov     [rsi], ecx
0x1800b24a0  lea     rcx, [rsp+48h+string]; this
0x1800b24a5  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800b24aa  xor     ebx, ebx
0x1800b24ac  lea     rcx, [rsp+48h+arg_8]
0x1800b24b1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b24b6  mov     eax, ebx
0x1800b24b8  mov     rbx, [rsp+48h+arg_10]
0x1800b24bd  add     rsp, 30h
0x1800b24c1  pop     r14
0x1800b24c3  pop     rdi
0x1800b24c4  pop     rsi
0x1800b24c5  retn
```
