# HamGetApplicationInterruptiveUIState

- ea: `0x18000c0a0`
- end: `0x18000c331`
- name: `HamGetApplicationInterruptiveUIState`
- size: `657`
- prototype: `__int64 __fastcall(__int64, void *, int, bool *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000c0a0`
- `0x18001aec0`

## import_xrefs

- `ntdll!RtlValidSid` at `0x18000c0e7`
- `ntdll!RtlValidSid` at `0x18000c0e7`
- `ntdll!RtlLengthSid` at `0x18000c243`
- `ntdll!RtlLengthSid` at `0x18000c243`
- `RPCRT4!NdrClientCall3` at `0x18000c27f`
- `RPCRT4!NdrClientCall3` at `0x18000c27f`
- `RPCRT4!RpcBindingCreateW` at `0x18000c1f2`
- `RPCRT4!RpcBindingCreateW` at `0x18000c1f2`
- `RPCRT4!RpcBindingBind` at `0x18000c210`
- `RPCRT4!RpcBindingBind` at `0x18000c210`
- `RPCRT4!RpcBindingFree` at `0x18000c2c7`
- `RPCRT4!RpcBindingFree` at `0x18000c326`
- `RPCRT4!RpcBindingFree` at `0x18000c2c7`
- `RPCRT4!RpcBindingFree` at `0x18000c326`
- `RPCRT4!RpcExceptionFilter` at `0x18001b34e`
- `RPCRT4!RpcExceptionFilter` at `0x18001b34e`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000c295`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000c295`

## pseudocode

```c
__int64 __fastcall HamGetApplicationInterruptiveUIState(__int64 a1, void *a2, int a3, bool *a4)
{
  int v8; // esi
  RPC_STATUS v9; // eax
  signed int Pointer; // ebx
  RPC_STATUS v11; // eax
  ULONG v12; // eax
  CLIENT_CALL_RETURN v13; // rax
  _BYTE v15[8]; // [rsp+50h] [rbp-118h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+58h] [rbp-110h] BYREF
  int v17; // [rsp+60h] [rbp-108h]
  RPC_BINDING_HANDLE v18[2]; // [rsp+68h] [rbp-100h] BYREF
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+78h] [rbp-F0h] BYREF
  __int64 v20; // [rsp+A0h] [rbp-C8h] BYREF
  int v21; // [rsp+A8h] [rbp-C0h]
  int v22; // [rsp+ACh] [rbp-BCh]
  __int128 v23; // [rsp+B0h] [rbp-B8h]
  __int128 v24; // [rsp+C0h] [rbp-A8h]
  __int64 v25; // [rsp+D0h] [rbp-98h]
  RPC_BINDING_HANDLE_OPTIONS_V1 Options; // [rsp+D8h] [rbp-90h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+E8h] [rbp-80h] BYREF

  v18[1] = a4;
  v18[0] = 0;
  v15[0] = 0;
  v8 = 0;
  if ( RtlValidSid(a2) )
  {
    Binding = 0;
    memset(&Template, 0, sizeof(Template));
    *(_QWORD *)&Options.ComTimeout = 5;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    *(_QWORD *)(&Security.Version + 1) = 0;
    HIDWORD(Security.ServerPrincName) = 0;
    Security.AuthIdentity = 0;
    Template.Version = 1;
    Template.ProtocolSequence = 3;
    Options.Version = 1;
    Options.Flags = 1;
    v20 = 5;
    v21 = 1;
    v22 = 3;
    Security.Version = 1;
    Security.AuthnLevel = 6;
    Security.AuthnSvc = 10;
    Security.SecurityQos = (RPC_SECURITY_QOS *)&v20;
    v9 = RpcBindingCreateW(&Template, &Security, &Options, &Binding);
    Pointer = v9;
    if ( v9 )
    {
      if ( v9 > 0 )
        Pointer = (unsigned __int16)v9 | 0xC0070000;
    }
    else
    {
      v11 = RpcBindingBind(0, Binding, qword_18001DC80);
      Pointer = v11;
      if ( v11 )
      {
        if ( v11 > 0 )
          Pointer = (unsigned __int16)v11 | 0xC0070000;
      }
      else
      {
        v18[0] = Binding;
        Binding = 0;
        Pointer = 0;
      }
    }
    if ( Binding )
      RpcBindingFree(&Binding);
    if ( Pointer >= 0 )
    {
      v12 = RtlLengthSid(a2);
      Binding = 0;
      v13.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x13u, 0, v18[0], a1, a2, v12, a3, v15).Pointer;
      Pointer = (signed int)v13.Pointer;
      Binding = (RPC_BINDING_HANDLE)v13.Simple;
      v17 = (int)v13.Pointer;
      v8 = 1;
      if ( SLODWORD(v13.Simple) >= 0 )
      {
        *a4 = v15[0] != 0;
        Pointer = 0;
      }
    }
  }
  else
  {
    Pointer = -1073741584;
  }
  if ( v8 )
    RpcBindingFree(v18);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x18000c0a0  push    rbx
0x18000c0a2  push    rsi
0x18000c0a3  push    rdi
0x18000c0a4  push    r12
0x18000c0a6  push    r13
0x18000c0a8  push    r14
0x18000c0aa  push    r15
0x18000c0ac  sub     rsp, 130h
0x18000c0b3  mov     rax, cs:__security_cookie
0x18000c0ba  xor     rax, rsp
0x18000c0bd  mov     [rsp+168h+var_48], rax
0x18000c0c5  mov     r15, r9
0x18000c0c8  mov     r13d, r8d
0x18000c0cb  mov     r14, rdx
0x18000c0ce  mov     r12, rcx
0x18000c0d1  mov     [rsp+168h+var_F8], r9
0x18000c0d6  xor     edi, edi
0x18000c0d8  mov     [rsp+168h+var_100], rdi
0x18000c0dd  mov     [rsp+168h+var_118], dil
0x18000c0e2  mov     esi, edi
0x18000c0e4  mov     rcx, rdx; Sid
0x18000c0e7  call    cs:__imp_RtlValidSid
0x18000c0ed  test    al, al
0x18000c0ef  jz      loc_18000C2F2
0x18000c0f5  mov     [rsp+168h+Binding], rdi
0x18000c0fa  xorps   xmm0, xmm0
0x18000c0fd  xor     eax, eax
0x18000c0ff  movups  xmmword ptr [rsp+168h+Template.Version], xmm0
0x18000c107  movups  xmmword ptr [rsp+168h+Template.NetworkAddress], xmm0
0x18000c10f  movups  xmmword ptr [rsp+168h+Template.u1], xmm0
0x18000c117  mov     qword ptr [rsp+168h+Template.ObjectUuid.Data4], rax
0x18000c11f  mov     qword ptr [rsp+168h+Options.ComTimeout], 5
0x18000c12b  movdqu  [rsp+168h+var_B8], xmm0
0x18000c134  xorps   xmm1, xmm1
0x18000c137  movdqu  [rsp+168h+var_A8], xmm1
0x18000c140  mov     [rsp+168h+var_98], rdi
0x18000c148  mov     qword ptr [rsp+168h+Security+4], rdi
0x18000c14d  mov     dword ptr [rsp+168h+Security.ServerPrincName+4], edi
0x18000c154  mov     [rsp+168h+Security.AuthIdentity], rdi
0x18000c15c  mov     [rsp+168h+Template.Version], 1
0x18000c167  mov     [rsp+168h+Template.ProtocolSequence], 3
0x18000c172  mov     [rsp+168h+Options.Version], 1
0x18000c17d  mov     [rsp+168h+Options.Flags], 1
0x18000c188  mov     [rsp+168h+var_C8], 5
0x18000c194  mov     [rsp+168h+var_C0], 1
0x18000c19f  mov     [rsp+168h+var_BC], 3
0x18000c1aa  mov     [rsp+168h+Security.Version], 1
0x18000c1b2  mov     [rsp+168h+Security.AuthnLevel], 6
0x18000c1bd  mov     [rsp+168h+Security.AuthnSvc], 0Ah
0x18000c1c8  lea     rax, [rsp+168h+var_C8]
0x18000c1d0  mov     [rsp+168h+Security.SecurityQos], rax
0x18000c1d8  lea     r9, [rsp+168h+Binding]; Binding
0x18000c1dd  lea     r8, [rsp+168h+Options]; Options
0x18000c1e5  lea     rdx, [rsp+168h+Security]; Security
0x18000c1ea  lea     rcx, [rsp+168h+Template]; Template
0x18000c1f2  call    cs:__imp_RpcBindingCreateW
0x18000c1f8  mov     ebx, eax
0x18000c1fa  test    eax, eax
0x18000c1fc  jnz     loc_18000C2F9
0x18000c202  lea     r8, qword_18001DC80; IfSpec
0x18000c209  mov     rdx, [rsp+168h+Binding]; Binding
0x18000c20e  xor     ecx, ecx; pAsync
0x18000c210  call    cs:__imp_RpcBindingBind
0x18000c216  mov     ebx, eax
0x18000c218  test    eax, eax
0x18000c21a  jnz     loc_18000C30D
0x18000c220  mov     rax, [rsp+168h+Binding]
0x18000c225  mov     [rsp+168h+var_100], rax
0x18000c22a  mov     [rsp+168h+Binding], rdi
0x18000c22f  mov     ebx, edi
0x18000c231  cmp     [rsp+168h+Binding], rsi
0x18000c236  jnz     loc_18000C321
0x18000c23c  test    ebx, ebx
0x18000c23e  js      short loc_18000C2BE
0x18000c240  mov     rcx, r14; Sid
0x18000c243  call    cs:__imp_RtlLengthSid
0x18000c249  mov     [rsp+168h+Binding], rdi
0x18000c24e  lea     rcx, [rsp+168h+var_118]
0x18000c253  mov     [rsp+168h+var_128], rcx
0x18000c258  mov     [rsp+168h+var_130], r13d
0x18000c25d  mov     [rsp+168h+var_138], eax
0x18000c261  mov     [rsp+168h+var_140], r14
0x18000c266  mov     [rsp+168h+var_148], r12
0x18000c26b  mov     r9, [rsp+168h+var_100]
0x18000c270  xor     r8d, r8d; pReturnValue
0x18000c273  mov     edx, 13h; nProcNum
0x18000c278  lea     rcx, pProxyInfo; pProxyInfo
0x18000c27f  call    cs:__imp_NdrClientCall3
0x18000c285  mov     rbx, rax
0x18000c288  mov     [rsp+168h+Binding], rax
0x18000c28d  mov     [rsp+168h+var_108], eax
0x18000c291  jmp     short loc_18000C2A8
0x18000c293  mov     ecx, eax; Status
0x18000c295  call    cs:__imp_I_RpcMapWin32Status
0x18000c29b  mov     ebx, eax
0x18000c29d  mov     [rsp+168h+var_108], eax
0x18000c2a1  xor     edi, edi
0x18000c2a3  mov     r15, [rsp+168h+var_F8]
0x18000c2a8  mov     esi, 1
0x18000c2ad  test    ebx, ebx
0x18000c2af  js      short loc_18000C2BE
0x18000c2b1  cmp     [rsp+168h+var_118], 0
0x18000c2b6  setnz   al
0x18000c2b9  mov     [r15], al
0x18000c2bc  mov     ebx, edi
0x18000c2be  test    esi, esi
0x18000c2c0  jz      short loc_18000C2CD
0x18000c2c2  lea     rcx, [rsp+168h+var_100]; Binding
0x18000c2c7  call    cs:__imp_RpcBindingFree
0x18000c2cd  mov     eax, ebx
0x18000c2cf  mov     rcx, [rsp+168h+var_48]
0x18000c2d7  xor     rcx, rsp; StackCookie
0x18000c2da  call    __security_check_cookie
0x18000c2df  add     rsp, 130h
0x18000c2e6  pop     r15
0x18000c2e8  pop     r14
0x18000c2ea  pop     r13
0x18000c2ec  pop     r12
0x18000c2ee  pop     rdi
0x18000c2ef  pop     rsi
0x18000c2f0  pop     rbx
0x18000c2f1  retn
0x18000c2f2  mov     ebx, 0C00000F0h
0x18000c2f7  jmp     short loc_18000C2BE
0x18000c2f9  jle     loc_18000C231
0x18000c2ff  movzx   ebx, ax
0x18000c302  or      ebx, 0C0070000h
0x18000c308  jmp     loc_18000C231
0x18000c30d  jle     loc_18000C231
0x18000c313  movzx   ebx, ax
0x18000c316  or      ebx, 0C0070000h
0x18000c31c  jmp     loc_18000C231
0x18000c321  lea     rcx, [rsp+168h+Binding]; Binding
0x18000c326  call    cs:__imp_RpcBindingFree
0x18000c32c  jmp     loc_18000C23C
0x18001b340  push    rbp
0x18001b342  sub     rsp, 50h
0x18001b346  mov     rbp, rdx
0x18001b349  mov     rcx, [rcx]
0x18001b34c  mov     ecx, [rcx]; ExceptionCode
0x18001b34e  call    cs:__imp_RpcExceptionFilter
0x18001b354  nop
0x18001b355  add     rsp, 50h
0x18001b359  pop     rbp
0x18001b35a  retn
```
