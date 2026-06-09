# Microsoft::Diagnostics::UtcDecoderHostApiServer::RegisterInterface(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,void *)

- ea: `0x140011ea4`
- end: `0x1400120dd`
- name: `?RegisterInterface@UtcDecoderHostApiServer@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAX@Z`
- size: `569`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400110a4`

## callees

- `0x140001008`
- `0x140008660`
- `0x14000a840`
- `0x14000c434`
- `0x14000ebb4`
- `0x140011ea4`
- `0x1400120e4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140011f2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400120b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140011f2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400120b8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140011f02`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140011f02`
- `RPCRT4!RpcBindingVectorFree` at `0x140011ff0`
- `RPCRT4!RpcBindingVectorFree` at `0x1400120a8`
- `RPCRT4!RpcBindingVectorFree` at `0x140011ff0`
- `RPCRT4!RpcBindingVectorFree` at `0x1400120a8`
- `RPCRT4!RpcEpRegisterW` at `0x14001201f`
- `RPCRT4!RpcEpRegisterW` at `0x14001201f`
- `RPCRT4!RpcServerInqBindings` at `0x140011fae`
- `RPCRT4!RpcServerInqBindings` at `0x140011fae`
- `RPCRT4!RpcServerRegisterIf3` at `0x140011f6f`
- `RPCRT4!RpcServerRegisterIf3` at `0x140011f6f`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x140012003`
- `RPCRT4!RpcServerUnregisterIfEx` at `0x140012003`

## string_xrefs

- `0x140011f8f`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\server\utcdecoderhostapiserver.cpp`
- `0x140011fcf`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\server\utcdecoderhostapiserver.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::UtcDecoderHostApiServer::RegisterInterface(__int64 a1, __int64 a2)
{
  const WCHAR *v2; // rcx
  BOOL v3; // ebx
  unsigned int v4; // r8d
  const char *v5; // r9
  signed int v6; // ebx
  int v8; // eax
  RPC_STATUS v9; // eax
  __int64 v10; // rdx
  RPC_STATUS v11; // eax
  unsigned int v12; // [rsp+20h] [rbp-60h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-40h] BYREF
  RPC_BINDING_VECTOR *BindingVector; // [rsp+48h] [rbp-38h] BYREF
  RPC_BINDING_VECTOR *v15; // [rsp+50h] [rbp-30h] BYREF
  LPCWSTR StringSecurityDescriptor[2]; // [rsp+58h] [rbp-28h] BYREF
  __int128 v17; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  SecurityDescriptor = 0;
  *(_OWORD *)StringSecurityDescriptor = 0;
  v17 = 0;
  std::wstring::_Construct<1,wchar_t const *>(StringSecurityDescriptor, *(const void **)a2, *(_QWORD *)(a2 + 8));
  v2 = (const WCHAR *)StringSecurityDescriptor;
  if ( *((_QWORD *)&v17 + 1) > 7u )
    v2 = StringSecurityDescriptor[0];
  v3 = ConvertStringSecurityDescriptorToSecurityDescriptorW(v2, 1u, &SecurityDescriptor, 0);
  std::wstring::~wstring((char **)StringSecurityDescriptor);
  if ( !v3 )
  {
    v6 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x3B, v4, v5, v12);
LABEL_5:
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    return (unsigned int)v6;
  }
  v8 = RpcServerRegisterIf3(qword_14001B150, 0, 0, 41);
  v6 = v8;
  if ( v8 > 0 )
    v6 = (unsigned __int16)v8 | 0x80010000;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\server\\utcdecoderhostapiserver.cpp",
      (const char *)(unsigned int)v6,
      1);
    goto LABEL_5;
  }
  BindingVector = 0;
  v9 = RpcServerInqBindings(&BindingVector);
  v6 = v9;
  if ( v9 > 0 )
    v6 = (unsigned __int16)v9 | 0x80010000;
  if ( v6 < 0 )
  {
    v10 = 85;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\server\\utcdecoderhostapiserver.cpp",
      (const char *)(unsigned int)v6,
      1);
    if ( BindingVector )
    {
      v15 = BindingVector;
      RpcBindingVectorFree(&v15);
    }
    RpcServerUnregisterIfEx(qword_14001B150, 0, 1);
    goto LABEL_5;
  }
  v11 = RpcEpRegisterW(qword_14001B150, BindingVector, 0, 0);
  v6 = v11;
  if ( v11 > 0 )
    v6 = (unsigned __int16)v11 | 0x80010000;
  if ( v6 < 0 )
  {
    v10 = 86;
    goto LABEL_16;
  }
  if ( (unsigned int)dword_140025000 > 4
    && (qword_140025010 & 0x2000) != 0
    && (qword_140025018 & 0x2000) == qword_140025018 )
  {
    tlgWriteTransfer_EventWriteTransfer(&dword_140025000, byte_140020E75, 0);
  }
  if ( BindingVector )
  {
    v15 = BindingVector;
    RpcBindingVectorFree(&v15);
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return 0;
}

```

## disassembly

```asm
0x140011ea4  mov     [rsp-8+arg_0], rbx
0x140011ea9  push    rbp
0x140011eaa  mov     rbp, rsp
0x140011ead  sub     rsp, 80h
0x140011eb4  mov     rax, cs:__security_cookie
0x140011ebb  xor     rax, rsp
0x140011ebe  mov     [rbp+var_8], rax
0x140011ec2  mov     [rbp+SecurityDescriptor], 0
0x140011eca  xorps   xmm0, xmm0
0x140011ecd  movups  xmmword ptr [rbp+StringSecurityDescriptor], xmm0
0x140011ed1  xorps   xmm1, xmm1
0x140011ed4  movdqu  [rbp+var_18], xmm1
0x140011ed9  mov     r8, [rdx+8]
0x140011edd  mov     rdx, [rdx]
0x140011ee0  lea     rcx, [rbp+StringSecurityDescriptor]
0x140011ee4  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140011ee9  lea     rcx, [rbp+StringSecurityDescriptor]
0x140011eed  cmp     qword ptr [rbp+var_18+8], 7
0x140011ef2  cmova   rcx, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x140011ef7  xor     r9d, r9d; SecurityDescriptorSize
0x140011efa  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140011efe  lea     edx, [r9+1]; StringSDRevision
0x140011f02  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140011f08  mov     ebx, eax
0x140011f0a  lea     rcx, [rbp+StringSecurityDescriptor]; void *
0x140011f0e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140011f13  test    ebx, ebx
0x140011f15  jnz     short loc_140011F3B
0x140011f17  mov     rcx, [rbp+8]; this
0x140011f1b  lea     edx, [rbx+3Bh]; void *
0x140011f1e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140011f23  mov     ebx, eax
0x140011f25  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x140011f29  test    rcx, rcx
0x140011f2c  jz      short loc_140011F34
0x140011f2e  call    cs:__imp_LocalFree
0x140011f34  mov     eax, ebx
0x140011f36  jmp     loc_1400120C0
0x140011f3b  mov     rax, [rbp+SecurityDescriptor]
0x140011f3f  mov     [rsp+80h+var_48], rax
0x140011f44  mov     [rsp+80h+var_50], 0
0x140011f4d  mov     dword ptr [rsp+80h+var_58], 0
0x140011f55  mov     [rsp+80h+var_60], 1; int
0x140011f5d  mov     r9d, 29h ; ')'
0x140011f63  xor     r8d, r8d
0x140011f66  xor     edx, edx
0x140011f68  lea     rcx, qword_14001B150
0x140011f6f  call    cs:__imp_RpcServerRegisterIf3
0x140011f75  mov     ebx, eax
0x140011f77  test    eax, eax
0x140011f79  jle     short loc_140011F84
0x140011f7b  movzx   ebx, ax
0x140011f7e  or      ebx, 80010000h
0x140011f84  test    ebx, ebx
0x140011f86  jns     short loc_140011FA2
0x140011f88  mov     rcx, [rbp+8]; this
0x140011f8c  mov     r9d, ebx; char *
0x140011f8f  lea     r8, aOnecoreBaseTel_2; "onecore\\base\\telemetry\\utc\\service"...
0x140011f96  mov     edx, 49h ; 'I'; void *
0x140011f9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011fa0  jmp     short loc_140011F25
0x140011fa2  mov     [rbp+BindingVector], 0
0x140011faa  lea     rcx, [rbp+BindingVector]; BindingVector
0x140011fae  call    cs:__imp_RpcServerInqBindings
0x140011fb4  mov     ebx, eax
0x140011fb6  test    eax, eax
0x140011fb8  jle     short loc_140011FC3
0x140011fba  movzx   ebx, ax
0x140011fbd  or      ebx, 80010000h
0x140011fc3  test    ebx, ebx
0x140011fc5  jns     short loc_14001200E
0x140011fc7  mov     edx, 55h ; 'U'; void *
0x140011fcc  mov     r9d, ebx; char *
0x140011fcf  lea     r8, aOnecoreBaseTel_2; "onecore\\base\\telemetry\\utc\\service"...
0x140011fd6  mov     rcx, [rbp+8]; this
0x140011fda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011fdf  mov     rax, [rbp+BindingVector]
0x140011fe3  test    rax, rax
0x140011fe6  jz      short loc_140011FF6
0x140011fe8  mov     [rbp+var_30], rax
0x140011fec  lea     rcx, [rbp+var_30]; BindingVector
0x140011ff0  call    cs:__imp_RpcBindingVectorFree
0x140011ff6  xor     edx, edx; MgrTypeUuid
0x140011ff8  lea     r8d, [rdx+1]; RundownContextHandles
0x140011ffc  lea     rcx, qword_14001B150; IfSpec
0x140012003  call    cs:__imp_RpcServerUnregisterIfEx
0x140012009  jmp     loc_140011F25
0x14001200e  xor     r9d, r9d; Annotation
0x140012011  xor     r8d, r8d; UuidVector
0x140012014  mov     rdx, [rbp+BindingVector]; BindingVector
0x140012018  lea     rcx, qword_14001B150; IfSpec
0x14001201f  call    cs:__imp_RpcEpRegisterW
0x140012025  mov     ebx, eax
0x140012027  test    eax, eax
0x140012029  jle     short loc_140012034
0x14001202b  movzx   ebx, ax
0x14001202e  or      ebx, 80010000h
0x140012034  test    ebx, ebx
0x140012036  jns     short loc_14001203F
0x140012038  mov     edx, 56h ; 'V'
0x14001203d  jmp     short loc_140011FCC
0x14001203f  mov     eax, cs:dword_140025000
0x140012045  cmp     eax, 4
0x140012048  jbe     short loc_140012097
0x14001204a  mov     rcx, cs:qword_140025018
0x140012051  mov     rax, cs:qword_140025010
0x140012058  mov     edx, 2000h
0x14001205d  test    rdx, rax
0x140012060  jz      short loc_140012097
0x140012062  mov     rax, rcx
0x140012065  and     rax, rdx
0x140012068  cmp     rax, rcx
0x14001206b  jnz     short loc_140012097
0x14001206d  lea     rax, [rbp+StringSecurityDescriptor]
0x140012071  mov     [rsp+80h+var_58], rax
0x140012076  mov     [rsp+80h+var_60], 2
0x14001207e  xor     r9d, r9d
0x140012081  xor     r8d, r8d
0x140012084  lea     rdx, byte_140020E75
0x14001208b  lea     rcx, dword_140025000
0x140012092  call    _tlgWriteTransfer_EventWriteTransfer
0x140012097  mov     rax, [rbp+BindingVector]
0x14001209b  test    rax, rax
0x14001209e  jz      short loc_1400120AF
0x1400120a0  mov     [rbp+var_30], rax
0x1400120a4  lea     rcx, [rbp+var_30]; BindingVector
0x1400120a8  call    cs:__imp_RpcBindingVectorFree
0x1400120ae  nop
0x1400120af  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x1400120b3  test    rcx, rcx
0x1400120b6  jz      short loc_1400120BE
0x1400120b8  call    cs:__imp_LocalFree
0x1400120be  xor     eax, eax
0x1400120c0  mov     rcx, [rbp+var_8]
0x1400120c4  xor     rcx, rsp; StackCookie
0x1400120c7  call    __security_check_cookie
0x1400120cc  mov     rbx, [rsp+80h+arg_0]
0x1400120d4  add     rsp, 80h
0x1400120db  pop     rbp
0x1400120dc  retn
```
