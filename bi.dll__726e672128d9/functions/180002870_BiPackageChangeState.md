# BiPackageChangeState

- ea: `0x180002870`
- end: `0x18000292c`
- name: `BiPackageChangeState`
- size: `188`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180002870`
- `0x180003228`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180002896`
- `ntdll!RtlLengthSid` at `0x180002896`
- `RPCRT4!NdrClientCall3` at `0x1800028e7`
- `RPCRT4!NdrClientCall3` at `0x1800028e7`
- `RPCRT4!RpcBindingFree` at `0x180002916`
- `RPCRT4!RpcBindingFree` at `0x180002916`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800028fd`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800028fd`

## pseudocode

```c
__int64 __fastcall BiPackageChangeState(int a1, void *a2, __int64 a3, int a4)
{
  ULONG v8; // r12d
  int Pointer; // ebx
  __int64 v10; // rcx
  CLIENT_CALL_RETURN v11; // rax
  int v13; // [rsp+20h] [rbp-88h]
  ULONG v14; // [rsp+28h] [rbp-80h]
  int v15; // [rsp+40h] [rbp-68h]
  RPC_BINDING_HANDLE Binding; // [rsp+58h] [rbp-50h] BYREF
  CLIENT_CALL_RETURN v17; // [rsp+60h] [rbp-48h]

  Binding = 0;
  v8 = RtlLengthSid(a2);
  Pointer = BipCreateRpcBinding(&Binding);
  if ( Pointer >= 0 )
  {
    v10 = *(_QWORD *)(a3 + 8);
    v17.Simple = 0;
    v15 = a4;
    v14 = v8;
    v13 = a1;
    v11.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x10u, 0, Binding, v13, v14, a2, v10, v15).Pointer;
    Pointer = (int)v11.Pointer;
    v17.Pointer = v11.Pointer;
  }
  if ( Binding )
    RpcBindingFree(&Binding);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180002870  push    rbx
0x180002872  push    rsi
0x180002873  push    rdi
0x180002874  push    r12
0x180002876  push    r14
0x180002878  push    r15
0x18000287a  sub     rsp, 78h
0x18000287e  mov     esi, r9d
0x180002881  mov     r14, r8
0x180002884  mov     rdi, rdx
0x180002887  mov     r15d, ecx
0x18000288a  mov     [rsp+0A8h+Binding], 0
0x180002893  mov     rcx, rdx; Sid
0x180002896  call    cs:__imp_RtlLengthSid
0x18000289c  mov     r12d, eax
0x18000289f  lea     rcx, [rsp+0A8h+Binding]
0x1800028a4  call    BipCreateRpcBinding
0x1800028a9  mov     ebx, eax
0x1800028ab  test    eax, eax
0x1800028ad  js      short loc_180002909
0x1800028af  mov     rcx, [r14+8]
0x1800028b3  mov     [rsp+0A8h+var_48], 0
0x1800028bc  mov     [rsp+0A8h+var_68], esi
0x1800028c0  mov     [rsp+0A8h+var_70], rcx
0x1800028c5  mov     [rsp+0A8h+var_78], rdi
0x1800028ca  mov     [rsp+0A8h+var_80], r12d
0x1800028cf  mov     [rsp+0A8h+var_88], r15d
0x1800028d4  mov     r9, [rsp+0A8h+Binding]
0x1800028d9  xor     r8d, r8d; pReturnValue
0x1800028dc  lea     edx, [r8+10h]; nProcNum
0x1800028e0  lea     rcx, pProxyInfo; pProxyInfo
0x1800028e7  call    cs:__imp_NdrClientCall3
0x1800028ed  mov     rbx, rax
0x1800028f0  mov     [rsp+0A8h+var_48], rax
0x1800028f5  mov     [rsp+0A8h+var_58], eax
0x1800028f9  jmp     short loc_180002909
0x1800028fb  mov     ecx, eax; Status
0x1800028fd  call    cs:__imp_I_RpcMapWin32Status
0x180002903  mov     ebx, eax
0x180002905  mov     [rsp+0A8h+var_58], eax
0x180002909  cmp     [rsp+0A8h+Binding], 0
0x18000290f  jz      short loc_18000291C
0x180002911  lea     rcx, [rsp+0A8h+Binding]; Binding
0x180002916  call    cs:__imp_RpcBindingFree
0x18000291c  mov     eax, ebx
0x18000291e  add     rsp, 78h
0x180002922  pop     r15
0x180002924  pop     r14
0x180002926  pop     r12
0x180002928  pop     rdi
0x180002929  pop     rsi
0x18000292a  pop     rbx
0x18000292b  retn
```
