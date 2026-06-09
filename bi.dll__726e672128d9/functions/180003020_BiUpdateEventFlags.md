# BiUpdateEventFlags

- ea: `0x180003020`
- end: `0x1800030b3`
- name: `BiUpdateEventFlags`
- size: `147`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180003020`
- `0x180003228`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180003077`
- `RPCRT4!NdrClientCall3` at `0x180003077`
- `RPCRT4!RpcBindingFree` at `0x1800030a1`
- `RPCRT4!RpcBindingFree` at `0x1800030a1`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000308d`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000308d`

## pseudocode

```c
__int64 __fastcall BiUpdateEventFlags(__int64 a1, int a2, int a3)
{
  int Pointer; // ebx
  int v8; // [rsp+28h] [rbp-50h]
  int v9; // [rsp+30h] [rbp-48h]
  RPC_BINDING_HANDLE Binding; // [rsp+98h] [rbp+20h] BYREF

  Binding = 0;
  Pointer = BipCreateRpcBinding(&Binding);
  if ( Pointer >= 0 )
  {
    v9 = a3;
    v8 = a2;
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x1Bu, 0, Binding, a1, v8, v9).Pointer;
    RpcBindingFree(&Binding);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180003020  mov     rax, rsp
0x180003023  push    rbx
0x180003024  push    rsi
0x180003025  push    rdi
0x180003026  push    r14
0x180003028  sub     rsp, 58h
0x18000302c  mov     edi, r8d
0x18000302f  mov     esi, edx
0x180003031  mov     r14, rcx
0x180003034  mov     qword ptr [rax+20h], 0
0x18000303c  lea     rcx, [rax+20h]
0x180003040  call    BipCreateRpcBinding
0x180003045  mov     ebx, eax
0x180003047  test    eax, eax
0x180003049  js      short loc_1800030A7
0x18000304b  mov     [rsp+78h+var_30], 0
0x180003054  mov     [rsp+78h+var_48], edi
0x180003058  mov     [rsp+78h+var_50], esi
0x18000305c  mov     [rsp+78h+var_58], r14
0x180003061  mov     r9, [rsp+78h+Binding]
0x180003069  xor     r8d, r8d; pReturnValue
0x18000306c  lea     edx, [r8+1Bh]; nProcNum
0x180003070  lea     rcx, pProxyInfo; pProxyInfo
0x180003077  call    cs:__imp_NdrClientCall3
0x18000307d  mov     rbx, rax
0x180003080  mov     [rsp+78h+var_30], rax
0x180003085  mov     [rsp+78h+var_38], eax
0x180003089  jmp     short loc_180003099
0x18000308b  mov     ecx, eax; Status
0x18000308d  call    cs:__imp_I_RpcMapWin32Status
0x180003093  mov     ebx, eax
0x180003095  mov     [rsp+78h+var_38], eax
0x180003099  lea     rcx, [rsp+78h+Binding]; Binding
0x1800030a1  call    cs:__imp_RpcBindingFree
0x1800030a7  mov     eax, ebx
0x1800030a9  add     rsp, 58h
0x1800030ad  pop     r14
0x1800030af  pop     rdi
0x1800030b0  pop     rsi
0x1800030b1  pop     rbx
0x1800030b2  retn
```
