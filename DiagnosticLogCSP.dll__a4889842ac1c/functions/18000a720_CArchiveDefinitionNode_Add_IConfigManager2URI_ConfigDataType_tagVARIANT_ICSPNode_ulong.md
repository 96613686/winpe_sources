# CArchiveDefinitionNode::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)

- ea: `0x18000a720`
- end: `0x18000a811`
- name: `?Add@CArchiveDefinitionNode@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z`
- size: `241`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int128 *, _QWORD *, _DWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001104`
- `0x180001b60`
- `0x18000a720`
- `0x180014640`
- `0x180037010`

## pseudocode

```c
__int64 __fastcall CArchiveDefinitionNode::Add(
        _DWORD *a1,
        __int64 a2,
        __int64 a3,
        __int128 *a4,
        _QWORD *a5,
        _DWORD *a6)
{
  __int128 v6; // xmm0
  __int64 v7; // xmm1_8
  bool v8; // zf
  unsigned int v9; // eax
  unsigned int v10; // ebx
  int v12; // [rsp+30h] [rbp-50h] BYREF
  __int128 v13; // [rsp+40h] [rbp-40h] BYREF
  __int64 v14; // [rsp+50h] [rbp-30h]
  int *v15; // [rsp+60h] [rbp-20h]
  __int64 v16; // [rsp+68h] [rbp-18h]

  if ( a2 && a5 && a6 )
  {
    v6 = *a4;
    *a5 = 0;
    v7 = *((_QWORD *)a4 + 2);
    *a6 = 0;
    v8 = a1[11] == 30;
    v13 = v6;
    v14 = v7;
    if ( v8 )
      v9 = (*(__int64 (__fastcall **)(_DWORD *, __int128 *))(*(_QWORD *)a1 + 64LL))(a1, &v13);
    else
      v9 = CCSPNodeImpl::Add(a1, a2, a3, &v13, a5, a6);
    v10 = v9;
  }
  else
  {
    v10 = -2147024809;
  }
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v15 = &v12;
    v16 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_180048E90, &byte_18003EF5F, 0, 0, 3, &v13, v10);
  }
  return v10;
}

```

## disassembly

```asm
0x18000a720  mov     [rsp-8+arg_10], rbx
0x18000a725  push    rbp
0x18000a726  mov     rbp, rsp
0x18000a729  sub     rsp, 80h
0x18000a730  mov     rax, cs:__security_cookie
0x18000a737  xor     rax, rsp
0x18000a73a  mov     [rbp+var_10], rax
0x18000a73e  mov     rax, [rbp+arg_20]
0x18000a742  mov     r10, [rbp+arg_28]
0x18000a746  test    rdx, rdx
0x18000a749  jz      short loc_18000A7A5
0x18000a74b  test    rax, rax
0x18000a74e  jz      short loc_18000A7A5
0x18000a750  test    r10, r10
0x18000a753  jz      short loc_18000A7A5
0x18000a755  movups  xmm0, xmmword ptr [r9]
0x18000a759  mov     qword ptr [rax], 0
0x18000a760  movsd   xmm1, qword ptr [r9+10h]
0x18000a766  mov     dword ptr [r10], 0
0x18000a76d  cmp     dword ptr [rcx+2Ch], 1Eh
0x18000a771  movaps  [rbp+var_40], xmm0
0x18000a775  movsd   [rbp+var_30], xmm1
0x18000a77a  jz      short loc_18000A791
0x18000a77c  mov     [rsp+80h+var_58], r10
0x18000a781  lea     r9, [rbp+var_40]
0x18000a785  mov     [rsp+80h+var_60], rax
0x18000a78a  call    ?Add@CCSPNodeImpl@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z; CCSPNodeImpl::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)
0x18000a78f  jmp     short loc_18000A7A1
0x18000a791  mov     rax, [rcx]
0x18000a794  lea     rdx, [rbp+var_40]
0x18000a798  mov     rax, [rax+40h]
0x18000a79c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7a1  mov     ebx, eax
0x18000a7a3  jmp     short loc_18000A7AA
0x18000a7a5  mov     ebx, 80070057h
0x18000a7aa  mov     eax, cs:dword_180048E90
0x18000a7b0  cmp     eax, 5
0x18000a7b3  jbe     short loc_18000A7F2
0x18000a7b5  lea     rax, [rbp+var_50]
0x18000a7b9  mov     [rbp+var_50], ebx
0x18000a7bc  mov     [rbp+var_20], rax
0x18000a7c0  lea     rdx, byte_18003EF5F
0x18000a7c7  lea     rax, [rbp+var_40]
0x18000a7cb  mov     [rbp+var_18], 4
0x18000a7d3  mov     [rsp+80h+var_58], rax
0x18000a7d8  lea     rcx, dword_180048E90
0x18000a7df  xor     r9d, r9d
0x18000a7e2  mov     dword ptr [rsp+80h+var_60], 3
0x18000a7ea  xor     r8d, r8d
0x18000a7ed  call    _tlgWriteTransfer_EventWriteTransfer
0x18000a7f2  mov     eax, ebx
0x18000a7f4  mov     rcx, [rbp+var_10]
0x18000a7f8  xor     rcx, rsp; StackCookie
0x18000a7fb  call    __security_check_cookie
0x18000a800  mov     rbx, [rsp+80h+arg_10]
0x18000a808  add     rsp, 80h
0x18000a80f  pop     rbp
0x18000a810  retn
```
