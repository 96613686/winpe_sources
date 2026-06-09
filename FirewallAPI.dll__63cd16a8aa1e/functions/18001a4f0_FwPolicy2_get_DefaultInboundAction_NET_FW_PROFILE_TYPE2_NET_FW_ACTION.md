# FwPolicy2::get_DefaultInboundAction(NET_FW_PROFILE_TYPE2_,NET_FW_ACTION_ *)

- ea: `0x18001a4f0`
- end: `0x18001a73c`
- name: `?get_DefaultInboundAction@FwPolicy2@@UEAAJW4NET_FW_PROFILE_TYPE2_@@PEAW4NET_FW_ACTION_@@@Z`
- size: `588`
- prototype: `__int64 __fastcall(FwPolicy2 *__hidden this, enum NET_FW_PROFILE_TYPE2_, enum NET_FW_ACTION_ *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x180005954`
- `0x180008b30`
- `0x18001a4f0`
- `0x18001a744`
- `0x1800277b0`
- `0x18003104c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18001a5af`
- `ntdll!EtwEventWrite` at `0x18001a631`
- `ntdll!EtwEventWrite` at `0x18001a5af`
- `ntdll!EtwEventWrite` at `0x18001a631`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001a5cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001a5cb`
- `fwbase!FwReportReturnError` at `0x18001a685`
- `fwbase!FwReportReturnError` at `0x18001a694`
- `fwbase!FwReportReturnError` at `0x18001a685`
- `fwbase!FwReportReturnError` at `0x18001a694`

## pseudocode

```c
__int64 __fastcall FwPolicy2::get_DefaultInboundAction(
        FwPolicy2 *this,
        enum NET_FW_PROFILE_TYPE2_ a2,
        enum NET_FW_ACTION_ *a3)
{
  int PolicyStoreHandle; // eax
  signed int v7; // ebx
  unsigned int v8; // ebx
  unsigned int v9; // eax
  bool v10; // sf
  __int64 v12; // rdx
  void *v13; // [rsp+40h] [rbp-38h] BYREF
  _DWORD v14[2]; // [rsp+48h] [rbp-30h] BYREF
  int v15; // [rsp+50h] [rbp-28h] BYREF

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_651265e8da5238d82b2cc9a323e5c212_Traceguids);
  v14[0] = 0;
  v15 = 4;
  v13 = 0;
  if ( !a3 )
  {
    v7 = -2147467261;
    goto LABEL_22;
  }
  if ( (unsigned int)(a2 - 1) > 3 )
  {
    v7 = -2147024809;
    goto LABEL_22;
  }
  PolicyStoreHandle = FwPolicy2::GetPolicyStoreHandle(this, &v13);
  v7 = PolicyStoreHandle;
  if ( PolicyStoreHandle < 0 )
  {
    v12 = (unsigned int)PolicyStoreHandle;
    goto LABEL_23;
  }
  if ( a2 == NET_FW_PROFILE2_DOMAIN )
  {
    v8 = 1;
  }
  else
  {
    v8 = 2;
    if ( a2 != NET_FW_PROFILE2_PRIVATE )
    {
      v8 = 0;
      if ( a2 == NET_FW_PROFILE2_PUBLIC )
        v8 = 4;
    }
  }
  v14[1] = 0;
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_GetConfig, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  GetTickCount64();
  v9 = Int_FWGetOrSetConfig(1u, (__int64)v13, 0x11u, v8, 1, (__int64)v14, &v15);
  v7 = v9;
  if ( v9 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v9);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
  v10 = v7 < 0;
  if ( v7 > 0 )
  {
    v7 = (unsigned __int16)v7 | 0x80070000;
    v10 = v7 < 0;
  }
  if ( v10 )
  {
LABEL_22:
    v12 = (unsigned int)v7;
LABEL_23:
    FwReportReturnError("FwPolicy2::get_DefaultInboundAction", v12);
    return (unsigned int)FwReportReturnError("FwPolicy2::get_DefaultInboundAction", (unsigned int)v7);
  }
  *a3 = v14[0] == 0;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001a4f0  mov     [rsp+arg_8], rbx
0x18001a4f5  mov     [rsp+arg_18], rsi
0x18001a4fa  push    rdi
0x18001a4fb  push    r12
0x18001a4fd  push    r15
0x18001a4ff  sub     rsp, 60h
0x18001a503  mov     rax, cs:__security_cookie
0x18001a50a  xor     rax, rsp
0x18001a50d  mov     [rsp+78h+var_20], rax
0x18001a512  mov     rsi, r8
0x18001a515  mov     edi, edx
0x18001a517  mov     rbx, rcx
0x18001a51a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a521  lea     r12, WPP_GLOBAL_Control
0x18001a528  cmp     rcx, r12
0x18001a52b  jnz     loc_18001A6E9
0x18001a531  mov     [rsp+78h+var_30], 0
0x18001a539  mov     r15d, 4
0x18001a53f  mov     [rsp+78h+var_28], r15d
0x18001a544  mov     [rsp+78h+var_38], 0
0x18001a54d  test    rsi, rsi
0x18001a550  jz      loc_18001A6E2
0x18001a556  lea     eax, [rdi-1]
0x18001a559  cmp     eax, 3
0x18001a55c  ja      loc_18001A677
0x18001a562  lea     rdx, [rsp+78h+var_38]; void **
0x18001a567  mov     rcx, rbx; this
0x18001a56a  call    ?GetPolicyStoreHandle@FwPolicy2@@AEAAJPEAPEAX@Z; FwPolicy2::GetPolicyStoreHandle(void * *)
0x18001a56f  mov     ebx, eax
0x18001a571  test    eax, eax
0x18001a573  js      loc_18001A70D
0x18001a579  cmp     edi, 1
0x18001a57c  jz      loc_18001A66D
0x18001a582  lea     ebx, [r15-2]
0x18001a586  cmp     edi, ebx
0x18001a588  jnz     loc_18001A714
0x18001a58e  mov     rcx, cs:g_Provider
0x18001a595  mov     [rsp+78h+var_2C], 0
0x18001a59d  test    rcx, rcx
0x18001a5a0  jz      short loc_18001A5B5
0x18001a5a2  xor     r9d, r9d
0x18001a5a5  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x18001a5ac  xor     r8d, r8d
0x18001a5af  call    cs:__imp_EtwEventWrite
0x18001a5b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a5bc  cmp     rcx, r12
0x18001a5bf  jz      short loc_18001A5CB
0x18001a5c1  test    byte ptr [rcx+1Ch], 8
0x18001a5c5  jnz     loc_18001A722
0x18001a5cb  call    cs:__imp_GetTickCount64
0x18001a5d1  mov     rdx, [rsp+78h+var_38]
0x18001a5d6  lea     rax, [rsp+78h+var_2C]
0x18001a5db  mov     [rsp+78h+var_40], rax
0x18001a5e0  mov     r8d, 11h
0x18001a5e6  lea     rax, [rsp+78h+var_28]
0x18001a5eb  mov     r9d, ebx
0x18001a5ee  mov     [rsp+78h+var_48], rax
0x18001a5f3  lea     rax, [rsp+78h+var_30]
0x18001a5f8  mov     [rsp+78h+var_50], rax
0x18001a5fd  lea     ecx, [r8-10h]
0x18001a601  mov     [rsp+78h+var_58], 1
0x18001a609  call    Int_FWGetOrSetConfig
0x18001a60e  mov     ebx, eax
0x18001a610  test    eax, eax
0x18001a612  jnz     loc_18001A6AB
0x18001a618  mov     rcx, cs:g_Provider
0x18001a61f  test    rcx, rcx
0x18001a622  jz      short loc_18001A637
0x18001a624  xor     r9d, r9d
0x18001a627  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x18001a62e  xor     r8d, r8d
0x18001a631  call    cs:__imp_EtwEventWrite
0x18001a637  test    ebx, ebx
0x18001a639  jg      short loc_18001A69E
0x18001a63b  js      short loc_18001A67C
0x18001a63d  xor     eax, eax
0x18001a63f  cmp     [rsp+78h+var_30], eax
0x18001a643  setz    al
0x18001a646  mov     [rsi], eax
0x18001a648  mov     eax, ebx
0x18001a64a  mov     rcx, [rsp+78h+var_20]
0x18001a64f  xor     rcx, rsp; StackCookie
0x18001a652  call    __security_check_cookie
0x18001a657  lea     r11, [rsp+78h+var_18]
0x18001a65c  mov     rbx, [r11+28h]
0x18001a660  mov     rsi, [r11+38h]
0x18001a664  mov     rsp, r11
0x18001a667  pop     r15
0x18001a669  pop     r12
0x18001a66b  pop     rdi
0x18001a66c  retn
0x18001a66d  mov     ebx, 1
0x18001a672  jmp     loc_18001A58E
0x18001a677  mov     ebx, 80070057h
0x18001a67c  mov     edx, ebx
0x18001a67e  lea     rcx, aFwpolicy2GetDe_0; "FwPolicy2::get_DefaultInboundAction"
0x18001a685  call    cs:__imp_FwReportReturnError
0x18001a68b  mov     edx, ebx
0x18001a68d  lea     rcx, aFwpolicy2GetDe_0; "FwPolicy2::get_DefaultInboundAction"
0x18001a694  call    cs:__imp_FwReportReturnError
0x18001a69a  mov     ebx, eax
0x18001a69c  jmp     short loc_18001A648
0x18001a69e  movzx   ebx, bx
0x18001a6a1  or      ebx, 80070000h
0x18001a6a7  test    ebx, ebx
0x18001a6a9  jmp     short loc_18001A63B
0x18001a6ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a6b2  cmp     rcx, r12
0x18001a6b5  jz      loc_18001A618
0x18001a6bb  test    byte ptr [rcx+1Ch], 1
0x18001a6bf  jz      loc_18001A618
0x18001a6c5  mov     rcx, [rcx+10h]
0x18001a6c9  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18001a6d0  mov     edx, 6Bh ; 'k'
0x18001a6d5  mov     r9d, ebx
0x18001a6d8  call    WPP_SF_d
0x18001a6dd  jmp     loc_18001A618
0x18001a6e2  mov     ebx, 80004003h
0x18001a6e7  jmp     short loc_18001A67C
0x18001a6e9  test    byte ptr [rcx+1Ch], 8
0x18001a6ed  jz      loc_18001A531
0x18001a6f3  mov     rcx, [rcx+10h]
0x18001a6f7  lea     r8, WPP_651265e8da5238d82b2cc9a323e5c212_Traceguids
0x18001a6fe  mov     edx, 29h ; ')'
0x18001a703  call    WPP_SF_
0x18001a708  jmp     loc_18001A531
0x18001a70d  mov     edx, eax
0x18001a70f  jmp     loc_18001A67E
0x18001a714  xor     ebx, ebx
0x18001a716  cmp     edi, r15d
0x18001a719  cmovz   ebx, r15d
0x18001a71d  jmp     loc_18001A58E
0x18001a722  mov     rcx, [rcx+10h]
0x18001a726  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18001a72d  mov     edx, 6Ah ; 'j'
0x18001a732  call    WPP_SF_
0x18001a737  jmp     loc_18001A5CB
```
