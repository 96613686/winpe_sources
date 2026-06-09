# PrintScanBrokerUtilities::GetCallerUserSid(void)

- ea: `0x180035798`
- end: `0x18003589b`
- name: `?GetCallerUserSid@PrintScanBrokerUtilities@@YA?AUhstring@winrt@@XZ`
- size: `259`
- prototype: `void *__fastcall(void *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800293fc`
- `0x18002a148`

## callees

- `0x180002d40`
- `0x18000792c`
- `0x18000f8a8`
- `0x18001255c`
- `0x18001cfb4`
- `0x180027cb4`
- `0x180028758`
- `0x18002f194`
- `0x180035798`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180035854`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180035854`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800357e2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800357e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800357cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800357cc`

## string_xrefs

- `0x180035877`: `onecoreuap\printscan\print\printscanbroker\class\utilities.cpp`
- `0x180035889`: `onecoreuap\printscan\print\printscanbroker\class\utilities.cpp`

## pseudocode

```c
void *__fastcall PrintScanBrokerUtilities::GetCallerUserSid(void *a1)
{
  HANDLE CurrentThread; // rax
  const char *v3; // r9
  int UserSidFromToken; // eax
  const unsigned __int16 *v5; // rdx
  int v7; // [rsp+20h] [rbp-40h] BYREF
  void *TokenHandle[2]; // [rsp+28h] [rbp-38h] BYREF
  unsigned __int16 *v9[2]; // [rsp+38h] [rbp-28h] BYREF
  __m128i si128; // [rsp+48h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  TokenHandle[0] = a1;
  wil::CoImpersonateClient(&v7);
  TokenHandle[0] = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, TokenHandle) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\utilities.cpp",
      v3);
  *(_OWORD *)v9 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v9[0]) = 0;
  UserSidFromToken = PrintCore::TokenHelpers::GetUserSidFromToken(TokenHandle[0]);
  if ( UserSidFromToken < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x67,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\utilities.cpp",
      (const char *)(unsigned int)UserSidFromToken,
      v7);
  v5 = (const unsigned __int16 *)v9;
  if ( si128.m128i_i64[1] > 7uLL )
    v5 = v9[0];
  winrt::hstring::hstring((winrt::hstring *)a1, v5);
  std::wstring::_Tidy_deallocate(v9);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(TokenHandle);
  if ( (_BYTE)v7 )
    CoRevertToSelf();
  return a1;
}

```

## disassembly

```asm
0x180035798  mov     [rsp-8+arg_8], rbx
0x18003579d  push    rbp
0x18003579e  mov     rbp, rsp
0x1800357a1  sub     rsp, 60h
0x1800357a5  mov     rax, cs:__security_cookie
0x1800357ac  xor     rax, rsp
0x1800357af  mov     [rbp+var_8], rax
0x1800357b3  mov     rbx, rcx
0x1800357b6  mov     [rbp+TokenHandle], rcx
0x1800357ba  lea     rcx, [rbp+var_40]
0x1800357be  call    ?CoImpersonateClient@wil@@YA?AV?$unique_call@P6AJXZ$1?CoRevertToSelf@@YAJXZ$00@1@XZ; wil::CoImpersonateClient(void)
0x1800357c3  nop
0x1800357c4  mov     [rbp+TokenHandle], 0
0x1800357cc  call    cs:__imp_GetCurrentThread
0x1800357d2  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800357d6  mov     edx, 8; DesiredAccess
0x1800357db  lea     r8d, [rdx-7]; OpenAsSelf
0x1800357df  mov     rcx, rax; ThreadHandle
0x1800357e2  call    cs:__imp_OpenThreadToken
0x1800357e8  mov     rcx, [rbp+8]; this
0x1800357ec  test    eax, eax
0x1800357ee  jz      loc_180035889
0x1800357f4  xorps   xmm0, xmm0
0x1800357f7  movups  xmmword ptr [rbp+var_28], xmm0
0x1800357fb  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180035803  movdqu  [rbp+var_18], xmm1
0x180035808  xor     eax, eax
0x18003580a  mov     word ptr [rbp+var_28], ax
0x18003580e  lea     rdx, [rbp+var_28]
0x180035812  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180035816  call    ?GetUserSidFromToken@TokenHelpers@PrintCore@@SAJPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PrintCore::TokenHelpers::GetUserSidFromToken(void *,std::wstring &)
0x18003581b  mov     rcx, [rbp+8]; this
0x18003581f  test    eax, eax
0x180035821  js      short loc_180035874
0x180035823  lea     rdx, [rbp+var_28]
0x180035827  cmp     qword ptr [rbp+var_18+8], 7
0x18003582c  cmova   rdx, [rbp+var_28]; unsigned __int16 *
0x180035831  mov     rcx, rbx; this
0x180035834  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x180035839  nop
0x18003583a  lea     rcx, [rbp+var_28]
0x18003583e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180035843  nop
0x180035844  lea     rcx, [rbp+TokenHandle]
0x180035848  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003584d  nop
0x18003584e  cmp     byte ptr [rbp+var_40], 0
0x180035852  jz      short loc_18003585A
0x180035854  call    cs:__imp_CoRevertToSelf
0x18003585a  mov     rax, rbx
0x18003585d  mov     rcx, [rbp+var_8]
0x180035861  xor     rcx, rsp; StackCookie
0x180035864  call    __security_check_cookie
0x180035869  mov     rbx, [rsp+60h+arg_8]
0x18003586e  add     rsp, 60h
0x180035872  pop     rbp
0x180035873  retn
0x180035874  mov     r9d, eax; char *
0x180035877  lea     r8, aOnecoreuapPrin_0; "onecoreuap\\printscan\\print\\printscan"...
0x18003587e  mov     edx, 67h ; 'g'; void *
0x180035883  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180035889  lea     r8, aOnecoreuapPrin_0; "onecoreuap\\printscan\\print\\printscan"...
0x180035890  mov     edx, 64h ; 'd'; void *
0x180035895  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
