# ActivitiesByAppActivityIdCallback::OnActivitiesByAppActivityIdDownloaded(ushort,ICDPActivity * *)

- ea: `0x180005cd0`
- end: `0x180005f98`
- name: `?OnActivitiesByAppActivityIdDownloaded@ActivitiesByAppActivityIdCallback@@UEAAJGPEAPEAVICDPActivity@@@Z`
- size: `712`
- prototype: `__int64 __fastcall(ActivitiesByAppActivityIdCallback *__hidden this, unsigned __int16, struct ICDPActivity **)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180005cd0`
- `0x180006494`
- `0x180006524`
- `0x180006698`
- `0x1800069c0`
- `0x1800097d0`
- `0x18000eb48`
- `0x18001ed1c`
- `0x18001ed30`
- `0x18001eda4`
- `0x180023b70`
- `0x180064010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180005f91`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180005f91`
- `msvcp_win!_Mtx_unlock` at `0x180005e83`
- `msvcp_win!_Mtx_unlock` at `0x180005e83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005d27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005d27`

## string_xrefs

- `0x180005f7b`: `{"text":"OnActivitiesByAppActivityDownloaded: failed to convert a cdp activity to com activity"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ActivitiesByAppActivityIdCallback::OnActivitiesByAppActivityIdDownloaded(
        ActivitiesByAppActivityIdCallback *this,
        unsigned __int16 a2,
        struct ICDPActivity **a3)
{
  __int64 v5; // r10
  volatile signed __int32 *v6; // rbx
  __int64 v7; // rsi
  int v8; // r12d
  __int64 v9; // rdx
  __int64 v10; // rcx
  LPVOID v11; // rdi
  __int64 v12; // r9
  unsigned __int16 i; // r15
  unsigned int v14; // r14d
  __int64 v15; // r15
  __int64 v16; // r12
  _OWORD *v17; // rax
  __int64 v18; // rcx
  void ***v19; // rdx
  signed __int32 v21; // eax
  signed __int32 v22; // ett
  __int16 v23; // [rsp+36h] [rbp-63h]
  __int128 v24; // [rsp+48h] [rbp-51h] BYREF
  __int64 v25; // [rsp+58h] [rbp-41h]
  void **v26; // [rsp+60h] [rbp-39h] BYREF
  int v27; // [rsp+68h] [rbp-31h]
  unsigned __int16 v28; // [rsp+6Ch] [rbp-2Dh]
  __int16 v29; // [rsp+6Eh] [rbp-2Bh]
  LPVOID v30; // [rsp+70h] [rbp-29h]
  void ***v31; // [rsp+98h] [rbp-1h]
  int v32; // [rsp+A0h] [rbp+7h] BYREF
  __int128 v33; // [rsp+A8h] [rbp+Fh]
  __int64 v34; // [rsp+B8h] [rbp+1Fh]
  void ***v35; // [rsp+100h] [rbp+67h] BYREF
  __int64 v36; // [rsp+118h] [rbp+7Fh] BYREF

  v23 = 0;
  v5 = *((_QWORD *)this + 5);
  if ( v5 )
  {
    v21 = *(_DWORD *)(v5 + 8);
    while ( v21 )
    {
      v22 = v21;
      v21 = _InterlockedCompareExchange((volatile signed __int32 *)(v5 + 8), v21 + 1, v21);
      if ( v22 == v21 )
      {
        v7 = *((_QWORD *)this + 4);
        v23 = HIWORD(v7);
        v6 = (volatile signed __int32 *)*((_QWORD *)this + 5);
        goto LABEL_3;
      }
    }
  }
  v6 = 0;
  v7 = 0;
LABEL_3:
  if ( v7 )
  {
    v8 = *((_DWORD *)this + 12);
    v11 = CoTaskMemAlloc(232LL * a2);
    if ( v11 )
    {
      for ( i = 0; i < a2; ++i )
      {
        if ( (int)CDPActivityToComActivityData((__int64 *)a3[i], (__int64)v11 + 232 * i) < 0 )
          Log<>(
            1u,
            "{\"text\":\"OnActivitiesByAppActivityDownloaded: failed to convert a cdp activity to com activity\"}");
      }
      v26 = &std::_Func_impl_no_alloc<_lambda_55da5f7b955609108794e94b4e9ba4ab_,long,CDPComGetActivitiesByAppActivityIdResult &>::`vftable';
      v27 = v8;
      v28 = i;
      v29 = v23;
      v30 = v11;
      v31 = &v26;
      v35 = &v26;
      v36 = v7;
      std::_Mutex_base::lock((std::_Mutex_base *)v7);
      v24 = 0;
      v25 = 0;
      if ( !v31 )
      {
        std::_Xbad_function_call();
        JUMPOUT(0x180005F97LL);
      }
      v14 = ((__int64 (__fastcall *)(void ***, __int128 *))(*v31)[2])(v31, &v24);
      v32 = 0;
      v33 = v24;
      v34 = v25;
      if ( *(_QWORD *)(v7 + 96) <= (unsigned __int64)(*(_QWORD *)(v7 + 112) + 1LL) )
        std::deque<std::pair<enum CDPComGetGroupActivitiesResultType,CDPComGetGroupActivitiesResult>>::_Growmap(v7 + 80);
      *(_QWORD *)(v7 + 104) &= *(_QWORD *)(v7 + 96) - 1LL;
      v15 = *(_QWORD *)(v7 + 112) + *(_QWORD *)(v7 + 104);
      v16 = 8
          * std::deque<std::pair<enum CDPComActivityStoreReaderEventType,CDPComActivityStoreReaderEventData>>::_Getblock(
              v7 + 80,
              v15);
      if ( !*(_QWORD *)(v16 + *(_QWORD *)(v7 + 88)) )
        *(_QWORD *)(v16 + *(_QWORD *)(v7 + 88)) = std::_Allocate<16,std::_Default_allocate_traits>(0x20u);
      v17 = (_OWORD *)std::_Deque_val<std::_Deque_simple_types<std::pair<enum CDPComActivityStoreInfoWatcherEventType,CDPComActivityStoreInfoWatcherEventInfo>>>::_Address_subscript(
                        v7 + 80,
                        v15);
      std::_Default_allocator_traits<std::allocator<std::pair<enum CDPComGetActivitiesByAppActivityIdResultType,CDPComGetActivitiesByAppActivityIdResult>>>::construct<std::pair<enum CDPComGetActivitiesByAppActivityIdResultType,CDPComGetActivitiesByAppActivityIdResult>,std::pair<enum CDPComGetActivitiesByAppActivityIdResultType,CDPComGetActivitiesByAppActivityIdResult>>(
        v18,
        v17,
        &v32);
      ++*(_QWORD *)(v7 + 112);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v7 + 120) + 32LL))(*(_QWORD *)(v7 + 120));
      _Mtx_unlock((_Mtx_t)v7);
      if ( v31 )
      {
        v19 = &v26;
        LOBYTE(v19) = v31 != &v26;
        ((void (__fastcall *)(void ***, void ***))(*v31)[4])(v31, v19);
        v31 = 0;
      }
      if ( v6 && _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
        if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
      }
      return v14;
    }
    else
    {
      LODWORD(v35) = -2147024882;
      LODWORD(v36) = 1394;
      Log<long &,char const (&)[27],int>(v10, v9, &v35, v12, &v36);
      if ( v6 )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v6);
      return (unsigned int)v35;
    }
  }
  else
  {
    if ( v6 )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v6);
    return 0;
  }
}

```

## disassembly

```asm
0x180005cd0  mov     [rsp-8+arg_8], rbx
0x180005cd5  push    rbp
0x180005cd6  push    rsi
0x180005cd7  push    rdi
0x180005cd8  push    r12
0x180005cda  push    r13
0x180005cdc  push    r14
0x180005cde  push    r15
0x180005ce0  lea     rbp, [rsp-27h]
0x180005ce5  sub     rsp, 0C0h
0x180005cec  mov     r13, r8
0x180005cef  movzx   r14d, dx
0x180005cf3  mov     r9, rcx
0x180005cf6  xorps   xmm0, xmm0
0x180005cf9  movdqu  xmmword ptr [rbp+57h+var_C0], xmm0
0x180005cfe  mov     r10, [rcx+28h]
0x180005d02  test    r10, r10
0x180005d05  jnz     loc_180005F08
0x180005d0b  mov     rbx, [rbp+57h+var_C0+8]
0x180005d0f  mov     rsi, [rbp+57h+var_C0]
0x180005d13  test    rsi, rsi
0x180005d16  jz      loc_180005F34
0x180005d1c  mov     r12d, [r9+30h]
0x180005d20  imul    rcx, r14, 0E8h; cb
0x180005d27  call    cs:__imp_CoTaskMemAlloc
0x180005d2d  mov     rdi, rax
0x180005d30  mov     [rbp+57h+var_B0], rax
0x180005d34  test    rax, rax
0x180005d37  jz      loc_180005F45
0x180005d3d  xor     r15d, r15d
0x180005d40  xor     ecx, ecx
0x180005d42  cmp     cx, r14w
0x180005d46  jnb     short loc_180005D72
0x180005d48  movzx   ecx, r15w
0x180005d4c  imul    rdx, rcx, 0E8h
0x180005d53  add     rdx, rdi
0x180005d56  mov     rcx, [r13+rcx*8+0]
0x180005d5b  call    CDPActivityToComActivityData
0x180005d60  test    eax, eax
0x180005d62  js      loc_180005F7B
0x180005d68  inc     r15w
0x180005d6c  cmp     r15w, r14w
0x180005d70  jb      short loc_180005D48
0x180005d72  xor     r13d, r13d
0x180005d75  mov     [rbp+57h+var_B0], r13
0x180005d79  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_55da5f7b955609108794e94b4e9ba4ab_@@JAEAUCDPComGetActivitiesByAppActivityIdResult@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_55da5f7b955609108794e94b4e9ba4ab_,long,CDPComGetActivitiesByAppActivityIdResult &>::`vftable'
0x180005d80  mov     [rbp+57h+var_90], rax
0x180005d84  mov     [rbp+57h+var_88], r12d
0x180005d88  mov     [rbp+57h+var_84], r15w
0x180005d8d  movzx   eax, word ptr [rbp+57h+var_C0+6]
0x180005d91  mov     [rbp+57h+var_82], ax
0x180005d95  mov     [rbp+57h+var_80], rdi
0x180005d99  lea     rax, [rbp+57h+var_90]
0x180005d9d  mov     [rbp+57h+var_58], rax
0x180005da1  lea     rax, [rbp+57h+var_90]
0x180005da5  mov     [rbp+57h+arg_0], rax
0x180005da9  mov     [rbp+57h+arg_18], rsi
0x180005dad  mov     rcx, rsi; this
0x180005db0  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180005db5  nop
0x180005db6  xorps   xmm0, xmm0
0x180005db9  xor     eax, eax
0x180005dbb  movups  [rbp+57h+var_A8], xmm0
0x180005dbf  mov     [rbp+57h+var_98], rax
0x180005dc3  mov     rcx, [rbp+57h+var_58]
0x180005dc7  test    rcx, rcx
0x180005dca  jz      loc_180005F91
0x180005dd0  mov     rax, [rcx]
0x180005dd3  lea     rdx, [rbp+57h+var_A8]
0x180005dd7  mov     rax, [rax+10h]
0x180005ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005de0  mov     r14d, eax
0x180005de3  mov     [rbp+57h+var_50], r13d
0x180005de7  movups  xmm0, [rbp+57h+var_A8]
0x180005deb  movups  [rbp+57h+var_48], xmm0
0x180005def  movsd   xmm1, [rbp+57h+var_98]
0x180005df4  movsd   [rbp+57h+var_38], xmm1
0x180005df9  mov     rcx, [rsi+70h]
0x180005dfd  inc     rcx
0x180005e00  cmp     [rsi+60h], rcx
0x180005e04  ja      short loc_180005E0F
0x180005e06  lea     rcx, [rsi+50h]
0x180005e0a  call    ?_Growmap@?$deque@U?$pair@W4CDPComGetGroupActivitiesResultType@@UCDPComGetGroupActivitiesResult@@@std@@V?$allocator@U?$pair@W4CDPComGetGroupActivitiesResultType@@UCDPComGetGroupActivitiesResult@@@std@@@2@@std@@AEAAX_K@Z; std::deque<std::pair<CDPComGetGroupActivitiesResultType,CDPComGetGroupActivitiesResult>>::_Growmap(unsigned __int64)
0x180005e0f  mov     rax, [rsi+60h]
0x180005e13  dec     rax
0x180005e16  and     [rsi+68h], rax
0x180005e1a  mov     r15, [rsi+68h]
0x180005e1e  add     r15, [rsi+70h]
0x180005e22  mov     rdx, r15
0x180005e25  lea     rcx, [rsi+50h]
0x180005e29  call    ?_Getblock@?$deque@U?$pair@W4CDPComActivityStoreReaderEventType@@UCDPComActivityStoreReaderEventData@@@std@@V?$allocator@U?$pair@W4CDPComActivityStoreReaderEventType@@UCDPComActivityStoreReaderEventData@@@std@@@2@@std@@AEBA_J_K@Z; std::deque<std::pair<CDPComActivityStoreReaderEventType,CDPComActivityStoreReaderEventData>>::_Getblock(unsigned __int64)
0x180005e2e  lea     r12, ds:0[rax*8]
0x180005e36  mov     rax, [rsi+58h]
0x180005e3a  cmp     qword ptr [r12+rax], 0
0x180005e3f  jnz     short loc_180005E53
0x180005e41  mov     ecx, 20h ; ' '
0x180005e46  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180005e4b  mov     rcx, [rsi+58h]
0x180005e4f  mov     [r12+rcx], rax
0x180005e53  mov     rdx, r15
0x180005e56  lea     rcx, [rsi+50h]
0x180005e5a  call    ?_Address_subscript@?$_Deque_val@U?$_Deque_simple_types@U?$pair@W4CDPComActivityStoreInfoWatcherEventType@@UCDPComActivityStoreInfoWatcherEventInfo@@@std@@@std@@@std@@QEAAPEAU?$pair@W4CDPComActivityStoreInfoWatcherEventType@@UCDPComActivityStoreInfoWatcherEventInfo@@@2@_K@Z; std::_Deque_val<std::_Deque_simple_types<std::pair<CDPComActivityStoreInfoWatcherEventType,CDPComActivityStoreInfoWatcherEventInfo>>>::_Address_subscript(unsigned __int64)
0x180005e5f  lea     r8, [rbp+57h+var_50]
0x180005e63  mov     rdx, rax
0x180005e66  call    ??$construct@U?$pair@W4CDPComGetActivitiesByAppActivityIdResultType@@UCDPComGetActivitiesByAppActivityIdResult@@@std@@U12@@?$_Default_allocator_traits@V?$allocator@U?$pair@W4CDPComGetActivitiesByAppActivityIdResultType@@UCDPComGetActivitiesByAppActivityIdResult@@@std@@@std@@@std@@SAXAEAV?$allocator@U?$pair@W4CDPComGetActivitiesByAppActivityIdResultType@@UCDPComGetActivitiesByAppActivityIdResult@@@std@@@1@QEAU?$pair@W4CDPComGetActivitiesByAppActivityIdResultType@@UCDPComGetActivitiesByAppActivityIdResult@@@1@$$QEAU31@@Z; std::_Default_allocator_traits<std::allocator<std::pair<CDPComGetActivitiesByAppActivityIdResultType,CDPComGetActivitiesByAppActivityIdResult>>>::construct<std::pair<CDPComGetActivitiesByAppActivityIdResultType,CDPComGetActivitiesByAppActivityIdResult>,std::pair<CDPComGetActivitiesByAppActivityIdResultType,CDPComGetActivitiesByAppActivityIdResult>>(std::allocator<std::pair<CDPComGetActivitiesByAppActivityIdResultType,CDPComGetActivitiesByAppActivityIdResult>> &,std::pair<CDPComGetActivitiesByAppActivityIdResultType,CDPComGetActivitiesByAppActivityIdResult> * const,std::pair<CDPComGetActivitiesByAppActivityIdResultType,CDPComGetActivitiesByAppActivityIdResult> &&)
0x180005e6b  inc     qword ptr [rsi+70h]
0x180005e6f  mov     rcx, [rsi+78h]
0x180005e73  mov     rax, [rcx]
0x180005e76  mov     rax, [rax+20h]
0x180005e7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e7f  nop
0x180005e80  mov     rcx, rsi; _Mtx_t
0x180005e83  call    cs:__imp__Mtx_unlock
0x180005e89  nop
0x180005e8a  mov     rcx, [rbp+57h+var_58]
0x180005e8e  test    rcx, rcx
0x180005e91  jz      short loc_180005EAD
0x180005e93  mov     rax, [rcx]
0x180005e96  lea     rdx, [rbp+57h+var_90]
0x180005e9a  cmp     rcx, rdx
0x180005e9d  setnz   dl
0x180005ea0  mov     rax, [rax+20h]
0x180005ea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ea9  mov     [rbp+57h+var_58], r13
0x180005ead  test    rbx, rbx
0x180005eb0  jz      short loc_180005EEA
0x180005eb2  mov     edi, 0FFFFFFFFh
0x180005eb7  mov     eax, edi
0x180005eb9  lock xadd [rbx+8], eax
0x180005ebe  cmp     eax, 1
0x180005ec1  jnz     short loc_180005EEA
0x180005ec3  mov     rax, [rbx]
0x180005ec6  mov     rcx, rbx
0x180005ec9  mov     rax, [rax]
0x180005ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ed1  lock xadd [rbx+0Ch], edi
0x180005ed6  cmp     edi, 1
0x180005ed9  jnz     short loc_180005EEA
0x180005edb  mov     rax, [rbx]
0x180005ede  mov     rcx, rbx
0x180005ee1  mov     rax, [rax+8]
0x180005ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eea  mov     eax, r14d
0x180005eed  mov     rbx, [rsp+0F0h+arg_8]
0x180005ef5  add     rsp, 0C0h
0x180005efc  pop     r15
0x180005efe  pop     r14
0x180005f00  pop     r13
0x180005f02  pop     r12
0x180005f04  pop     rdi
0x180005f05  pop     rsi
0x180005f06  pop     rbp
0x180005f07  retn
0x180005f08  mov     eax, [r10+8]
0x180005f0c  test    eax, eax
0x180005f0e  jz      loc_180005D0B
0x180005f14  lea     ecx, [rax+1]
0x180005f17  lock cmpxchg [r10+8], ecx
0x180005f1d  jnz     short loc_180005F0C
0x180005f1f  mov     rsi, [r9+20h]
0x180005f23  mov     [rbp+57h+var_C0], rsi
0x180005f27  mov     rbx, [r9+28h]
0x180005f2b  mov     [rbp+57h+var_C0+8], rbx
0x180005f2f  jmp     loc_180005D13
0x180005f34  test    rbx, rbx
0x180005f37  jz      short loc_180005F41
0x180005f39  mov     rcx, rbx; this
0x180005f3c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180005f41  xor     eax, eax
0x180005f43  jmp     short loc_180005EED
0x180005f45  mov     dword ptr [rbp+57h+arg_0], 8007000Eh
0x180005f4c  mov     dword ptr [rbp+57h+arg_18], 572h
0x180005f53  lea     rax, [rbp+57h+arg_18]
0x180005f57  mov     [rsp+0F0h+var_D0], rax
0x180005f5c  lea     r8, [rbp+57h+arg_0]
0x180005f60  call    ??$Log@AEAJAEAY0BL@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BL@$$CBD$$QEAH@Z; Log<long &,char const (&)[27],int>(CDPLogLevel,char const *,long &,char const (&)[27],int &&)
0x180005f65  nop
0x180005f66  test    rbx, rbx
0x180005f69  jz      short loc_180005F73
0x180005f6b  mov     rcx, rbx; this
0x180005f6e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180005f73  mov     eax, dword ptr [rbp+57h+arg_0]
0x180005f76  jmp     loc_180005EED
0x180005f7b  lea     rdx, aTextOnactiviti_0; "{\"text\":\"OnActivitiesByAppActivityDo"...
0x180005f82  mov     ecx, 1
0x180005f87  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x180005f8c  jmp     loc_180005D68
0x180005f91  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
```
