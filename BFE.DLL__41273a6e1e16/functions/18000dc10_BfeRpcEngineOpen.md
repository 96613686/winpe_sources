# BfeRpcEngineOpen

- ea: `0x18000dc10`
- end: `0x18000de1b`
- name: `BfeRpcEngineOpen`
- size: `523`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation`

## callees

- `0x18000dc10`
- `0x18000e7e0`
- `0x1800135ac`
- `0x1800197d0`
- `0x18001f27c`
- `0x180024ab0`
- `0x18002681c`
- `0x180026f44`
- `0x18003889c`
- `0x18004cce8`
- `0x18004fb50`
- `0x1800560f8`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dd37`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dd37`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000ddfb`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18000ddfb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000dcb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000dcb8`
- `RPCRT4!RpcRaiseException` at `0x18000dd86`
- `RPCRT4!RpcRaiseException` at `0x18000ddb4`
- `RPCRT4!RpcRaiseException` at `0x18000dd86`
- `RPCRT4!RpcRaiseException` at `0x18000ddb4`

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
0x18000dc10  push    rbp
0x18000dc12  push    rbx
0x18000dc13  push    rsi
0x18000dc14  push    rdi
0x18000dc15  push    r12
0x18000dc17  push    r13
0x18000dc19  push    r14
0x18000dc1b  push    r15
0x18000dc1d  mov     rbp, rsp
0x18000dc20  sub     rsp, 58h
0x18000dc24  mov     rax, cs:__security_cookie
0x18000dc2b  xor     rax, rsp
0x18000dc2e  mov     [rbp+var_18], rax
0x18000dc32  mov     r14, [rbp+arg_28]
0x18000dc36  mov     r15, r9
0x18000dc39  mov     r13, [rbp+arg_20]
0x18000dc3d  mov     rsi, r8
0x18000dc40  mov     [rbp+var_20], rdx
0x18000dc44  mov     rbx, rdx
0x18000dc47  mov     [rbp+var_28], 0
0x18000dc4f  mov     r12, rcx
0x18000dc52  mov     qword ptr [r14], 0
0x18000dc59  test    rdx, rdx
0x18000dc5c  jz      loc_18000DD1E
0x18000dc62  mov     rcx, rdx
0x18000dc65  call    BfeFwpmSessionValidate
0x18000dc6a  mov     rdi, rax
0x18000dc6d  test    rax, rax
0x18000dc70  jnz     short loc_18000DCD0
0x18000dc72  test    rsi, rsi
0x18000dc75  jz      short loc_18000DC87
0x18000dc77  mov     rcx, rsi
0x18000dc7a  call    BfeFwpmLangInfoValidate
0x18000dc7f  mov     rdi, rax
0x18000dc82  test    rax, rax
0x18000dc85  jnz     short loc_18000DCD0
0x18000dc87  lea     rax, [rbp+var_28]
0x18000dc8b  mov     r9, r13
0x18000dc8e  mov     r8, rsi
0x18000dc91  mov     [rsp+58h+var_38], rax; __int64
0x18000dc96  lea     rdx, [rbp+var_20]
0x18000dc9a  mov     rcx, r12; ClientBinding
0x18000dc9d  call    BfeSessionCreate
0x18000dca2  mov     rdi, rax
0x18000dca5  test    rax, rax
0x18000dca8  jnz     short loc_18000DCCC
0x18000dcaa  mov     rsi, [rbp+var_28]
0x18000dcae  mov     [r15], rsi
0x18000dcb1  mov     rax, [rsi+10h]
0x18000dcb5  mov     ebx, [rax+28h]
0x18000dcb8  call    cs:__imp_GetCurrentProcessId
0x18000dcbf  nop     dword ptr [rax+rax+00h]
0x18000dcc4  cmp     ebx, eax
0x18000dcc6  jz      loc_18000DE13
0x18000dccc  mov     rbx, [rbp+var_20]
0x18000dcd0  test    rbx, rbx
0x18000dcd3  jz      short loc_18000DCF0
0x18000dcd5  lea     rcx, [rbx+10h]
0x18000dcd9  call    BfeDestroyInner_IKEEXT_IPV6_CGA_AUTHENTICATION0
0x18000dcde  lea     rcx, [rbx+30h]
0x18000dce2  call    WfpMemFree
0x18000dce7  lea     rcx, [rbx+38h]
0x18000dceb  call    WfpMemFree
0x18000dcf0  lea     rcx, [rbp+var_20]
0x18000dcf4  call    WfpMemFree
0x18000dcf9  test    rdi, rdi
0x18000dcfc  jnz     short loc_18000DD6B
0x18000dcfe  xor     eax, eax
0x18000dd00  mov     rcx, [rbp+var_18]
0x18000dd04  xor     rcx, rsp; StackCookie
0x18000dd07  call    __security_check_cookie
0x18000dd0c  add     rsp, 58h
0x18000dd10  pop     r15
0x18000dd12  pop     r14
0x18000dd14  pop     r13
0x18000dd16  pop     r12
0x18000dd18  pop     rdi
0x18000dd19  pop     rsi
0x18000dd1a  pop     rbx
0x18000dd1b  pop     rbp
0x18000dd1c  retn
0x18000dd1e  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x18000dd23  mov     edx, 8; dwFlags
0x18000dd28  test    eax, eax
0x18000dd2a  jnz     short loc_18000DD93
0x18000dd2c  mov     rcx, cs:gWfpHeap; hHeap
0x18000dd33  lea     r8d, [rdx+40h]; dwBytes
0x18000dd37  call    cs:__imp_HeapAlloc
0x18000dd3e  nop     dword ptr [rax+rax+00h]
0x18000dd43  mov     [rbp+var_20], rax
0x18000dd47  mov     rbx, rax
0x18000dd4a  test    rax, rax
0x18000dd4d  jz      short loc_18000DDC1
0x18000dd4f  xor     edi, edi
0x18000dd51  cmp     cs:gWfpTrackHeapBytes, edi
0x18000dd57  jnz     loc_18000DDEF
0x18000dd5d  test    rdi, rdi
0x18000dd60  jz      loc_18000DC72
0x18000dd66  jmp     loc_18000DCD0
0x18000dd6b  call    BfeRpcIsKernelModeCaller
0x18000dd70  test    eax, eax
0x18000dd72  jnz     short loc_18000DDAA
0x18000dd74  mov     eax, edi
0x18000dd76  movzx   ecx, di
0x18000dd79  and     eax, 1FFF0000h
0x18000dd7e  cmp     eax, 70000h
0x18000dd83  cmovnz  ecx, edi; exception
0x18000dd86  call    cs:__imp_RpcRaiseException
0x18000dd8d  nop     dword ptr [rax+rax+00h]
0x18000dd92  int     3; Trap to Debugger
0x18000dd93  lea     r8, [rbp+var_20]
0x18000dd97  mov     ecx, 48h ; 'H'; dwBytes
0x18000dd9c  call    WfpMemAlloc25B
0x18000dda1  mov     rbx, [rbp+var_20]
0x18000dda5  mov     rdi, rax
0x18000dda8  jmp     short loc_18000DD5D
0x18000ddaa  mov     rcx, rdi
0x18000ddad  call    WfpErrorToNtStatus
0x18000ddb2  mov     ecx, eax; exception
0x18000ddb4  call    cs:__imp_RpcRaiseException
0x18000ddbb  nop     dword ptr [rax+rax+00h]
0x18000ddc0  int     3; Trap to Debugger
0x18000ddc1  mov     r8d, 0C0000017h
0x18000ddc7  lea     rdx, aHeapalloc; "HeapAlloc"
0x18000ddce  call    WfpReportSysErrorAsNtStatus
0x18000ddd3  mov     rdi, rax
0x18000ddd6  test    rax, rax
0x18000ddd9  jz      short loc_18000DD5D
0x18000dddb  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
0x18000dde2  mov     rcx, rax
0x18000dde5  call    WfpReportError
0x18000ddea  jmp     loc_18000DD5D
0x18000ddef  mov     rcx, cs:gWfpHeap; hHeap
0x18000ddf6  mov     r8, rax; lpMem
0x18000ddf9  xor     edx, edx; dwFlags
0x18000ddfb  call    cs:__imp_HeapSize
0x18000de02  nop     dword ptr [rax+rax+00h]
0x18000de07  lock add cs:gWfpHeapBytesAllocated, eax
0x18000de0e  jmp     loc_18000DD5D
0x18000de13  mov     [r14], rsi
0x18000de16  jmp     loc_18000DCCC
```
