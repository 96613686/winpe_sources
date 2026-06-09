# AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800054c0`
- end: `0x1800055d1`
- name: `?QueryInterface@?$AppHostNavigatorTemplate@VAppHostConfigPathNavigator@@UIAppHostConfigPathNavigator@@VConfigPathNavigationTree@@@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x1800055e0`

## callees

- `0x1800054c0`
- `0x180011e98`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::QueryInterface(
        __int64 a1,
        _QWORD *a2,
        struct ISupportErrorInfo **a3)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax

  if ( !a3 )
    return 2147942487LL;
  v4 = *a2 - *(_QWORD *)&IID_ISupportErrorInfo.Data1;
  if ( *a2 == *(_QWORD *)&IID_ISupportErrorInfo.Data1 )
    v4 = a2[1] - *(_QWORD *)IID_ISupportErrorInfo.Data4;
  if ( !v4 )
    return SupportErrorInfoImpl::CreateInstance(a3);
  v5 = 0;
  v6 = *a2 - *(_QWORD *)&IID_IUnknown.Data1;
  if ( *a2 == *(_QWORD *)&IID_IUnknown.Data1 )
    v6 = a2[1] - *(_QWORD *)IID_IUnknown.Data4;
  if ( !v6 )
    goto LABEL_16;
  v7 = *a2 - *(_QWORD *)&IID_IDispatch.Data1;
  if ( *a2 == *(_QWORD *)&IID_IDispatch.Data1 )
    v7 = a2[1] - *(_QWORD *)IID_IDispatch.Data4;
  if ( !v7 )
    goto LABEL_23;
  v8 = *a2 - *(_QWORD *)&IID_IXPathNavigator.Data1;
  if ( *a2 == *(_QWORD *)&IID_IXPathNavigator.Data1 )
    v8 = a2[1] - *(_QWORD *)IID_IXPathNavigator.Data4;
  if ( !v8 )
  {
LABEL_16:
    v9 = a1;
    goto LABEL_24;
  }
  v10 = *a2 - *(_QWORD *)&IID_IAppHostNavigator.Data1;
  if ( *a2 == *(_QWORD *)&IID_IAppHostNavigator.Data1 )
    v10 = a2[1] - *(_QWORD *)IID_IAppHostNavigator.Data4;
  if ( !v10 )
    goto LABEL_23;
  v11 = *a2 - *(_QWORD *)&GUID_a0601362_def3_4571_809b_5b856e5e5521.Data1;
  if ( *a2 == *(_QWORD *)&GUID_a0601362_def3_4571_809b_5b856e5e5521.Data1 )
    v11 = a2[1] - *(_QWORD *)GUID_a0601362_def3_4571_809b_5b856e5e5521.Data4;
  if ( !v11 )
  {
LABEL_23:
    v9 = (a1 + 8) & -(__int64)(a1 != 0);
LABEL_24:
    *a3 = (struct ISupportErrorInfo *)v9;
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    return v5;
  }
  v5 = -2147467262;
  *a3 = 0;
  return v5;
}

```

## disassembly

```asm
0x1800054c0  push    rbx
0x1800054c2  sub     rsp, 20h
0x1800054c6  mov     r9, rcx
0x1800054c9  test    r8, r8
0x1800054cc  jnz     short loc_1800054D8
0x1800054ce  mov     eax, 80070057h
0x1800054d3  jmp     loc_1800055CB
0x1800054d8  mov     rax, [rdx]
0x1800054db  sub     rax, qword ptr cs:IID_ISupportErrorInfo.Data1
0x1800054e2  jnz     short loc_1800054EF
0x1800054e4  mov     rax, [rdx+8]
0x1800054e8  sub     rax, qword ptr cs:IID_ISupportErrorInfo.Data4
0x1800054ef  test    rax, rax
0x1800054f2  jnz     short loc_180005501
0x1800054f4  mov     rcx, r8; struct ISupportErrorInfo **
0x1800054f7  add     rsp, 20h
0x1800054fb  pop     rbx
0x1800054fc  jmp     ?CreateInstance@SupportErrorInfoImpl@@SAJPEAPEAUISupportErrorInfo@@@Z; SupportErrorInfoImpl::CreateInstance(ISupportErrorInfo * *)
0x180005501  mov     rax, [rdx]
0x180005504  xor     ebx, ebx
0x180005506  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x18000550d  jnz     short loc_18000551A
0x18000550f  mov     rax, [rdx+8]
0x180005513  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x18000551a  test    rax, rax
0x18000551d  jz      short loc_180005557
0x18000551f  mov     rax, [rdx]
0x180005522  sub     rax, qword ptr cs:IID_IDispatch.Data1
0x180005529  jnz     short loc_180005536
0x18000552b  mov     rax, [rdx+8]
0x18000552f  sub     rax, qword ptr cs:IID_IDispatch.Data4
0x180005536  test    rax, rax
0x180005539  jz      short loc_180005594
0x18000553b  mov     rax, [rdx]
0x18000553e  sub     rax, qword ptr cs:IID_IXPathNavigator.Data1
0x180005545  jnz     short loc_180005552
0x180005547  mov     rax, [rdx+8]
0x18000554b  sub     rax, qword ptr cs:IID_IXPathNavigator.Data4
0x180005552  test    rax, rax
0x180005555  jnz     short loc_18000555C
0x180005557  mov     rax, r9
0x18000555a  jmp     short loc_1800055A4
0x18000555c  mov     rax, [rdx]
0x18000555f  sub     rax, qword ptr cs:IID_IAppHostNavigator.Data1
0x180005566  jnz     short loc_180005573
0x180005568  mov     rax, [rdx+8]
0x18000556c  sub     rax, qword ptr cs:IID_IAppHostNavigator.Data4
0x180005573  test    rax, rax
0x180005576  jz      short loc_180005594
0x180005578  mov     rax, [rdx]
0x18000557b  sub     rax, qword ptr cs:_GUID_a0601362_def3_4571_809b_5b856e5e5521.Data1
0x180005582  jnz     short loc_18000558F
0x180005584  mov     rax, [rdx+8]
0x180005588  sub     rax, qword ptr cs:_GUID_a0601362_def3_4571_809b_5b856e5e5521.Data4
0x18000558f  test    rax, rax
0x180005592  jnz     short loc_1800055BD
0x180005594  add     rcx, 8
0x180005598  mov     rax, r9
0x18000559b  neg     rax
0x18000559e  sbb     rax, rax
0x1800055a1  and     rax, rcx
0x1800055a4  mov     [r8], rax
0x1800055a7  test    rax, rax
0x1800055aa  jz      short loc_1800055C9
0x1800055ac  mov     rax, [r9]
0x1800055af  mov     rcx, r9
0x1800055b2  mov     rax, [rax+8]
0x1800055b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055bb  jmp     short loc_1800055C9
0x1800055bd  mov     ebx, 80004002h
0x1800055c2  mov     qword ptr [r8], 0
0x1800055c9  mov     eax, ebx
0x1800055cb  add     rsp, 20h
0x1800055cf  pop     rbx
0x1800055d0  retn
```
