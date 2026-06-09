# PrintCore::TokenHelpers::GetUserSid(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180017614`
- end: `0x1800176ee`
- name: `?GetUserSid@TokenHelpers@PrintCore@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `218`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001463c`

## callees

- `0x1800067a4`
- `0x180006edc`
- `0x18000792c`
- `0x18000e164`
- `0x18000e5e8`
- `0x1800126c8`
- `0x180017614`
- `0x1800176f4`
- `0x18001e470`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800176b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800176b3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001768f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001768f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001766c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001766c`

## pseudocode

```c
__int64 __fastcall PrintCore::TokenHelpers::GetUserSid(__int64 a1)
{
  signed int UserSidRaw; // ebx
  HLOCAL v3; // rdi
  __int64 v4; // rcx
  const char *v5; // r9
  signed int LastError; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HLOCAL hMem; // [rsp+40h] [rbp+8h] BYREF
  PSID Sid; // [rsp+48h] [rbp+10h] BYREF
  char v11; // [rsp+50h] [rbp+18h] BYREF

  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1) = 0;
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
      std::_WChar_traits<unsigned short>::length(hMem);
      try
      {
        std::wstring::_Assign<unsigned short>(a1, v4);
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0xA2,
                               (unsigned int)"onecoreuap\\internal\\printscan\\inc\\TokenHelpers.h",
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
0x180017614  push    rbx
0x180017616  push    rsi
0x180017617  push    rdi
0x180017618  sub     rsp, 20h
0x18001761c  mov     rsi, rcx
0x18001761f  mov     qword ptr [rcx+10h], 0
0x180017627  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001762c  xor     edx, edx
0x18001762e  mov     [rax], dx
0x180017631  mov     [rsp+38h+Sid], rdx
0x180017636  mov     [rsp+38h+hMem], rdx
0x18001763b  lea     rcx, [rsp+38h+Sid]
0x180017640  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180017645  lea     rcx, [rsp+38h+Sid]; void **
0x18001764a  call    ?GetUserSidRaw@TokenHelpers@PrintCore@@SAJPEAPEAX@Z; PrintCore::TokenHelpers::GetUserSidRaw(void * *)
0x18001764f  mov     ebx, eax
0x180017651  test    eax, eax
0x180017653  js      short loc_1800176C8
0x180017655  mov     rdi, [rsp+38h+hMem]
0x18001765a  test    rdi, rdi
0x18001765d  jz      short loc_18001767C
0x18001765f  lea     rcx, [rsp+38h+arg_10]; this
0x180017664  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180017669  mov     rcx, rdi; hMem
0x18001766c  call    cs:__imp_LocalFree
0x180017672  lea     rcx, [rsp+38h+arg_10]; this
0x180017677  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001767c  mov     [rsp+38h+hMem], 0
0x180017685  lea     rdx, [rsp+38h+hMem]; StringSid
0x18001768a  mov     rcx, [rsp+38h+Sid]; Sid
0x18001768f  call    cs:__imp_ConvertSidToStringSidW
0x180017695  test    eax, eax
0x180017697  jz      short loc_1800176B3
0x180017699  mov     rcx, [rsp+38h+hMem]
0x18001769e  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800176a3  mov     r8, rax
0x1800176a6  mov     rdx, rcx
0x1800176a9  mov     rcx, rsi
0x1800176ac  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800176b1  jmp     short loc_1800176C8
0x1800176b3  call    cs:__imp_GetLastError
0x1800176b9  mov     ebx, eax
0x1800176bb  test    eax, eax
0x1800176bd  jle     short loc_1800176C8
0x1800176bf  movzx   ebx, ax
0x1800176c2  or      ebx, 80070000h
0x1800176c8  lea     rcx, [rsp+38h+hMem]
0x1800176cd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800176d2  nop
0x1800176d3  lea     rcx, [rsp+38h+Sid]
0x1800176d8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800176dd  mov     eax, ebx
0x1800176df  jmp     short loc_1800176E5
0x1800176e1  mov     eax, dword ptr [rsp+38h+hMem]
0x1800176e5  add     rsp, 20h
0x1800176e9  pop     rdi
0x1800176ea  pop     rsi
0x1800176eb  pop     rbx
0x1800176ec  retn
```
