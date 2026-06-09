# CDPComRetrieveResourceModel::GetSerializedResourceModel(char * *)

- ea: `0x180015430`
- end: `0x180015615`
- name: `?GetSerializedResourceModel@CDPComRetrieveResourceModel@@UEAAJPEAPEAD@Z`
- size: `485`
- prototype: `__int64 __fastcall(CDPComRetrieveResourceModel *__hidden this, char **)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x180015430`
- `0x18001fb30`
- `0x18001ffd4`
- `0x1800506a8`
- `0x18005074c`
- `0x1800507c4`
- `0x180050928`
- `0x180050a30`
- `0x180050ae0`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800155f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800155f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015466`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015466`

## string_xrefs

- `0x1800154c4`: `..\cdpcomretrieveresourcemodel.cpp`
- `0x1800154f6`: `..\cdpcomretrieveresourcemodel.cpp`
- `0x180015573`: `..\cdpcomretrieveresourcemodel.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDPComRetrieveResourceModel::GetSerializedResourceModel(
        CDPComRetrieveResourceModel *this,
        char **a2,
        __int64 a3,
        __int64 a4)
{
  unsigned int v6; // edi
  char *v7; // rbx
  int v8; // r14d
  char *v9; // r15
  int v10; // eax
  const struct std::exception *v11; // rax
  __int64 result; // rax
  const struct std::exception *v13; // rdx
  char *v14; // rax
  int v15; // edx
  int v16; // r8d
  const char *v17; // [rsp+30h] [rbp-88h] BYREF
  int v18; // [rsp+38h] [rbp-80h]
  _QWORD v19[3]; // [rsp+40h] [rbp-78h] BYREF
  _QWORD v20[12]; // [rsp+58h] [rbp-60h] BYREF
  unsigned int v21; // [rsp+C8h] [rbp+10h] BYREF
  int v22; // [rsp+D0h] [rbp+18h] BYREF
  char *v23; // [rsp+D8h] [rbp+20h] BYREF

  try
  {
    if ( a2 )
    {
      *a2 = 0;
      v6 = 2048;
      v7 = 0;
      v8 = 0;
      while ( 1 )
      {
        v9 = (char *)CoTaskMemAlloc(v6);
        if ( v7 )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)&v22);
          CoTaskMemFree(v7);
          wil::last_error_context::~last_error_context((wil::last_error_context *)&v22);
        }
        v7 = v9;
        v23 = v9;
        if ( !v9 )
        {
          v17 = "..\\cdpcomretrieveresourcemodel.cpp";
          v18 = 46;
          v19[2] = 0;
          v19[1] = "bad allocation";
          v19[0] = &std::bad_alloc::`vftable';
          cdp::CdpThrow<std::bad_alloc>((__int64)&v17, (const struct std::exception *)v19);
        }
        *v9 = 0;
        v21 = v6;
        v10 = (*(__int64 (__fastcall **)(_QWORD, char *, unsigned int *))(**((_QWORD **)this + 3) + 56LL))(
                *((_QWORD *)this + 3),
                v9,
                &v21);
        if ( v10 >= 0 )
          break;
        if ( v10 != -2147221235 )
        {
          v17 = "..\\cdpcomretrieveresourcemodel.cpp";
          v18 = 65;
          v11 = (const struct std::exception *)cdp::MakeException<cdp::hresult_exception>(v20, &v17, (unsigned int)v10);
          cdp::CdpThrow<cdp::hresult_exception>((__int64)&v17, v11);
        }
        if ( v21 > v6 )
          v6 = v21;
        if ( (unsigned int)++v8 >= 0xA )
        {
          v17 = "..\\cdpcomretrieveresourcemodel.cpp";
          v18 = 69;
          v13 = (const struct std::exception *)cdp::MakeException<cdp::HResultException<-2147418113>,>(
                                                 v20,
                                                 (__int64)&v17);
          cdp::CdpThrow<cdp::HResultException<-2147418113>>((__int64)&v17, v13);
        }
      }
      *a2 = v9;
      result = 0;
    }
    else
    {
      v21 = -2147467261;
      v22 = 30;
      Log<long &,char const (&)[35],int>((__int64)this, 0, &v21, a4, &v22);
      result = v21;
    }
  }
  catch ( ... )
  {
    v21 = -2147418113;
    LODWORD(v14) = GetCurrentThreadId();
    v23 = v14;
    v22 = 75;
    cdp::CatchAllToHR<char const (&)[35],int,unsigned __int64>(
      (unsigned int)&v21,
      v15,
      v16,
      (unsigned int)&v22,
      (__int64)&v23);
  }
  return result;
}

```

## disassembly

```asm
0x180015430  mov     [rsp+arg_0], rbx
0x180015435  push    rsi
0x180015436  push    rdi
0x180015437  push    r13
0x180015439  push    r14
0x18001543b  push    r15
0x18001543d  sub     rsp, 90h
0x180015444  mov     rsi, rdx
0x180015447  mov     r13, rcx
0x18001544a  test    rdx, rdx
0x18001544d  jz      loc_1800155A5
0x180015453  mov     qword ptr [rdx], 0
0x18001545a  mov     edi, 800h
0x18001545f  xor     ebx, ebx
0x180015461  xor     r14d, r14d
0x180015464  mov     ecx, edi; cb
0x180015466  call    cs:__imp_CoTaskMemAlloc
0x18001546c  mov     r15, rax
0x18001546f  test    rbx, rbx
0x180015472  jnz     loc_1800155E1
0x180015478  mov     rbx, r15
0x18001547b  mov     [rsp+0B8h+arg_18], rbx
0x180015483  test    r15, r15
0x180015486  jz      short loc_1800154F6
0x180015488  mov     byte ptr [r15], 0
0x18001548c  mov     [rsp+0B8h+arg_8], edi
0x180015493  mov     rcx, [r13+18h]
0x180015497  mov     rax, [rcx]
0x18001549a  lea     r8, [rsp+0B8h+arg_8]
0x1800154a2  mov     rdx, rbx
0x1800154a5  mov     rax, [rax+38h]
0x1800154a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154ae  mov     r8d, eax
0x1800154b1  test    eax, eax
0x1800154b3  jns     loc_18001553A
0x1800154b9  cmp     eax, 8004010Dh
0x1800154be  jz      loc_180015557
0x1800154c4  lea     rax, aCdpcomretrieve; "..\\cdpcomretrieveresourcemodel.cpp"
0x1800154cb  mov     [rsp+0B8h+var_88], rax
0x1800154d0  mov     [rsp+0B8h+var_80], 41h ; 'A'
0x1800154d8  lea     rdx, [rsp+0B8h+var_88]
0x1800154dd  lea     rcx, [rsp+0B8h+var_60]
0x1800154e2  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1800154e7  nop
0x1800154e8  mov     rdx, rax
0x1800154eb  lea     rcx, [rsp+0B8h+var_88]
0x1800154f0  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800154f6  lea     rax, aCdpcomretrieve; "..\\cdpcomretrieveresourcemodel.cpp"
0x1800154fd  mov     [rsp+0B8h+var_88], rax
0x180015502  mov     [rsp+0B8h+var_80], 2Eh ; '.'
0x18001550a  xorps   xmm0, xmm0
0x18001550d  movups  [rsp+0B8h+var_70], xmm0
0x180015512  lea     rax, aBadAllocation; "bad allocation"
0x180015519  mov     qword ptr [rsp+0B8h+var_70], rax
0x18001551e  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180015525  mov     [rsp+0B8h+var_78], rax
0x18001552a  lea     rdx, [rsp+0B8h+var_78]
0x18001552f  lea     rcx, [rsp+0B8h+var_88]
0x180015534  call    ??$CdpThrow@Vbad_alloc@std@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVbad_alloc@std@@@Z; cdp::CdpThrow<std::bad_alloc>(cdp::CDPSourceLocationInfo const &,std::bad_alloc &&)
0x18001553a  mov     [rsi], rbx
0x18001553d  xor     eax, eax
0x18001553f  mov     rbx, [rsp+0B8h+arg_0]
0x180015547  add     rsp, 90h
0x18001554e  pop     r15
0x180015550  pop     r14
0x180015552  pop     r13
0x180015554  pop     rdi
0x180015555  pop     rsi
0x180015556  retn
0x180015557  cmp     [rsp+0B8h+arg_8], edi
0x18001555e  cmova   edi, [rsp+0B8h+arg_8]
0x180015566  inc     r14d
0x180015569  cmp     r14d, 0Ah
0x18001556d  jb      loc_180015464
0x180015573  lea     rax, aCdpcomretrieve; "..\\cdpcomretrieveresourcemodel.cpp"
0x18001557a  mov     [rsp+0B8h+var_88], rax
0x18001557f  mov     [rsp+0B8h+var_80], 45h ; 'E'
0x180015587  lea     rdx, [rsp+0B8h+var_88]
0x18001558c  lea     rcx, [rsp+0B8h+var_60]
0x180015591  call    ??$MakeException@V?$HResultException@$0?HPPPAAAB@@cdp@@$$V@cdp@@YA?AV?$HResultException@$0?HPPPAAAB@@0@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<cdp::HResultException<-2147418113>,>(cdp::CDPSourceLocationInfo const &,char const *)
0x180015596  nop
0x180015597  mov     rdx, rax
0x18001559a  lea     rcx, [rsp+0B8h+var_88]
0x18001559f  call    ??$CdpThrow@V?$HResultException@$0?HPPPAAAB@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPPAAAB@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147418113>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147418113> &&)
0x1800155a5  mov     [rsp+0B8h+arg_8], 80004003h
0x1800155b0  mov     [rsp+0B8h+arg_10], 1Eh
0x1800155bb  lea     rax, [rsp+0B8h+arg_10]
0x1800155c3  mov     [rsp+0B8h+var_98], rax
0x1800155c8  lea     r8, [rsp+0B8h+arg_8]
0x1800155d0  call    ??$Log@AEAJAEAY0CD@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CD@$$CBD$$QEAH@Z; Log<long &,char const (&)[35],int>(CDPLogLevel,char const *,long &,char const (&)[35],int &&)
0x1800155d5  mov     eax, [rsp+0B8h+arg_8]
0x1800155dc  jmp     loc_18001553F
0x1800155e1  lea     rcx, [rsp+0B8h+arg_10]; this
0x1800155e9  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800155ee  mov     rcx, rbx; pv
0x1800155f1  call    cs:__imp_CoTaskMemFree
0x1800155f7  lea     rcx, [rsp+0B8h+arg_10]; this
0x1800155ff  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180015604  jmp     loc_180015478
0x180015609  mov     eax, [rsp+0B8h+arg_8]
0x180015610  jmp     loc_18001553F
```
