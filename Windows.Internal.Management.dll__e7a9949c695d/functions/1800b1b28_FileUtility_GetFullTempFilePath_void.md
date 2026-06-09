# FileUtility::GetFullTempFilePath(void)

- ea: `0x1800b1b28`
- end: `0x1800b1cf2`
- name: `?GetFullTempFilePath@FileUtility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `458`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `11`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x1800b2220`
- `0x1800b3120`

## callees

- `0x1800011d4`
- `0x180004d50`
- `0x18000578c`
- `0x18000a8a4`
- `0x18000cfdc`
- `0x180024cf0`
- `0x180037a84`
- `0x18003ec00`
- `0x1800ac740`
- `0x1800b1b04`
- `0x1800b1b28`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800b1c25`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800b1c25`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x1800b1c93`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x1800b1c93`
- `CRYPT32!CryptBinaryToStringW` at `0x1800b1c64`
- `CRYPT32!CryptBinaryToStringW` at `0x1800b1c64`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x1800b1b6f`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x1800b1b6f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FileUtility::GetFullTempFilePath(__int64 a1)
{
  int BasicProfileFolderPathAlloc; // eax
  unsigned __int64 v3; // rdx
  unsigned __int64 v4; // rsi
  void *v5; // rax
  HRESULT v6; // eax
  const char *v7; // r9
  HRESULT v8; // eax
  int pcchString; // [rsp+20h] [rbp-79h]
  int pcchStringa; // [rsp+20h] [rbp-79h]
  unsigned __int16 *v12; // [rsp+30h] [rbp-69h] BYREF
  PWSTR pszPath; // [rsp+38h] [rbp-61h] BYREF
  DWORD v14; // [rsp+40h] [rbp-59h] BYREF
  unsigned __int16 **v15; // [rsp+48h] [rbp-51h] BYREF
  __int64 v16; // [rsp+50h] [rbp-49h] BYREF
  char v17; // [rsp+58h] [rbp-41h]
  GUID pguid; // [rsp+60h] [rbp-39h] BYREF
  WCHAR pszString[40]; // [rsp+70h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v12 = 0;
  v15 = &v12;
  v16 = 0;
  v17 = 1;
  BasicProfileFolderPathAlloc = GetBasicProfileFolderPathAlloc(6, 0, &v16);
  if ( BasicProfileFolderPathAlloc < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\fileutility.cpp",
      (const char *)(unsigned int)BasicProfileFolderPathAlloc,
      pcchString);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v15);
  v3 = -1;
  do
    ++v3;
  while ( v12[v3] );
  if ( v3 + 46 < v3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\fileutility.cpp",
      v3 + 46 < v3 ? (const char *)0x80070216LL : 0,
      pcchString);
  v4 = v3 + 46;
  v5 = operator new[](saturated_mul(v4, 2u));
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&pszPath, (__int64)v5);
  StringCchCopyW(pszPath, v4, v12);
  pguid = 0;
  v14 = 38;
  v6 = CoCreateGuid(&pguid);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\fileutility.cpp",
      (const char *)(unsigned int)v6,
      pcchString);
  if ( !CryptBinaryToStringW((const BYTE *)&pguid, 0x10u, 0x4000000Cu, pszString, &v14) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\fileutility.cpp",
      v7);
  v8 = PathCchAppendEx(pszPath, v4, pszString, 1u);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\fileutility.cpp",
      (const char *)(unsigned int)v8,
      pcchStringa);
  std::wstring::wstring(a1, pszPath);
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&pszPath);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v12);
  return a1;
}

```

## disassembly

```asm
0x1800b1b28  push    rbp
0x1800b1b2a  push    rsi
0x1800b1b2b  push    rdi
0x1800b1b2c  push    r14
0x1800b1b2e  lea     rbp, [rsp-3Fh]
0x1800b1b33  sub     rsp, 0D8h
0x1800b1b3a  mov     rax, cs:__security_cookie
0x1800b1b41  xor     rax, rsp
0x1800b1b44  mov     [rbp+57h+var_30], rax
0x1800b1b48  mov     rdi, rcx
0x1800b1b4b  mov     [rbp+57h+var_C0], rcx
0x1800b1b4f  xor     r14d, r14d
0x1800b1b52  mov     [rbp+57h+var_C0], r14
0x1800b1b56  lea     rax, [rbp+57h+var_C0]
0x1800b1b5a  mov     [rbp+57h+var_A8], rax
0x1800b1b5e  mov     [rbp+57h+var_A0], r14
0x1800b1b62  mov     [rbp+57h+var_98], 1
0x1800b1b66  lea     r8, [rbp+57h+var_A0]
0x1800b1b6a  xor     edx, edx
0x1800b1b6c  lea     ecx, [rdx+6]
0x1800b1b6f  call    cs:__imp_GetBasicProfileFolderPathAlloc
0x1800b1b75  mov     rcx, [rbp+5Fh]; this
0x1800b1b79  test    eax, eax
0x1800b1b7b  jns     short loc_1800B1B91
0x1800b1b7d  mov     r9d, eax; char *
0x1800b1b80  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x1800b1b87  lea     edx, [r14+0Ch]; void *
0x1800b1b8b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b1b91  lea     rcx, [rbp+57h+var_A8]
0x1800b1b95  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800b1b9a  mov     rax, [rbp+57h+var_C0]
0x1800b1b9e  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800b1ba2  mov     rdx, r8
0x1800b1ba5  inc     rdx
0x1800b1ba8  cmp     [rax+rdx*2], r14w
0x1800b1bad  jnz     short loc_1800B1BA5
0x1800b1baf  lea     rax, [rdx+2Eh]
0x1800b1bb3  mov     rsi, r8
0x1800b1bb6  cmp     rax, rdx
0x1800b1bb9  cmovnb  rsi, rax
0x1800b1bbd  sbb     r9d, r9d
0x1800b1bc0  and     r9d, 80070216h; char *
0x1800b1bc7  mov     rcx, [rbp+5Fh]; this
0x1800b1bcb  cmp     rax, rdx
0x1800b1bce  jnb     short loc_1800B1BE2
0x1800b1bd0  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x1800b1bd7  mov     edx, 10h; void *
0x1800b1bdc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b1be2  mov     eax, 2
0x1800b1be7  mul     rsi
0x1800b1bea  cmovb   rax, r8
0x1800b1bee  mov     rcx, rax; unsigned __int64
0x1800b1bf1  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800b1bf6  mov     rdx, rax
0x1800b1bf9  lea     rcx, [rbp+57h+pszPath]
0x1800b1bfd  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800b1c02  nop
0x1800b1c03  mov     r8, [rbp+57h+var_C0]; unsigned __int16 *
0x1800b1c07  mov     rdx, rsi; unsigned __int64
0x1800b1c0a  mov     rcx, [rbp+57h+pszPath]; unsigned __int16 *
0x1800b1c0e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b1c13  xorps   xmm0, xmm0
0x1800b1c16  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x1800b1c1a  mov     [rbp+57h+var_B0], 26h ; '&'
0x1800b1c21  lea     rcx, [rbp+57h+pguid]; pguid
0x1800b1c25  call    cs:__imp_CoCreateGuid
0x1800b1c2b  mov     rcx, [rbp+5Fh]; this
0x1800b1c2f  test    eax, eax
0x1800b1c31  jns     short loc_1800B1C48
0x1800b1c33  mov     r9d, eax; char *
0x1800b1c36  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x1800b1c3d  mov     edx, 19h; void *
0x1800b1c42  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b1c48  lea     rax, [rbp+57h+var_B0]
0x1800b1c4c  mov     qword ptr [rsp+0F0h+pcchString], rax; int
0x1800b1c51  lea     r9, [rbp+57h+pszString]; pszString
0x1800b1c55  mov     edx, 10h; cbBinary
0x1800b1c5a  mov     r8d, 4000000Ch; dwFlags
0x1800b1c60  lea     rcx, [rbp+57h+pguid]; pbBinary
0x1800b1c64  call    cs:__imp_CryptBinaryToStringW
0x1800b1c6a  mov     rcx, [rbp+5Fh]; this
0x1800b1c6e  test    eax, eax
0x1800b1c70  jnz     short loc_1800B1C82
0x1800b1c72  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x1800b1c79  lea     edx, [rax+1Bh]; void *
0x1800b1c7c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800b1c82  mov     r9d, 1; dwFlags
0x1800b1c88  lea     r8, [rbp+57h+pszString]; pszMore
0x1800b1c8c  mov     rdx, rsi; cchPath
0x1800b1c8f  mov     rcx, [rbp+57h+pszPath]; pszPath
0x1800b1c93  call    cs:__imp_PathCchAppendEx
0x1800b1c99  mov     rcx, [rbp+5Fh]; this
0x1800b1c9d  test    eax, eax
0x1800b1c9f  jns     short loc_1800B1CB6
0x1800b1ca1  mov     r9d, eax; char *
0x1800b1ca4  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x1800b1cab  mov     edx, 1Eh; void *
0x1800b1cb0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b1cb6  mov     rdx, [rbp+57h+pszPath]
0x1800b1cba  mov     rcx, rdi
0x1800b1cbd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b1cc2  nop
0x1800b1cc3  lea     rcx, [rbp+57h+pszPath]
0x1800b1cc7  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1800b1ccc  nop
0x1800b1ccd  lea     rcx, [rbp+57h+var_C0]
0x1800b1cd1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800b1cd6  mov     rax, rdi
0x1800b1cd9  mov     rcx, [rbp+57h+var_30]
0x1800b1cdd  xor     rcx, rsp; StackCookie
0x1800b1ce0  call    __security_check_cookie
0x1800b1ce5  add     rsp, 0D8h
0x1800b1cec  pop     r14
0x1800b1cee  pop     rdi
0x1800b1cef  pop     rsi
0x1800b1cf0  pop     rbp
0x1800b1cf1  retn
```
