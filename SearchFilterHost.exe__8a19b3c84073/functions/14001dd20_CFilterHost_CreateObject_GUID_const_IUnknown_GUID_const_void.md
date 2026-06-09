# CFilterHost::CreateObject(_GUID const &,IUnknown *,_GUID const &,void * *)

- ea: `0x14001dd20`
- end: `0x14001df17`
- name: `?CreateObject@CFilterHost@@UEAAJAEBU_GUID@@PEAUIUnknown@@0PEAPEAX@Z`
- size: `503`
- prototype: `__int64 __fastcall(CFilterHost *this, const struct _GUID *, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140009f14`
- `0x14001ae6c`
- `0x14001bcbc`
- `0x14001bcf4`
- `0x14001d694`
- `0x14001da50`
- `0x14001dd20`
- `0x1400253dc`
- `0x140025454`
- `0x140025580`
- `0x14004f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001ddc1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001de85`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001ddc1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001de85`

## pseudocode

```c
__int64 __fastcall CFilterHost::CreateObject(
        CFilterHost *this,
        const struct _GUID *a2,
        struct IUnknown *a3,
        const struct _GUID *a4,
        void **a5)
{
  __int64 *v9; // rcx
  IID v10; // xmm0
  __int64 v11; // rax
  HRESULT EmptyPropertyHandler; // ebx
  __int64 v13; // rdx
  __int64 v14; // rbx
  __int64 *v15; // rcx
  struct _GUID v16; // xmm0
  __int64 v17; // rax
  HRESULT Instance; // eax
  __int64 v19; // rdx
  __int64 v21; // rbx
  int ppv; // [rsp+20h] [rbp-51h]
  _DWORD v23[4]; // [rsp+30h] [rbp-41h] BYREF
  struct _GUID v24; // [rsp+40h] [rbp-31h] BYREF
  _BYTE v25[56]; // [rsp+50h] [rbp-21h] BYREF
  __int64 v26; // [rsp+88h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58386382>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58386382>::GetImpl'::`2'::impl) )
  {
    tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>>>((struct wil::details::IFailureCallback *)v25);
    v14 = v26;
    *(_QWORD *)&v24.Data1 = v26;
    if ( v26 )
      _InterlockedIncrement((volatile signed __int32 *)(v26 + 448));
    tip2::details::shared_data<1,0,0>::begin_update(v14 + 8);
    _tip_FilterHostTest::CLSID((_tip_FilterHostTest *)(v14 + 256), a2);
    tip2::test_data_control<tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>>::~test_data_control<tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>>(&v24);
    v15 = (__int64 *)*((_QWORD *)this + 27);
    v16 = *a2;
    v23[0] = 1;
    v17 = *v15;
    v24 = v16;
    Instance = (*(__int64 (__fastcall **)(__int64 *, struct _GUID *, _DWORD *))(v17 + 40))(v15, &v24, v23);
    EmptyPropertyHandler = Instance;
    if ( Instance < 0 )
    {
      v19 = 527;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchfilterhost\\fltrhost.cxx",
        (const char *)(unsigned int)Instance,
        ppv);
      tip2::test_watcher<tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>>::~test_watcher<tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>>(v25);
      return (unsigned int)EmptyPropertyHandler;
    }
    if ( v23[0] )
    {
      Instance = CoCreateInstance(a2, a3, 1u, a4, a5);
      EmptyPropertyHandler = Instance;
      if ( Instance < 0 )
      {
        v19 = 531;
        goto LABEL_19;
      }
    }
    else
    {
      Instance = CreateEmptyPropertyHandler(a5);
      EmptyPropertyHandler = Instance;
      if ( Instance < 0 )
      {
        v19 = 537;
        goto LABEL_19;
      }
    }
    v21 = v26;
    *(_QWORD *)&v24.Data1 = v26;
    if ( v26 )
      _InterlockedIncrement((volatile signed __int32 *)(v26 + 448));
    tip2::details::shared_data<1,0,0>::begin_update(v21 + 8);
    tip2::details::shared_data<1,0,0>::complete(v21 + 8);
    tip2::test_data_control<tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>>::~test_data_control<tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>>(&v24);
    tip2::test_watcher<tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>>::~test_watcher<tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>>(v25);
    return 0;
  }
  v9 = (__int64 *)*((_QWORD *)this + 27);
  v10 = *a2;
  v23[0] = 1;
  v11 = *v9;
  v24 = v10;
  EmptyPropertyHandler = (*(__int64 (__fastcall **)(__int64 *, struct _GUID *, _DWORD *))(v11 + 40))(v9, &v24, v23);
  if ( EmptyPropertyHandler < 0 )
  {
    v13 = 546;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchfilterhost\\fltrhost.cxx",
      (const char *)(unsigned int)EmptyPropertyHandler,
      ppv);
    return (unsigned int)EmptyPropertyHandler;
  }
  if ( v23[0] )
  {
    EmptyPropertyHandler = CoCreateInstance(a2, a3, 1u, a4, a5);
    if ( EmptyPropertyHandler < 0 )
    {
      v13 = 550;
      goto LABEL_4;
    }
  }
  else
  {
    EmptyPropertyHandler = CreateEmptyPropertyHandler(a5);
    if ( EmptyPropertyHandler < 0 )
    {
      v13 = 556;
      goto LABEL_4;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14001dd20  push    rbp
0x14001dd22  push    rbx
0x14001dd23  push    rsi
0x14001dd24  push    r13
0x14001dd26  push    r14
0x14001dd28  push    r15
0x14001dd2a  lea     rbp, [rsp-27h]
0x14001dd2f  sub     rsp, 98h
0x14001dd36  mov     r14, r9
0x14001dd39  mov     r15, r8
0x14001dd3c  mov     rsi, rdx
0x14001dd3f  mov     r13, rcx
0x14001dd42  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_58386382@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_58386382@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58386382> `wil::Feature<__WilFeatureTraits_Feature_58386382>::GetImpl(void)'::`2'::impl
0x14001dd49  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_58386382@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58386382>::__private_IsEnabled(void)
0x14001dd4e  test    al, al
0x14001dd50  jnz     loc_14001DDF2
0x14001dd56  mov     rcx, [r13+0D8h]
0x14001dd5d  lea     r8, [rbp+4Fh+var_90]
0x14001dd61  movups  xmm0, xmmword ptr [rsi]
0x14001dd64  mov     [rbp+4Fh+var_90], 1
0x14001dd6b  lea     rdx, [rbp+4Fh+var_80]
0x14001dd6f  mov     rax, [rcx]
0x14001dd72  movdqu  [rbp+4Fh+var_80], xmm0
0x14001dd77  mov     rax, [rax+28h]
0x14001dd7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001dd80  mov     ebx, eax
0x14001dd82  test    eax, eax
0x14001dd84  jns     short loc_14001DDA3
0x14001dd86  mov     edx, 222h; void *
0x14001dd8b  mov     rcx, [rbp+57h]; this
0x14001dd8f  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\search\\sea"...
0x14001dd96  mov     r9d, ebx; char *
0x14001dd99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001dd9e  jmp     loc_14001DEC8
0x14001dda3  cmp     [rbp+4Fh+var_90], 0
0x14001dda7  jz      short loc_14001DDD8
0x14001dda9  mov     rax, [rbp+4Fh+arg_20]
0x14001ddad  mov     r9, r14; riid
0x14001ddb0  mov     r8d, 1; dwClsContext
0x14001ddb6  mov     qword ptr [rsp+0C0h+ppv], rax; ppv
0x14001ddbb  mov     rdx, r15; pUnkOuter
0x14001ddbe  mov     rcx, rsi; rclsid
0x14001ddc1  call    cs:__imp_CoCreateInstance
0x14001ddc7  mov     ebx, eax
0x14001ddc9  test    eax, eax
0x14001ddcb  jns     loc_14001DF04
0x14001ddd1  mov     edx, 226h
0x14001ddd6  jmp     short loc_14001DD8B
0x14001ddd8  mov     rcx, [rbp+4Fh+arg_20]; void **
0x14001dddc  call    ?CreateEmptyPropertyHandler@@YAJPEAPEAX@Z; CreateEmptyPropertyHandler(void * *)
0x14001dde1  mov     ebx, eax
0x14001dde3  test    eax, eax
0x14001dde5  jns     loc_14001DF04
0x14001ddeb  mov     edx, 22Ch
0x14001ddf0  jmp     short loc_14001DD8B
0x14001ddf2  lea     rcx, [rbp+4Fh+var_70]; struct wil::details::IFailureCallback *
0x14001ddf6  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_FilterHostTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x14001ddfb  mov     rbx, [rbp+4Fh+var_38]
0x14001ddff  mov     qword ptr [rbp+4Fh+var_80], rbx
0x14001de03  test    rbx, rbx
0x14001de06  jz      short loc_14001DE0F
0x14001de08  lock inc dword ptr [rbx+1C0h]
0x14001de0f  lea     rcx, [rbx+8]
0x14001de13  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x14001de18  lea     rcx, [rbx+100h]; this
0x14001de1f  mov     rdx, rsi; struct _GUID *
0x14001de22  call    ?CLSID@_tip_FilterHostTest@@QEAAXAEBU_GUID@@@Z; _tip_FilterHostTest::CLSID(_GUID const &)
0x14001de27  lea     rcx, [rbp+4Fh+var_80]
0x14001de2b  call    ??1?$test_data_control@V?$merged_data@U_tip_FilterHostTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>>::~test_data_control<tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>>(void)
0x14001de30  mov     rcx, [r13+0D8h]
0x14001de37  lea     r8, [rbp+4Fh+var_90]
0x14001de3b  movups  xmm0, xmmword ptr [rsi]
0x14001de3e  mov     [rbp+4Fh+var_90], 1
0x14001de45  lea     rdx, [rbp+4Fh+var_80]
0x14001de49  mov     rax, [rcx]
0x14001de4c  movdqu  [rbp+4Fh+var_80], xmm0
0x14001de51  mov     rax, [rax+28h]
0x14001de55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001de5a  mov     ebx, eax
0x14001de5c  test    eax, eax
0x14001de5e  jns     short loc_14001DE67
0x14001de60  mov     edx, 20Fh
0x14001de65  jmp     short loc_14001DEAC
0x14001de67  cmp     [rbp+4Fh+var_90], 0
0x14001de6b  jz      short loc_14001DE98
0x14001de6d  mov     rax, [rbp+4Fh+arg_20]
0x14001de71  mov     r9, r14; riid
0x14001de74  mov     r8d, 1; dwClsContext
0x14001de7a  mov     qword ptr [rsp+0C0h+ppv], rax; ppv
0x14001de7f  mov     rdx, r15; pUnkOuter
0x14001de82  mov     rcx, rsi; rclsid
0x14001de85  call    cs:__imp_CoCreateInstance
0x14001de8b  mov     ebx, eax
0x14001de8d  test    eax, eax
0x14001de8f  jns     short loc_14001DECC
0x14001de91  mov     edx, 213h
0x14001de96  jmp     short loc_14001DEAC
0x14001de98  mov     rcx, [rbp+4Fh+arg_20]; void **
0x14001de9c  call    ?CreateEmptyPropertyHandler@@YAJPEAPEAX@Z; CreateEmptyPropertyHandler(void * *)
0x14001dea1  mov     ebx, eax
0x14001dea3  test    eax, eax
0x14001dea5  jns     short loc_14001DECC
0x14001dea7  mov     edx, 219h; void *
0x14001deac  mov     rcx, [rbp+57h]; this
0x14001deb0  lea     r8, aOnecoreuapBase_36; "onecoreuap\\base\\appmodel\\search\\sea"...
0x14001deb7  mov     r9d, eax; char *
0x14001deba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001debf  lea     rcx, [rbp+4Fh+var_70]
0x14001dec3  call    ??1?$test_watcher@V?$merged_data@U_tip_FilterHostTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>>::~test_watcher<tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>>(void)
0x14001dec8  mov     eax, ebx
0x14001deca  jmp     short loc_14001DF06
0x14001decc  mov     rbx, [rbp+4Fh+var_38]
0x14001ded0  mov     qword ptr [rbp+4Fh+var_80], rbx
0x14001ded4  test    rbx, rbx
0x14001ded7  jz      short loc_14001DEE0
0x14001ded9  lock inc dword ptr [rbx+1C0h]
0x14001dee0  lea     rcx, [rbx+8]
0x14001dee4  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x14001dee9  lea     rcx, [rbx+8]
0x14001deed  call    ?complete@?$shared_data@$00$0A@$0A@@details@tip2@@QEAAXXZ; tip2::details::shared_data<1,0,0>::complete(void)
0x14001def2  lea     rcx, [rbp+4Fh+var_80]
0x14001def6  call    ??1?$test_data_control@V?$merged_data@U_tip_FilterHostTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>>::~test_data_control<tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>>(void)
0x14001defb  lea     rcx, [rbp+4Fh+var_70]
0x14001deff  call    ??1?$test_watcher@V?$merged_data@U_tip_FilterHostTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>>::~test_watcher<tip2::details::merged_data<_tip_FilterHostTest,_tip_FilterHostTest>>(void)
0x14001df04  xor     eax, eax
0x14001df06  add     rsp, 98h
0x14001df0d  pop     r15
0x14001df0f  pop     r14
0x14001df11  pop     r13
0x14001df13  pop     rsi
0x14001df14  pop     rbx
0x14001df15  pop     rbp
0x14001df16  retn
```
