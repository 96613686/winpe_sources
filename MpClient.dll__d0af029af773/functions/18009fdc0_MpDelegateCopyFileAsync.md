# MpDelegateCopyFileAsync

- ea: `0x18009fdc0`
- end: `0x1800a03b5`
- name: `MpDelegateCopyFileAsync`
- size: `1525`
- prototype: `__int64 __fastcall(int, __int64, __int64, int, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001b270`
- `0x18001e25c`
- `0x18003b830`
- `0x1800733a8`
- `0x180078724`
- `0x180078e00`
- `0x180079490`
- `0x18009fdc0`
- `0x180125920`
- `0x1801259a0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18009fff1`
- `KERNEL32!CloseHandle` at `0x1800a0292`
- `KERNEL32!CloseHandle` at `0x1800a02c8`
- `KERNEL32!CloseHandle` at `0x1800a0328`
- `KERNEL32!CloseHandle` at `0x18009fff1`
- `KERNEL32!CloseHandle` at `0x1800a0292`
- `KERNEL32!CloseHandle` at `0x1800a02c8`
- `KERNEL32!CloseHandle` at `0x1800a0328`
- `KERNEL32!WaitForSingleObject` at `0x1800a00af`
- `KERNEL32!WaitForSingleObject` at `0x1800a017e`
- `KERNEL32!WaitForSingleObject` at `0x1800a00af`
- `KERNEL32!WaitForSingleObject` at `0x1800a017e`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800a010f`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800a010f`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800a009d`
- `RPCRT4!Ndr64AsyncClientCall` at `0x1800a009d`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18009ff29`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x18009ff29`
- `RPCRT4!RpcRaiseException` at `0x1800a016a`
- `RPCRT4!RpcRaiseException` at `0x1800a01d9`
- `RPCRT4!RpcRaiseException` at `0x1800a0238`
- `RPCRT4!RpcRaiseException` at `0x1800a016a`
- `RPCRT4!RpcRaiseException` at `0x1800a01d9`
- `RPCRT4!RpcRaiseException` at `0x1800a0238`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800a015f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800a01ce`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800a01f0`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800a015f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800a01ce`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800a01f0`

## pseudocode

```c
__int64 __fastcall MpDelegateCopyFileAsync(int a1, __int64 a2, __int64 a3, int a4, __int64 a5, __int64 a6, __int64 a7)
{
  int v9; // eax
  unsigned int v10; // ebx
  void *v12; // rbx
  int v13; // eax
  unsigned int v14; // r14d
  RPC_STATUS v15; // r14d
  int v16; // eax
  DWORD v17; // eax
  unsigned int v18; // eax
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  RPC_STATUS v21; // eax
  RPC_STATUS v22; // eax
  RPC_STATUS v23; // r15d
  unsigned int v24; // r15d
  unsigned int v25; // r15d
  LPVOID lpMem; // [rsp+68h] [rbp-F0h] BYREF
  __int64 v28; // [rsp+70h] [rbp-E8h] BYREF
  __int64 v29; // [rsp+78h] [rbp-E0h]
  __int64 v30; // [rsp+80h] [rbp-D8h]
  __int64 v31; // [rsp+88h] [rbp-D0h]
  _RPC_ASYNC_STATE pAsync; // [rsp+A0h] [rbp-B8h] BYREF
  int v33; // [rsp+110h] [rbp-48h] BYREF
  int Reply; // [rsp+114h] [rbp-44h] BYREF
  HANDLE hObject; // [rsp+118h] [rbp-40h] BYREF

  v31 = a3;
  v30 = a5;
  v29 = a6;
  Reply = 0;
  if ( !a7 || !*(_QWORD *)a7 )
    return 2147942487LL;
  lpMem = 0;
  v9 = MpManagerOpen(0, &lpMem);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
      sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 180, &stru_180146EE0, (unsigned int)v9);
    if ( lpMem )
      MpHandleClose(lpMem);
    return v10;
  }
  v28 = 0;
  v12 = lpMem;
  v13 = sub_180078724(1, *((_QWORD *)lpMem + 1), &v28);
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
      sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 181, &stru_180146EE0, (unsigned int)v13);
LABEL_26:
    MpHandleClose(v12);
    return v14;
  }
  sub_1801259A0(&pAsync, 0, 112);
  v15 = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( v15 )
  {
    v14 = v15 | 0x80010000;
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
      sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 182, &stru_180146EE0, v14);
    goto LABEL_26;
  }
  hObject = 0;
  v16 = sub_18001E25C((int)&hObject, 1, 0, 0, 0);
  v14 = v16;
  if ( v16 < 0 )
  {
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
      sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 183, &stru_180146EE0, (unsigned int)v16);
    if ( hObject )
      CloseHandle(hObject);
    goto LABEL_26;
  }
  pAsync.UserInfo = 0;
  pAsync.NotificationType = RpcNotificationTypeEvent;
  pAsync.u.APC.NotificationRoutine = (PFN_RPCNOTIFICATION_ROUTINE)hObject;
  v33 = 0;
  Ndr64AsyncClientCall(
    (MIDL_STUBLESS_PROXY_INFO *)&stru_1801555E8,
    1u,
    0,
    &pAsync,
    v28,
    a1,
    a2,
    v31,
    a4,
    v30,
    v29,
    &v33);
  do
  {
    v17 = WaitForSingleObject(pAsync.u.APC.NotificationRoutine, *(_DWORD *)(a7 + 16));
    if ( !v17 )
      goto LABEL_45;
    if ( v17 != 258 )
    {
      v18 = sub_18001B270();
      v19 = off_18019DE80;
      if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
      {
        v20 = 184;
        goto LABEL_43;
      }
      goto LABEL_44;
    }
  }
  while ( !(*(unsigned int (__fastcall **)(_QWORD))a7)(*(_QWORD *)(a7 + 8)) );
  v21 = RpcAsyncCancelCall(&pAsync, 0);
  if ( v21 )
  {
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
      sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 185, &stru_180146EE0, v21 | 0x80010000);
    RpcAsyncCompleteCall(&pAsync, &Reply);
    RpcRaiseException(1766);
  }
  if ( WaitForSingleObject(pAsync.u.APC.NotificationRoutine, 0x1D4C0u) )
  {
    v18 = sub_18001B270();
    v19 = off_18019DE80;
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
    {
      v20 = 186;
LABEL_43:
      sub_1800733A8(v19[2], v20, &stru_180146EE0, v18);
    }
LABEL_44:
    RpcAsyncCompleteCall(&pAsync, &Reply);
    RpcRaiseException(1460);
  }
LABEL_45:
  v22 = RpcAsyncCompleteCall(&pAsync, &Reply);
  v23 = v22;
  if ( v22 )
  {
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
      sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 187, &stru_180146EE0, v22 | 0x80010000);
    RpcRaiseException(v23);
  }
  if ( v33 )
  {
    v24 = v33 | 0x80010000;
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
      sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 188, &stru_180146EE0, v24);
    if ( hObject )
      CloseHandle(hObject);
    if ( v12 )
      MpHandleClose(v12);
    return v24;
  }
  else
  {
    v25 = Reply;
    if ( Reply < 0 )
    {
      if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
      {
        sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 189, &stru_180146EE0, (unsigned int)Reply);
        v25 = Reply;
      }
      if ( hObject )
        CloseHandle(hObject);
      if ( v12 )
        MpHandleClose(v12);
      return v25;
    }
    else
    {
      if ( hObject )
        CloseHandle(hObject);
      if ( v12 )
        MpHandleClose(v12);
      return v14;
    }
  }
}

```

## disassembly

```asm
0x18009fdc0  push    rbx
0x18009fdc2  push    r12
0x18009fdc4  push    r13
0x18009fdc6  push    r14
0x18009fdc8  push    r15
0x18009fdca  sub     rsp, 130h
0x18009fdd1  mov     rax, cs:__security_cookie
0x18009fdd8  xor     rax, rsp
0x18009fddb  mov     [rsp+158h+var_38], rax
0x18009fde3  mov     [rsp+158h+var_F8], r9d
0x18009fde8  mov     [rsp+158h+var_D0], r8
0x18009fdf0  mov     r13, rdx
0x18009fdf3  mov     r12d, ecx
0x18009fdf6  mov     r15, [rsp+158h+arg_30]
0x18009fdfe  mov     rax, [rsp+158h+arg_20]
0x18009fe06  mov     [rsp+158h+var_D8], rax
0x18009fe0e  mov     rax, [rsp+158h+arg_28]
0x18009fe16  mov     [rsp+158h+var_E0], rax
0x18009fe1b  mov     [rsp+158h+Reply], 0
0x18009fe26  test    r15, r15
0x18009fe29  jz      loc_1800A038E
0x18009fe2f  cmp     qword ptr [r15], 0
0x18009fe33  jz      loc_1800A038E
0x18009fe39  mov     [rsp+158h+lpMem], 0
0x18009fe42  lea     rdx, [rsp+158h+lpMem]
0x18009fe47  xor     ecx, ecx
0x18009fe49  call    MpManagerOpen
0x18009fe4e  mov     ebx, eax
0x18009fe50  test    eax, eax
0x18009fe52  jns     short loc_18009FE9C
0x18009fe54  lea     rdx, off_18019DE80
0x18009fe5b  mov     rcx, cs:off_18019DE80
0x18009fe62  cmp     rcx, rdx
0x18009fe65  jz      short loc_18009FE86
0x18009fe67  test    byte ptr [rcx+1Ch], 1
0x18009fe6b  jz      short loc_18009FE86
0x18009fe6d  mov     edx, 0B4h
0x18009fe72  mov     r9d, eax
0x18009fe75  lea     r8, stru_180146EE0
0x18009fe7c  mov     rcx, [rcx+10h]
0x18009fe80  call    sub_1800733A8
0x18009fe85  nop
0x18009fe86  mov     rcx, [rsp+158h+lpMem]; lpMem
0x18009fe8b  test    rcx, rcx
0x18009fe8e  jz      short loc_18009FE95
0x18009fe90  call    MpHandleClose
0x18009fe95  mov     eax, ebx
0x18009fe97  jmp     loc_1800A0393
0x18009fe9c  mov     [rsp+158h+var_E8], 0
0x18009fea5  lea     r8, [rsp+158h+var_E8]
0x18009feaa  mov     rbx, [rsp+158h+lpMem]
0x18009feaf  mov     rdx, [rbx+8]
0x18009feb3  mov     ecx, 1
0x18009feb8  call    sub_180078724
0x18009febd  mov     r14d, eax
0x18009fec0  test    eax, eax
0x18009fec2  jns     short loc_18009FF06
0x18009fec4  lea     rdx, off_18019DE80
0x18009fecb  mov     rcx, cs:off_18019DE80
0x18009fed2  cmp     rcx, rdx
0x18009fed5  jz      short loc_18009FEF6
0x18009fed7  test    byte ptr [rcx+1Ch], 1
0x18009fedb  jz      short loc_18009FEF6
0x18009fedd  mov     edx, 0B5h
0x18009fee2  mov     r9d, eax
0x18009fee5  lea     r8, stru_180146EE0
0x18009feec  mov     rcx, [rcx+10h]
0x18009fef0  call    sub_1800733A8
0x18009fef5  nop
0x18009fef6  mov     rcx, rbx; lpMem
0x18009fef9  call    MpHandleClose
0x18009fefe  mov     eax, r14d
0x18009ff01  jmp     loc_1800A0393
0x18009ff06  mov     r14d, 70h ; 'p'
0x18009ff0c  mov     r8d, r14d
0x18009ff0f  xor     edx, edx
0x18009ff11  lea     rcx, [rsp+158h+pAsync]
0x18009ff19  call    sub_1801259A0
0x18009ff1e  mov     edx, r14d; Size
0x18009ff21  lea     rcx, [rsp+158h+pAsync]; pAsync
0x18009ff29  call    cs:RpcAsyncInitializeHandle
0x18009ff2f  mov     r14d, eax
0x18009ff32  test    eax, eax
0x18009ff34  jz      short loc_18009FF7F
0x18009ff36  or      r14d, 80010000h
0x18009ff3d  lea     rdx, off_18019DE80
0x18009ff44  mov     rcx, cs:off_18019DE80
0x18009ff4b  cmp     rcx, rdx
0x18009ff4e  jz      short loc_18009FF6F
0x18009ff50  test    byte ptr [rcx+1Ch], 1
0x18009ff54  jz      short loc_18009FF6F
0x18009ff56  mov     edx, 0B6h
0x18009ff5b  mov     r9d, r14d
0x18009ff5e  lea     r8, stru_180146EE0
0x18009ff65  mov     rcx, [rcx+10h]
0x18009ff69  call    sub_1800733A8
0x18009ff6e  nop
0x18009ff6f  mov     rcx, rbx; lpMem
0x18009ff72  call    MpHandleClose
0x18009ff77  mov     eax, r14d
0x18009ff7a  jmp     loc_1800A0393
0x18009ff7f  mov     [rsp+158h+hObject], 0
0x18009ff8b  mov     [rsp+158h+lpEventAttributes], 0; lpEventAttributes
0x18009ff94  xor     r9d, r9d; int
0x18009ff97  xor     r8d, r8d; int
0x18009ff9a  lea     edx, [r9+1]; int
0x18009ff9e  lea     rcx, [rsp+158h+hObject]; int
0x18009ffa6  call    sub_18001E25C
0x18009ffab  mov     r14d, eax
0x18009ffae  test    eax, eax
0x18009ffb0  jns     short loc_1800A0008
0x18009ffb2  lea     rdx, off_18019DE80
0x18009ffb9  mov     rcx, cs:off_18019DE80
0x18009ffc0  cmp     rcx, rdx
0x18009ffc3  jz      short loc_18009FFE4
0x18009ffc5  test    byte ptr [rcx+1Ch], 1
0x18009ffc9  jz      short loc_18009FFE4
0x18009ffcb  mov     edx, 0B7h
0x18009ffd0  mov     r9d, eax
0x18009ffd3  lea     r8, stru_180146EE0
0x18009ffda  mov     rcx, [rcx+10h]
0x18009ffde  call    sub_1800733A8
0x18009ffe3  nop
0x18009ffe4  mov     rcx, [rsp+158h+hObject]; hObject
0x18009ffec  test    rcx, rcx
0x18009ffef  jz      short loc_18009FFF8
0x18009fff1  call    cs:CloseHandle
0x18009fff7  nop
0x18009fff8  mov     rcx, rbx; lpMem
0x18009fffb  call    MpHandleClose
0x1800a0000  mov     eax, r14d
0x1800a0003  jmp     loc_1800A0393
0x1800a0008  mov     [rsp+158h+pAsync.UserInfo], 0
0x1800a0014  mov     [rsp+158h+pAsync.NotificationType], 1
0x1800a001f  mov     rax, [rsp+158h+hObject]
0x1800a0027  mov     qword ptr [rsp+158h+pAsync.u], rax
0x1800a002f  mov     [rsp+158h+var_48], 0
0x1800a003a  lea     rax, [rsp+158h+var_48]
0x1800a0042  mov     [rsp+158h+var_100], rax
0x1800a0047  mov     rax, [rsp+158h+var_E0]
0x1800a004c  mov     [rsp+158h+var_108], rax
0x1800a0051  mov     rax, [rsp+158h+var_D8]
0x1800a0059  mov     [rsp+158h+var_110], rax
0x1800a005e  mov     eax, [rsp+158h+var_F8]
0x1800a0062  mov     [rsp+158h+var_118], eax
0x1800a0066  mov     rax, [rsp+158h+var_D0]
0x1800a006e  mov     [rsp+158h+var_120], rax
0x1800a0073  mov     [rsp+158h+var_128], r13
0x1800a0078  mov     [rsp+158h+var_130], r12d
0x1800a007d  mov     rax, [rsp+158h+var_E8]
0x1800a0082  mov     [rsp+158h+lpEventAttributes], rax
0x1800a0087  lea     r9, [rsp+158h+pAsync]
0x1800a008f  xor     r8d, r8d; pReturnValue
0x1800a0092  lea     edx, [r8+1]; nProcNum
0x1800a0096  lea     rcx, stru_1801555E8; pProxyInfo
0x1800a009d  call    cs:Ndr64AsyncClientCall
0x1800a00a3  mov     edx, [r15+10h]; dwMilliseconds
0x1800a00a7  mov     rcx, qword ptr [rsp+158h+pAsync.u]; hHandle
0x1800a00af  call    cs:WaitForSingleObject
0x1800a00b5  test    eax, eax
0x1800a00b7  jz      loc_1800A01E0
0x1800a00bd  cmp     eax, 102h
0x1800a00c2  jz      short loc_1800A00F4
0x1800a00c4  call    sub_18001B270
0x1800a00c9  lea     rdx, off_18019DE80
0x1800a00d0  mov     rcx, cs:off_18019DE80
0x1800a00d7  cmp     rcx, rdx
0x1800a00da  jz      loc_1800A01BE
0x1800a00e0  test    byte ptr [rcx+1Ch], 1
0x1800a00e4  jz      loc_1800A01BE
0x1800a00ea  mov     edx, 0B8h
0x1800a00ef  jmp     loc_1800A01AB
0x1800a00f4  mov     rcx, [r15+8]
0x1800a00f8  mov     rax, [r15]
0x1800a00fb  call    cs:__guard_dispatch_icall_fptr
0x1800a0101  test    eax, eax
0x1800a0103  jz      short loc_1800A00A3
0x1800a0105  xor     edx, edx; fAbort
0x1800a0107  lea     rcx, [rsp+158h+pAsync]; pAsync
0x1800a010f  call    cs:RpcAsyncCancelCall
0x1800a0115  test    eax, eax
0x1800a0117  jz      short loc_1800A0171
0x1800a0119  lea     rdx, off_18019DE80
0x1800a0120  mov     rcx, cs:off_18019DE80
0x1800a0127  cmp     rcx, rdx
0x1800a012a  jz      short loc_1800A014F
0x1800a012c  test    byte ptr [rcx+1Ch], 1
0x1800a0130  jz      short loc_1800A014F
0x1800a0132  or      eax, 80010000h
0x1800a0137  mov     edx, 0B9h
0x1800a013c  mov     r9d, eax
0x1800a013f  lea     r8, stru_180146EE0
0x1800a0146  mov     rcx, [rcx+10h]
0x1800a014a  call    sub_1800733A8
0x1800a014f  lea     rdx, [rsp+158h+Reply]; Reply
0x1800a0157  lea     rcx, [rsp+158h+pAsync]; pAsync
0x1800a015f  call    cs:RpcAsyncCompleteCall
0x1800a0165  mov     ecx, 6E6h; exception
0x1800a016a  call    cs:RpcRaiseException
0x1800a0170  int     3; Trap to Debugger
0x1800a0171  mov     edx, 1D4C0h; dwMilliseconds
0x1800a0176  mov     rcx, qword ptr [rsp+158h+pAsync.u]; hHandle
0x1800a017e  call    cs:WaitForSingleObject
0x1800a0184  test    eax, eax
0x1800a0186  jz      short loc_1800A01E0
0x1800a0188  call    sub_18001B270
0x1800a018d  lea     rdx, off_18019DE80
0x1800a0194  mov     rcx, cs:off_18019DE80
0x1800a019b  cmp     rcx, rdx
0x1800a019e  jz      short loc_1800A01BE
0x1800a01a0  test    byte ptr [rcx+1Ch], 1
0x1800a01a4  jz      short loc_1800A01BE
0x1800a01a6  mov     edx, 0BAh
0x1800a01ab  mov     r9d, eax
0x1800a01ae  lea     r8, stru_180146EE0
0x1800a01b5  mov     rcx, [rcx+10h]
0x1800a01b9  call    sub_1800733A8
0x1800a01be  lea     rdx, [rsp+158h+Reply]; Reply
0x1800a01c6  lea     rcx, [rsp+158h+pAsync]; pAsync
0x1800a01ce  call    cs:RpcAsyncCompleteCall
0x1800a01d4  mov     ecx, 5B4h; exception
0x1800a01d9  call    cs:RpcRaiseException
0x1800a01df  int     3; Trap to Debugger
0x1800a01e0  lea     rdx, [rsp+158h+Reply]; Reply
0x1800a01e8  lea     rcx, [rsp+158h+pAsync]; pAsync
0x1800a01f0  call    cs:RpcAsyncCompleteCall
0x1800a01f6  mov     r15d, eax
0x1800a01f9  test    eax, eax
0x1800a01fb  jz      short loc_1800A023F
0x1800a01fd  lea     rdx, off_18019DE80
0x1800a0204  mov     rcx, cs:off_18019DE80
0x1800a020b  cmp     rcx, rdx
0x1800a020e  jz      short loc_1800A0235
0x1800a0210  test    byte ptr [rcx+1Ch], 1
0x1800a0214  jz      short loc_1800A0235
0x1800a0216  mov     r9d, eax
0x1800a0219  or      r9d, 80010000h
0x1800a0220  mov     edx, 0BBh
0x1800a0225  lea     r8, stru_180146EE0
0x1800a022c  mov     rcx, [rcx+10h]
0x1800a0230  call    sub_1800733A8
0x1800a0235  mov     ecx, r15d; exception
0x1800a0238  call    cs:RpcRaiseException
0x1800a023e  int     3; Trap to Debugger
0x1800a023f  mov     r15d, [rsp+158h+var_48]
0x1800a0247  test    r15d, r15d
0x1800a024a  jz      short loc_1800A02AE
0x1800a024c  or      r15d, 80010000h
0x1800a0253  lea     rdx, off_18019DE80
0x1800a025a  mov     rcx, cs:off_18019DE80
0x1800a0261  cmp     rcx, rdx
0x1800a0264  jz      short loc_1800A0285
0x1800a0266  test    byte ptr [rcx+1Ch], 1
0x1800a026a  jz      short loc_1800A0285
0x1800a026c  mov     edx, 0BCh
0x1800a0271  mov     r9d, r15d
0x1800a0274  lea     r8, stru_180146EE0
0x1800a027b  mov     rcx, [rcx+10h]
0x1800a027f  call    sub_1800733A8
0x1800a0284  nop
0x1800a0285  mov     rcx, [rsp+158h+hObject]; hObject
0x1800a028d  test    rcx, rcx
0x1800a0290  jz      short loc_1800A0299
0x1800a0292  call    cs:CloseHandle
0x1800a0298  nop
0x1800a0299  test    rbx, rbx
0x1800a029c  jz      short loc_1800A02A6
0x1800a029e  mov     rcx, rbx; lpMem
0x1800a02a1  call    MpHandleClose
0x1800a02a6  mov     eax, r15d
0x1800a02a9  jmp     loc_1800A0393
0x1800a02ae  mov     r15d, [rsp+158h+Reply]
0x1800a02b6  test    r15d, r15d
0x1800a02b9  js      short loc_1800A02E2
0x1800a02bb  mov     rcx, [rsp+158h+hObject]; hObject
0x1800a02c3  test    rcx, rcx
0x1800a02c6  jz      short loc_1800A02CF
0x1800a02c8  call    cs:CloseHandle
0x1800a02ce  nop
0x1800a02cf  test    rbx, rbx
0x1800a02d2  jz      short loc_1800A02DD
0x1800a02d4  mov     rcx, rbx; lpMem
0x1800a02d7  call    MpHandleClose
0x1800a02dc  nop
0x1800a02dd  jmp     loc_1800A0389
0x1800a02e2  lea     rdx, off_18019DE80
0x1800a02e9  mov     rcx, cs:off_18019DE80
0x1800a02f0  cmp     rcx, rdx
0x1800a02f3  jz      short loc_1800A031B
0x1800a02f5  test    byte ptr [rcx+1Ch], 1
0x1800a02f9  jz      short loc_1800A031B
0x1800a02fb  mov     edx, 0BDh
0x1800a0300  mov     r9d, r15d
0x1800a0303  lea     r8, stru_180146EE0
0x1800a030a  mov     rcx, [rcx+10h]
0x1800a030e  call    sub_1800733A8
0x1800a0313  mov     r15d, [rsp+158h+Reply]
0x1800a031b  mov     rcx, [rsp+158h+hObject]; hObject
0x1800a0323  test    rcx, rcx
0x1800a0326  jz      short loc_1800A032F
  ... truncated ...
```
