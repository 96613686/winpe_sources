# CSmsBrokerHandler::OnCreateEvent(ushort const *,ushort const *,ushort const *,ushort const *,_WNF_STATE_NAME *,int)

- ea: `0x180039cb4`
- end: `0x180039ed6`
- name: `?OnCreateEvent@CSmsBrokerHandler@@QEAAJPEBG000PEAU_WNF_STATE_NAME@@H@Z`
- size: `546`
- prototype: `int(CSmsBrokerHandler *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct _WNF_STATE_NAME *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003c580`

## callees

- `0x180015360`
- `0x180016c90`
- `0x180039cb4`
- `0x180051420`
- `0x180051628`
- `0x18006f010`

## string_xrefs

- `0x180039ea2`: `Invalid parameters RegistrationName=%S, AppName=%S, UserSidStr=%S, RegistrationXml=%S.`
- `0x180039d75`: `ServiceManager is not available.`
- `0x180039d89`: `CSmsBrokerHandler::OnCreateEvent`
- `0x180039ddb`: `CSmsBrokerHandler::OnCreateEvent`
- `0x180039e6c`: `CSmsBrokerHandler::OnCreateEvent`
- `0x180039eb4`: `CSmsBrokerHandler::OnCreateEvent`
- `0x180039e2f`: `Registration succeeded: name=%S, AppName=%S, UserSid=%S.`
- `0x180039df5`: `Registration failed: name=%S, AppName=%S, UserSid=%S.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSmsBrokerHandler::OnCreateEvent(
        CSmsBrokerHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        struct _WNF_STATE_NAME *a6,
        int a7)
{
  struct _WNF_STATE_NAME *v11; // r12
  char *v12; // rbx
  CSmsServiceManager *v13; // rcx
  unsigned int v14; // edi
  int v16; // eax
  unsigned int v17; // r15d
  int MessageAvailableEvent; // eax

  if ( !a6 )
    return 2147942487LL;
  if ( !a3 || !*a3 || !a2 || !*a2 || !a4 || !*a4 || !a5 || !*a5 )
  {
    LogSmsRouterError(
      "CSmsBrokerHandler::OnCreateEvent",
      0x295u,
      -2147024809,
      "Invalid parameters RegistrationName=%S, AppName=%S, UserSidStr=%S, RegistrationXml=%S.",
      a2,
      a3,
      a4,
      a5);
    return 2147942487LL;
  }
  if ( a6->Data[0] || (v11 = 0, a6->Data[1]) )
    v11 = a6;
  v12 = (char *)this + 16;
  (**((void (__fastcall ***)(char *))this + 2))((char *)this + 16);
  v13 = (CSmsServiceManager *)*((_QWORD *)this + 1);
  if ( !v13 )
  {
    v14 = -2147024875;
    LogSmsRouterError("CSmsBrokerHandler::OnCreateEvent", 0x2A8u, -2147024875, "ServiceManager is not available.");
    (*(void (__fastcall **)(char *))(*(_QWORD *)v12 + 8LL))(v12);
    return v14;
  }
  v16 = CSmsServiceManager::RegisterForMessages(v13, a2, a3, a4, a5, v11, 1, a7);
  v17 = v16;
  if ( v16 >= 0 )
  {
    LogSmsRouterInfo(
      "CSmsBrokerHandler::OnCreateEvent",
      0x2B6u,
      "Registration succeeded: name=%S, AppName=%S, UserSid=%S.",
      a2,
      a3,
      a4);
    MessageAvailableEvent = CSmsServiceManager::GetMessageAvailableEvent(
                              *((CSmsServiceManager **)this + 1),
                              a2,
                              a3,
                              a4,
                              a6);
    v14 = MessageAvailableEvent;
    if ( MessageAvailableEvent < 0 )
      LogSmsRouterError(
        "CSmsBrokerHandler::OnCreateEvent",
        0x2BBu,
        MessageAvailableEvent,
        "GetMessageAvailableEvent failed.");
    (*(void (__fastcall **)(char *))(*(_QWORD *)v12 + 8LL))(v12);
    return v14;
  }
  LogSmsRouterError(
    "CSmsBrokerHandler::OnCreateEvent",
    0x2B1u,
    v16,
    "Registration failed: name=%S, AppName=%S, UserSid=%S.",
    a2,
    a3,
    a4);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v12 + 8LL))(v12);
  return v17;
}

```

## disassembly

```asm
0x180039cb4  push    rbx
0x180039cb6  push    rbp
0x180039cb7  push    rsi
0x180039cb8  push    rdi
0x180039cb9  push    r12
0x180039cbb  push    r13
0x180039cbd  push    r14
0x180039cbf  push    r15
0x180039cc1  sub     rsp, 58h
0x180039cc5  mov     rdi, r9
0x180039cc8  mov     rsi, r8
0x180039ccb  mov     rbp, rdx
0x180039cce  mov     r13, rcx
0x180039cd1  mov     r14, [rsp+98h+arg_28]
0x180039cd9  xor     eax, eax
0x180039cdb  test    r14, r14
0x180039cde  jz      loc_180039EC0
0x180039ce4  mov     r15, [rsp+98h+arg_20]
0x180039cec  test    r8, r8
0x180039cef  jz      loc_180039E8E
0x180039cf5  cmp     [r8], ax
0x180039cf9  jz      loc_180039E8E
0x180039cff  test    rdx, rdx
0x180039d02  jz      loc_180039E8E
0x180039d08  cmp     [rdx], ax
0x180039d0b  jz      loc_180039E8E
0x180039d11  test    r9, r9
0x180039d14  jz      loc_180039E8E
0x180039d1a  cmp     [r9], ax
0x180039d1e  jz      loc_180039E8E
0x180039d24  test    r15, r15
0x180039d27  jz      loc_180039E8E
0x180039d2d  cmp     [r15], ax
0x180039d31  jz      loc_180039E8E
0x180039d37  cmp     [r14], eax
0x180039d3a  jnz     short loc_180039D45
0x180039d3c  mov     r12d, eax
0x180039d3f  cmp     [r14+4], eax
0x180039d43  jz      short loc_180039D48
0x180039d45  mov     r12, r14
0x180039d48  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x180039d4f  mov     [rsp+98h+var_58], rax
0x180039d54  lea     rbx, [rcx+10h]
0x180039d58  mov     [rsp+98h+var_50], rbx
0x180039d5d  mov     rax, [rbx]
0x180039d60  mov     rcx, rbx
0x180039d63  mov     rax, [rax]
0x180039d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039d6b  nop
0x180039d6c  mov     rcx, [r13+8]; this
0x180039d70  test    rcx, rcx
0x180039d73  jnz     short loc_180039DAD
0x180039d75  lea     r9, aServicemanager; "ServiceManager is not available."
0x180039d7c  mov     edi, 80070015h
0x180039d81  mov     r8d, edi; int
0x180039d84  mov     edx, 2A8h; unsigned int
0x180039d89  lea     rcx, aCsmsbrokerhand; "CSmsBrokerHandler::OnCreateEvent"
0x180039d90  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180039d95  nop
0x180039d96  mov     rdx, [rbx]
0x180039d99  mov     rcx, rbx
0x180039d9c  mov     rax, [rdx+8]
0x180039da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039da5  nop
0x180039da6  mov     eax, edi
0x180039da8  jmp     loc_180039EC5
0x180039dad  mov     eax, [rsp+98h+arg_30]
0x180039db4  mov     [rsp+98h+var_60], eax; int
0x180039db8  mov     [rsp+98h+var_68], 1; int
0x180039dc0  mov     [rsp+98h+var_70], r12; struct _WNF_STATE_NAME *
0x180039dc5  mov     [rsp+98h+var_78], r15; unsigned __int16 *
0x180039dca  mov     r9, rdi; unsigned __int16 *
0x180039dcd  mov     r8, rsi; unsigned __int16 *
0x180039dd0  mov     rdx, rbp; unsigned __int16 *
0x180039dd3  call    ?RegisterForMessages@CSmsServiceManager@@QEAAJPEBG000PEAU_WNF_STATE_NAME@@HH@Z; CSmsServiceManager::RegisterForMessages(ushort const *,ushort const *,ushort const *,ushort const *,_WNF_STATE_NAME *,int,int)
0x180039dd8  mov     r15d, eax
0x180039ddb  lea     rcx, aCsmsbrokerhand; "CSmsBrokerHandler::OnCreateEvent"
0x180039de2  test    eax, eax
0x180039de4  jns     short loc_180039E22
0x180039de6  mov     qword ptr [rsp+98h+var_68], rdi
0x180039deb  mov     [rsp+98h+var_70], rsi
0x180039df0  mov     [rsp+98h+var_78], rbp
0x180039df5  lea     r9, aRegistrationFa_0; "Registration failed: name=%S, AppName=%"...
0x180039dfc  mov     r8d, eax; int
0x180039dff  mov     edx, 2B1h; unsigned int
0x180039e04  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180039e09  nop
0x180039e0a  mov     rax, [rbx]
0x180039e0d  mov     rcx, rbx
0x180039e10  mov     rax, [rax+8]
0x180039e14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e19  nop
0x180039e1a  mov     eax, r15d
0x180039e1d  jmp     loc_180039EC5
0x180039e22  mov     [rsp+98h+var_70], rdi
0x180039e27  mov     [rsp+98h+var_78], rsi
0x180039e2c  mov     r9, rbp
0x180039e2f  lea     r8, aRegistrationSu; "Registration succeeded: name=%S, AppNam"...
0x180039e36  mov     edx, 2B6h; unsigned int
0x180039e3b  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180039e40  mov     [rsp+98h+var_78], r14; struct _WNF_STATE_NAME *
0x180039e45  mov     r9, rdi; unsigned __int16 *
0x180039e48  mov     r8, rsi; unsigned __int16 *
0x180039e4b  mov     rdx, rbp; unsigned __int16 *
0x180039e4e  mov     rcx, [r13+8]; this
0x180039e52  call    ?GetMessageAvailableEvent@CSmsServiceManager@@QEAAJPEBG00PEAU_WNF_STATE_NAME@@@Z; CSmsServiceManager::GetMessageAvailableEvent(ushort const *,ushort const *,ushort const *,_WNF_STATE_NAME *)
0x180039e57  mov     edi, eax
0x180039e59  test    eax, eax
0x180039e5b  jns     short loc_180039E79
0x180039e5d  lea     r9, aGetmessageavai; "GetMessageAvailableEvent failed."
0x180039e64  mov     r8d, eax; int
0x180039e67  mov     edx, 2BBh; unsigned int
0x180039e6c  lea     rcx, aCsmsbrokerhand; "CSmsBrokerHandler::OnCreateEvent"
0x180039e73  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180039e78  nop
0x180039e79  mov     rcx, [rbx]
0x180039e7c  mov     rax, [rcx+8]
0x180039e80  mov     rcx, rbx
0x180039e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e88  nop
0x180039e89  jmp     loc_180039DA6
0x180039e8e  mov     qword ptr [rsp+98h+var_60], r15
0x180039e93  mov     qword ptr [rsp+98h+var_68], rdi
0x180039e98  mov     [rsp+98h+var_70], rsi
0x180039e9d  mov     [rsp+98h+var_78], rbp
0x180039ea2  lea     r9, aInvalidParamet_2; "Invalid parameters RegistrationName=%S,"...
0x180039ea9  mov     edx, 295h; unsigned int
0x180039eae  mov     r8d, 80070057h; int
0x180039eb4  lea     rcx, aCsmsbrokerhand; "CSmsBrokerHandler::OnCreateEvent"
0x180039ebb  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180039ec0  mov     eax, 80070057h
0x180039ec5  add     rsp, 58h
0x180039ec9  pop     r15
0x180039ecb  pop     r14
0x180039ecd  pop     r13
0x180039ecf  pop     r12
0x180039ed1  pop     rdi
0x180039ed2  pop     rsi
0x180039ed3  pop     rbp
0x180039ed4  pop     rbx
0x180039ed5  retn
```
