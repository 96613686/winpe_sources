# BiCreateEventForPackageName

- ea: `0x180002170`
- end: `0x180002286`
- name: `BiCreateEventForPackageName`
- size: `278`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int16 *, void *, int, __int64, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180002170`
- `0x180003228`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x1800021d9`
- `ntdll!RtlLengthSid` at `0x1800021d9`
- `RPCRT4!NdrClientCall3` at `0x180002243`
- `RPCRT4!NdrClientCall3` at `0x180002243`
- `RPCRT4!RpcExceptionFilter` at `0x180003890`
- `RPCRT4!RpcExceptionFilter` at `0x180003890`
- `RPCRT4!RpcBindingFree` at `0x18000226d`
- `RPCRT4!RpcBindingFree` at `0x18000226d`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002259`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002259`

## pseudocode

```c
__int64 __fastcall BiCreateEventForPackageName(
        __int64 a1,
        __int64 a2,
        unsigned __int16 *a3,
        void *a4,
        int a5,
        __int64 a6,
        int a7)
{
  int Pointer; // ebx
  __int64 v11; // r14
  int v12; // edi
  ULONG v13; // ecx
  RPC_BINDING_HANDLE Binding; // [rsp+D0h] [rbp+18h] BYREF

  Binding = 0;
  if ( a3 )
  {
    if ( (*(_BYTE *)a3 & 1) != 0 )
      return (unsigned int)-1073741811;
    v11 = *((_QWORD *)a3 + 1);
    v12 = *a3 >> 1;
  }
  else
  {
    v11 = 0;
    v12 = 0;
  }
  Pointer = BipCreateRpcBinding(&Binding);
  if ( Pointer >= 0 )
  {
    if ( a4 )
      v13 = RtlLengthSid(a4);
    else
      v13 = 0;
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              7u,
                              0,
                              Binding,
                              a1,
                              a2,
                              v11,
                              v12,
                              a4,
                              v13,
                              a5,
                              a6,
                              a7).Pointer;
    RpcBindingFree(&Binding);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180002170  mov     rax, rsp
0x180002173  push    rbx
0x180002174  push    rsi
0x180002175  push    rdi
0x180002176  push    r12
0x180002178  push    r14
0x18000217a  push    r15
0x18000217c  sub     rsp, 88h
0x180002183  mov     rsi, r9
0x180002186  mov     r15, rdx
0x180002189  mov     r12, rcx
0x18000218c  mov     qword ptr [rax+18h], 0
0x180002194  test    r8, r8
0x180002197  jz      short loc_1800021B5
0x180002199  test    byte ptr [r8], 1
0x18000219d  jz      short loc_1800021A9
0x18000219f  mov     ebx, 0C000000Dh
0x1800021a4  jmp     loc_180002273
0x1800021a9  mov     r14, [r8+8]
0x1800021ad  movzx   edi, word ptr [r8]
0x1800021b1  shr     edi, 1
0x1800021b3  jmp     short loc_1800021BA
0x1800021b5  xor     r14d, r14d
0x1800021b8  xor     edi, edi
0x1800021ba  lea     rcx, [rsp+0B8h+Binding]
0x1800021c2  call    BipCreateRpcBinding
0x1800021c7  mov     ebx, eax
0x1800021c9  test    eax, eax
0x1800021cb  js      loc_180002273
0x1800021d1  test    rsi, rsi
0x1800021d4  jz      short loc_1800021E3
0x1800021d6  mov     rcx, rsi; Sid
0x1800021d9  call    cs:__imp_RtlLengthSid
0x1800021df  mov     ecx, eax
0x1800021e1  jmp     short loc_1800021E5
0x1800021e3  xor     ecx, ecx
0x1800021e5  mov     [rsp+0B8h+var_40], 0
0x1800021ee  mov     eax, [rsp+0B8h+arg_30]
0x1800021f5  mov     [rsp+0B8h+var_58], eax
0x1800021f9  mov     rax, [rsp+0B8h+arg_28]
0x180002201  mov     [rsp+0B8h+var_60], rax
0x180002206  mov     eax, [rsp+0B8h+arg_20]
0x18000220d  mov     [rsp+0B8h+var_68], eax
0x180002211  mov     [rsp+0B8h+var_70], ecx
0x180002215  mov     [rsp+0B8h+var_78], rsi
0x18000221a  mov     [rsp+0B8h+var_80], edi
0x18000221e  mov     [rsp+0B8h+var_88], r14
0x180002223  mov     [rsp+0B8h+var_90], r15
0x180002228  mov     [rsp+0B8h+var_98], r12
0x18000222d  mov     r9, [rsp+0B8h+Binding]
0x180002235  xor     r8d, r8d; pReturnValue
0x180002238  lea     edx, [r8+7]; nProcNum
0x18000223c  lea     rcx, pProxyInfo; pProxyInfo
0x180002243  call    cs:__imp_NdrClientCall3
0x180002249  mov     rbx, rax
0x18000224c  mov     [rsp+0B8h+var_40], rax
0x180002251  mov     [rsp+0B8h+var_48], eax
0x180002255  jmp     short loc_180002265
0x180002257  mov     ecx, eax; Status
0x180002259  call    cs:__imp_I_RpcMapWin32Status
0x18000225f  mov     ebx, eax
0x180002261  mov     [rsp+0B8h+var_48], eax
0x180002265  lea     rcx, [rsp+0B8h+Binding]; Binding
0x18000226d  call    cs:__imp_RpcBindingFree
0x180002273  mov     eax, ebx
0x180002275  add     rsp, 88h
0x18000227c  pop     r15
0x18000227e  pop     r14
0x180002280  pop     r12
0x180002282  pop     rdi
0x180002283  pop     rsi
0x180002284  pop     rbx
0x180002285  retn
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
