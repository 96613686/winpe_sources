# HandlerProc

- ea: `0x18000f930`
- end: `0x18000fac1`
- name: `HandlerProc`
- size: `401`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, char *lpContext)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800061a0`
- `0x180008b18`
- `0x180009090`
- `0x18000ee78`
- `0x18000f930`
- `0x180017a28`
- `0x180017bdc`
- `0x1800a4d70`
- `0x1800f9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000fa40`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000fa40`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000fa24`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000fa71`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000fa24`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000fa71`

## string_xrefs

- `0x18000f9bb`: `ServiceHandlerEx`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall HandlerProc(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, char *lpContext)
{
  DWORD v5; // ecx
  unsigned int v6; // ebx
  _QWORD *v7; // rdx
  char *v8; // rbx
  DWORD v10; // [rsp+28h] [rbp-41h] BYREF
  DWORD v11; // [rsp+30h] [rbp-39h] BYREF
  char *v12; // [rsp+38h] [rbp-31h] BYREF
  LPVOID v13; // [rsp+40h] [rbp-29h] BYREF
  _OWORD v14[2]; // [rsp+48h] [rbp-21h] BYREF
  _QWORD v15[7]; // [rsp+70h] [rbp+7h] BYREF
  _QWORD *v16; // [rsp+A8h] [rbp+3Fh]
  void *retaddr; // [rsp+C8h] [rbp+5Fh]

  v13 = lpEventData;
  v11 = dwEventType;
  v10 = dwControl;
  v12 = lpContext;
  v5 = dwControl - 1;
  if ( !v5 )
  {
    *((_DWORD *)lpContext + 15) = 3;
    *((_DWORD *)lpContext + 16) = 0;
    if ( !SetServiceStatus(*((SERVICE_STATUS_HANDLE *)lpContext + 6), (LPSERVICE_STATUS)lpContext + 2) )
      sub_180017A28(retaddr, 203);
    if ( !SetEvent(*((HANDLE *)lpContext + 11)) )
      sub_18000EE78(retaddr, 2561);
    v8 = v12;
    if ( !_InterlockedCompareExchange8(v12 + 176, 1, 0) )
    {
      *(_QWORD *)(v12 + 60) = 1;
      if ( !SetServiceStatus(*((SERVICE_STATUS_HANDLE *)v8 + 6), (LPSERVICE_STATUS)v8 + 2) )
        sub_180017A28(retaddr, 246);
      sub_180017BDC(v8);
    }
    return 0;
  }
  if ( v5 == 3 )
    return 0;
  v15[0] = &std::_Func_impl_no_alloc<_lambda_c4bb717dac9c97fefb83755ccf644241_,void,>::`vftable';
  v15[1] = &v12;
  v15[2] = &v10;
  v15[3] = &v11;
  v15[4] = &v13;
  v16 = v15;
  memset(v14, 0, sizeof(v14));
  sub_180008B18(v14, L"ServiceHandlerEx", 16);
  v6 = sub_1800A4D70(v14, v15);
  sub_180009090(v14);
  if ( v16 )
  {
    v7 = v15;
    LOBYTE(v7) = v16 != v15;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v16 + 32LL))(v16, v7);
  }
  return v6;
}

```

## disassembly

```asm
0x18000f930  mov     [rsp-8+arg_0], rbx
0x18000f935  push    rbp
0x18000f936  lea     rbp, [rsp-57h]
0x18000f93b  sub     rsp, 0C0h
0x18000f942  mov     rax, cs:__security_cookie
0x18000f949  xor     rax, rsp
0x18000f94c  mov     [rbp+57h+var_10], rax
0x18000f950  mov     rbx, r9
0x18000f953  mov     [rbp+57h+var_80], r8
0x18000f957  mov     [rbp+57h+var_90], edx
0x18000f95a  mov     [rbp+57h+var_98], ecx
0x18000f95d  mov     [rbp+57h+var_88], rbx
0x18000f961  sub     ecx, 1
0x18000f964  jz      loc_18000FA0D
0x18000f96a  cmp     ecx, 3
0x18000f96d  jz      loc_18000FA91
0x18000f973  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_c4bb717dac9c97fefb83755ccf644241_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_c4bb717dac9c97fefb83755ccf644241_,void,>::`vftable'
0x18000f97a  mov     [rbp+57h+var_50], rax
0x18000f97e  lea     rax, [rbp+57h+var_88]
0x18000f982  mov     [rbp+57h+var_48], rax
0x18000f986  lea     rax, [rbp+57h+var_98]
0x18000f98a  mov     [rbp+57h+var_40], rax
0x18000f98e  lea     rax, [rbp+57h+var_90]
0x18000f992  mov     [rbp+57h+var_38], rax
0x18000f996  lea     rax, [rbp+57h+var_80]
0x18000f99a  mov     [rbp+57h+var_30], rax
0x18000f99e  lea     rax, [rbp+57h+var_50]
0x18000f9a2  mov     [rbp+57h+var_18], rax
0x18000f9a6  xorps   xmm0, xmm0
0x18000f9a9  movups  [rbp+57h+var_78], xmm0
0x18000f9ad  xorps   xmm1, xmm1
0x18000f9b0  movdqu  [rbp+57h+var_68], xmm1
0x18000f9b5  mov     r8d, 10h
0x18000f9bb  lea     rdx, aServicehandler; "ServiceHandlerEx"
0x18000f9c2  lea     rcx, [rbp+57h+var_78]
0x18000f9c6  call    sub_180008B18
0x18000f9cb  nop
0x18000f9cc  lea     rdx, [rbp+57h+var_50]
0x18000f9d0  lea     rcx, [rbp+57h+var_78]
0x18000f9d4  call    sub_1800A4D70
0x18000f9d9  mov     ebx, eax
0x18000f9db  lea     rcx, [rbp+57h+var_78]
0x18000f9df  call    sub_180009090
0x18000f9e4  nop
0x18000f9e5  mov     rcx, [rbp+57h+var_18]
0x18000f9e9  test    rcx, rcx
0x18000f9ec  jz      loc_18000FA93
0x18000f9f2  mov     rax, [rcx]
0x18000f9f5  lea     rdx, [rbp+57h+var_50]
0x18000f9f9  cmp     rcx, rdx
0x18000f9fc  setnz   dl
0x18000f9ff  mov     rax, [rax+20h]
0x18000fa03  call    j__guard_dispatch_icall
0x18000fa08  jmp     loc_18000FA93
0x18000fa0d  lea     rdx, [r9+38h]; lpServiceStatus
0x18000fa11  mov     dword ptr [rdx+4], 3
0x18000fa18  mov     dword ptr [r9+40h], 0
0x18000fa20  mov     rcx, [r9+30h]; hServiceStatus
0x18000fa24  call    cs:SetServiceStatus
0x18000fa2a  test    eax, eax
0x18000fa2c  jnz     short loc_18000FA3C
0x18000fa2e  mov     rcx, [rbp+5Fh]
0x18000fa32  mov     edx, 0CBh
0x18000fa37  call    sub_180017A28
0x18000fa3c  mov     rcx, [rbx+58h]; hEvent
0x18000fa40  call    cs:SetEvent
0x18000fa46  test    eax, eax
0x18000fa48  jz      short loc_18000FAB2
0x18000fa4a  mov     rbx, [rbp+57h+var_88]
0x18000fa4e  mov     ecx, 1
0x18000fa53  xor     eax, eax
0x18000fa55  lock cmpxchg [rbx+0B0h], cl
0x18000fa5d  jnz     short loc_18000FA91
0x18000fa5f  lea     rdx, [rbx+38h]; lpServiceStatus
0x18000fa63  mov     [rdx+4], ecx
0x18000fa66  mov     dword ptr [rbx+40h], 0
0x18000fa6d  mov     rcx, [rbx+30h]; hServiceStatus
0x18000fa71  call    cs:SetServiceStatus
0x18000fa77  test    eax, eax
0x18000fa79  jnz     short loc_18000FA89
0x18000fa7b  mov     rcx, [rbp+5Fh]
0x18000fa7f  mov     edx, 0F6h
0x18000fa84  call    sub_180017A28
0x18000fa89  mov     rcx, rbx
0x18000fa8c  call    sub_180017BDC
0x18000fa91  xor     ebx, ebx
0x18000fa93  mov     eax, ebx
0x18000fa95  mov     rcx, [rbp+57h+var_10]
0x18000fa99  xor     rcx, rsp; StackCookie
0x18000fa9c  call    __security_check_cookie
0x18000faa1  mov     rbx, [rsp+0C0h+arg_0]
0x18000faa9  add     rsp, 0C0h
0x18000fab0  pop     rbp
0x18000fab1  retn
0x18000fab2  mov     rcx, [rbp+5Fh]
0x18000fab6  mov     edx, 0A01h
0x18000fabb  call    sub_18000EE78
```
