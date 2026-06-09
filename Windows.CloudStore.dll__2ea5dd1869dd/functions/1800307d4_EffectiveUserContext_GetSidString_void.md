# EffectiveUserContext::GetSidString(void)

- ea: `0x1800307d4`
- end: `0x18003091c`
- name: `?GetSidString@EffectiveUserContext@@QEBAPEBGXZ`
- size: `328`
- prototype: `const unsigned __int16 *__fastcall(EffectiveUserContext *__hidden this)`
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180010020`
- `0x18002f260`
- `0x1800e6384`
- `0x180108080`
- `0x180176220`

## callees

- `0x180024300`
- `0x1800307d4`
- `0x180031e18`
- `0x180031e70`
- `0x180120850`
- `0x180178038`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030902`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030902`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800307f1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800307f1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800308a0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800308a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003080c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003082a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003080c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003082a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800308cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800308cd`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180030870`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180030870`

## string_xrefs

- `0x18003090a`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
const unsigned __int16 *__fastcall EffectiveUserContext::GetSidString(__int64 **this)
{
  RTL_SRWLOCK *v2; // rbx
  __int64 v3; // rsi
  __int64 v5; // rdx
  const char *v6; // r9
  RTL_SRWLOCK *v7; // rbx
  _QWORD *v8; // rcx
  __int64 v9; // rdi
  void *v10; // rcx
  LPWSTR StringSid; // [rsp+28h] [rbp-18h] BYREF
  char v12; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  HLOCAL hMem; // [rsp+60h] [rbp+20h] BYREF
  void *Block; // [rsp+68h] [rbp+28h] BYREF

  v2 = (RTL_SRWLOCK *)(this[2] + 1);
  AcquireSRWLockShared(v2);
  v3 = this[2][3];
  if ( v3 )
  {
    if ( v2 )
      ReleaseSRWLockShared(v2);
    return (const unsigned __int16 *)v3;
  }
  else
  {
    if ( v2 )
      ReleaseSRWLockShared(v2);
    if ( *this )
      v5 = **this;
    else
      v5 = 0;
    wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&Block, v5);
    hMem = 0;
    StringSid = 0;
    v12 = 1;
    if ( !ConvertSidToStringSidW(*(PSID *)Block, &StringSid) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x23A,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
        v6);
    if ( v12 )
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &hMem,
        StringSid);
    v7 = (RTL_SRWLOCK *)(this[2] + 1);
    AcquireSRWLockExclusive(v7);
    v8 = this[2] + 3;
    if ( !*v8 )
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        v8,
        &hMem);
    v9 = this[2][3];
    if ( v7 )
      ReleaseSRWLockExclusive(v7);
    if ( hMem )
      LocalFree(hMem);
    v10 = Block;
    Block = 0;
    if ( v10 )
      operator delete(v10);
    return (const unsigned __int16 *)v9;
  }
}

```

## disassembly

```asm
0x1800307d4  mov     [rsp-18h+arg_10], rbx
0x1800307d9  push    rbp
0x1800307da  push    rsi
0x1800307db  push    rdi
0x1800307dc  mov     rbp, rsp
0x1800307df  sub     rsp, 40h
0x1800307e3  mov     rdi, rcx
0x1800307e6  mov     rbx, [rcx+10h]
0x1800307ea  add     rbx, 8
0x1800307ee  mov     rcx, rbx; SRWLock
0x1800307f1  call    cs:__imp_AcquireSRWLockShared
0x1800307f7  mov     rax, [rdi+10h]
0x1800307fb  mov     rsi, [rax+18h]
0x1800307ff  test    rsi, rsi
0x180030802  jz      short loc_180030822
0x180030804  test    rbx, rbx
0x180030807  jz      short loc_180030812
0x180030809  mov     rcx, rbx; SRWLock
0x18003080c  call    cs:__imp_ReleaseSRWLockShared
0x180030812  mov     rax, rsi
0x180030815  mov     rbx, [rsp+40h+arg_10]
0x18003081a  add     rsp, 40h
0x18003081e  pop     rdi
0x18003081f  pop     rsi
0x180030820  pop     rbp
0x180030821  retn
0x180030822  test    rbx, rbx
0x180030825  jz      short loc_180030830
0x180030827  mov     rcx, rbx; SRWLock
0x18003082a  call    cs:__imp_ReleaseSRWLockShared
0x180030830  mov     rax, [rdi]
0x180030833  test    rax, rax
0x180030836  jz      loc_1800308FB
0x18003083c  mov     rdx, [rax]
0x18003083f  lea     rcx, [rbp+Block]
0x180030843  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x180030848  nop
0x180030849  mov     [rbp+hMem], 0
0x180030851  lea     rax, [rbp+hMem]
0x180030855  mov     [rbp+var_20], rax
0x180030859  mov     [rbp+StringSid], 0
0x180030861  mov     [rbp+var_10], 1
0x180030865  lea     rdx, [rbp+StringSid]; StringSid
0x180030869  mov     rcx, [rbp+Block]
0x18003086d  mov     rcx, [rcx]; Sid
0x180030870  call    cs:__imp_ConvertSidToStringSidW
0x180030876  mov     rcx, [rbp+18h]; this
0x18003087a  test    eax, eax
0x18003087c  jz      loc_18003090A
0x180030882  cmp     [rbp+var_10], 0
0x180030886  jz      short loc_180030895
0x180030888  mov     rdx, [rbp+StringSid]
0x18003088c  mov     rcx, [rbp+var_20]
0x180030890  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180030895  mov     rbx, [rdi+10h]
0x180030899  add     rbx, 8
0x18003089d  mov     rcx, rbx; SRWLock
0x1800308a0  call    cs:__imp_AcquireSRWLockExclusive
0x1800308a6  mov     rcx, [rdi+10h]
0x1800308aa  add     rcx, 18h
0x1800308ae  cmp     qword ptr [rcx], 0
0x1800308b2  jnz     short loc_1800308BD
0x1800308b4  lea     rdx, [rbp+hMem]
0x1800308b8  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800308bd  mov     rax, [rdi+10h]
0x1800308c1  mov     rdi, [rax+18h]
0x1800308c5  test    rbx, rbx
0x1800308c8  jz      short loc_1800308D4
0x1800308ca  mov     rcx, rbx; SRWLock
0x1800308cd  call    cs:__imp_ReleaseSRWLockExclusive
0x1800308d3  nop
0x1800308d4  mov     rcx, [rbp+hMem]; hMem
0x1800308d8  test    rcx, rcx
0x1800308db  jnz     short loc_180030902
0x1800308dd  mov     rcx, [rbp+Block]; Block
0x1800308e1  mov     [rbp+Block], 0
0x1800308e9  test    rcx, rcx
0x1800308ec  jz      short loc_1800308F3
0x1800308ee  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800308f3  mov     rax, rdi
0x1800308f6  jmp     loc_180030815
0x1800308fb  xor     edx, edx
0x1800308fd  jmp     loc_18003083F
0x180030902  call    cs:__imp_LocalFree
0x180030908  jmp     short loc_1800308DD
0x18003090a  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudstore\\common\\"...
0x180030911  mov     edx, 23Ah; void *
0x180030916  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
