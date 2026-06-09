# CTnoNetworkCfg::ReserveHttpUrl(_TNO_URL_RESERVATION_ID)

- ea: `0x18011a450`
- end: `0x18011a7e5`
- name: `?ReserveHttpUrl@CTnoNetworkCfg@@UEAAJW4_TNO_URL_RESERVATION_ID@@@Z`
- size: `917`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180004374`
- `0x180004510`
- `0x180004874`
- `0x180008290`
- `0x180117dbc`
- `0x180118dfc`
- `0x18011a18c`
- `0x18011a450`
- `0x180144882`
- `0x1801448c0`

## import_xrefs

- `HTTPAPI!HttpSetServiceConfiguration` at `0x18011a795`
- `HTTPAPI!HttpSetServiceConfiguration` at `0x18011a795`
- `HTTPAPI!HttpDeleteServiceConfiguration` at `0x18011a6dc`
- `HTTPAPI!HttpDeleteServiceConfiguration` at `0x18011a6dc`

## pseudocode

```c
__int64 __fastcall CTnoNetworkCfg::ReserveHttpUrl(__int64 a1, unsigned int a2)
{
  signed int v4; // ebx
  int v5; // eax
  CTnoNetworkCfg *v6; // rcx
  CHostedCacheMsgEncoding *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  int v10; // eax
  int v11; // eax
  unsigned int v12; // r15d
  CHostedCacheMsgEncoding *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  int v17; // eax
  ULONG v18; // eax
  bool v19; // [rsp+30h] [rbp-D0h] BYREF
  bool v20; // [rsp+31h] [rbp-CFh] BYREF
  __int128 pConfigInformation; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v22[24]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v23[520]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v24[536]; // [rsp+268h] [rbp+168h] BYREF

  v20 = 0;
  v19 = 0;
  memset_0(v23, 0, 0x412u);
  pConfigInformation = 0;
  InCritSec::InCritSec((InCritSec *)v22, (struct CritSec *)(a1 + 8), 1);
  if ( (int)a2 >= 3 )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x4000000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 41, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids);
    }
    v4 = -2147024809;
    goto LABEL_34;
  }
  if ( !CTnoNetworkCfg::CheckIsObjectInitialized((CTnoNetworkCfg *)a1) )
  {
    v4 = -2147020842;
    goto LABEL_34;
  }
  v5 = CTnoNetworkCfg::CopyUrlReservation(a1, a2, v23);
  if ( v5 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x4000000) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_33;
    }
    v8 = 42;
    v9 = (unsigned int)v5;
    goto LABEL_32;
  }
  v10 = CTnoNetworkCfg::QueryUrlReservation(v6, (struct _TNO_URL_RESERVATION *)v23, &v20, &v19);
  v4 = v10;
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x4000000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        43,
        WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids,
        (unsigned int)v10);
    }
    goto LABEL_34;
  }
  if ( v20 && v19 )
    goto LABEL_33;
  v4 = 0;
  if ( !v20 || v19 )
    goto LABEL_43;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x4000000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 44, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids);
  }
  v11 = CTnoNetworkCfg::CopyUrlReservation(a1, a2, v23);
  v12 = v11;
  if ( v11 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x4000000) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      goto LABEL_33;
    }
    v8 = 45;
    v9 = (unsigned int)v11;
LABEL_32:
    WPP_SF_d(*((_QWORD *)v7 + 12), v8, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids, v9);
LABEL_33:
    v4 = 0;
    goto LABEL_34;
  }
  *(_QWORD *)&pConfigInformation = v23;
  *((_QWORD *)&pConfigInformation + 1) = v24;
  v4 = HttpDeleteServiceConfiguration(0, HttpServiceConfigUrlAclInfo, &pConfigInformation, 0x10u, 0);
  if ( v4 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x4000000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v15 = 46;
      v16 = v12;
LABEL_40:
      WPP_SF_d(*((_QWORD *)v14 + 12), v15, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids, v16);
    }
  }
  else
  {
LABEL_43:
    v17 = CTnoNetworkCfg::CopyUrlReservation(a1, a2, v23);
    if ( v17 >= 0 )
    {
      *(_QWORD *)&pConfigInformation = v23;
      *((_QWORD *)&pConfigInformation + 1) = v24;
      v18 = HttpSetServiceConfiguration(0, HttpServiceConfigUrlAclInfo, &pConfigInformation, 0x10u, 0);
      v4 = v18;
      if ( !v18 )
        goto LABEL_33;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x4000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 48, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids, v18);
      }
      goto LABEL_41;
    }
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x4000000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v15 = 47;
      v16 = (unsigned int)v17;
      goto LABEL_40;
    }
  }
LABEL_41:
  if ( v4 > 0 )
    v4 = (unsigned __int16)v4 | 0x80070000;
LABEL_34:
  InCritSec::~InCritSec((InCritSec *)v22);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18011a450  mov     [rsp-8+arg_10], rbx
0x18011a455  mov     [rsp-8+arg_18], rsi
0x18011a45a  push    rbp
0x18011a45b  push    rdi
0x18011a45c  push    r12
0x18011a45e  push    r14
0x18011a460  push    r15
0x18011a462  lea     rbp, [rsp-390h]
0x18011a46a  sub     rsp, 490h
0x18011a471  mov     rax, cs:__security_cookie
0x18011a478  xor     rax, rsp
0x18011a47b  mov     [rbp+3B0h+var_30], rax
0x18011a482  mov     r12d, edx
0x18011a485  mov     [rsp+4B0h+var_47F], 0
0x18011a48a  mov     r14, rcx
0x18011a48d  mov     [rsp+4B0h+var_480], 0
0x18011a492  xor     edx, edx; Val
0x18011a494  lea     rcx, [rsp+4B0h+var_450]; void *
0x18011a499  mov     r8d, 412h; Size
0x18011a49f  call    memset_0
0x18011a4a4  xorps   xmm0, xmm0
0x18011a4a7  lea     rdx, [r14+8]; struct CritSec *
0x18011a4ab  mov     r15b, 1
0x18011a4ae  lea     rcx, [rsp+4B0h+var_468]; this
0x18011a4b3  mov     r8b, r15b; bool
0x18011a4b6  movdqu  [rsp+4B0h+pConfigInformation], xmm0
0x18011a4bc  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x18011a4c1  cmp     r12d, 3
0x18011a4c5  jl      short loc_18011A509
0x18011a4c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18011a4ce  lea     rdi, WPP_GLOBAL_Control
0x18011a4d5  cmp     rcx, rdi
0x18011a4d8  jz      short loc_18011A4FF
0x18011a4da  mov     esi, 4000000h
0x18011a4df  test    [rcx+6Ch], esi
0x18011a4e2  jz      short loc_18011A4FF
0x18011a4e4  cmp     [rcx+69h], r15b
0x18011a4e8  jb      short loc_18011A4FF
0x18011a4ea  mov     rcx, [rcx+60h]
0x18011a4ee  lea     r8, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids
0x18011a4f5  mov     edx, 29h ; ')'
0x18011a4fa  call    WPP_SF_
0x18011a4ff  mov     ebx, 80070057h
0x18011a504  jmp     loc_18011A679
0x18011a509  mov     rcx, r14; this
0x18011a50c  call    ?CheckIsObjectInitialized@CTnoNetworkCfg@@AEAA_NXZ; CTnoNetworkCfg::CheckIsObjectInitialized(void)
0x18011a511  test    al, al
0x18011a513  jnz     short loc_18011A51F
0x18011a515  mov     ebx, 80070FD6h
0x18011a51a  jmp     loc_18011A679
0x18011a51f  lea     r8, [rsp+4B0h+var_450]
0x18011a524  mov     edx, r12d
0x18011a527  mov     rcx, r14
0x18011a52a  call    ?CopyUrlReservation@CTnoNetworkCfg@@AEAAJW4_TNO_URL_RESERVATION_ID@@PEAU_TNO_URL_RESERVATION@@@Z; CTnoNetworkCfg::CopyUrlReservation(_TNO_URL_RESERVATION_ID,_TNO_URL_RESERVATION *)
0x18011a52f  test    eax, eax
0x18011a531  jns     short loc_18011A56F
0x18011a533  mov     rcx, cs:WPP_GLOBAL_Control
0x18011a53a  lea     rdi, WPP_GLOBAL_Control
0x18011a541  cmp     rcx, rdi
0x18011a544  jz      loc_18011A677
0x18011a54a  mov     esi, 4000000h
0x18011a54f  test    [rcx+6Ch], esi
0x18011a552  jz      loc_18011A677
0x18011a558  cmp     [rcx+69h], r15b
0x18011a55c  jb      loc_18011A677
0x18011a562  mov     edx, 2Ah ; '*'
0x18011a567  mov     r9d, eax
0x18011a56a  jmp     loc_18011A667
0x18011a56f  lea     r9, [rsp+4B0h+var_480]; bool *
0x18011a574  lea     r8, [rsp+4B0h+var_47F]; bool *
0x18011a579  lea     rdx, [rsp+4B0h+var_450]; struct _TNO_URL_RESERVATION *
0x18011a57e  call    ?QueryUrlReservation@CTnoNetworkCfg@@AEAAJPEAU_TNO_URL_RESERVATION@@PEA_N1@Z; CTnoNetworkCfg::QueryUrlReservation(_TNO_URL_RESERVATION *,bool *,bool *)
0x18011a583  mov     ebx, eax
0x18011a585  test    eax, eax
0x18011a587  jns     short loc_18011A5D5
0x18011a589  mov     rcx, cs:WPP_GLOBAL_Control
0x18011a590  lea     rdi, WPP_GLOBAL_Control
0x18011a597  cmp     rcx, rdi
0x18011a59a  jz      loc_18011A679
0x18011a5a0  mov     esi, 4000000h
0x18011a5a5  test    [rcx+6Ch], esi
0x18011a5a8  jz      loc_18011A679
0x18011a5ae  cmp     [rcx+69h], r15b
0x18011a5b2  jb      loc_18011A679
0x18011a5b8  mov     rcx, [rcx+60h]
0x18011a5bc  lea     r8, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids
0x18011a5c3  mov     edx, 2Bh ; '+'
0x18011a5c8  mov     r9d, eax
0x18011a5cb  call    WPP_SF_d
0x18011a5d0  jmp     loc_18011A679
0x18011a5d5  mov     cl, [rsp+4B0h+var_47F]
0x18011a5d9  mov     al, [rsp+4B0h+var_480]
0x18011a5dd  test    cl, cl
0x18011a5df  jz      short loc_18011A5E9
0x18011a5e1  test    al, al
0x18011a5e3  jnz     loc_18011A677
0x18011a5e9  xor     ebx, ebx
0x18011a5eb  lea     rdi, WPP_GLOBAL_Control
0x18011a5f2  mov     esi, 4000000h
0x18011a5f7  test    cl, cl
0x18011a5f9  jz      loc_18011A730
0x18011a5ff  test    al, al
0x18011a601  jnz     loc_18011A730
0x18011a607  mov     rcx, cs:WPP_GLOBAL_Control
0x18011a60e  cmp     rcx, rdi
0x18011a611  jz      short loc_18011A631
0x18011a613  test    [rcx+6Ch], esi
0x18011a616  jz      short loc_18011A631
0x18011a618  cmp     byte ptr [rcx+69h], 2
0x18011a61c  jb      short loc_18011A631
0x18011a61e  mov     rcx, [rcx+60h]
0x18011a622  lea     edx, [rbx+2Ch]
0x18011a625  lea     r8, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids
0x18011a62c  call    WPP_SF_
0x18011a631  lea     r8, [rsp+4B0h+var_450]
0x18011a636  mov     edx, r12d
0x18011a639  mov     rcx, r14
0x18011a63c  call    ?CopyUrlReservation@CTnoNetworkCfg@@AEAAJW4_TNO_URL_RESERVATION_ID@@PEAU_TNO_URL_RESERVATION@@@Z; CTnoNetworkCfg::CopyUrlReservation(_TNO_URL_RESERVATION_ID,_TNO_URL_RESERVATION *)
0x18011a641  mov     r15d, eax
0x18011a644  test    eax, eax
0x18011a646  jns     short loc_18011A6B0
0x18011a648  mov     rcx, cs:WPP_GLOBAL_Control
0x18011a64f  cmp     rcx, rdi
0x18011a652  jz      short loc_18011A677
0x18011a654  test    [rcx+6Ch], esi
0x18011a657  jz      short loc_18011A677
0x18011a659  cmp     byte ptr [rcx+69h], 1
0x18011a65d  jb      short loc_18011A677
0x18011a65f  mov     edx, 2Dh ; '-'
0x18011a664  mov     r9d, eax
0x18011a667  mov     rcx, [rcx+60h]
0x18011a66b  lea     r8, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids
0x18011a672  call    WPP_SF_d
0x18011a677  xor     ebx, ebx
0x18011a679  lea     rcx, [rsp+4B0h+var_468]; this
0x18011a67e  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x18011a683  mov     eax, ebx
0x18011a685  mov     rcx, [rbp+3B0h+var_30]
0x18011a68c  xor     rcx, rsp; StackCookie
0x18011a68f  call    __security_check_cookie
0x18011a694  lea     r11, [rsp+4B0h+var_20]
0x18011a69c  mov     rbx, [r11+40h]
0x18011a6a0  mov     rsi, [r11+48h]
0x18011a6a4  mov     rsp, r11
0x18011a6a7  pop     r15
0x18011a6a9  pop     r14
0x18011a6ab  pop     r12
0x18011a6ad  pop     rdi
0x18011a6ae  pop     rbp
0x18011a6af  retn
0x18011a6b0  mov     r9d, 10h; ConfigInformationLength
0x18011a6b6  mov     [rsp+4B0h+pOverlapped], rbx; pOverlapped
0x18011a6bb  lea     rax, [rsp+4B0h+var_450]
0x18011a6c0  xor     ecx, ecx; ServiceHandle
0x18011a6c2  mov     qword ptr [rsp+4B0h+pConfigInformation], rax
0x18011a6c7  lea     r8, [rsp+4B0h+pConfigInformation]; pConfigInformation
0x18011a6cc  lea     rax, [rbp+3B0h+var_248]
0x18011a6d3  lea     edx, [r9-0Eh]; ConfigId
0x18011a6d7  mov     qword ptr [rsp+4B0h+pConfigInformation+8], rax
0x18011a6dc  call    cs:__imp_HttpDeleteServiceConfiguration
0x18011a6e2  mov     ebx, eax
0x18011a6e4  test    eax, eax
0x18011a6e6  jz      short loc_18011A72D
0x18011a6e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18011a6ef  cmp     rcx, rdi
0x18011a6f2  jz      short loc_18011A717
0x18011a6f4  test    [rcx+6Ch], esi
0x18011a6f7  jz      short loc_18011A717
0x18011a6f9  cmp     byte ptr [rcx+69h], 1
0x18011a6fd  jb      short loc_18011A717
0x18011a6ff  mov     edx, 2Eh ; '.'
0x18011a704  mov     r9d, r15d
0x18011a707  mov     rcx, [rcx+60h]
0x18011a70b  lea     r8, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids
0x18011a712  call    WPP_SF_d
0x18011a717  test    ebx, ebx
0x18011a719  jle     loc_18011A679
0x18011a71f  movzx   ebx, bx
0x18011a722  or      ebx, 80070000h
0x18011a728  jmp     loc_18011A679
0x18011a72d  mov     r15b, 1
0x18011a730  lea     r8, [rsp+4B0h+var_450]
0x18011a735  mov     edx, r12d
0x18011a738  mov     rcx, r14
0x18011a73b  call    ?CopyUrlReservation@CTnoNetworkCfg@@AEAAJW4_TNO_URL_RESERVATION_ID@@PEAU_TNO_URL_RESERVATION@@@Z; CTnoNetworkCfg::CopyUrlReservation(_TNO_URL_RESERVATION_ID,_TNO_URL_RESERVATION *)
0x18011a740  test    eax, eax
0x18011a742  jns     short loc_18011A765
0x18011a744  mov     rcx, cs:WPP_GLOBAL_Control
0x18011a74b  cmp     rcx, rdi
0x18011a74e  jz      short loc_18011A717
0x18011a750  test    [rcx+6Ch], esi
0x18011a753  jz      short loc_18011A717
0x18011a755  cmp     [rcx+69h], r15b
0x18011a759  jb      short loc_18011A717
0x18011a75b  mov     edx, 2Fh ; '/'
0x18011a760  mov     r9d, eax
0x18011a763  jmp     short loc_18011A707
0x18011a765  mov     r9d, 10h; ConfigInformationLength
0x18011a76b  mov     [rsp+4B0h+pOverlapped], 0; pOverlapped
0x18011a774  lea     rax, [rsp+4B0h+var_450]
0x18011a779  xor     ecx, ecx; ServiceHandle
0x18011a77b  mov     qword ptr [rsp+4B0h+pConfigInformation], rax
0x18011a780  lea     r8, [rsp+4B0h+pConfigInformation]; pConfigInformation
0x18011a785  lea     rax, [rbp+3B0h+var_248]
0x18011a78c  lea     edx, [r9-0Eh]; ConfigId
0x18011a790  mov     qword ptr [rsp+4B0h+pConfigInformation+8], rax
0x18011a795  call    cs:__imp_HttpSetServiceConfiguration
0x18011a79b  mov     ebx, eax
0x18011a79d  test    eax, eax
0x18011a79f  jz      loc_18011A677
0x18011a7a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18011a7ac  cmp     rcx, rdi
0x18011a7af  jz      loc_18011A717
0x18011a7b5  test    [rcx+6Ch], esi
0x18011a7b8  jz      loc_18011A717
0x18011a7be  cmp     [rcx+69h], r15b
0x18011a7c2  jb      loc_18011A717
0x18011a7c8  mov     rcx, [rcx+60h]
0x18011a7cc  lea     r8, WPP_5a74d6135c0f3c32f7221422afaf5bc4_Traceguids
0x18011a7d3  mov     edx, 30h ; '0'
0x18011a7d8  mov     r9d, eax
0x18011a7db  call    WPP_SF_d
0x18011a7e0  jmp     loc_18011A717
```
