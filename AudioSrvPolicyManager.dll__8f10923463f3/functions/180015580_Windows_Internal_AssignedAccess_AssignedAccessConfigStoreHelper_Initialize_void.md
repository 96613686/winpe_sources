# Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::Initialize(void)

- ea: `0x180015580`
- end: `0x180015697`
- name: `?Initialize@AssignedAccessConfigStoreHelper@AssignedAccess@Internal@Windows@@AEAA_NXZ`
- size: `279`
- prototype: `bool __fastcall(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006e04`

## callees

- `0x18000a384`
- `0x180015064`
- `0x180015580`
- `0x180015800`
- `0x180015824`
- `0x18002ea78`
- `0x180031960`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015621`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015643`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001565d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015621`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015643`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001565d`

## string_xrefs

- `0x1800155b3`: `SOFTWARE\Microsoft\Windows\AssignedAccessConfiguration`
- `0x1800155a8`: `AssignedAccessConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::Initialize(LPVOID *this)
{
  int v2; // esi
  void *v4; // rbx
  LPVOID pv; // [rsp+20h] [rbp-69h] BYREF
  void *v6; // [rsp+28h] [rbp-61h] BYREF
  const wchar_t *v7; // [rsp+30h] [rbp-59h] BYREF
  const wchar_t *v8; // [rsp+38h] [rbp-51h] BYREF
  char v9[8]; // [rsp+40h] [rbp-49h] BYREF
  _QWORD v10[14]; // [rsp+48h] [rbp-41h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v6 = 0;
  v8 = L"AssignedAccessConfiguration";
  v7 = L"SOFTWARE\\Microsoft\\Windows\\AssignedAccessConfiguration";
  pv = 0;
  v10[0] = &wistd::__function::__func<_lambda_6166c63e326ec22a386edc375e0b06c9_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
  v10[1] = &v7;
  v10[2] = &v8;
  v10[13] = v10;
  v2 = wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
         (__int64)&pv,
         (__int64)v9);
  wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::~function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>(v9);
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\inc\\persistentlocationhelper.h",
      (const char *)(unsigned int)v2,
      (int)pv);
    if ( pv )
      CoTaskMemFree(pv);
    return 0;
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    &v6,
    &pv);
  if ( pv )
    CoTaskMemFree(pv);
  v4 = v6;
  if ( !v6 )
    return 0;
  if ( *this )
    CoTaskMemFree(*this);
  *this = v4;
  this[2] = (LPVOID)-1LL;
  this[1] = (LPVOID)-1LL;
  *((_DWORD *)this + 6) = Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::GetStoreVersion((Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper *)this);
  return 1;
}

```

## disassembly

```asm
0x180015580  push    rbp
0x180015582  push    rbx
0x180015583  push    rsi
0x180015584  push    rdi
0x180015585  lea     rbp, [rsp-3Fh]
0x18001558a  sub     rsp, 0C8h
0x180015591  mov     rax, cs:__security_cookie
0x180015598  xor     rax, rsp
0x18001559b  mov     [rbp+57h+var_28], rax
0x18001559f  mov     rdi, rcx
0x1800155a2  xor     ebx, ebx
0x1800155a4  mov     [rbp+57h+var_B8], rbx
0x1800155a8  lea     rax, aAssignedaccess; "AssignedAccessConfiguration"
0x1800155af  mov     [rbp+57h+var_A8], rax
0x1800155b3  lea     rax, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\AssignedA"...
0x1800155ba  mov     [rbp+57h+var_B0], rax
0x1800155be  mov     [rbp+57h+pv], rbx
0x1800155c2  lea     rax, ??_7?$__func@V_lambda_6166c63e326ec22a386edc375e0b06c9_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_6166c63e326ec22a386edc375e0b06c9_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x1800155c9  mov     [rbp+57h+var_98], rax
0x1800155cd  lea     rax, [rbp+57h+var_B0]
0x1800155d1  mov     [rbp+57h+var_90], rax
0x1800155d5  lea     rax, [rbp+57h+var_A8]
0x1800155d9  mov     [rbp+57h+var_88], rax
0x1800155dd  lea     rax, [rbp+57h+var_98]
0x1800155e1  mov     [rbp+57h+var_30], rax
0x1800155e5  lea     rdx, [rbp+57h+var_A0]
0x1800155e9  lea     rcx, [rbp+57h+pv]
0x1800155ed  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)
0x1800155f2  mov     esi, eax
0x1800155f4  lea     rcx, [rbp+57h+var_A0]
0x1800155f8  call    ??1?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEAA@XZ; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::~function<long (ushort *,unsigned __int64,unsigned __int64 *)>(void)
0x1800155fd  test    esi, esi
0x1800155ff  jns     short loc_18001562C
0x180015601  mov     rcx, [rbp+5Fh]; this
0x180015605  mov     r9d, esi; char *
0x180015608  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18001560f  lea     edx, [rbx+1Fh]; void *
0x180015612  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015617  nop
0x180015618  mov     rcx, [rbp+57h+pv]; pv
0x18001561c  test    rcx, rcx
0x18001561f  jz      short loc_180015628
0x180015621  call    cs:__imp_CoTaskMemFree
0x180015627  nop
0x180015628  xor     al, al
0x18001562a  jmp     short loc_18001567F
0x18001562c  lea     rdx, [rbp+57h+pv]
0x180015630  lea     rcx, [rbp+57h+var_B8]
0x180015634  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180015639  nop
0x18001563a  mov     rcx, [rbp+57h+pv]; pv
0x18001563e  test    rcx, rcx
0x180015641  jz      short loc_18001564A
0x180015643  call    cs:__imp_CoTaskMemFree
0x180015649  nop
0x18001564a  mov     rbx, [rbp+57h+var_B8]
0x18001564e  test    rbx, rbx
0x180015651  jnz     short loc_180015655
0x180015653  jmp     short loc_180015628
0x180015655  mov     rcx, [rdi]; pv
0x180015658  test    rcx, rcx
0x18001565b  jz      short loc_180015663
0x18001565d  call    cs:__imp_CoTaskMemFree
0x180015663  mov     [rdi], rbx
0x180015666  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001566a  mov     [rdi+10h], rax
0x18001566e  mov     [rdi+8], rax
0x180015672  mov     rcx, rdi; this
0x180015675  call    ?GetStoreVersion@AssignedAccessConfigStoreHelper@AssignedAccess@Internal@Windows@@AEAAKXZ; Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::GetStoreVersion(void)
0x18001567a  mov     [rdi+18h], eax
0x18001567d  mov     al, 1
0x18001567f  mov     rcx, [rbp+57h+var_28]
0x180015683  xor     rcx, rsp; StackCookie
0x180015686  call    __security_check_cookie
0x18001568b  add     rsp, 0C8h
0x180015692  pop     rdi
0x180015693  pop     rsi
0x180015694  pop     rbx
0x180015695  pop     rbp
0x180015696  retn
```
