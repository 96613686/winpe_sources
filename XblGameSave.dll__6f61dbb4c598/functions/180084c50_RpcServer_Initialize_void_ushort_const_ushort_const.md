# RpcServer::Initialize(void *,ushort const *,ushort const *)

- ea: `0x180084c50`
- end: `0x180084dab`
- name: `?Initialize@RpcServer@@QEAAJPEAXPEBG1@Z`
- size: `347`
- prototype: `__int64 __fastcall(RpcServer *__hidden this, void *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180011734`

## callees

- `0x18000aba4`
- `0x180084c24`
- `0x180084c50`
- `0x180084db4`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180084c90`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180084c90`
- `RPCRT4!RpcBindingVectorFree` at `0x180084ceb`
- `RPCRT4!RpcBindingVectorFree` at `0x180084ceb`
- `RPCRT4!RpcServerInqBindings` at `0x180084cfa`
- `RPCRT4!RpcServerInqBindings` at `0x180084cfa`
- `RPCRT4!RpcServerRegisterIf3` at `0x180084d42`
- `RPCRT4!RpcServerRegisterIf3` at `0x180084d42`
- `RPCRT4!RpcEpRegisterW` at `0x180084d67`
- `RPCRT4!RpcEpRegisterW` at `0x180084d67`
- `RPCRT4!RpcServerUseProtseqW` at `0x180084cbf`
- `RPCRT4!RpcServerUseProtseqW` at `0x180084cbf`

## string_xrefs

- `0x180084d5a`: `XblGameSaveService`
- `0x180084c9e`: `onecoreuap\xbox\connectedstorage\common\rpcserver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall RpcServer::Initialize(
        RpcServer *this,
        void *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  const char *v5; // r9
  int LastError; // eax
  unsigned int v7; // eax
  unsigned int v8; // r8d
  __int64 v9; // rdx
  unsigned int v10; // ebx
  unsigned int v12; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp+20h] BYREF
  RPC_BINDING_VECTOR *BindingVector; // [rsp+68h] [rbp+28h] BYREF

  BindingVector = 0;
  SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;;GA;;;SY)(A;;GA;;;BA)(A;;GR;;;RC)(A;;GR;;;WD)(A;;GR;;;AC)",
         1u,
         &SecurityDescriptor,
         0) )
  {
    v7 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, SecurityDescriptor);
    if ( v7 )
    {
      v9 = 50;
    }
    else
    {
      v7 = RpcServerInqBindings(&BindingVector);
      if ( v7 )
      {
        v9 = 58;
      }
      else
      {
        v12 = 1234;
        v7 = RpcServerRegisterIf3(qword_180093460, 0, 0, 41);
        if ( v7 )
        {
          v9 = 76;
        }
        else
        {
          v7 = RpcEpRegisterW(qword_180093460, BindingVector, 0, (RPC_WSTR)L"XblGameSaveService");
          if ( !v7 )
          {
            *((_QWORD *)this + 1) = BindingVector;
            *(_QWORD *)this = qword_180093460;
            v10 = 0;
            BindingVector = 0;
            goto LABEL_15;
          }
          v9 = 85;
        }
      }
    }
    LastError = wil::details::in1diag3::Return_Win32(retaddr, (void *)v9, v8, (const char *)v7, v12);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x29,
                  (unsigned int)"onecoreuap\\xbox\\connectedstorage\\common\\rpcserver.cpp",
                  v5);
  }
  v10 = LastError;
  if ( BindingVector )
    RpcBindingVectorFree(&BindingVector);
LABEL_15:
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&SecurityDescriptor);
  return v10;
}

```

## disassembly

```asm
0x180084c50  mov     rax, rsp
0x180084c53  mov     [rax+8], rbx
0x180084c57  mov     [rax+10h], rsi
0x180084c5b  mov     [rax+20h], r9
0x180084c5f  mov     [rax+18h], r8
0x180084c63  push    rbp
0x180084c64  mov     rbp, rsp
0x180084c67  sub     rsp, 40h
0x180084c6b  xor     r9d, r9d; SecurityDescriptorSize
0x180084c6e  mov     [rbp+BindingVector], 0
0x180084c76  mov     rbx, rcx
0x180084c79  mov     [rbp+SecurityDescriptor], 0
0x180084c81  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180084c85  lea     rcx, aDAGaSyAGaBaAGr; "D:(A;;GA;;;SY)(A;;GA;;;BA)(A;;GR;;;RC)("...
0x180084c8c  lea     edx, [r9+1]; StringSDRevision
0x180084c90  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180084c96  test    eax, eax
0x180084c98  jnz     short loc_180084CAF
0x180084c9a  mov     rcx, [rbp+8]; this
0x180084c9e  lea     r8, aOnecoreuapXbox; "onecoreuap\\xbox\\connectedstorage\\com"...
0x180084ca5  lea     edx, [rax+29h]; void *
0x180084ca8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180084cad  jmp     short loc_180084CDA
0x180084caf  mov     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180084cb3  lea     rcx, Protseq; "ncalrpc"
0x180084cba  mov     edx, 0Ah; MaxCalls
0x180084cbf  call    cs:__imp_RpcServerUseProtseqW
0x180084cc5  test    eax, eax
0x180084cc7  jz      short loc_180084CF6
0x180084cc9  mov     edx, 32h ; '2'; void *
0x180084cce  mov     rcx, [rbp+8]; this
0x180084cd2  mov     r9d, eax; char *
0x180084cd5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180084cda  cmp     [rbp+BindingVector], 0
0x180084cdf  mov     ebx, eax
0x180084ce1  jz      loc_180084D90
0x180084ce7  lea     rcx, [rbp+BindingVector]; BindingVector
0x180084ceb  call    cs:__imp_RpcBindingVectorFree
0x180084cf1  jmp     loc_180084D90
0x180084cf6  lea     rcx, [rbp+BindingVector]; BindingVector
0x180084cfa  call    cs:__imp_RpcServerInqBindings
0x180084d00  test    eax, eax
0x180084d02  jz      short loc_180084D0B
0x180084d04  mov     edx, 3Ah ; ':'
0x180084d09  jmp     short loc_180084CCE
0x180084d0b  mov     rax, [rbp+SecurityDescriptor]
0x180084d0f  lea     rsi, qword_180093460
0x180084d16  mov     [rsp+40h+var_8], rax
0x180084d1b  mov     r9d, 29h ; ')'
0x180084d21  mov     [rsp+40h+var_10], 0
0x180084d2a  xor     r8d, r8d
0x180084d2d  mov     [rsp+40h+var_18], 0FFFFFFFFh
0x180084d35  xor     edx, edx
0x180084d37  mov     rcx, rsi
0x180084d3a  mov     [rsp+40h+var_20], 4D2h
0x180084d42  call    cs:__imp_RpcServerRegisterIf3
0x180084d48  test    eax, eax
0x180084d4a  jz      short loc_180084D56
0x180084d4c  mov     edx, 4Ch ; 'L'
0x180084d51  jmp     loc_180084CCE
0x180084d56  mov     rdx, [rbp+BindingVector]; BindingVector
0x180084d5a  lea     r9, Annotation; "XblGameSaveService"
0x180084d61  xor     r8d, r8d; UuidVector
0x180084d64  mov     rcx, rsi; IfSpec
0x180084d67  call    cs:__imp_RpcEpRegisterW
0x180084d6d  test    eax, eax
0x180084d6f  jz      short loc_180084D7B
0x180084d71  mov     edx, 55h ; 'U'
0x180084d76  jmp     loc_180084CCE
0x180084d7b  mov     rax, [rbp+BindingVector]
0x180084d7f  mov     [rbx+8], rax
0x180084d83  mov     [rbx], rsi
0x180084d86  xor     ebx, ebx
0x180084d88  mov     [rbp+BindingVector], 0
0x180084d90  lea     rcx, [rbp+SecurityDescriptor]
0x180084d94  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180084d99  mov     rsi, [rsp+40h+arg_8]
0x180084d9e  mov     eax, ebx
0x180084da0  mov     rbx, [rsp+40h+arg_0]
0x180084da5  add     rsp, 40h
0x180084da9  pop     rbp
0x180084daa  retn
```
