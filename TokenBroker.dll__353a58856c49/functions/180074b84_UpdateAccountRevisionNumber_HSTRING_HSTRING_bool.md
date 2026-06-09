# UpdateAccountRevisionNumber(HSTRING__ *,HSTRING__ *,bool)

- ea: `0x180074b84`
- end: `0x180074e03`
- name: `?UpdateAccountRevisionNumber@@YAJPEAUHSTRING__@@0_N@Z`
- size: `639`
- prototype: `__int64 __fastcall(HSTRING string, HSTRING, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180073f54`

## callees

- `0x1800060e0`
- `0x18000bd40`
- `0x18002a3e0`
- `0x180035880`
- `0x1800454f0`
- `0x180051dd0`
- `0x180072cd0`
- `0x180074b84`
- `0x180074e0c`
- `0x18010ebf0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180074c44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180074ca6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180074c44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180074ca6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180074bcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180074cfa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180074d0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180074d24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180074d35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180074d45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180074d55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180074bcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180074cfa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180074d0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180074d24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180074d35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180074d45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180074d55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074c2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074c8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074dc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074dd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074c2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074c8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074dc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180074dd2`

## string_xrefs

- `0x180074c09`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180074c55`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x180074cb7`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall UpdateAccountRevisionNumber(HSTRING string, HSTRING a2)
{
  unsigned __int16 *StringRawBuffer; // rax
  int v5; // eax
  unsigned int updated; // ebx
  __int64 v7; // rdx
  HRESULT v8; // eax
  __int64 v9; // rdx
  HRESULT v10; // eax
  __int64 v11; // rdx
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  int v16; // [rsp+20h] [rbp-E0h]
  HSTRING newString; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v18; // [rsp+68h] [rbp-98h] BYREF
  int v19; // [rsp+70h] [rbp-90h] BYREF
  PCWSTR v20; // [rsp+78h] [rbp-88h] BYREF
  PCWSTR v21; // [rsp+80h] [rbp-80h] BYREF
  PCWSTR v22; // [rsp+88h] [rbp-78h] BYREF
  PCWSTR v23; // [rsp+90h] [rbp-70h] BYREF
  PCWSTR v24; // [rsp+98h] [rbp-68h] BYREF
  PCWSTR v25; // [rsp+A0h] [rbp-60h] BYREF
  HLOCAL v26; // [rsp+A8h] [rbp-58h] BYREF
  int v27; // [rsp+B0h] [rbp-50h]
  __int128 v28; // [rsp+B8h] [rbp-48h]
  __int64 v29; // [rsp+C8h] [rbp-38h]
  HSTRING v30[7]; // [rsp+D0h] [rbp-30h] BYREF
  HSTRING stringa; // [rsp+108h] [rbp+8h] BYREF
  HSTRING v32; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  AccountSystemOnlyInfo::AccountSystemOnlyInfo((AccountSystemOnlyInfo *)v30);
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  StringRawBuffer = (unsigned __int16 *)WindowsGetStringRawBuffer(string, 0);
  v5 = Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InitializeFromStringId(
         &v26,
         StringRawBuffer);
  updated = v5;
  if ( v5 < 0 )
  {
    v7 = 2028;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v5,
      v16);
    goto LABEL_23;
  }
  v5 = AccountSystemOnlyInfo::InitializeFromAccountId(
         (AccountSystemOnlyInfo *)v30,
         (struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&v26,
         a2);
  updated = v5;
  if ( v5 < 0 )
  {
    v7 = 2031;
    goto LABEL_5;
  }
  WindowsDeleteString(0);
  newString = 0;
  v8 = WindowsDuplicateString(stringa, &newString);
  updated = v8;
  if ( v8 >= 0 )
  {
    v8 = ComputeNewAccountRevisionNumber(&stringa);
    updated = v8;
    if ( v8 < 0 )
    {
      v9 = 2035;
      goto LABEL_8;
    }
    v18 = 0;
    WindowsDeleteString(0);
    v18 = 0;
    v10 = WindowsDuplicateString(v32, &v18);
    updated = v10;
    if ( v10 >= 0 )
    {
      v10 = ComputeNewAccountRevisionNumber(&v32);
      updated = v10;
      if ( v10 >= 0 )
      {
        if ( (unsigned int)dword_180175000 > 5 )
        {
          v20 = WindowsGetStringRawBuffer(v32, 0);
          v21 = WindowsGetStringRawBuffer(v18, 0);
          v19 = 1;
          v22 = WindowsGetStringRawBuffer(stringa, 0);
          v23 = WindowsGetStringRawBuffer(newString, 0);
          v24 = WindowsGetStringRawBuffer(v30[0], 0);
          v25 = WindowsGetStringRawBuffer(v30[5], 0);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            v12,
            (unsigned int)&unk_1801588A8,
            v13,
            v14,
            (__int64)&v25,
            (__int64)&v24,
            (__int64)&v23,
            (__int64)&v22,
            (__int64)&v19,
            (__int64)&v21,
            (__int64)&v20);
        }
        updated = UpdateAccountSystemOnlyData((struct AccountSystemOnlyInfo *)v30);
        goto LABEL_19;
      }
      v11 = 2042;
    }
    else
    {
      v11 = 2038;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v10,
      v16);
LABEL_19:
    if ( v18 )
      WindowsDeleteString(v18);
    goto LABEL_21;
  }
  v9 = 2034;
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
    (const char *)(unsigned int)v8,
    v16);
LABEL_21:
  if ( newString )
    WindowsDeleteString(newString);
LABEL_23:
  Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease((Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *)&v26);
  AccountSystemOnlyInfo::~AccountSystemOnlyInfo((AccountSystemOnlyInfo *)v30);
  return updated;
}

```

## disassembly

```asm
0x180074b84  mov     [rsp-8+arg_0], rbx
0x180074b89  mov     [rsp-8+arg_10], rdi
0x180074b8e  push    rbp
0x180074b8f  lea     rbp, [rsp-30h]
0x180074b94  sub     rsp, 130h
0x180074b9b  mov     rdi, rdx
0x180074b9e  mov     rbx, rcx
0x180074ba1  lea     rcx, [rbp+30h+var_60]; this
0x180074ba5  call    ??0AccountSystemOnlyInfo@@QEAA@XZ; AccountSystemOnlyInfo::AccountSystemOnlyInfo(void)
0x180074baa  nop
0x180074bab  mov     [rbp+30h+var_88], 0
0x180074bb3  mov     [rbp+30h+var_80], 0
0x180074bba  xorps   xmm0, xmm0
0x180074bbd  movdqu  [rbp+30h+var_78], xmm0
0x180074bc2  mov     [rbp+30h+var_68], 0
0x180074bca  xor     edx, edx; length
0x180074bcc  mov     rcx, rbx; string
0x180074bcf  call    cs:__imp_WindowsGetStringRawBuffer
0x180074bd5  mov     rdx, rax; unsigned __int16 *
0x180074bd8  lea     rcx, [rbp+30h+var_88]; this
0x180074bdc  call    ?InitializeFromStringId@StoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InitializeFromStringId(ushort const *)
0x180074be1  mov     ebx, eax
0x180074be3  test    eax, eax
0x180074be5  jns     short loc_180074BEE
0x180074be7  mov     edx, 7ECh
0x180074bec  jmp     short loc_180074C09
0x180074bee  mov     r8, rdi; HSTRING
0x180074bf1  lea     rdx, [rbp+30h+var_88]; struct Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId *
0x180074bf5  lea     rcx, [rbp+30h+var_60]; this
0x180074bf9  call    ?InitializeFromAccountId@AccountSystemOnlyInfo@@QEAAJAEAVStoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@PEAUHSTRING__@@@Z; AccountSystemOnlyInfo::InitializeFromAccountId(Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId &,HSTRING__ *)
0x180074bfe  mov     ebx, eax
0x180074c00  test    eax, eax
0x180074c02  jns     short loc_180074C21
0x180074c04  mov     edx, 7EFh; void *
0x180074c09  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180074c10  mov     r9d, eax; char *
0x180074c13  mov     rcx, [rbp+38h]; this
0x180074c17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074c1c  jmp     loc_180074DD9
0x180074c21  mov     [rsp+130h+newString], 0
0x180074c2a  xor     ecx, ecx; string
0x180074c2c  call    cs:__imp_WindowsDeleteString
0x180074c32  mov     [rsp+130h+newString], 0
0x180074c3b  lea     rdx, [rsp+130h+newString]; newString
0x180074c40  mov     rcx, [rbp+30h+string]; string
0x180074c44  call    cs:__imp_WindowsDuplicateString
0x180074c4a  mov     ebx, eax
0x180074c4c  test    eax, eax
0x180074c4e  jns     short loc_180074C6D
0x180074c50  mov     edx, 7F2h; void *
0x180074c55  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180074c5c  mov     r9d, eax; char *
0x180074c5f  mov     rcx, [rbp+38h]; this
0x180074c63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074c68  jmp     loc_180074DC8
0x180074c6d  lea     rcx, [rbp+30h+string]; newString
0x180074c71  call    ?ComputeNewAccountRevisionNumber@@YAJAEAVString@Internal@Windows@@@Z; ComputeNewAccountRevisionNumber(Windows::Internal::String &)
0x180074c76  mov     ebx, eax
0x180074c78  test    eax, eax
0x180074c7a  jns     short loc_180074C83
0x180074c7c  mov     edx, 7F3h
0x180074c81  jmp     short loc_180074C55
0x180074c83  mov     [rsp+130h+var_C8], 0
0x180074c8c  xor     ecx, ecx; string
0x180074c8e  call    cs:__imp_WindowsDeleteString
0x180074c94  mov     [rsp+130h+var_C8], 0
0x180074c9d  lea     rdx, [rsp+130h+var_C8]; newString
0x180074ca2  mov     rcx, [rbp+30h+var_20]; string
0x180074ca6  call    cs:__imp_WindowsDuplicateString
0x180074cac  mov     ebx, eax
0x180074cae  test    eax, eax
0x180074cb0  jns     short loc_180074CCF
0x180074cb2  mov     edx, 7F6h; void *
0x180074cb7  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180074cbe  mov     r9d, eax; char *
0x180074cc1  mov     rcx, [rbp+38h]; this
0x180074cc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074cca  jmp     loc_180074DB7
0x180074ccf  lea     rcx, [rbp+30h+var_20]; newString
0x180074cd3  call    ?ComputeNewAccountRevisionNumber@@YAJAEAVString@Internal@Windows@@@Z; ComputeNewAccountRevisionNumber(Windows::Internal::String &)
0x180074cd8  mov     ebx, eax
0x180074cda  test    eax, eax
0x180074cdc  jns     short loc_180074CE5
0x180074cde  mov     edx, 7FAh
0x180074ce3  jmp     short loc_180074CB7
0x180074ce5  mov     eax, cs:dword_180175000
0x180074ceb  cmp     eax, 5
0x180074cee  jbe     loc_180074DAC
0x180074cf4  xor     edx, edx; length
0x180074cf6  mov     rcx, [rbp+30h+var_20]; string
0x180074cfa  call    cs:__imp_WindowsGetStringRawBuffer
0x180074d00  mov     [rsp+130h+var_B8], rax
0x180074d05  xor     edx, edx; length
0x180074d07  mov     rcx, [rsp+130h+var_C8]; string
0x180074d0c  call    cs:__imp_WindowsGetStringRawBuffer
0x180074d12  mov     [rbp+30h+var_B0], rax
0x180074d16  mov     [rsp+130h+var_C0], 1
0x180074d1e  xor     edx, edx; length
0x180074d20  mov     rcx, [rbp+30h+string]; string
0x180074d24  call    cs:__imp_WindowsGetStringRawBuffer
0x180074d2a  mov     [rbp+30h+var_A8], rax
0x180074d2e  xor     edx, edx; length
0x180074d30  mov     rcx, [rsp+130h+newString]; string
0x180074d35  call    cs:__imp_WindowsGetStringRawBuffer
0x180074d3b  mov     [rbp+30h+var_A0], rax
0x180074d3f  xor     edx, edx; length
0x180074d41  mov     rcx, [rbp+30h+var_60]; string
0x180074d45  call    cs:__imp_WindowsGetStringRawBuffer
0x180074d4b  mov     [rbp+30h+var_98], rax
0x180074d4f  xor     edx, edx; length
0x180074d51  mov     rcx, [rbp+30h+var_38]; string
0x180074d55  call    cs:__imp_WindowsGetStringRawBuffer
0x180074d5b  mov     [rbp+30h+var_90], rax
0x180074d5f  lea     rax, [rsp+130h+var_B8]
0x180074d64  mov     [rsp+130h+var_E0], rax
0x180074d69  lea     rax, [rbp+30h+var_B0]
0x180074d6d  mov     [rsp+130h+var_E8], rax
0x180074d72  lea     rax, [rsp+130h+var_C0]
0x180074d77  mov     [rsp+130h+var_F0], rax
0x180074d7c  lea     rax, [rbp+30h+var_A8]
0x180074d80  mov     [rsp+130h+var_F8], rax
0x180074d85  lea     rax, [rbp+30h+var_A0]
0x180074d89  mov     [rsp+130h+var_100], rax
0x180074d8e  lea     rax, [rbp+30h+var_98]
0x180074d92  mov     [rsp+130h+var_108], rax
0x180074d97  lea     rax, [rbp+30h+var_90]
0x180074d9b  mov     [rsp+130h+var_110], rax
0x180074da0  lea     rdx, unk_1801588A8
0x180074da7  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U1@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@333AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180074dac  lea     rcx, [rbp+30h+var_60]; struct AccountSystemOnlyInfo *
0x180074db0  call    ?UpdateAccountSystemOnlyData@@YAJAEAUAccountSystemOnlyInfo@@@Z; UpdateAccountSystemOnlyData(AccountSystemOnlyInfo &)
0x180074db5  mov     ebx, eax
0x180074db7  mov     rcx, [rsp+130h+var_C8]; string
0x180074dbc  test    rcx, rcx
0x180074dbf  jz      short loc_180074DC8
0x180074dc1  call    cs:__imp_WindowsDeleteString
0x180074dc7  nop
0x180074dc8  mov     rcx, [rsp+130h+newString]; string
0x180074dcd  test    rcx, rcx
0x180074dd0  jz      short loc_180074DD9
0x180074dd2  call    cs:__imp_WindowsDeleteString
0x180074dd8  nop
0x180074dd9  lea     rcx, [rbp+30h+var_88]; this
0x180074ddd  call    ?InternalRelease@StoredObjectId@TokenBroker@Authentication@Security@Internal@Windows@@AEAAXXZ; Windows::Internal::Security::Authentication::TokenBroker::StoredObjectId::InternalRelease(void)
0x180074de2  nop
0x180074de3  lea     rcx, [rbp+30h+var_60]; this
0x180074de7  call    ??1AccountSystemOnlyInfo@@QEAA@XZ; AccountSystemOnlyInfo::~AccountSystemOnlyInfo(void)
0x180074dec  mov     eax, ebx
0x180074dee  lea     r11, [rsp+130h+var_s0]
0x180074df6  mov     rbx, [r11+10h]
0x180074dfa  mov     rdi, [r11+20h]
0x180074dfe  mov     rsp, r11
0x180074e01  pop     rbp
0x180074e02  retn
```
