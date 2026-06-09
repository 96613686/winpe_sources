# FWEnumConnectionSecurityRules

- ea: `0x180021440`
- end: `0x180021603`
- name: `FWEnumConnectionSecurityRules`
- size: `451`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180020370`
- `0x180025744`

## callees

- `0x180005954`
- `0x18000cd90`
- `0x180021440`
- `0x1800277b0`
- `0x18003104c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180021494`
- `ntdll!EtwEventWrite` at `0x1800215db`
- `ntdll!EtwEventWrite` at `0x180021494`
- `ntdll!EtwEventWrite` at `0x1800215db`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800214c8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800214c8`

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
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v10);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_EnumConnectionSecurityRules, 0, 0);
  return v11;
}

```

## disassembly

```asm
0x180021440  push    rbp
0x180021442  push    rbx
0x180021443  push    rsi
0x180021444  push    rdi
0x180021445  push    r12
0x180021447  push    r13
0x180021449  push    r14
0x18002144b  push    r15
0x18002144d  lea     rbp, [rsp-0Fh]
0x180021452  sub     rsp, 0E8h
0x180021459  mov     rax, cs:__security_cookie
0x180021460  xor     rax, rsp
0x180021463  mov     [rbp+47h+var_50], rax
0x180021467  mov     r15, [rbp+47h+arg_20]
0x18002146b  mov     rbx, rcx
0x18002146e  mov     rcx, cs:g_Provider
0x180021475  movzx   r14d, r9w
0x180021479  mov     r12, [rbp+47h+arg_28]
0x18002147d  mov     esi, r8d
0x180021480  mov     edi, edx
0x180021482  test    rcx, rcx
0x180021485  jz      short loc_18002149A
0x180021487  xor     r9d, r9d
0x18002148a  lea     rdx, MPS_CLNT_API_Enter_EnumConnectionSecurityRules
0x180021491  xor     r8d, r8d
0x180021494  call    cs:__imp_EtwEventWrite
0x18002149a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800214a1  lea     r13, WPP_GLOBAL_Control
0x1800214a8  cmp     rcx, r13
0x1800214ab  jz      short loc_1800214C8
0x1800214ad  test    byte ptr [rcx+1Ch], 8
0x1800214b1  jz      short loc_1800214C8
0x1800214b3  mov     rcx, [rcx+10h]
0x1800214b7  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x1800214be  mov     edx, 76h ; 'v'
0x1800214c3  call    WPP_SF_
0x1800214c8  call    cs:__imp_GetTickCount64
0x1800214ce  mov     r9d, 200h
0x1800214d4  mov     [rsp+120h+var_D8], 0
0x1800214dc  mov     [rsp+120h+var_E0], r12
0x1800214e1  lea     rax, ?Int_RPC_FWEnumConnectionSecurityRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RPC_FWEnumConnectionSecurityRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x1800214e8  mov     [rbp+47h+var_B0], rax
0x1800214ec  mov     ecx, 1
0x1800214f1  mov     [rsp+120h+var_E8], r15
0x1800214f6  lea     rax, RPC_FWEnumConnectionSecurityRules2_10
0x1800214fd  mov     [rbp+47h+var_A0], rax
0x180021501  lea     r8d, [r9+0Ah]
0x180021505  lea     edx, [r9+14h]
0x180021509  mov     [rbp+47h+var_A8], r9w
0x18002150e  lea     rax, RPC_FWEnumConnectionSecurityRules2_20
0x180021515  mov     [rbp+47h+var_98], r8w
0x18002151a  mov     [rbp+47h+var_90], rax
0x18002151e  lea     rax, [rbp+47h+var_B0]
0x180021522  mov     [rbp+47h+var_B8], rax
0x180021526  lea     rax, ?Int_RRPC_FWEnumConnectionSecurityRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RRPC_FWEnumConnectionSecurityRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x18002152d  mov     [rbp+47h+var_80], rax
0x180021531  lea     rax, RRPC_FWEnumConnectionSecurityRules2_10
0x180021538  mov     [rbp+47h+var_70], rax
0x18002153c  lea     rax, RRPC_FWEnumConnectionSecurityRules2_20
0x180021543  mov     [rbp+47h+var_60], rax
0x180021547  lea     rax, [rbp+47h+var_80]
0x18002154b  mov     [rbp+47h+var_88], dx
0x18002154f  mov     [rbp+47h+var_78], r9w
0x180021554  mov     r9, rbx
0x180021557  mov     [rbp+47h+var_68], r8w
0x18002155c  lea     r8, [rsp+120h+var_D0]
0x180021561  mov     [rbp+47h+var_58], dx
0x180021565  lea     rdx, [rbp+47h+var_C0]
0x180021569  mov     [rsp+120h+var_F0], r14w
0x18002156f  mov     [rsp+120h+var_F8], esi
0x180021573  mov     [rsp+120h+var_C8], rax
0x180021578  mov     [rbp+47h+var_C0], 3
0x180021580  mov     [rsp+120h+var_D0], 3
0x180021589  mov     [rsp+120h+var_100], edi
0x18002158d  call    Int_FWEnumObject
0x180021592  mov     ebx, eax
0x180021594  test    eax, eax
0x180021596  jz      short loc_1800215C2
0x180021598  mov     rcx, cs:WPP_GLOBAL_Control
0x18002159f  cmp     rcx, r13
0x1800215a2  jz      short loc_1800215C2
0x1800215a4  test    byte ptr [rcx+1Ch], 1
0x1800215a8  jz      short loc_1800215C2
0x1800215aa  mov     rcx, [rcx+10h]
0x1800215ae  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x1800215b5  mov     edx, 77h ; 'w'
0x1800215ba  mov     r9d, eax
0x1800215bd  call    WPP_SF_d
0x1800215c2  mov     rcx, cs:g_Provider
0x1800215c9  test    rcx, rcx
0x1800215cc  jz      short loc_1800215E1
0x1800215ce  xor     r9d, r9d
0x1800215d1  lea     rdx, MPS_CLNT_API_Exit_EnumConnectionSecurityRules
0x1800215d8  xor     r8d, r8d
0x1800215db  call    cs:__imp_EtwEventWrite
0x1800215e1  mov     eax, ebx
0x1800215e3  mov     rcx, [rbp+47h+var_50]
0x1800215e7  xor     rcx, rsp; StackCookie
0x1800215ea  call    __security_check_cookie
0x1800215ef  add     rsp, 0E8h
0x1800215f6  pop     r15
0x1800215f8  pop     r14
0x1800215fa  pop     r13
0x1800215fc  pop     r12
0x1800215fe  pop     rdi
0x1800215ff  pop     rsi
0x180021600  pop     rbx
0x180021601  pop     rbp
0x180021602  retn
```
