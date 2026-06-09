# AppHostNavigatorTemplate<AppHostFileSystemNavigator,IAppHostFileSystemNavigator,FileSystemTree>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800063d0`
- end: `0x1800064e1`
- name: `?QueryInterface@?$AppHostNavigatorTemplate@VAppHostFileSystemNavigator@@UIAppHostFileSystemNavigator@@VFileSystemTree@@@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800064f0`

## callees

- `0x1800063d0`
- `0x180011e98`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall AppHostNavigatorTemplate<AppHostFileSystemNavigator,IAppHostFileSystemNavigator,FileSystemTree>::QueryInterface(
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
  v11 = *a2 - *(_QWORD *)&GUID_355bd6c9_0a2e_42fa_ba7e_b4495b9dbeae.Data1;
  if ( *a2 == *(_QWORD *)&GUID_355bd6c9_0a2e_42fa_ba7e_b4495b9dbeae.Data1 )
    v11 = a2[1] - *(_QWORD *)GUID_355bd6c9_0a2e_42fa_ba7e_b4495b9dbeae.Data4;
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
0x1800063d0  push    rbx
0x1800063d2  sub     rsp, 20h
0x1800063d6  mov     r9, rcx
0x1800063d9  test    r8, r8
0x1800063dc  jnz     short loc_1800063E8
0x1800063de  mov     eax, 80070057h
0x1800063e3  jmp     loc_1800064DB
0x1800063e8  mov     rax, [rdx]
0x1800063eb  sub     rax, qword ptr cs:IID_ISupportErrorInfo.Data1
0x1800063f2  jnz     short loc_1800063FF
0x1800063f4  mov     rax, [rdx+8]
0x1800063f8  sub     rax, qword ptr cs:IID_ISupportErrorInfo.Data4
0x1800063ff  test    rax, rax
0x180006402  jnz     short loc_180006411
0x180006404  mov     rcx, r8; struct ISupportErrorInfo **
0x180006407  add     rsp, 20h
0x18000640b  pop     rbx
0x18000640c  jmp     ?CreateInstance@SupportErrorInfoImpl@@SAJPEAPEAUISupportErrorInfo@@@Z; SupportErrorInfoImpl::CreateInstance(ISupportErrorInfo * *)
0x180006411  mov     rax, [rdx]
0x180006414  xor     ebx, ebx
0x180006416  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x18000641d  jnz     short loc_18000642A
0x18000641f  mov     rax, [rdx+8]
0x180006423  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x18000642a  test    rax, rax
0x18000642d  jz      short loc_180006467
0x18000642f  mov     rax, [rdx]
0x180006432  sub     rax, qword ptr cs:IID_IDispatch.Data1
0x180006439  jnz     short loc_180006446
0x18000643b  mov     rax, [rdx+8]
0x18000643f  sub     rax, qword ptr cs:IID_IDispatch.Data4
0x180006446  test    rax, rax
0x180006449  jz      short loc_1800064A4
0x18000644b  mov     rax, [rdx]
0x18000644e  sub     rax, qword ptr cs:IID_IXPathNavigator.Data1
0x180006455  jnz     short loc_180006462
0x180006457  mov     rax, [rdx+8]
0x18000645b  sub     rax, qword ptr cs:IID_IXPathNavigator.Data4
0x180006462  test    rax, rax
0x180006465  jnz     short loc_18000646C
0x180006467  mov     rax, r9
0x18000646a  jmp     short loc_1800064B4
0x18000646c  mov     rax, [rdx]
0x18000646f  sub     rax, qword ptr cs:IID_IAppHostNavigator.Data1
0x180006476  jnz     short loc_180006483
0x180006478  mov     rax, [rdx+8]
0x18000647c  sub     rax, qword ptr cs:IID_IAppHostNavigator.Data4
0x180006483  test    rax, rax
0x180006486  jz      short loc_1800064A4
0x180006488  mov     rax, [rdx]
0x18000648b  sub     rax, qword ptr cs:_GUID_355bd6c9_0a2e_42fa_ba7e_b4495b9dbeae.Data1
0x180006492  jnz     short loc_18000649F
0x180006494  mov     rax, [rdx+8]
0x180006498  sub     rax, qword ptr cs:_GUID_355bd6c9_0a2e_42fa_ba7e_b4495b9dbeae.Data4
0x18000649f  test    rax, rax
0x1800064a2  jnz     short loc_1800064CD
0x1800064a4  add     rcx, 8
0x1800064a8  mov     rax, r9
0x1800064ab  neg     rax
0x1800064ae  sbb     rax, rax
0x1800064b1  and     rax, rcx
0x1800064b4  mov     [r8], rax
0x1800064b7  test    rax, rax
0x1800064ba  jz      short loc_1800064D9
0x1800064bc  mov     rax, [r9]
0x1800064bf  mov     rcx, r9
0x1800064c2  mov     rax, [rax+8]
0x1800064c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064cb  jmp     short loc_1800064D9
0x1800064cd  mov     ebx, 80004002h
0x1800064d2  mov     qword ptr [r8], 0
0x1800064d9  mov     eax, ebx
0x1800064db  add     rsp, 20h
0x1800064df  pop     rbx
0x1800064e0  retn
```
