# ActivitiesByGroupCallback::OnActivitiesByGroupDownloaded(ushort,ICDPActivity * *)

- ea: `0x180006830`
- end: `0x1800069b5`
- name: `?OnActivitiesByGroupDownloaded@ActivitiesByGroupCallback@@UEAAJGPEAPEAVICDPActivity@@@Z`
- size: `389`
- prototype: `__int64 __fastcall(ActivitiesByGroupCallback *__hidden this, unsigned __int16, struct ICDPActivity **)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006830`
- `0x1800069c0`
- `0x1800097d0`
- `0x18000b67c`
- `0x18000eb48`
- `0x180016e18`
- `0x180023b70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000689c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000689c`

## string_xrefs

- `0x18000699e`: `{"text":"OnActivitiesByGroupDownloaded: failed to convert a cdp activity to com activity"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ActivitiesByGroupCallback::OnActivitiesByGroupDownloaded(
        std::_Ref_count_base **this,
        unsigned __int16 a2,
        struct ICDPActivity **a3)
{
  __int64 v4; // r15
  ActivitiesByGroupCallback *v5; // r9
  std::_Ref_count_base *v6; // rcx
  struct _Mtx_internal_imp_t *v7; // rsi
  std::_Ref_count_base *v8; // rbx
  int v9; // r12d
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r9
  LPVOID v13; // r14
  unsigned __int16 i; // di
  unsigned int v15; // edi
  __int16 v17; // [rsp+3Eh] [rbp-2Bh]
  void **v18; // [rsp+48h] [rbp-21h] BYREF
  int v19; // [rsp+50h] [rbp-19h]
  unsigned __int16 v20; // [rsp+54h] [rbp-15h]
  __int16 v21; // [rsp+56h] [rbp-13h]
  LPVOID v22; // [rsp+58h] [rbp-11h]
  void ***v23; // [rsp+80h] [rbp+17h]
  unsigned int v24; // [rsp+D0h] [rbp+67h] BYREF
  int v25; // [rsp+E8h] [rbp+7Fh] BYREF

  v4 = a2;
  v5 = (ActivitiesByGroupCallback *)this;
  v17 = 0;
  v6 = this[5];
  if ( v6 && std::_Ref_count_base::_Incref_nz(v6) )
  {
    v7 = (struct _Mtx_internal_imp_t *)*((_QWORD *)v5 + 4);
    v17 = HIWORD(v7);
    v8 = (std::_Ref_count_base *)*((_QWORD *)v5 + 5);
  }
  else
  {
    v8 = 0;
    v7 = 0;
  }
  if ( v7 )
  {
    v9 = *((_DWORD *)v5 + 12);
    v13 = CoTaskMemAlloc(232 * v4);
    if ( v13 )
    {
      for ( i = 0; i < (unsigned __int16)v4; ++i )
      {
        if ( (int)CDPActivityToComActivityData((__int64 *)a3[i], (__int64)v13 + 232 * i) < 0 )
          Log<>(3u, "{\"text\":\"OnActivitiesByGroupDownloaded: failed to convert a cdp activity to com activity\"}");
      }
      v18 = &std::_Func_impl_no_alloc<_lambda_049f0b0a81be2039309b92dc9d64b631_,long,CDPComGetGroupActivitiesResult &>::`vftable';
      v19 = v9;
      v20 = i;
      v21 = v17;
      v22 = v13;
      v23 = &v18;
      v15 = ServiceCallbackNotifier<enum CDPComGetGroupActivitiesResultType,CDPComGetGroupActivitiesResult>::StoreResult(v7);
      if ( v8 )
        std::_Ref_count_base::_Decref(v8);
      return v15;
    }
    else
    {
      v24 = -2147024882;
      v25 = 1073;
      Log<long &,char const (&)[27],int>(v11, v10, &v24, v12, &v25);
      if ( v8 )
        std::_Ref_count_base::_Decref(v8);
      return v24;
    }
  }
  else
  {
    if ( v8 )
      std::_Ref_count_base::_Decref(v8);
    return 0;
  }
}

```

## disassembly

```asm
0x180006830  mov     [rsp-8+arg_8], rbx
0x180006835  push    rbp
0x180006836  push    rsi
0x180006837  push    rdi
0x180006838  push    r12
0x18000683a  push    r13
0x18000683c  push    r14
0x18000683e  push    r15
0x180006840  lea     rbp, [rsp-27h]
0x180006845  sub     rsp, 90h
0x18000684c  mov     r13, r8
0x18000684f  movzx   r15d, dx
0x180006853  mov     r9, rcx
0x180006856  xorps   xmm0, xmm0
0x180006859  movdqu  [rbp+57h+var_88], xmm0
0x18000685e  mov     rcx, [rcx+28h]; this
0x180006862  test    rcx, rcx
0x180006865  jz      loc_18000694D
0x18000686b  call    ?_Incref_nz@_Ref_count_base@std@@QEAA_NXZ; std::_Ref_count_base::_Incref_nz(void)
0x180006870  test    al, al
0x180006872  jz      loc_18000694D
0x180006878  mov     rsi, [r9+20h]
0x18000687c  mov     qword ptr [rbp+57h+var_88], rsi
0x180006880  mov     rbx, [r9+28h]
0x180006884  mov     qword ptr [rbp+57h+var_88+8], rbx
0x180006888  test    rsi, rsi
0x18000688b  jz      loc_18000698D
0x180006891  mov     r12d, [r9+30h]
0x180006895  imul    rcx, r15, 0E8h; cb
0x18000689c  call    cs:__imp_CoTaskMemAlloc
0x1800068a2  mov     r14, rax
0x1800068a5  mov     [rbp+57h+var_90], rax
0x1800068a9  test    rax, rax
0x1800068ac  jz      loc_18000695A
0x1800068b2  xor     edi, edi
0x1800068b4  xor     ecx, ecx
0x1800068b6  cmp     cx, r15w
0x1800068ba  jnb     short loc_1800068E4
0x1800068bc  movzx   ecx, di
0x1800068bf  imul    rdx, rcx, 0E8h
0x1800068c6  add     rdx, r14
0x1800068c9  mov     rcx, [r13+rcx*8+0]
0x1800068ce  call    CDPActivityToComActivityData
0x1800068d3  test    eax, eax
0x1800068d5  js      loc_18000699E
0x1800068db  inc     di
0x1800068de  cmp     di, r15w
0x1800068e2  jb      short loc_1800068BC
0x1800068e4  mov     [rbp+57h+var_90], 0
0x1800068ec  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_049f0b0a81be2039309b92dc9d64b631_@@JAEAUCDPComGetGroupActivitiesResult@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_049f0b0a81be2039309b92dc9d64b631_,long,CDPComGetGroupActivitiesResult &>::`vftable'
0x1800068f3  mov     [rbp+57h+var_78], rax
0x1800068f7  mov     [rbp+57h+var_70], r12d
0x1800068fb  mov     [rbp+57h+var_6C], di
0x1800068ff  movzx   eax, word ptr [rbp+57h+var_88+6]
0x180006903  mov     [rbp+57h+var_6A], ax
0x180006907  mov     [rbp+57h+var_68], r14
0x18000690b  lea     rax, [rbp+57h+var_78]
0x18000690f  mov     [rbp+57h+var_40], rax
0x180006913  lea     r8, [rbp+57h+var_78]
0x180006917  xor     edx, edx
0x180006919  mov     rcx, rsi; _Mtx_t
0x18000691c  call    ?StoreResult@?$ServiceCallbackNotifier@W4CDPComGetGroupActivitiesResultType@@UCDPComGetGroupActivitiesResult@@@@QEAAJW4CDPComGetGroupActivitiesResultType@@V?$function@$$A6AJAEAUCDPComGetGroupActivitiesResult@@@Z@std@@@Z; ServiceCallbackNotifier<CDPComGetGroupActivitiesResultType,CDPComGetGroupActivitiesResult>::StoreResult(CDPComGetGroupActivitiesResultType,std::function<long (CDPComGetGroupActivitiesResult &)>)
0x180006921  mov     edi, eax
0x180006923  test    rbx, rbx
0x180006926  jz      short loc_180006930
0x180006928  mov     rcx, rbx; this
0x18000692b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180006930  mov     eax, edi
0x180006932  mov     rbx, [rsp+0C0h+arg_8]
0x18000693a  add     rsp, 90h
0x180006941  pop     r15
0x180006943  pop     r14
0x180006945  pop     r13
0x180006947  pop     r12
0x180006949  pop     rdi
0x18000694a  pop     rsi
0x18000694b  pop     rbp
0x18000694c  retn
0x18000694d  mov     rbx, qword ptr [rbp+57h+var_88+8]
0x180006951  mov     rsi, qword ptr [rbp+57h+var_88]
0x180006955  jmp     loc_180006888
0x18000695a  mov     [rbp+57h+arg_0], 8007000Eh
0x180006961  mov     [rbp+57h+arg_18], 431h
0x180006968  lea     rax, [rbp+57h+arg_18]
0x18000696c  mov     [rsp+0C0h+var_A0], rax
0x180006971  lea     r8, [rbp+57h+arg_0]
0x180006975  call    ??$Log@AEAJAEAY0BL@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BL@$$CBD$$QEAH@Z; Log<long &,char const (&)[27],int>(CDPLogLevel,char const *,long &,char const (&)[27],int &&)
0x18000697a  nop
0x18000697b  test    rbx, rbx
0x18000697e  jz      short loc_180006988
0x180006980  mov     rcx, rbx; this
0x180006983  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180006988  mov     eax, [rbp+57h+arg_0]
0x18000698b  jmp     short loc_180006932
0x18000698d  test    rbx, rbx
0x180006990  jz      short loc_18000699A
0x180006992  mov     rcx, rbx; this
0x180006995  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000699a  xor     eax, eax
0x18000699c  jmp     short loc_180006932
0x18000699e  lea     rdx, aTextOnactiviti; "{\"text\":\"OnActivitiesByGroupDownload"...
0x1800069a5  mov     ecx, 3
0x1800069aa  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x1800069af  jmp     loc_1800068DB
```
