# RpcSecurityHelper::Initialize(ushort const *)

- ea: `0x180078d6c`
- end: `0x180078f9a`
- name: `?Initialize@RpcSecurityHelper@@QEAAJPEBG@Z`
- size: `558`
- prototype: `int(RpcSecurityHelper *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18004d180`

## callees

- `0x180005654`
- `0x1800056ac`
- `0x180006e94`
- `0x180007780`
- `0x18000bb40`
- `0x180078d6c`
- `0x180078fa0`
- `0x18008d9b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078ddc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078ddc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180078dd2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180078dd2`
- `RPCRT4!RpcServerUseProtseqW` at `0x180078f1c`
- `RPCRT4!RpcServerUseProtseqW` at `0x180078f1c`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180078ee5`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180078ee5`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x180078dab`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x180078dab`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180078ec4`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180078f43`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180078f78`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180078ec4`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180078f43`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180078f78`

## string_xrefs

- `0x180078da1`: `DefaultRpcAccess`

## pseudocode

```c
__int64 __fastcall RpcSecurityHelper::Initialize(RpcSecurityHelper *this, const unsigned __int16 *a2)
{
  _QWORD *v4; // rax
  PSECURITY_DESCRIPTOR *v5; // rax
  signed int LastError; // eax
  BackTraceCollection *v7; // rcx
  unsigned int v8; // ebx
  __int64 v9; // r8
  __int64 v10; // r9
  const unsigned __int16 *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r9
  __int64 v14; // rdx
  unsigned __int64 v15; // rsi
  unsigned __int16 *v16; // rax
  BackTraceCollection *v17; // rcx
  unsigned __int16 *v18; // rbx
  int v19; // eax
  BackTraceCollection *v20; // rcx
  unsigned int v21; // edi
  __int64 v22; // r8
  RPC_STATUS v24; // edi
  BackTraceCollection *v25; // rcx
  void *SecurityDescriptor; // [rsp+30h] [rbp-28h] BYREF

  SecurityDescriptor = 0;
  v4 = tlx::replace<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),0>(&SecurityDescriptor);
  if ( (unsigned int)QueryTransientObjectSecurityDescriptor(8, L"DefaultRpcAccess", v4) == -1073741772 )
  {
    v5 = (PSECURITY_DESCRIPTOR *)tlx::replace<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),0>(&SecurityDescriptor);
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;GR;;;IU)(A;;GR;;;AC)(A;;GR;;;AU)", 1u, v5, 0) )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      BackTraceCollection::Capture(v7, v8);
      v10 = 34;
      goto LABEL_29;
    }
  }
  if ( a2 )
  {
    v11 = a2;
    v12 = 0x7FFFFFFF;
    do
    {
      if ( !*v11 )
        break;
      ++v11;
      --v12;
    }
    while ( v12 );
    v8 = v12 == 0 ? 0x80070057 : 0;
    v13 = (0x7FFFFFFF - v12) & -(__int64)(v12 != 0);
    if ( !v12 )
    {
      BackTraceCollection::Capture(0, v8);
      v14 = 1;
      v10 = 43;
LABEL_30:
      Log_HREvent_21(v8, v14, v9, v10);
      if ( SecurityDescriptor )
        FreeTransientObjectSecurityDescriptor();
      return v8;
    }
    v15 = v13 + 1;
    v16 = (unsigned __int16 *)operator new[](saturated_mul(v13 + 1, 2u));
    v18 = v16;
    if ( !v16 )
    {
      v8 = -2147024882;
      BackTraceCollection::Capture(v17, -2147024882);
      v10 = 48;
LABEL_29:
      v14 = 0;
      goto LABEL_30;
    }
    v19 = StringCchCopyW(v16, v15, a2);
    v21 = v19;
    if ( v19 < 0 )
    {
      BackTraceCollection::Capture(v20, v19);
      Log_HREvent_21(v21, 1, v22, 50);
      operator delete(v18);
      if ( SecurityDescriptor )
        FreeTransientObjectSecurityDescriptor();
      return v21;
    }
    v24 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0xAu, v18, SecurityDescriptor);
    operator delete(v18);
  }
  else
  {
    v24 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, SecurityDescriptor);
    *(_DWORD *)this = 1;
  }
  v8 = 0;
  if ( v24 != 1740 )
    v8 = v24;
  if ( v8 )
  {
    if ( (int)v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    BackTraceCollection::Capture(v25, v8);
    v10 = 73;
    goto LABEL_29;
  }
  if ( SecurityDescriptor )
    FreeTransientObjectSecurityDescriptor();
  return 0;
}

```

## disassembly

```asm
0x180078d6c  mov     [rsp+arg_10], rbx
0x180078d71  push    rbp
0x180078d72  push    rsi
0x180078d73  push    rdi
0x180078d74  sub     rsp, 40h
0x180078d78  mov     rax, cs:__security_cookie
0x180078d7f  xor     rax, rsp
0x180078d82  mov     [rsp+58h+var_20], rax
0x180078d87  mov     rbx, rcx
0x180078d8a  xor     ebp, ebp
0x180078d8c  lea     rcx, [rsp+58h+SecurityDescriptor]
0x180078d91  mov     [rsp+58h+SecurityDescriptor], rbp
0x180078d96  mov     rdi, rdx
0x180078d99  call    ??$replace@PEAXP6AXPEAX@Z$1?FreeTransientObjectSecurityDescriptor@@YAX0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AXPEAX@Z$1?FreeTransientObjectSecurityDescriptor@@YAX0@Z$0A@@0@@Z; tlx::replace<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),0>(tlx::auto_xxx<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),0> &)
0x180078d9e  mov     r8, rax
0x180078da1  lea     rdx, aDefaultrpcacce; "DefaultRpcAccess"
0x180078da8  lea     ecx, [rbp+8]
0x180078dab  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x180078db1  cmp     eax, 0C0000034h
0x180078db6  jnz     short loc_180078E03
0x180078db8  lea     rcx, [rsp+58h+SecurityDescriptor]
0x180078dbd  call    ??$replace@PEAXP6AXPEAX@Z$1?FreeTransientObjectSecurityDescriptor@@YAX0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AXPEAX@Z$1?FreeTransientObjectSecurityDescriptor@@YAX0@Z$0A@@0@@Z; tlx::replace<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),0>(tlx::auto_xxx<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),0> &)
0x180078dc2  mov     r8, rax; SecurityDescriptor
0x180078dc5  lea     edx, [rbp+1]; StringSDRevision
0x180078dc8  xor     r9d, r9d; SecurityDescriptorSize
0x180078dcb  lea     rcx, StringSecurityDescriptor; "D:(A;;GR;;;IU)(A;;GR;;;AC)(A;;GR;;;AU)"
0x180078dd2  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180078dd8  test    eax, eax
0x180078dda  jnz     short loc_180078E03
0x180078ddc  call    cs:__imp_GetLastError
0x180078de2  mov     ebx, eax
0x180078de4  test    eax, eax
0x180078de6  jle     short loc_180078DF1
0x180078de8  movzx   ebx, ax
0x180078deb  or      ebx, 80070000h
0x180078df1  mov     edx, ebx; int
0x180078df3  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180078df8  mov     r9d, 22h ; '"'
0x180078dfe  jmp     loc_180078F65
0x180078e03  test    rdi, rdi
0x180078e06  jz      loc_180078F0B
0x180078e0c  mov     r8d, 7FFFFFFFh
0x180078e12  mov     rax, rdi
0x180078e15  mov     ecx, r8d
0x180078e18  cmp     [rax], bp
0x180078e1b  jz      short loc_180078E27
0x180078e1d  add     rax, 2
0x180078e21  sub     rcx, 1; this
0x180078e25  jnz     short loc_180078E18
0x180078e27  mov     rax, rcx
0x180078e2a  neg     rax
0x180078e2d  mov     rax, rcx
0x180078e30  sbb     ebx, ebx
0x180078e32  sub     r8, rcx
0x180078e35  not     ebx
0x180078e37  and     ebx, 80070057h
0x180078e3d  neg     rax
0x180078e40  sbb     r9, r9
0x180078e43  and     r9, r8
0x180078e46  test    rcx, rcx
0x180078e49  jnz     short loc_180078E60
0x180078e4b  mov     edx, ebx; int
0x180078e4d  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180078e52  mov     edx, 1
0x180078e57  lea     r9d, [rdx+2Ah]
0x180078e5b  jmp     loc_180078F67
0x180078e60  lea     rsi, [r9+1]
0x180078e64  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180078e6b  mov     eax, 2
0x180078e70  mul     rsi
0x180078e73  cmovb   rax, rcx
0x180078e77  mov     rcx, rax; unsigned __int64
0x180078e7a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180078e7f  mov     rbx, rax
0x180078e82  test    rax, rax
0x180078e85  jz      short loc_180078EF7
0x180078e87  mov     r8, rdi; unsigned __int16 *
0x180078e8a  mov     rdx, rsi; unsigned __int64
0x180078e8d  mov     rcx, rax; unsigned __int16 *
0x180078e90  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180078e95  mov     edi, eax
0x180078e97  test    eax, eax
0x180078e99  jns     short loc_180078ED1
0x180078e9b  mov     edx, eax; int
0x180078e9d  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180078ea2  mov     edx, 1
0x180078ea7  mov     ecx, edi
0x180078ea9  lea     r9d, [rdx+31h]
0x180078ead  call    Log_HREvent_21
0x180078eb2  mov     rcx, rbx; Block
0x180078eb5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180078eba  mov     rcx, [rsp+58h+SecurityDescriptor]
0x180078ebf  test    rcx, rcx
0x180078ec2  jz      short loc_180078ECA
0x180078ec4  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180078eca  mov     eax, edi
0x180078ecc  jmp     loc_180078F80
0x180078ed1  mov     r9, [rsp+58h+SecurityDescriptor]; SecurityDescriptor
0x180078ed6  lea     rcx, Protseq; "ncalrpc"
0x180078edd  mov     r8, rbx; Endpoint
0x180078ee0  mov     edx, 0Ah; MaxCalls
0x180078ee5  call    cs:__imp_RpcServerUseProtseqEpW
0x180078eeb  mov     rcx, rbx; Block
0x180078eee  mov     edi, eax
0x180078ef0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180078ef5  jmp     short loc_180078F2A
0x180078ef7  mov     ebx, 8007000Eh
0x180078efc  mov     edx, ebx; int
0x180078efe  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180078f03  mov     r9d, 30h ; '0'
0x180078f09  jmp     short loc_180078F65
0x180078f0b  mov     r8, [rsp+58h+SecurityDescriptor]; SecurityDescriptor
0x180078f10  lea     rcx, Protseq; "ncalrpc"
0x180078f17  mov     edx, 0Ah; MaxCalls
0x180078f1c  call    cs:__imp_RpcServerUseProtseqW
0x180078f22  mov     edi, eax
0x180078f24  mov     dword ptr [rbx], 1
0x180078f2a  cmp     edi, 6CCh
0x180078f30  mov     ebx, ebp
0x180078f32  cmovnz  ebx, edi
0x180078f35  test    ebx, ebx
0x180078f37  jnz     short loc_180078F4D
0x180078f39  mov     rcx, [rsp+58h+SecurityDescriptor]
0x180078f3e  test    rcx, rcx
0x180078f41  jz      short loc_180078F49
0x180078f43  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180078f49  xor     eax, eax
0x180078f4b  jmp     short loc_180078F80
0x180078f4d  jle     short loc_180078F58
0x180078f4f  movzx   ebx, bx
0x180078f52  or      ebx, 80070000h
0x180078f58  mov     edx, ebx; int
0x180078f5a  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180078f5f  mov     r9d, 49h ; 'I'
0x180078f65  xor     edx, edx
0x180078f67  mov     ecx, ebx
0x180078f69  call    Log_HREvent_21
0x180078f6e  mov     rcx, [rsp+58h+SecurityDescriptor]
0x180078f73  test    rcx, rcx
0x180078f76  jz      short loc_180078F7E
0x180078f78  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180078f7e  mov     eax, ebx
0x180078f80  mov     rcx, [rsp+58h+var_20]
0x180078f85  xor     rcx, rsp; StackCookie
0x180078f88  call    __security_check_cookie
0x180078f8d  mov     rbx, [rsp+58h+arg_10]
0x180078f92  add     rsp, 40h
0x180078f96  pop     rdi
0x180078f97  pop     rsi
0x180078f98  pop     rbp
0x180078f99  retn
```
