# NamespaceRestrictionHelper::IsNetworkOrURLItem(IShellItem *)

- ea: `0x180058220`
- end: `0x1800582ce`
- name: `?IsNetworkOrURLItem@NamespaceRestrictionHelper@@AEAA_NPEAUIShellItem@@@Z`
- size: `174`
- prototype: `bool(NamespaceRestrictionHelper *__hidden this, struct IShellItem *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005a8ac`

## callees

- `0x1800292a8`
- `0x180035c0c`
- `0x180053ee0`
- `0x180058220`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058264`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180058264`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x180058299`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x180058299`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x180058257`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x180058257`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall NamespaceRestrictionHelper::IsNetworkOrURLItem(NamespaceRestrictionHelper *this, struct IShellItem *a2)
{
  char v3; // di
  BOOL IsNetworkPathW; // ebx
  enum _SIGDN v5; // edx
  bool v6; // bl
  LPCWSTR pszPath; // [rsp+30h] [rbp+8h] BYREF

  pszPath = 0;
  v3 = 1;
  if ( (int)GetIdentityItemName(a2, (enum _SIGDN)a2, (unsigned __int16 **)&pszPath) < 0
    || (IsNetworkPathW = PathIsNetworkPathW(pszPath), CoTaskMemFree((LPVOID)pszPath), !IsNetworkPathW) )
  {
    pszPath = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &pszPath,
      0);
    v6 = (int)GetIdentityItemName(a2, v5, (unsigned __int16 **)&pszPath) >= 0 && PathIsURLW(pszPath);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszPath);
    if ( !v6 )
      return 0;
  }
  return v3;
}

```

## disassembly

```asm
0x180058220  mov     rax, rsp
0x180058223  mov     [rax+10h], rbx
0x180058227  mov     [rax+18h], rsi
0x18005822b  mov     [rax+8], rcx
0x18005822f  push    rdi
0x180058230  sub     rsp, 20h
0x180058234  mov     rsi, rdx
0x180058237  mov     qword ptr [rax+8], 0
0x18005823f  lea     r8, [rax+8]; unsigned __int16 **
0x180058243  mov     rcx, rdx; struct IShellItem *
0x180058246  call    ?GetIdentityItemName@@YAJPEAUIShellItem@@W4_SIGDN@@PEAPEAG@Z; GetIdentityItemName(IShellItem *,_SIGDN,ushort * *)
0x18005824b  mov     dil, 1
0x18005824e  test    eax, eax
0x180058250  js      short loc_18005826E
0x180058252  mov     rcx, [rsp+28h+pszPath]; pszPath
0x180058257  call    cs:__imp_PathIsNetworkPathW
0x18005825d  mov     ebx, eax
0x18005825f  mov     rcx, [rsp+28h+pszPath]; pv
0x180058264  call    cs:__imp_CoTaskMemFree
0x18005826a  test    ebx, ebx
0x18005826c  jnz     short loc_1800582BB
0x18005826e  mov     [rsp+28h+pszPath], 0
0x180058277  xor     edx, edx
0x180058279  lea     rcx, [rsp+28h+pszPath]
0x18005827e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180058283  lea     r8, [rsp+28h+pszPath]; unsigned __int16 **
0x180058288  mov     rcx, rsi; struct IShellItem *
0x18005828b  call    ?GetIdentityItemName@@YAJPEAUIShellItem@@W4_SIGDN@@PEAPEAG@Z; GetIdentityItemName(IShellItem *,_SIGDN,ushort * *)
0x180058290  test    eax, eax
0x180058292  js      short loc_1800582A8
0x180058294  mov     rcx, [rsp+28h+pszPath]; pszPath
0x180058299  call    cs:__imp_PathIsURLW
0x18005829f  test    eax, eax
0x1800582a1  jz      short loc_1800582A8
0x1800582a3  mov     bl, dil
0x1800582a6  jmp     short loc_1800582AA
0x1800582a8  xor     bl, bl
0x1800582aa  lea     rcx, [rsp+28h+pszPath]
0x1800582af  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800582b4  test    bl, bl
0x1800582b6  jnz     short loc_1800582BB
0x1800582b8  xor     dil, dil
0x1800582bb  mov     al, dil
0x1800582be  mov     rbx, [rsp+28h+arg_8]
0x1800582c3  mov     rsi, [rsp+28h+arg_10]
0x1800582c8  add     rsp, 20h
0x1800582cc  pop     rdi
0x1800582cd  retn
```
