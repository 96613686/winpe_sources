# AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>::QueryInterface(_GUID const &,void * *)

- ea: `0x180003860`
- end: `0x180003971`
- name: `?QueryInterface@?$AppHostNavigatorTemplate@VAppHostConfigLocationsNavigator@@UIAppHostConfigLocationsNavigator@@VConfigLocationsTree@@@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180003980`

## callees

- `0x180003860`
- `0x180011e98`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>::QueryInterface(
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
  v11 = *a2 - *(_QWORD *)&GUID_9dfa9beb_c15f_450e_bf3a_1d56c67b5c0b.Data1;
  if ( *a2 == *(_QWORD *)&GUID_9dfa9beb_c15f_450e_bf3a_1d56c67b5c0b.Data1 )
    v11 = a2[1] - *(_QWORD *)GUID_9dfa9beb_c15f_450e_bf3a_1d56c67b5c0b.Data4;
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
0x180003860  push    rbx
0x180003862  sub     rsp, 20h
0x180003866  mov     r9, rcx
0x180003869  test    r8, r8
0x18000386c  jnz     short loc_180003878
0x18000386e  mov     eax, 80070057h
0x180003873  jmp     loc_18000396B
0x180003878  mov     rax, [rdx]
0x18000387b  sub     rax, qword ptr cs:IID_ISupportErrorInfo.Data1
0x180003882  jnz     short loc_18000388F
0x180003884  mov     rax, [rdx+8]
0x180003888  sub     rax, qword ptr cs:IID_ISupportErrorInfo.Data4
0x18000388f  test    rax, rax
0x180003892  jnz     short loc_1800038A1
0x180003894  mov     rcx, r8; struct ISupportErrorInfo **
0x180003897  add     rsp, 20h
0x18000389b  pop     rbx
0x18000389c  jmp     ?CreateInstance@SupportErrorInfoImpl@@SAJPEAPEAUISupportErrorInfo@@@Z; SupportErrorInfoImpl::CreateInstance(ISupportErrorInfo * *)
0x1800038a1  mov     rax, [rdx]
0x1800038a4  xor     ebx, ebx
0x1800038a6  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x1800038ad  jnz     short loc_1800038BA
0x1800038af  mov     rax, [rdx+8]
0x1800038b3  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x1800038ba  test    rax, rax
0x1800038bd  jz      short loc_1800038F7
0x1800038bf  mov     rax, [rdx]
0x1800038c2  sub     rax, qword ptr cs:IID_IDispatch.Data1
0x1800038c9  jnz     short loc_1800038D6
0x1800038cb  mov     rax, [rdx+8]
0x1800038cf  sub     rax, qword ptr cs:IID_IDispatch.Data4
0x1800038d6  test    rax, rax
0x1800038d9  jz      short loc_180003934
0x1800038db  mov     rax, [rdx]
0x1800038de  sub     rax, qword ptr cs:IID_IXPathNavigator.Data1
0x1800038e5  jnz     short loc_1800038F2
0x1800038e7  mov     rax, [rdx+8]
0x1800038eb  sub     rax, qword ptr cs:IID_IXPathNavigator.Data4
0x1800038f2  test    rax, rax
0x1800038f5  jnz     short loc_1800038FC
0x1800038f7  mov     rax, r9
0x1800038fa  jmp     short loc_180003944
0x1800038fc  mov     rax, [rdx]
0x1800038ff  sub     rax, qword ptr cs:IID_IAppHostNavigator.Data1
0x180003906  jnz     short loc_180003913
0x180003908  mov     rax, [rdx+8]
0x18000390c  sub     rax, qword ptr cs:IID_IAppHostNavigator.Data4
0x180003913  test    rax, rax
0x180003916  jz      short loc_180003934
0x180003918  mov     rax, [rdx]
0x18000391b  sub     rax, qword ptr cs:_GUID_9dfa9beb_c15f_450e_bf3a_1d56c67b5c0b.Data1
0x180003922  jnz     short loc_18000392F
0x180003924  mov     rax, [rdx+8]
0x180003928  sub     rax, qword ptr cs:_GUID_9dfa9beb_c15f_450e_bf3a_1d56c67b5c0b.Data4
0x18000392f  test    rax, rax
0x180003932  jnz     short loc_18000395D
0x180003934  add     rcx, 8
0x180003938  mov     rax, r9
0x18000393b  neg     rax
0x18000393e  sbb     rax, rax
0x180003941  and     rax, rcx
0x180003944  mov     [r8], rax
0x180003947  test    rax, rax
0x18000394a  jz      short loc_180003969
0x18000394c  mov     rax, [r9]
0x18000394f  mov     rcx, r9
0x180003952  mov     rax, [rax+8]
0x180003956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000395b  jmp     short loc_180003969
0x18000395d  mov     ebx, 80004002h
0x180003962  mov     qword ptr [r8], 0
0x180003969  mov     eax, ebx
0x18000396b  add     rsp, 20h
0x18000396f  pop     rbx
0x180003970  retn
```
