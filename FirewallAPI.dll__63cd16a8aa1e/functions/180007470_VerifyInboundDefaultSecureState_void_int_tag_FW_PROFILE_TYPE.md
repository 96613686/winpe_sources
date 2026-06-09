# VerifyInboundDefaultSecureState(void *,int *,_tag_FW_PROFILE_TYPE)

- ea: `0x180007470`
- end: `0x180007875`
- name: `?VerifyInboundDefaultSecureState@@YAJPEAXPEAHW4_tag_FW_PROFILE_TYPE@@@Z`
- size: `1029`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180006394`
- `0x180033630`

## callees

- `0x180005954`
- `0x180007470`
- `0x180008b30`
- `0x18001d554`
- `0x1800277b0`
- `0x18003104c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800074e9`
- `ntdll!EtwEventWrite` at `0x180007571`
- `ntdll!EtwEventWrite` at `0x1800075c1`
- `ntdll!EtwEventWrite` at `0x18000764a`
- `ntdll!EtwEventWrite` at `0x1800074e9`
- `ntdll!EtwEventWrite` at `0x180007571`
- `ntdll!EtwEventWrite` at `0x1800075c1`
- `ntdll!EtwEventWrite` at `0x18000764a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180007505`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800075de`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180007505`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800075de`

## pseudocode

```c
__int64 __fastcall VerifyInboundDefaultSecureState(__int64 a1, _DWORD *a2, unsigned int a3)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  FwPolicy2 *v8; // r10
  __int64 v9; // rcx
  int v10; // eax
  int v11; // esi
  FwPolicy2 *v12; // rax
  int active; // eax
  int v15; // [rsp+40h] [rbp-58h] BYREF
  int v16; // [rsp+44h] [rbp-54h] BYREF
  int v17; // [rsp+48h] [rbp-50h] BYREF
  int v18; // [rsp+4Ch] [rbp-4Ch] BYREF

  v17 = 4;
  v16 = 0;
  v18 = 0;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids);
  *a2 = 0;
  v15 = 0;
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_GetConfig, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  GetTickCount64();
  v6 = Int_FWGetOrSetConfig(1, a1, 3, a3, 1, (__int64)&v16, (__int64)&v17, (__int64)&v15);
  v7 = v6;
  if ( !v6 )
    goto LABEL_10;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v6);
LABEL_10:
    v8 = WPP_GLOBAL_Control;
  }
  v9 = g_Provider;
  if ( g_Provider )
  {
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
    v8 = WPP_GLOBAL_Control;
    v9 = g_Provider;
  }
  if ( v7 == 2 )
  {
    v10 = 0;
    v16 = 0;
  }
  else
  {
    if ( v7 )
    {
      if ( (int)v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
      if ( v8 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)v8 + 2), 44, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids, v7);
      return v7;
    }
    v10 = v16;
  }
  v7 = 0;
  if ( v10 )
  {
    *a2 = 1;
    return v7;
  }
  v15 = 0;
  if ( v9 )
  {
    EtwEventWrite(v9, MPS_CLNT_API_Enter_GetConfig, 0, 0);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)v8 + 2), 106, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  GetTickCount64();
  v11 = Int_FWGetOrSetConfig(1, a1, 17, a3, 1, (__int64)&v18, (__int64)&v17, (__int64)&v15);
  if ( !v11 )
    goto LABEL_23;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      107,
      WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids,
      (unsigned int)v11);
LABEL_23:
    v12 = WPP_GLOBAL_Control;
  }
  if ( g_Provider )
  {
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
    v12 = WPP_GLOBAL_Control;
  }
  if ( v11 == 2 )
    goto LABEL_27;
  if ( v11 )
  {
    if ( v11 > 0 )
      v7 = (unsigned __int16)v11 | 0x80070000;
    else
      v7 = v11;
    if ( v12 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)v12 + 2), 45, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids, v7);
  }
  else
  {
    if ( v18 )
      goto LABEL_27;
    v15 = 0;
    active = ActiveBlockInboundRulesExist(a1, &v15, a3);
    v7 = active;
    if ( active < 0 )
    {
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          46,
          WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids,
          (unsigned int)active);
      return v7;
    }
    if ( v15 )
    {
LABEL_27:
      *a2 = 1;
      return v7;
    }
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids, a3);
    *a2 = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180007470  push    rbx
0x180007472  push    rbp
0x180007473  push    rdi
0x180007474  push    r12
0x180007476  push    r14
0x180007478  push    r15
0x18000747a  sub     rsp, 68h
0x18000747e  mov     rax, cs:__security_cookie
0x180007485  xor     rax, rsp
0x180007488  mov     [rsp+98h+var_48], rax
0x18000748d  xor     r15d, r15d
0x180007490  mov     [rsp+98h+var_50], 4
0x180007498  mov     [rsp+98h+var_54], r15d
0x18000749d  mov     ebp, r8d
0x1800074a0  mov     [rsp+98h+var_4C], r15d
0x1800074a5  mov     rdi, rdx
0x1800074a8  mov     r14, rcx
0x1800074ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800074b2  lea     r12, WPP_GLOBAL_Control
0x1800074b9  cmp     rcx, r12
0x1800074bc  jz      short loc_1800074C8
0x1800074be  test    byte ptr [rcx+1Ch], 8
0x1800074c2  jnz     loc_18000777A
0x1800074c8  mov     [rdi], r15d
0x1800074cb  mov     rcx, cs:g_Provider
0x1800074d2  mov     [rsp+98h+var_58], r15d
0x1800074d7  test    rcx, rcx
0x1800074da  jz      short loc_1800074EF
0x1800074dc  xor     r9d, r9d
0x1800074df  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x1800074e6  xor     r8d, r8d
0x1800074e9  call    cs:__imp_EtwEventWrite
0x1800074ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800074f6  cmp     rcx, r12
0x1800074f9  jz      short loc_180007505
0x1800074fb  test    byte ptr [rcx+1Ch], 8
0x1800074ff  jnz     loc_180007794
0x180007505  call    cs:__imp_GetTickCount64
0x18000750b  lea     rax, [rsp+98h+var_58]
0x180007510  mov     r9d, ebp
0x180007513  mov     [rsp+98h+var_60], rax
0x180007518  mov     r8d, 3
0x18000751e  lea     rax, [rsp+98h+var_50]
0x180007523  mov     rdx, r14
0x180007526  mov     [rsp+98h+var_68], rax
0x18000752b  mov     ecx, 1
0x180007530  lea     rax, [rsp+98h+var_54]
0x180007535  mov     [rsp+98h+var_70], rax
0x18000753a  mov     [rsp+98h+var_78], 1
0x180007542  call    Int_FWGetOrSetConfig
0x180007547  mov     ebx, eax
0x180007549  test    eax, eax
0x18000754b  jnz     loc_180007690
0x180007551  mov     r10, cs:WPP_GLOBAL_Control
0x180007558  mov     rcx, cs:g_Provider
0x18000755f  test    rcx, rcx
0x180007562  jz      short loc_180007585
0x180007564  xor     r9d, r9d
0x180007567  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x18000756e  xor     r8d, r8d
0x180007571  call    cs:__imp_EtwEventWrite
0x180007577  mov     r10, cs:WPP_GLOBAL_Control
0x18000757e  mov     rcx, cs:g_Provider
0x180007585  cmp     ebx, 2
0x180007588  jz      loc_1800077AE
0x18000758e  test    ebx, ebx
0x180007590  jnz     loc_1800076FF
0x180007596  mov     eax, [rsp+98h+var_54]
0x18000759a  mov     ebx, r15d
0x18000759d  test    eax, eax
0x18000759f  jnz     loc_180007688
0x1800075a5  mov     [rsp+98h+var_38], rsi
0x1800075aa  mov     [rsp+98h+var_58], r15d
0x1800075af  test    rcx, rcx
0x1800075b2  jz      short loc_1800075CE
0x1800075b4  xor     r9d, r9d
0x1800075b7  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x1800075be  xor     r8d, r8d
0x1800075c1  call    cs:__imp_EtwEventWrite
0x1800075c7  mov     r10, cs:WPP_GLOBAL_Control
0x1800075ce  cmp     r10, r12
0x1800075d1  jz      short loc_1800075DE
0x1800075d3  test    byte ptr [r10+1Ch], 8
0x1800075d8  jnz     loc_1800077BA
0x1800075de  call    cs:__imp_GetTickCount64
0x1800075e4  lea     rax, [rsp+98h+var_58]
0x1800075e9  mov     r9d, ebp
0x1800075ec  mov     [rsp+98h+var_60], rax
0x1800075f1  mov     r8d, 11h
0x1800075f7  lea     rax, [rsp+98h+var_50]
0x1800075fc  mov     rdx, r14
0x1800075ff  mov     [rsp+98h+var_68], rax
0x180007604  mov     ecx, 1
0x180007609  lea     rax, [rsp+98h+var_4C]
0x18000760e  mov     [rsp+98h+var_70], rax
0x180007613  mov     [rsp+98h+var_78], 1
0x18000761b  call    Int_FWGetOrSetConfig
0x180007620  mov     esi, eax
0x180007622  test    eax, eax
0x180007624  jnz     loc_1800076C8
0x18000762a  mov     rax, cs:WPP_GLOBAL_Control
0x180007631  mov     rcx, cs:g_Provider
0x180007638  test    rcx, rcx
0x18000763b  jz      short loc_180007657
0x18000763d  xor     r9d, r9d
0x180007640  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x180007647  xor     r8d, r8d
0x18000764a  call    cs:__imp_EtwEventWrite
0x180007650  mov     rax, cs:WPP_GLOBAL_Control
0x180007657  cmp     esi, 2
0x18000765a  jnz     loc_1800077D4
0x180007660  mov     dword ptr [rdi], 1
0x180007666  mov     rsi, [rsp+98h+var_38]
0x18000766b  mov     eax, ebx
0x18000766d  mov     rcx, [rsp+98h+var_48]
0x180007672  xor     rcx, rsp; StackCookie
0x180007675  call    __security_check_cookie
0x18000767a  add     rsp, 68h
0x18000767e  pop     r15
0x180007680  pop     r14
0x180007682  pop     r12
0x180007684  pop     rdi
0x180007685  pop     rbp
0x180007686  pop     rbx
0x180007687  retn
0x180007688  mov     dword ptr [rdi], 1
0x18000768e  jmp     short loc_18000766B
0x180007690  mov     r10, cs:WPP_GLOBAL_Control
0x180007697  cmp     r10, r12
0x18000769a  jz      loc_180007558
0x1800076a0  test    byte ptr [r10+1Ch], 1
0x1800076a5  jz      loc_180007558
0x1800076ab  mov     rcx, [r10+10h]
0x1800076af  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x1800076b6  mov     edx, 6Bh ; 'k'
0x1800076bb  mov     r9d, ebx
0x1800076be  call    WPP_SF_d
0x1800076c3  jmp     loc_180007551
0x1800076c8  mov     rax, cs:WPP_GLOBAL_Control
0x1800076cf  cmp     rax, r12
0x1800076d2  jz      loc_180007631
0x1800076d8  test    byte ptr [rax+1Ch], 1
0x1800076dc  jz      loc_180007631
0x1800076e2  mov     rcx, [rax+10h]
0x1800076e6  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x1800076ed  mov     edx, 6Bh ; 'k'
0x1800076f2  mov     r9d, esi
0x1800076f5  call    WPP_SF_d
0x1800076fa  jmp     loc_18000762A
0x1800076ff  jle     short loc_18000770A
0x180007701  movzx   ebx, bx
0x180007704  or      ebx, 80070000h
0x18000770a  cmp     r10, r12
0x18000770d  jz      loc_18000766B
0x180007713  test    byte ptr [r10+1Ch], 1
0x180007718  jz      loc_18000766B
0x18000771e  mov     rcx, [r10+10h]
0x180007722  lea     r8, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids
0x180007729  mov     edx, 2Ch ; ','
0x18000772e  mov     r9d, ebx
0x180007731  call    WPP_SF_d
0x180007736  jmp     loc_18000766B
0x18000773b  jg      short loc_18000776F
0x18000773d  mov     ebx, esi
0x18000773f  cmp     rax, r12
0x180007742  jz      loc_180007666
0x180007748  test    byte ptr [rax+1Ch], 1
0x18000774c  jz      loc_180007666
0x180007752  mov     rcx, [rax+10h]
0x180007756  lea     r8, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids
0x18000775d  mov     edx, 2Dh ; '-'
0x180007762  mov     r9d, ebx
0x180007765  call    WPP_SF_d
0x18000776a  jmp     loc_180007666
0x18000776f  movzx   ebx, si
0x180007772  or      ebx, 80070000h
0x180007778  jmp     short loc_18000773F
0x18000777a  mov     rcx, [rcx+10h]
0x18000777e  lea     r8, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids
0x180007785  mov     edx, 2Bh ; '+'
0x18000778a  call    WPP_SF_
0x18000778f  jmp     loc_1800074C8
0x180007794  mov     rcx, [rcx+10h]
0x180007798  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000779f  mov     edx, 6Ah ; 'j'
0x1800077a4  call    WPP_SF_
0x1800077a9  jmp     loc_180007505
0x1800077ae  mov     eax, r15d
0x1800077b1  mov     [rsp+98h+var_54], eax
0x1800077b5  jmp     loc_18000759A
0x1800077ba  mov     rcx, [r10+10h]
0x1800077be  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x1800077c5  mov     edx, 6Ah ; 'j'
0x1800077ca  call    WPP_SF_
0x1800077cf  jmp     loc_1800075DE
0x1800077d4  test    esi, esi
0x1800077d6  jnz     loc_18000773B
0x1800077dc  cmp     [rsp+98h+var_4C], ebx
0x1800077e0  jnz     loc_180007660
0x1800077e6  mov     r8d, ebp
0x1800077e9  mov     [rsp+98h+var_58], r15d
0x1800077ee  lea     rdx, [rsp+98h+var_58]
0x1800077f3  mov     rcx, r14
0x1800077f6  call    ?ActiveBlockInboundRulesExist@@YAJPEAXPEAHW4_tag_FW_PROFILE_TYPE@@@Z; ActiveBlockInboundRulesExist(void *,int *,_tag_FW_PROFILE_TYPE)
0x1800077fb  mov     ebx, eax
0x1800077fd  test    eax, eax
0x1800077ff  jns     short loc_180007838
0x180007801  mov     rcx, cs:WPP_GLOBAL_Control
0x180007808  cmp     rcx, r12
0x18000780b  jz      loc_180007666
0x180007811  test    byte ptr [rcx+1Ch], 1
0x180007815  jz      loc_180007666
0x18000781b  mov     rcx, [rcx+10h]
0x18000781f  lea     r8, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids
0x180007826  mov     edx, 2Eh ; '.'
0x18000782b  mov     r9d, eax
0x18000782e  call    WPP_SF_d
0x180007833  jmp     loc_180007666
0x180007838  cmp     [rsp+98h+var_58], r15d
0x18000783d  jnz     loc_180007660
0x180007843  mov     rcx, cs:WPP_GLOBAL_Control
0x18000784a  cmp     rcx, r12
0x18000784d  jz      short loc_18000786D
0x18000784f  test    byte ptr [rcx+1Ch], 4
0x180007853  jz      short loc_18000786D
0x180007855  mov     rcx, [rcx+10h]
0x180007859  lea     r8, WPP_7a1bb6b0559931aedf4a075b0cecbabd_Traceguids
0x180007860  mov     edx, 2Fh ; '/'
0x180007865  mov     r9d, ebp
0x180007868  call    WPP_SF_d
0x18000786d  mov     [rdi], r15d
0x180007870  jmp     loc_180007666
```
