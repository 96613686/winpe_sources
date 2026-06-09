# Windows::Service::System::SystemOrAdminPrivilege(void)

- ea: `0x180053454`
- end: `0x180053528`
- name: `?SystemOrAdminPrivilege@System@Service@Windows@@UEAA_NXZ`
- size: `212`
- prototype: `bool __fastcall(Windows::Service::System *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180046270`

## callees

- `0x180053454`
- `0x1800672b4`
- `0x180067360`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053513`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053513`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800534a7`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800534ec`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800534a7`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800534ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall Windows::Service::System::SystemOrAdminPrivilege(Windows::Service::System *this)
{
  char v1; // di
  char v2; // si
  bool IsSidInToken; // bl
  char *v4; // rbx
  bool v5; // r14
  HANDLE v7; // [rsp+20h] [rbp-10h] BYREF
  PSID pSid; // [rsp+70h] [rbp+40h] BYREF
  char *v9; // [rsp+78h] [rbp+48h] BYREF

  v7 = 0;
  v1 = 1;
  v2 = 1;
  Windows::Trust::CreateSid(&pSid);
  IsSidInToken = Windows::Trust::IsSidInToken(&v7, &pSid);
  if ( pSid )
    FreeSid(pSid);
  if ( IsSidInToken )
  {
    v4 = v9;
  }
  else
  {
    v4 = 0;
    v9 = 0;
    v2 = 3;
    Windows::Trust::CreateSid(&pSid);
    v5 = Windows::Trust::IsSidInToken((HANDLE *)&v9, &pSid);
    if ( pSid )
      FreeSid(pSid);
    if ( !v5 )
      v1 = 0;
  }
  if ( (v2 & 2) != 0 && (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v4);
  return v1;
}

```

## disassembly

```asm
0x180053454  push    rbp
0x180053456  push    rbx
0x180053457  push    rsi
0x180053458  push    rdi
0x180053459  push    r14
0x18005345b  mov     rbp, rsp
0x18005345e  sub     rsp, 30h
0x180053462  mov     [rbp+arg_8], 0
0x180053469  mov     [rbp+var_10], 0
0x180053471  mov     edi, 1
0x180053476  mov     esi, edi
0x180053478  mov     [rbp+arg_8], edi
0x18005347b  xor     r9d, r9d
0x18005347e  lea     r8d, [rdi+11h]
0x180053482  mov     dl, dil
0x180053485  lea     rcx, [rbp+pSid]; pSid
0x180053489  call    ?CreateSid@Trust@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@EKK@Z; Windows::Trust::CreateSid(uchar,ulong,ulong)
0x18005348e  nop
0x18005348f  lea     rdx, [rbp+pSid]
0x180053493  lea     rcx, [rbp+var_10]
0x180053497  call    ?IsSidInToken@Trust@Windows@@YA_NAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@4@@Z; Windows::Trust::IsSidInToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> const &)
0x18005349c  mov     bl, al
0x18005349e  mov     rcx, [rbp+pSid]; pSid
0x1800534a2  test    rcx, rcx
0x1800534a5  jz      short loc_1800534AD
0x1800534a7  call    cs:__imp_FreeSid
0x1800534ad  test    bl, bl
0x1800534af  jnz     short loc_1800534FC
0x1800534b1  xor     ebx, ebx
0x1800534b3  mov     [rbp+arg_18], rbx
0x1800534b7  lea     esi, [rbx+3]
0x1800534ba  mov     [rbp+arg_8], esi
0x1800534bd  mov     r9d, 220h
0x1800534c3  lea     r8d, [rbx+20h]
0x1800534c7  mov     dl, 2
0x1800534c9  lea     rcx, [rbp+pSid]; pSid
0x1800534cd  call    ?CreateSid@Trust@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@EKK@Z; Windows::Trust::CreateSid(uchar,ulong,ulong)
0x1800534d2  nop
0x1800534d3  lea     rdx, [rbp+pSid]
0x1800534d7  lea     rcx, [rbp+arg_18]
0x1800534db  call    ?IsSidInToken@Trust@Windows@@YA_NAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@4@@Z; Windows::Trust::IsSidInToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> const &)
0x1800534e0  mov     r14b, al
0x1800534e3  mov     rcx, [rbp+pSid]; pSid
0x1800534e7  test    rcx, rcx
0x1800534ea  jz      short loc_1800534F2
0x1800534ec  call    cs:__imp_FreeSid
0x1800534f2  test    r14b, r14b
0x1800534f5  jnz     short loc_180053500
0x1800534f7  xor     dil, dil
0x1800534fa  jmp     short loc_180053500
0x1800534fc  mov     rbx, [rbp+arg_18]
0x180053500  test    sil, 2
0x180053504  jz      short loc_18005351A
0x180053506  lea     rdx, [rbx-1]
0x18005350a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18005350e  ja      short loc_18005351A
0x180053510  mov     rcx, rbx; hObject
0x180053513  call    cs:__imp_CloseHandle
0x180053519  nop
0x18005351a  mov     al, dil
0x18005351d  add     rsp, 30h
0x180053521  pop     r14
0x180053523  pop     rdi
0x180053524  pop     rsi
0x180053525  pop     rbx
0x180053526  pop     rbp
0x180053527  retn
```
