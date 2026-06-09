# BiEnumerateWorkItemsForPackageNameEx

- ea: `0x180002740`
- end: `0x180002845`
- name: `BiEnumerateWorkItemsForPackageNameEx`
- size: `261`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180002740`
- `0x180003228`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x1800027a4`
- `ntdll!RtlLengthSid` at `0x1800027a4`
- `RPCRT4!NdrClientCall3` at `0x180002805`
- `RPCRT4!NdrClientCall3` at `0x180002805`
- `RPCRT4!RpcExceptionFilter` at `0x18000386e`
- `RPCRT4!RpcExceptionFilter` at `0x18000386e`
- `RPCRT4!RpcBindingFree` at `0x18000282f`
- `RPCRT4!RpcBindingFree` at `0x18000282f`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000281b`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000281b`

## pseudocode

```c
__int64 __fastcall BiEnumerateWorkItemsForPackageNameEx(
        unsigned __int16 *a1,
        void *a2,
        int a3,
        int a4,
        __int64 a5,
        __int64 a6)
{
  int Pointer; // ebx
  __int64 v10; // r14
  int v11; // edi
  ULONG v12; // ecx
  RPC_BINDING_HANDLE Binding; // [rsp+B0h] [rbp+8h] BYREF

  Binding = 0;
  if ( a1 )
  {
    if ( (*(_BYTE *)a1 & 1) != 0 )
      return (unsigned int)-1073741811;
    v10 = *((_QWORD *)a1 + 1);
    v11 = *a1 >> 1;
  }
  else
  {
    v10 = 0;
    v11 = 0;
  }
  Pointer = BipCreateRpcBinding(&Binding);
  if ( Pointer >= 0 )
  {
    if ( a2 )
      v12 = RtlLengthSid(a2);
    else
      v12 = 0;
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0xEu,
                              0,
                              Binding,
                              v10,
                              v11,
                              a2,
                              v12,
                              a3,
                              a4,
                              a5,
                              a6).Pointer;
    RpcBindingFree(&Binding);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180002740  mov     rax, rsp
0x180002743  push    rbx
0x180002744  push    rsi
0x180002745  push    rdi
0x180002746  push    r12
0x180002748  push    r14
0x18000274a  push    r15
0x18000274c  sub     rsp, 78h
0x180002750  mov     r15d, r9d
0x180002753  mov     r12d, r8d
0x180002756  mov     rsi, rdx
0x180002759  mov     qword ptr [rax+8], 0
0x180002761  test    rcx, rcx
0x180002764  jz      short loc_180002780
0x180002766  test    byte ptr [rcx], 1
0x180002769  jz      short loc_180002775
0x18000276b  mov     ebx, 0C000000Dh
0x180002770  jmp     loc_180002835
0x180002775  mov     r14, [rcx+8]
0x180002779  movzx   edi, word ptr [rcx]
0x18000277c  shr     edi, 1
0x18000277e  jmp     short loc_180002785
0x180002780  xor     r14d, r14d
0x180002783  xor     edi, edi
0x180002785  lea     rcx, [rsp+0A8h+Binding]
0x18000278d  call    BipCreateRpcBinding
0x180002792  mov     ebx, eax
0x180002794  test    eax, eax
0x180002796  js      loc_180002835
0x18000279c  test    rsi, rsi
0x18000279f  jz      short loc_1800027AE
0x1800027a1  mov     rcx, rsi; Sid
0x1800027a4  call    cs:__imp_RtlLengthSid
0x1800027aa  mov     ecx, eax
0x1800027ac  jmp     short loc_1800027B0
0x1800027ae  xor     ecx, ecx
0x1800027b0  mov     [rsp+0A8h+var_40], 0
0x1800027b9  mov     rax, [rsp+0A8h+arg_28]
0x1800027c1  mov     [rsp+0A8h+var_50], rax
0x1800027c6  mov     rax, [rsp+0A8h+arg_20]
0x1800027ce  mov     [rsp+0A8h+var_58], rax
0x1800027d3  mov     [rsp+0A8h+var_60], r15d
0x1800027d8  mov     [rsp+0A8h+var_68], r12d
0x1800027dd  mov     [rsp+0A8h+var_70], ecx
0x1800027e1  mov     [rsp+0A8h+var_78], rsi
0x1800027e6  mov     [rsp+0A8h+var_80], edi
0x1800027ea  mov     [rsp+0A8h+var_88], r14
0x1800027ef  mov     r9, [rsp+0A8h+Binding]
0x1800027f7  xor     r8d, r8d; pReturnValue
0x1800027fa  lea     edx, [r8+0Eh]; nProcNum
0x1800027fe  lea     rcx, pProxyInfo; pProxyInfo
0x180002805  call    cs:__imp_NdrClientCall3
0x18000280b  mov     rbx, rax
0x18000280e  mov     [rsp+0A8h+var_40], rax
0x180002813  mov     [rsp+0A8h+var_48], eax
0x180002817  jmp     short loc_180002827
0x180002819  mov     ecx, eax; Status
0x18000281b  call    cs:__imp_I_RpcMapWin32Status
0x180002821  mov     ebx, eax
0x180002823  mov     [rsp+0A8h+var_48], eax
0x180002827  lea     rcx, [rsp+0A8h+Binding]; Binding
0x18000282f  call    cs:__imp_RpcBindingFree
0x180002835  mov     eax, ebx
0x180002837  add     rsp, 78h
0x18000283b  pop     r15
0x18000283d  pop     r14
0x18000283f  pop     r12
0x180002841  pop     rdi
0x180002842  pop     rsi
0x180002843  pop     rbx
0x180002844  retn
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
