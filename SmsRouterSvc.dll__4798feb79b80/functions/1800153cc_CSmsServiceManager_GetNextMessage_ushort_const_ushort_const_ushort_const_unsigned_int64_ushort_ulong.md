# CSmsServiceManager::GetNextMessage(ushort const *,ushort const *,ushort const *,unsigned __int64 *,ushort * *,ulong *)

- ea: `0x1800153cc`
- end: `0x18001575b`
- name: `?GetNextMessage@CSmsServiceManager@@QEAAJPEBG00PEA_KPEAPEAGPEAK@Z`
- size: `911`
- prototype: `__int64 __fastcall(CSmsServiceManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64 *, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180009d50`

## callees

- `0x18000f8b4`
- `0x180014d48`
- `0x1800153cc`
- `0x180034c5c`
- `0x1800352b8`
- `0x180051420`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015609`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015609`
- `OLEAUT32!__imp_SysFreeString` at `0x1800155ce`
- `OLEAUT32!__imp_SysFreeString` at `0x180015670`
- `OLEAUT32!__imp_SysFreeString` at `0x1800156eb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800155ce`
- `OLEAUT32!__imp_SysFreeString` at `0x180015670`
- `OLEAUT32!__imp_SysFreeString` at `0x1800156eb`

## string_xrefs

- `0x180015550`: `/Message/Imsi`
- `0x180015598`: `GetNextMessage.get_xml(dup) for RegId: %S, AppName: %S, UserSid: %S, MsgId: %llu failed`
- `0x1800155a7`: `CSmsServiceManager::GetNextMessage`
- `0x180015649`: `CSmsServiceManager::GetNextMessage`
- `0x18001571e`: `CSmsServiceManager::GetNextMessage`
- `0x180015635`: `GetNextMessage.LocalAlloc for RegId: %S, AppName: %S, UserSid: %S, MsgId: %llu failed`
- `0x18001570f`: `GetNextMessage for RegId: %S, AppName: %S, UserSid: %S, MsgId: %llu failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CSmsServiceManager::GetNextMessage(
        CSmsServiceManager *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int64 *a5,
        unsigned __int16 **a6,
        unsigned int *a7)
{
  const wchar_t *v9; // rsi
  struct IXMLDOMDocument *v10; // rbx
  const wchar_t *v11; // rdi
  int Registration; // r14d
  unsigned __int64 *v13; // r13
  volatile signed __int32 *v14; // rsi
  volatile signed __int32 *v15; // rsi
  __int64 v16; // rdi
  volatile signed __int32 *v17; // rbx
  int v18; // eax
  unsigned __int16 *v19; // rax
  __int64 v21; // rcx
  BSTR v22; // r8
  __int64 v23; // rdx
  OLECHAR v24; // r9
  unsigned __int16 *v25; // rcx
  BSTR bstrString[2]; // [rsp+40h] [rbp-20h] BYREF
  struct IXMLDOMDocument *v27; // [rsp+50h] [rbp-10h] BYREF
  struct IXMLDOMNode *v28; // [rsp+A0h] [rbp+40h] BYREF
  const unsigned __int16 *v29; // [rsp+A8h] [rbp+48h]

  v29 = a2;
  v9 = a2;
  v10 = 0;
  v27 = 0;
  v11 = (const wchar_t *)((char *)this + 96);
  *(_OWORD *)bstrString = 0;
  Registration = CSmsInterceptor::GetRegistration((char *)this + 96, a2, bstrString);
  v13 = a5;
  if ( Registration < 0 )
  {
    v14 = (volatile signed __int32 *)bstrString[1];
    if ( bstrString[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)bstrString[1] + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
        if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
      }
    }
LABEL_12:
    v9 = v29;
LABEL_41:
    LogSmsRouterError(
      "CSmsServiceManager::GetNextMessage",
      0x130u,
      Registration,
      "GetNextMessage for RegId: %S, AppName: %S, UserSid: %S, MsgId: %llu failed",
      v9,
      a3,
      a4,
      *v13);
LABEL_42:
    if ( v10 )
      ((void (__fastcall *)(struct IXMLDOMDocument *))v10->lpVtbl->Release)(v10);
    return (unsigned int)Registration;
  }
  if ( !(unsigned int)CRegistration::HasAccess((_QWORD *)bstrString[0], a3, a4, v11 + 36) )
  {
    v15 = (volatile signed __int32 *)bstrString[1];
    if ( bstrString[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)bstrString[1] + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
        if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      }
    }
    Registration = -2147024891;
    goto LABEL_12;
  }
  Registration = CRegistration::GetNextMessage((CRegistration *)bstrString[0], v13, &v27, a7);
  v16 = -1;
  v17 = (volatile signed __int32 *)bstrString[1];
  if ( bstrString[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)bstrString[1] + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
      if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
    }
  }
  if ( Registration < 0 )
  {
    v10 = v27;
    goto LABEL_41;
  }
  bstrString[0] = 0;
  v28 = 0;
  v10 = v27;
  ((void (__fastcall *)(struct IXMLDOMDocument *, __int64, struct IXMLDOMNode **))v27->lpVtbl->cloneNode)(
    v27,
    0xFFFFFFFFLL,
    &v28);
  Windows::Sms::Common::CSmsUtil::DeleteElement(v28, L"/Message/Imsi");
  v18 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))v28->lpVtbl->get_xml)(v28, bstrString);
  Registration = v18;
  if ( v18 < 0 )
  {
    LogSmsRouterError(
      "CSmsServiceManager::GetNextMessage",
      0x111u,
      v18,
      "GetNextMessage.get_xml(dup) for RegId: %S, AppName: %S, UserSid: %S, MsgId: %llu failed",
      v9,
      a3,
      a4,
      *v13);
    if ( v28 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v28->lpVtbl->Release)(v28);
    SysFreeString(bstrString[0]);
    if ( v10 )
      ((void (__fastcall *)(struct IXMLDOMDocument *))v10->lpVtbl->Release)(v10);
    return (unsigned int)Registration;
  }
  do
    ++v16;
  while ( bstrString[0][v16] );
  v19 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v16 + 2);
  *a6 = v19;
  if ( v19 )
  {
    v21 = 2147483646;
    v22 = bstrString[0];
    v23 = 0x7FFFFFFF;
    do
    {
      if ( !v21 )
        break;
      v24 = *v22;
      if ( !*v22 )
        break;
      ++v22;
      *v19++ = v24;
      --v21;
      --v23;
    }
    while ( v23 );
    v25 = v19 - 1;
    if ( v23 )
      v25 = v19;
    *v25 = 0;
    if ( v28 )
      ((void (__fastcall *)(struct IXMLDOMNode *, __int64, BSTR))v28->lpVtbl->Release)(v28, v23, v22);
    SysFreeString(bstrString[0]);
    goto LABEL_42;
  }
  LogSmsRouterError(
    "CSmsServiceManager::GetNextMessage",
    0x121u,
    -2147024882,
    "GetNextMessage.LocalAlloc for RegId: %S, AppName: %S, UserSid: %S, MsgId: %llu failed",
    v9,
    a3,
    a4,
    *v13);
  if ( v28 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v28->lpVtbl->Release)(v28);
  SysFreeString(bstrString[0]);
  if ( v10 )
    ((void (__fastcall *)(struct IXMLDOMDocument *))v10->lpVtbl->Release)(v10);
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800153cc  mov     [rsp-38h+arg_10], rbx
0x1800153d1  mov     [rsp-38h+arg_8], rdx
0x1800153d6  push    rbp
0x1800153d7  push    rsi
0x1800153d8  push    rdi
0x1800153d9  push    r12
0x1800153db  push    r13
0x1800153dd  push    r14
0x1800153df  push    r15
0x1800153e1  mov     rbp, rsp
0x1800153e4  sub     rsp, 60h
0x1800153e8  mov     r15, r9
0x1800153eb  mov     r12, r8
0x1800153ee  mov     rsi, rdx
0x1800153f1  xor     ebx, ebx
0x1800153f3  mov     [rbp+var_10], rbx
0x1800153f7  lea     rdi, [rcx+60h]
0x1800153fb  xorps   xmm0, xmm0
0x1800153fe  movdqu  xmmword ptr [rbp+bstrString], xmm0
0x180015403  lea     r8, [rbp+bstrString]
0x180015407  mov     rcx, rdi
0x18001540a  call    ?GetRegistration@CSmsInterceptor@@AEAAJPEBGAEAV?$shared_ptr@VCRegistration@@@std@@@Z; CSmsInterceptor::GetRegistration(ushort const *,std::shared_ptr<CRegistration> &)
0x18001540f  mov     r14d, eax
0x180015412  mov     r13, [rbp+arg_20]
0x180015416  test    eax, eax
0x180015418  jns     short loc_180015464
0x18001541a  mov     rsi, [rbp+bstrString+8]
0x18001541e  test    rsi, rsi
0x180015421  jz      loc_1800154C1
0x180015427  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001542b  mov     eax, edi
0x18001542d  lock xadd [rsi+8], eax
0x180015432  add     eax, edi
0x180015434  jnz     loc_1800154C1
0x18001543a  mov     rax, [rsi]
0x18001543d  mov     rcx, rsi
0x180015440  mov     rax, [rax]
0x180015443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015448  mov     eax, edi
0x18001544a  lock xadd [rsi+0Ch], eax
0x18001544f  add     eax, edi
0x180015451  jnz     short loc_1800154C1
0x180015453  mov     rax, [rsi]
0x180015456  mov     rcx, rsi
0x180015459  mov     rax, [rax+8]
0x18001545d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015462  jmp     short loc_1800154C1
0x180015464  lea     r9, [rdi+48h]
0x180015468  mov     r8, r15
0x18001546b  mov     rdx, r12
0x18001546e  mov     rcx, [rbp+bstrString]
0x180015472  call    ?HasAccess@CRegistration@@QEAAHPEBG0AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CRegistration::HasAccess(ushort const *,ushort const *,std::wstring const &)
0x180015477  test    eax, eax
0x180015479  jnz     short loc_1800154CA
0x18001547b  mov     rsi, [rbp+bstrString+8]
0x18001547f  test    rsi, rsi
0x180015482  jz      short loc_1800154BB
0x180015484  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180015488  mov     eax, edi
0x18001548a  lock xadd [rsi+8], eax
0x18001548f  add     eax, edi
0x180015491  jnz     short loc_1800154BB
0x180015493  mov     rax, [rsi]
0x180015496  mov     rcx, rsi
0x180015499  mov     rax, [rax]
0x18001549c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154a1  mov     eax, edi
0x1800154a3  lock xadd [rsi+0Ch], eax
0x1800154a8  add     eax, edi
0x1800154aa  jnz     short loc_1800154BB
0x1800154ac  mov     rax, [rsi]
0x1800154af  mov     rcx, rsi
0x1800154b2  mov     rax, [rax+8]
0x1800154b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154bb  mov     r14d, 80070005h
0x1800154c1  mov     rsi, [rbp+arg_8]
0x1800154c5  jmp     loc_1800156F7
0x1800154ca  mov     r9, [rbp+arg_30]; unsigned int *
0x1800154ce  lea     r8, [rbp+var_10]; struct IXMLDOMDocument **
0x1800154d2  mov     rdx, r13; unsigned __int64 *
0x1800154d5  mov     rcx, [rbp+bstrString]; this
0x1800154d9  call    ?GetNextMessage@CRegistration@@QEAAJPEA_KPEAPEAUIXMLDOMDocument@@PEAK@Z; CRegistration::GetNextMessage(unsigned __int64 *,IXMLDOMDocument * *,ulong *)
0x1800154de  mov     r14d, eax
0x1800154e1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800154e5  mov     rbx, [rbp+bstrString+8]
0x1800154e9  test    rbx, rbx
0x1800154ec  jz      short loc_180015521
0x1800154ee  mov     eax, edi
0x1800154f0  lock xadd [rbx+8], eax
0x1800154f5  add     eax, edi
0x1800154f7  jnz     short loc_180015521
0x1800154f9  mov     rax, [rbx]
0x1800154fc  mov     rcx, rbx
0x1800154ff  mov     rax, [rax]
0x180015502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015507  mov     eax, edi
0x180015509  lock xadd [rbx+0Ch], eax
0x18001550e  add     eax, edi
0x180015510  jnz     short loc_180015521
0x180015512  mov     rax, [rbx]
0x180015515  mov     rcx, rbx
0x180015518  mov     rax, [rax+8]
0x18001551c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015521  xor     ebx, ebx
0x180015523  test    r14d, r14d
0x180015526  js      loc_1800156F3
0x18001552c  mov     [rbp+bstrString], rbx
0x180015530  mov     [rbp+arg_0], rbx
0x180015534  mov     rbx, [rbp+var_10]
0x180015538  mov     rax, [rbx]
0x18001553b  mov     edx, edi
0x18001553d  lea     r8, [rbp+arg_0]
0x180015541  mov     rcx, rbx
0x180015544  mov     rax, [rax+0C0h]
0x18001554b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015550  lea     rdx, aMessageImsi; "/Message/Imsi"
0x180015557  mov     rcx, [rbp+arg_0]; struct IXMLDOMNode *
0x18001555b  call    ?DeleteElement@CSmsUtil@Common@Sms@Windows@@SAJPEAUIXMLDOMNode@@PEBG@Z; Windows::Sms::Common::CSmsUtil::DeleteElement(IXMLDOMNode *,ushort const *)
0x180015560  mov     rcx, [rbp+arg_0]
0x180015564  mov     rax, [rcx]
0x180015567  lea     rdx, [rbp+bstrString]
0x18001556b  mov     rax, [rax+110h]
0x180015572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015577  mov     r14d, eax
0x18001557a  xor     ecx, ecx
0x18001557c  test    eax, eax
0x18001557e  jns     short loc_1800155EF
0x180015580  mov     rcx, [r13+0]
0x180015584  mov     [rsp+60h+var_28], rcx
0x180015589  mov     [rsp+60h+var_30], r15
0x18001558e  mov     [rsp+60h+var_38], r12
0x180015593  mov     [rsp+60h+var_40], rsi
0x180015598  lea     r9, aGetnextmessage_2; "GetNextMessage.get_xml(dup) for RegId: "...
0x18001559f  mov     r8d, eax; int
0x1800155a2  mov     edx, 111h; unsigned int
0x1800155a7  lea     rcx, aCsmsserviceman_9; "CSmsServiceManager::GetNextMessage"
0x1800155ae  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x1800155b3  nop
0x1800155b4  mov     rcx, [rbp+arg_0]
0x1800155b8  test    rcx, rcx
0x1800155bb  jz      short loc_1800155CA
0x1800155bd  mov     rax, [rcx]
0x1800155c0  mov     rax, [rax+10h]
0x1800155c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155c9  nop
0x1800155ca  mov     rcx, [rbp+bstrString]; bstrString
0x1800155ce  call    cs:__imp_SysFreeString
0x1800155d4  nop
0x1800155d5  test    rbx, rbx
0x1800155d8  jz      short loc_1800155EA
0x1800155da  mov     rax, [rbx]
0x1800155dd  mov     rcx, rbx
0x1800155e0  mov     rax, [rax+10h]
0x1800155e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155e9  nop
0x1800155ea  jmp     loc_180015740
0x1800155ef  mov     rax, [rbp+bstrString]
0x1800155f3  inc     rdi
0x1800155f6  cmp     [rax+rdi*2], cx
0x1800155fa  jnz     short loc_1800155F3
0x1800155fc  lea     rdx, ds:2[rdi*2]; uBytes
0x180015604  mov     ecx, 40h ; '@'; uFlags
0x180015609  call    cs:__imp_LocalAlloc
0x18001560f  mov     rcx, [rbp+arg_28]
0x180015613  mov     [rcx], rax
0x180015616  xor     edi, edi
0x180015618  test    rax, rax
0x18001561b  jnz     short loc_180015693
0x18001561d  mov     rax, [r13+0]
0x180015621  mov     [rsp+60h+var_28], rax
0x180015626  mov     [rsp+60h+var_30], r15
0x18001562b  mov     [rsp+60h+var_38], r12
0x180015630  mov     [rsp+60h+var_40], rsi
0x180015635  lea     r9, aGetnextmessage_0; "GetNextMessage.LocalAlloc for RegId: %S"...
0x18001563c  mov     esi, 8007000Eh
0x180015641  mov     r8d, esi; int
0x180015644  mov     edx, 121h; unsigned int
0x180015649  lea     rcx, aCsmsserviceman_9; "CSmsServiceManager::GetNextMessage"
0x180015650  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180015655  nop
0x180015656  mov     rcx, [rbp+arg_0]
0x18001565a  test    rcx, rcx
0x18001565d  jz      short loc_18001566C
0x18001565f  mov     rax, [rcx]
0x180015662  mov     rax, [rax+10h]
0x180015666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001566b  nop
0x18001566c  mov     rcx, [rbp+bstrString]; bstrString
0x180015670  call    cs:__imp_SysFreeString
0x180015676  nop
0x180015677  test    rbx, rbx
0x18001567a  jz      short loc_18001568C
0x18001567c  mov     rcx, [rbx]
0x18001567f  mov     rax, [rcx+10h]
0x180015683  mov     rcx, rbx
0x180015686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001568b  nop
0x18001568c  mov     eax, esi
0x18001568e  jmp     loc_180015743
0x180015693  mov     ecx, 7FFFFFFEh
0x180015698  mov     r8, [rbp+bstrString]
0x18001569c  lea     edx, [rcx+1]
0x18001569f  test    rcx, rcx
0x1800156a2  jz      short loc_1800156C3
0x1800156a4  movzx   r9d, word ptr [r8]
0x1800156a8  test    r9w, r9w
0x1800156ac  jz      short loc_1800156C3
0x1800156ae  add     r8, 2
0x1800156b2  mov     [rax], r9w
0x1800156b6  add     rax, 2
0x1800156ba  dec     rcx
0x1800156bd  sub     rdx, 1
0x1800156c1  jnz     short loc_18001569F
0x1800156c3  lea     rcx, [rax-2]
0x1800156c7  test    rdx, rdx
0x1800156ca  cmovnz  rcx, rax
0x1800156ce  mov     [rcx], di
0x1800156d1  mov     rcx, [rbp+arg_0]
0x1800156d5  test    rcx, rcx
0x1800156d8  jz      short loc_1800156E7
0x1800156da  mov     rax, [rcx]
0x1800156dd  mov     rax, [rax+10h]
0x1800156e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156e6  nop
0x1800156e7  mov     rcx, [rbp+bstrString]; bstrString
0x1800156eb  call    cs:__imp_SysFreeString
0x1800156f1  jmp     short loc_18001572B
0x1800156f3  mov     rbx, [rbp+var_10]
0x1800156f7  mov     rax, [r13+0]
0x1800156fb  mov     [rsp+60h+var_28], rax
0x180015700  mov     [rsp+60h+var_30], r15
0x180015705  mov     [rsp+60h+var_38], r12
0x18001570a  mov     [rsp+60h+var_40], rsi
0x18001570f  lea     r9, aGetnextmessage; "GetNextMessage for RegId: %S, AppName: "...
0x180015716  mov     r8d, r14d; int
0x180015719  mov     edx, 130h; unsigned int
0x18001571e  lea     rcx, aCsmsserviceman_9; "CSmsServiceManager::GetNextMessage"
0x180015725  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18001572a  nop
0x18001572b  test    rbx, rbx
0x18001572e  jz      short loc_180015740
0x180015730  mov     rax, [rbx]
0x180015733  mov     rcx, rbx
0x180015736  mov     rax, [rax+10h]
0x18001573a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001573f  nop
0x180015740  mov     eax, r14d
0x180015743  mov     rbx, [rsp+60h+arg_10]
0x18001574b  add     rsp, 60h
0x18001574f  pop     r15
0x180015751  pop     r14
0x180015753  pop     r13
0x180015755  pop     r12
0x180015757  pop     rdi
0x180015758  pop     rsi
0x180015759  pop     rbp
0x18001575a  retn
```
