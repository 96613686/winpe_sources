# BipCreateRpcBinding

- ea: `0x140031128`
- end: `0x140031268`
- name: `BipCreateRpcBinding`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400310a8`

## callees

- `0x140031128`
- `0x140077fa0`

## import_xrefs

- `msrpc!RpcBindingCreateW` at `0x1400311eb`
- `msrpc!RpcBindingCreateW` at `0x1400311eb`
- `msrpc!RpcBindingFree` at `0x14003125a`
- `msrpc!RpcBindingFree` at `0x14003125a`
- `msrpc!RpcBindingBind` at `0x14003120a`
- `msrpc!RpcBindingBind` at `0x14003120a`

## pseudocode

```c
__int64 __fastcall BipCreateRpcBinding(RPC_BINDING_HANDLE *a1)
{
  RPC_STATUS v2; // ebx
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-69h] BYREF
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+28h] [rbp-61h] BYREF
  _DWORD v6[4]; // [rsp+50h] [rbp-39h] BYREF
  __int128 v7; // [rsp+60h] [rbp-29h]
  _DWORD *v8; // [rsp+70h] [rbp-19h]
  _DWORD v9[4]; // [rsp+78h] [rbp-11h] BYREF
  RPC_BINDING_HANDLE_OPTIONS_V1 Options; // [rsp+88h] [rbp-1h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+98h] [rbp+Fh] BYREF

  v9[0] = 257;
  *(_QWORD *)(&Security.Version + 1) = 0;
  HIDWORD(Security.ServerPrincName) = 0;
  Security.AuthIdentity = 0;
  v9[1] = 83886080;
  v9[2] = 18;
  memset(&Template, 0, sizeof(Template));
  Template.Version = 1;
  Options.Version = 1;
  Options.Flags = 1;
  Template.ProtocolSequence = 3;
  v6[0] = 3;
  v6[3] = 3;
  v8 = v9;
  v6[1] = 1;
  v6[2] = 1;
  Security.Version = 1;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v6;
  Binding = 0;
  *(_QWORD *)&Options.ComTimeout = 5;
  Security.AuthnLevel = 6;
  v7 = 0;
  Security.AuthnSvc = 20;
  v2 = RpcBindingCreateW(&Template, &Security, &Options, &Binding);
  if ( v2 || (v2 = RpcBindingBind(0, Binding, qword_14007F000)) != 0 )
  {
    if ( v2 < 0 && Binding )
      RpcBindingFree(&Binding);
  }
  else
  {
    v2 = 0;
    *a1 = Binding;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140031128  mov     [rsp-8+arg_8], rbx
0x14003112d  mov     [rsp-8+arg_10], rdi
0x140031132  push    rbp
0x140031133  lea     rbp, [rsp-57h]
0x140031138  sub     rsp, 0E0h
0x14003113f  mov     rax, cs:__security_cookie
0x140031146  xor     rax, rsp
0x140031149  mov     [rbp+57h+var_10], rax
0x14003114d  xor     eax, eax
0x14003114f  mov     [rbp+57h+var_68], 101h
0x140031156  xorps   xmm0, xmm0
0x140031159  mov     qword ptr [rbp+57h+Template.ObjectUuid.Data4], rax
0x14003115d  mov     qword ptr [rbp+57h+Security+4], rax
0x140031161  lea     r9, [rbp+57h+Binding]; Binding
0x140031165  mov     dword ptr [rbp+57h+Security.ServerPrincName+4], eax
0x140031168  lea     r8, [rbp+57h+Options]; Options
0x14003116c  mov     [rbp+57h+Security.AuthIdentity], rax
0x140031170  lea     rdx, [rbp+57h+Security]; Security
0x140031174  mov     rdi, rcx
0x140031177  mov     [rbp+57h+var_64], 5000000h
0x14003117e  mov     ecx, 1
0x140031183  mov     [rbp+57h+var_60], 12h
0x14003118a  movups  xmmword ptr [rbp+57h+Template.Version], xmm0
0x14003118e  mov     [rbp+57h+Template.Version], ecx
0x140031191  mov     [rbp+57h+Options.Version], ecx
0x140031194  lea     eax, [rcx+2]
0x140031197  mov     [rbp+57h+Options.Flags], ecx
0x14003119a  mov     [rbp+57h+Template.ProtocolSequence], eax
0x14003119d  mov     [rbp+57h+var_90], eax
0x1400311a0  mov     [rbp+57h+var_84], eax
0x1400311a3  lea     rax, [rbp+57h+var_68]
0x1400311a7  mov     [rbp+57h+var_70], rax
0x1400311ab  lea     rax, [rbp+57h+var_90]
0x1400311af  mov     [rbp+57h+var_8C], ecx
0x1400311b2  mov     [rbp+57h+var_88], ecx
0x1400311b5  mov     [rbp+57h+Security.Version], ecx
0x1400311b8  lea     rcx, [rbp+57h+Template]; Template
0x1400311bc  mov     [rbp+57h+Security.SecurityQos], rax
0x1400311c0  mov     [rbp+57h+Binding], 0
0x1400311c8  movups  xmmword ptr [rbp+57h+Template.NetworkAddress], xmm0
0x1400311cc  mov     qword ptr [rbp+57h+Options.ComTimeout], 5
0x1400311d4  movups  xmmword ptr [rbp+57h+Template.u1], xmm0
0x1400311d8  mov     [rbp+57h+Security.AuthnLevel], 6
0x1400311df  movdqu  [rbp+57h+var_80], xmm0
0x1400311e4  mov     [rbp+57h+Security.AuthnSvc], 14h
0x1400311eb  call    cs:__imp_RpcBindingCreateW
0x1400311f2  nop     dword ptr [rax+rax+00h]
0x1400311f7  mov     ebx, eax
0x1400311f9  test    eax, eax
0x1400311fb  jnz     short loc_14003121C
0x1400311fd  mov     rdx, [rbp+57h+Binding]; Binding
0x140031201  lea     r8, qword_14007F000; IfSpec
0x140031208  xor     ecx, ecx; pAsync
0x14003120a  call    cs:__imp_RpcBindingBind
0x140031211  nop     dword ptr [rax+rax+00h]
0x140031216  mov     ebx, eax
0x140031218  test    eax, eax
0x14003121a  jz      short loc_140031244
0x14003121c  test    ebx, ebx
0x14003121e  js      short loc_14003124F
0x140031220  mov     eax, ebx
0x140031222  mov     rcx, [rbp+57h+var_10]
0x140031226  xor     rcx, rsp; StackCookie
0x140031229  call    __security_check_cookie
0x14003122e  lea     r11, [rsp+0E0h+var_s0]
0x140031236  mov     rbx, [r11+18h]
0x14003123a  mov     rdi, [r11+20h]
0x14003123e  mov     rsp, r11
0x140031241  pop     rbp
0x140031242  retn
0x140031244  mov     rcx, [rbp+57h+Binding]
0x140031248  xor     ebx, ebx
0x14003124a  mov     [rdi], rcx
0x14003124d  jmp     short loc_140031220
0x14003124f  cmp     [rbp+57h+Binding], 0
0x140031254  jz      short loc_140031220
0x140031256  lea     rcx, [rbp+57h+Binding]; Binding
0x14003125a  call    cs:__imp_RpcBindingFree
0x140031261  nop     dword ptr [rax+rax+00h]
0x140031266  jmp     short loc_140031220
```
