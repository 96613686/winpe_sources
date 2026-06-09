# FSRegUtils::DecryptStringFromByteArray(uchar *,ulong,ushort * *)

- ea: `0x18008561c`
- end: `0x18008576f`
- name: `?DecryptStringFromByteArray@FSRegUtils@@CAJPEAEKPEAPEAG@Z`
- size: `339`
- prototype: `__int64 __fastcall(unsigned __int8 *Src, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18008603c`

## callees

- `0x180007b71`
- `0x18000cc6c`
- `0x18000cc8c`
- `0x18008551c`
- `0x1800855dc`
- `0x1800855fc`
- `0x18008561c`
- `0x1800861ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085736`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085736`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDecrypt` at `0x18008570d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDecrypt` at `0x18008570d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180085658`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180085658`

## string_xrefs

- `0x180085666`: `onecore\base\flighting\flightsettings\broker\libs\common\fsregutils.cpp`
- `0x1800856a5`: `onecore\base\flighting\flightsettings\broker\libs\common\fsregutils.cpp`
- `0x18008571b`: `onecore\base\flighting\flightsettings\broker\libs\common\fsregutils.cpp`

## pseudocode

```c
__int64 __fastcall FSRegUtils::DecryptStringFromByteArray(unsigned __int8 *Src, int a2, unsigned __int16 **a3)
{
  const char *v5; // r9
  unsigned int LastError; // ebx
  int SymmetricKey; // eax
  __int64 v8; // r9
  __int64 v9; // rdx
  unsigned __int16 *v10; // rbx
  const char *v11; // r9
  unsigned int v12; // edi
  int dwFlags; // [rsp+20h] [rbp-20h]
  HCRYPTPROV phProv; // [rsp+30h] [rbp-10h] BYREF
  BYTE *pbData; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  size_t Size; // [rsp+68h] [rbp+28h] BYREF
  HCRYPTKEY hKey; // [rsp+78h] [rbp+38h] BYREF

  LODWORD(Size) = a2;
  phProv = 0;
  if ( !CryptAcquireContextW(&phProv, 0, L"Microsoft Enhanced RSA and AES Cryptographic Provider", 0x18u, 0xF0000040) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x149,
                  (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\common\\fsregutils.cpp",
                  v5);
    goto LABEL_13;
  }
  hKey = 0;
  SymmetricKey = FSRegUtils::GetSymmetricKey(phProv, &hKey);
  LastError = SymmetricKey;
  if ( SymmetricKey < 0 )
  {
    v8 = (unsigned int)SymmetricKey;
    v9 = 332;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\common\\fsregutils.cpp",
      (const char *)v8,
      dwFlags);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int CryptDestroyKey(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int CryptDestroyKey(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hKey);
    goto LABEL_13;
  }
  wil::make_unique_cotaskmem_nothrow<unsigned char [0]>(&pbData, (unsigned int)Size);
  v10 = (unsigned __int16 *)pbData;
  if ( !pbData )
  {
    LastError = -2147024882;
    v9 = 335;
    v8 = 2147942414LL;
    goto LABEL_5;
  }
  memcpy_0(pbData, Src, (unsigned int)Size);
  if ( CryptDecrypt(hKey, 0, 1, 0, (BYTE *)v10, (DWORD *)&Size) )
  {
    *a3 = v10;
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int CryptDestroyKey(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int CryptDestroyKey(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hKey);
    LastError = 0;
  }
  else
  {
    v12 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x154,
            (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\common\\fsregutils.cpp",
            v11);
    if ( v10 )
      CoTaskMemFree(v10);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int CryptDestroyKey(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int CryptDestroyKey(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hKey);
    LastError = v12;
  }
LABEL_13:
  __1__unique_storage_U__resource_policy__KP6AX_K__E_1_CryptReleaseContextNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd___K_K_0A___T_details_wil___details_wil__QEAA_XZ(&phProv);
  return LastError;
}

```

## disassembly

```asm
0x18008561c  mov     [rsp-18h+arg_0], rbx
0x180085621  mov     dword ptr [rsp-18h+Size], edx
0x180085625  push    rbp
0x180085626  push    rsi
0x180085627  push    rdi
0x180085628  mov     rbp, rsp
0x18008562b  sub     rsp, 40h
0x18008562f  mov     rdi, r8
0x180085632  mov     [rbp+phProv], 0
0x18008563a  mov     rsi, rcx
0x18008563d  mov     [rsp+40h+dwFlags], 0F0000040h; int
0x180085645  lea     r8, szProvider; "Microsoft Enhanced RSA and AES Cryptogr"...
0x18008564c  mov     r9d, 18h; dwProvType
0x180085652  lea     rcx, [rbp+phProv]; phProv
0x180085656  xor     edx, edx; szContainer
0x180085658  call    cs:__imp_CryptAcquireContextW
0x18008565e  test    eax, eax
0x180085660  jnz     short loc_18008567E
0x180085662  mov     rcx, [rbp+18h]; this
0x180085666  lea     r8, aOnecoreBaseFli_5; "onecore\\base\\flighting\\flightsetting"...
0x18008566d  mov     edx, 149h; void *
0x180085672  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180085677  mov     ebx, eax
0x180085679  jmp     loc_180085757
0x18008567e  mov     rcx, [rbp+phProv]; hProv
0x180085682  lea     rdx, [rbp+hKey]; phKey
0x180085686  mov     [rbp+hKey], 0
0x18008568e  call    ?GetSymmetricKey@FSRegUtils@@CAJ_KPEA_K@Z; FSRegUtils::GetSymmetricKey(unsigned __int64,unsigned __int64 *)
0x180085693  mov     ebx, eax
0x180085695  test    eax, eax
0x180085697  jns     short loc_1800856BF
0x180085699  mov     r9d, eax; char *
0x18008569c  mov     edx, 14Ch; void *
0x1800856a1  mov     rcx, [rbp+18h]; this
0x1800856a5  lea     r8, aOnecoreBaseFli_5; "onecore\\base\\flighting\\flightsetting"...
0x1800856ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800856b1  lea     rcx, [rbp+hKey]
0x1800856b5  call    ??1?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?CryptDestroyKey@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&CryptDestroyKey(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&CryptDestroyKey(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800856ba  jmp     loc_180085757
0x1800856bf  mov     edx, dword ptr [rbp+Size]
0x1800856c2  lea     rcx, [rbp+pbData]
0x1800856c6  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<uchar [0]>(unsigned __int64)
0x1800856cb  mov     rbx, [rbp+pbData]
0x1800856cf  test    rbx, rbx
0x1800856d2  jnz     short loc_1800856E3
0x1800856d4  mov     ebx, 8007000Eh
0x1800856d9  mov     edx, 14Fh
0x1800856de  mov     r9d, ebx
0x1800856e1  jmp     short loc_1800856A1
0x1800856e3  mov     r8d, dword ptr [rbp+Size]; Size
0x1800856e7  mov     rdx, rsi; Src
0x1800856ea  mov     rcx, rbx; void *
0x1800856ed  call    memcpy_0
0x1800856f2  mov     rcx, [rbp+hKey]; hKey
0x1800856f6  lea     rax, [rbp+Size]
0x1800856fa  xor     r9d, r9d; dwFlags
0x1800856fd  mov     [rsp+40h+pdwDataLen], rax; pdwDataLen
0x180085702  xor     edx, edx; hHash
0x180085704  mov     qword ptr [rsp+40h+dwFlags], rbx; pbData
0x180085709  lea     r8d, [r9+1]; Final
0x18008570d  call    cs:__imp_CryptDecrypt
0x180085713  test    eax, eax
0x180085715  jnz     short loc_180085749
0x180085717  mov     rcx, [rbp+18h]; this
0x18008571b  lea     r8, aOnecoreBaseFli_5; "onecore\\base\\flighting\\flightsetting"...
0x180085722  mov     edx, 154h; void *
0x180085727  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008572c  mov     edi, eax
0x18008572e  test    rbx, rbx
0x180085731  jz      short loc_18008573C
0x180085733  mov     rcx, rbx; pv
0x180085736  call    cs:__imp_CoTaskMemFree
0x18008573c  lea     rcx, [rbp+hKey]
0x180085740  call    ??1?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?CryptDestroyKey@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&CryptDestroyKey(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&CryptDestroyKey(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180085745  mov     ebx, edi
0x180085747  jmp     short loc_180085757
0x180085749  lea     rcx, [rbp+hKey]
0x18008574d  mov     [rdi], rbx
0x180085750  call    ??1?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?CryptDestroyKey@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&CryptDestroyKey(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&CryptDestroyKey(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180085755  xor     ebx, ebx
0x180085757  lea     rcx, [rbp+phProv]
0x18008575b  call    ??1?$unique_storage@U?$resource_policy@_KP6AX_K@_E$1?CryptReleaseContextNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180085760  mov     eax, ebx
0x180085762  mov     rbx, [rsp+40h+arg_0]
0x180085767  add     rsp, 40h
0x18008576b  pop     rdi
0x18008576c  pop     rsi
0x18008576d  pop     rbp
0x18008576e  retn
```
