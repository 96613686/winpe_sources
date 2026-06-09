# Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::Initialize(void)

- ea: `0x1800105d4`
- end: `0x1800106ef`
- name: `?Initialize@AssignedAccessConfigStoreHelper@AssignedAccess@Internal@Windows@@AEAA_NXZ`
- size: `283`
- prototype: `bool __fastcall(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180010348`

## callees

- `0x1800105d4`
- `0x1800112a0`
- `0x1800112bc`
- `0x180012930`
- `0x18005d488`
- `0x180060464`
- `0x18006c000`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001066c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800106de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800106e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001066c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800106de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800106e7`

## string_xrefs

- `0x180010607`: `SOFTWARE\Microsoft\Windows\AssignedAccessConfiguration`
- `0x1800105fc`: `AssignedAccessConfiguration`
- `0x1800106c3`: `shellcommondesktopbase\base\embedded\sys\lockdown\inc\persistentlocationhelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::Initialize(LPVOID *this)
{
  int v2; // esi
  void *v3; // rbx
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
  v10[0] = &wistd::__function::__func<_lambda_42d7dced1872ed24a4c1197da8e68253_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
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
      (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\inc\\persistentlocationhelper.h",
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
  v3 = v6;
  if ( !v6 )
    return 0;
  if ( *this )
    CoTaskMemFree(*this);
  *this = v3;
  this[2] = (LPVOID)-1LL;
  this[1] = (LPVOID)-1LL;
  *((_DWORD *)this + 6) = Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::GetStoreVersion((Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper *)this);
  return 1;
}

```

## disassembly

```asm
0x1800105d4  push    rbp
0x1800105d6  push    rbx
0x1800105d7  push    rsi
0x1800105d8  push    rdi
0x1800105d9  lea     rbp, [rsp-3Fh]
0x1800105de  sub     rsp, 0C8h
0x1800105e5  mov     rax, cs:__security_cookie
0x1800105ec  xor     rax, rsp
0x1800105ef  mov     [rbp+57h+var_28], rax
0x1800105f3  mov     rdi, rcx
0x1800105f6  xor     ebx, ebx
0x1800105f8  mov     [rbp+57h+var_B8], rbx
0x1800105fc  lea     rax, aAssignedaccess; "AssignedAccessConfiguration"
0x180010603  mov     [rbp+57h+var_A8], rax
0x180010607  lea     rax, aSoftwareMicros_19; "SOFTWARE\\Microsoft\\Windows\\AssignedA"...
0x18001060e  mov     [rbp+57h+var_B0], rax
0x180010612  mov     [rbp+57h+pv], rbx
0x180010616  lea     rax, ??_7?$__func@V_lambda_42d7dced1872ed24a4c1197da8e68253_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_42d7dced1872ed24a4c1197da8e68253_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x18001061d  mov     [rbp+57h+var_98], rax
0x180010621  lea     rax, [rbp+57h+var_B0]
0x180010625  mov     [rbp+57h+var_90], rax
0x180010629  lea     rax, [rbp+57h+var_A8]
0x18001062d  mov     [rbp+57h+var_88], rax
0x180010631  lea     rax, [rbp+57h+var_98]
0x180010635  mov     [rbp+57h+var_30], rax
0x180010639  lea     rdx, [rbp+57h+var_A0]
0x18001063d  lea     rcx, [rbp+57h+pv]
0x180010641  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)
0x180010646  mov     esi, eax
0x180010648  lea     rcx, [rbp+57h+var_A0]
0x18001064c  call    ??1?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEAA@XZ; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::~function<long (ushort *,unsigned __int64,unsigned __int64 *)>(void)
0x180010651  test    esi, esi
0x180010653  js      short loc_1800106BC
0x180010655  lea     rdx, [rbp+57h+pv]
0x180010659  lea     rcx, [rbp+57h+var_B8]
0x18001065d  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180010662  nop
0x180010663  mov     rcx, [rbp+57h+pv]; pv
0x180010667  test    rcx, rcx
0x18001066a  jz      short loc_180010673
0x18001066c  call    cs:__imp_CoTaskMemFree
0x180010672  nop
0x180010673  mov     rbx, [rbp+57h+var_B8]
0x180010677  test    rbx, rbx
0x18001067a  jnz     short loc_180010680
0x18001067c  xor     al, al
0x18001067e  jmp     short loc_1800106A4
0x180010680  mov     rcx, [rdi]; pv
0x180010683  test    rcx, rcx
0x180010686  jnz     short loc_1800106E7
0x180010688  mov     [rdi], rbx
0x18001068b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001068f  mov     [rdi+10h], rax
0x180010693  mov     [rdi+8], rax
0x180010697  mov     rcx, rdi; this
0x18001069a  call    ?GetStoreVersion@AssignedAccessConfigStoreHelper@AssignedAccess@Internal@Windows@@AEAAKXZ; Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::GetStoreVersion(void)
0x18001069f  mov     [rdi+18h], eax
0x1800106a2  mov     al, 1
0x1800106a4  mov     rcx, [rbp+57h+var_28]
0x1800106a8  xor     rcx, rsp; StackCookie
0x1800106ab  call    __security_check_cookie
0x1800106b0  add     rsp, 0C8h
0x1800106b7  pop     rdi
0x1800106b8  pop     rsi
0x1800106b9  pop     rbx
0x1800106ba  pop     rbp
0x1800106bb  retn
0x1800106bc  mov     rcx, [rbp+5Fh]; this
0x1800106c0  mov     r9d, esi; char *
0x1800106c3  lea     r8, aShellcommondes; "shellcommondesktopbase\\base\\embedded"...
0x1800106ca  mov     edx, 1Fh; void *
0x1800106cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800106d4  nop
0x1800106d5  mov     rcx, [rbp+57h+pv]; pv
0x1800106d9  test    rcx, rcx
0x1800106dc  jz      short loc_1800106E5
0x1800106de  call    cs:__imp_CoTaskMemFree
0x1800106e4  nop
0x1800106e5  jmp     short loc_18001067C
0x1800106e7  call    cs:__imp_CoTaskMemFree
0x1800106ed  jmp     short loc_180010688
```
