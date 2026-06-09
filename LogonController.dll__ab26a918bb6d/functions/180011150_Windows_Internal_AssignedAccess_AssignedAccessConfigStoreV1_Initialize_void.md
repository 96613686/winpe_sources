# Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::Initialize(void)

- ea: `0x180011150`
- end: `0x180011291`
- name: `?Initialize@AssignedAccessConfigStoreV1@AssignedAccess@Internal@Windows@@MEAA_NXZ`
- size: `321`
- prototype: `bool __fastcall(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180011150`
- `0x1800112a0`
- `0x180012930`
- `0x18005d488`
- `0x180060464`
- `0x18006c000`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800111fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001127e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011289`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800111fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001127e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011289`

## string_xrefs

- `0x18001118b`: `SOFTWARE\Microsoft\Windows\AssignedAccessConfiguration`
- `0x18001117f`: `AssignedAccessConfiguration`
- `0x180011262`: `shellcommondesktopbase\base\embedded\sys\lockdown\inc\persistentlocationhelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1::Initialize(
        Windows::Internal::AssignedAccess::AssignedAccessConfigStoreV1 *this)
{
  int v2; // ebx
  char v3; // bl
  __int64 v4; // rsi
  void *v5; // rcx
  LPVOID pv; // [rsp+20h] [rbp-A8h] BYREF
  __int64 v8; // [rsp+28h] [rbp-A0h] BYREF
  const wchar_t *v9; // [rsp+30h] [rbp-98h] BYREF
  const wchar_t *v10; // [rsp+38h] [rbp-90h] BYREF
  _BYTE v11[8]; // [rsp+40h] [rbp-88h] BYREF
  _QWORD v12[14]; // [rsp+48h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v8 = 0;
  v10 = L"AssignedAccessConfiguration";
  v9 = L"SOFTWARE\\Microsoft\\Windows\\AssignedAccessConfiguration";
  pv = 0;
  v12[0] = &wistd::__function::__func<_lambda_42d7dced1872ed24a4c1197da8e68253_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
  v12[1] = &v9;
  v12[2] = &v10;
  v12[13] = v12;
  v2 = wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
         (__int64)&pv,
         (__int64)v11);
  wistd::function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::~function<long (unsigned short *,unsigned __int64,unsigned __int64 *)>(v11);
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
  }
  else
  {
    v3 = 0;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &v8,
      &pv);
    if ( pv )
      CoTaskMemFree(pv);
    v4 = v8;
    if ( v8 )
    {
      v5 = (void *)*((_QWORD *)this + 1);
      if ( v5 )
        CoTaskMemFree(v5);
      *((_QWORD *)this + 1) = v4;
      *((_QWORD *)this + 3) = -1;
      *((_QWORD *)this + 2) = -1;
      v3 = 1;
    }
    if ( v3 )
      return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180011150  mov     r11, rsp
0x180011153  mov     [r11+8], rbx
0x180011157  mov     [r11+10h], rsi
0x18001115b  push    rdi
0x18001115c  sub     rsp, 0C0h
0x180011163  mov     rax, cs:__security_cookie
0x18001116a  xor     rax, rsp
0x18001116d  mov     [rsp+0C8h+var_10], rax
0x180011175  mov     rdi, rcx
0x180011178  xor     ecx, ecx
0x18001117a  mov     [rsp+0C8h+var_A0], rcx
0x18001117f  lea     rax, aAssignedaccess; "AssignedAccessConfiguration"
0x180011186  mov     [rsp+0C8h+var_90], rax
0x18001118b  lea     rax, aSoftwareMicros_19; "SOFTWARE\\Microsoft\\Windows\\AssignedA"...
0x180011192  mov     [rsp+0C8h+var_98], rax
0x180011197  mov     [rsp+0C8h+pv], rcx; int
0x18001119c  lea     rax, ??_7?$__func@V_lambda_42d7dced1872ed24a4c1197da8e68253_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_42d7dced1872ed24a4c1197da8e68253_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x1800111a3  mov     [r11-80h], rax
0x1800111a7  lea     rax, [rsp+0C8h+var_98]
0x1800111ac  mov     [r11-78h], rax
0x1800111b0  lea     rax, [rsp+0C8h+var_90]
0x1800111b5  mov     [r11-70h], rax
0x1800111b9  lea     rax, [r11-80h]
0x1800111bd  mov     [r11-18h], rax
0x1800111c1  lea     rdx, [rsp+0C8h+var_88]
0x1800111c6  lea     rcx, [rsp+0C8h+pv]
0x1800111cb  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)
0x1800111d0  mov     ebx, eax
0x1800111d2  lea     rcx, [rsp+0C8h+var_88]
0x1800111d7  call    ??1?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@QEAA@XZ; wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)>::~function<long (ushort *,unsigned __int64,unsigned __int64 *)>(void)
0x1800111dc  test    ebx, ebx
0x1800111de  js      short loc_180011257
0x1800111e0  xor     bl, bl
0x1800111e2  lea     rdx, [rsp+0C8h+pv]
0x1800111e7  lea     rcx, [rsp+0C8h+var_A0]
0x1800111ec  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800111f1  nop
0x1800111f2  mov     rcx, [rsp+0C8h+pv]; pv
0x1800111f7  test    rcx, rcx
0x1800111fa  jz      short loc_180011203
0x1800111fc  call    cs:__imp_CoTaskMemFree
0x180011202  nop
0x180011203  mov     rsi, [rsp+0C8h+var_A0]
0x180011208  test    rsi, rsi
0x18001120b  jz      short loc_18001122C
0x18001120d  mov     rcx, [rdi+8]; pv
0x180011211  test    rcx, rcx
0x180011214  jnz     short loc_180011289
0x180011216  mov     [rdi+8], rsi
0x18001121a  mov     qword ptr [rdi+18h], 0FFFFFFFFFFFFFFFFh
0x180011222  mov     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFFFh
0x18001122a  mov     bl, 1
0x18001122c  test    bl, bl
0x18001122e  jz      short loc_180011285
0x180011230  mov     al, 1
0x180011232  mov     rcx, [rsp+0C8h+var_10]
0x18001123a  xor     rcx, rsp; StackCookie
0x18001123d  call    __security_check_cookie
0x180011242  lea     r11, [rsp+0C8h+var_8]
0x18001124a  mov     rbx, [r11+10h]
0x18001124e  mov     rsi, [r11+18h]
0x180011252  mov     rsp, r11
0x180011255  pop     rdi
0x180011256  retn
0x180011257  mov     rcx, [rsp+0C8h]; this
0x18001125f  mov     r9d, ebx; char *
0x180011262  lea     r8, aShellcommondes; "shellcommondesktopbase\\base\\embedded"...
0x180011269  mov     edx, 1Fh; void *
0x18001126e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011273  nop
0x180011274  mov     rcx, [rsp+0C8h+pv]; pv
0x180011279  test    rcx, rcx
0x18001127c  jz      short loc_180011285
0x18001127e  call    cs:__imp_CoTaskMemFree
0x180011284  nop
0x180011285  xor     al, al
0x180011287  jmp     short loc_180011232
0x180011289  call    cs:__imp_CoTaskMemFree
0x18001128f  jmp     short loc_180011216
```
