# HamGetInterruptiveUIStateForAumid

- ea: `0x180001a70`
- end: `0x180001b70`
- name: `HamGetInterruptiveUIStateForAumid`
- size: `256`
- prototype: `__int64 __fastcall(__int64, void *, int, bool *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180001a70`
- `0x180002f50`

## import_xrefs

- `ntdll!RtlValidSid` at `0x180001aa1`
- `ntdll!RtlValidSid` at `0x180001aa1`
- `ntdll!RtlLengthSid` at `0x180001ad3`
- `ntdll!RtlLengthSid` at `0x180001ad3`
- `RPCRT4!NdrClientCall3` at `0x180001b12`
- `RPCRT4!NdrClientCall3` at `0x180001b12`
- `RPCRT4!RpcBindingFree` at `0x180001b5a`
- `RPCRT4!RpcBindingFree` at `0x180001b5a`
- `RPCRT4!RpcExceptionFilter` at `0x18001b000`
- `RPCRT4!RpcExceptionFilter` at `0x18001b000`
- `RPCRT4!I_RpcMapWin32Status` at `0x180001b28`
- `RPCRT4!I_RpcMapWin32Status` at `0x180001b28`

## pseudocode

```c
__int64 __fastcall HamGetInterruptiveUIStateForAumid(__int64 a1, void *a2, int a3, bool *a4)
{
  int v8; // edi
  int Pointer; // ebx
  ULONG v10; // eax
  CLIENT_CALL_RETURN v11; // rax
  ULONG v13; // [rsp+30h] [rbp-78h]
  int v14; // [rsp+38h] [rbp-70h]
  _BYTE v15[4]; // [rsp+50h] [rbp-58h] BYREF
  int v16; // [rsp+54h] [rbp-54h]
  RPC_BINDING_HANDLE Binding; // [rsp+58h] [rbp-50h] BYREF
  CLIENT_CALL_RETURN v18; // [rsp+60h] [rbp-48h]

  Binding = 0;
  v15[0] = 0;
  v8 = 0;
  if ( RtlValidSid(a2) )
  {
    Pointer = CempRpcBindToServer(qword_18001DC80, &Binding);
    if ( Pointer >= 0 )
    {
      v10 = RtlLengthSid(a2);
      v18.Simple = 0;
      v14 = a3;
      v13 = v10;
      v11.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x15u, 0, Binding, a1, a2, v13, v14, v15).Pointer;
      Pointer = (int)v11.Pointer;
      v18.Pointer = v11.Pointer;
      v16 = (int)v11.Pointer;
      v8 = 1;
      if ( SLODWORD(v11.Simple) >= 0 )
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
    RpcBindingFree(&Binding);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180001a70  mov     [rsp+arg_18], r9
0x180001a75  push    rbx
0x180001a76  push    rsi
0x180001a77  push    rdi
0x180001a78  push    r12
0x180001a7a  push    r14
0x180001a7c  push    r15
0x180001a7e  sub     rsp, 78h
0x180001a82  mov     rsi, r9
0x180001a85  mov     r15d, r8d
0x180001a88  mov     r14, rdx
0x180001a8b  mov     r12, rcx
0x180001a8e  mov     [rsp+0A8h+Binding], 0
0x180001a97  mov     [rsp+0A8h+var_58], 0
0x180001a9c  xor     edi, edi
0x180001a9e  mov     rcx, rdx; Sid
0x180001aa1  call    cs:__imp_RtlValidSid
0x180001aa7  test    al, al
0x180001aa9  jnz     short loc_180001AB5
0x180001aab  mov     ebx, 0C00000F0h
0x180001ab0  jmp     loc_180001B51
0x180001ab5  lea     rdx, [rsp+0A8h+Binding]
0x180001aba  lea     rcx, qword_18001DC80; IfSpec
0x180001ac1  call    CempRpcBindToServer
0x180001ac6  mov     ebx, eax
0x180001ac8  test    eax, eax
0x180001aca  js      loc_180001B51
0x180001ad0  mov     rcx, r14; Sid
0x180001ad3  call    cs:__imp_RtlLengthSid
0x180001ad9  mov     [rsp+0A8h+var_48], 0
0x180001ae2  lea     rcx, [rsp+0A8h+var_58]
0x180001ae7  mov     [rsp+0A8h+var_68], rcx
0x180001aec  mov     [rsp+0A8h+var_70], r15d
0x180001af1  mov     [rsp+0A8h+var_78], eax
0x180001af5  mov     [rsp+0A8h+var_80], r14
0x180001afa  mov     [rsp+0A8h+var_88], r12
0x180001aff  mov     r9, [rsp+0A8h+Binding]
0x180001b04  xor     r8d, r8d; pReturnValue
0x180001b07  lea     edx, [r8+15h]; nProcNum
0x180001b0b  lea     rcx, pProxyInfo; pProxyInfo
0x180001b12  call    cs:__imp_NdrClientCall3
0x180001b18  mov     rbx, rax
0x180001b1b  mov     [rsp+0A8h+var_48], rax
0x180001b20  mov     [rsp+0A8h+var_54], eax
0x180001b24  jmp     short loc_180001B3C
0x180001b26  mov     ecx, eax; Status
0x180001b28  call    cs:__imp_I_RpcMapWin32Status
0x180001b2e  mov     ebx, eax
0x180001b30  mov     [rsp+0A8h+var_54], eax
0x180001b34  mov     rsi, [rsp+0A8h+arg_18]
0x180001b3c  mov     edi, 1
0x180001b41  test    ebx, ebx
0x180001b43  js      short loc_180001B51
0x180001b45  cmp     [rsp+0A8h+var_58], 0
0x180001b4a  setnz   al
0x180001b4d  mov     [rsi], al
0x180001b4f  xor     ebx, ebx
0x180001b51  test    edi, edi
0x180001b53  jz      short loc_180001B60
0x180001b55  lea     rcx, [rsp+0A8h+Binding]; Binding
0x180001b5a  call    cs:__imp_RpcBindingFree
0x180001b60  mov     eax, ebx
0x180001b62  add     rsp, 78h
0x180001b66  pop     r15
0x180001b68  pop     r14
0x180001b6a  pop     r12
0x180001b6c  pop     rdi
0x180001b6d  pop     rsi
0x180001b6e  pop     rbx
0x180001b6f  retn
0x18001aff2  push    rbp
0x18001aff4  sub     rsp, 50h
0x18001aff8  mov     rbp, rdx
0x18001affb  mov     rcx, [rcx]
0x18001affe  mov     ecx, [rcx]; ExceptionCode
0x18001b000  call    cs:__imp_RpcExceptionFilter
0x18001b006  nop
0x18001b007  add     rsp, 50h
0x18001b00b  pop     rbp
0x18001b00c  retn
```
