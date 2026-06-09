# SspiSrvInitialize

- ea: `0x1800027c0`
- end: `0x1800028a2`
- name: `SspiSrvInitialize`
- size: `226`
- prototype: `int __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000233c`
- `0x1800027c0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180002825`
- `ntdll!RtlFreeHeap` at `0x18000287f`
- `ntdll!RtlFreeHeap` at `0x180002825`
- `ntdll!RtlFreeHeap` at `0x18000287f`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180002807`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180002807`
- `RPCRT4!RpcServerRegisterIf3` at `0x180002865`
- `RPCRT4!RpcServerRegisterIf3` at `0x180002865`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000282d`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000282d`

## pseudocode

```c
int __fastcall SspiSrvInitialize(__int64 a1)
{
  int result; // eax
  void *v3; // rbx
  RPC_STATUS v4; // esi
  void *SecurityDescriptor; // [rsp+58h] [rbp+10h] BYREF

  SecurityDescriptor = 0;
  result = LsapMakeLowBoxRpcSD(&SecurityDescriptor);
  if ( result >= 0 )
  {
    v3 = SecurityDescriptor;
    v4 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0xAu, (RPC_WSTR)L"lsasspirpc", SecurityDescriptor);
    if ( v4 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
      return I_RpcMapWin32Status(v4);
    }
    v4 = RpcServerRegisterIf3(qword_180006CA0, 0, 0, 33, 1234, 0x100000, 0, v3);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
    if ( v4 )
      return I_RpcMapWin32Status(v4);
    gLsapSspiExtension = a1;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800027c0  mov     rax, rsp
0x1800027c3  mov     [rax+8], rbx
0x1800027c7  mov     [rax+18h], rsi
0x1800027cb  push    rdi
0x1800027cc  sub     rsp, 40h
0x1800027d0  mov     rdi, rcx
0x1800027d3  mov     qword ptr [rax+10h], 0
0x1800027db  lea     rcx, [rax+10h]
0x1800027df  call    LsapMakeLowBoxRpcSD
0x1800027e4  test    eax, eax
0x1800027e6  js      loc_180002892
0x1800027ec  mov     rbx, [rsp+48h+SecurityDescriptor]
0x1800027f1  lea     r8, Endpoint; "lsasspirpc"
0x1800027f8  mov     r9, rbx; SecurityDescriptor
0x1800027fb  lea     rcx, Protseq; "ncalrpc"
0x180002802  mov     edx, 0Ah; MaxCalls
0x180002807  call    cs:__imp_RpcServerUseProtseqEpW
0x18000280d  mov     esi, eax
0x18000280f  test    eax, eax
0x180002811  jz      short loc_180002835
0x180002813  mov     rcx, gs:60h
0x18000281c  mov     r8, rbx; P
0x18000281f  xor     edx, edx; Flags
0x180002821  mov     rcx, [rcx+30h]; HeapHandle
0x180002825  call    cs:__imp_RtlFreeHeap
0x18000282b  mov     ecx, esi; Status
0x18000282d  call    cs:__imp_I_RpcMapWin32Status
0x180002833  jmp     short loc_180002892
0x180002835  mov     [rsp+48h+var_10], rbx
0x18000283a  lea     rcx, qword_180006CA0
0x180002841  mov     [rsp+48h+var_18], 0
0x18000284a  mov     r9d, 21h ; '!'
0x180002850  mov     [rsp+48h+var_20], 100000h
0x180002858  xor     r8d, r8d
0x18000285b  xor     edx, edx
0x18000285d  mov     [rsp+48h+var_28], 4D2h
0x180002865  call    cs:__imp_RpcServerRegisterIf3
0x18000286b  mov     rcx, gs:60h
0x180002874  mov     r8, rbx; P
0x180002877  xor     edx, edx; Flags
0x180002879  mov     esi, eax
0x18000287b  mov     rcx, [rcx+30h]; HeapHandle
0x18000287f  call    cs:__imp_RtlFreeHeap
0x180002885  test    esi, esi
0x180002887  jnz     short loc_18000282B
0x180002889  mov     cs:gLsapSspiExtension, rdi
0x180002890  xor     eax, eax
0x180002892  mov     rbx, [rsp+48h+arg_0]
0x180002897  mov     rsi, [rsp+48h+arg_10]
0x18000289c  add     rsp, 40h
0x1800028a0  pop     rdi
0x1800028a1  retn
```
