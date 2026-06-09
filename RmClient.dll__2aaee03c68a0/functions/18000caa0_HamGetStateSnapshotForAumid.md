# HamGetStateSnapshotForAumid

- ea: `0x18000caa0`
- end: `0x18000cd29`
- name: `HamGetStateSnapshotForAumid`
- size: `649`
- prototype: `__int64 __fastcall(__int64, void *, int, _BYTE *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000caa0`
- `0x18001aec0`

## import_xrefs

- `ntdll!RtlValidSid` at `0x18000cae3`
- `ntdll!RtlValidSid` at `0x18000cae3`
- `ntdll!RtlLengthSid` at `0x18000cc3f`
- `ntdll!RtlLengthSid` at `0x18000cc3f`
- `RPCRT4!NdrClientCall3` at `0x18000cc7b`
- `RPCRT4!NdrClientCall3` at `0x18000cc7b`
- `RPCRT4!RpcBindingCreateW` at `0x18000cbee`
- `RPCRT4!RpcBindingCreateW` at `0x18000cbee`
- `RPCRT4!RpcBindingBind` at `0x18000cc0c`
- `RPCRT4!RpcBindingBind` at `0x18000cc0c`
- `RPCRT4!RpcBindingFree` at `0x18000ccb5`
- `RPCRT4!RpcBindingFree` at `0x18000cd1e`
- `RPCRT4!RpcBindingFree` at `0x18000ccb5`
- `RPCRT4!RpcBindingFree` at `0x18000cd1e`
- `RPCRT4!RpcExceptionFilter` at `0x18001b37e`
- `RPCRT4!RpcExceptionFilter` at `0x18001b37e`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000cc91`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000cc91`

## pseudocode

```c
__int64 __fastcall HamGetStateSnapshotForAumid(__int64 a1, void *a2, int a3, _BYTE *a4)
{
  RPC_STATUS v8; // eax
  signed int Pointer; // ebx
  RPC_STATUS v10; // eax
  ULONG v11; // eax
  CLIENT_CALL_RETURN v12; // rax
  _BYTE v14[8]; // [rsp+50h] [rbp-118h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+58h] [rbp-110h] BYREF
  RPC_BINDING_HANDLE v16; // [rsp+60h] [rbp-108h] BYREF
  int v17; // [rsp+68h] [rbp-100h]
  _BYTE *v18; // [rsp+70h] [rbp-F8h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+78h] [rbp-F0h] BYREF
  __int64 v20; // [rsp+A0h] [rbp-C8h] BYREF
  int v21; // [rsp+A8h] [rbp-C0h]
  int v22; // [rsp+ACh] [rbp-BCh]
  __int128 v23; // [rsp+B0h] [rbp-B8h]
  __int128 v24; // [rsp+C0h] [rbp-A8h]
  __int64 v25; // [rsp+D0h] [rbp-98h]
  RPC_BINDING_HANDLE_OPTIONS_V1 Options; // [rsp+D8h] [rbp-90h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+E8h] [rbp-80h] BYREF

  v18 = a4;
  v14[0] = 0;
  v16 = 0;
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
    v8 = RpcBindingCreateW(&Template, &Security, &Options, &Binding);
    Pointer = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
        Pointer = (unsigned __int16)v8 | 0xC0070000;
    }
    else
    {
      v10 = RpcBindingBind(0, Binding, qword_18001DC80);
      Pointer = v10;
      if ( v10 )
      {
        if ( v10 > 0 )
          Pointer = (unsigned __int16)v10 | 0xC0070000;
      }
      else
      {
        v16 = Binding;
        Binding = 0;
        Pointer = 0;
      }
    }
    if ( Binding )
      RpcBindingFree(&Binding);
    if ( Pointer >= 0 )
    {
      v11 = RtlLengthSid(a2);
      Binding = 0;
      v12.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x16u, 0, v16, a1, a2, v11, a3, v14).Pointer;
      Pointer = (signed int)v12.Pointer;
      Binding = (RPC_BINDING_HANDLE)v12.Simple;
      v17 = (int)v12.Pointer;
      if ( SLODWORD(v12.Simple) >= 0 )
      {
        *a4 = v14[0];
        Pointer = 0;
      }
    }
  }
  else
  {
    Pointer = -1073741584;
  }
  if ( v16 )
    RpcBindingFree(&v16);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x18000caa0  push    rbx
0x18000caa2  push    rsi
0x18000caa3  push    rdi
0x18000caa4  push    r12
0x18000caa6  push    r14
0x18000caa8  push    r15
0x18000caaa  sub     rsp, 138h
0x18000cab1  mov     rax, cs:__security_cookie
0x18000cab8  xor     rax, rsp
0x18000cabb  mov     [rsp+168h+var_48], rax
0x18000cac3  mov     r14, r9
0x18000cac6  mov     r12d, r8d
0x18000cac9  mov     rsi, rdx
0x18000cacc  mov     r15, rcx
0x18000cacf  mov     [rsp+168h+var_F8], r9
0x18000cad4  mov     [rsp+168h+var_118], 0
0x18000cad9  xor     edi, edi
0x18000cadb  mov     [rsp+168h+var_108], rdi
0x18000cae0  mov     rcx, rdx; Sid
0x18000cae3  call    cs:__imp_RtlValidSid
0x18000cae9  test    al, al
0x18000caeb  jz      loc_18000CCEA
0x18000caf1  mov     [rsp+168h+Binding], rdi
0x18000caf6  xorps   xmm0, xmm0
0x18000caf9  xor     eax, eax
0x18000cafb  movups  xmmword ptr [rsp+168h+Template.Version], xmm0
0x18000cb03  movups  xmmword ptr [rsp+168h+Template.NetworkAddress], xmm0
0x18000cb0b  movups  xmmword ptr [rsp+168h+Template.u1], xmm0
0x18000cb13  mov     qword ptr [rsp+168h+Template.ObjectUuid.Data4], rax
0x18000cb1b  mov     qword ptr [rsp+168h+Options.ComTimeout], 5
0x18000cb27  movdqu  [rsp+168h+var_B8], xmm0
0x18000cb30  xorps   xmm1, xmm1
0x18000cb33  movdqu  [rsp+168h+var_A8], xmm1
0x18000cb3c  mov     [rsp+168h+var_98], rdi
0x18000cb44  mov     qword ptr [rsp+168h+Security+4], rdi
0x18000cb49  mov     dword ptr [rsp+168h+Security.ServerPrincName+4], edi
0x18000cb50  mov     [rsp+168h+Security.AuthIdentity], rdi
0x18000cb58  mov     [rsp+168h+Template.Version], 1
0x18000cb63  mov     [rsp+168h+Template.ProtocolSequence], 3
0x18000cb6e  mov     [rsp+168h+Options.Version], 1
0x18000cb79  mov     [rsp+168h+Options.Flags], 1
0x18000cb84  mov     [rsp+168h+var_C8], 5
0x18000cb90  mov     [rsp+168h+var_C0], 1
0x18000cb9b  mov     [rsp+168h+var_BC], 3
0x18000cba6  mov     [rsp+168h+Security.Version], 1
0x18000cbae  mov     [rsp+168h+Security.AuthnLevel], 6
0x18000cbb9  mov     [rsp+168h+Security.AuthnSvc], 0Ah
0x18000cbc4  lea     rax, [rsp+168h+var_C8]
0x18000cbcc  mov     [rsp+168h+Security.SecurityQos], rax
0x18000cbd4  lea     r9, [rsp+168h+Binding]; Binding
0x18000cbd9  lea     r8, [rsp+168h+Options]; Options
0x18000cbe1  lea     rdx, [rsp+168h+Security]; Security
0x18000cbe6  lea     rcx, [rsp+168h+Template]; Template
0x18000cbee  call    cs:__imp_RpcBindingCreateW
0x18000cbf4  mov     ebx, eax
0x18000cbf6  test    eax, eax
0x18000cbf8  jnz     loc_18000CCF1
0x18000cbfe  lea     r8, qword_18001DC80; IfSpec
0x18000cc05  mov     rdx, [rsp+168h+Binding]; Binding
0x18000cc0a  xor     ecx, ecx; pAsync
0x18000cc0c  call    cs:__imp_RpcBindingBind
0x18000cc12  mov     ebx, eax
0x18000cc14  test    eax, eax
0x18000cc16  jnz     loc_18000CD05
0x18000cc1c  mov     rax, [rsp+168h+Binding]
0x18000cc21  mov     [rsp+168h+var_108], rax
0x18000cc26  mov     [rsp+168h+Binding], rdi
0x18000cc2b  mov     ebx, edi
0x18000cc2d  cmp     [rsp+168h+Binding], rdi
0x18000cc32  jnz     loc_18000CD19
0x18000cc38  test    ebx, ebx
0x18000cc3a  js      short loc_18000CCA8
0x18000cc3c  mov     rcx, rsi; Sid
0x18000cc3f  call    cs:__imp_RtlLengthSid
0x18000cc45  mov     [rsp+168h+Binding], rdi
0x18000cc4a  lea     rcx, [rsp+168h+var_118]
0x18000cc4f  mov     [rsp+168h+var_128], rcx
0x18000cc54  mov     [rsp+168h+var_130], r12d
0x18000cc59  mov     [rsp+168h+var_138], eax
0x18000cc5d  mov     [rsp+168h+var_140], rsi
0x18000cc62  mov     [rsp+168h+var_148], r15
0x18000cc67  mov     r9, [rsp+168h+var_108]
0x18000cc6c  xor     r8d, r8d; pReturnValue
0x18000cc6f  mov     edx, 16h; nProcNum
0x18000cc74  lea     rcx, pProxyInfo; pProxyInfo
0x18000cc7b  call    cs:__imp_NdrClientCall3
0x18000cc81  mov     rbx, rax
0x18000cc84  mov     [rsp+168h+Binding], rax
0x18000cc89  mov     [rsp+168h+var_100], eax
0x18000cc8d  jmp     short loc_18000CCA4
0x18000cc8f  mov     ecx, eax; Status
0x18000cc91  call    cs:__imp_I_RpcMapWin32Status
0x18000cc97  mov     ebx, eax
0x18000cc99  mov     [rsp+168h+var_100], eax
0x18000cc9d  xor     edi, edi
0x18000cc9f  mov     r14, [rsp+168h+var_F8]
0x18000cca4  test    ebx, ebx
0x18000cca6  jns     short loc_18000CCDE
0x18000cca8  cmp     [rsp+168h+var_108], 0
0x18000ccae  jz      short loc_18000CCBB
0x18000ccb0  lea     rcx, [rsp+168h+var_108]; Binding
0x18000ccb5  call    cs:__imp_RpcBindingFree
0x18000ccbb  mov     eax, ebx
0x18000ccbd  mov     rcx, [rsp+168h+var_48]
0x18000ccc5  xor     rcx, rsp; StackCookie
0x18000ccc8  call    __security_check_cookie
0x18000cccd  add     rsp, 138h
0x18000ccd4  pop     r15
0x18000ccd6  pop     r14
0x18000ccd8  pop     r12
0x18000ccda  pop     rdi
0x18000ccdb  pop     rsi
0x18000ccdc  pop     rbx
0x18000ccdd  retn
0x18000ccde  movzx   eax, [rsp+168h+var_118]
0x18000cce3  mov     [r14], al
0x18000cce6  mov     ebx, edi
0x18000cce8  jmp     short loc_18000CCA8
0x18000ccea  mov     ebx, 0C00000F0h
0x18000ccef  jmp     short loc_18000CCA8
0x18000ccf1  jle     loc_18000CC2D
0x18000ccf7  movzx   ebx, ax
0x18000ccfa  or      ebx, 0C0070000h
0x18000cd00  jmp     loc_18000CC2D
0x18000cd05  jle     loc_18000CC2D
0x18000cd0b  movzx   ebx, ax
0x18000cd0e  or      ebx, 0C0070000h
0x18000cd14  jmp     loc_18000CC2D
0x18000cd19  lea     rcx, [rsp+168h+Binding]; Binding
0x18000cd1e  call    cs:__imp_RpcBindingFree
0x18000cd24  jmp     loc_18000CC38
0x18001b370  push    rbp
0x18001b372  sub     rsp, 50h
0x18001b376  mov     rbp, rdx
0x18001b379  mov     rcx, [rcx]
0x18001b37c  mov     ecx, [rcx]; ExceptionCode
0x18001b37e  call    cs:__imp_RpcExceptionFilter
0x18001b384  nop
0x18001b385  add     rsp, 50h
0x18001b389  pop     rbp
0x18001b38a  retn
```
