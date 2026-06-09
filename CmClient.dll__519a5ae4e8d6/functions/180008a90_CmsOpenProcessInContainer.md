# CmsOpenProcessInContainer

- ea: `0x180008a90`
- end: `0x180008c86`
- name: `CmsOpenProcessInContainer`
- size: `502`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callees

- `0x180001550`
- `0x180001574`
- `0x180001944`
- `0x1800021dc`
- `0x180002524`
- `0x180003c74`
- `0x18000639c`
- `0x1800066e4`
- `0x180007044`
- `0x180008a90`

## string_xrefs

- `0x180008b54`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`
- `0x180008bdb`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`
- `0x180008bf3`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`
- `0x180008c4b`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsOpenProcessInContainer(__int64 a1, int a2, __int64 a3, _QWORD *a4)
{
  _QWORD *v8; // rax
  __int64 v9; // rcx
  _QWORD *v10; // rbx
  int v11; // eax
  unsigned int v12; // edi
  void *v13; // rsi
  int v14; // esi
  int v15; // eax
  void *v16; // rdi
  int v18; // [rsp+20h] [rbp-50h]
  int *v19; // [rsp+20h] [rbp-50h]
  int v20; // [rsp+30h] [rbp-40h] BYREF
  __int64 v21; // [rsp+38h] [rbp-38h] BYREF
  __int64 *v22; // [rsp+40h] [rbp-30h] BYREF
  int v23[2]; // [rsp+48h] [rbp-28h] BYREF
  struct _WNF_STATE_NAME *v24; // [rsp+50h] [rbp-20h] BYREF
  struct _WNF_STATE_NAME v25; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v20 = a2;
  v8 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v8;
  if ( v8 )
  {
    *v8 = 0;
    *((_DWORD *)v8 + 2) = 0;
    v8[2] = 0;
    *((_DWORD *)v8 + 6) = 0;
    *((_DWORD *)v8 + 7) = 259;
    v8[4] = 0;
    *(_QWORD *)v23 = &v21;
    v24 = &v25;
    v22 = *(__int64 **)(a1 + 8);
    v19 = v23;
    v21 = 0;
    v25 = 0;
    v11 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,unsigned long,_WNF_STATE_NAME *,void * *),void *,unsigned long &,_WNF_STATE_NAME *,void * *>(
            v9,
            &v22,
            &v20,
            &v24);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x364,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
        (const char *)(unsigned int)v11,
        (int)v23);
      v13 = (void *)v10[4];
      v10[4] = 0;
      if ( v13 )
      {
        Csl::OutOfProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::~OutOfProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>(v13);
        operator delete(v13, (const struct std::nothrow_t *)0x18);
      }
LABEL_11:
      operator delete(v10, (const struct std::nothrow_t *)0x28);
      return v12;
    }
    *v10 = v21;
    *((_DWORD *)v10 + 2) = a2;
    v10[2] = a3;
    v14 = Container::Manager::Client::Process::RegisterForNotifications(
            (Container::Manager::Client::Process *)v10,
            &v25);
    if ( v14 < 0 )
    {
      v22 = &v21;
      v15 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(CmsRpcClt_CloseProcess, &v22);
      if ( v15 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x36E,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
          (const char *)(unsigned int)v15,
          (int)v23);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x370,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
        (const char *)(unsigned int)v14,
        (int)v19);
      v16 = (void *)v10[4];
      v10[4] = 0;
      if ( v16 )
      {
        Csl::OutOfProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::~OutOfProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>(v16);
        operator delete(v16, (const struct std::nothrow_t *)0x18);
      }
      v12 = v14;
      goto LABEL_11;
    }
    *a4 = v10;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x357,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)0x8007000ELL,
      v18);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180008a90  mov     [rsp-28h+arg_10], rbx
0x180008a95  push    rbp
0x180008a96  push    rsi
0x180008a97  push    rdi
0x180008a98  push    r14
0x180008a9a  push    r15
0x180008a9c  mov     rbp, rsp
0x180008a9f  sub     rsp, 70h
0x180008aa3  mov     rax, cs:__security_cookie
0x180008aaa  xor     rax, rsp
0x180008aad  mov     [rbp+var_10], rax
0x180008ab1  mov     esi, edx
0x180008ab3  mov     [rbp+var_40], edx
0x180008ab6  mov     rdi, rcx
0x180008ab9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008ac0  mov     ecx, 28h ; '('; unsigned __int64
0x180008ac5  mov     r14, r9
0x180008ac8  mov     r15, r8
0x180008acb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180008ad0  mov     rbx, rax
0x180008ad3  test    rax, rax
0x180008ad6  jz      loc_180008C47
0x180008adc  mov     qword ptr [rax], 0
0x180008ae3  lea     r9, [rbp+var_20]
0x180008ae7  mov     dword ptr [rax+8], 0
0x180008aee  lea     r8, [rbp+var_40]
0x180008af2  mov     qword ptr [rax+10h], 0
0x180008afa  lea     rdx, [rbp+var_30]
0x180008afe  mov     dword ptr [rax+18h], 0
0x180008b05  mov     dword ptr [rax+1Ch], 103h
0x180008b0c  mov     qword ptr [rax+20h], 0
0x180008b14  lea     rax, [rbp+var_38]
0x180008b18  mov     qword ptr [rbp+var_28], rax
0x180008b1c  lea     rax, [rbp+var_18]
0x180008b20  mov     [rbp+var_20], rax
0x180008b24  mov     rax, [rdi+8]
0x180008b28  mov     [rbp+var_30], rax
0x180008b2c  lea     rax, [rbp+var_28]
0x180008b30  mov     qword ptr [rsp+70h+var_50], rax; int
0x180008b35  mov     [rbp+var_38], 0
0x180008b3d  mov     qword ptr [rbp+var_18.Data], 0
0x180008b45  call    ??$InvokeStubFunction@P6AJPEAXKPEAU_WNF_STATE_NAME@@PEAPEAX@ZPEAXAEAKPEAU1@PEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAXKPEAU_WNF_STATE_NAME@@PEAPEAX@Z$$QEAPEAXAEAK$$QEAPEAU3@$$QEAPEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,ulong,_WNF_STATE_NAME *,void * *),void *,ulong &,_WNF_STATE_NAME *,void * *>(long (*)(void *,ulong,_WNF_STATE_NAME *,void * *),void * &&,ulong &,_WNF_STATE_NAME * &&,void * * &&)
0x180008b4a  mov     edi, eax
0x180008b4c  test    eax, eax
0x180008b4e  jns     short loc_180008B97
0x180008b50  mov     rcx, [rbp+28h]; this
0x180008b54  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180008b5b  mov     r9d, eax; char *
0x180008b5e  mov     edx, 364h; void *
0x180008b63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008b68  mov     rsi, [rbx+20h]
0x180008b6c  mov     qword ptr [rbx+20h], 0
0x180008b74  test    rsi, rsi
0x180008b77  jz      loc_180008C2F
0x180008b7d  mov     rcx, rsi
0x180008b80  call    ??1?$OutOfProcNotificationSubscriber@U_CMS_PROCESS_NOTIFICATION@@$00@Csl@@QEAA@XZ; Csl::OutOfProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::~OutOfProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>(void)
0x180008b85  mov     edx, 18h; struct std::nothrow_t *
0x180008b8a  mov     rcx, rsi; void *
0x180008b8d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008b92  jmp     loc_180008C2F
0x180008b97  mov     rax, [rbp+var_38]
0x180008b9b  lea     rdx, [rbp+var_18]; struct _WNF_STATE_NAME *
0x180008b9f  mov     rcx, rbx; this
0x180008ba2  mov     [rbx], rax
0x180008ba5  mov     [rbx+8], esi
0x180008ba8  mov     [rbx+10h], r15
0x180008bac  call    ?RegisterForNotifications@Process@Client@Manager@Container@@QEAAJAEBU_WNF_STATE_NAME@@@Z; Container::Manager::Client::Process::RegisterForNotifications(_WNF_STATE_NAME const &)
0x180008bb1  mov     esi, eax
0x180008bb3  test    eax, eax
0x180008bb5  jns     loc_180008C40
0x180008bbb  lea     rax, [rbp+var_38]
0x180008bbf  lea     rdx, [rbp+var_30]
0x180008bc3  mov     [rbp+var_30], rax
0x180008bc7  lea     rcx, CmsRpcClt_CloseProcess
0x180008bce  call    ??$InvokeStubFunction@P6AJPEAX@ZAEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAX@ZAEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *),void * &>(long (*)(void *),void * &)
0x180008bd3  test    eax, eax
0x180008bd5  jns     short loc_180008BEF
0x180008bd7  mov     rcx, [rbp+28h]; this
0x180008bdb  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180008be2  mov     r9d, eax; char *
0x180008be5  mov     edx, 36Eh; void *
0x180008bea  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180008bef  mov     rcx, [rbp+28h]; this
0x180008bf3  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180008bfa  mov     r9d, esi; char *
0x180008bfd  mov     edx, 370h; void *
0x180008c02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008c07  mov     rdi, [rbx+20h]
0x180008c0b  mov     qword ptr [rbx+20h], 0
0x180008c13  test    rdi, rdi
0x180008c16  jz      short loc_180008C2D
0x180008c18  mov     rcx, rdi
0x180008c1b  call    ??1?$OutOfProcNotificationSubscriber@U_CMS_PROCESS_NOTIFICATION@@$00@Csl@@QEAA@XZ; Csl::OutOfProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::~OutOfProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>(void)
0x180008c20  mov     edx, 18h; struct std::nothrow_t *
0x180008c25  mov     rcx, rdi; void *
0x180008c28  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008c2d  mov     edi, esi
0x180008c2f  mov     edx, 28h ; '('; struct std::nothrow_t *
0x180008c34  mov     rcx, rbx; void *
0x180008c37  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180008c3c  mov     eax, edi
0x180008c3e  jmp     short loc_180008C66
0x180008c40  mov     [r14], rbx
0x180008c43  xor     eax, eax
0x180008c45  jmp     short loc_180008C66
0x180008c47  mov     rcx, [rbp+28h]; this
0x180008c4b  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x180008c52  mov     ebx, 8007000Eh
0x180008c57  mov     edx, 357h; void *
0x180008c5c  mov     r9d, ebx; char *
0x180008c5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008c64  mov     eax, ebx
0x180008c66  mov     rcx, [rbp+var_10]
0x180008c6a  xor     rcx, rsp; StackCookie
0x180008c6d  call    __security_check_cookie
0x180008c72  mov     rbx, [rsp+70h+arg_10]
0x180008c7a  add     rsp, 70h
0x180008c7e  pop     r15
0x180008c80  pop     r14
0x180008c82  pop     rdi
0x180008c83  pop     rsi
0x180008c84  pop     rbp
0x180008c85  retn
```
