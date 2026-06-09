# GetDisabledInterfaces(void *,_tag_FW_PROFILE_TYPE,_tag_FW_INTERFACE_LUIDS * *)

- ea: `0x180006ea0`
- end: `0x18000711d`
- name: `?GetDisabledInterfaces@@YAJPEAXW4_tag_FW_PROFILE_TYPE@@PEAPEAU_tag_FW_INTERFACE_LUIDS@@@Z`
- size: `637`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180037850`

## callees

- `0x180005954`
- `0x180006ea0`
- `0x180008b30`
- `0x1800277b0`
- `0x18003104c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180006f0c`
- `ntdll!EtwEventWrite` at `0x180006f8f`
- `ntdll!EtwEventWrite` at `0x180006f0c`
- `ntdll!EtwEventWrite` at `0x180006f8f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180006f28`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180006f28`
- `fwbase!FwBaseAlloc` at `0x180006fc0`
- `fwbase!FwBaseAlloc` at `0x180006fc0`
- `fwbase!FwBaseFree` at `0x1800070a3`
- `fwbase!FwBaseFree` at `0x1800070da`
- `fwbase!FwBaseFree` at `0x1800070a3`
- `fwbase!FwBaseFree` at `0x1800070da`

## pseudocode

```c
__int64 __fastcall GetDisabledInterfaces(__int64 a1, unsigned int a2, __int64 *a3)
{
  FwPolicy2 *v5; // rax
  __int64 v7; // rcx
  unsigned int v8; // ebp
  unsigned int v9; // esi
  __int64 v10; // rdi
  int v11; // ebx
  int v13[2]; // [rsp+40h] [rbp-48h] BYREF

  *a3 = 0;
  v5 = WPP_GLOBAL_Control;
  v7 = g_Provider;
  v8 = 0;
  v13[0] = 0;
  v9 = 0;
  v10 = 0;
  while ( 1 )
  {
    v13[1] = 0;
    if ( v7 )
    {
      EtwEventWrite(v7, MPS_CLNT_API_Enter_GetConfig, 0, 0);
      v5 = WPP_GLOBAL_Control;
    }
    if ( v5 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)v5 + 2), 106, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
    GetTickCount64();
    v11 = Int_FWGetOrSetConfig(1u, a1, 0xFu, a2, 1, v10, v13);
    if ( !v11 )
      goto LABEL_8;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        107,
        WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids,
        (unsigned int)v11);
LABEL_8:
      v5 = WPP_GLOBAL_Control;
    }
    v7 = g_Provider;
    if ( g_Provider )
    {
      EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
      v5 = WPP_GLOBAL_Control;
      v7 = g_Provider;
    }
    if ( !v11 )
      goto LABEL_17;
    if ( v11 != 234 )
      break;
    if ( v10 )
      FwBaseFree(v10);
    v10 = FwBaseAlloc((unsigned int)v13[0]);
    if ( !v10 )
    {
      v8 = -2147024882;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_428964b663db31776494a5e8e5edd24b_Traceguids, 2147942414LL);
      goto LABEL_32;
    }
    v5 = WPP_GLOBAL_Control;
    v7 = g_Provider;
LABEL_17:
    if ( v9 <= 5 && !v11 )
    {
      *a3 = v10;
      return v8;
    }
    ++v9;
  }
  if ( v11 > 0 )
    v8 = (unsigned __int16)v11 | 0x80070000;
  else
    v8 = v11;
  if ( v5 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v5 + 2), 14, WPP_428964b663db31776494a5e8e5edd24b_Traceguids, v8);
  if ( v10 )
    FwBaseFree(v10);
LABEL_32:
  *a3 = 0;
  return v8;
}

```

## disassembly

```asm
0x180006ea0  mov     [rsp+arg_18], rbx
0x180006ea5  push    rbp
0x180006ea6  push    rsi
0x180006ea7  push    rdi
0x180006ea8  push    r12
0x180006eaa  push    r13
0x180006eac  push    r14
0x180006eae  push    r15
0x180006eb0  sub     rsp, 50h
0x180006eb4  mov     rax, cs:__security_cookie
0x180006ebb  xor     rax, rsp
0x180006ebe  mov     [rsp+88h+var_40], rax
0x180006ec3  xor     r13d, r13d
0x180006ec6  mov     r14, rcx
0x180006ec9  mov     [r8], r13
0x180006ecc  mov     r12, r8
0x180006ecf  mov     rax, cs:WPP_GLOBAL_Control
0x180006ed6  mov     r15d, edx
0x180006ed9  mov     rcx, cs:g_Provider
0x180006ee0  mov     ebp, r13d
0x180006ee3  mov     [rsp+88h+var_48], r13d
0x180006ee8  mov     esi, r13d
0x180006eeb  mov     edi, r13d
0x180006eee  mov     [rsp+88h+var_44], r13d
0x180006ef3  lea     rbx, WPP_GLOBAL_Control
0x180006efa  test    rcx, rcx
0x180006efd  jz      short loc_180006F19
0x180006eff  xor     r9d, r9d
0x180006f02  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x180006f09  xor     r8d, r8d
0x180006f0c  call    cs:__imp_EtwEventWrite
0x180006f12  mov     rax, cs:WPP_GLOBAL_Control
0x180006f19  cmp     rax, rbx
0x180006f1c  jz      short loc_180006F28
0x180006f1e  test    byte ptr [rax+1Ch], 8
0x180006f22  jnz     loc_1800070BD
0x180006f28  call    cs:__imp_GetTickCount64
0x180006f2e  lea     rax, [rsp+88h+var_44]
0x180006f33  mov     r9d, r15d
0x180006f36  mov     [rsp+88h+var_50], rax
0x180006f3b  mov     r8d, 0Fh
0x180006f41  lea     rax, [rsp+88h+var_48]
0x180006f46  mov     rdx, r14
0x180006f49  mov     [rsp+88h+var_58], rax
0x180006f4e  mov     ecx, 1
0x180006f53  mov     [rsp+88h+var_60], rdi
0x180006f58  mov     [rsp+88h+var_68], 1
0x180006f60  call    Int_FWGetOrSetConfig
0x180006f65  mov     ebx, eax
0x180006f67  test    eax, eax
0x180006f69  jnz     loc_180007025
0x180006f6f  mov     rax, cs:WPP_GLOBAL_Control
0x180006f76  mov     rcx, cs:g_Provider
0x180006f7d  test    rcx, rcx
0x180006f80  jz      short loc_180006FA3
0x180006f82  xor     r9d, r9d
0x180006f85  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x180006f8c  xor     r8d, r8d
0x180006f8f  call    cs:__imp_EtwEventWrite
0x180006f95  mov     rax, cs:WPP_GLOBAL_Control
0x180006f9c  mov     rcx, cs:g_Provider
0x180006fa3  test    ebx, ebx
0x180006fa5  jz      short loc_180006FE0
0x180006fa7  cmp     ebx, 0EAh
0x180006fad  jnz     loc_180007063
0x180006fb3  test    rdi, rdi
0x180006fb6  jnz     loc_1800070D7
0x180006fbc  mov     ecx, [rsp+88h+var_48]
0x180006fc0  call    cs:__imp_FwBaseAlloc
0x180006fc6  mov     rdi, rax
0x180006fc9  test    rax, rax
0x180006fcc  jz      loc_1800070E5
0x180006fd2  mov     rax, cs:WPP_GLOBAL_Control
0x180006fd9  mov     rcx, cs:g_Provider
0x180006fe0  cmp     esi, 5
0x180006fe3  ja      short loc_18000701E
0x180006fe5  mov     edx, ebp
0x180006fe7  test    ebx, ebx
0x180006fe9  jnz     short loc_18000701E
0x180006feb  mov     [r12], rdi
0x180006fef  test    edx, edx
0x180006ff1  js      loc_18000709B
0x180006ff7  mov     eax, ebp
0x180006ff9  mov     rcx, [rsp+88h+var_40]
0x180006ffe  xor     rcx, rsp; StackCookie
0x180007001  call    __security_check_cookie
0x180007006  mov     rbx, [rsp+88h+arg_18]
0x18000700e  add     rsp, 50h
0x180007012  pop     r15
0x180007014  pop     r14
0x180007016  pop     r13
0x180007018  pop     r12
0x18000701a  pop     rdi
0x18000701b  pop     rsi
0x18000701c  pop     rbp
0x18000701d  retn
0x18000701e  inc     esi
0x180007020  jmp     loc_180006EEE
0x180007025  mov     rax, cs:WPP_GLOBAL_Control
0x18000702c  lea     rcx, WPP_GLOBAL_Control
0x180007033  cmp     rax, rcx
0x180007036  jz      loc_180006F76
0x18000703c  test    byte ptr [rax+1Ch], 1
0x180007040  jz      loc_180006F76
0x180007046  mov     rcx, [rax+10h]
0x18000704a  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180007051  mov     edx, 6Bh ; 'k'
0x180007056  mov     r9d, ebx
0x180007059  call    WPP_SF_d
0x18000705e  jmp     loc_180006F6F
0x180007063  test    ebx, ebx
0x180007065  jg      short loc_1800070B2
0x180007067  mov     ebp, ebx
0x180007069  test    ebp, ebp
0x18000706b  jns     loc_180006FE0
0x180007071  lea     rcx, WPP_GLOBAL_Control
0x180007078  cmp     rax, rcx
0x18000707b  jz      short loc_18000709B
0x18000707d  test    byte ptr [rax+1Ch], 1
0x180007081  jz      short loc_18000709B
0x180007083  mov     rcx, [rax+10h]
0x180007087  lea     r8, WPP_428964b663db31776494a5e8e5edd24b_Traceguids
0x18000708e  mov     edx, 0Eh
0x180007093  mov     r9d, ebp
0x180007096  call    WPP_SF_d
0x18000709b  test    rdi, rdi
0x18000709e  jz      short loc_1800070A9
0x1800070a0  mov     rcx, rdi
0x1800070a3  call    cs:__imp_FwBaseFree
0x1800070a9  mov     [r12], r13
0x1800070ad  jmp     loc_180006FF7
0x1800070b2  movzx   ebp, bx
0x1800070b5  or      ebp, 80070000h
0x1800070bb  jmp     short loc_180007069
0x1800070bd  mov     rcx, [rax+10h]
0x1800070c1  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x1800070c8  mov     edx, 6Ah ; 'j'
0x1800070cd  call    WPP_SF_
0x1800070d2  jmp     loc_180006F28
0x1800070d7  mov     rcx, rdi
0x1800070da  call    cs:__imp_FwBaseFree
0x1800070e0  jmp     loc_180006FBC
0x1800070e5  mov     ebp, 8007000Eh
0x1800070ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070f1  lea     rax, WPP_GLOBAL_Control
0x1800070f8  cmp     rcx, rax
0x1800070fb  jz      short loc_1800070A9
0x1800070fd  test    byte ptr [rcx+1Ch], 1
0x180007101  jz      short loc_1800070A9
0x180007103  mov     rcx, [rcx+10h]
0x180007107  lea     r8, WPP_428964b663db31776494a5e8e5edd24b_Traceguids
0x18000710e  mov     edx, 0Dh
0x180007113  mov     r9d, ebp
0x180007116  call    WPP_SF_d
0x18000711b  jmp     short loc_1800070A9
```
