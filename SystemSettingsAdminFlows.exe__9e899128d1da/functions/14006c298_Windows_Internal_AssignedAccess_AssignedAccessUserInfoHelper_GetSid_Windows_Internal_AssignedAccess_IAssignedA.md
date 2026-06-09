# Windows::Internal::AssignedAccess::AssignedAccessUserInfoHelper::GetSid(Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *,ushort * *)

- ea: `0x14006c298`
- end: `0x14006c3b0`
- name: `?GetSid@AssignedAccessUserInfoHelper@AssignedAccess@Internal@Windows@@SAJPEAUIAssignedAccessUserInfo@234@PEAPEAG@Z`
- size: `280`
- prototype: `static int(struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14006c3b8`

## callees

- `0x14000e428`
- `0x14000f164`
- `0x14000f384`
- `0x14001f3d4`
- `0x1400694d0`
- `0x1400695a4`
- `0x14006c298`
- `0x14007d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14006c362`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14006c362`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14006c307`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14006c307`

## string_xrefs

- `0x14006c2c4`: `shellcommondesktopbase\base\embedded\sys\lockdown\inc\assignedaccessconfigurationhelper.h`
- `0x14006c33b`: `shellcommondesktopbase\base\embedded\sys\lockdown\inc\assignedaccessconfigurationhelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::AssignedAccess::AssignedAccessUserInfoHelper::GetSid(
        struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *a1,
        unsigned __int16 **a2)
{
  unsigned int v3; // ebx
  __int64 (__fastcall *v5)(struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *, HSTRING *); // r14
  int v6; // eax
  char *StringRawBuffer; // rax
  const char *v8; // r9
  unsigned __int16 *v9; // rax
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  HSTRING string; // [rsp+40h] [rbp+20h] BYREF
  unsigned __int16 *v13; // [rsp+50h] [rbp+30h] BYREF

  if ( !a1 )
  {
    v3 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\inc\\assignedaccessconfigurationhelper.h",
      (const char *)0x80004003LL,
      savedregs);
    return v3;
  }
  *a2 = 0;
  string = 0;
  v5 = *(__int64 (__fastcall **)(struct Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *, HSTRING *))(*(_QWORD *)a1 + 48LL);
  string = 0;
  v6 = v5(a1, &string);
  v3 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\inc\\assignedaccessconfigurationhelper.h",
      (const char *)(unsigned int)v6,
      savedregs);
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    return v3;
  }
  StringRawBuffer = (char *)WindowsGetStringRawBuffer(string, 0);
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v13,
    StringRawBuffer,
    0xFFFFFFFFFFFFFFFFuLL,
    v8);
  v9 = v13;
  v13 = 0;
  *a2 = v9;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v13);
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  return 0;
}

```

## disassembly

```asm
0x14006c298  mov     [rsp-18h+arg_8], rbx
0x14006c29d  mov     [rsp-18h+arg_18], rsi
0x14006c2a2  push    rbp
0x14006c2a3  push    rdi
0x14006c2a4  push    r14; int
0x14006c2a6  mov     rbp, rsp
0x14006c2a9  sub     rsp, 20h
0x14006c2ad  mov     rsi, rdx
0x14006c2b0  mov     rbx, rcx
0x14006c2b3  test    rcx, rcx
0x14006c2b6  jnz     short loc_14006C2DC
0x14006c2b8  mov     rcx, [rbp+18h]; this
0x14006c2bc  mov     ebx, 80004003h
0x14006c2c1  mov     r9d, ebx; char *
0x14006c2c4  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x14006c2cb  mov     edx, 2Eh ; '.'; void *
0x14006c2d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006c2d5  mov     eax, ebx
0x14006c2d7  jmp     loc_14006C39D
0x14006c2dc  mov     qword ptr [rdx], 0
0x14006c2e3  mov     [rbp+string], 0
0x14006c2eb  mov     rax, [rcx]
0x14006c2ee  mov     r14, [rax+30h]
0x14006c2f2  mov     rdi, [rbp+string]
0x14006c2f6  test    rdi, rdi
0x14006c2f9  jz      short loc_14006C317
0x14006c2fb  lea     rcx, [rbp+arg_10]; this
0x14006c2ff  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14006c304  mov     rcx, rdi; string
0x14006c307  call    cs:__imp_WindowsDeleteString
0x14006c30d  lea     rcx, [rbp+arg_10]; this
0x14006c311  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14006c316  nop
0x14006c317  mov     [rbp+string], 0
0x14006c31f  lea     rdx, [rbp+string]
0x14006c323  mov     rcx, rbx
0x14006c326  mov     rax, r14
0x14006c329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006c32e  mov     ebx, eax
0x14006c330  test    eax, eax
0x14006c332  jns     short loc_14006C35C
0x14006c334  mov     rcx, [rbp+18h]; this
0x14006c338  mov     r9d, eax; char *
0x14006c33b  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x14006c342  mov     edx, 31h ; '1'; void *
0x14006c347  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006c34c  nop
0x14006c34d  lea     rcx, [rbp+string]; this
0x14006c351  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x14006c356  nop
0x14006c357  jmp     loc_14006C2D5
0x14006c35c  xor     edx, edx; length
0x14006c35e  mov     rcx, [rbp+string]; string
0x14006c362  call    cs:__imp_WindowsGetStringRawBuffer
0x14006c368  or      r8, 0FFFFFFFFFFFFFFFFh
0x14006c36c  mov     rdx, rax
0x14006c36f  lea     rcx, [rbp+arg_10]
0x14006c373  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x14006c378  mov     rax, [rbp+arg_10]
0x14006c37c  mov     [rbp+arg_10], 0
0x14006c384  mov     [rsi], rax
0x14006c387  lea     rcx, [rbp+arg_10]
0x14006c38b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14006c390  nop
0x14006c391  lea     rcx, [rbp+string]; this
0x14006c395  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x14006c39a  nop
0x14006c39b  xor     eax, eax
0x14006c39d  mov     rbx, [rsp+20h+arg_8]
0x14006c3a2  mov     rsi, [rsp+20h+arg_18]
0x14006c3a7  add     rsp, 20h
0x14006c3ab  pop     r14
0x14006c3ad  pop     rdi
0x14006c3ae  pop     rbp
0x14006c3af  retn
```
