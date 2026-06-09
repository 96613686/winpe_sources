# CUserIdentityProvider::GetDefaultAccount(FlightingAccountType *,ushort * *)

- ea: `0x1800b2934`
- end: `0x1800b2b68`
- name: `?GetDefaultAccount@CUserIdentityProvider@@AEAAJPEAW4FlightingAccountType@@PEAPEAG@Z`
- size: `564`
- prototype: `__int64 __fastcall(CUserIdentityProvider *__hidden this, enum FlightingAccountType *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800b53f8`

## callees

- `0x18000cc8c`
- `0x180013da0`
- `0x1800177bc`
- `0x180086644`
- `0x180086944`
- `0x1800961e0`
- `0x1800b148c`
- `0x1800b1d50`
- `0x1800b2934`
- `0x1800b40b8`
- `0x1800b446c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2a84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2b21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2a84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2b21`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800b2a7a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800b2b17`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800b2a7a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800b2b17`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b2a8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b2b2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b2a8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b2b2b`

## string_xrefs

- `0x1800b2984`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b2a5b`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`

## pseudocode

```c
__int64 __fastcall CUserIdentityProvider::GetDefaultAccount(
        CUserIdentityProvider *this,
        enum FlightingAccountType *a2,
        unsigned __int16 **a3)
{
  HANDLE v6; // rdx
  unsigned __int8 v7; // cl
  __int64 result; // rax
  const unsigned __int16 *v9; // rdi
  unsigned int v10; // ebx
  unsigned int v11; // r15d
  unsigned __int64 v12; // rdx
  unsigned int v13; // esi
  __int64 v14; // rcx
  FlightSettingsAPITelemetryClass *v15; // rax
  const unsigned __int16 *v16; // r9
  __int64 v17; // r9
  __int64 v18; // rcx
  FlightSettingsAPITelemetryClass *v19; // rax
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+38h]
  HANDLE Token; // [rsp+68h] [rbp+48h] BYREF
  __int64 v23; // [rsp+78h] [rbp+58h] BYREF

  *(_DWORD *)a2 = 0;
  if ( (int)CUserIdentityProvider::GetPrimaryAccountId(this, a2, a3) >= 0 )
  {
    v10 = 1;
    v11 = 2;
    if ( *(_DWORD *)a2 == 1 )
    {
      v9 = L"MsaPrimary";
    }
    else
    {
      v9 = L"AadPrimary";
      if ( *(_DWORD *)a2 != 2 )
        v9 = L"UnknownAccountType";
    }
  }
  else
  {
    result = CUserIdentityProvider::GetSoleSecondaryAccountId(this, a2, a3);
    if ( (int)result < 0 )
      return result;
    if ( !*a3 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x24F,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
        (const char *)0x80070525LL,
        savedregs);
      return 2147943717LL;
    }
    if ( *(_DWORD *)a2 == 1 )
    {
      v9 = L"MsaSecondary";
    }
    else
    {
      v9 = L"AadSecondary";
      if ( *(_DWORD *)a2 != 2 )
        v9 = L"UnknownAccountType";
    }
    v10 = 0;
    v11 = 6;
  }
  if ( *((_BYTE *)this + 140) )
  {
    Token = 0;
    v13 = UstCommon::CComTemporaryRevertToSelf::RevertToSelf(&Token);
    if ( (int)(v13 + 0x80000000) >= 0 && v13 != -2147023888 )
    {
      if ( FlightSettingsAPITelemetryClass::IsEnabled(v13, v12) )
      {
        v15 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                                   v14,
                                                   _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
        FlightSettingsAPITelemetryClass::CComTemporaryRevertToSelfFailed_(v15, v13);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x27B,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
        (const char *)v13,
        savedregs);
      if ( Token )
      {
        if ( !SetThreadToken(0, Token) )
          GetLastError();
        CloseHandle(Token);
      }
      return v13;
    }
    v16 = *a3;
    v23 = -2147483646;
    FSRegUtils::SetFlightingRegString((HKEY *)&v23, 4u, L"Id", v16);
    v23 = -2147483646;
    FSRegUtils::SetFlightingRegDWORD(&v23, 4, L"Status", v11);
    v17 = *(unsigned int *)a2;
    v23 = -2147483646;
    FSRegUtils::SetFlightingRegDWORD(&v23, 4, L"Type", v17);
    v23 = -2147483646;
    FSRegUtils::SetFlightingRegDWORD(&v23, 4, L"IsPrimary", v10);
    v6 = Token;
    if ( Token )
    {
      if ( !SetThreadToken(0, Token) )
        GetLastError();
      CloseHandle(Token);
    }
  }
  if ( FlightSettingsAPITelemetryClass::IsEnabled(v7, (unsigned __int64)v6) )
  {
    v19 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                               v18,
                                               _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
    FlightSettingsAPITelemetryClass::FlightingAccountDefaulted_(v19, v9);
  }
  return 0;
}

```

## disassembly

```asm
0x1800b2934  mov     [rsp-38h+arg_0], rbx
0x1800b2939  push    rbp
0x1800b293a  push    rsi
0x1800b293b  push    rdi
0x1800b293c  push    r12
0x1800b293e  push    r13
0x1800b2940  push    r14
0x1800b2942  push    r15; int
0x1800b2944  mov     rbp, rsp
0x1800b2947  sub     rsp, 20h
0x1800b294b  mov     r12, r8
0x1800b294e  mov     dword ptr [rdx], 0
0x1800b2954  mov     r14, rdx
0x1800b2957  mov     rsi, rcx
0x1800b295a  call    ?GetPrimaryAccountId@CUserIdentityProvider@@AEAAJPEAW4FlightingAccountType@@PEAPEAG@Z; CUserIdentityProvider::GetPrimaryAccountId(FlightingAccountType *,ushort * *)
0x1800b295f  test    eax, eax
0x1800b2961  jns     short loc_1800B29DA
0x1800b2963  mov     r8, r12; unsigned __int16 **
0x1800b2966  mov     rdx, r14; enum FlightingAccountType *
0x1800b2969  mov     rcx, rsi; this
0x1800b296c  call    ?GetSoleSecondaryAccountId@CUserIdentityProvider@@AEAAJPEAW4FlightingAccountType@@PEAPEAG@Z; CUserIdentityProvider::GetSoleSecondaryAccountId(FlightingAccountType *,ushort * *)
0x1800b2971  test    eax, eax
0x1800b2973  js      loc_1800B2B53
0x1800b2979  cmp     qword ptr [r12], 0
0x1800b297e  jnz     short loc_1800B29A4
0x1800b2980  mov     rcx, [rbp+38h]; this
0x1800b2984  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b298b  mov     ebx, 80070525h
0x1800b2990  mov     edx, 24Fh; void *
0x1800b2995  mov     r9d, ebx; char *
0x1800b2998  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b299d  mov     eax, ebx
0x1800b299f  jmp     loc_1800B2B53
0x1800b29a4  mov     ebx, 1
0x1800b29a9  cmp     [r14], ebx
0x1800b29ac  jnz     short loc_1800B29B7
0x1800b29ae  lea     rdi, aMsasecondary; "MsaSecondary"
0x1800b29b5  jmp     short loc_1800B29D2
0x1800b29b7  mov     r15d, 2
0x1800b29bd  lea     rdi, aAadsecondary; "AadSecondary"
0x1800b29c4  cmp     [r14], r15d
0x1800b29c7  lea     rax, aUnknownaccount; "UnknownAccountType"
0x1800b29ce  cmovnz  rdi, rax
0x1800b29d2  xor     ebx, ebx
0x1800b29d4  lea     r15d, [rbx+6]
0x1800b29d8  jmp     short loc_1800B2A04
0x1800b29da  mov     ebx, 1
0x1800b29df  lea     r15d, [rbx+1]
0x1800b29e3  cmp     [r14], ebx
0x1800b29e6  jnz     short loc_1800B29F1
0x1800b29e8  lea     rdi, aMsaprimary; "MsaPrimary"
0x1800b29ef  jmp     short loc_1800B2A04
0x1800b29f1  lea     rdi, aAadprimary; "AadPrimary"
0x1800b29f8  cmp     [r14], r15d
0x1800b29fb  jz      short loc_1800B2A04
0x1800b29fd  lea     rdi, aUnknownaccount; "UnknownAccountType"
0x1800b2a04  cmp     byte ptr [rsi+8Ch], 0
0x1800b2a0b  jz      loc_1800B2B31
0x1800b2a11  lea     rcx, [rbp+Token]; TokenHandle
0x1800b2a15  mov     [rbp+Token], 0
0x1800b2a1d  call    ?RevertToSelf@CComTemporaryRevertToSelf@UstCommon@@QEAAJXZ; UstCommon::CComTemporaryRevertToSelf::RevertToSelf(void)
0x1800b2a22  mov     esi, eax
0x1800b2a24  mov     eax, 80000000h
0x1800b2a29  lea     ecx, [rsi+rax]; unsigned __int8
0x1800b2a2c  test    eax, ecx
0x1800b2a2e  jnz     short loc_1800B2A9B
0x1800b2a30  cmp     esi, 800703F0h
0x1800b2a36  jz      short loc_1800B2A9B
0x1800b2a38  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x1800b2a3d  test    al, al
0x1800b2a3f  jz      short loc_1800B2A57
0x1800b2a41  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x1800b2a48  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x1800b2a4d  mov     edx, esi; int
0x1800b2a4f  mov     rcx, rax; this
0x1800b2a52  call    ?CComTemporaryRevertToSelfFailed_@FlightSettingsAPITelemetryClass@@QEAAXJ@Z; FlightSettingsAPITelemetryClass::CComTemporaryRevertToSelfFailed_(long)
0x1800b2a57  mov     rcx, [rbp+38h]; this
0x1800b2a5b  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b2a62  mov     r9d, esi; char *
0x1800b2a65  mov     edx, 27Bh; void *
0x1800b2a6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2a6f  mov     rdx, [rbp+Token]; Token
0x1800b2a73  test    rdx, rdx
0x1800b2a76  jz      short loc_1800B2A94
0x1800b2a78  xor     ecx, ecx; Thread
0x1800b2a7a  call    cs:__imp_SetThreadToken
0x1800b2a80  test    eax, eax
0x1800b2a82  jnz     short loc_1800B2A8A
0x1800b2a84  call    cs:__imp_GetLastError
0x1800b2a8a  mov     rcx, [rbp+Token]; hObject
0x1800b2a8e  call    cs:__imp_CloseHandle
0x1800b2a94  mov     eax, esi
0x1800b2a96  jmp     loc_1800B2B53
0x1800b2a9b  mov     r9, [r12]
0x1800b2a9f  lea     r8, aId; "Id"
0x1800b2aa6  mov     esi, 4
0x1800b2aab  lea     rcx, [rbp+arg_18]
0x1800b2aaf  mov     r13, 0FFFFFFFF80000002h
0x1800b2ab6  mov     edx, esi
0x1800b2ab8  mov     [rbp+arg_18], r13
0x1800b2abc  call    ?SetFlightingRegString@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBG2@Z; FSRegUtils::SetFlightingRegString(HKEY__ * const &,FlightingRegistryKey,ushort const *,ushort const *)
0x1800b2ac1  mov     r9d, r15d
0x1800b2ac4  mov     [rbp+arg_18], r13
0x1800b2ac8  lea     r8, aStatus; "Status"
0x1800b2acf  mov     edx, esi
0x1800b2ad1  lea     rcx, [rbp+arg_18]
0x1800b2ad5  call    ?SetFlightingRegDWORD@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGK@Z; FSRegUtils::SetFlightingRegDWORD(HKEY__ * const &,FlightingRegistryKey,ushort const *,ulong)
0x1800b2ada  mov     r9d, [r14]
0x1800b2add  lea     r8, aType; "Type"
0x1800b2ae4  mov     edx, esi
0x1800b2ae6  mov     [rbp+arg_18], r13
0x1800b2aea  lea     rcx, [rbp+arg_18]
0x1800b2aee  call    ?SetFlightingRegDWORD@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGK@Z; FSRegUtils::SetFlightingRegDWORD(HKEY__ * const &,FlightingRegistryKey,ushort const *,ulong)
0x1800b2af3  mov     r9d, ebx
0x1800b2af6  mov     [rbp+arg_18], r13
0x1800b2afa  lea     r8, aIsprimary; "IsPrimary"
0x1800b2b01  mov     edx, esi
0x1800b2b03  lea     rcx, [rbp+arg_18]
0x1800b2b07  call    ?SetFlightingRegDWORD@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGK@Z; FSRegUtils::SetFlightingRegDWORD(HKEY__ * const &,FlightingRegistryKey,ushort const *,ulong)
0x1800b2b0c  mov     rdx, [rbp+Token]; Token
0x1800b2b10  test    rdx, rdx
0x1800b2b13  jz      short loc_1800B2B31
0x1800b2b15  xor     ecx, ecx; Thread
0x1800b2b17  call    cs:__imp_SetThreadToken
0x1800b2b1d  test    eax, eax
0x1800b2b1f  jnz     short loc_1800B2B27
0x1800b2b21  call    cs:__imp_GetLastError
0x1800b2b27  mov     rcx, [rbp+Token]; hObject
0x1800b2b2b  call    cs:__imp_CloseHandle
0x1800b2b31  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x1800b2b36  test    al, al
0x1800b2b38  jz      short loc_1800B2B51
0x1800b2b3a  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x1800b2b41  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x1800b2b46  mov     rdx, rdi; unsigned __int16 *
0x1800b2b49  mov     rcx, rax; this
0x1800b2b4c  call    ?FlightingAccountDefaulted_@FlightSettingsAPITelemetryClass@@QEAAXPEBG@Z; FlightSettingsAPITelemetryClass::FlightingAccountDefaulted_(ushort const *)
0x1800b2b51  xor     eax, eax
0x1800b2b53  mov     rbx, [rsp+20h+arg_0]
0x1800b2b58  add     rsp, 20h
0x1800b2b5c  pop     r15
0x1800b2b5e  pop     r14
0x1800b2b60  pop     r13
0x1800b2b62  pop     r12
0x1800b2b64  pop     rdi
0x1800b2b65  pop     rsi
0x1800b2b66  pop     rbp
0x1800b2b67  retn
```
