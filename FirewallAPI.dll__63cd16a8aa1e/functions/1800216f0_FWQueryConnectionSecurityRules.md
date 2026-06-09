# FWQueryConnectionSecurityRules

- ea: `0x1800216f0`
- end: `0x18002181b`
- name: `FWQueryConnectionSecurityRules`
- size: `299`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005954`
- `0x180009fb0`
- `0x1800216f0`
- `0x18003104c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18002172b`
- `ntdll!EtwEventWrite` at `0x180021806`
- `ntdll!EtwEventWrite` at `0x18002172b`
- `ntdll!EtwEventWrite` at `0x180021806`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002175f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18002175f`

## pseudocode

```c
__int64 __fastcall FWQueryConnectionSecurityRules(__int64 a1, __int64 a2, __int16 a3, __int64 a4, __int64 a5)
{
  unsigned int v9; // eax
  unsigned int v10; // ebx

  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_QueryConnectionSecurityRules, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 185, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  GetTickCount64();
  v9 = Int_FWQueryObject(
         1,
         (unsigned int)FWVerifyConnectionSecurityRuleQuery,
         (unsigned int)RPC_FWQueryConnectionSecurityRules2_10,
         (unsigned int)RRPC_FWQueryConnectionSecurityRules2_10,
         (__int64)Int_RPC_FWEnumConnectionSecurityRules2_0,
         (__int64)Int_RRPC_FWEnumConnectionSecurityRules2_0,
         a1,
         a2,
         a3,
         a4,
         a5,
         0);
  v10 = v9;
  if ( v9 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 186, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v9);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_QueryConnectionSecurityRules, 0, 0);
  return v10;
}

```

## disassembly

```asm
0x1800216f0  push    rbx
0x1800216f2  push    rbp
0x1800216f3  push    rsi
0x1800216f4  push    rdi
0x1800216f5  push    r14
0x1800216f7  push    r15
0x1800216f9  sub     rsp, 68h
0x1800216fd  mov     r14, [rsp+98h+arg_20]
0x180021705  mov     rbx, rcx
0x180021708  mov     rcx, cs:g_Provider
0x18002170f  mov     rbp, r9
0x180021712  movzx   esi, r8w
0x180021716  mov     rdi, rdx
0x180021719  test    rcx, rcx
0x18002171c  jz      short loc_180021731
0x18002171e  xor     r9d, r9d
0x180021721  lea     rdx, MPS_CLNT_API_Enter_QueryConnectionSecurityRules
0x180021728  xor     r8d, r8d
0x18002172b  call    cs:__imp_EtwEventWrite
0x180021731  mov     rcx, cs:WPP_GLOBAL_Control
0x180021738  lea     r15, WPP_GLOBAL_Control
0x18002173f  cmp     rcx, r15
0x180021742  jz      short loc_18002175F
0x180021744  test    byte ptr [rcx+1Ch], 8
0x180021748  jz      short loc_18002175F
0x18002174a  mov     rcx, [rcx+10h]
0x18002174e  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180021755  mov     edx, 0B9h
0x18002175a  call    WPP_SF_
0x18002175f  call    cs:__imp_GetTickCount64
0x180021765  mov     [rsp+98h+var_40], 0
0x18002176d  lea     rax, ?Int_RRPC_FWEnumConnectionSecurityRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RRPC_FWEnumConnectionSecurityRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x180021774  mov     [rsp+98h+var_48], r14
0x180021779  lea     r9, RRPC_FWQueryConnectionSecurityRules2_10
0x180021780  mov     [rsp+98h+var_50], rbp
0x180021785  lea     r8, RPC_FWQueryConnectionSecurityRules2_10
0x18002178c  mov     [rsp+98h+var_58], si
0x180021791  lea     rdx, FWVerifyConnectionSecurityRuleQuery
0x180021798  mov     [rsp+98h+var_60], rdi
0x18002179d  mov     ecx, 1
0x1800217a2  mov     [rsp+98h+var_68], rbx
0x1800217a7  mov     [rsp+98h+var_70], rax
0x1800217ac  lea     rax, ?Int_RPC_FWEnumConnectionSecurityRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RPC_FWEnumConnectionSecurityRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x1800217b3  mov     [rsp+98h+var_78], rax
0x1800217b8  call    Int_FWQueryObject
0x1800217bd  mov     ebx, eax
0x1800217bf  test    eax, eax
0x1800217c1  jz      short loc_1800217ED
0x1800217c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800217ca  cmp     rcx, r15
0x1800217cd  jz      short loc_1800217ED
0x1800217cf  test    byte ptr [rcx+1Ch], 1
0x1800217d3  jz      short loc_1800217ED
0x1800217d5  mov     rcx, [rcx+10h]
0x1800217d9  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x1800217e0  mov     edx, 0BAh
0x1800217e5  mov     r9d, eax
0x1800217e8  call    WPP_SF_d
0x1800217ed  mov     rcx, cs:g_Provider
0x1800217f4  test    rcx, rcx
0x1800217f7  jz      short loc_18002180C
0x1800217f9  xor     r9d, r9d
0x1800217fc  lea     rdx, MPS_CLNT_API_Exit_QueryConnectionSecurityRules
0x180021803  xor     r8d, r8d
0x180021806  call    cs:__imp_EtwEventWrite
0x18002180c  mov     eax, ebx
0x18002180e  add     rsp, 68h
0x180021812  pop     r15
0x180021814  pop     r14
0x180021816  pop     rdi
0x180021817  pop     rsi
0x180021818  pop     rbp
0x180021819  pop     rbx
0x18002181a  retn
```
