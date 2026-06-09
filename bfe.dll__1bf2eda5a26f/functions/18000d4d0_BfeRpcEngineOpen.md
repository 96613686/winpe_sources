# BfeRpcEngineOpen

- ea: `0x18000d4d0`
- end: `0x18000d6bc`
- name: `BfeRpcEngineOpen`
- size: `492`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation`

## callees

- `0x18000d4d0`
- `0x18000e000`
- `0x180012b54`
- `0x180018b74`
- `0x1800223a8`
- `0x180023e78`
- `0x180024720`
- `0x1800375bc`
- `0x180039cdc`
- `0x18004aeb8`
- `0x18004e230`
- `0x1800542bc`
- `0x180058b30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d5f0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d5f0`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000d6a2`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000d6a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d578`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d578`
- `RPCRT4!RpcRaiseException` at `0x18000d639`
- `RPCRT4!RpcRaiseException` at `0x18000d661`
- `RPCRT4!RpcRaiseException` at `0x18000d639`
- `RPCRT4!RpcRaiseException` at `0x18000d661`

## pseudocode

```c
__int64 __fastcall BfeRpcEngineOpen(
        RPC_BINDING_HANDLE ClientBinding,
        char *a2,
        __int64 a3,
        __int64 *a4,
        _QWORD *a5,
        __int64 *a6)
{
  char *v8; // rbx
  __int64 v10; // rdi
  __int64 v11; // rsi
  int v12; // ebx
  char *v14; // rax
  __int64 v15; // rcx
  RPC_STATUS v16; // ecx
  RPC_STATUS v17; // eax
  __int64 v18; // rax
  __int64 v19; // [rsp+30h] [rbp-28h] BYREF
  char *v20; // [rsp+38h] [rbp-20h] BYREF

  v20 = a2;
  v8 = a2;
  v19 = 0;
  *a6 = 0;
  if ( a2 )
  {
    v10 = BfeFwpmSessionValidate(a2);
    if ( v10 )
      goto LABEL_9;
    goto LABEL_3;
  }
  if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline(ClientBinding, 0, a3) )
  {
    v8 = v20;
    v10 = WfpMemAlloc25B(0x48u);
  }
  else
  {
    v14 = (char *)HeapAlloc(gWfpHeap, 8u, 0x48u);
    v20 = v14;
    v8 = v14;
    if ( v14 )
    {
      v10 = 0;
      if ( gWfpTrackHeapBytes )
        _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v14));
    }
    else
    {
      v18 = WfpReportSysErrorAsNtStatus(v15, "HeapAlloc", 3221225495LL);
      v10 = v18;
      if ( v18 )
        WfpReportError(v18, "WfpMemAlloc");
    }
  }
  if ( !v10 )
  {
LABEL_3:
    if ( !a3 || (v10 = BfeFwpmLangInfoValidate(a3)) == 0 )
    {
      v10 = BfeSessionCreate(ClientBinding, &v20, a3, a5, &v19);
      if ( !v10 )
      {
        v11 = v19;
        *a4 = v19;
        v12 = *(_DWORD *)(*(_QWORD *)(v11 + 16) + 40LL);
        if ( v12 == GetCurrentProcessId() )
          *a6 = v11;
      }
      v8 = v20;
    }
  }
LABEL_9:
  if ( v8 )
  {
    BfeDestroyInner_IKEEXT_IPV6_CGA_AUTHENTICATION0(v8 + 16);
    WfpMemFree(v8 + 48);
    WfpMemFree(v8 + 56);
  }
  WfpMemFree(&v20);
  if ( v10 )
  {
    if ( !(unsigned int)BfeRpcIsKernelModeCaller() )
    {
      v16 = (unsigned __int16)v10;
      if ( (v10 & 0x1FFF0000) != 0x70000 )
        v16 = v10;
      RpcRaiseException(v16);
    }
    v17 = WfpErrorToNtStatus(v10);
    RpcRaiseException(v17);
  }
  return 0;
}

```

## disassembly

```asm
0x18000d4d0  push    rbp
0x18000d4d2  push    rbx
0x18000d4d3  push    rsi
0x18000d4d4  push    rdi
0x18000d4d5  push    r12
0x18000d4d7  push    r13
0x18000d4d9  push    r14
0x18000d4db  push    r15
0x18000d4dd  mov     rbp, rsp
0x18000d4e0  sub     rsp, 58h
0x18000d4e4  mov     rax, cs:__security_cookie
0x18000d4eb  xor     rax, rsp
0x18000d4ee  mov     [rbp+var_18], rax
0x18000d4f2  mov     r14, [rbp+arg_28]
0x18000d4f6  mov     r15, r9
0x18000d4f9  mov     r13, [rbp+arg_20]
0x18000d4fd  mov     rsi, r8
0x18000d500  mov     [rbp+var_20], rdx
0x18000d504  mov     rbx, rdx
0x18000d507  mov     [rbp+var_28], 0
0x18000d50f  mov     r12, rcx
0x18000d512  mov     qword ptr [r14], 0
0x18000d519  test    rdx, rdx
0x18000d51c  jz      loc_18000D5D7
0x18000d522  mov     rcx, rdx
0x18000d525  call    BfeFwpmSessionValidate
0x18000d52a  mov     rdi, rax
0x18000d52d  test    rax, rax
0x18000d530  jnz     short loc_18000D58A
0x18000d532  test    rsi, rsi
0x18000d535  jz      short loc_18000D547
0x18000d537  mov     rcx, rsi
0x18000d53a  call    BfeFwpmLangInfoValidate
0x18000d53f  mov     rdi, rax
0x18000d542  test    rax, rax
0x18000d545  jnz     short loc_18000D58A
0x18000d547  lea     rax, [rbp+var_28]
0x18000d54b  mov     r9, r13
0x18000d54e  mov     r8, rsi
0x18000d551  mov     [rsp+58h+var_38], rax; __int64
0x18000d556  lea     rdx, [rbp+var_20]
0x18000d55a  mov     rcx, r12; ClientBinding
0x18000d55d  call    BfeSessionCreate
0x18000d562  mov     rdi, rax
0x18000d565  test    rax, rax
0x18000d568  jnz     short loc_18000D586
0x18000d56a  mov     rsi, [rbp+var_28]
0x18000d56e  mov     [r15], rsi
0x18000d571  mov     rax, [rsi+10h]
0x18000d575  mov     ebx, [rax+28h]
0x18000d578  call    cs:__imp_GetCurrentProcessId
0x18000d57e  cmp     ebx, eax
0x18000d580  jz      loc_18000D6B4
0x18000d586  mov     rbx, [rbp+var_20]
0x18000d58a  test    rbx, rbx
0x18000d58d  jz      short loc_18000D5AA
0x18000d58f  lea     rcx, [rbx+10h]
0x18000d593  call    BfeDestroyInner_IKEEXT_IPV6_CGA_AUTHENTICATION0
0x18000d598  lea     rcx, [rbx+30h]
0x18000d59c  call    WfpMemFree
0x18000d5a1  lea     rcx, [rbx+38h]
0x18000d5a5  call    WfpMemFree
0x18000d5aa  lea     rcx, [rbp+var_20]
0x18000d5ae  call    WfpMemFree
0x18000d5b3  test    rdi, rdi
0x18000d5b6  jnz     short loc_18000D61E
0x18000d5b8  xor     eax, eax
0x18000d5ba  mov     rcx, [rbp+var_18]
0x18000d5be  xor     rcx, rsp; StackCookie
0x18000d5c1  call    __security_check_cookie
0x18000d5c6  add     rsp, 58h
0x18000d5ca  pop     r15
0x18000d5cc  pop     r14
0x18000d5ce  pop     r13
0x18000d5d0  pop     r12
0x18000d5d2  pop     rdi
0x18000d5d3  pop     rsi
0x18000d5d4  pop     rbx
0x18000d5d5  pop     rbp
0x18000d5d6  retn
0x18000d5d7  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18000d5dc  mov     edx, 8; dwFlags
0x18000d5e1  test    eax, eax
0x18000d5e3  jnz     short loc_18000D640
0x18000d5e5  mov     rcx, cs:gWfpHeap; hHeap
0x18000d5ec  lea     r8d, [rdx+40h]; dwBytes
0x18000d5f0  call    cs:__imp_HeapAlloc
0x18000d5f6  mov     [rbp+var_20], rax
0x18000d5fa  mov     rbx, rax
0x18000d5fd  test    rax, rax
0x18000d600  jz      short loc_18000D668
0x18000d602  xor     edi, edi
0x18000d604  cmp     cs:gWfpTrackHeapBytes, edi
0x18000d60a  jnz     loc_18000D696
0x18000d610  test    rdi, rdi
0x18000d613  jz      loc_18000D532
0x18000d619  jmp     loc_18000D58A
0x18000d61e  call    BfeRpcIsKernelModeCaller
0x18000d623  test    eax, eax
0x18000d625  jnz     short loc_18000D657
0x18000d627  mov     eax, edi
0x18000d629  movzx   ecx, di
0x18000d62c  and     eax, 1FFF0000h
0x18000d631  cmp     eax, 70000h
0x18000d636  cmovnz  ecx, edi; exception
0x18000d639  call    cs:__imp_RpcRaiseException
0x18000d63f  int     3; Trap to Debugger
0x18000d640  lea     r8, [rbp+var_20]
0x18000d644  mov     ecx, 48h ; 'H'; dwBytes
0x18000d649  call    WfpMemAlloc25B
0x18000d64e  mov     rbx, [rbp+var_20]
0x18000d652  mov     rdi, rax
0x18000d655  jmp     short loc_18000D610
0x18000d657  mov     rcx, rdi
0x18000d65a  call    WfpErrorToNtStatus
0x18000d65f  mov     ecx, eax; exception
0x18000d661  call    cs:__imp_RpcRaiseException
0x18000d667  int     3; Trap to Debugger
0x18000d668  mov     r8d, 0C0000017h
0x18000d66e  lea     rdx, aHeapalloc; "HeapAlloc"
0x18000d675  call    WfpReportSysErrorAsNtStatus
0x18000d67a  mov     rdi, rax
0x18000d67d  test    rax, rax
0x18000d680  jz      short loc_18000D610
0x18000d682  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
0x18000d689  mov     rcx, rax
0x18000d68c  call    WfpReportError
0x18000d691  jmp     loc_18000D610
0x18000d696  mov     rcx, cs:gWfpHeap; hHeap
0x18000d69d  mov     r8, rax; lpMem
0x18000d6a0  xor     edx, edx; dwFlags
0x18000d6a2  call    cs:__imp_HeapSize
0x18000d6a8  lock add cs:gWfpHeapBytesAllocated, eax
0x18000d6af  jmp     loc_18000D610
0x18000d6b4  mov     [r14], rsi
0x18000d6b7  jmp     loc_18000D586
```
