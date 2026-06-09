# AppHostNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::QueryInterface(_GUID const &,void * *)

- ea: `0x180007030`
- end: `0x180007141`
- name: `?QueryInterface@?$AppHostNavigatorTemplate@VAppHostMergedConfigNavigator@@UIAppHostMergedConfigNavigator@@VMergedConfigTree@@@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x180007150`

## callees

- `0x180007030`
- `0x180011e98`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall AppHostNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::QueryInterface(
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
  v11 = *a2 - *(_QWORD *)&GUID_6bf27412_bb61_40c6_9ad6_1a790cbd0cb8.Data1;
  if ( *a2 == *(_QWORD *)&GUID_6bf27412_bb61_40c6_9ad6_1a790cbd0cb8.Data1 )
    v11 = a2[1] - *(_QWORD *)GUID_6bf27412_bb61_40c6_9ad6_1a790cbd0cb8.Data4;
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
0x180007030  push    rbx
0x180007032  sub     rsp, 20h
0x180007036  mov     r9, rcx
0x180007039  test    r8, r8
0x18000703c  jnz     short loc_180007048
0x18000703e  mov     eax, 80070057h
0x180007043  jmp     loc_18000713B
0x180007048  mov     rax, [rdx]
0x18000704b  sub     rax, qword ptr cs:IID_ISupportErrorInfo.Data1
0x180007052  jnz     short loc_18000705F
0x180007054  mov     rax, [rdx+8]
0x180007058  sub     rax, qword ptr cs:IID_ISupportErrorInfo.Data4
0x18000705f  test    rax, rax
0x180007062  jnz     short loc_180007071
0x180007064  mov     rcx, r8; struct ISupportErrorInfo **
0x180007067  add     rsp, 20h
0x18000706b  pop     rbx
0x18000706c  jmp     ?CreateInstance@SupportErrorInfoImpl@@SAJPEAPEAUISupportErrorInfo@@@Z; SupportErrorInfoImpl::CreateInstance(ISupportErrorInfo * *)
0x180007071  mov     rax, [rdx]
0x180007074  xor     ebx, ebx
0x180007076  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x18000707d  jnz     short loc_18000708A
0x18000707f  mov     rax, [rdx+8]
0x180007083  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x18000708a  test    rax, rax
0x18000708d  jz      short loc_1800070C7
0x18000708f  mov     rax, [rdx]
0x180007092  sub     rax, qword ptr cs:IID_IDispatch.Data1
0x180007099  jnz     short loc_1800070A6
0x18000709b  mov     rax, [rdx+8]
0x18000709f  sub     rax, qword ptr cs:IID_IDispatch.Data4
0x1800070a6  test    rax, rax
0x1800070a9  jz      short loc_180007104
0x1800070ab  mov     rax, [rdx]
0x1800070ae  sub     rax, qword ptr cs:IID_IXPathNavigator.Data1
0x1800070b5  jnz     short loc_1800070C2
0x1800070b7  mov     rax, [rdx+8]
0x1800070bb  sub     rax, qword ptr cs:IID_IXPathNavigator.Data4
0x1800070c2  test    rax, rax
0x1800070c5  jnz     short loc_1800070CC
0x1800070c7  mov     rax, r9
0x1800070ca  jmp     short loc_180007114
0x1800070cc  mov     rax, [rdx]
0x1800070cf  sub     rax, qword ptr cs:IID_IAppHostNavigator.Data1
0x1800070d6  jnz     short loc_1800070E3
0x1800070d8  mov     rax, [rdx+8]
0x1800070dc  sub     rax, qword ptr cs:IID_IAppHostNavigator.Data4
0x1800070e3  test    rax, rax
0x1800070e6  jz      short loc_180007104
0x1800070e8  mov     rax, [rdx]
0x1800070eb  sub     rax, qword ptr cs:_GUID_6bf27412_bb61_40c6_9ad6_1a790cbd0cb8.Data1
0x1800070f2  jnz     short loc_1800070FF
0x1800070f4  mov     rax, [rdx+8]
0x1800070f8  sub     rax, qword ptr cs:_GUID_6bf27412_bb61_40c6_9ad6_1a790cbd0cb8.Data4
0x1800070ff  test    rax, rax
0x180007102  jnz     short loc_18000712D
0x180007104  add     rcx, 8
0x180007108  mov     rax, r9
0x18000710b  neg     rax
0x18000710e  sbb     rax, rax
0x180007111  and     rax, rcx
0x180007114  mov     [r8], rax
0x180007117  test    rax, rax
0x18000711a  jz      short loc_180007139
0x18000711c  mov     rax, [r9]
0x18000711f  mov     rcx, r9
0x180007122  mov     rax, [rax+8]
0x180007126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000712b  jmp     short loc_180007139
0x18000712d  mov     ebx, 80004002h
0x180007132  mov     qword ptr [r8], 0
0x180007139  mov     eax, ebx
0x18000713b  add     rsp, 20h
0x18000713f  pop     rbx
0x180007140  retn
```
