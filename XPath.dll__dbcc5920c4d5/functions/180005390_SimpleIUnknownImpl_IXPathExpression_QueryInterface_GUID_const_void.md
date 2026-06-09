# SimpleIUnknownImpl<IXPathExpression>::QueryInterface(_GUID const &,void * *)

- ea: `0x180005390`
- end: `0x180005435`
- name: `?QueryInterface@?$SimpleIUnknownImpl@UIXPathExpression@@@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d6f0`

## callees

- `0x180005390`
- `0x180010618`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall SimpleIUnknownImpl<IXPathExpression>::QueryInterface(
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
  v7 = *a2 - *(_QWORD *)&GUID_69010634_90e9_4e24_9568_083801973afb.Data1;
  if ( *a2 == *(_QWORD *)&GUID_69010634_90e9_4e24_9568_083801973afb.Data1 )
    v7 = a2[1] - *(_QWORD *)GUID_69010634_90e9_4e24_9568_083801973afb.Data4;
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
0x180005390  push    rbx
0x180005392  sub     rsp, 20h
0x180005396  test    r8, r8
0x180005399  jnz     short loc_1800053A5
0x18000539b  mov     eax, 80070057h
0x1800053a0  jmp     loc_18000542F
0x1800053a5  mov     rax, [rdx]
0x1800053a8  sub     rax, qword ptr cs:IID_ISupportErrorInfo.Data1
0x1800053af  jnz     short loc_1800053BC
0x1800053b1  mov     rax, [rdx+8]
0x1800053b5  sub     rax, qword ptr cs:IID_ISupportErrorInfo.Data4
0x1800053bc  test    rax, rax
0x1800053bf  jnz     short loc_1800053CE
0x1800053c1  mov     rcx, r8; struct ISupportErrorInfo **
0x1800053c4  add     rsp, 20h
0x1800053c8  pop     rbx
0x1800053c9  jmp     ?CreateInstance@SupportErrorInfoImpl@@SAJPEAPEAUISupportErrorInfo@@@Z; SupportErrorInfoImpl::CreateInstance(ISupportErrorInfo * *)
0x1800053ce  mov     rax, [rdx]
0x1800053d1  xor     ebx, ebx
0x1800053d3  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x1800053da  jnz     short loc_1800053E7
0x1800053dc  mov     rax, [rdx+8]
0x1800053e0  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x1800053e7  test    rax, rax
0x1800053ea  jz      short loc_180005408
0x1800053ec  mov     rax, [rdx]
0x1800053ef  sub     rax, qword ptr cs:_GUID_69010634_90e9_4e24_9568_083801973afb.Data1
0x1800053f6  jnz     short loc_180005403
0x1800053f8  mov     rax, [rdx+8]
0x1800053fc  sub     rax, qword ptr cs:_GUID_69010634_90e9_4e24_9568_083801973afb.Data4
0x180005403  test    rax, rax
0x180005406  jnz     short loc_180005421
0x180005408  mov     rax, rcx
0x18000540b  mov     [r8], rcx
0x18000540e  test    rax, rax
0x180005411  jz      short loc_18000542D
0x180005413  mov     rax, [rcx]
0x180005416  mov     rax, [rax+8]
0x18000541a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000541f  jmp     short loc_18000542D
0x180005421  mov     ebx, 80004002h
0x180005426  mov     qword ptr [r8], 0
0x18000542d  mov     eax, ebx
0x18000542f  add     rsp, 20h
0x180005433  pop     rbx
0x180005434  retn
```
