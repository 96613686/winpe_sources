# GetUserContextAndUnmodifiedLogonTokenOfTokenUser(void *,unsigned __int64 *,void * *)

- ea: `0x1800092f0`
- end: `0x1800093a2`
- name: `?GetUserContextAndUnmodifiedLogonTokenOfTokenUser@@YAJPEAXPEA_KPEAPEAX@Z`
- size: `178`
- prototype: `int(void *, unsigned __int64 *, void **)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180027534`
- `0x180027c34`
- `0x180028604`
- `0x180032ad0`

## callees

- `0x180007c78`
- `0x1800092f0`

## import_xrefs

- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18000930d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18000930d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180009351`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180009351`

## string_xrefs

- `0x180009324`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180009368`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

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
  UserContext = UMgrQueryUserContext(a1);
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
        (void *)0x1356,
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
      (void *)0x1355,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)(unsigned int)UserContext,
      v10);
    return v6;
  }
}

```

## disassembly

```asm
0x1800092f0  mov     [rsp+arg_0], rbx
0x1800092f5  mov     [rsp+arg_8], rsi
0x1800092fa  push    rdi; int
0x1800092fb  sub     rsp, 20h
0x1800092ff  xor     eax, eax
0x180009301  mov     rdi, r8
0x180009304  mov     [rdx], rax
0x180009307  mov     rbx, rdx
0x18000930a  mov     [r8], rax
0x18000930d  call    cs:__imp_UMgrQueryUserContext
0x180009314  nop     dword ptr [rax+rax+00h]
0x180009319  mov     esi, eax
0x18000931b  test    eax, eax
0x18000931d  jns     short loc_18000934B
0x18000931f  mov     rcx, [rsp+28h]; this
0x180009324  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18000932b  mov     r9d, eax; char *
0x18000932e  mov     edx, 1355h; void *
0x180009333  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009338  mov     eax, esi
0x18000933a  mov     rbx, [rsp+28h+arg_0]
0x18000933f  mov     rsi, [rsp+28h+arg_8]
0x180009344  add     rsp, 20h
0x180009348  pop     rdi
0x180009349  retn
0x18000934b  mov     rcx, [rbx]
0x18000934e  mov     rdx, rdi
0x180009351  call    cs:__imp_UMgrQueryUserToken
0x180009358  nop     dword ptr [rax+rax+00h]
0x18000935d  mov     ebx, eax
0x18000935f  test    eax, eax
0x180009361  jns     short loc_18000938F
0x180009363  mov     rcx, [rsp+28h]; this
0x180009368  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18000936f  mov     r9d, eax; char *
0x180009372  mov     edx, 1356h; void *
0x180009377  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000937c  mov     eax, ebx
0x18000937e  mov     rbx, [rsp+28h+arg_0]
0x180009383  mov     rsi, [rsp+28h+arg_8]
0x180009388  add     rsp, 20h
0x18000938c  pop     rdi
0x18000938d  retn
0x18000938f  mov     rbx, [rsp+28h+arg_0]
0x180009394  xor     eax, eax
0x180009396  mov     rsi, [rsp+28h+arg_8]
0x18000939b  add     rsp, 20h
0x18000939f  pop     rdi
0x1800093a0  retn
```
