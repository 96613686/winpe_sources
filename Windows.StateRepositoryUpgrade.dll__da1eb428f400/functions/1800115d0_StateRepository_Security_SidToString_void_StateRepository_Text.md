# StateRepository::Security::SidToString(void *,StateRepository::Text &)

- ea: `0x1800115d0`
- end: `0x1800116b2`
- name: `?SidToString@Security@StateRepository@@YAJPEAXAEAVText@2@@Z`
- size: `226`
- prototype: `__int64 __fastcall(PSID Sid, void *, struct StateRepository::Text *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180011a40`

## callees

- `0x18000a3a0`
- `0x18000a3c0`
- `0x18000f3e8`
- `0x18000f6e0`
- `0x1800115d0`
- `0x180012338`
- `0x1800148ec`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180011617`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180011617`

## string_xrefs

- `0x180011626`: `onecore\base\appmodel\staterepository\common\inc\Security.hpp`
- `0x18001168b`: `onecore\base\appmodel\staterepository\common\inc\Security.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Security::SidToString(
        PSID Sid,
        StateRepository::Text *a2,
        struct StateRepository::Text *a3)
{
  const char *v5; // r9
  int LastError; // ebx
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  int v9; // eax
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  LPWSTR StringSid; // [rsp+30h] [rbp+8h] BYREF
  unsigned __int16 *v14; // [rsp+40h] [rbp+18h] BYREF

  v14 = 0;
  if ( Sid )
  {
    StringSid = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &StringSid,
      0,
      a3);
    if ( ConvertSidToStringSidW(Sid, &StringSid) )
    {
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        &v14,
        &StringSid);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x23,
                    (unsigned int)"onecore\\base\\appmodel\\staterepository\\common\\inc\\Security.hpp",
                    v5);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
      if ( LastError < 0 )
      {
        v7 = (unsigned int)LastError;
        v8 = 47;
        goto LABEL_9;
      }
    }
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v14,
      0,
      a3);
  }
  v9 = StateRepository::Text::Set(a2, v14, 0);
  LastError = v9;
  if ( v9 >= 0 )
  {
    LastError = 0;
    goto LABEL_11;
  }
  v7 = (unsigned int)v9;
  v8 = 48;
LABEL_9:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\common\\inc\\Security.hpp",
    (const char *)v7,
    v11);
LABEL_11:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v14);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800115d0  mov     [rsp+arg_8], rbx
0x1800115d5  push    rdi; int
0x1800115d6  sub     rsp, 20h
0x1800115da  mov     rdi, rdx
0x1800115dd  mov     [rsp+28h+arg_10], 0
0x1800115e6  xor     edx, edx
0x1800115e8  mov     rbx, rcx
0x1800115eb  test    rcx, rcx
0x1800115ee  jnz     short loc_1800115FC
0x1800115f0  lea     rcx, [rsp+28h+arg_10]
0x1800115f5  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800115fa  jmp     short loc_180011668
0x1800115fc  lea     rcx, [rsp+28h+StringSid]
0x180011601  mov     [rsp+28h+StringSid], 0
0x18001160a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001160f  lea     rdx, [rsp+28h+StringSid]; StringSid
0x180011614  mov     rcx, rbx; Sid
0x180011617  call    cs:__imp_ConvertSidToStringSidW
0x18001161d  test    eax, eax
0x18001161f  jnz     short loc_18001164F
0x180011621  mov     rcx, [rsp+28h]; this
0x180011626  lea     r8, aOnecoreBaseApp_55; "onecore\\base\\appmodel\\staterepositor"...
0x18001162d  lea     edx, [rax+23h]; void *
0x180011630  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011635  lea     rcx, [rsp+28h+StringSid]
0x18001163a  mov     ebx, eax
0x18001163c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180011641  test    ebx, ebx
0x180011643  jns     short loc_180011668
0x180011645  mov     r9d, ebx
0x180011648  mov     edx, 2Fh ; '/'
0x18001164d  jmp     short loc_180011686
0x18001164f  lea     rdx, [rsp+28h+StringSid]
0x180011654  lea     rcx, [rsp+28h+arg_10]
0x180011659  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18001165e  lea     rcx, [rsp+28h+StringSid]
0x180011663  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180011668  mov     rdx, [rsp+28h+arg_10]; unsigned __int16 *
0x18001166d  xor     r8d, r8d; unsigned __int64
0x180011670  mov     rcx, rdi; this
0x180011673  call    ?Set@Text@StateRepository@@QEAAJPEBG_K@Z; StateRepository::Text::Set(ushort const *,unsigned __int64)
0x180011678  mov     ebx, eax
0x18001167a  test    eax, eax
0x18001167c  jns     short loc_180011699
0x18001167e  mov     r9d, eax; char *
0x180011681  mov     edx, 30h ; '0'; void *
0x180011686  mov     rcx, [rsp+28h]; this
0x18001168b  lea     r8, aOnecoreBaseApp_55; "onecore\\base\\appmodel\\staterepositor"...
0x180011692  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011697  jmp     short loc_18001169B
0x180011699  xor     ebx, ebx
0x18001169b  lea     rcx, [rsp+28h+arg_10]
0x1800116a0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800116a5  mov     eax, ebx
0x1800116a7  mov     rbx, [rsp+28h+arg_8]
0x1800116ac  add     rsp, 20h
0x1800116b0  pop     rdi
0x1800116b1  retn
```
