# HvsipRpcConnect

- ea: `0x1400ac844`
- end: `0x1400ac9c1`
- name: `HvsipRpcConnect`
- size: `381`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400ac6c0`
- `0x1400ac748`
- `0x1400ac7bc`

## callees

- `0x140077fa0`
- `0x1400ac844`

## import_xrefs

- `ntoskrnl!SeExports` at `0x1400ac8cb`
- `msrpc!RpcBindingCreateW` at `0x1400ac931`
- `msrpc!RpcBindingCreateW` at `0x1400ac931`
- `msrpc!RpcBindingFree` at `0x1400ac991`
- `msrpc!RpcBindingFree` at `0x1400ac991`
- `msrpc!RpcBindingBind` at `0x1400ac955`
- `msrpc!RpcBindingBind` at `0x1400ac955`

## pseudocode

```c
__int64 __fastcall HvsipRpcConnect(RPC_BINDING_HANDLE *a1)
{
  unsigned int v2; // ebx
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-B8h] BYREF
  unsigned int v5; // [rsp+28h] [rbp-B0h]
  _OWORD v6[2]; // [rsp+30h] [rbp-A8h] BYREF
  PSID SeNetworkServiceSid; // [rsp+50h] [rbp-88h]
  RPC_BINDING_HANDLE_SECURITY_V1_W v8; // [rsp+58h] [rbp-80h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W v9; // [rsp+80h] [rbp-58h] BYREF
  RPC_BINDING_HANDLE_OPTIONS_V1 v10; // [rsp+B8h] [rbp-20h] BYREF

  Binding = 0;
  memset(v6, 0, sizeof(v6));
  SeNetworkServiceSid = 0;
  v10 = 0;
  memset(&v9, 0, 24);
  memset(&v9.u1, 0, 24);
  memset(&v8, 0, sizeof(v8));
  *a1 = 0;
  v9.Version = 1;
  v9.ProtocolSequence = 3;
  v9.StringEndpoint = L"IHvsiKLrpcEp001";
  SeNetworkServiceSid = SeExports->SeNetworkServiceSid;
  *(_QWORD *)&v6[0] = 0x100000003LL;
  *((_QWORD *)&v6[0] + 1) = 0x300000001LL;
  v8.Version = 1;
  *(_QWORD *)&v8.AuthnLevel = 0x1400000006LL;
  v8.SecurityQos = (RPC_SECURITY_QOS *)v6;
  *(_QWORD *)&v10.Version = 0x100000001LL;
  v10.ComTimeout = 5;
  v2 = RpcBindingCreateW(&v9, &v8, &v10, &Binding);
  v5 = v2;
  if ( !v2 )
  {
    v2 = RpcBindingBind(0, Binding, qword_1400831D0);
    v5 = v2;
    if ( !v2 )
    {
      *a1 = Binding;
      Binding = 0;
    }
  }
  if ( Binding )
    RpcBindingFree(&Binding);
  return v2;
}

```

## disassembly

```asm
0x1400ac844  mov     r11, rsp
0x1400ac847  mov     [r11+10h], rbx
0x1400ac84b  push    rdi
0x1400ac84c  sub     rsp, 0D0h
0x1400ac853  mov     rax, cs:__security_cookie
0x1400ac85a  xor     rax, rsp
0x1400ac85d  mov     [rsp+0D8h+var_10], rax
0x1400ac865  mov     rdi, rcx
0x1400ac868  mov     [rsp+0D8h+Binding], 0
0x1400ac871  xorps   xmm0, xmm0
0x1400ac874  xor     eax, eax
0x1400ac876  movups  [rsp+0D8h+var_A8], xmm0
0x1400ac87b  movups  [rsp+0D8h+var_98], xmm0
0x1400ac880  mov     [rsp+0D8h+var_88], rax
0x1400ac885  movups  xmmword ptr [r11-20h], xmm0
0x1400ac88a  xorps   xmm1, xmm1
0x1400ac88d  movups  xmmword ptr [r11-58h], xmm1
0x1400ac892  movups  xmmword ptr [r11-48h], xmm1
0x1400ac897  movups  xmmword ptr [r11-38h], xmm1
0x1400ac89c  mov     [r11-28h], rax
0x1400ac8a0  movups  [rsp+0D8h+var_80], xmm0
0x1400ac8a5  movups  [rsp+0D8h+var_70], xmm0
0x1400ac8aa  mov     [r11-60h], rax
0x1400ac8ae  mov     [rcx], rax
0x1400ac8b1  lea     r8d, [rax+1]
0x1400ac8b5  mov     [r11-58h], r8d
0x1400ac8b9  lea     edx, [rax+3]
0x1400ac8bc  mov     [r11-50h], edx
0x1400ac8c0  lea     rax, aIhvsiklrpcep00; "IHvsiKLrpcEp001"
0x1400ac8c7  mov     [r11-40h], rax
0x1400ac8cb  mov     rax, cs:__imp_SeExports
0x1400ac8d2  mov     rcx, [rax]
0x1400ac8d5  mov     rax, [rcx+188h]
0x1400ac8dc  mov     [rsp+0D8h+var_88], rax
0x1400ac8e1  mov     dword ptr [rsp+0D8h+var_A8], edx
0x1400ac8e5  mov     dword ptr [rsp+0D8h+var_A8+4], r8d
0x1400ac8ea  mov     dword ptr [rsp+0D8h+var_A8+8], r8d
0x1400ac8ef  mov     dword ptr [rsp+0D8h+var_A8+0Ch], edx
0x1400ac8f3  mov     [r11-80h], r8d
0x1400ac8f7  mov     dword ptr [rsp+0D8h+var_70], 6
0x1400ac8ff  mov     dword ptr [rsp+0D8h+var_70+4], 14h
0x1400ac907  lea     rax, [rsp+0D8h+var_A8]
0x1400ac90c  mov     [r11-60h], rax
0x1400ac910  mov     [r11-20h], r8d
0x1400ac914  mov     [r11-1Ch], r8d
0x1400ac918  mov     dword ptr [r11-18h], 5
0x1400ac920  lea     r9, [rsp+0D8h+Binding]; Binding
0x1400ac925  lea     r8, [r11-20h]; Options
0x1400ac929  lea     rdx, [r11-80h]; Security
0x1400ac92d  lea     rcx, [r11-58h]; Template
0x1400ac931  call    cs:__imp_RpcBindingCreateW
0x1400ac938  nop     dword ptr [rax+rax+00h]
0x1400ac93d  mov     ebx, eax
0x1400ac93f  mov     [rsp+0D8h+var_B0], eax
0x1400ac943  test    eax, eax
0x1400ac945  jnz     short loc_1400AC984
0x1400ac947  lea     r8, qword_1400831D0; IfSpec
0x1400ac94e  mov     rdx, [rsp+0D8h+Binding]; Binding
0x1400ac953  xor     ecx, ecx; pAsync
0x1400ac955  call    cs:__imp_RpcBindingBind
0x1400ac95c  nop     dword ptr [rax+rax+00h]
0x1400ac961  mov     ebx, eax
0x1400ac963  mov     [rsp+0D8h+var_B0], eax
0x1400ac967  test    eax, eax
0x1400ac969  jnz     short loc_1400AC984
0x1400ac96b  mov     rax, [rsp+0D8h+Binding]
0x1400ac970  mov     [rdi], rax
0x1400ac973  mov     [rsp+0D8h+Binding], 0
0x1400ac97c  jmp     short loc_1400AC984
0x1400ac97e  mov     ebx, eax
0x1400ac980  mov     [rsp+0D8h+var_B0], eax
0x1400ac984  cmp     [rsp+0D8h+Binding], 0
0x1400ac98a  jz      short loc_1400AC99D
0x1400ac98c  lea     rcx, [rsp+0D8h+Binding]; Binding
0x1400ac991  call    cs:__imp_RpcBindingFree
0x1400ac998  nop     dword ptr [rax+rax+00h]
0x1400ac99d  mov     eax, ebx
0x1400ac99f  mov     rcx, [rsp+0D8h+var_10]
0x1400ac9a7  xor     rcx, rsp; StackCookie
0x1400ac9aa  call    __security_check_cookie
0x1400ac9af  mov     rbx, [rsp+0D8h+arg_8]
0x1400ac9b7  add     rsp, 0D0h
0x1400ac9be  pop     rdi
0x1400ac9bf  retn
0x1400addad  push    rbp
0x1400addaf  sub     rsp, 20h
0x1400addb3  mov     rbp, rdx
0x1400addb6  mov     rcx, [rcx]
0x1400addb9  mov     ecx, [rcx]; ExceptionCode
0x1400addbb  call    cs:__imp_I_RpcExceptionFilter
0x1400addc2  nop     dword ptr [rax+rax+00h]
0x1400addc7  nop
0x1400addc8  add     rsp, 20h
0x1400addcc  pop     rbp
0x1400addcd  retn
```
