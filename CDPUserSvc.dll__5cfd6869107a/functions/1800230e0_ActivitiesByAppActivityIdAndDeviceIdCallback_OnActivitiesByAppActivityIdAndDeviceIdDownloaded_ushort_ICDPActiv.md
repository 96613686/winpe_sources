# ActivitiesByAppActivityIdAndDeviceIdCallback::OnActivitiesByAppActivityIdAndDeviceIdDownloaded(ushort,ICDPActivity * *)

- ea: `0x1800230e0`
- end: `0x180023236`
- name: `?OnActivitiesByAppActivityIdAndDeviceIdDownloaded@ActivitiesByAppActivityIdAndDeviceIdCallback@@UEAAJGPEAPEAVICDPActivity@@@Z`
- size: `342`
- prototype: `__int64 __fastcall(ActivitiesByAppActivityIdAndDeviceIdCallback *__hidden this, unsigned __int16, struct ICDPActivity **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800069c0`
- `0x1800077c0`
- `0x1800097d0`
- `0x18000b634`
- `0x1800230e0`
- `0x180023b70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023181`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023181`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023125`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023125`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ActivitiesByAppActivityIdAndDeviceIdCallback::OnActivitiesByAppActivityIdAndDeviceIdDownloaded(
        ActivitiesByAppActivityIdAndDeviceIdCallback *this,
        unsigned __int16 a2,
        struct ICDPActivity **a3)
{
  __int64 v4; // rsi
  __int64 v5; // r10
  int v6; // r12d
  __int64 v7; // rdx
  __int64 v8; // rcx
  void *v9; // rdi
  __int64 v10; // r9
  unsigned __int16 i; // bx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r9
  unsigned int v16; // ebx
  _Mtx_t v18; // [rsp+38h] [rbp-21h] BYREF
  std::_Ref_count_base *v19; // [rsp+40h] [rbp-19h]
  void **v20; // [rsp+48h] [rbp-11h] BYREF
  int v21; // [rsp+50h] [rbp-9h]
  unsigned __int16 v22; // [rsp+54h] [rbp-5h]
  __int16 v23; // [rsp+56h] [rbp-3h]
  void *v24; // [rsp+58h] [rbp-1h]
  void ***v25; // [rsp+80h] [rbp+27h]
  unsigned int v26; // [rsp+C0h] [rbp+67h] BYREF
  int v27; // [rsp+D8h] [rbp+7Fh] BYREF

  v4 = a2;
  std::weak_ptr<ServiceCallbackNotifier<enum CDPComGetActivityByIdResultType,CDPComGetActivityByIdResult>>::lock(
    (char *)this + 32,
    &v18);
  if ( v18 )
  {
    v6 = *(_DWORD *)(v5 + 48);
    v9 = CoTaskMemAlloc(232 * v4);
    if ( v9 )
    {
      for ( i = 0; i < (unsigned __int16)v4; ++i )
      {
        v12 = CDPActivityToComActivityData((__int64 *)a3[i], (__int64)v9 + 232 * i);
        if ( v12 < 0 )
        {
          v26 = v12;
          v27 = 1517;
          Log<long &,char const (&)[27],int>(v14, v13, &v26, v15, &v27);
          CoTaskMemFree(v9);
          goto LABEL_12;
        }
      }
      v20 = &std::_Func_impl_no_alloc<_lambda_1e8215fa49a4f02de2a2e516276d71ba_,long,CDPComGetActivitiesByAppActivityIdResult &>::`vftable';
      v21 = v6;
      v22 = i;
      v23 = HIWORD(v18);
      v24 = v9;
      v25 = &v20;
      v16 = ServiceCallbackNotifier<enum CDPComGetActivitiesByAppActivityIdResultType,CDPComGetActivitiesByAppActivityIdResult>::StoreResult(v18);
      if ( v19 )
        std::_Ref_count_base::_Decref(v19);
      return v16;
    }
    else
    {
      v26 = -2147024882;
      v27 = 1512;
      Log<long &,char const (&)[27],int>(v8, v7, &v26, v10, &v27);
LABEL_12:
      if ( v19 )
        std::_Ref_count_base::_Decref(v19);
      return v26;
    }
  }
  else
  {
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
    return 0;
  }
}

```

## disassembly

```asm
0x1800230e0  mov     [rsp-8+arg_8], rbx
0x1800230e5  push    rbp
0x1800230e6  push    rsi
0x1800230e7  push    rdi
0x1800230e8  push    r12
0x1800230ea  push    r15
0x1800230ec  lea     rbp, [rsp-37h]
0x1800230f1  sub     rsp, 90h
0x1800230f8  mov     r15, r8
0x1800230fb  movzx   esi, dx
0x1800230fe  mov     r10, rcx
0x180023101  add     rcx, 20h ; ' '
0x180023105  lea     rdx, [rbp+57h+var_78]
0x180023109  call    ?lock@?$weak_ptr@V?$ServiceCallbackNotifier@W4CDPComGetActivityByIdResultType@@UCDPComGetActivityByIdResult@@@@@std@@QEBA?AV?$shared_ptr@V?$ServiceCallbackNotifier@W4CDPComGetActivityByIdResultType@@UCDPComGetActivityByIdResult@@@@@2@XZ; std::weak_ptr<ServiceCallbackNotifier<CDPComGetActivityByIdResultType,CDPComGetActivityByIdResult>>::lock(void)
0x18002310e  nop
0x18002310f  cmp     [rbp+57h+var_78], 0
0x180023114  jz      loc_18002320F
0x18002311a  mov     r12d, [r10+30h]
0x18002311e  imul    rcx, rsi, 0E8h; cb
0x180023125  call    cs:__imp_CoTaskMemAlloc
0x18002312b  mov     rdi, rax
0x18002312e  mov     [rbp+57h+var_80], rax
0x180023132  test    rax, rax
0x180023135  jz      loc_1800231DB
0x18002313b  xor     ebx, ebx
0x18002313d  cmp     bx, si
0x180023140  jnb     short loc_180023189
0x180023142  movzx   ecx, bx
0x180023145  imul    rdx, rcx, 0E8h
0x18002314c  add     rdx, rdi
0x18002314f  mov     rcx, [r15+rcx*8]
0x180023153  call    CDPActivityToComActivityData
0x180023158  test    eax, eax
0x18002315a  js      short loc_180023161
0x18002315c  inc     bx
0x18002315f  jmp     short loc_18002313D
0x180023161  mov     [rbp+57h+arg_0], eax
0x180023164  mov     [rbp+57h+arg_18], 5EDh
0x18002316b  lea     rax, [rbp+57h+arg_18]
0x18002316f  mov     [rsp+0B0h+var_90], rax
0x180023174  lea     r8, [rbp+57h+arg_0]
0x180023178  call    ??$Log@AEAJAEAY0BL@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BL@$$CBD$$QEAH@Z; Log<long &,char const (&)[27],int>(CDPLogLevel,char const *,long &,char const (&)[27],int &&)
0x18002317d  nop
0x18002317e  mov     rcx, rdi; pv
0x180023181  call    cs:__imp_CoTaskMemFree
0x180023187  jmp     short loc_1800231FC
0x180023189  mov     [rbp+57h+var_80], 0
0x180023191  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1e8215fa49a4f02de2a2e516276d71ba_@@JAEAUCDPComGetActivitiesByAppActivityIdResult@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_1e8215fa49a4f02de2a2e516276d71ba_,long,CDPComGetActivitiesByAppActivityIdResult &>::`vftable'
0x180023198  mov     [rbp+57h+var_68], rax
0x18002319c  mov     [rbp+57h+var_60], r12d
0x1800231a0  mov     [rbp+57h+var_5C], bx
0x1800231a4  movzx   eax, word ptr [rbp+57h+var_78+6]
0x1800231a8  mov     [rbp+57h+var_5A], ax
0x1800231ac  mov     [rbp+57h+var_58], rdi
0x1800231b0  lea     rax, [rbp+57h+var_68]
0x1800231b4  mov     [rbp+57h+var_30], rax
0x1800231b8  lea     r8, [rbp+57h+var_68]
0x1800231bc  xor     edx, edx
0x1800231be  mov     rcx, [rbp+57h+var_78]; _Mtx_t
0x1800231c2  call    ?StoreResult@?$ServiceCallbackNotifier@W4CDPComGetActivitiesByAppActivityIdResultType@@UCDPComGetActivitiesByAppActivityIdResult@@@@QEAAJW4CDPComGetActivitiesByAppActivityIdResultType@@V?$function@$$A6AJAEAUCDPComGetActivitiesByAppActivityIdResult@@@Z@std@@@Z; ServiceCallbackNotifier<CDPComGetActivitiesByAppActivityIdResultType,CDPComGetActivitiesByAppActivityIdResult>::StoreResult(CDPComGetActivitiesByAppActivityIdResultType,std::function<long (CDPComGetActivitiesByAppActivityIdResult &)>)
0x1800231c7  mov     ebx, eax
0x1800231c9  mov     rcx, [rbp+57h+var_70]; this
0x1800231cd  test    rcx, rcx
0x1800231d0  jz      short loc_1800231D7
0x1800231d2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800231d7  mov     eax, ebx
0x1800231d9  jmp     short loc_18002321F
0x1800231db  mov     [rbp+57h+arg_0], 8007000Eh
0x1800231e2  mov     [rbp+57h+arg_18], 5E8h
0x1800231e9  lea     rax, [rbp+57h+arg_18]
0x1800231ed  mov     [rsp+0B0h+var_90], rax
0x1800231f2  lea     r8, [rbp+57h+arg_0]
0x1800231f6  call    ??$Log@AEAJAEAY0BL@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BL@$$CBD$$QEAH@Z; Log<long &,char const (&)[27],int>(CDPLogLevel,char const *,long &,char const (&)[27],int &&)
0x1800231fb  nop
0x1800231fc  mov     rcx, [rbp+57h+var_70]; this
0x180023200  test    rcx, rcx
0x180023203  jz      short loc_18002320A
0x180023205  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002320a  mov     eax, [rbp+57h+arg_0]
0x18002320d  jmp     short loc_18002321F
0x18002320f  mov     rcx, [rbp+57h+var_70]; this
0x180023213  test    rcx, rcx
0x180023216  jz      short loc_18002321D
0x180023218  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002321d  xor     eax, eax
0x18002321f  mov     rbx, [rsp+0B0h+arg_8]
0x180023227  add     rsp, 90h
0x18002322e  pop     r15
0x180023230  pop     r12
0x180023232  pop     rdi
0x180023233  pop     rsi
0x180023234  pop     rbp
0x180023235  retn
```
