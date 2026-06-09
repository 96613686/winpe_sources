# FirewallHelper::DeleteAppRoutePolicyRulesByProviderId(_GUID const &)

- ea: `0x18002bb4c`
- end: `0x18002bcd3`
- name: `?DeleteAppRoutePolicyRulesByProviderId@FirewallHelper@@YAJAEBU_GUID@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(GUID *this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180029bb0`

## callees

- `0x18001c080`
- `0x18001d8e0`
- `0x18002ab94`
- `0x18002b8a4`
- `0x18002bb4c`
- `0x18002c07c`

## import_xrefs

- `fwpuclnt!FwpmEngineOpen0` at `0x18002bc3a`
- `fwpuclnt!FwpmEngineOpen0` at `0x18002bc3a`
- `fwpuclnt!FwpmEngineClose0` at `0x18002bc9d`
- `fwpuclnt!FwpmEngineClose0` at `0x18002bc9d`

## pseudocode

```c
__int64 __fastcall FirewallHelper::DeleteAppRoutePolicyRulesByProviderId(GUID *this, const struct _GUID *a2)
{
  DWORD v3; // eax
  const struct _GUID *v4; // r9
  unsigned int v5; // ebx
  unsigned int v6; // r8d
  const char *v7; // r9
  __int64 result; // rax
  HANDLE v9; // rsi
  const struct _GUID *v10; // rbx
  struct _GUID *v11; // rdi
  unsigned int engineHandle; // [rsp+20h] [rbp-F8h]
  HANDLE v13; // [rsp+30h] [rbp-E8h] BYREF
  struct _GUID *v14[2]; // [rsp+38h] [rbp-E0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-D0h]
  __int64 *v16; // [rsp+50h] [rbp-C8h] BYREF
  _OWORD *v17; // [rsp+58h] [rbp-C0h] BYREF
  _OWORD v18[8]; // [rsp+60h] [rbp-B8h] BYREF
  __int64 v19; // [rsp+E0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  try
  {
    v13 = 0;
    v18[0] = FWPM_LAYER_ALE_BIND_REDIRECT_V4;
    v18[1] = FWPM_LAYER_ALE_BIND_REDIRECT_V6;
    v18[2] = FWPM_LAYER_ALE_CONNECT_REDIRECT_V4;
    v18[3] = FWPM_LAYER_ALE_CONNECT_REDIRECT_V6;
    v18[4] = FWPM_LAYER_ALE_FLOW_ESTABLISHED_V4;
    v18[5] = FWPM_LAYER_ALE_FLOW_ESTABLISHED_V6;
    v18[6] = FWPM_LAYER_ALE_ENDPOINT_CLOSURE_V4;
    v18[7] = FWPM_LAYER_ALE_ENDPOINT_CLOSURE_V6;
    *(_OWORD *)v14 = 0;
    v15 = 0;
    v16 = &v19;
    v17 = v18;
    std::vector<_GUID>::_Construct_n<_GUID const *,_GUID const *>(v14, 8, &v17, &v16);
    v3 = FwpmEngineOpen0(0, 0xFFFFFFFF, 0, 0, &v13);
    if ( v3 )
    {
      v5 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x1FB,
             (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\ncb\\src\\firewallhelper.cpp",
             (const char *)v3,
             engineHandle);
      std::vector<_GUID>::_Tidy(v14);
      result = v5;
    }
    else
    {
      v9 = v13;
      v10 = v14[0];
      v11 = v14[1];
      while ( v10 != v11 )
        FirewallHelper::DeleteAppRoutePolicyFiltersByLayerKey(&v13, this, v10++, v4);
      FwpmEngineClose0(v9);
      std::vector<_GUID>::_Tidy(v14);
      result = 0;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x207, v6, v7);
  }
  return result;
}

```

## disassembly

```asm
0x18002bb4c  mov     r11, rsp
0x18002bb4f  push    rbx
0x18002bb50  push    rsi
0x18002bb51  push    rdi
0x18002bb52  push    r14
0x18002bb54  sub     rsp, 0F8h
0x18002bb5b  mov     rax, cs:__security_cookie
0x18002bb62  xor     rax, rsp
0x18002bb65  mov     [rsp+118h+var_38], rax
0x18002bb6d  mov     r14, rcx
0x18002bb70  mov     [rsp+118h+var_E8], 0
0x18002bb79  movups  xmm0, xmmword ptr cs:FWPM_LAYER_ALE_BIND_REDIRECT_V4.Data1
0x18002bb80  movdqu  [rsp+118h+var_B8], xmm0
0x18002bb86  xorps   xmm0, xmm0
0x18002bb89  movups  xmm1, xmmword ptr cs:FWPM_LAYER_ALE_BIND_REDIRECT_V6.Data1
0x18002bb90  movdqu  [rsp+118h+var_A8], xmm1
0x18002bb96  movups  xmm1, xmmword ptr cs:FWPM_LAYER_ALE_CONNECT_REDIRECT_V4.Data1
0x18002bb9d  movdqu  [rsp+118h+var_98], xmm1
0x18002bba6  movups  xmm1, xmmword ptr cs:FWPM_LAYER_ALE_CONNECT_REDIRECT_V6.Data1
0x18002bbad  movdqu  [rsp+118h+var_88], xmm1
0x18002bbb6  movups  xmm1, xmmword ptr cs:FWPM_LAYER_ALE_FLOW_ESTABLISHED_V4.Data1
0x18002bbbd  movdqu  xmmword ptr [r11-78h], xmm1
0x18002bbc3  movups  xmm1, xmmword ptr cs:FWPM_LAYER_ALE_FLOW_ESTABLISHED_V6.Data1
0x18002bbca  movdqu  xmmword ptr [r11-68h], xmm1
0x18002bbd0  movups  xmm1, xmmword ptr cs:FWPM_LAYER_ALE_ENDPOINT_CLOSURE_V4.Data1
0x18002bbd7  movdqu  xmmword ptr [r11-58h], xmm1
0x18002bbdd  movups  xmm1, xmmword ptr cs:FWPM_LAYER_ALE_ENDPOINT_CLOSURE_V6.Data1
0x18002bbe4  movdqu  xmmword ptr [r11-48h], xmm1
0x18002bbea  movdqu  xmmword ptr [rsp+118h+var_E0], xmm0
0x18002bbf0  mov     [rsp+118h+var_D0], 0
0x18002bbf9  lea     rax, [r11-38h]
0x18002bbfd  mov     [rsp+118h+var_C8], rax
0x18002bc02  lea     rax, [rsp+118h+var_B8]
0x18002bc07  mov     [rsp+118h+var_C0], rax
0x18002bc0c  lea     r9, [rsp+118h+var_C8]
0x18002bc11  lea     r8, [rsp+118h+var_C0]
0x18002bc16  mov     edx, 8
0x18002bc1b  lea     rcx, [rsp+118h+var_E0]
0x18002bc20  call    ??$_Construct_n@PEBU_GUID@@PEBU1@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAX_K$$QEAPEBU_GUID@@1@Z; std::vector<_GUID>::_Construct_n<_GUID const *,_GUID const *>(unsigned __int64,_GUID const * &&,_GUID const * &&)
0x18002bc25  lea     rax, [rsp+118h+var_E8]
0x18002bc2a  mov     qword ptr [rsp+118h+engineHandle], rax; unsigned int
0x18002bc2f  xor     r9d, r9d; session
0x18002bc32  xor     r8d, r8d; authIdentity
0x18002bc35  or      edx, 0FFFFFFFFh; authnService
0x18002bc38  xor     ecx, ecx; serverName
0x18002bc3a  call    cs:__imp_FwpmEngineOpen0
0x18002bc40  test    eax, eax
0x18002bc42  jz      short loc_18002BC70
0x18002bc44  mov     rcx, [rsp+118h]; this
0x18002bc4c  mov     r9d, eax; char *
0x18002bc4f  lea     r8, aOnecoreuapNetN; "onecoreuap\\net\\netio\\iphlpsvc\\ncb\\"...
0x18002bc56  mov     edx, 1FBh; void *
0x18002bc5b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002bc60  mov     ebx, eax
0x18002bc62  lea     rcx, [rsp+118h+var_E0]
0x18002bc67  call    ?_Tidy@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAXXZ; std::vector<_GUID>::_Tidy(void)
0x18002bc6c  mov     eax, ebx
0x18002bc6e  jmp     short loc_18002BCB5
0x18002bc70  mov     rsi, [rsp+118h+var_E8]
0x18002bc75  mov     rbx, [rsp+118h+var_E0]
0x18002bc7a  mov     rdi, [rsp+118h+var_E0+8]
0x18002bc7f  jmp     short loc_18002BC95
0x18002bc81  mov     r8, rbx; struct _GUID *
0x18002bc84  mov     rdx, r14; void **
0x18002bc87  lea     rcx, [rsp+118h+var_E8]; this
0x18002bc8c  call    ?DeleteAppRoutePolicyFiltersByLayerKey@FirewallHelper@@YAXAEBQEAXAEBU_GUID@@1@Z; FirewallHelper::DeleteAppRoutePolicyFiltersByLayerKey(void * const &,_GUID const &,_GUID const &)
0x18002bc91  add     rbx, 10h
0x18002bc95  cmp     rbx, rdi
0x18002bc98  jnz     short loc_18002BC81
0x18002bc9a  mov     rcx, rsi; engineHandle
0x18002bc9d  call    cs:__imp_FwpmEngineClose0
0x18002bca3  lea     rcx, [rsp+118h+var_E0]
0x18002bca8  call    ?_Tidy@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAXXZ; std::vector<_GUID>::_Tidy(void)
0x18002bcad  xor     eax, eax
0x18002bcaf  jmp     short loc_18002BCB5
0x18002bcb1  mov     eax, dword ptr [rsp+118h+var_E8]
0x18002bcb5  mov     rcx, [rsp+118h+var_38]
0x18002bcbd  xor     rcx, rsp; StackCookie
0x18002bcc0  call    __security_check_cookie
0x18002bcc5  add     rsp, 0F8h
0x18002bccc  pop     r14
0x18002bcce  pop     rdi
0x18002bccf  pop     rsi
0x18002bcd0  pop     rbx
0x18002bcd1  retn
```
