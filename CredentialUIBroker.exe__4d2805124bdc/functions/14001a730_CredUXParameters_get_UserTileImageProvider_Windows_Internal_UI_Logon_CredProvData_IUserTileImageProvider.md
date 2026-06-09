# CredUXParameters::get_UserTileImageProvider(Windows::Internal::UI::Logon::CredProvData::IUserTileImageProvider * *)

- ea: `0x14001a730`
- end: `0x14001a780`
- name: `?get_UserTileImageProvider@CredUXParameters@@UEAAJPEAPEAUIUserTileImageProvider@CredProvData@Logon@UI@Internal@Windows@@@Z`
- size: `80`
- prototype: `__int64 __fastcall(CredUXParameters *this, struct Windows::Internal::UI::Logon::CredProvData::IUserTileImageProvider **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400136fc`
- `0x14001a730`
- `0x14001f010`

## string_xrefs

- `0x14001a760`: `shellcommon\internal\shell\inc\creduxparameters.h`

## pseudocode

```c
__int64 __fastcall CredUXParameters::get_UserTileImageProvider(
        CredUXParameters *this,
        struct Windows::Internal::UI::Logon::CredProvData::IUserTileImageProvider **a2)
{
  __int64 v2; // rcx
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *a2 = 0;
  v2 = *((_QWORD *)this + 24);
  if ( !v2 )
    return 0;
  v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 80LL))(v2);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x162,
    (unsigned int)"shellcommon\\internal\\shell\\inc\\creduxparameters.h",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x14001a730  push    rbx; int
0x14001a732  sub     rsp, 20h
0x14001a736  mov     qword ptr [rdx], 0
0x14001a73d  mov     rcx, [rcx+0C0h]
0x14001a744  test    rcx, rcx
0x14001a747  jz      short loc_14001A778
0x14001a749  mov     rax, [rcx]
0x14001a74c  mov     rax, [rax+50h]
0x14001a750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a755  mov     ebx, eax
0x14001a757  test    eax, eax
0x14001a759  jns     short loc_14001A778
0x14001a75b  mov     rcx, [rsp+28h]; this
0x14001a760  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\cred"...
0x14001a767  mov     r9d, eax; char *
0x14001a76a  mov     edx, 162h; void *
0x14001a76f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a774  mov     eax, ebx
0x14001a776  jmp     short loc_14001A77A
0x14001a778  xor     eax, eax
0x14001a77a  add     rsp, 20h
0x14001a77e  pop     rbx
0x14001a77f  retn
```
