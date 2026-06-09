# FSRegUtils::EncryptDataFromString(ushort const *,uchar * *,ulong *)

- ea: `0x180085778`
- end: `0x1800858e8`
- name: `?EncryptDataFromString@FSRegUtils@@CAJPEBGPEAPEAEPEAK@Z`
- size: `368`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180086350`

## callees

- `0x180007b71`
- `0x18000cc6c`
- `0x18000cc8c`
- `0x18008551c`
- `0x1800855dc`
- `0x1800855fc`
- `0x180085778`
- `0x1800861ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800858a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800858a9`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptEncrypt` at `0x180085880`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptEncrypt` at `0x180085880`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x1800857b1`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x1800857b1`

## string_xrefs

- `0x1800857bf`: `onecore\base\flighting\flightsettings\broker\libs\common\fsregutils.cpp`
- `0x1800857fa`: `onecore\base\flighting\flightsettings\broker\libs\common\fsregutils.cpp`
- `0x18008588e`: `onecore\base\flighting\flightsettings\broker\libs\common\fsregutils.cpp`

## pseudocode

```c
__int64 __fastcall FSRegUtils::EncryptDataFromString(
        const unsigned __int16 *Src,
        unsigned __int8 **a2,
        unsigned int *a3)
{
  const char *v6; // r9
  unsigned int LastError; // ebx
  int SymmetricKey; // eax
  __int64 v9; // r9
  __int64 v10; // rdx
  __int64 v11; // rax
  unsigned __int8 *v12; // rbx
  const char *v13; // r9
  unsigned int v14; // edi
  int dwFlags; // [rsp+20h] [rbp-48h]
  HCRYPTKEY hKey; // [rsp+40h] [rbp-28h] BYREF
  HCRYPTPROV phProv; // [rsp+48h] [rbp-20h] BYREF
  BYTE *pbData; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]
  size_t Size; // [rsp+B8h] [rbp+50h] BYREF

  phProv = 0;
  if ( !CryptAcquireContextW(&phProv, 0, L"Microsoft Enhanced RSA and AES Cryptographic Provider", 0x18u, 0xF0000040) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x12F,
                  (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\common\\fsregutils.cpp",
                  v6);
    goto LABEL_15;
  }
  hKey = 0;
  SymmetricKey = FSRegUtils::GetSymmetricKey(phProv, &hKey);
  LastError = SymmetricKey;
  if ( SymmetricKey < 0 )
  {
    v9 = (unsigned int)SymmetricKey;
    v10 = 306;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\common\\fsregutils.cpp",
      (const char *)v9,
      dwFlags);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int CryptDestroyKey(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int CryptDestroyKey(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hKey);
    goto LABEL_15;
  }
  v11 = -1;
  do
    ++v11;
  while ( Src[v11] );
  LODWORD(Size) = 2 * v11 + 2;
  wil::make_unique_cotaskmem_nothrow<unsigned char [0]>(&pbData, (unsigned int)Size);
  v12 = pbData;
  if ( !pbData )
  {
    LastError = -2147024882;
    v10 = 312;
    v9 = 2147942414LL;
    goto LABEL_5;
  }
  memcpy_0(pbData, Src, (unsigned int)Size);
  if ( CryptEncrypt(hKey, 0, 1, 0, v12, (DWORD *)&Size, Size) )
  {
    *a3 = Size;
    *a2 = v12;
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int CryptDestroyKey(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int CryptDestroyKey(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hKey);
    LastError = 0;
  }
  else
  {
    v14 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x13E,
            (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\common\\fsregutils.cpp",
            v13);
    if ( v12 )
      CoTaskMemFree(v12);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int CryptDestroyKey(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&int CryptDestroyKey(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&hKey);
    LastError = v14;
  }
LABEL_15:
  __1__unique_storage_U__resource_policy__KP6AX_K__E_1_CryptReleaseContextNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd___K_K_0A___T_details_wil___details_wil__QEAA_XZ(&phProv);
  return LastError;
}

```

## disassembly

```asm
0x180085778  push    rbp
0x18008577a  push    rbx
0x18008577b  push    rsi
0x18008577c  push    rdi
0x18008577d  push    r14
0x18008577f  push    r15
0x180085781  mov     rbp, rsp
0x180085784  sub     rsp, 68h
0x180085788  xor     r15d, r15d
0x18008578b  mov     [rsp+68h+dwFlags], 0F0000040h; int
0x180085793  mov     rsi, r8
0x180085796  mov     [rbp+phProv], r15
0x18008579a  mov     r14, rdx
0x18008579d  lea     r8, szProvider; "Microsoft Enhanced RSA and AES Cryptogr"...
0x1800857a4  mov     rdi, rcx
0x1800857a7  xor     edx, edx; szContainer
0x1800857a9  lea     r9d, [r15+18h]; dwProvType
0x1800857ad  lea     rcx, [rbp+phProv]; phProv
0x1800857b1  call    cs:__imp_CryptAcquireContextW
0x1800857b7  test    eax, eax
0x1800857b9  jnz     short loc_1800857D7
0x1800857bb  mov     rcx, [rbp+30h]; this
0x1800857bf  lea     r8, aOnecoreBaseFli_5; "onecore\\base\\flighting\\flightsetting"...
0x1800857c6  mov     edx, 12Fh; void *
0x1800857cb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800857d0  mov     ebx, eax
0x1800857d2  jmp     loc_1800858D0
0x1800857d7  mov     rcx, [rbp+phProv]; hProv
0x1800857db  lea     rdx, [rbp+hKey]; phKey
0x1800857df  mov     [rbp+hKey], r15
0x1800857e3  call    ?GetSymmetricKey@FSRegUtils@@CAJ_KPEA_K@Z; FSRegUtils::GetSymmetricKey(unsigned __int64,unsigned __int64 *)
0x1800857e8  mov     ebx, eax
0x1800857ea  test    eax, eax
0x1800857ec  jns     short loc_180085814
0x1800857ee  mov     r9d, eax; char *
0x1800857f1  mov     edx, 132h; void *
0x1800857f6  mov     rcx, [rbp+30h]; this
0x1800857fa  lea     r8, aOnecoreBaseFli_5; "onecore\\base\\flighting\\flightsetting"...
0x180085801  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085806  lea     rcx, [rbp+hKey]
0x18008580a  call    ??1?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?CryptDestroyKey@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&CryptDestroyKey(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&CryptDestroyKey(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18008580f  jmp     loc_1800858D0
0x180085814  or      rax, 0FFFFFFFFFFFFFFFFh
0x180085818  inc     rax
0x18008581b  cmp     [rdi+rax*2], r15w
0x180085820  jnz     short loc_180085818
0x180085822  lea     eax, ds:2[rax*2]
0x180085829  mov     edx, eax
0x18008582b  lea     rcx, [rbp+pbData]
0x18008582f  mov     dword ptr [rbp+Size], eax
0x180085832  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<uchar [0]>(unsigned __int64)
0x180085837  mov     rbx, [rbp+pbData]
0x18008583b  test    rbx, rbx
0x18008583e  jnz     short loc_18008584F
0x180085840  mov     ebx, 8007000Eh
0x180085845  mov     edx, 138h
0x18008584a  mov     r9d, ebx
0x18008584d  jmp     short loc_1800857F6
0x18008584f  mov     r8d, dword ptr [rbp+Size]; Size
0x180085853  mov     rdx, rdi; Src
0x180085856  mov     rcx, rbx; void *
0x180085859  call    memcpy_0
0x18008585e  mov     eax, dword ptr [rbp+Size]
0x180085861  xor     r9d, r9d; dwFlags
0x180085864  mov     rcx, [rbp+hKey]; hKey
0x180085868  xor     edx, edx; hHash
0x18008586a  mov     [rsp+68h+dwBufLen], eax; dwBufLen
0x18008586e  lea     rax, [rbp+Size]
0x180085872  mov     [rsp+68h+pdwDataLen], rax; pdwDataLen
0x180085877  lea     r8d, [r9+1]; Final
0x18008587b  mov     qword ptr [rsp+68h+dwFlags], rbx; pbData
0x180085880  call    cs:__imp_CryptEncrypt
0x180085886  test    eax, eax
0x180085888  jnz     short loc_1800858BC
0x18008588a  mov     rcx, [rbp+30h]; this
0x18008588e  lea     r8, aOnecoreBaseFli_5; "onecore\\base\\flighting\\flightsetting"...
0x180085895  mov     edx, 13Eh; void *
0x18008589a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008589f  mov     edi, eax
0x1800858a1  test    rbx, rbx
0x1800858a4  jz      short loc_1800858AF
0x1800858a6  mov     rcx, rbx; pv
0x1800858a9  call    cs:__imp_CoTaskMemFree
0x1800858af  lea     rcx, [rbp+hKey]
0x1800858b3  call    ??1?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?CryptDestroyKey@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&CryptDestroyKey(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&CryptDestroyKey(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800858b8  mov     ebx, edi
0x1800858ba  jmp     short loc_1800858D0
0x1800858bc  mov     eax, dword ptr [rbp+Size]
0x1800858bf  lea     rcx, [rbp+hKey]
0x1800858c3  mov     [rsi], eax
0x1800858c5  mov     [r14], rbx
0x1800858c8  call    ??1?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?CryptDestroyKey@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&CryptDestroyKey(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&CryptDestroyKey(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1800858cd  mov     ebx, r15d
0x1800858d0  lea     rcx, [rbp+phProv]
0x1800858d4  call    ??1?$unique_storage@U?$resource_policy@_KP6AX_K@_E$1?CryptReleaseContextNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800858d9  mov     eax, ebx
0x1800858db  add     rsp, 68h
0x1800858df  pop     r15
0x1800858e1  pop     r14
0x1800858e3  pop     rdi
0x1800858e4  pop     rsi
0x1800858e5  pop     rbx
0x1800858e6  pop     rbp
0x1800858e7  retn
```
