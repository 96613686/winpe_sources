# CArchiveDefinitionNode::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)

- ea: `0x18000aa50`
- end: `0x18000ab42`
- name: `?Add@CArchiveDefinitionNode@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001108`
- `0x180001b90`
- `0x18000aa50`
- `0x180015100`
- `0x180039010`

## pseudocode

```c
__int64 __fastcall CArchiveDefinitionNode::Add(
        _DWORD *a1,
        __int64 a2,
        __int64 a3,
        struct _EVENT_DATA_DESCRIPTOR *a4,
        _QWORD *a5,
        _DWORD *a6)
{
  struct _EVENT_DATA_DESCRIPTOR v6; // xmm0
  ULONGLONG Ptr; // xmm1_8
  bool v8; // zf
  unsigned int v9; // eax
  unsigned int v10; // ebx
  unsigned int v12; // [rsp+30h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+40h] [rbp-40h] BYREF
  ULONGLONG v14; // [rsp+50h] [rbp-30h]
  unsigned int *v15; // [rsp+60h] [rbp-20h]
  __int64 v16; // [rsp+68h] [rbp-18h]

  if ( a2 && a5 && a6 )
  {
    v6 = *a4;
    *a5 = 0;
    Ptr = a4[1].Ptr;
    *a6 = 0;
    v8 = a1[11] == 30;
    v13 = v6;
    v14 = Ptr;
    if ( v8 )
      v9 = (*(__int64 (__fastcall **)(_DWORD *, struct _EVENT_DATA_DESCRIPTOR *))(*(_QWORD *)a1 + 64LL))(a1, &v13);
    else
      v9 = CCSPNodeImpl::Add((__int64)a1, a2, a3, (__int64)&v13, a5, a6);
    v10 = v9;
  }
  else
  {
    v10 = -2147024809;
  }
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    v12 = v10;
    v15 = &v12;
    v16 = 4;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18004AE90, (unsigned __int8 *)byte_180040F5F, 0, 0, 3u, &v13);
  }
  return v10;
}

```

## disassembly

```asm
0x18000aa50  mov     [rsp-8+arg_10], rbx
0x18000aa55  push    rbp
0x18000aa56  mov     rbp, rsp
0x18000aa59  sub     rsp, 80h
0x18000aa60  mov     rax, cs:__security_cookie
0x18000aa67  xor     rax, rsp
0x18000aa6a  mov     [rbp+var_10], rax
0x18000aa6e  mov     rax, [rbp+arg_20]
0x18000aa72  mov     r10, [rbp+arg_28]
0x18000aa76  test    rdx, rdx
0x18000aa79  jz      short loc_18000AAD5
0x18000aa7b  test    rax, rax
0x18000aa7e  jz      short loc_18000AAD5
0x18000aa80  test    r10, r10
0x18000aa83  jz      short loc_18000AAD5
0x18000aa85  movups  xmm0, xmmword ptr [r9]
0x18000aa89  mov     qword ptr [rax], 0
0x18000aa90  movsd   xmm1, qword ptr [r9+10h]
0x18000aa96  mov     dword ptr [r10], 0
0x18000aa9d  cmp     dword ptr [rcx+2Ch], 1Eh
0x18000aaa1  movaps  [rbp+var_40], xmm0
0x18000aaa5  movsd   [rbp+var_30], xmm1
0x18000aaaa  jz      short loc_18000AAC1
0x18000aaac  mov     [rsp+80h+var_58], r10
0x18000aab1  lea     r9, [rbp+var_40]
0x18000aab5  mov     [rsp+80h+var_60], rax
0x18000aaba  call    ?Add@CCSPNodeImpl@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z; CCSPNodeImpl::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)
0x18000aabf  jmp     short loc_18000AAD1
0x18000aac1  mov     rax, [rcx]
0x18000aac4  lea     rdx, [rbp+var_40]
0x18000aac8  mov     rax, [rax+40h]
0x18000aacc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aad1  mov     ebx, eax
0x18000aad3  jmp     short loc_18000AADA
0x18000aad5  mov     ebx, 80070057h
0x18000aada  mov     eax, cs:dword_18004AE90
0x18000aae0  cmp     eax, 5
0x18000aae3  jbe     short loc_18000AB22
0x18000aae5  lea     rax, [rbp+var_50]
0x18000aae9  mov     [rbp+var_50], ebx
0x18000aaec  mov     [rbp+var_20], rax
0x18000aaf0  lea     rdx, byte_180040F5F
0x18000aaf7  lea     rax, [rbp+var_40]
0x18000aafb  mov     [rbp+var_18], 4
0x18000ab03  mov     [rsp+80h+var_58], rax
0x18000ab08  lea     rcx, dword_18004AE90
0x18000ab0f  xor     r9d, r9d
0x18000ab12  mov     dword ptr [rsp+80h+var_60], 3
0x18000ab1a  xor     r8d, r8d
0x18000ab1d  call    _tlgWriteTransfer_EventWriteTransfer
0x18000ab22  mov     eax, ebx
0x18000ab24  mov     rcx, [rbp+var_10]
0x18000ab28  xor     rcx, rsp; StackCookie
0x18000ab2b  call    __security_check_cookie
0x18000ab30  mov     rbx, [rsp+80h+arg_10]
0x18000ab38  add     rsp, 80h
0x18000ab3f  pop     rbp
0x18000ab40  retn
```
