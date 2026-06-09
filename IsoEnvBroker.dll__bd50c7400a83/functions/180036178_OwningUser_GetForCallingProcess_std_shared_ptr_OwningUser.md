# OwningUser::GetForCallingProcess(std::shared_ptr<OwningUser> &)

- ea: `0x180036178`
- end: `0x18003624b`
- name: `?GetForCallingProcess@OwningUser@@SAJAEAV?$shared_ptr@VOwningUser@@@std@@@Z`
- size: `211`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180010b00`
- `0x180036488`

## callees

- `0x180002a54`
- `0x18000a464`
- `0x180010240`
- `0x180013270`
- `0x180036178`
- `0x180036254`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800361c5`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800361c5`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180036185`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180036185`

## string_xrefs

- `0x180036239`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x180036224`: `onecore\internal\sdk\inc\wil\opensource/wil/result_macros.h`
- `0x1800361e4`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\owninguser.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 OwningUser::GetForCallingProcess()
{
  HRESULT v0; // eax
  int token_information; // eax
  void **v2; // rbx
  int v3; // eax
  unsigned int v4; // edi
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *Block; // [rsp+38h] [rbp+10h] BYREF

  v0 = CoImpersonateClient();
  if ( v0 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x14AA,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      (const char *)(unsigned int)v0,
      v6);
  Block = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, -5);
  if ( token_information < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x1C9B,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/result_macros.h",
      (const char *)(unsigned int)token_information,
      v6);
  v2 = (void **)Block;
  CoRevertToSelf();
  v3 = OwningUser::GetForSid(*v2);
  v4 = v3;
  if ( v3 >= 0 )
  {
    if ( v2 )
      operator delete(v2);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x95,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\owninguser.cpp",
      (const char *)(unsigned int)v3,
      v6);
    if ( v2 )
      operator delete(v2);
    return v4;
  }
}

```

## disassembly

```asm
0x180036178  mov     [rsp+arg_0], rbx
0x18003617d  push    rdi; int
0x18003617e  sub     rsp, 20h
0x180036182  mov     rdi, rcx
0x180036185  call    cs:__imp_CoImpersonateClient
0x18003618b  mov     rcx, [rsp+28h]; this
0x180036190  test    eax, eax
0x180036192  js      loc_180036236
0x180036198  mov     [rsp+28h+Block], 0
0x1800361a1  mov     rdx, 0FFFFFFFFFFFFFFFBh
0x1800361a8  lea     rcx, [rsp+28h+Block]
0x1800361ad  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x1800361b2  mov     rcx, [rsp+28h]; this
0x1800361b7  test    eax, eax
0x1800361b9  js      short loc_180036221
0x1800361bb  mov     rbx, [rsp+28h+Block]
0x1800361c0  mov     [rsp+28h+Block], rbx
0x1800361c5  call    cs:__imp_CoRevertToSelf
0x1800361cb  mov     rdx, rdi
0x1800361ce  mov     rcx, [rbx]; void *
0x1800361d1  call    ?GetForSid@OwningUser@@SAJPEAXAEAV?$shared_ptr@VOwningUser@@@std@@@Z; OwningUser::GetForSid(void *,std::shared_ptr<OwningUser> &)
0x1800361d6  mov     edi, eax
0x1800361d8  test    eax, eax
0x1800361da  jns     short loc_180036207
0x1800361dc  mov     rcx, [rsp+28h]; this
0x1800361e1  mov     r9d, eax; char *
0x1800361e4  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800361eb  mov     edx, 95h; void *
0x1800361f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800361f5  nop
0x1800361f6  test    rbx, rbx
0x1800361f9  jz      short loc_180036203
0x1800361fb  mov     rcx, rbx; Block
0x1800361fe  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180036203  mov     eax, edi
0x180036205  jmp     short loc_180036216
0x180036207  test    rbx, rbx
0x18003620a  jz      short loc_180036214
0x18003620c  mov     rcx, rbx; Block
0x18003620f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180036214  xor     eax, eax
0x180036216  mov     rbx, [rsp+28h+arg_0]
0x18003621b  add     rsp, 20h
0x18003621f  pop     rdi
0x180036220  retn
0x180036221  mov     r9d, eax; char *
0x180036224  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003622b  mov     edx, 1C9Bh; void *
0x180036230  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180036236  mov     r9d, eax; char *
0x180036239  lea     r8, aOnecoreInterna_8; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180036240  mov     edx, 14AAh; void *
0x180036245  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
