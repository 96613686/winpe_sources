# BiCreateEvent

- ea: `0x180002040`
- end: `0x180002161`
- name: `BiCreateEvent`
- size: `289`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int16 *, void *, int, __int64, int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180002040`
- `0x180003228`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x1800020a9`
- `ntdll!RtlLengthSid` at `0x1800020a9`
- `RPCRT4!NdrClientCall3` at `0x18000211e`
- `RPCRT4!NdrClientCall3` at `0x18000211e`
- `RPCRT4!RpcBindingFree` at `0x180002148`
- `RPCRT4!RpcBindingFree` at `0x180002148`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002134`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002134`

## pseudocode

```c
__int64 __fastcall BiCreateEvent(
        __int64 a1,
        __int64 a2,
        unsigned __int16 *a3,
        void *a4,
        int a5,
        __int64 a6,
        int a7,
        int a8)
{
  int Pointer; // ebx
  __int64 v12; // r14
  int v13; // edi
  ULONG v14; // ecx
  RPC_BINDING_HANDLE Binding; // [rsp+D0h] [rbp+18h] BYREF

  Binding = 0;
  if ( a3 )
  {
    if ( (*(_BYTE *)a3 & 1) != 0 )
      return (unsigned int)-1073741811;
    v12 = *((_QWORD *)a3 + 1);
    v13 = *a3 >> 1;
  }
  else
  {
    v12 = 0;
    v13 = 0;
  }
  Pointer = BipCreateRpcBinding(&Binding);
  if ( Pointer >= 0 )
  {
    if ( a4 )
      v14 = RtlLengthSid(a4);
    else
      v14 = 0;
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              6u,
                              0,
                              Binding,
                              a1,
                              a2,
                              v12,
                              v13,
                              a4,
                              v14,
                              a5,
                              a6,
                              a7,
                              a8).Pointer;
    RpcBindingFree(&Binding);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180002040  mov     rax, rsp
0x180002043  push    rbx
0x180002044  push    rsi
0x180002045  push    rdi
0x180002046  push    r12
0x180002048  push    r14
0x18000204a  push    r15
0x18000204c  sub     rsp, 88h
0x180002053  mov     rsi, r9
0x180002056  mov     r15, rdx
0x180002059  mov     r12, rcx
0x18000205c  mov     qword ptr [rax+18h], 0
0x180002064  test    r8, r8
0x180002067  jz      short loc_180002085
0x180002069  test    byte ptr [r8], 1
0x18000206d  jz      short loc_180002079
0x18000206f  mov     ebx, 0C000000Dh
0x180002074  jmp     loc_18000214E
0x180002079  mov     r14, [r8+8]
0x18000207d  movzx   edi, word ptr [r8]
0x180002081  shr     edi, 1
0x180002083  jmp     short loc_18000208A
0x180002085  xor     r14d, r14d
0x180002088  xor     edi, edi
0x18000208a  lea     rcx, [rsp+0B8h+Binding]
0x180002092  call    BipCreateRpcBinding
0x180002097  mov     ebx, eax
0x180002099  test    eax, eax
0x18000209b  js      loc_18000214E
0x1800020a1  test    rsi, rsi
0x1800020a4  jz      short loc_1800020B3
0x1800020a6  mov     rcx, rsi; Sid
0x1800020a9  call    cs:__imp_RtlLengthSid
0x1800020af  mov     ecx, eax
0x1800020b1  jmp     short loc_1800020B5
0x1800020b3  xor     ecx, ecx
0x1800020b5  mov     [rsp+0B8h+var_40], 0
0x1800020be  mov     eax, [rsp+0B8h+arg_38]
0x1800020c5  mov     [rsp+0B8h+var_50], eax
0x1800020c9  mov     eax, [rsp+0B8h+arg_30]
0x1800020d0  mov     [rsp+0B8h+var_58], eax
0x1800020d4  mov     rax, [rsp+0B8h+arg_28]
0x1800020dc  mov     [rsp+0B8h+var_60], rax
0x1800020e1  mov     eax, [rsp+0B8h+arg_20]
0x1800020e8  mov     [rsp+0B8h+var_68], eax
0x1800020ec  mov     [rsp+0B8h+var_70], ecx
0x1800020f0  mov     [rsp+0B8h+var_78], rsi
0x1800020f5  mov     [rsp+0B8h+var_80], edi
0x1800020f9  mov     [rsp+0B8h+var_88], r14
0x1800020fe  mov     [rsp+0B8h+var_90], r15
0x180002103  mov     [rsp+0B8h+var_98], r12
0x180002108  mov     r9, [rsp+0B8h+Binding]
0x180002110  xor     r8d, r8d; pReturnValue
0x180002113  lea     edx, [r8+6]; nProcNum
0x180002117  lea     rcx, pProxyInfo; pProxyInfo
0x18000211e  call    cs:__imp_NdrClientCall3
0x180002124  mov     rbx, rax
0x180002127  mov     [rsp+0B8h+var_40], rax
0x18000212c  mov     [rsp+0B8h+var_48], eax
0x180002130  jmp     short loc_180002140
0x180002132  mov     ecx, eax; Status
0x180002134  call    cs:__imp_I_RpcMapWin32Status
0x18000213a  mov     ebx, eax
0x18000213c  mov     [rsp+0B8h+var_48], eax
0x180002140  lea     rcx, [rsp+0B8h+Binding]; Binding
0x180002148  call    cs:__imp_RpcBindingFree
0x18000214e  mov     eax, ebx
0x180002150  add     rsp, 88h
0x180002157  pop     r15
0x180002159  pop     r14
0x18000215b  pop     r12
0x18000215d  pop     rdi
0x18000215e  pop     rsi
0x18000215f  pop     rbx
0x180002160  retn
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
