# Windows::Internal::CapabilityAccess::Private::GetAppExecutionContext(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180040788`
- end: `0x180040927`
- name: `?GetAppExecutionContext@Private@CapabilityAccess@Internal@Windows@@YA?AW4AppExecutionContext@1234@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006ae88`

## callees

- `0x1800094c0`
- `0x18001c3b4`
- `0x18002392c`
- `0x18003ae98`
- `0x180040788`
- `0x180042410`
- `0x180045c38`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x1800408bf`
- `ntdll!RtlCompareUnicodeString` at `0x1800408bf`
- `ntdll!NtQueryInformationToken` at `0x1800407df`
- `ntdll!NtQueryInformationToken` at `0x18004087b`
- `ntdll!NtQueryInformationToken` at `0x1800407df`
- `ntdll!NtQueryInformationToken` at `0x18004087b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800408f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040901`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800408f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040901`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004082f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004082f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::GetAppExecutionContext(HANDLE *a1)
{
  char *v2; // rcx
  unsigned int v3; // eax
  void *v4; // rdx
  unsigned int v5; // r8d
  HLOCAL v7; // rax
  NTSTATUS v8; // eax
  __int64 i; // rbx
  int v10; // ebx
  int ReturnLength; // [rsp+20h] [rbp-60h]
  int ReturnLengtha; // [rsp+20h] [rbp-60h]
  int ReturnLengthb; // [rsp+20h] [rbp-60h]
  ULONG TokenInformationLength; // [rsp+30h] [rbp-50h] BYREF
  HLOCAL hMem[2]; // [rsp+38h] [rbp-48h] BYREF
  char v16; // [rsp+48h] [rbp-38h]
  _BYTE v17[16]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v18; // [rsp+60h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  v2 = (char *)*a1;
  if ( (unsigned __int64)(v2 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x55A,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)0x80070057LL,
      ReturnLength);
  TokenInformationLength = 0;
  v3 = NtQueryInformationToken(v2, TokenSecurityAttributes, 0, 0, &TokenInformationLength);
  if ( v3 != -1073741789 )
    wil::details::in1diag3::Throw_NtStatus(retaddr, v4, v5, (const char *)v3, ReturnLengtha);
  if ( TokenInformationLength )
  {
    v7 = LocalAlloc(0x40u, 16LL * TokenInformationLength);
    hMem[0] = v7;
    if ( !v7 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x576,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        (const char *)0x80070008LL,
        ReturnLengtha);
    hMem[1] = hMem;
    v16 = 1;
    v8 = NtQueryInformationToken(*a1, TokenSecurityAttributes, v7, TokenInformationLength, &TokenInformationLength);
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x583,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        (const char *)(unsigned int)v8,
        ReturnLengthb);
    for ( i = 0; (unsigned int)i < *((_DWORD *)hMem[0] + 1); i = (unsigned int)(i + 1) )
    {
      if ( !RtlCompareUnicodeString(&String1, (PCUNICODE_STRING)(*((_QWORD *)hMem[0] + 1) + 40 * i), 1u) )
      {
        Windows::Internal::CapabilityAccess::Private::GetPackageFamilyNameFromToken(v17);
        v10 = -(v18 != 0);
        std::wstring::_Tidy_deallocate(v17);
        LocalFree(hMem[0]);
        return (unsigned int)(v10 + 2);
      }
    }
    LocalFree(hMem[0]);
  }
  return 0;
}

```

## disassembly

```asm
0x180040788  mov     [rsp-8+arg_8], rbx
0x18004078d  mov     [rsp-8+arg_10], rdi
0x180040792  push    rbp
0x180040793  mov     rbp, rsp
0x180040796  sub     rsp, 80h
0x18004079d  mov     rax, cs:__security_cookie
0x1800407a4  xor     rax, rsp
0x1800407a7  mov     [rbp+var_10], rax
0x1800407ab  mov     rdi, rcx
0x1800407ae  mov     r10, [rbp+8]
0x1800407b2  mov     rcx, [rcx]; TokenHandle
0x1800407b5  lea     rax, [rcx-1]
0x1800407b9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800407bd  ja      loc_18004090C
0x1800407c3  mov     [rbp+TokenInformationLength], 0
0x1800407ca  lea     rax, [rbp+TokenInformationLength]
0x1800407ce  mov     qword ptr [rsp+80h+ReturnLength], rax; int
0x1800407d3  xor     r9d, r9d; TokenInformationLength
0x1800407d6  xor     r8d, r8d; TokenInformation
0x1800407d9  lea     ebx, [r9+27h]
0x1800407dd  mov     edx, ebx; TokenInformationClass
0x1800407df  call    cs:__imp_NtQueryInformationToken
0x1800407e5  cmp     eax, 0C0000023h
0x1800407ea  jz      short loc_1800407F9
0x1800407ec  mov     rcx, [rbp+8]; this
0x1800407f0  mov     r9d, eax; char *
0x1800407f3  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x1800407f9  mov     eax, [rbp+TokenInformationLength]
0x1800407fc  test    eax, eax
0x1800407fe  jnz     short loc_180040823
0x180040800  xor     eax, eax
0x180040802  mov     rcx, [rbp+var_10]
0x180040806  xor     rcx, rsp; StackCookie
0x180040809  call    __security_check_cookie
0x18004080e  lea     r11, [rsp+80h+var_s0]
0x180040816  mov     rbx, [r11+18h]
0x18004081a  mov     rdi, [r11+20h]
0x18004081e  mov     rsp, r11
0x180040821  pop     rbp
0x180040822  retn
0x180040823  mov     rdx, rax
0x180040826  shl     rdx, 4; uBytes
0x18004082a  mov     ecx, 40h ; '@'; uFlags
0x18004082f  call    cs:__imp_LocalAlloc
0x180040835  mov     [rbp+hMem], rax
0x180040839  test    rax, rax
0x18004083c  jnz     short loc_18004085A
0x18004083e  mov     rcx, [rbp+8]; this
0x180040842  mov     r9d, 80070008h; char *
0x180040848  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x18004084f  mov     edx, 576h; void *
0x180040854  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004085a  lea     rcx, [rbp+hMem]
0x18004085e  mov     [rbp+var_40], rcx
0x180040862  mov     [rbp+var_38], 1
0x180040866  lea     rcx, [rbp+TokenInformationLength]
0x18004086a  mov     qword ptr [rsp+80h+ReturnLength], rcx; int
0x18004086f  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180040873  mov     r8, rax; TokenInformation
0x180040876  mov     edx, ebx; TokenInformationClass
0x180040878  mov     rcx, [rdi]; TokenHandle
0x18004087b  call    cs:__imp_NtQueryInformationToken
0x180040881  mov     rcx, [rbp+8]; this
0x180040885  test    eax, eax
0x180040887  jns     short loc_18004089E
0x180040889  mov     r9d, eax; char *
0x18004088c  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180040893  mov     edx, 583h; void *
0x180040898  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18004089e  xor     ebx, ebx
0x1800408a0  mov     rdx, [rbp+hMem]
0x1800408a4  cmp     ebx, [rdx+4]
0x1800408a7  jnb     short loc_1800408FE
0x1800408a9  lea     rcx, [rbx+rbx*4]
0x1800408ad  mov     rax, [rdx+8]
0x1800408b1  lea     rdx, [rax+rcx*8]; String2
0x1800408b5  mov     r8b, 1; CaseInsensitive
0x1800408b8  lea     rcx, String1; String1
0x1800408bf  call    cs:__imp_RtlCompareUnicodeString
0x1800408c5  test    eax, eax
0x1800408c7  jz      short loc_1800408CD
0x1800408c9  inc     ebx
0x1800408cb  jmp     short loc_1800408A0
0x1800408cd  mov     rdx, rdi
0x1800408d0  lea     rcx, [rbp+var_30]
0x1800408d4  call    ?GetPackageFamilyNameFromToken@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Windows::Internal::CapabilityAccess::Private::GetPackageFamilyNameFromToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)
0x1800408d9  mov     rax, [rbp+var_20]
0x1800408dd  neg     rax
0x1800408e0  sbb     ebx, ebx
0x1800408e2  lea     rcx, [rbp+var_30]
0x1800408e6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800408eb  nop
0x1800408ec  mov     rcx, [rbp+hMem]; hMem
0x1800408f0  call    cs:__imp_LocalFree
0x1800408f6  lea     eax, [rbx+2]
0x1800408f9  jmp     loc_180040802
0x1800408fe  mov     rcx, rdx; hMem
0x180040901  call    cs:__imp_LocalFree
0x180040907  jmp     loc_180040800
0x18004090c  mov     r9d, 80070057h; char *
0x180040912  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180040919  mov     edx, 55Ah; void *
0x18004091e  mov     rcx, r10; this
0x180040921  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
