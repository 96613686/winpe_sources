# SimpleIUnknownImpl<IXPathQueryStringCompiler>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800022b0`
- end: `0x180002355`
- name: `?QueryInterface@?$SimpleIUnknownImpl@UIXPathQueryStringCompiler@@@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `165`
- prototype: `__int64 __fastcall(struct ISupportErrorInfo *, _QWORD *, struct ISupportErrorInfo **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800022b0`
- `0x180010618`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall SimpleIUnknownImpl<IXPathQueryStringCompiler>::QueryInterface(
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
  v7 = *a2 - *(_QWORD *)&GUID_5fd1dce3_10f9_4d4e_b18a_90851d05690c.Data1;
  if ( *a2 == *(_QWORD *)&GUID_5fd1dce3_10f9_4d4e_b18a_90851d05690c.Data1 )
    v7 = a2[1] - *(_QWORD *)GUID_5fd1dce3_10f9_4d4e_b18a_90851d05690c.Data4;
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
0x1800022b0  push    rbx
0x1800022b2  sub     rsp, 20h
0x1800022b6  test    r8, r8
0x1800022b9  jnz     short loc_1800022C5
0x1800022bb  mov     eax, 80070057h
0x1800022c0  jmp     loc_18000234F
0x1800022c5  mov     rax, [rdx]
0x1800022c8  sub     rax, qword ptr cs:IID_ISupportErrorInfo.Data1
0x1800022cf  jnz     short loc_1800022DC
0x1800022d1  mov     rax, [rdx+8]
0x1800022d5  sub     rax, qword ptr cs:IID_ISupportErrorInfo.Data4
0x1800022dc  test    rax, rax
0x1800022df  jnz     short loc_1800022EE
0x1800022e1  mov     rcx, r8; struct ISupportErrorInfo **
0x1800022e4  add     rsp, 20h
0x1800022e8  pop     rbx
0x1800022e9  jmp     ?CreateInstance@SupportErrorInfoImpl@@SAJPEAPEAUISupportErrorInfo@@@Z; SupportErrorInfoImpl::CreateInstance(ISupportErrorInfo * *)
0x1800022ee  mov     rax, [rdx]
0x1800022f1  xor     ebx, ebx
0x1800022f3  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x1800022fa  jnz     short loc_180002307
0x1800022fc  mov     rax, [rdx+8]
0x180002300  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x180002307  test    rax, rax
0x18000230a  jz      short loc_180002328
0x18000230c  mov     rax, [rdx]
0x18000230f  sub     rax, qword ptr cs:_GUID_5fd1dce3_10f9_4d4e_b18a_90851d05690c.Data1
0x180002316  jnz     short loc_180002323
0x180002318  mov     rax, [rdx+8]
0x18000231c  sub     rax, qword ptr cs:_GUID_5fd1dce3_10f9_4d4e_b18a_90851d05690c.Data4
0x180002323  test    rax, rax
0x180002326  jnz     short loc_180002341
0x180002328  mov     rax, rcx
0x18000232b  mov     [r8], rcx
0x18000232e  test    rax, rax
0x180002331  jz      short loc_18000234D
0x180002333  mov     rax, [rcx]
0x180002336  mov     rax, [rax+8]
0x18000233a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000233f  jmp     short loc_18000234D
0x180002341  mov     ebx, 80004002h
0x180002346  mov     qword ptr [r8], 0
0x18000234d  mov     eax, ebx
0x18000234f  add     rsp, 20h
0x180002353  pop     rbx
0x180002354  retn
```
