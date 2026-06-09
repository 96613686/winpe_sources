# BiEnumerateWorkItemsForPackageName

- ea: `0x180002630`
- end: `0x180002730`
- name: `BiEnumerateWorkItemsForPackageName`
- size: `256`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180002630`
- `0x180003228`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180002694`
- `ntdll!RtlLengthSid` at `0x180002694`
- `RPCRT4!NdrClientCall3` at `0x1800026f0`
- `RPCRT4!NdrClientCall3` at `0x1800026f0`
- `RPCRT4!RpcBindingFree` at `0x18000271a`
- `RPCRT4!RpcBindingFree` at `0x18000271a`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002706`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002706`

## pseudocode

```c
__int64 __fastcall BiEnumerateWorkItemsForPackageName(unsigned __int16 *a1, void *a2, int a3, __int64 a4, __int64 a5)
{
  int Pointer; // ebx
  __int64 v9; // r14
  int v10; // edi
  ULONG v11; // ecx
  RPC_BINDING_HANDLE Binding; // [rsp+B0h] [rbp+8h] BYREF

  Binding = 0;
  if ( a1 )
  {
    if ( (*(_BYTE *)a1 & 1) != 0 )
      return (unsigned int)-1073741811;
    v9 = *((_QWORD *)a1 + 1);
    v10 = *a1 >> 1;
  }
  else
  {
    v9 = 0;
    v10 = 0;
  }
  Pointer = BipCreateRpcBinding(&Binding);
  if ( Pointer >= 0 )
  {
    if ( a2 )
      v11 = RtlLengthSid(a2);
    else
      v11 = 0;
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0xEu,
                              0,
                              Binding,
                              v9,
                              v10,
                              a2,
                              v11,
                              a3,
                              2,
                              a4,
                              a5).Pointer;
    RpcBindingFree(&Binding);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180002630  mov     rax, rsp
0x180002633  push    rbx
0x180002634  push    rsi
0x180002635  push    rdi
0x180002636  push    r12
0x180002638  push    r14
0x18000263a  push    r15
0x18000263c  sub     rsp, 78h
0x180002640  mov     r15, r9
0x180002643  mov     r12d, r8d
0x180002646  mov     rsi, rdx
0x180002649  mov     qword ptr [rax+8], 0
0x180002651  test    rcx, rcx
0x180002654  jz      short loc_180002670
0x180002656  test    byte ptr [rcx], 1
0x180002659  jz      short loc_180002665
0x18000265b  mov     ebx, 0C000000Dh
0x180002660  jmp     loc_180002720
0x180002665  mov     r14, [rcx+8]
0x180002669  movzx   edi, word ptr [rcx]
0x18000266c  shr     edi, 1
0x18000266e  jmp     short loc_180002675
0x180002670  xor     r14d, r14d
0x180002673  xor     edi, edi
0x180002675  lea     rcx, [rsp+0A8h+Binding]
0x18000267d  call    BipCreateRpcBinding
0x180002682  mov     ebx, eax
0x180002684  test    eax, eax
0x180002686  js      loc_180002720
0x18000268c  test    rsi, rsi
0x18000268f  jz      short loc_18000269E
0x180002691  mov     rcx, rsi; Sid
0x180002694  call    cs:__imp_RtlLengthSid
0x18000269a  mov     ecx, eax
0x18000269c  jmp     short loc_1800026A0
0x18000269e  xor     ecx, ecx
0x1800026a0  mov     [rsp+0A8h+var_40], 0
0x1800026a9  mov     rax, [rsp+0A8h+arg_20]
0x1800026b1  mov     [rsp+0A8h+var_50], rax
0x1800026b6  mov     [rsp+0A8h+var_58], r15
0x1800026bb  mov     [rsp+0A8h+var_60], 2
0x1800026c3  mov     [rsp+0A8h+var_68], r12d
0x1800026c8  mov     [rsp+0A8h+var_70], ecx
0x1800026cc  mov     [rsp+0A8h+var_78], rsi
0x1800026d1  mov     [rsp+0A8h+var_80], edi
0x1800026d5  mov     [rsp+0A8h+var_88], r14
0x1800026da  mov     r9, [rsp+0A8h+Binding]
0x1800026e2  xor     r8d, r8d; pReturnValue
0x1800026e5  lea     edx, [r8+0Eh]; nProcNum
0x1800026e9  lea     rcx, pProxyInfo; pProxyInfo
0x1800026f0  call    cs:__imp_NdrClientCall3
0x1800026f6  mov     rbx, rax
0x1800026f9  mov     [rsp+0A8h+var_40], rax
0x1800026fe  mov     [rsp+0A8h+var_48], eax
0x180002702  jmp     short loc_180002712
0x180002704  mov     ecx, eax; Status
0x180002706  call    cs:__imp_I_RpcMapWin32Status
0x18000270c  mov     ebx, eax
0x18000270e  mov     [rsp+0A8h+var_48], eax
0x180002712  lea     rcx, [rsp+0A8h+Binding]; Binding
0x18000271a  call    cs:__imp_RpcBindingFree
0x180002720  mov     eax, ebx
0x180002722  add     rsp, 78h
0x180002726  pop     r15
0x180002728  pop     r14
0x18000272a  pop     r12
0x18000272c  pop     rdi
0x18000272d  pop     rsi
0x18000272e  pop     rbx
0x18000272f  retn
0x180003860  push    rbp
0x180003862  sub     rsp, 60h
0x180003866  mov     rbp, rdx
0x180003869  mov     rcx, [rcx]
0x18000386c  mov     ecx, [rcx]; ExceptionCode
0x18000386e  call    cs:__imp_RpcExceptionFilter
0x180003874  nop
0x180003875  add     rsp, 60h
0x180003879  pop     rbp
0x18000387a  retn
```
