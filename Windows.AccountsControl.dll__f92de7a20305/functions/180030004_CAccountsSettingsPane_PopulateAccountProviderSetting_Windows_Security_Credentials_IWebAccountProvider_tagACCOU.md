# CAccountsSettingsPane::_PopulateAccountProviderSetting(Windows::Security::Credentials::IWebAccountProvider *,tagACCOUNT_PROVIDER_SETTING *)

- ea: `0x180030004`
- end: `0x1800301cc`
- name: `?_PopulateAccountProviderSetting@CAccountsSettingsPane@@AEAAJPEAUIWebAccountProvider@Credentials@Security@Windows@@PEAUtagACCOUNT_PROVIDER_SETTING@@@Z`
- size: `456`
- prototype: `__int64 __fastcall(CAccountsSettingsPane *__hidden this, struct Windows::Security::Credentials::IWebAccountProvider *, struct tagACCOUNT_PROVIDER_SETTING *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002aa70`
- `0x1800303c8`

## callees

- `0x180011ffc`
- `0x180018f90`
- `0x18001c434`
- `0x180030004`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030036`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800300f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003015b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800301ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180030036`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800300f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003015b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800301ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180030080`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003012d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180030080`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003012d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CAccountsSettingsPane::_PopulateAccountProviderSetting(
        CAccountsSettingsPane *this,
        struct Windows::Security::Credentials::IWebAccountProvider *a2,
        struct tagACCOUNT_PROVIDER_SETTING *a3)
{
  __int64 (__fastcall *v5)(struct Windows::Security::Credentials::IWebAccountProvider *, HSTRING *); // rbx
  int v6; // edi
  __int64 v7; // rsi
  PCWSTR StringRawBuffer; // rax
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 v11; // r14
  __int64 v12; // rbx
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rdi
  PCWSTR v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v18; // [rsp+30h] [rbp-30h] BYREF
  __int64 v19; // [rsp+38h] [rbp-28h]
  __int64 v20; // [rsp+40h] [rbp-20h]
  __int64 v21; // [rsp+48h] [rbp-18h] BYREF
  __int64 v22; // [rsp+50h] [rbp-10h]
  __int64 v23; // [rsp+58h] [rbp-8h]
  HSTRING v24; // [rsp+A0h] [rbp+40h] BYREF
  HSTRING string; // [rsp+A8h] [rbp+48h] BYREF
  __int64 v26; // [rsp+B8h] [rbp+58h] BYREF

  v24 = (HSTRING)this;
  string = 0;
  v5 = *(__int64 (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *, HSTRING *))(*(_QWORD *)a2 + 56LL);
  WindowsDeleteString(0);
  string = 0;
  v6 = v5(a2, &string);
  if ( v6 >= 0 )
  {
    v21 = 0;
    v22 = 0;
    v23 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v21);
    v7 = -1;
    v22 = -1;
    v23 = -1;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v10 = -1;
    do
      ++v10;
    while ( StringRawBuffer[v10] );
    v6 = _AllocStringWorker<CTCoAllocPolicy>(&v21, v9, StringRawBuffer);
    if ( v6 >= 0 )
    {
      v26 = 0;
      v11 = 0;
      v18 = 0;
      v19 = 0;
      v20 = 0;
      v6 = (*(__int64 (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *, __int64 *))(*(_QWORD *)a2 + 64LL))(
             a2,
             &v26);
      if ( v6 >= 0 )
      {
        v12 = v26;
        if ( !v26 )
          goto LABEL_12;
        v24 = 0;
        v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v26 + 128LL);
        WindowsDeleteString(0);
        v24 = 0;
        v6 = v13(v12, &v24);
        if ( v6 >= 0 )
        {
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v18);
          v19 = -1;
          v20 = -1;
          v14 = WindowsGetStringRawBuffer(v24, 0);
          do
            ++v7;
          while ( v14[v7] );
          v6 = _AllocStringWorker<CTCoAllocPolicy>(&v18, v15, v14);
          v11 = v18;
        }
        WindowsDeleteString(v24);
        if ( v6 >= 0 )
        {
LABEL_12:
          v16 = v21;
          v21 = 0;
          v23 = 0;
          v22 = 0;
          *(_QWORD *)a3 = v16;
          v18 = 0;
          v20 = 0;
          v19 = 0;
          *((_QWORD *)a3 + 1) = v11;
        }
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v18);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v21);
  }
  WindowsDeleteString(string);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180030004  mov     [rsp-38h+arg_10], rbx
0x180030009  mov     [rsp-38h+arg_0], rcx
0x18003000e  push    rbp
0x18003000f  push    rsi
0x180030010  push    rdi
0x180030011  push    r12
0x180030013  push    r13
0x180030015  push    r14
0x180030017  push    r15
0x180030019  mov     rbp, rsp
0x18003001c  sub     rsp, 60h
0x180030020  mov     r12, r8
0x180030023  mov     r15, rdx
0x180030026  xor     r13d, r13d
0x180030029  mov     [rbp+string], r13
0x18003002d  mov     rax, [rdx]
0x180030030  mov     rbx, [rax+38h]
0x180030034  xor     ecx, ecx; string
0x180030036  call    cs:__imp_WindowsDeleteString
0x18003003c  mov     [rbp+string], r13
0x180030040  lea     rdx, [rbp+string]
0x180030044  mov     rcx, r15
0x180030047  mov     rax, rbx
0x18003004a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003004f  mov     edi, eax
0x180030051  test    eax, eax
0x180030053  js      loc_1800301A8
0x180030059  mov     [rbp+var_18], r13
0x18003005d  mov     [rbp+var_10], r13
0x180030061  mov     [rbp+var_8], r13
0x180030065  lea     rcx, [rbp+var_18]
0x180030069  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003006e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180030072  mov     [rbp+var_10], rsi
0x180030076  mov     [rbp+var_8], rsi
0x18003007a  xor     edx, edx; length
0x18003007c  mov     rcx, [rbp+string]; string
0x180030080  call    cs:__imp_WindowsGetStringRawBuffer
0x180030086  mov     r9, rsi
0x180030089  inc     r9
0x18003008c  cmp     [rax+r9*2], r13w
0x180030091  jnz     short loc_180030089
0x180030093  lea     rcx, [rbp+var_18]
0x180030097  mov     [rsp+60h+var_38], rcx
0x18003009c  mov     r8, rax
0x18003009f  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1800300a4  mov     edi, eax
0x1800300a6  test    eax, eax
0x1800300a8  js      loc_18003019E
0x1800300ae  mov     [rbp+arg_18], r13
0x1800300b2  mov     r14, r13
0x1800300b5  mov     [rbp+var_30], r13
0x1800300b9  mov     [rbp+var_28], r13
0x1800300bd  mov     [rbp+var_20], r13
0x1800300c1  mov     rax, [r15]
0x1800300c4  lea     rdx, [rbp+arg_18]
0x1800300c8  mov     rcx, r15
0x1800300cb  mov     rax, [rax+40h]
0x1800300cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300d4  mov     edi, eax
0x1800300d6  test    eax, eax
0x1800300d8  js      loc_18003018A
0x1800300de  mov     rbx, [rbp+arg_18]
0x1800300e2  test    rbx, rbx
0x1800300e5  jz      short loc_180030165
0x1800300e7  mov     [rbp+arg_0], r13
0x1800300eb  mov     rax, [rbx]
0x1800300ee  mov     rdi, [rax+80h]
0x1800300f5  xor     ecx, ecx; string
0x1800300f7  call    cs:__imp_WindowsDeleteString
0x1800300fd  mov     [rbp+arg_0], r13
0x180030101  lea     rdx, [rbp+arg_0]
0x180030105  mov     rcx, rbx
0x180030108  mov     rax, rdi
0x18003010b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030110  mov     edi, eax
0x180030112  test    eax, eax
0x180030114  js      short loc_180030157
0x180030116  lea     rcx, [rbp+var_30]
0x18003011a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003011f  mov     [rbp+var_28], rsi
0x180030123  mov     [rbp+var_20], rsi
0x180030127  xor     edx, edx; length
0x180030129  mov     rcx, [rbp+arg_0]; string
0x18003012d  call    cs:__imp_WindowsGetStringRawBuffer
0x180030133  inc     rsi
0x180030136  cmp     [rax+rsi*2], r13w
0x18003013b  jnz     short loc_180030133
0x18003013d  lea     rcx, [rbp+var_30]
0x180030141  mov     [rsp+60h+var_38], rcx
0x180030146  mov     r9, rsi
0x180030149  mov     r8, rax
0x18003014c  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180030151  mov     edi, eax
0x180030153  mov     r14, [rbp+var_30]
0x180030157  mov     rcx, [rbp+arg_0]; string
0x18003015b  call    cs:__imp_WindowsDeleteString
0x180030161  test    edi, edi
0x180030163  js      short loc_18003018A
0x180030165  mov     rax, [rbp+var_18]
0x180030169  mov     [rbp+var_18], r13
0x18003016d  mov     [rbp+var_8], r13
0x180030171  mov     [rbp+var_10], r13
0x180030175  mov     [r12], rax
0x180030179  mov     [rbp+var_30], r13
0x18003017d  mov     [rbp+var_20], r13
0x180030181  mov     [rbp+var_28], r13
0x180030185  mov     [r12+8], r14
0x18003018a  lea     rcx, [rbp+var_30]
0x18003018e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180030193  nop
0x180030194  lea     rcx, [rbp+arg_18]
0x180030198  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003019d  nop
0x18003019e  lea     rcx, [rbp+var_18]
0x1800301a2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800301a7  nop
0x1800301a8  mov     rcx, [rbp+string]; string
0x1800301ac  call    cs:__imp_WindowsDeleteString
0x1800301b2  mov     eax, edi
0x1800301b4  mov     rbx, [rsp+60h+arg_10]
0x1800301bc  add     rsp, 60h
0x1800301c0  pop     r15
0x1800301c2  pop     r14
0x1800301c4  pop     r13
0x1800301c6  pop     r12
0x1800301c8  pop     rdi
0x1800301c9  pop     rsi
0x1800301ca  pop     rbp
0x1800301cb  retn
```
