# PrintCore::TokenHelpers::GetUserSid(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18003161c`
- end: `0x180031705`
- name: `?GetUserSid@TokenHelpers@PrintCore@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003170c`

## callees

- `0x180007a28`
- `0x18000876c`
- `0x180023a20`
- `0x180027020`
- `0x18003161c`
- `0x1800317bc`
- `0x1800328d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800316c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800316c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003167e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003167e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003169d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003169d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PrintCore::TokenHelpers::GetUserSid(_QWORD *a1)
{
  _QWORD *v1; // rdi
  signed int UserSidRaw; // ebx
  HLOCAL v3; // rsi
  __int64 v4; // r8
  const char *v5; // r9
  signed int LastError; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HLOCAL hMem; // [rsp+40h] [rbp+8h] BYREF
  PSID Sid; // [rsp+48h] [rbp+10h] BYREF
  char v11; // [rsp+50h] [rbp+18h] BYREF

  v1 = a1;
  a1[2] = 0;
  if ( a1[3] > 7u )
    a1 = (_QWORD *)*a1;
  *(_WORD *)a1 = 0;
  Sid = 0;
  hMem = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &Sid,
    0);
  UserSidRaw = PrintCore::TokenHelpers::GetUserSidRaw(&Sid);
  if ( UserSidRaw >= 0 )
  {
    v3 = hMem;
    if ( hMem )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v11);
      LocalFree(v3);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v11);
    }
    hMem = 0;
    if ( ConvertSidToStringSidW(Sid, (LPWSTR *)&hMem) )
    {
      v4 = -1;
      do
        ++v4;
      while ( *((_WORD *)hMem + v4) );
      try
      {
        std::wstring::_Assign<unsigned short>(v1, hMem);
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0xA2,
                               (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\TokenHelpers.h",
                               v5);
      }
    }
    else
    {
      LastError = GetLastError();
      UserSidRaw = LastError;
      if ( LastError > 0 )
        UserSidRaw = (unsigned __int16)LastError | 0x80070000;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
  return (unsigned int)UserSidRaw;
}

```

## disassembly

```asm
0x18003161c  mov     [rsp+arg_18], rbx
0x180031621  push    rsi
0x180031622  push    rdi
0x180031623  push    r14
0x180031625  sub     rsp, 20h
0x180031629  mov     rdi, rcx
0x18003162c  xor     r14d, r14d
0x18003162f  mov     [rcx+10h], r14
0x180031633  cmp     qword ptr [rcx+18h], 7
0x180031638  jbe     short loc_18003163D
0x18003163a  mov     rcx, [rcx]
0x18003163d  mov     [rcx], r14w
0x180031641  mov     [rsp+38h+Sid], r14
0x180031646  mov     [rsp+38h+hMem], r14
0x18003164b  xor     edx, edx
0x18003164d  lea     rcx, [rsp+38h+Sid]
0x180031652  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180031657  lea     rcx, [rsp+38h+Sid]; void **
0x18003165c  call    ?GetUserSidRaw@TokenHelpers@PrintCore@@SAJPEAPEAX@Z; PrintCore::TokenHelpers::GetUserSidRaw(void * *)
0x180031661  mov     ebx, eax
0x180031663  test    eax, eax
0x180031665  js      short loc_1800316D9
0x180031667  mov     rsi, [rsp+38h+hMem]
0x18003166c  test    rsi, rsi
0x18003166f  jz      short loc_18003168E
0x180031671  lea     rcx, [rsp+38h+arg_10]; this
0x180031676  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003167b  mov     rcx, rsi; hMem
0x18003167e  call    cs:__imp_LocalFree
0x180031684  lea     rcx, [rsp+38h+arg_10]; this
0x180031689  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003168e  mov     [rsp+38h+hMem], r14
0x180031693  lea     rdx, [rsp+38h+hMem]; StringSid
0x180031698  mov     rcx, [rsp+38h+Sid]; Sid
0x18003169d  call    cs:__imp_ConvertSidToStringSidW
0x1800316a3  test    eax, eax
0x1800316a5  jz      short loc_1800316C4
0x1800316a7  mov     rdx, [rsp+38h+hMem]
0x1800316ac  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800316b0  inc     r8
0x1800316b3  cmp     [rdx+r8*2], r14w
0x1800316b8  jnz     short loc_1800316B0
0x1800316ba  mov     rcx, rdi
0x1800316bd  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800316c2  jmp     short loc_1800316D9
0x1800316c4  call    cs:__imp_GetLastError
0x1800316ca  mov     ebx, eax
0x1800316cc  test    eax, eax
0x1800316ce  jle     short loc_1800316D9
0x1800316d0  movzx   ebx, ax
0x1800316d3  or      ebx, 80070000h
0x1800316d9  lea     rcx, [rsp+38h+hMem]
0x1800316de  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800316e3  nop
0x1800316e4  lea     rcx, [rsp+38h+Sid]
0x1800316e9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800316ee  mov     eax, ebx
0x1800316f0  jmp     short loc_1800316F6
0x1800316f2  mov     eax, dword ptr [rsp+38h+hMem]
0x1800316f6  mov     rbx, [rsp+38h+arg_18]
0x1800316fb  add     rsp, 20h
0x1800316ff  pop     r14
0x180031701  pop     rdi
0x180031702  pop     rsi
0x180031703  retn
```
