# BiActivateInBackgroundEx

- ea: `0x1800019f0`
- end: `0x180001c39`
- name: `BiActivateInBackgroundEx`
- size: `585`
- prototype: `__int64 __fastcall(int, int, int, int, PSID Sid, __int64, __int64, __int64, int, int, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180001970`

## callees

- `0x1800019f0`
- `0x180003228`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180001acb`
- `ntdll!RtlLengthSid` at `0x180001acb`
- `RPCRT4!NdrClientCall3` at `0x180001be4`
- `RPCRT4!NdrClientCall3` at `0x180001be4`
- `RPCRT4!RpcExceptionFilter` at `0x180003849`
- `RPCRT4!RpcExceptionFilter` at `0x180003849`
- `RPCRT4!RpcBindingFree` at `0x180001c17`
- `RPCRT4!RpcBindingFree` at `0x180001c17`
- `RPCRT4!I_RpcMapWin32Status` at `0x180001c00`
- `RPCRT4!I_RpcMapWin32Status` at `0x180001c00`

## pseudocode

```c
__int64 __fastcall BiActivateInBackgroundEx(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 *a4,
        PSID Sid,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        int a9,
        int a10,
        __int64 a11,
        __int64 a12,
        int a13,
        __int64 a14)
{
  int v14; // r15d
  int v15; // r12d
  int v16; // r13d
  __int64 v17; // r14
  int v18; // edi
  int Pointer; // ebx
  CLIENT_CALL_RETURN v20; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+C8h] [rbp-60h] BYREF
  __int64 v23; // [rsp+D0h] [rbp-58h]
  __int64 v24; // [rsp+D8h] [rbp-50h]
  __int64 v25; // [rsp+E0h] [rbp-48h]
  CLIENT_CALL_RETURN v26; // [rsp+E8h] [rbp-40h]
  ULONG v30; // [rsp+148h] [rbp+20h]

  Binding = 0;
  if ( a4 && a6 && a7 && Sid && (*(_BYTE *)a4 & 1) == 0 && (*(_BYTE *)a6 & 1) == 0 && (*(_BYTE *)a7 & 1) == 0 )
  {
    v25 = *((_QWORD *)a4 + 1);
    v14 = *a4 >> 1;
    v24 = *((_QWORD *)a6 + 1);
    v15 = *a6 >> 1;
    v23 = *((_QWORD *)a7 + 1);
    v16 = *a7 >> 1;
    if ( a8 )
    {
      v17 = *((_QWORD *)a8 + 1);
      v18 = *a8 >> 1;
    }
    else
    {
      v17 = 0;
      v18 = 0;
    }
    v30 = RtlLengthSid(Sid);
    Pointer = BipCreateRpcBinding(&Binding);
    if ( Pointer >= 0 )
    {
      v26.Simple = 0;
      v20.Pointer = NdrClientCall3(
                      (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                      1u,
                      0,
                      Binding,
                      a1,
                      a2,
                      a3,
                      v25,
                      v14,
                      Sid,
                      v30,
                      v24,
                      v15,
                      v23,
                      v16,
                      v17,
                      v18,
                      a9,
                      a10,
                      a11,
                      a12,
                      a13,
                      a14).Pointer;
      Pointer = (int)v20.Pointer;
      v26.Pointer = v20.Pointer;
      RpcBindingFree(&Binding);
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x1800019f0  mov     rax, rsp
0x1800019f3  mov     [rax+18h], r8
0x1800019f7  mov     [rax+10h], rdx
0x1800019fb  mov     [rax+8], rcx
0x1800019ff  push    rbx
0x180001a00  push    rsi
0x180001a01  push    rdi
0x180001a02  push    r12
0x180001a04  push    r13
0x180001a06  push    r14
0x180001a08  push    r15
0x180001a0a  sub     rsp, 0F0h
0x180001a11  mov     qword ptr [rax-60h], 0
0x180001a19  test    r9, r9
0x180001a1c  jz      loc_180001C1F
0x180001a22  mov     rax, [rsp+128h+arg_28]
0x180001a2a  test    rax, rax
0x180001a2d  jz      loc_180001C1F
0x180001a33  mov     r10, [rsp+128h+arg_30]
0x180001a3b  test    r10, r10
0x180001a3e  jz      loc_180001C1F
0x180001a44  mov     rsi, [rsp+128h+Sid]
0x180001a4c  test    rsi, rsi
0x180001a4f  jz      loc_180001C1F
0x180001a55  test    byte ptr [r9], 1
0x180001a59  jnz     loc_180001C1F
0x180001a5f  test    byte ptr [rax], 1
0x180001a62  jnz     loc_180001C1F
0x180001a68  test    byte ptr [r10], 1
0x180001a6c  jnz     loc_180001C1F
0x180001a72  mov     rcx, [r9+8]
0x180001a76  mov     [rsp+128h+var_48], rcx
0x180001a7e  movzx   r15d, word ptr [r9]
0x180001a82  shr     r15d, 1
0x180001a85  mov     rcx, [rax+8]
0x180001a89  mov     [rsp+128h+var_50], rcx
0x180001a91  movzx   r12d, word ptr [rax]
0x180001a95  shr     r12d, 1
0x180001a98  mov     rax, [r10+8]
0x180001a9c  mov     [rsp+128h+var_58], rax
0x180001aa4  movzx   r13d, word ptr [r10]
0x180001aa8  shr     r13d, 1
0x180001aab  mov     rax, [rsp+128h+arg_38]
0x180001ab3  test    rax, rax
0x180001ab6  jz      short loc_180001AC3
0x180001ab8  mov     r14, [rax+8]
0x180001abc  movzx   edi, word ptr [rax]
0x180001abf  shr     edi, 1
0x180001ac1  jmp     short loc_180001AC8
0x180001ac3  xor     r14d, r14d
0x180001ac6  xor     edi, edi
0x180001ac8  mov     rcx, rsi; Sid
0x180001acb  call    cs:__imp_RtlLengthSid
0x180001ad1  mov     [rsp+128h+arg_18], eax
0x180001ad8  lea     rcx, [rsp+128h+Binding]
0x180001ae0  call    BipCreateRpcBinding
0x180001ae5  mov     ebx, eax
0x180001ae7  test    eax, eax
0x180001ae9  js      loc_180001C24
0x180001aef  mov     [rsp+128h+var_40], 0
0x180001afb  mov     rcx, [rsp+128h+arg_68]
0x180001b03  mov     [rsp+128h+var_78], rcx
0x180001b0b  mov     eax, [rsp+128h+arg_60]
0x180001b12  mov     [rsp+128h+var_80], eax
0x180001b19  mov     rax, [rsp+128h+arg_58]
0x180001b21  mov     [rsp+128h+var_88], rax
0x180001b29  mov     rax, [rsp+128h+arg_50]
0x180001b31  mov     [rsp+128h+var_90], rax
0x180001b39  mov     eax, [rsp+128h+arg_48]
0x180001b40  mov     [rsp+128h+var_98], eax
0x180001b47  mov     eax, [rsp+128h+arg_40]
0x180001b4e  mov     [rsp+128h+var_A0], eax
0x180001b55  mov     [rsp+128h+var_A8], edi
0x180001b5c  mov     [rsp+128h+var_B0], r14
0x180001b61  mov     [rsp+128h+var_B8], r13d
0x180001b66  mov     rax, [rsp+128h+var_58]
0x180001b6e  mov     [rsp+128h+var_C0], rax
0x180001b73  mov     [rsp+128h+var_C8], r12d
0x180001b78  mov     rax, [rsp+128h+var_50]
0x180001b80  mov     [rsp+128h+var_D0], rax
0x180001b85  mov     eax, [rsp+128h+arg_18]
0x180001b8c  mov     [rsp+128h+var_D8], eax
0x180001b90  mov     [rsp+128h+var_E0], rsi
0x180001b95  mov     [rsp+128h+var_E8], r15d
0x180001b9a  mov     rax, [rsp+128h+var_48]
0x180001ba2  mov     [rsp+128h+var_F0], rax
0x180001ba7  mov     rax, [rsp+128h+arg_10]
0x180001baf  mov     [rsp+128h+var_F8], rax
0x180001bb4  mov     rax, [rsp+128h+arg_8]
0x180001bbc  mov     [rsp+128h+var_100], rax
0x180001bc1  mov     rax, [rsp+128h+arg_0]
0x180001bc9  mov     [rsp+128h+var_108], rax
0x180001bce  mov     r9, [rsp+128h+Binding]
0x180001bd6  xor     r8d, r8d; pReturnValue
0x180001bd9  lea     edx, [r8+1]; nProcNum
0x180001bdd  lea     rcx, pProxyInfo; pProxyInfo
0x180001be4  call    cs:__imp_NdrClientCall3
0x180001bea  mov     rbx, rax
0x180001bed  mov     [rsp+128h+var_40], rax
0x180001bf5  mov     [rsp+128h+var_68], eax
0x180001bfc  jmp     short loc_180001C0F
0x180001bfe  mov     ecx, eax; Status
0x180001c00  call    cs:__imp_I_RpcMapWin32Status
0x180001c06  mov     ebx, eax
0x180001c08  mov     [rsp+128h+var_68], eax
0x180001c0f  lea     rcx, [rsp+128h+Binding]; Binding
0x180001c17  call    cs:__imp_RpcBindingFree
0x180001c1d  jmp     short loc_180001C24
0x180001c1f  mov     ebx, 0C000000Dh
0x180001c24  mov     eax, ebx
0x180001c26  add     rsp, 0F0h
0x180001c2d  pop     r15
0x180001c2f  pop     r14
0x180001c31  pop     r13
0x180001c33  pop     r12
0x180001c35  pop     rdi
0x180001c36  pop     rsi
0x180001c37  pop     rbx
0x180001c38  retn
0x180003838  push    rbp
0x18000383a  sub     rsp, 0C0h
0x180003841  mov     rbp, rdx
0x180003844  mov     rcx, [rcx]
0x180003847  mov     ecx, [rcx]; ExceptionCode
0x180003849  call    cs:__imp_RpcExceptionFilter
0x18000384f  nop
0x180003850  add     rsp, 0C0h
0x180003857  pop     rbp
0x180003858  retn
```
