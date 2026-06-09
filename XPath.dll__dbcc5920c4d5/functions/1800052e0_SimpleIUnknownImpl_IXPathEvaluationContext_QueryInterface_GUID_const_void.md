# SimpleIUnknownImpl<IXPathEvaluationContext>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800052e0`
- end: `0x180005385`
- name: `?QueryInterface@?$SimpleIUnknownImpl@UIXPathEvaluationContext@@@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `165`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800052e0`
- `0x180010618`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall SimpleIUnknownImpl<IXPathEvaluationContext>::QueryInterface(
        struct ISupportErrorInfo *a1,
        _QWORD *a2,
        struct ISupportErrorInfo **a3)
{
  __int64 v4; // rax
  unsigned int v5; // ebx
  __int64 v6; // rax
  __int64 v7; // rax

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
    goto LABEL_13;
  v7 = *a2 - *(_QWORD *)&GUID_9beec600_5aa3_45a2_a918_f13ccde2e202.Data1;
  if ( *a2 == *(_QWORD *)&GUID_9beec600_5aa3_45a2_a918_f13ccde2e202.Data1 )
    v7 = a2[1] - *(_QWORD *)GUID_9beec600_5aa3_45a2_a918_f13ccde2e202.Data4;
  if ( v7 )
  {
    v5 = -2147467262;
    *a3 = 0;
  }
  else
  {
LABEL_13:
    *a3 = a1;
    if ( a1 )
      ((void (__fastcall *)(struct ISupportErrorInfo *))a1->lpVtbl->AddRef)(a1);
  }
  return v5;
}

```

## disassembly

```asm
0x1800052e0  push    rbx
0x1800052e2  sub     rsp, 20h
0x1800052e6  test    r8, r8
0x1800052e9  jnz     short loc_1800052F5
0x1800052eb  mov     eax, 80070057h
0x1800052f0  jmp     loc_18000537F
0x1800052f5  mov     rax, [rdx]
0x1800052f8  sub     rax, qword ptr cs:IID_ISupportErrorInfo.Data1
0x1800052ff  jnz     short loc_18000530C
0x180005301  mov     rax, [rdx+8]
0x180005305  sub     rax, qword ptr cs:IID_ISupportErrorInfo.Data4
0x18000530c  test    rax, rax
0x18000530f  jnz     short loc_18000531E
0x180005311  mov     rcx, r8; struct ISupportErrorInfo **
0x180005314  add     rsp, 20h
0x180005318  pop     rbx
0x180005319  jmp     ?CreateInstance@SupportErrorInfoImpl@@SAJPEAPEAUISupportErrorInfo@@@Z; SupportErrorInfoImpl::CreateInstance(ISupportErrorInfo * *)
0x18000531e  mov     rax, [rdx]
0x180005321  xor     ebx, ebx
0x180005323  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x18000532a  jnz     short loc_180005337
0x18000532c  mov     rax, [rdx+8]
0x180005330  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x180005337  test    rax, rax
0x18000533a  jz      short loc_180005358
0x18000533c  mov     rax, [rdx]
0x18000533f  sub     rax, qword ptr cs:_GUID_9beec600_5aa3_45a2_a918_f13ccde2e202.Data1
0x180005346  jnz     short loc_180005353
0x180005348  mov     rax, [rdx+8]
0x18000534c  sub     rax, qword ptr cs:_GUID_9beec600_5aa3_45a2_a918_f13ccde2e202.Data4
0x180005353  test    rax, rax
0x180005356  jnz     short loc_180005371
0x180005358  mov     rax, rcx
0x18000535b  mov     [r8], rcx
0x18000535e  test    rax, rax
0x180005361  jz      short loc_18000537D
0x180005363  mov     rax, [rcx]
0x180005366  mov     rax, [rax+8]
0x18000536a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000536f  jmp     short loc_18000537D
0x180005371  mov     ebx, 80004002h
0x180005376  mov     qword ptr [r8], 0
0x18000537d  mov     eax, ebx
0x18000537f  add     rsp, 20h
0x180005383  pop     rbx
0x180005384  retn
```
