# CConnectedSearchShellService::GetAcceptLanguage(ushort * *)

- ea: `0x1801ab400`
- end: `0x1801ab5e9`
- name: `?GetAcceptLanguage@CConnectedSearchShellService@@UEAAJPEAPEAG@Z`
- size: `489`
- prototype: `__int64 __fastcall(CConnectedSearchShellService *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callees

- `0x18002fc18`
- `0x180041f54`
- `0x180053740`
- `0x180092fd0`
- `0x1800b2c68`
- `0x1800ba13c`
- `0x1800f9388`
- `0x180142e10`
- `0x1801ab400`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1801ab587`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1801ab587`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x1801ab445`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x1801ab495`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x1801ab445`
- `api-ms-win-core-localization-l1-2-0!GetThreadPreferredUILanguages` at `0x1801ab495`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ab4d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ab53b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ab4d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801ab53b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ab516`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801ab516`
- `Bcp47Langs!Bcp47Normalize` at `0x1801ab4fe`
- `Bcp47Langs!Bcp47Normalize` at `0x1801ab4fe`

## pseudocode

```c
__int64 __fastcall CConnectedSearchShellService::GetAcceptLanguage(
        CConnectedSearchShellService *this,
        unsigned __int16 **a2)
{
  __int64 v3; // rcx
  int Error; // edi
  PZZWSTR v5; // rbx
  __int64 v6; // rax
  PCWSTR StringRawBuffer; // rax
  __int64 v8; // rax
  __int64 v9; // rbx
  unsigned __int16 *i; // rsi
  ULONG pcchLanguagesBuffer; // [rsp+20h] [rbp-39h] BYREF
  ULONG pulNumLanguages; // [rsp+24h] [rbp-35h] BYREF
  HSTRING string; // [rsp+28h] [rbp-31h] BYREF
  PZZWSTR pwszLanguagesBuffer; // [rsp+30h] [rbp-29h] BYREF
  unsigned __int16 *v16; // [rsp+38h] [rbp-21h] BYREF
  __int64 v17; // [rsp+40h] [rbp-19h]
  __int64 v18; // [rsp+48h] [rbp-11h]
  PZZWSTR v19; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v20[32]; // [rsp+58h] [rbp-1h] BYREF

  *a2 = 0;
  pulNumLanguages = 0;
  pcchLanguagesBuffer = 0;
  if ( GetThreadPreferredUILanguages(0x38u, &pulNumLanguages, 0, &pcchLanguagesBuffer)
    || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    pwszLanguagesBuffer = 0;
    Error = _AllocArray<unsigned short,CTCoAllocPolicy>(v3, 1, pcchLanguagesBuffer, &pwszLanguagesBuffer);
    if ( Error >= 0 )
    {
      v5 = pwszLanguagesBuffer;
      Error = GetThreadPreferredUILanguages(0x38u, &pulNumLanguages, pwszLanguagesBuffer, &pcchLanguagesBuffer)
            ? 0
            : ResultFromKnownLastError();
      if ( Error >= 0 )
      {
        v16 = 0;
        v17 = 0;
        v18 = 0;
        do
        {
          if ( !*v5 )
            break;
          string = 0;
          WindowsDeleteString(0);
          string = 0;
          v19 = v5;
          v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v20, &v19);
          Error = Bcp47Normalize(*(_QWORD *)(v6 + 24), &string);
          if ( Error >= 0 )
          {
            StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
            Error = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::ConcatFormat(
                      &v16,
                      L"%s, ",
                      StringRawBuffer);
          }
          WindowsDeleteString(string);
          v8 = -1;
          do
            ++v8;
          while ( v5[v8] );
          v5 += v8 + 1;
        }
        while ( Error >= 0 );
        Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_EnsureCount(&v16);
        v9 = v17;
        for ( i = v16; v9; --v9 )
        {
          if ( !wcschr(L", ", i[v9 - 1]) )
            break;
        }
        if ( v9 != v17 )
          i[v9] = 0;
        v16 = 0;
        v18 = 0;
        v17 = 0;
        *a2 = i;
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v16);
      }
    }
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&pwszLanguagesBuffer);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1801ab400  push    rbp
0x1801ab402  push    rbx
0x1801ab403  push    rsi
0x1801ab404  push    rdi
0x1801ab405  push    r14
0x1801ab407  push    r15
0x1801ab409  lea     rbp, [rsp-2Fh]
0x1801ab40e  sub     rsp, 88h
0x1801ab415  mov     rax, cs:__security_cookie
0x1801ab41c  xor     rax, rsp
0x1801ab41f  mov     [rbp+57h+var_38], rax
0x1801ab423  xor     r15d, r15d
0x1801ab426  lea     r9, [rbp+57h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x1801ab42a  mov     r14, rdx
0x1801ab42d  mov     [rdx], r15
0x1801ab430  xor     r8d, r8d; pwszLanguagesBuffer
0x1801ab433  mov     [rbp+57h+pulNumLanguages], r15d
0x1801ab437  lea     rdx, [rbp+57h+pulNumLanguages]; pulNumLanguages
0x1801ab43b  mov     [rbp+57h+pcchLanguagesBuffer], r15d
0x1801ab43f  lea     esi, [r15+38h]
0x1801ab443  mov     ecx, esi; dwFlags
0x1801ab445  call    cs:__imp_GetThreadPreferredUILanguages
0x1801ab44c  nop     dword ptr [rax+rax+00h]
0x1801ab451  test    eax, eax
0x1801ab453  jnz     short loc_1801AB464
0x1801ab455  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1801ab45a  mov     edi, eax
0x1801ab45c  test    eax, eax
0x1801ab45e  js      loc_1801AB5CA
0x1801ab464  mov     r8d, [rbp+57h+pcchLanguagesBuffer]
0x1801ab468  lea     r9, [rbp+57h+pwszLanguagesBuffer]
0x1801ab46c  mov     edx, 1
0x1801ab471  mov     [rbp+57h+pwszLanguagesBuffer], r15
0x1801ab475  call    ??$_AllocArray@GVCTCoAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTCoAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x1801ab47a  mov     edi, eax
0x1801ab47c  test    eax, eax
0x1801ab47e  js      loc_1801AB5C1
0x1801ab484  mov     rbx, [rbp+57h+pwszLanguagesBuffer]
0x1801ab488  lea     r9, [rbp+57h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x1801ab48c  mov     r8, rbx; pwszLanguagesBuffer
0x1801ab48f  lea     rdx, [rbp+57h+pulNumLanguages]; pulNumLanguages
0x1801ab493  mov     ecx, esi; dwFlags
0x1801ab495  call    cs:__imp_GetThreadPreferredUILanguages
0x1801ab49c  nop     dword ptr [rax+rax+00h]
0x1801ab4a1  test    eax, eax
0x1801ab4a3  jz      short loc_1801AB4AA
0x1801ab4a5  mov     edi, r15d
0x1801ab4a8  jmp     short loc_1801AB4B1
0x1801ab4aa  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1801ab4af  mov     edi, eax
0x1801ab4b1  test    edi, edi
0x1801ab4b3  js      loc_1801AB5C1
0x1801ab4b9  mov     [rbp+57h+var_78], r15
0x1801ab4bd  mov     [rbp+57h+var_70], r15
0x1801ab4c1  mov     [rbp+57h+var_68], r15
0x1801ab4c5  cmp     [rbx], r15w
0x1801ab4c9  jz      loc_1801AB565
0x1801ab4cf  xor     ecx, ecx; string
0x1801ab4d1  mov     [rbp+57h+string], r15
0x1801ab4d5  call    cs:__imp_WindowsDeleteString
0x1801ab4dc  nop     dword ptr [rax+rax+00h]
0x1801ab4e1  lea     rdx, [rbp+57h+var_60]
0x1801ab4e5  mov     [rbp+57h+string], r15
0x1801ab4e9  lea     rcx, [rbp+57h+var_58]
0x1801ab4ed  mov     [rbp+57h+var_60], rbx
0x1801ab4f1  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801ab4f6  lea     rdx, [rbp+57h+string]
0x1801ab4fa  mov     rcx, [rax+18h]
0x1801ab4fe  call    cs:__imp_Bcp47Normalize
0x1801ab505  nop     dword ptr [rax+rax+00h]
0x1801ab50a  mov     edi, eax
0x1801ab50c  test    eax, eax
0x1801ab50e  js      short loc_1801AB537
0x1801ab510  mov     rcx, [rbp+57h+string]; string
0x1801ab514  xor     edx, edx; length
0x1801ab516  call    cs:__imp_WindowsGetStringRawBuffer
0x1801ab51d  nop     dword ptr [rax+rax+00h]
0x1801ab522  mov     r8, rax
0x1801ab525  lea     rdx, aS_2; "%s, "
0x1801ab52c  lea     rcx, [rbp+57h+var_78]
0x1801ab530  call    ?ConcatFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x1801ab535  mov     edi, eax
0x1801ab537  mov     rcx, [rbp+57h+string]; string
0x1801ab53b  call    cs:__imp_WindowsDeleteString
0x1801ab542  nop     dword ptr [rax+rax+00h]
0x1801ab547  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801ab54b  inc     rax
0x1801ab54e  cmp     [rbx+rax*2], r15w
0x1801ab553  jnz     short loc_1801AB54B
0x1801ab555  lea     rbx, [rbx+rax*2]
0x1801ab559  add     rbx, 2
0x1801ab55d  test    edi, edi
0x1801ab55f  jns     loc_1801AB4C5
0x1801ab565  lea     rcx, [rbp+57h+var_78]
0x1801ab569  call    ?_EnsureCount@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_EnsureCount(void)
0x1801ab56e  mov     rbx, [rbp+57h+var_70]
0x1801ab572  mov     rsi, [rbp+57h+var_78]
0x1801ab576  test    rbx, rbx
0x1801ab579  jz      short loc_1801AB59E
0x1801ab57b  movzx   edx, word ptr [rsi+rbx*2-2]; Ch
0x1801ab580  lea     rcx, asc_180424104; ", "
0x1801ab587  call    cs:__imp_wcschr
0x1801ab58e  nop     dword ptr [rax+rax+00h]
0x1801ab593  test    rax, rax
0x1801ab596  jz      short loc_1801AB59E
0x1801ab598  sub     rbx, 1
0x1801ab59c  jnz     short loc_1801AB57B
0x1801ab59e  cmp     rbx, [rbp+57h+var_70]
0x1801ab5a2  jz      short loc_1801AB5A9
0x1801ab5a4  mov     [rsi+rbx*2], r15w
0x1801ab5a9  lea     rcx, [rbp+57h+var_78]
0x1801ab5ad  mov     [rbp+57h+var_78], r15
0x1801ab5b1  mov     [rbp+57h+var_68], r15
0x1801ab5b5  mov     [rbp+57h+var_70], r15
0x1801ab5b9  mov     [r14], rsi
0x1801ab5bc  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801ab5c1  lea     rcx, [rbp+57h+pwszLanguagesBuffer]
0x1801ab5c5  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1801ab5ca  mov     eax, edi
0x1801ab5cc  mov     rcx, [rbp+57h+var_38]
0x1801ab5d0  xor     rcx, rsp; StackCookie
0x1801ab5d3  call    __security_check_cookie
0x1801ab5d8  add     rsp, 88h
0x1801ab5df  pop     r15
0x1801ab5e1  pop     r14
0x1801ab5e3  pop     rdi
0x1801ab5e4  pop     rsi
0x1801ab5e5  pop     rbx
0x1801ab5e6  pop     rbp
0x1801ab5e7  retn
```
