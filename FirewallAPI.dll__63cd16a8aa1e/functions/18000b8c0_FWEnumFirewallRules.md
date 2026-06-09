# FWEnumFirewallRules

- ea: `0x18000b8c0`
- end: `0x18000bba0`
- name: `FWEnumFirewallRules`
- size: `736`
- prototype: ``
- caller_count: `23`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180001e58`
- `0x1800021f0`
- `0x180002e3c`
- `0x180003b4c`
- `0x180003e10`
- `0x180003f80`
- `0x180004300`
- `0x180007880`
- `0x180009340`
- `0x18001d554`
- `0x18001e068`
- `0x180020370`
- `0x180025744`
- `0x180032ac0`
- `0x180032f90`
- `0x1800332c0`
- `0x180039168`
- `0x180042484`
- `0x180043fc8`
- `0x1800456b0`
- `0x180045c50`
- `0x180046370`
- `0x180047734`

## callees

- `0x180005954`
- `0x18000b8c0`
- `0x18000cd90`
- `0x1800277b0`
- `0x18003104c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000b920`
- `ntdll!EtwEventWrite` at `0x18000bb17`
- `ntdll!EtwEventWrite` at `0x18000b920`
- `ntdll!EtwEventWrite` at `0x18000bb17`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b93d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b93d`

## pseudocode

```c
__int64 __fastcall FWEnumFirewallRules(__int64 a1, int a2, int a3, __int16 a4, __int64 a5, __int64 a6)
{
  unsigned int v10; // ebx
  __int16 v12; // [rsp+30h] [rbp-D0h]
  _QWORD v13[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v14[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int (__fastcall *v15)(void *, void *, unsigned int, unsigned int, unsigned __int16, unsigned int *, void **); // [rsp+70h] [rbp-90h] BYREF
  __int16 v16; // [rsp+78h] [rbp-88h]
  __int64 (__fastcall *v17)(int, int, int, int, __int16, __int64, __int64); // [rsp+80h] [rbp-80h]
  __int16 v18; // [rsp+88h] [rbp-78h]
  __int64 (__fastcall *v19)(int, int, int, int, __int16, __int64, __int64); // [rsp+90h] [rbp-70h]
  __int16 v20; // [rsp+98h] [rbp-68h]
  __int64 (__fastcall *v21)(int, int, int, int, __int16, __int64, __int64); // [rsp+A0h] [rbp-60h]
  __int16 v22; // [rsp+A8h] [rbp-58h]
  __int64 (__fastcall *v23)(int, int, int, int, __int16, __int64, __int64); // [rsp+B0h] [rbp-50h]
  __int16 v24; // [rsp+B8h] [rbp-48h]
  __int64 (__fastcall *v25)(int, int, int, int, __int16, __int64, __int64); // [rsp+C0h] [rbp-40h]
  __int16 v26; // [rsp+C8h] [rbp-38h]
  __int64 (__fastcall *v27)(int, int, int, int, __int16, __int64, __int64); // [rsp+D0h] [rbp-30h]
  __int16 v28; // [rsp+D8h] [rbp-28h]
  __int64 (__fastcall *v29)(int, int, int, int, __int16, __int64, __int64); // [rsp+E0h] [rbp-20h]
  __int16 v30; // [rsp+E8h] [rbp-18h]
  __int64 (__fastcall *v31)(int, int, int, int, __int16, __int64, __int64); // [rsp+F0h] [rbp-10h]
  __int16 v32; // [rsp+F8h] [rbp-8h]
  unsigned int (__fastcall *v33)(void *, void *, unsigned int, unsigned int, unsigned __int16, unsigned int *, void **); // [rsp+100h] [rbp+0h] BYREF
  __int16 v34; // [rsp+108h] [rbp+8h]
  __int64 (__fastcall *v35)(int, int, int, int, __int16, __int64, __int64); // [rsp+110h] [rbp+10h]
  __int16 v36; // [rsp+118h] [rbp+18h]
  __int64 (__fastcall *v37)(int, int, int, int, __int16, __int64, __int64); // [rsp+120h] [rbp+20h]
  __int16 v38; // [rsp+128h] [rbp+28h]
  __int64 (__fastcall *v39)(int, int, int, int, __int16, __int64, __int64); // [rsp+130h] [rbp+30h]
  __int16 v40; // [rsp+138h] [rbp+38h]
  __int64 (__fastcall *v41)(int, int, int, int, __int16, __int64, __int64); // [rsp+140h] [rbp+40h]
  __int16 v42; // [rsp+148h] [rbp+48h]
  __int64 (__fastcall *v43)(int, int, int, int, __int16, __int64, __int64); // [rsp+150h] [rbp+50h]
  __int16 v44; // [rsp+158h] [rbp+58h]
  __int64 (__fastcall *v45)(int, int, int, int, __int16, __int64, __int64); // [rsp+160h] [rbp+60h]
  __int16 v46; // [rsp+168h] [rbp+68h]
  __int64 (__fastcall *v47)(int, int, int, int, __int16, __int64, __int64); // [rsp+170h] [rbp+70h]
  __int16 v48; // [rsp+178h] [rbp+78h]
  __int64 (__fastcall *v49)(int, int, int, int, __int16, __int64, __int64); // [rsp+180h] [rbp+80h]
  __int16 v50; // [rsp+188h] [rbp+88h]

  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_EnumFirewallRules, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  GetTickCount64();
  v15 = Int_RPC_FWEnumFirewallRules2_0;
  v16 = 512;
  v17 = RPC_FWEnumFirewallRules2_10;
  v12 = a4;
  v18 = 522;
  v26 = 538;
  v19 = RPC_FWEnumFirewallRules2_20;
  v28 = 539;
  v21 = RPC_FWEnumFirewallRules2_24;
  v30 = 543;
  v23 = RPC_FWEnumFirewallRules2_25;
  v44 = 538;
  v25 = RPC_FWEnumFirewallRules2_26;
  v46 = 539;
  v27 = RPC_FWEnumFirewallRules2_27;
  v48 = 543;
  v29 = RPC_FWEnumFirewallRules2_31;
  v31 = RPC_FWEnumFirewallRules2_33;
  v14[1] = &v15;
  v33 = Int_RRPC_FWEnumFirewallRules2_0;
  v34 = 512;
  v35 = RRPC_FWEnumFirewallRules2_10;
  v36 = 522;
  v37 = RRPC_FWEnumFirewallRules2_20;
  v39 = RRPC_FWEnumFirewallRules2_24;
  v41 = RRPC_FWEnumFirewallRules2_25;
  v43 = RRPC_FWEnumFirewallRules2_26;
  v45 = RRPC_FWEnumFirewallRules2_27;
  v47 = RRPC_FWEnumFirewallRules2_31;
  v49 = RRPC_FWEnumFirewallRules2_33;
  v13[1] = &v33;
  v20 = 532;
  v22 = 536;
  v24 = 537;
  v32 = 545;
  v14[0] = 9;
  v38 = 532;
  v40 = 536;
  v42 = 537;
  v50 = 545;
  v13[0] = 9;
  v10 = Int_FWEnumObject(0, v14, v13, a1, a2, a3, v12, a5, a6, 0);
  if ( v10 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v10);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_EnumFirewallRules, 0, 0);
  return v10;
}

```

## disassembly

```asm
0x18000b8c0  push    rbp
0x18000b8c2  push    rbx
0x18000b8c3  push    rsi
0x18000b8c4  push    rdi
0x18000b8c5  push    r12
0x18000b8c7  push    r13
0x18000b8c9  push    r14
0x18000b8cb  push    r15
0x18000b8cd  lea     rbp, [rsp-0A8h]
0x18000b8d5  sub     rsp, 1A8h
0x18000b8dc  mov     rax, cs:__security_cookie
0x18000b8e3  xor     rax, rsp
0x18000b8e6  mov     [rbp+0E0h+var_50], rax
0x18000b8ed  mov     r15, [rbp+0E0h+arg_20]
0x18000b8f4  mov     rbx, rcx
0x18000b8f7  mov     rcx, cs:g_Provider
0x18000b8fe  movzx   r14d, r9w
0x18000b902  mov     r12, [rbp+0E0h+arg_28]
0x18000b909  mov     esi, r8d
0x18000b90c  mov     edi, edx
0x18000b90e  test    rcx, rcx
0x18000b911  jz      short loc_18000B926
0x18000b913  xor     r9d, r9d
0x18000b916  lea     rdx, MPS_CLNT_API_Enter_EnumFirewallRules
0x18000b91d  xor     r8d, r8d
0x18000b920  call    cs:__imp_EtwEventWrite
0x18000b926  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b92d  lea     rax, WPP_GLOBAL_Control
0x18000b934  cmp     rcx, rax
0x18000b937  jnz     loc_18000BB42
0x18000b93d  call    cs:__imp_GetTickCount64
0x18000b943  lea     rax, ?Int_RPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x18000b94a  mov     [rsp+1E0h+var_198], 0
0x18000b952  mov     [rsp+1E0h+var_170], rax
0x18000b957  mov     r9d, 21Ah
0x18000b95d  mov     eax, 200h
0x18000b962  mov     [rsp+1E0h+var_1A0], r12
0x18000b967  mov     [rsp+1E0h+var_168], ax
0x18000b96c  mov     r8d, 21Bh
0x18000b972  lea     rax, RPC_FWEnumFirewallRules2_10
0x18000b979  mov     [rsp+1E0h+var_1A8], r15
0x18000b97e  mov     [rbp+0E0h+var_160], rax
0x18000b982  mov     edx, 21Fh
0x18000b987  mov     eax, 20Ah
0x18000b98c  mov     [rsp+1E0h+var_1B0], r14w
0x18000b992  mov     [rbp+0E0h+var_158], ax
0x18000b996  mov     r13d, 214h
0x18000b99c  lea     rax, RPC_FWEnumFirewallRules2_20
0x18000b9a3  mov     [rbp+0E0h+var_118], r9w
0x18000b9a8  mov     [rbp+0E0h+var_150], rax
0x18000b9ac  mov     r11d, 218h
0x18000b9b2  lea     rax, RPC_FWEnumFirewallRules2_24
0x18000b9b9  mov     [rbp+0E0h+var_108], r8w
0x18000b9be  mov     [rbp+0E0h+var_140], rax
0x18000b9c2  mov     r10d, 219h
0x18000b9c8  lea     rax, RPC_FWEnumFirewallRules2_25
0x18000b9cf  mov     [rbp+0E0h+var_F8], dx
0x18000b9d3  mov     [rbp+0E0h+var_130], rax
0x18000b9d7  mov     ecx, 221h
0x18000b9dc  lea     rax, RPC_FWEnumFirewallRules2_26
0x18000b9e3  mov     [rbp+0E0h+var_88], r9w
0x18000b9e8  mov     [rbp+0E0h+var_120], rax
0x18000b9ec  mov     r9, rbx
0x18000b9ef  lea     rax, RPC_FWEnumFirewallRules2_27
0x18000b9f6  mov     [rbp+0E0h+var_78], r8w
0x18000b9fb  mov     [rbp+0E0h+var_110], rax
0x18000b9ff  lea     r8, [rsp+1E0h+var_190]
0x18000ba04  lea     rax, RPC_FWEnumFirewallRules2_31
0x18000ba0b  mov     [rbp+0E0h+var_68], dx
0x18000ba0f  mov     [rbp+0E0h+var_100], rax
0x18000ba13  lea     rdx, [rsp+1E0h+var_180]
0x18000ba18  lea     rax, RPC_FWEnumFirewallRules2_33
0x18000ba1f  mov     [rsp+1E0h+var_1B8], esi
0x18000ba23  mov     [rbp+0E0h+var_F0], rax
0x18000ba27  lea     rax, [rsp+1E0h+var_170]
0x18000ba2c  mov     [rsp+1E0h+var_178], rax
0x18000ba31  lea     rax, ?Int_RRPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RRPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x18000ba38  mov     [rbp+0E0h+var_E0], rax
0x18000ba3c  mov     eax, 200h
0x18000ba41  mov     [rbp+0E0h+var_D8], ax
0x18000ba45  lea     rax, RRPC_FWEnumFirewallRules2_10
0x18000ba4c  mov     [rbp+0E0h+var_D0], rax
0x18000ba50  mov     eax, 20Ah
0x18000ba55  mov     [rbp+0E0h+var_C8], ax
0x18000ba59  lea     rax, RRPC_FWEnumFirewallRules2_20
0x18000ba60  mov     [rbp+0E0h+var_C0], rax
0x18000ba64  lea     rax, RRPC_FWEnumFirewallRules2_24
0x18000ba6b  mov     [rbp+0E0h+var_B0], rax
0x18000ba6f  lea     rax, RRPC_FWEnumFirewallRules2_25
0x18000ba76  mov     [rbp+0E0h+var_A0], rax
0x18000ba7a  lea     rax, RRPC_FWEnumFirewallRules2_26
0x18000ba81  mov     [rbp+0E0h+var_90], rax
0x18000ba85  lea     rax, RRPC_FWEnumFirewallRules2_27
0x18000ba8c  mov     [rbp+0E0h+var_80], rax
0x18000ba90  lea     rax, RRPC_FWEnumFirewallRules2_31
0x18000ba97  mov     [rbp+0E0h+var_70], rax
0x18000ba9b  lea     rax, RRPC_FWEnumFirewallRules2_33
0x18000baa2  mov     [rbp+0E0h+var_60], rax
0x18000baa9  lea     rax, [rbp+0E0h+var_E0]
0x18000baad  mov     [rsp+1E0h+var_188], rax
0x18000bab2  mov     [rbp+0E0h+var_148], r13w
0x18000bab7  mov     [rbp+0E0h+var_138], r11w
0x18000babc  mov     [rbp+0E0h+var_128], r10w
0x18000bac1  mov     [rbp+0E0h+var_E8], cx
0x18000bac5  mov     [rsp+1E0h+var_180], 9
0x18000bace  mov     [rbp+0E0h+var_B8], r13w
0x18000bad3  mov     [rbp+0E0h+var_A8], r11w
0x18000bad8  mov     [rbp+0E0h+var_98], r10w
0x18000badd  mov     [rbp+0E0h+var_58], cx
0x18000bae4  mov     [rsp+1E0h+var_190], 9
0x18000baed  mov     [rsp+1E0h+var_1C0], edi
0x18000baf1  xor     ecx, ecx
0x18000baf3  call    Int_FWEnumObject
0x18000baf8  mov     ebx, eax
0x18000bafa  test    eax, eax
0x18000bafc  jnz     short loc_18000BB66
0x18000bafe  mov     rcx, cs:g_Provider
0x18000bb05  test    rcx, rcx
0x18000bb08  jz      short loc_18000BB1D
0x18000bb0a  xor     r9d, r9d
0x18000bb0d  lea     rdx, MPS_CLNT_API_Exit_EnumFirewallRules
0x18000bb14  xor     r8d, r8d
0x18000bb17  call    cs:__imp_EtwEventWrite
0x18000bb1d  mov     eax, ebx
0x18000bb1f  mov     rcx, [rbp+0E0h+var_50]
0x18000bb26  xor     rcx, rsp; StackCookie
0x18000bb29  call    __security_check_cookie
0x18000bb2e  add     rsp, 1A8h
0x18000bb35  pop     r15
0x18000bb37  pop     r14
0x18000bb39  pop     r13
0x18000bb3b  pop     r12
0x18000bb3d  pop     rdi
0x18000bb3e  pop     rsi
0x18000bb3f  pop     rbx
0x18000bb40  pop     rbp
0x18000bb41  retn
0x18000bb42  test    byte ptr [rcx+1Ch], 8
0x18000bb46  jz      loc_18000B93D
0x18000bb4c  mov     rcx, [rcx+10h]
0x18000bb50  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000bb57  mov     edx, 61h ; 'a'
0x18000bb5c  call    WPP_SF_
0x18000bb61  jmp     loc_18000B93D
0x18000bb66  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb6d  lea     rax, WPP_GLOBAL_Control
0x18000bb74  cmp     rcx, rax
0x18000bb77  jz      short loc_18000BAFE
0x18000bb79  test    byte ptr [rcx+1Ch], 1
0x18000bb7d  jz      loc_18000BAFE
0x18000bb83  mov     rcx, [rcx+10h]
0x18000bb87  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000bb8e  mov     edx, 62h ; 'b'
0x18000bb93  mov     r9d, ebx
0x18000bb96  call    WPP_SF_d
0x18000bb9b  jmp     loc_18000BAFE
```
