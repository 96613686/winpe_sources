# HamGetPackageInterruptiveUIState

- ea: `0x180019b10`
- end: `0x180019c10`
- name: `HamGetPackageInterruptiveUIState`
- size: `256`
- prototype: `__int64 __fastcall(__int64, void *, int, bool *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180002f50`
- `0x180019b10`

## import_xrefs

- `ntdll!RtlValidSid` at `0x180019b41`
- `ntdll!RtlValidSid` at `0x180019b41`
- `ntdll!RtlLengthSid` at `0x180019b73`
- `ntdll!RtlLengthSid` at `0x180019b73`
- `RPCRT4!NdrClientCall3` at `0x180019bb2`
- `RPCRT4!NdrClientCall3` at `0x180019bb2`
- `RPCRT4!RpcBindingFree` at `0x180019bfa`
- `RPCRT4!RpcBindingFree` at `0x180019bfa`
- `RPCRT4!I_RpcMapWin32Status` at `0x180019bc8`
- `RPCRT4!I_RpcMapWin32Status` at `0x180019bc8`

## pseudocode

```c
__int64 __fastcall HamGetPackageInterruptiveUIState(__int64 a1, void *a2, int a3, bool *a4)
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
      v11.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x14u, 0, Binding, a1, a2, v13, v14, v15).Pointer;
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
0x180019b10  mov     [rsp+arg_18], r9
0x180019b15  push    rbx
0x180019b16  push    rsi
0x180019b17  push    rdi
0x180019b18  push    r12
0x180019b1a  push    r14
0x180019b1c  push    r15
0x180019b1e  sub     rsp, 78h
0x180019b22  mov     rsi, r9
0x180019b25  mov     r15d, r8d
0x180019b28  mov     r14, rdx
0x180019b2b  mov     r12, rcx
0x180019b2e  mov     [rsp+0A8h+Binding], 0
0x180019b37  mov     [rsp+0A8h+var_58], 0
0x180019b3c  xor     edi, edi
0x180019b3e  mov     rcx, rdx; Sid
0x180019b41  call    cs:__imp_RtlValidSid
0x180019b47  test    al, al
0x180019b49  jnz     short loc_180019B55
0x180019b4b  mov     ebx, 0C00000F0h
0x180019b50  jmp     loc_180019BF1
0x180019b55  lea     rdx, [rsp+0A8h+Binding]
0x180019b5a  lea     rcx, qword_18001DC80; IfSpec
0x180019b61  call    CempRpcBindToServer
0x180019b66  mov     ebx, eax
0x180019b68  test    eax, eax
0x180019b6a  js      loc_180019BF1
0x180019b70  mov     rcx, r14; Sid
0x180019b73  call    cs:__imp_RtlLengthSid
0x180019b79  mov     [rsp+0A8h+var_48], 0
0x180019b82  lea     rcx, [rsp+0A8h+var_58]
0x180019b87  mov     [rsp+0A8h+var_68], rcx
0x180019b8c  mov     [rsp+0A8h+var_70], r15d
0x180019b91  mov     [rsp+0A8h+var_78], eax
0x180019b95  mov     [rsp+0A8h+var_80], r14
0x180019b9a  mov     [rsp+0A8h+var_88], r12
0x180019b9f  mov     r9, [rsp+0A8h+Binding]
0x180019ba4  xor     r8d, r8d; pReturnValue
0x180019ba7  lea     edx, [r8+14h]; nProcNum
0x180019bab  lea     rcx, pProxyInfo; pProxyInfo
0x180019bb2  call    cs:__imp_NdrClientCall3
0x180019bb8  mov     rbx, rax
0x180019bbb  mov     [rsp+0A8h+var_48], rax
0x180019bc0  mov     [rsp+0A8h+var_54], eax
0x180019bc4  jmp     short loc_180019BDC
0x180019bc6  mov     ecx, eax; Status
0x180019bc8  call    cs:__imp_I_RpcMapWin32Status
0x180019bce  mov     ebx, eax
0x180019bd0  mov     [rsp+0A8h+var_54], eax
0x180019bd4  mov     rsi, [rsp+0A8h+arg_18]
0x180019bdc  mov     edi, 1
0x180019be1  test    ebx, ebx
0x180019be3  js      short loc_180019BF1
0x180019be5  cmp     [rsp+0A8h+var_58], 0
0x180019bea  setnz   al
0x180019bed  mov     [rsi], al
0x180019bef  xor     ebx, ebx
0x180019bf1  test    edi, edi
0x180019bf3  jz      short loc_180019C00
0x180019bf5  lea     rcx, [rsp+0A8h+Binding]; Binding
0x180019bfa  call    cs:__imp_RpcBindingFree
0x180019c00  mov     eax, ebx
0x180019c02  add     rsp, 78h
0x180019c06  pop     r15
0x180019c08  pop     r14
0x180019c0a  pop     r12
0x180019c0c  pop     rdi
0x180019c0d  pop     rsi
0x180019c0e  pop     rbx
0x180019c0f  retn
0x18001bb0e  push    rbp
0x18001bb10  sub     rsp, 50h
0x18001bb14  mov     rbp, rdx
0x18001bb17  mov     rcx, [rcx]
0x18001bb1a  mov     ecx, [rcx]; ExceptionCode
0x18001bb1c  call    cs:__imp_RpcExceptionFilter
0x18001bb22  nop
0x18001bb23  add     rsp, 50h
0x18001bb27  pop     rbp
0x18001bb28  retn
```
