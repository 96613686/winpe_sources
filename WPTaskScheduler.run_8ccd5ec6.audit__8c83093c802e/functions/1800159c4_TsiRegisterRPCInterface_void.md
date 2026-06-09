# TsiRegisterRPCInterface(void)

- ea: `0x1800159c4`
- end: `0x180015aff`
- name: `?TsiRegisterRPCInterface@@YAJXZ`
- size: `315`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180016120`

## callees

- `0x18000e970`
- `0x1800159c4`

## import_xrefs

- `RPCRT4!RpcServerRegisterIf3` at `0x180015ac2`
- `RPCRT4!RpcServerRegisterIf3` at `0x180015ac2`
- `RPCRT4!RpcServerUseProtseqW` at `0x180015a24`
- `RPCRT4!RpcServerUseProtseqW` at `0x180015a24`
- `RPCRT4!RpcEpRegisterW` at `0x180015ae4`
- `RPCRT4!RpcEpRegisterW` at `0x180015ae4`
- `RPCRT4!RpcServerInqBindings` at `0x180015a77`
- `RPCRT4!RpcServerInqBindings` at `0x180015a77`
- `RPCRT4!RpcBindingVectorFree` at `0x180015a48`
- `RPCRT4!RpcBindingVectorFree` at `0x180015a48`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800159f8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180015a0f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800159f8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180015a0f`

## pseudocode

```c
RPC_STATUS TsiRegisterRPCInterface(void)
{
  RPC_STATUS v0; // eax
  __int64 v1; // rcx
  signed int v2; // ebx
  bool v3; // cc
  RPC_STATUS result; // eax
  RPC_BINDING_VECTOR *BindingVector; // [rsp+50h] [rbp+8h] BYREF
  void *v6; // [rsp+58h] [rbp+10h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp+18h] BYREF

  v6 = 0;
  SecurityDescriptor = 0;
  BindingVector = 0;
  ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:P(A;;GR;;;WD)(A;;GR;;;S-1-15-2-1)", 1u, &v6, 0);
  ConvertStringSecurityDescriptorToSecurityDescriptorW(
    L"D:(A;;GRGWGX;;;SY)(A;;GRGWGX;;;LS)(A;;GR;;;NS)(A;;GR;;;IU)S:(ML;;NWNXNR;;;ME)",
    1u,
    &SecurityDescriptor,
    0);
  v0 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, v6);
  v2 = v0;
  v3 = v0 <= 0;
  if ( v0 )
    goto LABEL_2;
  result = RpcServerInqBindings(&BindingVector);
  if ( !result )
  {
    v0 = RpcServerRegisterIf3(qword_180023410, 0, 0, 41, 1234, 0, 0, SecurityDescriptor);
    v2 = v0;
    v3 = v0 <= 0;
    if ( !v0 )
    {
      v0 = RpcEpRegisterW(qword_180023410, BindingVector, 0, 0);
      if ( !v0 )
        goto LABEL_4;
      if ( v0 <= 0 )
      {
        v2 = v0;
        goto LABEL_4;
      }
      goto LABEL_3;
    }
LABEL_2:
    if ( v3 )
    {
LABEL_4:
      if ( BindingVector )
        RpcBindingVectorFree(&BindingVector);
      if ( v2 < 0 && (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 2) != 0 )
        McTemplateU0q_EventWriteTransfer(v1, RPCRegistrationError);
      return v2;
    }
LABEL_3:
    v2 = (unsigned __int16)v0 | 0x80070000;
    goto LABEL_4;
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800159c4  mov     rax, rsp
0x1800159c7  push    rbx
0x1800159c8  sub     rsp, 40h
0x1800159cc  xor     r9d, r9d; SecurityDescriptorSize
0x1800159cf  mov     qword ptr [rax+10h], 0
0x1800159d7  lea     r8, [rax+10h]; SecurityDescriptor
0x1800159db  mov     qword ptr [rax+18h], 0
0x1800159e3  lea     rcx, StringSecurityDescriptor; "D:P(A;;GR;;;WD)(A;;GR;;;S-1-15-2-1)"
0x1800159ea  mov     qword ptr [rax+8], 0
0x1800159f2  lea     ebx, [r9+1]
0x1800159f6  mov     edx, ebx; StringSDRevision
0x1800159f8  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800159fe  xor     r9d, r9d; SecurityDescriptorSize
0x180015a01  lea     r8, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x180015a06  mov     edx, ebx; StringSDRevision
0x180015a08  lea     rcx, aDAGrgwgxSyAGrg; "D:(A;;GRGWGX;;;SY)(A;;GRGWGX;;;LS)(A;;G"...
0x180015a0f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180015a15  mov     r8, [rsp+48h+arg_8]; SecurityDescriptor
0x180015a1a  lea     edx, [rbx+9]; MaxCalls
0x180015a1d  lea     rcx, Protseq; "ncalrpc"
0x180015a24  call    cs:__imp_RpcServerUseProtseqW
0x180015a2a  mov     ebx, eax
0x180015a2c  test    eax, eax
0x180015a2e  jz      short loc_180015A72
0x180015a30  jle     short loc_180015A3B
0x180015a32  movzx   ebx, ax
0x180015a35  or      ebx, 80070000h
0x180015a3b  cmp     [rsp+48h+BindingVector], 0
0x180015a41  jz      short loc_180015A4E
0x180015a43  lea     rcx, [rsp+48h+BindingVector]; BindingVector
0x180015a48  call    cs:__imp_RpcBindingVectorFree
0x180015a4e  test    ebx, ebx
0x180015a50  jns     short loc_180015A6A
0x180015a52  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 2
0x180015a59  jz      short loc_180015A6A
0x180015a5b  mov     r8d, ebx
0x180015a5e  lea     rdx, RPCRegistrationError
0x180015a65  call    McTemplateU0q_EventWriteTransfer
0x180015a6a  mov     eax, ebx
0x180015a6c  add     rsp, 40h
0x180015a70  pop     rbx
0x180015a71  retn
0x180015a72  lea     rcx, [rsp+48h+BindingVector]; BindingVector
0x180015a77  call    cs:__imp_RpcServerInqBindings
0x180015a7d  test    eax, eax
0x180015a7f  jz      short loc_180015A8D
0x180015a81  jle     short loc_180015A6C
0x180015a83  movzx   eax, ax
0x180015a86  or      eax, 80070000h
0x180015a8b  jmp     short loc_180015A6C
0x180015a8d  mov     rax, [rsp+48h+SecurityDescriptor]
0x180015a92  lea     rcx, qword_180023410
0x180015a99  mov     [rsp+48h+var_10], rax
0x180015a9e  mov     r9d, 29h ; ')'
0x180015aa4  mov     [rsp+48h+var_18], 0
0x180015aad  xor     r8d, r8d
0x180015ab0  mov     [rsp+48h+var_20], 0
0x180015ab8  xor     edx, edx
0x180015aba  mov     [rsp+48h+var_28], 4D2h
0x180015ac2  call    cs:__imp_RpcServerRegisterIf3
0x180015ac8  mov     ebx, eax
0x180015aca  test    eax, eax
0x180015acc  jnz     loc_180015A30
0x180015ad2  mov     rdx, [rsp+48h+BindingVector]; BindingVector
0x180015ad7  lea     rcx, qword_180023410; IfSpec
0x180015ade  xor     r9d, r9d; Annotation
0x180015ae1  xor     r8d, r8d; UuidVector
0x180015ae4  call    cs:__imp_RpcEpRegisterW
0x180015aea  test    eax, eax
0x180015aec  jz      loc_180015A3B
0x180015af2  jg      loc_180015A32
0x180015af8  mov     ebx, eax
0x180015afa  jmp     loc_180015A3B
```
