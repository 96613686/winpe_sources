# UserHelpers::GetUserContextToken(Windows::System::IUser *)

- ea: `0x180014794`
- end: `0x180014864`
- name: `?GetUserContextToken@UserHelpers@@YA_KPEAUIUser@System@Windows@@@Z`
- size: `208`
- prototype: `__int64 __fastcall(UserHelpers *this, struct Windows::System::IUser *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180014a04`

## callees

- `0x1800028c4`
- `0x180003518`
- `0x18000cd18`
- `0x180011770`
- `0x180014794`
- `0x180015904`
- `0x180024010`

## import_xrefs

- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800147bf`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800147bf`

## pseudocode

```c
__int64 __fastcall UserHelpers::GetUserContextToken(UserHelpers *this, struct Windows::System::IUser *a2)
{
  int v3; // eax
  int v4; // eax
  unsigned int v6; // eax
  void *v7; // rdx
  unsigned int v8; // r8d
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v11; // [rsp+30h] [rbp+8h] BYREF
  __int64 v12; // [rsp+38h] [rbp+10h] BYREF

  v11 = 0;
  if ( this )
  {
    wil::GetActivationFactory<Windows::System::Internal::ISignInStateManager>(&v12);
    v4 = (*(__int64 (__fastcall **)(__int64, UserHelpers *, __int64 *))(*(_QWORD *)v12 + 136LL))(v12, this, &v11);
    if ( v4 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x2A,
        (int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\textinput\\UserHelpers.h",
        (const char *)(unsigned int)v4,
        v9);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  else
  {
    if ( !(unsigned __int8)IsUMgrQueryUserContextPresent(0, a2) )
    {
      v6 = wil::verify_hresult<long>(2147500033LL);
      wil::details::in1diag3::Throw_Hr(retaddr, v7, v8, (const char *)v6, v9);
    }
    v3 = UMgrQueryUserContext(0, &v11);
    if ( v3 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x20,
        (int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\textinput\\UserHelpers.h",
        (const char *)(unsigned int)v3,
        v9);
  }
  return v11;
}

```

## disassembly

```asm
0x180014794  push    rbx; int
0x180014796  sub     rsp, 20h
0x18001479a  mov     rbx, rcx
0x18001479d  mov     [rsp+28h+arg_0], 0
0x1800147a6  test    rcx, rcx
0x1800147a9  jnz     short loc_1800147CB
0x1800147ab  call    IsUMgrQueryUserContextPresent
0x1800147b0  test    al, al
0x1800147b2  jz      loc_18001484C
0x1800147b8  lea     rdx, [rsp+28h+arg_0]
0x1800147bd  xor     ecx, ecx
0x1800147bf  call    cs:__imp_UMgrQueryUserContext
0x1800147c5  test    eax, eax
0x1800147c7  js      short loc_180014832
0x1800147c9  jmp     short loc_180014812
0x1800147cb  lea     rcx, [rsp+28h+arg_8]
0x1800147d0  call    ??$GetActivationFactory@UISignInStateManager@Internal@System@Windows@@@wil@@YA?AV?$com_ptr_t@UISignInStateManager@Internal@System@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::System::Internal::ISignInStateManager>(ushort const *)
0x1800147d5  nop
0x1800147d6  mov     rcx, [rsp+28h+arg_8]
0x1800147db  mov     rax, [rcx]
0x1800147de  lea     r8, [rsp+28h+arg_0]
0x1800147e3  mov     rdx, rbx
0x1800147e6  mov     rax, [rax+88h]
0x1800147ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147f2  mov     rcx, [rsp+28h]; this
0x1800147f7  test    eax, eax
0x1800147f9  js      short loc_18001481D
0x1800147fb  mov     rcx, [rsp+28h+arg_8]
0x180014800  test    rcx, rcx
0x180014803  jz      short loc_180014812
0x180014805  mov     rax, [rcx]
0x180014808  mov     rax, [rax+10h]
0x18001480c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014811  nop
0x180014812  mov     rax, [rsp+28h+arg_0]
0x180014817  add     rsp, 20h
0x18001481b  pop     rbx
0x18001481c  retn
0x18001481d  mov     r9d, eax; char *
0x180014820  lea     r8, aOnecoreInterna_6; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180014827  mov     edx, 2Ah ; '*'; void *
0x18001482c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180014832  mov     rcx, [rsp+28h]; this
0x180014837  mov     r9d, eax; char *
0x18001483a  lea     r8, aOnecoreInterna_6; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180014841  mov     edx, 20h ; ' '; void *
0x180014846  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001484c  mov     ecx, 80004001h
0x180014851  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180014856  mov     r9d, eax; char *
0x180014859  mov     rcx, [rsp+28h]; this
0x18001485e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
