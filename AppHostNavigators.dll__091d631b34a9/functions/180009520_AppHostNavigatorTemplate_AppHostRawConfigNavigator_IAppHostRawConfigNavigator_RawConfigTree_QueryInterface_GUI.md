# AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>::QueryInterface(_GUID const &,void * *)

- ea: `0x180009520`
- end: `0x180009631`
- name: `?QueryInterface@?$AppHostNavigatorTemplate@VAppHostRawConfigNavigator@@UIAppHostRawConfigNavigator@@VRawConfigTree@@@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180009640`

## callees

- `0x180009520`
- `0x180011e98`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>::QueryInterface(
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
  v11 = *a2 - *(_QWORD *)&GUID_4f29aa5f_4a59_4e88_bc5a_a902f6ff1d86.Data1;
  if ( *a2 == *(_QWORD *)&GUID_4f29aa5f_4a59_4e88_bc5a_a902f6ff1d86.Data1 )
    v11 = a2[1] - *(_QWORD *)GUID_4f29aa5f_4a59_4e88_bc5a_a902f6ff1d86.Data4;
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
0x180009520  push    rbx
0x180009522  sub     rsp, 20h
0x180009526  mov     r9, rcx
0x180009529  test    r8, r8
0x18000952c  jnz     short loc_180009538
0x18000952e  mov     eax, 80070057h
0x180009533  jmp     loc_18000962B
0x180009538  mov     rax, [rdx]
0x18000953b  sub     rax, qword ptr cs:IID_ISupportErrorInfo.Data1
0x180009542  jnz     short loc_18000954F
0x180009544  mov     rax, [rdx+8]
0x180009548  sub     rax, qword ptr cs:IID_ISupportErrorInfo.Data4
0x18000954f  test    rax, rax
0x180009552  jnz     short loc_180009561
0x180009554  mov     rcx, r8; struct ISupportErrorInfo **
0x180009557  add     rsp, 20h
0x18000955b  pop     rbx
0x18000955c  jmp     ?CreateInstance@SupportErrorInfoImpl@@SAJPEAPEAUISupportErrorInfo@@@Z; SupportErrorInfoImpl::CreateInstance(ISupportErrorInfo * *)
0x180009561  mov     rax, [rdx]
0x180009564  xor     ebx, ebx
0x180009566  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x18000956d  jnz     short loc_18000957A
0x18000956f  mov     rax, [rdx+8]
0x180009573  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x18000957a  test    rax, rax
0x18000957d  jz      short loc_1800095B7
0x18000957f  mov     rax, [rdx]
0x180009582  sub     rax, qword ptr cs:IID_IDispatch.Data1
0x180009589  jnz     short loc_180009596
0x18000958b  mov     rax, [rdx+8]
0x18000958f  sub     rax, qword ptr cs:IID_IDispatch.Data4
0x180009596  test    rax, rax
0x180009599  jz      short loc_1800095F4
0x18000959b  mov     rax, [rdx]
0x18000959e  sub     rax, qword ptr cs:IID_IXPathNavigator.Data1
0x1800095a5  jnz     short loc_1800095B2
0x1800095a7  mov     rax, [rdx+8]
0x1800095ab  sub     rax, qword ptr cs:IID_IXPathNavigator.Data4
0x1800095b2  test    rax, rax
0x1800095b5  jnz     short loc_1800095BC
0x1800095b7  mov     rax, r9
0x1800095ba  jmp     short loc_180009604
0x1800095bc  mov     rax, [rdx]
0x1800095bf  sub     rax, qword ptr cs:IID_IAppHostNavigator.Data1
0x1800095c6  jnz     short loc_1800095D3
0x1800095c8  mov     rax, [rdx+8]
0x1800095cc  sub     rax, qword ptr cs:IID_IAppHostNavigator.Data4
0x1800095d3  test    rax, rax
0x1800095d6  jz      short loc_1800095F4
0x1800095d8  mov     rax, [rdx]
0x1800095db  sub     rax, qword ptr cs:_GUID_4f29aa5f_4a59_4e88_bc5a_a902f6ff1d86.Data1
0x1800095e2  jnz     short loc_1800095EF
0x1800095e4  mov     rax, [rdx+8]
0x1800095e8  sub     rax, qword ptr cs:_GUID_4f29aa5f_4a59_4e88_bc5a_a902f6ff1d86.Data4
0x1800095ef  test    rax, rax
0x1800095f2  jnz     short loc_18000961D
0x1800095f4  add     rcx, 8
0x1800095f8  mov     rax, r9
0x1800095fb  neg     rax
0x1800095fe  sbb     rax, rax
0x180009601  and     rax, rcx
0x180009604  mov     [r8], rax
0x180009607  test    rax, rax
0x18000960a  jz      short loc_180009629
0x18000960c  mov     rax, [r9]
0x18000960f  mov     rcx, r9
0x180009612  mov     rax, [rax+8]
0x180009616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000961b  jmp     short loc_180009629
0x18000961d  mov     ebx, 80004002h
0x180009622  mov     qword ptr [r8], 0
0x180009629  mov     eax, ebx
0x18000962b  add     rsp, 20h
0x18000962f  pop     rbx
0x180009630  retn
```
