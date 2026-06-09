# FileUtility::GetFullTempFilePath(void)

- ea: `0x1800b4f28`
- end: `0x1800b510b`
- name: `?GetFullTempFilePath@FileUtility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `483`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x1800b5640`
- `0x1800b6588`

## callees

- `0x1800011d4`
- `0x180004eb0`
- `0x1800058ec`
- `0x18000abec`
- `0x18000d50c`
- `0x180023380`
- `0x180036d2c`
- `0x18003e5d4`
- `0x1800af8e4`
- `0x1800b4f04`
- `0x1800b4f28`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800b502b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800b502b`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x1800b50a5`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x1800b50a5`
- `CRYPT32!CryptBinaryToStringW` at `0x1800b5070`
- `CRYPT32!CryptBinaryToStringW` at `0x1800b5070`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x1800b4f6f`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x1800b4f6f`

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
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&pszPath, v5);
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
0x1800b4f28  push    rbp
0x1800b4f2a  push    rsi
0x1800b4f2b  push    rdi
0x1800b4f2c  push    r14
0x1800b4f2e  lea     rbp, [rsp-3Fh]
0x1800b4f33  sub     rsp, 0D8h
0x1800b4f3a  mov     rax, cs:__security_cookie
0x1800b4f41  xor     rax, rsp
0x1800b4f44  mov     [rbp+57h+var_30], rax
0x1800b4f48  mov     rdi, rcx
0x1800b4f4b  mov     [rbp+57h+var_C0], rcx
0x1800b4f4f  xor     r14d, r14d
0x1800b4f52  mov     [rbp+57h+var_C0], r14
0x1800b4f56  lea     rax, [rbp+57h+var_C0]
0x1800b4f5a  mov     [rbp+57h+var_A8], rax
0x1800b4f5e  mov     [rbp+57h+var_A0], r14
0x1800b4f62  mov     [rbp+57h+var_98], 1
0x1800b4f66  lea     r8, [rbp+57h+var_A0]
0x1800b4f6a  xor     edx, edx
0x1800b4f6c  lea     ecx, [rdx+6]
0x1800b4f6f  call    cs:__imp_GetBasicProfileFolderPathAlloc
0x1800b4f76  nop     dword ptr [rax+rax+00h]
0x1800b4f7b  mov     rcx, [rbp+5Fh]; this
0x1800b4f7f  test    eax, eax
0x1800b4f81  jns     short loc_1800B4F97
0x1800b4f83  mov     r9d, eax; char *
0x1800b4f86  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x1800b4f8d  lea     edx, [r14+0Ch]; void *
0x1800b4f91  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b4f97  lea     rcx, [rbp+57h+var_A8]
0x1800b4f9b  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800b4fa0  mov     rax, [rbp+57h+var_C0]
0x1800b4fa4  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800b4fa8  mov     rdx, r8
0x1800b4fab  inc     rdx
0x1800b4fae  cmp     [rax+rdx*2], r14w
0x1800b4fb3  jnz     short loc_1800B4FAB
0x1800b4fb5  lea     rax, [rdx+2Eh]
0x1800b4fb9  mov     rsi, r8
0x1800b4fbc  cmp     rax, rdx
0x1800b4fbf  cmovnb  rsi, rax
0x1800b4fc3  sbb     r9d, r9d
0x1800b4fc6  and     r9d, 80070216h; char *
0x1800b4fcd  mov     rcx, [rbp+5Fh]; this
0x1800b4fd1  cmp     rax, rdx
0x1800b4fd4  jnb     short loc_1800B4FE8
0x1800b4fd6  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x1800b4fdd  mov     edx, 10h; void *
0x1800b4fe2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b4fe8  mov     eax, 2
0x1800b4fed  mul     rsi
0x1800b4ff0  cmovb   rax, r8
0x1800b4ff4  mov     rcx, rax; unsigned __int64
0x1800b4ff7  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800b4ffc  mov     rdx, rax
0x1800b4fff  lea     rcx, [rbp+57h+pszPath]
0x1800b5003  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800b5008  nop
0x1800b5009  mov     r8, [rbp+57h+var_C0]; unsigned __int16 *
0x1800b500d  mov     rdx, rsi; unsigned __int64
0x1800b5010  mov     rcx, [rbp+57h+pszPath]; unsigned __int16 *
0x1800b5014  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b5019  xorps   xmm0, xmm0
0x1800b501c  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x1800b5020  mov     [rbp+57h+var_B0], 26h ; '&'
0x1800b5027  lea     rcx, [rbp+57h+pguid]; pguid
0x1800b502b  call    cs:__imp_CoCreateGuid
0x1800b5032  nop     dword ptr [rax+rax+00h]
0x1800b5037  mov     rcx, [rbp+5Fh]; this
0x1800b503b  test    eax, eax
0x1800b503d  jns     short loc_1800B5054
0x1800b503f  mov     r9d, eax; char *
0x1800b5042  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x1800b5049  mov     edx, 19h; void *
0x1800b504e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b5054  lea     rax, [rbp+57h+var_B0]
0x1800b5058  mov     qword ptr [rsp+0F0h+pcchString], rax; int
0x1800b505d  lea     r9, [rbp+57h+pszString]; pszString
0x1800b5061  mov     edx, 10h; cbBinary
0x1800b5066  mov     r8d, 4000000Ch; dwFlags
0x1800b506c  lea     rcx, [rbp+57h+pguid]; pbBinary
0x1800b5070  call    cs:__imp_CryptBinaryToStringW
0x1800b5077  nop     dword ptr [rax+rax+00h]
0x1800b507c  mov     rcx, [rbp+5Fh]; this
0x1800b5080  test    eax, eax
0x1800b5082  jnz     short loc_1800B5094
0x1800b5084  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x1800b508b  lea     edx, [rax+1Bh]; void *
0x1800b508e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800b5094  mov     r9d, 1; dwFlags
0x1800b509a  lea     r8, [rbp+57h+pszString]; pszMore
0x1800b509e  mov     rdx, rsi; cchPath
0x1800b50a1  mov     rcx, [rbp+57h+pszPath]; pszPath
0x1800b50a5  call    cs:__imp_PathCchAppendEx
0x1800b50ac  nop     dword ptr [rax+rax+00h]
0x1800b50b1  mov     rcx, [rbp+5Fh]; this
0x1800b50b5  test    eax, eax
0x1800b50b7  jns     short loc_1800B50CE
0x1800b50b9  mov     r9d, eax; char *
0x1800b50bc  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x1800b50c3  mov     edx, 1Eh; void *
0x1800b50c8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b50ce  mov     rdx, [rbp+57h+pszPath]
0x1800b50d2  mov     rcx, rdi
0x1800b50d5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b50da  nop
0x1800b50db  lea     rcx, [rbp+57h+pszPath]
0x1800b50df  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1800b50e4  nop
0x1800b50e5  lea     rcx, [rbp+57h+var_C0]
0x1800b50e9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800b50ee  mov     rax, rdi
0x1800b50f1  mov     rcx, [rbp+57h+var_30]
0x1800b50f5  xor     rcx, rsp; StackCookie
0x1800b50f8  call    __security_check_cookie
0x1800b50fd  add     rsp, 0D8h
0x1800b5104  pop     r14
0x1800b5106  pop     rdi
0x1800b5107  pop     rsi
0x1800b5108  pop     rbp
0x1800b5109  retn
```
