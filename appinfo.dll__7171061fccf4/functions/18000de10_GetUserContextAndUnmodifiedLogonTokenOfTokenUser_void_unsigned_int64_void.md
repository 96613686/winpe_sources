# GetUserContextAndUnmodifiedLogonTokenOfTokenUser(void *,unsigned __int64 *,void * *)

- ea: `0x18000de10`
- end: `0x18000deb3`
- name: `?GetUserContextAndUnmodifiedLogonTokenOfTokenUser@@YAJPEAXPEA_KPEAPEAX@Z`
- size: `163`
- prototype: `__int64 __fastcall(void *, unsigned __int64 *, void **)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002b27c`
- `0x18002bc04`
- `0x18002c480`
- `0x180035dbc`

## callees

- `0x18000720c`
- `0x18000de10`

## import_xrefs

- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18000de6a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18000de6a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18000de2d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18000de2d`

## string_xrefs

- `0x18000de3e`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18000de7b`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

## pseudocode

```c
__int64 __fastcall GetUserContextAndUnmodifiedLogonTokenOfTokenUser(void *a1, unsigned __int64 *a2, void **a3)
{
  int UserContext; // eax
  unsigned int v6; // esi
  int UserToken; // eax
  unsigned int v9; // ebx
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *a2 = 0;
  *a3 = 0;
  UserContext = UMgrQueryUserContext(a1, a2);
  v6 = UserContext;
  if ( UserContext >= 0 )
  {
    UserToken = UMgrQueryUserToken(*a2, a3);
    v9 = UserToken;
    if ( UserToken >= 0 )
    {
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x159D,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)UserToken,
        v10);
      return v9;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x159C,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)UserContext,
      v10);
    return v6;
  }
}

```

## disassembly

```asm
0x18000de10  mov     [rsp+arg_0], rbx
0x18000de15  mov     [rsp+arg_8], rsi
0x18000de1a  push    rdi; int
0x18000de1b  sub     rsp, 20h
0x18000de1f  xor     eax, eax
0x18000de21  mov     rdi, r8
0x18000de24  mov     [rdx], rax
0x18000de27  mov     rbx, rdx
0x18000de2a  mov     [r8], rax
0x18000de2d  call    cs:__imp_UMgrQueryUserContext
0x18000de33  mov     esi, eax
0x18000de35  test    eax, eax
0x18000de37  jns     short loc_18000DE64
0x18000de39  mov     rcx, [rsp+28h]; this
0x18000de3e  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18000de45  mov     r9d, eax; char *
0x18000de48  mov     edx, 159Ch; void *
0x18000de4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000de52  mov     eax, esi
0x18000de54  mov     rbx, [rsp+28h+arg_0]
0x18000de59  mov     rsi, [rsp+28h+arg_8]
0x18000de5e  add     rsp, 20h
0x18000de62  pop     rdi
0x18000de63  retn
0x18000de64  mov     rcx, [rbx]
0x18000de67  mov     rdx, rdi
0x18000de6a  call    cs:__imp_UMgrQueryUserToken
0x18000de70  mov     ebx, eax
0x18000de72  test    eax, eax
0x18000de74  jns     short loc_18000DEA1
0x18000de76  mov     rcx, [rsp+28h]; this
0x18000de7b  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18000de82  mov     r9d, eax; char *
0x18000de85  mov     edx, 159Dh; void *
0x18000de8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000de8f  mov     eax, ebx
0x18000de91  mov     rbx, [rsp+28h+arg_0]
0x18000de96  mov     rsi, [rsp+28h+arg_8]
0x18000de9b  add     rsp, 20h
0x18000de9f  pop     rdi
0x18000dea0  retn
0x18000dea1  mov     rbx, [rsp+28h+arg_0]
0x18000dea6  xor     eax, eax
0x18000dea8  mov     rsi, [rsp+28h+arg_8]
0x18000dead  add     rsp, 20h
0x18000deb1  pop     rdi
0x18000deb2  retn
```
