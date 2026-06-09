# FwPolicy2::GetBool(NET_FW_PROFILE_TYPE2_,_tag_FW_PROFILE_CONFIG,short,short *)

- ea: `0x180006b40`
- end: `0x180006e8c`
- name: `?GetBool@FwPolicy2@@AEAAJW4NET_FW_PROFILE_TYPE2_@@W4_tag_FW_PROFILE_CONFIG@@FPEAF@Z`
- size: `844`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800062a0`
- `0x180006320`
- `0x1800379b0`

## callees

- `0x180005954`
- `0x180006b40`
- `0x180008b30`
- `0x18000c560`
- `0x1800277b0`
- `0x18003104c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180006d09`
- `ntdll!EtwEventWrite` at `0x180006d8b`
- `ntdll!EtwEventWrite` at `0x180006d09`
- `ntdll!EtwEventWrite` at `0x180006d8b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180006d2c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180006d2c`
- `fwbase!FwReportReturnError` at `0x180006c94`
- `fwbase!FwReportReturnError` at `0x180006ca3`
- `fwbase!FwReportReturnError` at `0x180006cb7`
- `fwbase!FwReportReturnError` at `0x180006cc6`
- `fwbase!FwReportReturnError` at `0x180006c94`
- `fwbase!FwReportReturnError` at `0x180006ca3`
- `fwbase!FwReportReturnError` at `0x180006cb7`
- `fwbase!FwReportReturnError` at `0x180006cc6`

## pseudocode

```c
__int64 __fastcall FwPolicy2::GetBool(__int64 a1, int a2, unsigned int a3, __int16 a4, __int16 *a5)
{
  FwPolicy2 *v9; // rcx
  __int64 *v10; // rdi
  unsigned int v11; // ebx
  unsigned int v12; // r14d
  __int64 v13; // rdi
  int v14; // eax
  int v15; // eax
  __int64 v16; // rdx
  int v18; // eax
  unsigned int v19; // eax
  int v20; // edi
  __int16 v21; // ax
  _DWORD v22[2]; // [rsp+40h] [rbp-58h] BYREF
  int v23; // [rsp+48h] [rbp-50h] BYREF

  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_651265e8da5238d82b2cc9a323e5c212_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  v22[0] = 0;
  v23 = 4;
  if ( (unsigned int)(a2 - 1) > 3 )
  {
    v11 = -2147024809;
LABEL_19:
    v16 = v11;
LABEL_21:
    FwReportReturnError("FwPolicy2::GetBool", v16);
    return FwReportReturnError("FwPolicy2::GetBool", v11);
  }
  if ( !a5 )
  {
    v11 = -2147467261;
    goto LABEL_19;
  }
  if ( v9 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)v9 + 2), 40, WPP_651265e8da5238d82b2cc9a323e5c212_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  v10 = (__int64 *)(a1 + 32);
  v11 = 0;
  v12 = 2;
  if ( *v10 )
    goto LABEL_8;
  v14 = FWOpenPolicyStore(0x221u, 0, 2u, 2u, 0, v10);
  v11 = v14;
  if ( v14 > 0 )
    v11 = (unsigned __int16)v14 | 0x80070000;
  if ( v11 == -2147024891 )
  {
    v15 = FWOpenPolicyStore(0x221u, 0, 2u, 1u, 0, v10);
    v11 = v15;
    if ( v15 > 0 )
      v11 = (unsigned __int16)v15 | 0x80070000;
  }
  if ( (v11 & 0x80000000) == 0 )
  {
    v9 = WPP_GLOBAL_Control;
LABEL_8:
    v13 = *v10;
    goto LABEL_24;
  }
  FwReportReturnError("FwPolicy2::GetPolicyStoreHandle", v11);
  v18 = FwReportReturnError("FwPolicy2::GetPolicyStoreHandle", v11);
  v11 = v18;
  v13 = 0;
  if ( v18 < 0 )
  {
    v16 = (unsigned int)v18;
    goto LABEL_21;
  }
  v9 = WPP_GLOBAL_Control;
LABEL_24:
  if ( a2 == 1 )
  {
    v12 = 1;
  }
  else if ( a2 != 2 )
  {
    v12 = 0;
    if ( a2 == 4 )
      v12 = 4;
  }
  v22[1] = 0;
  if ( g_Provider )
  {
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_GetConfig, 0, 0);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v9 + 2), 106, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  GetTickCount64();
  v19 = Int_FWGetOrSetConfig(1u, v13, a3, v12, 0, (__int64)v22, &v23);
  v20 = v19;
  if ( v19 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v19);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
  if ( v20 != 2 )
  {
    if ( v20 > 0 )
      v11 = (unsigned __int16)v20 | 0x80070000;
    else
      v11 = v20;
    if ( (v11 & 0x80000000) == 0 )
    {
      v21 = -1;
      if ( !v22[0] )
        v21 = 0;
      goto LABEL_40;
    }
    goto LABEL_19;
  }
  v21 = -(a4 != 0);
LABEL_40:
  *a5 = v21;
  return v11;
}

```

## disassembly

```asm
0x180006b40  push    rbp
0x180006b42  push    rsi
0x180006b43  push    rdi
0x180006b44  push    r12
0x180006b46  push    r13
0x180006b48  push    r15
0x180006b4a  sub     rsp, 68h
0x180006b4e  mov     rax, cs:__security_cookie
0x180006b55  xor     rax, rsp
0x180006b58  mov     [rsp+98h+var_48], rax
0x180006b5d  mov     rsi, [rsp+98h+arg_20]
0x180006b65  movzx   r12d, r9w
0x180006b69  mov     r15d, r8d
0x180006b6c  mov     ebp, edx
0x180006b6e  mov     rdi, rcx
0x180006b71  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b78  lea     rdx, WPP_GLOBAL_Control
0x180006b7f  cmp     rcx, rdx
0x180006b82  jnz     short loc_180006BDF
0x180006b84  xor     r13d, r13d
0x180006b87  mov     [rsp+98h+arg_8], rbx
0x180006b8f  lea     eax, [rbp-1]
0x180006b92  mov     [rsp+98h+var_38], r14
0x180006b97  mov     [rsp+98h+var_58], r13d
0x180006b9c  mov     [rsp+98h+var_50], 4
0x180006ba4  cmp     eax, 3
0x180006ba7  ja      loc_180006C82
0x180006bad  test    rsi, rsi
0x180006bb0  jz      loc_180006E47
0x180006bb6  cmp     rcx, rdx
0x180006bb9  jz      short loc_180006BC5
0x180006bbb  test    byte ptr [rcx+1Ch], 8
0x180006bbf  jnz     loc_180006E51
0x180006bc5  add     rdi, 20h ; ' '
0x180006bc9  mov     ebx, r13d
0x180006bcc  mov     r14d, 2
0x180006bd2  cmp     [rdi], rbx
0x180006bd5  jz      short loc_180006C0D
0x180006bd7  mov     rdi, [rdi]
0x180006bda  jmp     loc_180006CDC
0x180006bdf  test    byte ptr [rcx+1Ch], 8
0x180006be3  jz      short loc_180006B84
0x180006be5  mov     rcx, [rcx+10h]
0x180006be9  lea     r8, WPP_651265e8da5238d82b2cc9a323e5c212_Traceguids
0x180006bf0  mov     edx, 26h ; '&'
0x180006bf5  call    WPP_SF_
0x180006bfa  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c01  lea     rdx, WPP_GLOBAL_Control
0x180006c08  jmp     loc_180006B84
0x180006c0d  mov     ecx, 221h
0x180006c12  mov     [rsp+98h+var_70], rdi
0x180006c17  mov     r9d, r14d
0x180006c1a  mov     [rsp+98h+var_78], r13d
0x180006c1f  mov     r8d, r14d
0x180006c22  xor     edx, edx
0x180006c24  call    FWOpenPolicyStore
0x180006c29  mov     ebx, eax
0x180006c2b  test    eax, eax
0x180006c2d  jg      short loc_180006C6C
0x180006c2f  cmp     ebx, 80070005h
0x180006c35  jnz     short loc_180006C5C
0x180006c37  mov     ecx, 221h
0x180006c3c  mov     [rsp+98h+var_70], rdi
0x180006c41  mov     r9d, 1
0x180006c47  mov     [rsp+98h+var_78], r13d
0x180006c4c  mov     r8d, r14d
0x180006c4f  xor     edx, edx
0x180006c51  call    FWOpenPolicyStore
0x180006c56  mov     ebx, eax
0x180006c58  test    eax, eax
0x180006c5a  jg      short loc_180006C77
0x180006c5c  test    ebx, ebx
0x180006c5e  js      short loc_180006CAE
0x180006c60  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c67  jmp     loc_180006BD7
0x180006c6c  movzx   ebx, ax
0x180006c6f  or      ebx, 80070000h
0x180006c75  jmp     short loc_180006C2F
0x180006c77  movzx   ebx, ax
0x180006c7a  or      ebx, 80070000h
0x180006c80  jmp     short loc_180006C5C
0x180006c82  mov     ebx, 80070057h
0x180006c87  mov     edx, ebx
0x180006c89  jmp     short loc_180006C8D
0x180006c8b  mov     edx, eax
0x180006c8d  lea     rcx, aFwpolicy2Getbo; "FwPolicy2::GetBool"
0x180006c94  call    cs:__imp_FwReportReturnError
0x180006c9a  mov     edx, ebx
0x180006c9c  lea     rcx, aFwpolicy2Getbo; "FwPolicy2::GetBool"
0x180006ca3  call    cs:__imp_FwReportReturnError
0x180006ca9  jmp     loc_180006DB7
0x180006cae  mov     edx, ebx
0x180006cb0  lea     rcx, aFwpolicy2Getpo; "FwPolicy2::GetPolicyStoreHandle"
0x180006cb7  call    cs:__imp_FwReportReturnError
0x180006cbd  mov     edx, ebx
0x180006cbf  lea     rcx, aFwpolicy2Getpo; "FwPolicy2::GetPolicyStoreHandle"
0x180006cc6  call    cs:__imp_FwReportReturnError
0x180006ccc  mov     ebx, eax
0x180006cce  mov     rdi, r13
0x180006cd1  test    eax, eax
0x180006cd3  js      short loc_180006C8B
0x180006cd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180006cdc  cmp     ebp, 1
0x180006cdf  jnz     loc_180006DDF
0x180006ce5  mov     r14d, ebp
0x180006ce8  mov     rax, cs:g_Provider
0x180006cef  mov     [rsp+98h+var_54], r13d
0x180006cf4  test    rax, rax
0x180006cf7  jz      short loc_180006D16
0x180006cf9  xor     r9d, r9d
0x180006cfc  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x180006d03  xor     r8d, r8d
0x180006d06  mov     rcx, rax
0x180006d09  call    cs:__imp_EtwEventWrite
0x180006d0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d16  lea     rbp, WPP_GLOBAL_Control
0x180006d1d  cmp     rcx, rbp
0x180006d20  jz      short loc_180006D2C
0x180006d22  test    byte ptr [rcx+1Ch], 8
0x180006d26  jnz     loc_180006E72
0x180006d2c  call    cs:__imp_GetTickCount64
0x180006d32  lea     rax, [rsp+98h+var_54]
0x180006d37  mov     r9d, r14d
0x180006d3a  mov     [rsp+98h+var_60], rax
0x180006d3f  mov     r8d, r15d
0x180006d42  lea     rax, [rsp+98h+var_50]
0x180006d47  mov     rdx, rdi
0x180006d4a  mov     [rsp+98h+var_68], rax
0x180006d4f  mov     ecx, 1
0x180006d54  lea     rax, [rsp+98h+var_58]
0x180006d59  mov     [rsp+98h+var_70], rax
0x180006d5e  mov     [rsp+98h+var_78], r13d
0x180006d63  call    Int_FWGetOrSetConfig
0x180006d68  mov     edi, eax
0x180006d6a  test    eax, eax
0x180006d6c  jnz     loc_180006E10
0x180006d72  mov     rcx, cs:g_Provider
0x180006d79  test    rcx, rcx
0x180006d7c  jz      short loc_180006D91
0x180006d7e  xor     r9d, r9d
0x180006d81  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x180006d88  xor     r8d, r8d
0x180006d8b  call    cs:__imp_EtwEventWrite
0x180006d91  cmp     edi, 2
0x180006d94  jz      short loc_180006E07
0x180006d96  test    edi, edi
0x180006d98  jg      short loc_180006DFC
0x180006d9a  mov     ebx, edi
0x180006d9c  test    ebx, ebx
0x180006d9e  js      loc_180006C87
0x180006da4  cmp     [rsp+98h+var_58], r13d
0x180006da9  mov     eax, 0FFFFFFFFh
0x180006dae  cmovz   eax, r13d
0x180006db2  mov     [rsi], ax
0x180006db5  mov     eax, ebx
0x180006db7  mov     r14, [rsp+98h+var_38]
0x180006dbc  mov     rbx, [rsp+98h+arg_8]
0x180006dc4  mov     rcx, [rsp+98h+var_48]
0x180006dc9  xor     rcx, rsp; StackCookie
0x180006dcc  call    __security_check_cookie
0x180006dd1  add     rsp, 68h
0x180006dd5  pop     r15
0x180006dd7  pop     r13
0x180006dd9  pop     r12
0x180006ddb  pop     rdi
0x180006ddc  pop     rsi
0x180006ddd  pop     rbp
0x180006dde  retn
0x180006ddf  cmp     ebp, r14d
0x180006de2  jz      loc_180006CE8
0x180006de8  cmp     ebp, 4
0x180006deb  mov     r14d, r13d
0x180006dee  mov     eax, 4
0x180006df3  cmovz   r14d, eax
0x180006df7  jmp     loc_180006CE8
0x180006dfc  movzx   ebx, di
0x180006dff  or      ebx, 80070000h
0x180006e05  jmp     short loc_180006D9C
0x180006e07  neg     r12w
0x180006e0b  sbb     ax, ax
0x180006e0e  jmp     short loc_180006DB2
0x180006e10  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e17  cmp     rcx, rbp
0x180006e1a  jz      loc_180006D72
0x180006e20  test    byte ptr [rcx+1Ch], 1
0x180006e24  jz      loc_180006D72
0x180006e2a  mov     rcx, [rcx+10h]
0x180006e2e  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180006e35  mov     edx, 6Bh ; 'k'
0x180006e3a  mov     r9d, edi
0x180006e3d  call    WPP_SF_d
0x180006e42  jmp     loc_180006D72
0x180006e47  mov     ebx, 80004003h
0x180006e4c  jmp     loc_180006C87
0x180006e51  mov     rcx, [rcx+10h]
0x180006e55  lea     r8, WPP_651265e8da5238d82b2cc9a323e5c212_Traceguids
0x180006e5c  mov     edx, 28h ; '('
0x180006e61  call    WPP_SF_
0x180006e66  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e6d  jmp     loc_180006BC5
0x180006e72  mov     rcx, [rcx+10h]
0x180006e76  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180006e7d  mov     edx, 6Ah ; 'j'
0x180006e82  call    WPP_SF_
0x180006e87  jmp     loc_180006D2C
```
