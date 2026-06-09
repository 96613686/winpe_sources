# AppxValidatePackagesWithOptions

- ea: `0x180025b40`
- end: `0x180025f4d`
- name: `AppxValidatePackagesWithOptions`
- size: `1037`
- prototype: `__int64 __fastcall(__int64, int, __int64, DWORD, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18008e280`

## callees

- `0x18000b614`
- `0x180025b40`
- `0x180025f54`
- `0x180026264`
- `0x180026280`
- `0x18002d2c8`
- `0x180035d98`
- `0x180039990`
- `0x180051870`
- `0x1800522e8`
- `0x180066cb0`
- `0x180068d70`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x180025cd2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180025cd2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180025c92`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180025c92`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180025e00`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180025e5b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180025e00`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180025e5b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180025c28`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180025c28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025e19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025ef3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025e19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025ef3`
- `RPCRT4!RpcAsyncCancelCall` at `0x180025e3f`
- `RPCRT4!RpcAsyncCancelCall` at `0x180025e3f`
- `RPCRT4!RpcBindingFree` at `0x180025dce`
- `RPCRT4!RpcBindingFree` at `0x180025dce`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180025e6e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180025e86`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180025e6e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180025e86`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180025bef`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180025bef`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180025d44`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180025d44`
- `RPCRT4!RpcBindingUnbind` at `0x180025dc3`
- `RPCRT4!RpcBindingUnbind` at `0x180025dc3`

## pseudocode

```c
__int64 __fastcall AppxValidatePackagesWithOptions(__int64 a1, int a2, __int64 a3, DWORD a4, int a5)
{
  unsigned int v8; // eax
  signed int v9; // edi
  char *EventW; // rbx
  int v11; // eax
  DWORD v13; // eax
  signed int LastError; // eax
  RPC_STATUS v15; // eax
  bool v16; // sf
  RPC_STATUS v17; // eax
  signed int v18; // eax
  unsigned int v19; // ebx
  int Reply; // [rsp+54h] [rbp-114h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+58h] [rbp-110h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp-108h] BYREF
  RPC_BINDING_HANDLE *v23; // [rsp+68h] [rbp-100h] BYREF
  char v24; // [rsp+70h] [rbp-F8h]
  int v25; // [rsp+78h] [rbp-F0h]
  DWORD v26; // [rsp+80h] [rbp-E8h]
  __int64 v27; // [rsp+88h] [rbp-E0h]
  _QWORD v28[4]; // [rsp+90h] [rbp-D8h] BYREF
  _RPC_ASYNC_STATE pAsync; // [rsp+B0h] [rbp-B8h] BYREF
  void *retaddr; // [rsp+168h] [rbp+0h]

  v27 = a3;
  v28[1] = a1;
  v25 = a2;
  v28[2] = a3;
  v26 = a4;
  Reply = 0;
  Binding = 0;
  memset(&pAsync, 0, sizeof(pAsync));
  unknown_libname_1(&hObject);
  v28[0] = &Binding;
  sub_180039990(&v23, v28);
  v8 = RpcAsyncInitializeHandle(&pAsync, 0x70u);
  if ( v8 )
  {
    v9 = sub_180035D98(retaddr, 1268, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", v8);
    goto LABEL_9;
  }
  EventW = (char *)CreateEventW(0, 1, 0, 0);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    sub_180068D70(hObject);
  hObject = EventW;
  if ( (unsigned __int64)(EventW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    pAsync.UserInfo = 0;
    pAsync.NotificationType = RpcNotificationTypeEvent;
    pAsync.u.APC.NotificationRoutine = (PFN_RPCNOTIFICATION_ROUTINE)EventW;
    Binding = &qword_180153630;
    RtlAcquireSRWLockExclusive(&qword_180153640);
    v11 = sub_180025F54(qword_1800E7010);
    v9 = v11;
    if ( v11 < 0 )
      sub_18000B614(retaddr, 1285, "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp", (unsigned int)v11);
    RtlReleaseSRWLockExclusive(&qword_180153640);
    if ( v9 < 0 )
      goto LABEL_9;
    Ndr64AsyncClientCall((MIDL_STUBLESS_PROXY_INFO *)&stru_1800EACA0, 0, 0, &pAsync, Binding, a2, a1, v27, a5);
    v13 = WaitForSingleObject(EventW, a4);
    if ( v13 == 258 )
    {
      v9 = -2147024638;
    }
    else
    {
      if ( v13 == -1 )
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
      }
      if ( v9 >= 0 )
      {
        v17 = RpcAsyncCompleteCall(&pAsync, &Reply);
        v9 = v17;
        if ( v17 > 0 )
          v9 = (unsigned __int16)v17 | 0x80070000;
        if ( v9 >= 0 )
        {
          v9 = Reply;
          if ( Reply >= 0 )
            v9 = 0;
          else
            sub_18000B614(
              retaddr,
              1348,
              "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp",
              (unsigned int)Reply);
        }
        else
        {
          sub_18000B614(
            retaddr,
            1347,
            "onecore\\admin\\appmodel\\packagemanager\\client\\exports.cpp",
            (unsigned int)v9);
        }
        goto LABEL_9;
      }
    }
    v15 = RpcAsyncCancelCall(&pAsync, 1);
    v16 = v15 < 0;
    if ( v15 > 0 )
      v16 = 1;
    if ( !v16 )
      WaitForSingleObject(EventW, 0xFFFFFFFF);
    RpcAsyncCompleteCall(&pAsync, &Reply);
LABEL_9:
    if ( v24 )
    {
      if ( *v23 )
        sub_18002D2C8(v23);
    }
    sub_180026264(&hObject);
    return (unsigned int)v9;
  }
  v18 = GetLastError();
  v19 = v18;
  if ( v18 > 0 )
    v19 = (unsigned __int16)v18 | 0x80070000;
  if ( v24 && *v23 )
    sub_18002D2C8(v23);
  sub_180026264(&hObject);
  return v19;
}

```

## disassembly

```asm
0x180025b40  push    rbx
0x180025b42  push    rdi
0x180025b43  push    r12
0x180025b45  push    r13
0x180025b47  push    r14
0x180025b49  push    r15
0x180025b4b  sub     rsp, 138h
0x180025b52  mov     rax, cs:__security_cookie
0x180025b59  xor     rax, rsp
0x180025b5c  mov     [rsp+168h+var_48], rax
0x180025b64  mov     r15d, r9d
0x180025b67  mov     rax, r8
0x180025b6a  mov     [rsp+168h+var_E0], rax
0x180025b72  mov     r13d, edx
0x180025b75  mov     r12, rcx
0x180025b78  mov     [rsp+168h+var_D0], rcx
0x180025b80  mov     [rsp+168h+var_F0], edx
0x180025b84  mov     [rsp+168h+var_C8], rax
0x180025b8c  mov     [rsp+168h+var_E8], r9d
0x180025b94  mov     [rsp+168h+Reply], 0
0x180025b9c  mov     [rsp+168h+Binding], 0
0x180025ba5  mov     ebx, 70h ; 'p'
0x180025baa  mov     r8d, ebx; Size
0x180025bad  xor     edx, edx; Val
0x180025baf  lea     rcx, [rsp+168h+pAsync]; void *
0x180025bb7  call    memset
0x180025bbc  lea     rcx, [rsp+168h+hObject]
0x180025bc1  call    unknown_libname_1; Microsoft VisualC v7/14 64bit runtime
0x180025bc6  lea     rcx, [rsp+168h+Binding]
0x180025bcb  mov     [rsp+168h+var_D8], rcx
0x180025bd3  lea     rdx, [rsp+168h+var_D8]
0x180025bdb  lea     rcx, [rsp+168h+var_100]
0x180025be0  call    sub_180039990
0x180025be5  mov     edx, ebx; Size
0x180025be7  lea     rcx, [rsp+168h+pAsync]; pAsync
0x180025bef  call    cs:RpcAsyncInitializeHandle
0x180025bf5  test    eax, eax
0x180025bf7  jz      short loc_180025C1C
0x180025bf9  mov     rcx, [rsp+168h]
0x180025c01  mov     r9d, eax
0x180025c04  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x180025c0b  mov     edx, 4F4h
0x180025c10  call    sub_180035D98
0x180025c15  mov     edi, eax
0x180025c17  jmp     loc_180025CDC
0x180025c1c  xor     r9d, r9d; lpName
0x180025c1f  xor     r8d, r8d; bInitialState
0x180025c22  lea     edx, [r9+1]; bManualReset
0x180025c26  xor     ecx, ecx; lpEventAttributes
0x180025c28  call    cs:CreateEventW
0x180025c2e  mov     rbx, rax
0x180025c31  mov     rcx, [rsp+168h+hObject]; hObject
0x180025c36  lea     rax, [rcx-1]
0x180025c3a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180025c3e  ja      short loc_180025C45
0x180025c40  call    sub_180068D70
0x180025c45  mov     [rsp+168h+hObject], rbx
0x180025c4a  lea     rax, [rbx-1]
0x180025c4e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180025c52  ja      loc_180025EF3
0x180025c58  xor     r14b, r14b
0x180025c5b  mov     [rsp+168h+var_118], r14b
0x180025c60  mov     [rsp+168h+pAsync.UserInfo], 0
0x180025c6c  mov     [rsp+168h+pAsync.NotificationType], 1
0x180025c77  mov     qword ptr [rsp+168h+pAsync.u], rbx
0x180025c7f  lea     rax, qword_180153630
0x180025c86  mov     [rsp+168h+Binding], rax
0x180025c8b  lea     rcx, qword_180153640
0x180025c92  call    cs:RtlAcquireSRWLockExclusive
0x180025c98  lea     rdx, [rsp+168h+Binding]
0x180025c9d  lea     rcx, qword_1800E7010; IfSpec
0x180025ca4  call    sub_180025F54
0x180025ca9  mov     edi, eax
0x180025cab  mov     rcx, [rsp+168h]
0x180025cb3  test    eax, eax
0x180025cb5  jns     short loc_180025CCB
0x180025cb7  mov     r9d, eax
0x180025cba  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x180025cc1  mov     edx, 505h
0x180025cc6  call    sub_18000B614
0x180025ccb  lea     rcx, qword_180153640
0x180025cd2  call    cs:RtlReleaseSRWLockExclusive
0x180025cd8  test    edi, edi
0x180025cda  jns     short loc_180025D04
0x180025cdc  cmp     [rsp+168h+var_F8], 0
0x180025ce1  jz      short loc_180025CF3
0x180025ce3  mov     rcx, [rsp+168h+var_100]; Binding
0x180025ce8  cmp     qword ptr [rcx], 0
0x180025cec  jz      short loc_180025CF3
0x180025cee  call    sub_18002D2C8
0x180025cf3  lea     rcx, [rsp+168h+hObject]
0x180025cf8  call    sub_180026264
0x180025cfd  mov     eax, edi
0x180025cff  jmp     loc_180025F2B
0x180025d04  mov     eax, [rsp+168h+arg_20]
0x180025d0b  mov     [rsp+168h+var_128], eax
0x180025d0f  mov     rax, [rsp+168h+var_E0]
0x180025d17  mov     [rsp+168h+var_130], rax
0x180025d1c  mov     [rsp+168h+var_138], r12
0x180025d21  mov     [rsp+168h+var_140], r13d
0x180025d26  mov     rax, [rsp+168h+Binding]
0x180025d2b  mov     [rsp+168h+var_148], rax
0x180025d30  lea     r9, [rsp+168h+pAsync]
0x180025d38  xor     r8d, r8d; pReturnValue
0x180025d3b  xor     edx, edx; nProcNum
0x180025d3d  lea     rcx, stru_1800EACA0; pProxyInfo
0x180025d44  call    cs:Ndr64AsyncClientCall
0x180025d4a  jmp     short loc_180025D8A
0x180025d4c  mov     edi, eax
0x180025d4e  test    eax, eax
0x180025d50  jle     short loc_180025D5B
0x180025d52  movzx   edi, ax
0x180025d55  or      edi, 80070000h
0x180025d5b  mov     rbx, [rsp+168h+hObject]
0x180025d60  mov     r14b, [rsp+168h+var_118]
0x180025d65  mov     r12, [rsp+168h+var_D0]
0x180025d6d  mov     r13d, [rsp+168h+var_F0]
0x180025d72  mov     rax, [rsp+168h+var_C8]
0x180025d7a  mov     [rsp+168h+var_E0], rax
0x180025d82  mov     r15d, [rsp+168h+var_E8]
0x180025d8a  test    edi, edi
0x180025d8c  jns     short loc_180025DFA
0x180025d8e  lea     eax, [rdi+7FF8F94Bh]
0x180025d94  cmp     eax, 24h ; '$'
0x180025d97  ja      short loc_180025DA9
0x180025d99  mov     rcx, 1000000621h
0x180025da3  bt      rcx, rax
0x180025da7  jb      short loc_180025DB1
0x180025da9  cmp     edi, 80080008h
0x180025daf  jnz     short loc_180025DD9
0x180025db1  test    r14b, r14b
0x180025db4  jnz     short loc_180025DD9
0x180025db6  mov     r14b, 1
0x180025db9  mov     [rsp+168h+var_118], r14b
0x180025dbe  mov     rcx, [rsp+168h+Binding]; Binding
0x180025dc3  call    cs:RpcBindingUnbind
0x180025dc9  lea     rcx, [rsp+168h+Binding]; Binding
0x180025dce  call    cs:RpcBindingFree
0x180025dd4  jmp     loc_180025C7F
0x180025dd9  mov     rcx, [rsp+168h]
0x180025de1  mov     r9d, edi
0x180025de4  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x180025deb  mov     edx, 522h
0x180025df0  call    sub_180066CB0
0x180025df5  jmp     loc_180025CDC
0x180025dfa  mov     edx, r15d; dwMilliseconds
0x180025dfd  mov     rcx, rbx; hHandle
0x180025e00  call    cs:WaitForSingleObject
0x180025e06  cmp     eax, 102h
0x180025e0b  jnz     short loc_180025E14
0x180025e0d  mov     edi, 80070102h
0x180025e12  jmp     short loc_180025E32
0x180025e14  cmp     eax, 0FFFFFFFFh
0x180025e17  jnz     short loc_180025E2E
0x180025e19  call    cs:GetLastError
0x180025e1f  mov     edi, eax
0x180025e21  test    eax, eax
0x180025e23  jle     short loc_180025E2E
0x180025e25  movzx   edi, ax
0x180025e28  or      edi, 80070000h
0x180025e2e  test    edi, edi
0x180025e30  jns     short loc_180025E79
0x180025e32  mov     edx, 1; fAbort
0x180025e37  lea     rcx, [rsp+168h+pAsync]; pAsync
0x180025e3f  call    cs:RpcAsyncCancelCall
0x180025e45  test    eax, eax
0x180025e47  jle     short loc_180025E53
0x180025e49  movzx   eax, ax
0x180025e4c  or      eax, 80070000h
0x180025e51  test    eax, eax
0x180025e53  js      short loc_180025E61
0x180025e55  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180025e58  mov     rcx, rbx; hHandle
0x180025e5b  call    cs:WaitForSingleObject
0x180025e61  lea     rdx, [rsp+168h+Reply]; Reply
0x180025e66  lea     rcx, [rsp+168h+pAsync]; pAsync
0x180025e6e  call    cs:RpcAsyncCompleteCall
0x180025e74  jmp     loc_180025CDC
0x180025e79  lea     rdx, [rsp+168h+Reply]; Reply
0x180025e7e  lea     rcx, [rsp+168h+pAsync]; pAsync
0x180025e86  call    cs:RpcAsyncCompleteCall
0x180025e8c  mov     edi, eax
0x180025e8e  test    eax, eax
0x180025e90  jle     short loc_180025E9B
0x180025e92  movzx   edi, ax
0x180025e95  or      edi, 80070000h
0x180025e9b  test    edi, edi
0x180025e9d  jns     short loc_180025EC3
0x180025e9f  mov     rcx, [rsp+168h]
0x180025ea7  mov     r9d, edi
0x180025eaa  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x180025eb1  mov     edx, 543h
0x180025eb6  call    sub_18000B614
0x180025ebb  test    edi, edi
0x180025ebd  js      loc_180025CDC
0x180025ec3  mov     edi, [rsp+168h+Reply]
0x180025ec7  test    edi, edi
0x180025ec9  jns     short loc_180025EEC
0x180025ecb  mov     rcx, [rsp+168h]
0x180025ed3  mov     r9d, edi
0x180025ed6  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\packagemanage"...
0x180025edd  mov     edx, 544h
0x180025ee2  call    sub_18000B614
0x180025ee7  jmp     loc_180025CDC
0x180025eec  xor     edi, edi
0x180025eee  jmp     loc_180025CDC
0x180025ef3  call    cs:GetLastError
0x180025ef9  mov     ebx, eax
0x180025efb  test    eax, eax
0x180025efd  jle     short loc_180025F08
0x180025eff  movzx   ebx, ax
0x180025f02  or      ebx, 80070000h
0x180025f08  cmp     [rsp+168h+var_F8], 0
0x180025f0d  jz      short loc_180025F1F
0x180025f0f  mov     rcx, [rsp+168h+var_100]; Binding
0x180025f14  cmp     qword ptr [rcx], 0
0x180025f18  jz      short loc_180025F1F
0x180025f1a  call    sub_18002D2C8
0x180025f1f  lea     rcx, [rsp+168h+hObject]
0x180025f24  call    sub_180026264
0x180025f29  mov     eax, ebx
0x180025f2b  mov     rcx, [rsp+168h+var_48]
0x180025f33  xor     rcx, rsp; StackCookie
0x180025f36  call    __security_check_cookie
0x180025f3b  add     rsp, 138h
0x180025f42  pop     r15
0x180025f44  pop     r14
0x180025f46  pop     r13
0x180025f48  pop     r12
0x180025f4a  pop     rdi
0x180025f4b  pop     rbx
0x180025f4c  retn
```
