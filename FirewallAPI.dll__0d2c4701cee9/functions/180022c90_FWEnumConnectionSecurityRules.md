# FWEnumConnectionSecurityRules

- ea: `0x180022c90`
- end: `0x180022e66`
- name: `FWEnumConnectionSecurityRules`
- size: `470`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180021b60`
- `0x180027370`

## callees

- `0x180005e0c`
- `0x18000d980`
- `0x180022c90`
- `0x1800294b0`
- `0x18003336c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180022ce4`
- `ntdll!EtwEventWrite` at `0x180022e37`
- `ntdll!EtwEventWrite` at `0x180022ce4`
- `ntdll!EtwEventWrite` at `0x180022e37`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180022d1e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180022d1e`

## pseudocode

```c
__int64 __fastcall FWEnumConnectionSecurityRules(__int64 a1, int a2, int a3, __int16 a4, __int64 a5, __int64 a6)
{
  unsigned int v10; // eax
  unsigned int v11; // ebx
  __int16 v13; // [rsp+30h] [rbp-A9h]
  _QWORD v14[2]; // [rsp+50h] [rbp-89h] BYREF
  _QWORD v15[2]; // [rsp+60h] [rbp-79h] BYREF
  unsigned int (__fastcall *v16)(void *, void *, unsigned int, unsigned int, unsigned __int16, unsigned int *, void **); // [rsp+70h] [rbp-69h] BYREF
  __int16 v17; // [rsp+78h] [rbp-61h]
  __int64 (__fastcall *v18)(int, int, int, int, __int16, __int64, __int64); // [rsp+80h] [rbp-59h]
  __int16 v19; // [rsp+88h] [rbp-51h]
  __int64 (__fastcall *v20)(int, int, int, int, __int16, __int64, __int64); // [rsp+90h] [rbp-49h]
  __int16 v21; // [rsp+98h] [rbp-41h]
  unsigned int (__fastcall *v22)(void *, void *, unsigned int, unsigned int, unsigned __int16, unsigned int *, void **); // [rsp+A0h] [rbp-39h] BYREF
  __int16 v23; // [rsp+A8h] [rbp-31h]
  __int64 (__fastcall *v24)(int, int, int, int, __int16, __int64, __int64); // [rsp+B0h] [rbp-29h]
  __int16 v25; // [rsp+B8h] [rbp-21h]
  __int64 (__fastcall *v26)(int, int, int, int, __int16, __int64, __int64); // [rsp+C0h] [rbp-19h]
  __int16 v27; // [rsp+C8h] [rbp-11h]

  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_EnumConnectionSecurityRules, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  GetTickCount64();
  v16 = Int_RPC_FWEnumConnectionSecurityRules2_0;
  v18 = RPC_FWEnumConnectionSecurityRules2_10;
  v17 = 512;
  v19 = 522;
  v20 = RPC_FWEnumConnectionSecurityRules2_20;
  v15[1] = &v16;
  v22 = Int_RRPC_FWEnumConnectionSecurityRules2_0;
  v24 = RRPC_FWEnumConnectionSecurityRules2_10;
  v26 = RRPC_FWEnumConnectionSecurityRules2_20;
  v21 = 532;
  v23 = 512;
  v25 = 522;
  v27 = 532;
  v13 = a4;
  v14[1] = &v22;
  v15[0] = 3;
  v14[0] = 3;
  v10 = Int_FWEnumObject(1, v15, v14, a1, a2, a3, v13, a5, a6, 0);
  v11 = v10;
  if ( v10 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v10);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_EnumConnectionSecurityRules, 0, 0);
  return v11;
}

```

## disassembly

```asm
0x180022c90  push    rbp
0x180022c92  push    rbx
0x180022c93  push    rsi
0x180022c94  push    rdi
0x180022c95  push    r12
0x180022c97  push    r13
0x180022c99  push    r14
0x180022c9b  push    r15
0x180022c9d  lea     rbp, [rsp-0Fh]
0x180022ca2  sub     rsp, 0E8h
0x180022ca9  mov     rax, cs:__security_cookie
0x180022cb0  xor     rax, rsp
0x180022cb3  mov     [rbp+47h+var_50], rax
0x180022cb7  mov     r15, [rbp+47h+arg_20]
0x180022cbb  mov     rbx, rcx
0x180022cbe  mov     rcx, cs:g_Provider
0x180022cc5  movzx   r14d, r9w
0x180022cc9  mov     r12, [rbp+47h+arg_28]
0x180022ccd  mov     esi, r8d
0x180022cd0  mov     edi, edx
0x180022cd2  test    rcx, rcx
0x180022cd5  jz      short loc_180022CF0
0x180022cd7  xor     r9d, r9d
0x180022cda  lea     rdx, MPS_CLNT_API_Enter_EnumConnectionSecurityRules
0x180022ce1  xor     r8d, r8d
0x180022ce4  call    cs:__imp_EtwEventWrite
0x180022ceb  nop     dword ptr [rax+rax+00h]
0x180022cf0  mov     rcx, cs:WPP_GLOBAL_Control
0x180022cf7  lea     r13, WPP_GLOBAL_Control
0x180022cfe  cmp     rcx, r13
0x180022d01  jz      short loc_180022D1E
0x180022d03  test    byte ptr [rcx+1Ch], 8
0x180022d07  jz      short loc_180022D1E
0x180022d09  mov     rcx, [rcx+10h]
0x180022d0d  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180022d14  mov     edx, 75h ; 'u'
0x180022d19  call    WPP_SF_
0x180022d1e  call    cs:__imp_GetTickCount64
0x180022d25  nop     dword ptr [rax+rax+00h]
0x180022d2a  mov     r9d, 200h
0x180022d30  mov     [rsp+120h+var_D8], 0
0x180022d38  mov     [rsp+120h+var_E0], r12
0x180022d3d  lea     rax, ?Int_RPC_FWEnumConnectionSecurityRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RPC_FWEnumConnectionSecurityRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x180022d44  mov     [rbp+47h+var_B0], rax
0x180022d48  mov     ecx, 1
0x180022d4d  mov     [rsp+120h+var_E8], r15
0x180022d52  lea     rax, RPC_FWEnumConnectionSecurityRules2_10
0x180022d59  mov     [rbp+47h+var_A0], rax
0x180022d5d  lea     r8d, [r9+0Ah]
0x180022d61  lea     edx, [r9+14h]
0x180022d65  mov     [rbp+47h+var_A8], r9w
0x180022d6a  lea     rax, RPC_FWEnumConnectionSecurityRules2_20
0x180022d71  mov     [rbp+47h+var_98], r8w
0x180022d76  mov     [rbp+47h+var_90], rax
0x180022d7a  lea     rax, [rbp+47h+var_B0]
0x180022d7e  mov     [rbp+47h+var_B8], rax
0x180022d82  lea     rax, ?Int_RRPC_FWEnumConnectionSecurityRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RRPC_FWEnumConnectionSecurityRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x180022d89  mov     [rbp+47h+var_80], rax
0x180022d8d  lea     rax, RRPC_FWEnumConnectionSecurityRules2_10
0x180022d94  mov     [rbp+47h+var_70], rax
0x180022d98  lea     rax, RRPC_FWEnumConnectionSecurityRules2_20
0x180022d9f  mov     [rbp+47h+var_60], rax
0x180022da3  lea     rax, [rbp+47h+var_80]
0x180022da7  mov     [rbp+47h+var_88], dx
0x180022dab  mov     [rbp+47h+var_78], r9w
0x180022db0  mov     r9, rbx
0x180022db3  mov     [rbp+47h+var_68], r8w
0x180022db8  lea     r8, [rsp+120h+var_D0]
0x180022dbd  mov     [rbp+47h+var_58], dx
0x180022dc1  lea     rdx, [rbp+47h+var_C0]
0x180022dc5  mov     [rsp+120h+var_F0], r14w
0x180022dcb  mov     [rsp+120h+var_F8], esi
0x180022dcf  mov     [rsp+120h+var_C8], rax
0x180022dd4  mov     [rbp+47h+var_C0], 3
0x180022ddc  mov     [rsp+120h+var_D0], 3
0x180022de5  mov     [rsp+120h+var_100], edi
0x180022de9  call    Int_FWEnumObject
0x180022dee  mov     ebx, eax
0x180022df0  test    eax, eax
0x180022df2  jz      short loc_180022E1E
0x180022df4  mov     rcx, cs:WPP_GLOBAL_Control
0x180022dfb  cmp     rcx, r13
0x180022dfe  jz      short loc_180022E1E
0x180022e00  test    byte ptr [rcx+1Ch], 1
0x180022e04  jz      short loc_180022E1E
0x180022e06  mov     rcx, [rcx+10h]
0x180022e0a  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180022e11  mov     edx, 76h ; 'v'
0x180022e16  mov     r9d, eax
0x180022e19  call    WPP_SF_d
0x180022e1e  mov     rcx, cs:g_Provider
0x180022e25  test    rcx, rcx
0x180022e28  jz      short loc_180022E43
0x180022e2a  xor     r9d, r9d
0x180022e2d  lea     rdx, MPS_CLNT_API_Exit_EnumConnectionSecurityRules
0x180022e34  xor     r8d, r8d
0x180022e37  call    cs:__imp_EtwEventWrite
0x180022e3e  nop     dword ptr [rax+rax+00h]
0x180022e43  mov     eax, ebx
0x180022e45  mov     rcx, [rbp+47h+var_50]
0x180022e49  xor     rcx, rsp; StackCookie
0x180022e4c  call    __security_check_cookie
0x180022e51  add     rsp, 0E8h
0x180022e58  pop     r15
0x180022e5a  pop     r14
0x180022e5c  pop     r13
0x180022e5e  pop     r12
0x180022e60  pop     rdi
0x180022e61  pop     rsi
0x180022e62  pop     rbx
0x180022e63  pop     rbp
0x180022e64  retn
```
