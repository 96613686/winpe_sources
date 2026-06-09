# GetDisabledInterfaces(void *,_tag_FW_PROFILE_TYPE,_tag_FW_INTERFACE_LUIDS * *)

- ea: `0x1800073f0`
- end: `0x180007692`
- name: `?GetDisabledInterfaces@@YAJPEAXW4_tag_FW_PROFILE_TYPE@@PEAPEAU_tag_FW_INTERFACE_LUIDS@@@Z`
- size: `674`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18003a170`

## callees

- `0x180005e0c`
- `0x1800073f0`
- `0x180009210`
- `0x1800294b0`
- `0x18003336c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000745c`
- `ntdll!EtwEventWrite` at `0x1800074eb`
- `ntdll!EtwEventWrite` at `0x18000745c`
- `ntdll!EtwEventWrite` at `0x1800074eb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000747e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000747e`
- `fwbase!FwBaseAlloc` at `0x180007522`
- `fwbase!FwBaseAlloc` at `0x180007522`
- `fwbase!FwBaseFree` at `0x18000760c`
- `fwbase!FwBaseFree` at `0x180007649`
- `fwbase!FwBaseFree` at `0x18000760c`
- `fwbase!FwBaseFree` at `0x180007649`

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
      WPP_SF_(*((_QWORD *)v5 + 2), 105, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
    GetTickCount64();
    v11 = Int_FWGetOrSetConfig(1u, a1, 0xFu, a2, 1, v10, v13);
    if ( !v11 )
      goto LABEL_8;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        106,
        WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids,
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
0x1800073f0  mov     [rsp+arg_18], rbx
0x1800073f5  push    rbp
0x1800073f6  push    rsi
0x1800073f7  push    rdi
0x1800073f8  push    r12
0x1800073fa  push    r13
0x1800073fc  push    r14
0x1800073fe  push    r15
0x180007400  sub     rsp, 50h
0x180007404  mov     rax, cs:__security_cookie
0x18000740b  xor     rax, rsp
0x18000740e  mov     [rsp+88h+var_40], rax
0x180007413  xor     r13d, r13d
0x180007416  mov     r14, rcx
0x180007419  mov     [r8], r13
0x18000741c  mov     r12, r8
0x18000741f  mov     rax, cs:WPP_GLOBAL_Control
0x180007426  mov     r15d, edx
0x180007429  mov     rcx, cs:g_Provider
0x180007430  mov     ebp, r13d
0x180007433  mov     [rsp+88h+var_48], r13d
0x180007438  mov     esi, r13d
0x18000743b  mov     edi, r13d
0x18000743e  mov     [rsp+88h+var_44], r13d
0x180007443  lea     rbx, WPP_GLOBAL_Control
0x18000744a  test    rcx, rcx
0x18000744d  jz      short loc_18000746F
0x18000744f  xor     r9d, r9d
0x180007452  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x180007459  xor     r8d, r8d
0x18000745c  call    cs:__imp_EtwEventWrite
0x180007463  nop     dword ptr [rax+rax+00h]
0x180007468  mov     rax, cs:WPP_GLOBAL_Control
0x18000746f  cmp     rax, rbx
0x180007472  jz      short loc_18000747E
0x180007474  test    byte ptr [rax+1Ch], 8
0x180007478  jnz     loc_18000762C
0x18000747e  call    cs:__imp_GetTickCount64
0x180007485  nop     dword ptr [rax+rax+00h]
0x18000748a  lea     rax, [rsp+88h+var_44]
0x18000748f  mov     r9d, r15d
0x180007492  mov     [rsp+88h+var_50], rax
0x180007497  mov     r8d, 0Fh
0x18000749d  lea     rax, [rsp+88h+var_48]
0x1800074a2  mov     rdx, r14
0x1800074a5  mov     [rsp+88h+var_58], rax
0x1800074aa  mov     ecx, 1
0x1800074af  mov     [rsp+88h+var_60], rdi
0x1800074b4  mov     [rsp+88h+var_68], 1
0x1800074bc  call    Int_FWGetOrSetConfig
0x1800074c1  mov     ebx, eax
0x1800074c3  test    eax, eax
0x1800074c5  jnz     loc_18000758E
0x1800074cb  mov     rax, cs:WPP_GLOBAL_Control
0x1800074d2  mov     rcx, cs:g_Provider
0x1800074d9  test    rcx, rcx
0x1800074dc  jz      short loc_180007505
0x1800074de  xor     r9d, r9d
0x1800074e1  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x1800074e8  xor     r8d, r8d
0x1800074eb  call    cs:__imp_EtwEventWrite
0x1800074f2  nop     dword ptr [rax+rax+00h]
0x1800074f7  mov     rax, cs:WPP_GLOBAL_Control
0x1800074fe  mov     rcx, cs:g_Provider
0x180007505  test    ebx, ebx
0x180007507  jz      short loc_180007548
0x180007509  cmp     ebx, 0EAh
0x18000750f  jnz     loc_1800075CC
0x180007515  test    rdi, rdi
0x180007518  jnz     loc_180007646
0x18000751e  mov     ecx, [rsp+88h+var_48]
0x180007522  call    cs:__imp_FwBaseAlloc
0x180007529  nop     dword ptr [rax+rax+00h]
0x18000752e  mov     rdi, rax
0x180007531  test    rax, rax
0x180007534  jz      loc_18000765A
0x18000753a  mov     rax, cs:WPP_GLOBAL_Control
0x180007541  mov     rcx, cs:g_Provider
0x180007548  cmp     esi, 5
0x18000754b  ja      short loc_180007587
0x18000754d  mov     edx, ebp
0x18000754f  test    ebx, ebx
0x180007551  jnz     short loc_180007587
0x180007553  mov     [r12], rdi
0x180007557  test    edx, edx
0x180007559  js      loc_180007604
0x18000755f  mov     eax, ebp
0x180007561  mov     rcx, [rsp+88h+var_40]
0x180007566  xor     rcx, rsp; StackCookie
0x180007569  call    __security_check_cookie
0x18000756e  mov     rbx, [rsp+88h+arg_18]
0x180007576  add     rsp, 50h
0x18000757a  pop     r15
0x18000757c  pop     r14
0x18000757e  pop     r13
0x180007580  pop     r12
0x180007582  pop     rdi
0x180007583  pop     rsi
0x180007584  pop     rbp
0x180007585  retn
0x180007587  inc     esi
0x180007589  jmp     loc_18000743E
0x18000758e  mov     rax, cs:WPP_GLOBAL_Control
0x180007595  lea     rcx, WPP_GLOBAL_Control
0x18000759c  cmp     rax, rcx
0x18000759f  jz      loc_1800074D2
0x1800075a5  test    byte ptr [rax+1Ch], 1
0x1800075a9  jz      loc_1800074D2
0x1800075af  mov     rcx, [rax+10h]
0x1800075b3  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x1800075ba  mov     edx, 6Ah ; 'j'
0x1800075bf  mov     r9d, ebx
0x1800075c2  call    WPP_SF_d
0x1800075c7  jmp     loc_1800074CB
0x1800075cc  test    ebx, ebx
0x1800075ce  jg      short loc_180007621
0x1800075d0  mov     ebp, ebx
0x1800075d2  test    ebp, ebp
0x1800075d4  jns     loc_180007548
0x1800075da  lea     rcx, WPP_GLOBAL_Control
0x1800075e1  cmp     rax, rcx
0x1800075e4  jz      short loc_180007604
0x1800075e6  test    byte ptr [rax+1Ch], 1
0x1800075ea  jz      short loc_180007604
0x1800075ec  mov     rcx, [rax+10h]
0x1800075f0  lea     r8, WPP_428964b663db31776494a5e8e5edd24b_Traceguids
0x1800075f7  mov     edx, 0Eh
0x1800075fc  mov     r9d, ebp
0x1800075ff  call    WPP_SF_d
0x180007604  test    rdi, rdi
0x180007607  jz      short loc_180007618
0x180007609  mov     rcx, rdi
0x18000760c  call    cs:__imp_FwBaseFree
0x180007613  nop     dword ptr [rax+rax+00h]
0x180007618  mov     [r12], r13
0x18000761c  jmp     loc_18000755F
0x180007621  movzx   ebp, bx
0x180007624  or      ebp, 80070000h
0x18000762a  jmp     short loc_1800075D2
0x18000762c  mov     rcx, [rax+10h]
0x180007630  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180007637  mov     edx, 69h ; 'i'
0x18000763c  call    WPP_SF_
0x180007641  jmp     loc_18000747E
0x180007646  mov     rcx, rdi
0x180007649  call    cs:__imp_FwBaseFree
0x180007650  nop     dword ptr [rax+rax+00h]
0x180007655  jmp     loc_18000751E
0x18000765a  mov     ebp, 8007000Eh
0x18000765f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007666  lea     rax, WPP_GLOBAL_Control
0x18000766d  cmp     rcx, rax
0x180007670  jz      short loc_180007618
0x180007672  test    byte ptr [rcx+1Ch], 1
0x180007676  jz      short loc_180007618
0x180007678  mov     rcx, [rcx+10h]
0x18000767c  lea     r8, WPP_428964b663db31776494a5e8e5edd24b_Traceguids
0x180007683  mov     edx, 0Dh
0x180007688  mov     r9d, ebp
0x18000768b  call    WPP_SF_d
0x180007690  jmp     short loc_180007618
```
