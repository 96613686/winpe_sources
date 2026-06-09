# RegistryStore::RecusevelyCreateAndOpenKey(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void * *)

- ea: `0x18002ff94`
- end: `0x1800301b0`
- name: `?RecusevelyCreateAndOpenKey@RegistryStore@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAX@Z`
- size: `540`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800819d0`

## callees

- `0x180015fa0`
- `0x180017a98`
- `0x180026f4c`
- `0x18002ff94`
- `0x1800301b8`
- `0x180030544`
- `0x180030568`
- `0x180030718`
- `0x180030bcc`
- `0x1800358d0`
- `0x180037780`
- `0x180080668`
- `0x180080700`

## import_xrefs

- `ntdll!NtClose` at `0x180030118`
- `ntdll!NtClose` at `0x180030118`
- `ntdll!NtCreateKey` at `0x1800300ed`
- `ntdll!NtCreateKey` at `0x1800300ed`
- `ntdll!RtlInitUnicodeString` at `0x180030076`
- `ntdll!RtlInitUnicodeString` at `0x180030076`

## string_xrefs

- `0x18003016a`: `onecore\windows\hvsi\settings\src\registryutils\registrystore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RegistryStore::RecusevelyCreateAndOpenKey(__int64 a1, __int64 *a2, _QWORD *a3)
{
  __int64 v5; // rbx
  size_t v6; // rax
  int v7; // r9d
  __int64 v8; // rcx
  __int64 v9; // r8
  void *v10; // rax
  __int64 v11; // rax
  const WCHAR *v12; // rdx
  NTSTATUS v13; // r15d
  HANDLE v14; // rcx
  NTSTATUS v15; // eax
  HANDLE v16; // rax
  unsigned __int64 v18; // r9
  __int64 v19; // rdx
  unsigned int v20; // ebx
  int Class; // [rsp+20h] [rbp-B9h]
  HANDLE Handle; // [rsp+40h] [rbp-99h] BYREF
  ULONG Disposition; // [rsp+48h] [rbp-91h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-89h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-79h] BYREF
  HANDLE *p_Handle; // [rsp+90h] [rbp-49h] BYREF
  void *KeyHandle; // [rsp+98h] [rbp-41h] BYREF
  char v28; // [rsp+A0h] [rbp-39h]
  PCWSTR SourceString[4]; // [rsp+B0h] [rbp-29h] BYREF
  _BYTE v30[32]; // [rsp+D0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  LODWORD(v5) = 0;
  Handle = 0;
  while ( 1 )
  {
    v6 = std::_WChar_traits<unsigned short>::length(L"\\", a2, a3);
    if ( (unsigned __int64)a2[3] <= 7 )
      LODWORD(v8) = (_DWORD)a2;
    else
      v8 = *a2;
    v5 = std::_Traits_find_first_of<std::char_traits<unsigned short>>(v8, a2[2], v5, v7, v6);
    std::wstring::wstring(SourceString);
    v10 = (void *)std::wstring::substr(a2, v30, v9, v5);
    v11 = std::wstring::_Insert<unsigned short>(v10);
    std::wstring::wstring(&p_Handle, v11);
    std::wstring::operator=(SourceString, &p_Handle);
    std::wstring::_Tidy_deallocate(&p_Handle);
    std::wstring::_Tidy_deallocate(v30);
    DestinationString = 0;
    v12 = (const WCHAR *)SourceString;
    if ( SourceString[3] > (PCWSTR)7 )
      v12 = SourceString[0];
    RtlInitUnicodeString(&DestinationString, v12);
    *(_QWORD *)&ObjectAttributes.Length = 48;
    *(_QWORD *)&ObjectAttributes.Attributes = 64;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    Disposition = 0;
    p_Handle = &Handle;
    KeyHandle = 0;
    v28 = 1;
    v13 = NtCreateKey(&KeyHandle, 0x2001Fu, &ObjectAttributes, 0, 0, 0, &Disposition);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_Handle);
    if ( v13 < 0 )
      break;
    if ( v5 != -1 )
    {
      v14 = Handle;
      Handle = 0;
      v15 = NtClose(v14);
      if ( v15 < 0 )
      {
        v18 = (unsigned int)v15;
        v19 = 226;
        goto LABEL_15;
      }
      ++v5;
    }
    std::wstring::_Tidy_deallocate(SourceString);
    if ( v5 == -1 )
    {
      v16 = Handle;
      Handle = 0;
      *a3 = v16;
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Handle);
      return 0;
    }
  }
  v18 = (unsigned int)v13;
  v19 = 220;
LABEL_15:
  v20 = wil::details::in1diag3::Return_NtStatus(
          retaddr,
          (void *)v19,
          (unsigned int)"onecore\\windows\\hvsi\\settings\\src\\registryutils\\registrystore.cpp",
          (const char *)v18,
          Class);
  std::wstring::_Tidy_deallocate(SourceString);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Handle);
  return v20;
}

```

## disassembly

```asm
0x18002ff94  push    rbp
0x18002ff96  push    rbx
0x18002ff97  push    rsi
0x18002ff98  push    rdi
0x18002ff99  push    r12
0x18002ff9b  push    r14
0x18002ff9d  push    r15
0x18002ff9f  lea     rbp, [rsp-27h]
0x18002ffa4  sub     rsp, 100h
0x18002ffab  mov     rax, cs:__security_cookie
0x18002ffb2  xor     rax, rsp
0x18002ffb5  mov     [rbp+57h+var_40], rax
0x18002ffb9  mov     r12, r8
0x18002ffbc  mov     rdi, rdx
0x18002ffbf  mov     rsi, rcx
0x18002ffc2  xor     ebx, ebx
0x18002ffc4  mov     [rsp+130h+Handle], rbx
0x18002ffc9  lea     rcx, S; "\\"
0x18002ffd0  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18002ffd5  cmp     qword ptr [rdi+18h], 7
0x18002ffda  jbe     short loc_18002FFE1
0x18002ffdc  mov     rcx, [rdi]
0x18002ffdf  jmp     short loc_18002FFE4
0x18002ffe1  mov     rcx, rdi; int
0x18002ffe4  mov     [rsp+130h+Class], rax; N
0x18002ffe9  mov     r8, rbx; int
0x18002ffec  mov     rdx, [rdi+10h]; int
0x18002fff0  call    ??$_Traits_find_first_of@U?$char_traits@G@std@@@std@@YA_KQEBG_K101@Z; std::_Traits_find_first_of<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x18002fff5  mov     rbx, rax
0x18002fff8  lea     rcx, [rbp+57h+SourceString]
0x18002fffc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180030001  nop
0x180030002  mov     r9, rbx
0x180030005  lea     rdx, [rbp+57h+var_60]
0x180030009  mov     rcx, rdi
0x18003000c  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180030011  nop
0x180030012  cmp     qword ptr [rsi+20h], 7
0x180030017  jbe     short loc_18003001F
0x180030019  mov     r8, [rsi+8]
0x18003001d  jmp     short loc_180030023
0x18003001f  lea     r8, [rsi+8]
0x180030023  mov     r9, [rsi+18h]
0x180030027  mov     rcx, rax; Src
0x18003002a  call    ??$_Insert@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KQEBG0@Z; std::wstring::_Insert<ushort>(unsigned __int64,ushort const * const,unsigned __int64)
0x18003002f  mov     rdx, rax
0x180030032  lea     rcx, [rbp+57h+var_A0]
0x180030036  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18003003b  lea     rdx, [rbp+57h+var_A0]
0x18003003f  lea     rcx, [rbp+57h+SourceString]
0x180030043  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180030048  lea     rcx, [rbp+57h+var_A0]
0x18003004c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030051  nop
0x180030052  lea     rcx, [rbp+57h+var_60]
0x180030056  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003005b  xorps   xmm0, xmm0
0x18003005e  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm0
0x180030063  lea     rdx, [rbp+57h+SourceString]
0x180030067  cmp     [rbp+57h+var_68], 7
0x18003006c  cmova   rdx, [rbp+57h+SourceString]; SourceString
0x180030071  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x180030076  call    cs:__imp_RtlInitUnicodeString
0x18003007c  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180030084  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18003008c  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180030094  lea     rax, [rsp+130h+DestinationString]
0x180030099  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18003009d  xorps   xmm0, xmm0
0x1800300a0  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800300a5  mov     [rsp+130h+var_E8], 0
0x1800300ad  lea     rax, [rsp+130h+Handle]
0x1800300b2  mov     [rbp+57h+var_A0], rax
0x1800300b6  mov     [rbp+57h+KeyHandle], 0
0x1800300be  mov     [rbp+57h+var_90], 1
0x1800300c2  lea     rax, [rsp+130h+var_E8]
0x1800300c7  mov     [rsp+130h+Disposition], rax; Disposition
0x1800300cc  mov     [rsp+130h+CreateOptions], 0; CreateOptions
0x1800300d4  mov     [rsp+130h+Class], 0; int
0x1800300dd  xor     r9d, r9d; TitleIndex
0x1800300e0  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800300e4  mov     edx, 2001Fh; DesiredAccess
0x1800300e9  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800300ed  call    cs:__imp_NtCreateKey
0x1800300f3  mov     r15d, eax
0x1800300f6  lea     rcx, [rbp+57h+var_A0]
0x1800300fa  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x1800300ff  test    r15d, r15d
0x180030102  js      short loc_180030162
0x180030104  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180030108  jz      short loc_180030125
0x18003010a  mov     rcx, [rsp+130h+Handle]; Handle
0x18003010f  mov     [rsp+130h+Handle], 0
0x180030118  call    cs:__imp_NtClose
0x18003011e  test    eax, eax
0x180030120  js      short loc_180030158
0x180030122  inc     rbx
0x180030125  lea     rcx, [rbp+57h+SourceString]
0x180030129  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003012e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180030132  jnz     loc_18002FFC9
0x180030138  mov     rax, [rsp+130h+Handle]
0x18003013d  mov     [rsp+130h+Handle], 0
0x180030146  mov     [r12], rax
0x18003014a  lea     rcx, [rsp+130h+Handle]
0x18003014f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180030154  xor     eax, eax
0x180030156  jmp     short loc_180030192
0x180030158  mov     r9d, eax
0x18003015b  mov     edx, 0E2h
0x180030160  jmp     short loc_18003016A
0x180030162  mov     r9d, r15d; char *
0x180030165  mov     edx, 0DCh; void *
0x18003016a  lea     r8, aOnecoreWindows; "onecore\\windows\\hvsi\\settings\\src\\"...
0x180030171  mov     rcx, [rbp+5Fh]; this
0x180030175  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18003017a  mov     ebx, eax
0x18003017c  lea     rcx, [rbp+57h+SourceString]
0x180030180  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030185  nop
0x180030186  lea     rcx, [rsp+130h+Handle]
0x18003018b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180030190  mov     eax, ebx
0x180030192  mov     rcx, [rbp+57h+var_40]
0x180030196  xor     rcx, rsp; StackCookie
0x180030199  call    __security_check_cookie
0x18003019e  add     rsp, 100h
0x1800301a5  pop     r15
0x1800301a7  pop     r14
0x1800301a9  pop     r12
0x1800301ab  pop     rdi
0x1800301ac  pop     rsi
0x1800301ad  pop     rbx
0x1800301ae  pop     rbp
0x1800301af  retn
```
