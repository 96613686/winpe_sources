# BiAssociateApplicationExtensionClass

- ea: `0x180001dd0`
- end: `0x180001efb`
- name: `BiAssociateApplicationExtensionClass`
- size: `299`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180001dd0`
- `0x180003228`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180001eac`
- `RPCRT4!NdrClientCall3` at `0x180001eac`
- `RPCRT4!RpcBindingFree` at `0x180001ed6`
- `RPCRT4!RpcBindingFree` at `0x180001ed6`
- `RPCRT4!I_RpcMapWin32Status` at `0x180001ec2`
- `RPCRT4!I_RpcMapWin32Status` at `0x180001ec2`

## pseudocode

```c
__int64 __fastcall BiAssociateApplicationExtensionClass(
        __int64 a1,
        unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        unsigned __int16 *a7)
{
  int Pointer; // ebx
  __int64 v10; // r14
  int v11; // edi
  __int64 v12; // r15
  int v13; // esi
  RPC_BINDING_HANDLE Binding; // [rsp+B8h] [rbp+10h] BYREF

  Binding = 0;
  if ( (*(_BYTE *)a2 & 1) != 0 )
    return (unsigned int)-1073741811;
  if ( a7 )
  {
    if ( (*(_BYTE *)a7 & 1) != 0 )
      return (unsigned int)-1073741811;
    v10 = *((_QWORD *)a7 + 1);
    v11 = *a7 >> 1;
  }
  else
  {
    v10 = 0;
    v11 = 0;
  }
  v12 = *((_QWORD *)a2 + 1);
  v13 = *a2 >> 1;
  Pointer = BipCreateRpcBinding(&Binding);
  if ( Pointer >= 0 )
  {
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              4u,
                              0,
                              Binding,
                              a1,
                              v12,
                              v13,
                              a3,
                              a4,
                              a5,
                              a6,
                              v10,
                              v11).Pointer;
    RpcBindingFree(&Binding);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180001dd0  mov     rax, rsp
0x180001dd3  mov     [rax+18h], rbx
0x180001dd7  mov     [rax+20h], rsi
0x180001ddb  mov     [rax+8], rcx
0x180001ddf  push    rdi
0x180001de0  push    r12
0x180001de2  push    r13
0x180001de4  push    r14
0x180001de6  push    r15
0x180001de8  sub     rsp, 80h
0x180001def  mov     r12, r9
0x180001df2  mov     r13, r8
0x180001df5  mov     qword ptr [rax+10h], 0
0x180001dfd  test    byte ptr [rdx], 1
0x180001e00  jz      short loc_180001E0C
0x180001e02  mov     ebx, 0C000000Dh
0x180001e07  jmp     loc_180001EDC
0x180001e0c  mov     rax, [rsp+0A8h+arg_30]
0x180001e14  test    rax, rax
0x180001e17  jz      short loc_180001E29
0x180001e19  test    byte ptr [rax], 1
0x180001e1c  jnz     short loc_180001E02
0x180001e1e  mov     r14, [rax+8]
0x180001e22  movzx   edi, word ptr [rax]
0x180001e25  shr     edi, 1
0x180001e27  jmp     short loc_180001E2E
0x180001e29  xor     r14d, r14d
0x180001e2c  xor     edi, edi
0x180001e2e  mov     r15, [rdx+8]
0x180001e32  movzx   esi, word ptr [rdx]
0x180001e35  shr     esi, 1
0x180001e37  lea     rcx, [rsp+0A8h+Binding]
0x180001e3f  call    BipCreateRpcBinding
0x180001e44  mov     ebx, eax
0x180001e46  test    eax, eax
0x180001e48  js      loc_180001EDC
0x180001e4e  mov     [rsp+0A8h+var_30], 0
0x180001e57  mov     [rsp+0A8h+var_48], edi
0x180001e5b  mov     [rsp+0A8h+var_50], r14
0x180001e60  mov     eax, [rsp+0A8h+arg_28]
0x180001e67  mov     [rsp+0A8h+var_58], eax
0x180001e6b  mov     eax, [rsp+0A8h+arg_20]
0x180001e72  mov     [rsp+0A8h+var_60], eax
0x180001e76  mov     [rsp+0A8h+var_68], r12
0x180001e7b  mov     [rsp+0A8h+var_70], r13
0x180001e80  mov     [rsp+0A8h+var_78], esi
0x180001e84  mov     [rsp+0A8h+var_80], r15
0x180001e89  mov     rax, [rsp+0A8h+arg_0]
0x180001e91  mov     [rsp+0A8h+var_88], rax
0x180001e96  mov     r9, [rsp+0A8h+Binding]
0x180001e9e  xor     r8d, r8d; pReturnValue
0x180001ea1  lea     edx, [r8+4]; nProcNum
0x180001ea5  lea     rcx, pProxyInfo; pProxyInfo
0x180001eac  call    cs:__imp_NdrClientCall3
0x180001eb2  mov     rbx, rax
0x180001eb5  mov     [rsp+0A8h+var_30], rax
0x180001eba  mov     [rsp+0A8h+var_38], eax
0x180001ebe  jmp     short loc_180001ECE
0x180001ec0  mov     ecx, eax; Status
0x180001ec2  call    cs:__imp_I_RpcMapWin32Status
0x180001ec8  mov     ebx, eax
0x180001eca  mov     [rsp+0A8h+var_38], eax
0x180001ece  lea     rcx, [rsp+0A8h+Binding]; Binding
0x180001ed6  call    cs:__imp_RpcBindingFree
0x180001edc  mov     eax, ebx
0x180001ede  lea     r11, [rsp+0A8h+var_28]
0x180001ee6  mov     rbx, [r11+40h]
0x180001eea  mov     rsi, [r11+48h]
0x180001eee  mov     rsp, r11
0x180001ef1  pop     r15
0x180001ef3  pop     r14
0x180001ef5  pop     r13
0x180001ef7  pop     r12
0x180001ef9  pop     rdi
0x180001efa  retn
0x180003882  push    rbp
0x180003884  sub     rsp, 70h
0x180003888  mov     rbp, rdx
0x18000388b  mov     rcx, [rcx]
0x18000388e  mov     ecx, [rcx]; ExceptionCode
0x180003890  call    cs:__imp_RpcExceptionFilter
0x180003896  nop
0x180003897  add     rsp, 70h
0x18000389b  pop     rbp
0x18000389c  retn
```
