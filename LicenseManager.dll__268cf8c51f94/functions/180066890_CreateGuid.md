# CreateGuid

- ea: `0x180066890`
- end: `0x180066943`
- name: `CreateGuid`
- size: `179`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006624c`
- `0x180071448`

## callees

- `0x18000a110`
- `0x18002aae8`
- `0x1800593bc`
- `0x180066890`
- `0x180075e60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x1800668f1`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x1800668f1`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800668ba`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800668ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
OLECHAR *__fastcall CreateGuid(OLECHAR *a1)
{
  HRESULT v2; // eax
  HRESULT v3; // eax
  LPOLESTR lpsz[2]; // [rsp+20h] [rbp-38h] BYREF
  GUID pguid; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  lpsz[0] = a1;
  pguid = 0;
  v2 = CoCreateGuid(&pguid);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\purchase.cpp",
      (const char *)(unsigned int)v2,
      (int)lpsz[0]);
  lpsz[0] = 0;
  v3 = StringFromIID(&pguid, lpsz);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\purchase.cpp",
      (const char *)(unsigned int)v3,
      (int)lpsz[0]);
  std::wstring::wstring(a1, lpsz[0]);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>((void **)lpsz);
  return a1;
}

```

## disassembly

```asm
0x180066890  push    rbx
0x180066892  sub     rsp, 50h
0x180066896  mov     rax, cs:__security_cookie
0x18006689d  xor     rax, rsp
0x1800668a0  mov     [rsp+58h+var_18], rax
0x1800668a5  mov     rbx, rcx
0x1800668a8  mov     [rsp+58h+lpsz], rcx; int
0x1800668ad  xorps   xmm0, xmm0
0x1800668b0  movups  xmmword ptr [rsp+58h+pguid.Data1], xmm0
0x1800668b5  lea     rcx, [rsp+58h+pguid]; pguid
0x1800668ba  call    cs:__imp_CoCreateGuid
0x1800668c0  mov     rcx, [rsp+58h]; this
0x1800668c5  test    eax, eax
0x1800668c7  jns     short loc_1800668DE
0x1800668c9  mov     r9d, eax; char *
0x1800668cc  lea     r8, aOnecoreuapEndu_19; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800668d3  mov     edx, 1Ah; void *
0x1800668d8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800668de  mov     [rsp+58h+lpsz], 0; int
0x1800668e7  lea     rdx, [rsp+58h+lpsz]; lplpsz
0x1800668ec  lea     rcx, [rsp+58h+pguid]; rclsid
0x1800668f1  call    cs:__imp_StringFromIID
0x1800668f7  mov     rcx, [rsp+58h]; this
0x1800668fc  test    eax, eax
0x1800668fe  jns     short loc_180066915
0x180066900  mov     r9d, eax; char *
0x180066903  lea     r8, aOnecoreuapEndu_19; "onecoreuap\\enduser\\winstore\\licensem"...
0x18006690a  mov     edx, 1Dh; void *
0x18006690f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180066915  mov     rdx, [rsp+58h+lpsz]
0x18006691a  mov     rcx, rbx
0x18006691d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180066922  nop
0x180066923  lea     rcx, [rsp+58h+lpsz]
0x180066928  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18006692d  mov     rax, rbx
0x180066930  mov     rcx, [rsp+58h+var_18]
0x180066935  xor     rcx, rsp; StackCookie
0x180066938  call    __security_check_cookie
0x18006693d  add     rsp, 50h
0x180066941  pop     rbx
0x180066942  retn
```
