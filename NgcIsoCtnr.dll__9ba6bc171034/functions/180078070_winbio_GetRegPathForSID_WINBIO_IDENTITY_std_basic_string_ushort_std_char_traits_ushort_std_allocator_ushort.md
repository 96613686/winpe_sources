# winbio::GetRegPathForSID(_WINBIO_IDENTITY *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180078070`
- end: `0x18007816d`
- name: `?GetRegPathForSID@winbio@@YAJPEAU_WINBIO_IDENTITY@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180077c2c`

## callees

- `0x18000d62c`
- `0x18001cee4`
- `0x180069140`
- `0x180070bd4`
- `0x180078070`
- `0x180078174`
- `0x1800781c0`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007811a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007811a`

## string_xrefs

- `0x180078094`: `onecore\ds\security\biometrics\service\common\winbio_enrollments.cpp`
- `0x1800780cb`: `onecore\ds\security\biometrics\service\common\winbio_enrollments.cpp`
- `0x18007812d`: `onecore\ds\security\biometrics\service\common\winbio_enrollments.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winbio::GetRegPathForSID(__int64 a1, __int64 a2, bool a3)
{
  __int64 v5; // rdx
  unsigned int v6; // ebx
  int WinBioRegistryLocation; // edi
  __int64 v8; // rdx
  unsigned int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  LPWSTR StringSid; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    if ( a2 )
    {
      WinBioRegistryLocation = winbio::ValidateIdentity((winbio *)a1, 0, a3);
      if ( WinBioRegistryLocation >= 0 )
      {
        WinBioRegistryLocation = GetWinBioRegistryLocation(a2);
        if ( WinBioRegistryLocation >= 0 )
        {
          std::wstring::append(a2, L"AccountInfo\\");
          StringSid = 0;
          if ( ConvertSidToStringSidW((PSID)(a1 + 8), &StringSid) )
          {
            std::wstring::append(a2, StringSid);
            v6 = 0;
          }
          else
          {
            v6 = wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)0x22D,
                   (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\winbio_enrollments.cpp",
                   (const char *)1,
                   v10);
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
          return v6;
        }
        v8 = 553;
      }
      else
      {
        v8 = 552;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\winbio_enrollments.cpp",
        (const char *)(unsigned int)WinBioRegistryLocation,
        v10);
      return (unsigned int)WinBioRegistryLocation;
    }
    v5 = 550;
  }
  else
  {
    v5 = 549;
  }
  v6 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\ds\\security\\biometrics\\service\\common\\winbio_enrollments.cpp",
    (const char *)0x80004003LL,
    v10);
  return v6;
}

```

## disassembly

```asm
0x180078070  mov     [rsp+arg_8], rbx
0x180078075  mov     [rsp+arg_10], rsi
0x18007807a  push    rdi; unsigned int
0x18007807b  sub     rsp, 20h
0x18007807f  mov     rbx, rdx
0x180078082  mov     rsi, rcx
0x180078085  test    rcx, rcx
0x180078088  jnz     short loc_1800780AD
0x18007808a  mov     edx, 225h; void *
0x18007808f  mov     ebx, 80004003h
0x180078094  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\biometrics\\serv"...
0x18007809b  mov     r9d, ebx; char *
0x18007809e  mov     rcx, [rsp+28h]; this
0x1800780a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800780a8  jmp     loc_18007815B
0x1800780ad  test    rbx, rbx
0x1800780b0  jnz     short loc_1800780B9
0x1800780b2  mov     edx, 226h
0x1800780b7  jmp     short loc_18007808F
0x1800780b9  xor     edx, edx; struct _WINBIO_IDENTITY *
0x1800780bb  call    ?ValidateIdentity@winbio@@YAJPEAU_WINBIO_IDENTITY@@_N@Z; winbio::ValidateIdentity(_WINBIO_IDENTITY *,bool)
0x1800780c0  mov     edi, eax
0x1800780c2  test    eax, eax
0x1800780c4  jns     short loc_1800780E3
0x1800780c6  mov     edx, 228h; void *
0x1800780cb  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\biometrics\\serv"...
0x1800780d2  mov     r9d, edi; char *
0x1800780d5  mov     rcx, [rsp+28h]; this
0x1800780da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800780df  mov     eax, edi
0x1800780e1  jmp     short loc_18007815D
0x1800780e3  mov     rcx, rbx
0x1800780e6  call    ?GetWinBioRegistryLocation@@YAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetWinBioRegistryLocation(std::wstring *)
0x1800780eb  mov     edi, eax
0x1800780ed  test    eax, eax
0x1800780ef  jns     short loc_1800780F8
0x1800780f1  mov     edx, 229h
0x1800780f6  jmp     short loc_1800780CB
0x1800780f8  lea     rdx, aAccountinfo; "AccountInfo\\"
0x1800780ff  mov     rcx, rbx
0x180078102  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180078107  nop
0x180078108  mov     [rsp+28h+StringSid], 0
0x180078111  lea     rcx, [rsi+8]; Sid
0x180078115  lea     rdx, [rsp+28h+StringSid]; StringSid
0x18007811a  call    cs:__imp_ConvertSidToStringSidW
0x180078120  test    eax, eax
0x180078122  jnz     short loc_180078142
0x180078124  mov     rcx, [rsp+28h]; this
0x180078129  lea     r9d, [rax+1]; char *
0x18007812d  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\biometrics\\serv"...
0x180078134  mov     edx, 22Dh; void *
0x180078139  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18007813e  mov     ebx, eax
0x180078140  jmp     short loc_180078151
0x180078142  mov     rdx, [rsp+28h+StringSid]
0x180078147  mov     rcx, rbx
0x18007814a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18007814f  xor     ebx, ebx
0x180078151  lea     rcx, [rsp+28h+StringSid]
0x180078156  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007815b  mov     eax, ebx
0x18007815d  mov     rbx, [rsp+28h+arg_8]
0x180078162  mov     rsi, [rsp+28h+arg_10]
0x180078167  add     rsp, 20h
0x18007816b  pop     rdi
0x18007816c  retn
```
