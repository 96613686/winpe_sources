# ActivitiesByGroupAndDeviceIdCallback::OnActivitiesByGroupAndDeviceIdDownloaded(ushort,ICDPActivity * *)

- ea: `0x180023720`
- end: `0x180023876`
- name: `?OnActivitiesByGroupAndDeviceIdDownloaded@ActivitiesByGroupAndDeviceIdCallback@@UEAAJGPEAPEAVICDPActivity@@@Z`
- size: `342`
- prototype: `__int64 __fastcall(ActivitiesByGroupAndDeviceIdCallback *__hidden this, unsigned __int16, struct ICDPActivity **)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800069c0`
- `0x1800097d0`
- `0x18000b634`
- `0x180016e18`
- `0x180023720`
- `0x180023b70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800237c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800237c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023765`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023765`

## pseudocode

```c
__int64 __fastcall ActivitiesByGroupAndDeviceIdCallback::OnActivitiesByGroupAndDeviceIdDownloaded(
        ActivitiesByGroupAndDeviceIdCallback *this,
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
          v27 = 1195;
          Log<long &,char const (&)[27],int>(v14, v13, &v26, v15, &v27);
          CoTaskMemFree(v9);
          goto LABEL_12;
        }
      }
      v20 = &std::_Func_impl_no_alloc<_lambda_c257cb9fd706a90f29c5f2ae02bdec57_,long,CDPComGetGroupActivitiesResult &>::`vftable';
      v21 = v6;
      v22 = i;
      v23 = HIWORD(v18);
      v24 = v9;
      v25 = &v20;
      v16 = ServiceCallbackNotifier<enum CDPComGetGroupActivitiesResultType,CDPComGetGroupActivitiesResult>::StoreResult(v18);
      if ( v19 )
        std::_Ref_count_base::_Decref(v19);
      return v16;
    }
    else
    {
      v26 = -2147024882;
      v27 = 1190;
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
0x180023720  mov     [rsp-8+arg_8], rbx
0x180023725  push    rbp
0x180023726  push    rsi
0x180023727  push    rdi
0x180023728  push    r12
0x18002372a  push    r15
0x18002372c  lea     rbp, [rsp-37h]
0x180023731  sub     rsp, 90h
0x180023738  mov     r15, r8
0x18002373b  movzx   esi, dx
0x18002373e  mov     r10, rcx
0x180023741  add     rcx, 20h ; ' '
0x180023745  lea     rdx, [rbp+57h+var_78]
0x180023749  call    ?lock@?$weak_ptr@V?$ServiceCallbackNotifier@W4CDPComGetActivityByIdResultType@@UCDPComGetActivityByIdResult@@@@@std@@QEBA?AV?$shared_ptr@V?$ServiceCallbackNotifier@W4CDPComGetActivityByIdResultType@@UCDPComGetActivityByIdResult@@@@@2@XZ; std::weak_ptr<ServiceCallbackNotifier<CDPComGetActivityByIdResultType,CDPComGetActivityByIdResult>>::lock(void)
0x18002374e  nop
0x18002374f  cmp     [rbp+57h+var_78], 0
0x180023754  jz      loc_18002384F
0x18002375a  mov     r12d, [r10+30h]
0x18002375e  imul    rcx, rsi, 0E8h; cb
0x180023765  call    cs:__imp_CoTaskMemAlloc
0x18002376b  mov     rdi, rax
0x18002376e  mov     [rbp+57h+var_80], rax
0x180023772  test    rax, rax
0x180023775  jz      loc_18002381B
0x18002377b  xor     ebx, ebx
0x18002377d  cmp     bx, si
0x180023780  jnb     short loc_1800237C9
0x180023782  movzx   ecx, bx
0x180023785  imul    rdx, rcx, 0E8h
0x18002378c  add     rdx, rdi
0x18002378f  mov     rcx, [r15+rcx*8]
0x180023793  call    CDPActivityToComActivityData
0x180023798  test    eax, eax
0x18002379a  js      short loc_1800237A1
0x18002379c  inc     bx
0x18002379f  jmp     short loc_18002377D
0x1800237a1  mov     [rbp+57h+arg_0], eax
0x1800237a4  mov     [rbp+57h+arg_18], 4ABh
0x1800237ab  lea     rax, [rbp+57h+arg_18]
0x1800237af  mov     [rsp+0B0h+var_90], rax
0x1800237b4  lea     r8, [rbp+57h+arg_0]
0x1800237b8  call    ??$Log@AEAJAEAY0BL@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BL@$$CBD$$QEAH@Z; Log<long &,char const (&)[27],int>(CDPLogLevel,char const *,long &,char const (&)[27],int &&)
0x1800237bd  nop
0x1800237be  mov     rcx, rdi; pv
0x1800237c1  call    cs:__imp_CoTaskMemFree
0x1800237c7  jmp     short loc_18002383C
0x1800237c9  mov     [rbp+57h+var_80], 0
0x1800237d1  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_c257cb9fd706a90f29c5f2ae02bdec57_@@JAEAUCDPComGetGroupActivitiesResult@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_c257cb9fd706a90f29c5f2ae02bdec57_,long,CDPComGetGroupActivitiesResult &>::`vftable'
0x1800237d8  mov     [rbp+57h+var_68], rax
0x1800237dc  mov     [rbp+57h+var_60], r12d
0x1800237e0  mov     [rbp+57h+var_5C], bx
0x1800237e4  movzx   eax, word ptr [rbp+57h+var_78+6]
0x1800237e8  mov     [rbp+57h+var_5A], ax
0x1800237ec  mov     [rbp+57h+var_58], rdi
0x1800237f0  lea     rax, [rbp+57h+var_68]
0x1800237f4  mov     [rbp+57h+var_30], rax
0x1800237f8  lea     r8, [rbp+57h+var_68]
0x1800237fc  xor     edx, edx
0x1800237fe  mov     rcx, [rbp+57h+var_78]; _Mtx_t
0x180023802  call    ?StoreResult@?$ServiceCallbackNotifier@W4CDPComGetGroupActivitiesResultType@@UCDPComGetGroupActivitiesResult@@@@QEAAJW4CDPComGetGroupActivitiesResultType@@V?$function@$$A6AJAEAUCDPComGetGroupActivitiesResult@@@Z@std@@@Z; ServiceCallbackNotifier<CDPComGetGroupActivitiesResultType,CDPComGetGroupActivitiesResult>::StoreResult(CDPComGetGroupActivitiesResultType,std::function<long (CDPComGetGroupActivitiesResult &)>)
0x180023807  mov     ebx, eax
0x180023809  mov     rcx, [rbp+57h+var_70]; this
0x18002380d  test    rcx, rcx
0x180023810  jz      short loc_180023817
0x180023812  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180023817  mov     eax, ebx
0x180023819  jmp     short loc_18002385F
0x18002381b  mov     [rbp+57h+arg_0], 8007000Eh
0x180023822  mov     [rbp+57h+arg_18], 4A6h
0x180023829  lea     rax, [rbp+57h+arg_18]
0x18002382d  mov     [rsp+0B0h+var_90], rax
0x180023832  lea     r8, [rbp+57h+arg_0]
0x180023836  call    ??$Log@AEAJAEAY0BL@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BL@$$CBD$$QEAH@Z; Log<long &,char const (&)[27],int>(CDPLogLevel,char const *,long &,char const (&)[27],int &&)
0x18002383b  nop
0x18002383c  mov     rcx, [rbp+57h+var_70]; this
0x180023840  test    rcx, rcx
0x180023843  jz      short loc_18002384A
0x180023845  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002384a  mov     eax, [rbp+57h+arg_0]
0x18002384d  jmp     short loc_18002385F
0x18002384f  mov     rcx, [rbp+57h+var_70]; this
0x180023853  test    rcx, rcx
0x180023856  jz      short loc_18002385D
0x180023858  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002385d  xor     eax, eax
0x18002385f  mov     rbx, [rsp+0B0h+arg_8]
0x180023867  add     rsp, 90h
0x18002386e  pop     r15
0x180023870  pop     r12
0x180023872  pop     rdi
0x180023873  pop     rsi
0x180023874  pop     rbp
0x180023875  retn
```
