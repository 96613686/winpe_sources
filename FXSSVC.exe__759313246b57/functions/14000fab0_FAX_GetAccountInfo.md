# FAX_GetAccountInfo

- ea: `0x14000fab0`
- end: `0x14000fecb`
- name: `FAX_GetAccountInfo`
- size: `1051`
- prototype: `__int64 __fastcall(__int64, wchar_t *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140004e48`
- `0x140004f64`
- `0x14000eba4`
- `0x14000f050`
- `0x14000f0e0`
- `0x14000fab0`
- `0x140047d20`
- `0x140048284`
- `0x14006998c`
- `0x1400735ec`
- `0x140079adc`
- `0x14007a518`

## import_xrefs

- `ADVAPI32!EqualSid` at `0x14000fc71`
- `ADVAPI32!EqualSid` at `0x14000fc71`
- `KERNEL32!GetLastError` at `0x14000fb99`
- `KERNEL32!GetLastError` at `0x14000fb99`
- `KERNEL32!EnterCriticalSection` at `0x14000fd3b`
- `KERNEL32!EnterCriticalSection` at `0x14000fd3b`
- `KERNEL32!LeaveCriticalSection` at `0x14000fd81`
- `KERNEL32!LeaveCriticalSection` at `0x14000fdf0`
- `KERNEL32!LeaveCriticalSection` at `0x14000fd81`
- `KERNEL32!LeaveCriticalSection` at `0x14000fdf0`

## pseudocode

```c
__int64 __fastcall FAX_GetAccountInfo(__int64 a1, wchar_t *a2, unsigned int a3, unsigned __int8 **a4, unsigned int *a5)
{
  void *v5; // rsi
  CMapDeviceId *v9; // rcx
  void *ClientUserSID; // rax
  void *v12; // r12
  unsigned int LastError; // ebx
  CMapDeviceId *v14; // rcx
  __int64 v15; // rdx
  BOOL v16; // eax
  CFaxAccountList *v17; // rcx
  CFaxAccount *AccountBySid; // rax
  unsigned int *v19; // r14
  int v20; // [rsp+80h] [rbp+18h] BYREF

  v5 = 0;
  v20 = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  if ( a3 )
  {
    if ( v9 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 && *((_BYTE *)v9 + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)v9 + 2), 104, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids, a3);
    return 87;
  }
  if ( a2 && !(unsigned int)ValidFaxAccountName(a2) )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids, a2);
    }
    return 87;
  }
  ClientUserSID = GetClientUserSID();
  v12 = ClientUserSID;
  if ( !ClientUserSID )
  {
    LastError = GetLastError();
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_67;
    }
    v15 = 106;
    goto LABEL_22;
  }
  if ( a2 )
  {
    LastError = ConvertUserNameToSid(a2);
    if ( LastError )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          107,
          (unsigned int)&WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids,
          (_DWORD)a2,
          LastError);
      }
      if ( LastError != 1332 )
      {
        v5 = 0;
        goto LABEL_67;
      }
    }
    v5 = 0;
  }
  else
  {
    v5 = ClientUserSID;
  }
  v16 = v5 && EqualSid(v12, v5);
  LastError = FaxSvcAccessCheck(v16 ? 0x2000000 : 32, &v20, 0, 1);
  if ( LastError )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_67;
    }
    v15 = 108;
    goto LABEL_22;
  }
  if ( !v20 )
  {
    LastError = 5;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids);
    }
    goto LABEL_67;
  }
  EnterCriticalSection(&g_CsConfig);
  v17 = g_pAccountList;
  if ( v5 )
  {
    AccountBySid = (CFaxAccount *)CFaxAccountList::_FindAccountBySid(g_pAccountList, v5, 0);
    if ( AccountBySid )
      goto LABEL_56;
    v17 = g_pAccountList;
  }
  AccountBySid = (CFaxAccount *)CFaxAccountList::_FindAccountByName(v17, a2, 0);
  if ( !AccountBySid )
  {
    LeaveCriticalSection(&g_CsConfig);
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids, a2);
    }
    LastError = 2;
    goto LABEL_67;
  }
LABEL_56:
  v19 = a5;
  LastError = CFaxAccount::Serialize(AccountBySid, a4, 0, a5);
  LeaveCriticalSection(&g_CsConfig);
  if ( !LastError )
  {
    if ( !(unsigned int)MarshallDownStructure(*a4, (struct _FieldInfo *)&fax_account_info0_fields, 0x10u) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids, 0);
      }
      pMemFree(*a4);
      *a4 = 0;
      LastError = 1359;
      *v19 = 0;
    }
    goto LABEL_67;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v15 = 111;
LABEL_22:
    WPP_SF_d(*((_QWORD *)v14 + 2), v15, &WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids, LastError);
  }
LABEL_67:
  pMemFree(v12);
  if ( a2 )
    pMemFree(v5);
  return LastError;
}

```

## disassembly

```asm
0x14000fab0  mov     rax, rsp
0x14000fab3  mov     [rax+8], rbx
0x14000fab7  mov     [rax+10h], rbp
0x14000fabb  push    rsi
0x14000fabc  push    rdi
0x14000fabd  push    r12
0x14000fabf  push    r14
0x14000fac1  push    r15
0x14000fac3  sub     rsp, 40h
0x14000fac7  xor     esi, esi
0x14000fac9  mov     dword ptr [rax+18h], 0
0x14000fad0  mov     [rax-38h], rsi
0x14000fad4  mov     r15, r9
0x14000fad7  mov     ebp, r8d
0x14000fada  mov     rdi, rdx
0x14000fadd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fae4  lea     rbx, WPP_GLOBAL_Control
0x14000faeb  lea     r12, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000faf2  mov     r14b, 4
0x14000faf5  cmp     rcx, rbx
0x14000faf8  jz      short loc_14000FB1C
0x14000fafa  test    [rcx+1Ch], r14b
0x14000fafe  jz      short loc_14000FB1C
0x14000fb00  cmp     byte ptr [rcx+19h], 5
0x14000fb04  jb      short loc_14000FB1C
0x14000fb06  mov     rcx, [rcx+10h]
0x14000fb0a  lea     edx, [rsi+67h]
0x14000fb0d  mov     r8, r12
0x14000fb10  call    WPP_SF_
0x14000fb15  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fb1c  test    ebp, ebp
0x14000fb1e  jz      short loc_14000FB47
0x14000fb20  cmp     rcx, rbx
0x14000fb23  jz      short loc_14000FB82
0x14000fb25  test    [rcx+1Ch], r14b
0x14000fb29  jz      short loc_14000FB82
0x14000fb2b  cmp     byte ptr [rcx+19h], 2
0x14000fb2f  jb      short loc_14000FB82
0x14000fb31  mov     rcx, [rcx+10h]
0x14000fb35  mov     edx, 68h ; 'h'
0x14000fb3a  mov     r9d, ebp
0x14000fb3d  mov     r8, r12
0x14000fb40  call    WPP_SF_d
0x14000fb45  jmp     short loc_14000FB82
0x14000fb47  test    rdi, rdi
0x14000fb4a  jz      short loc_14000FB8C
0x14000fb4c  mov     rcx, rdi; Str
0x14000fb4f  call    ValidFaxAccountName
0x14000fb54  test    eax, eax
0x14000fb56  jnz     short loc_14000FB8C
0x14000fb58  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fb5f  cmp     rcx, rbx
0x14000fb62  jz      short loc_14000FB82
0x14000fb64  test    [rcx+1Ch], r14b
0x14000fb68  jz      short loc_14000FB82
0x14000fb6a  cmp     byte ptr [rcx+19h], 2
0x14000fb6e  jb      short loc_14000FB82
0x14000fb70  mov     rcx, [rcx+10h]
0x14000fb74  lea     edx, [rax+69h]
0x14000fb77  mov     r9, rdi
0x14000fb7a  mov     r8, r12
0x14000fb7d  call    WPP_SF_S
0x14000fb82  mov     eax, 57h ; 'W'
0x14000fb87  jmp     loc_14000FEB3
0x14000fb8c  call    ?GetClientUserSID@@YAPEAXXZ; GetClientUserSID(void)
0x14000fb91  mov     r12, rax
0x14000fb94  test    rax, rax
0x14000fb97  jnz     short loc_14000FBEF
0x14000fb99  call    cs:__imp_GetLastError
0x14000fba0  nop     dword ptr [rax+rax+00h]
0x14000fba5  mov     ebx, eax
0x14000fba7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fbae  lea     rax, WPP_GLOBAL_Control
0x14000fbb5  cmp     rcx, rax
0x14000fbb8  jz      loc_14000FE9C
0x14000fbbe  test    [rcx+1Ch], r14b
0x14000fbc2  jz      loc_14000FE9C
0x14000fbc8  cmp     byte ptr [rcx+19h], 2
0x14000fbcc  jb      loc_14000FE9C
0x14000fbd2  lea     edx, [r12+6Ah]
0x14000fbd7  mov     rcx, [rcx+10h]
0x14000fbdb  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000fbe2  mov     r9d, ebx
0x14000fbe5  call    WPP_SF_d
0x14000fbea  jmp     loc_14000FE9C
0x14000fbef  test    rdi, rdi
0x14000fbf2  jnz     short loc_14000FBF9
0x14000fbf4  mov     rsi, r12
0x14000fbf7  jmp     short loc_14000FC61
0x14000fbf9  xor     r8d, r8d
0x14000fbfc  lea     rdx, [rsp+68h+var_38]
0x14000fc01  mov     rcx, rdi; lpAccountName
0x14000fc04  call    ConvertUserNameToSid
0x14000fc09  mov     ebx, eax
0x14000fc0b  test    eax, eax
0x14000fc0d  jz      short loc_14000FC5C
0x14000fc0f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fc16  lea     rax, WPP_GLOBAL_Control
0x14000fc1d  cmp     rcx, rax
0x14000fc20  jz      short loc_14000FC4A
0x14000fc22  test    [rcx+1Ch], r14b
0x14000fc26  jz      short loc_14000FC4A
0x14000fc28  cmp     byte ptr [rcx+19h], 2
0x14000fc2c  jb      short loc_14000FC4A
0x14000fc2e  mov     rcx, [rcx+10h]
0x14000fc32  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000fc39  mov     edx, 6Bh ; 'k'
0x14000fc3e  mov     [rsp+68h+var_48], ebx
0x14000fc42  mov     r9, rdi
0x14000fc45  call    WPP_SF_Sd
0x14000fc4a  cmp     ebx, 534h
0x14000fc50  jz      short loc_14000FC5C
0x14000fc52  mov     rsi, [rsp+68h+var_38]
0x14000fc57  jmp     loc_14000FE9C
0x14000fc5c  mov     rsi, [rsp+68h+var_38]
0x14000fc61  mov     ebx, 1
0x14000fc66  test    rsi, rsi
0x14000fc69  jz      short loc_14000FC85
0x14000fc6b  mov     rdx, rsi; pSid2
0x14000fc6e  mov     rcx, r12; pSid1
0x14000fc71  call    cs:__imp_EqualSid
0x14000fc78  nop     dword ptr [rax+rax+00h]
0x14000fc7d  test    eax, eax
0x14000fc7f  jz      short loc_14000FC85
0x14000fc81  mov     eax, ebx
0x14000fc83  jmp     short loc_14000FC87
0x14000fc85  xor     eax, eax
0x14000fc87  neg     eax
0x14000fc89  lea     rdx, [rsp+68h+arg_10]; int *
0x14000fc91  mov     r9d, ebx; int
0x14000fc94  sbb     ecx, ecx
0x14000fc96  xor     r8d, r8d; unsigned int *
0x14000fc99  and     ecx, 1FFFFE0h
0x14000fc9f  add     ecx, 20h ; ' '; unsigned int
0x14000fca2  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x14000fca7  mov     ebx, eax
0x14000fca9  test    eax, eax
0x14000fcab  jz      short loc_14000FCE2
0x14000fcad  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fcb4  lea     rax, WPP_GLOBAL_Control
0x14000fcbb  cmp     rcx, rax
0x14000fcbe  jz      loc_14000FE9C
0x14000fcc4  test    [rcx+1Ch], r14b
0x14000fcc8  jz      loc_14000FE9C
0x14000fcce  cmp     byte ptr [rcx+19h], 2
0x14000fcd2  jb      loc_14000FE9C
0x14000fcd8  mov     edx, 6Ch ; 'l'
0x14000fcdd  jmp     loc_14000FBD7
0x14000fce2  cmp     [rsp+68h+arg_10], 0
0x14000fcea  jnz     short loc_14000FD34
0x14000fcec  mov     ebx, 5
0x14000fcf1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fcf8  lea     rax, WPP_GLOBAL_Control
0x14000fcff  cmp     rcx, rax
0x14000fd02  jz      loc_14000FE9C
0x14000fd08  test    [rcx+1Ch], r14b
0x14000fd0c  jz      loc_14000FE9C
0x14000fd12  cmp     byte ptr [rcx+19h], 2
0x14000fd16  jb      loc_14000FE9C
0x14000fd1c  mov     rcx, [rcx+10h]
0x14000fd20  lea     edx, [rbx+68h]
0x14000fd23  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000fd2a  call    WPP_SF_
0x14000fd2f  jmp     loc_14000FE9C
0x14000fd34  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000fd3b  call    cs:__imp_EnterCriticalSection
0x14000fd42  nop     dword ptr [rax+rax+00h]
0x14000fd47  mov     rcx, cs:?g_pAccountList@@3PEAVCFaxAccountList@@EA; CFaxAccountList * g_pAccountList
0x14000fd4e  xor     r8d, r8d
0x14000fd51  test    rsi, rsi
0x14000fd54  jz      short loc_14000FD6D
0x14000fd56  mov     rdx, rsi
0x14000fd59  call    ?_FindAccountBySid@CFaxAccountList@@AEAAPEAVCFaxAccount@@PEAXPEAV?$_List_iterator@V?$_List_val@U?$_List_simple_types@PEAVCFaxAccount@@@std@@@std@@@std@@@Z; CFaxAccountList::_FindAccountBySid(void *,std::_List_iterator<std::_List_val<std::_List_simple_types<CFaxAccount *>>> *)
0x14000fd5e  test    rax, rax
0x14000fd61  jnz     short loc_14000FDCE
0x14000fd63  mov     rcx, cs:?g_pAccountList@@3PEAVCFaxAccountList@@EA; CFaxAccountList * g_pAccountList
0x14000fd6a  xor     r8d, r8d
0x14000fd6d  mov     rdx, rdi
0x14000fd70  call    ?_FindAccountByName@CFaxAccountList@@AEAAPEAVCFaxAccount@@PEBGPEAV?$_List_iterator@V?$_List_val@U?$_List_simple_types@PEAVCFaxAccount@@@std@@@std@@@std@@@Z; CFaxAccountList::_FindAccountByName(ushort const *,std::_List_iterator<std::_List_val<std::_List_simple_types<CFaxAccount *>>> *)
0x14000fd75  test    rax, rax
0x14000fd78  jnz     short loc_14000FDCE
0x14000fd7a  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000fd81  call    cs:__imp_LeaveCriticalSection
0x14000fd88  nop     dword ptr [rax+rax+00h]
0x14000fd8d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fd94  lea     rax, WPP_GLOBAL_Control
0x14000fd9b  cmp     rcx, rax
0x14000fd9e  jz      short loc_14000FDC4
0x14000fda0  test    [rcx+1Ch], r14b
0x14000fda4  jz      short loc_14000FDC4
0x14000fda6  cmp     byte ptr [rcx+19h], 2
0x14000fdaa  jb      short loc_14000FDC4
0x14000fdac  mov     rcx, [rcx+10h]
0x14000fdb0  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000fdb7  mov     edx, 6Eh ; 'n'
0x14000fdbc  mov     r9, rdi
0x14000fdbf  call    WPP_SF_S
0x14000fdc4  mov     ebx, 2
0x14000fdc9  jmp     loc_14000FE9C
0x14000fdce  mov     r14, [rsp+68h+arg_20]
0x14000fdd6  mov     r8d, ebp; unsigned int
0x14000fdd9  mov     r9, r14; unsigned int *
0x14000fddc  mov     rdx, r15; unsigned __int8 **
0x14000fddf  mov     rcx, rax; this
0x14000fde2  call    ?Serialize@CFaxAccount@@QEBAKPEAPEAEKPEAK@Z; CFaxAccount::Serialize(uchar * *,ulong,ulong *)
0x14000fde7  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000fdee  mov     ebx, eax
0x14000fdf0  call    cs:__imp_LeaveCriticalSection
0x14000fdf7  nop     dword ptr [rax+rax+00h]
0x14000fdfc  test    ebx, ebx
0x14000fdfe  jz      short loc_14000FE2D
0x14000fe00  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fe07  lea     rax, WPP_GLOBAL_Control
0x14000fe0e  cmp     rcx, rax
0x14000fe11  jz      loc_14000FE9C
0x14000fe17  test    byte ptr [rcx+1Ch], 4
0x14000fe1b  jz      short loc_14000FE9C
0x14000fe1d  cmp     byte ptr [rcx+19h], 2
0x14000fe21  jb      short loc_14000FE9C
0x14000fe23  mov     edx, 6Fh ; 'o'
0x14000fe28  jmp     loc_14000FBD7
0x14000fe2d  mov     rcx, [r15]; unsigned __int8 *
0x14000fe30  lea     rdx, ?fax_account_info0_fields@@3PAU_FieldInfo@@A; struct _FieldInfo *
0x14000fe37  mov     r9d, 1
0x14000fe3d  lea     r8d, [r9+0Fh]; unsigned __int64
0x14000fe41  call    MarshallDownStructure
0x14000fe46  test    eax, eax
0x14000fe48  jnz     short loc_14000FE9C
0x14000fe4a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fe51  lea     rax, WPP_GLOBAL_Control
0x14000fe58  cmp     rcx, rax
0x14000fe5b  jz      short loc_14000FE81
0x14000fe5d  test    byte ptr [rcx+1Ch], 4
0x14000fe61  jz      short loc_14000FE81
0x14000fe63  cmp     byte ptr [rcx+19h], 2
0x14000fe67  jb      short loc_14000FE81
0x14000fe69  mov     rcx, [rcx+10h]
0x14000fe6d  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000fe74  mov     edx, 70h ; 'p'
0x14000fe79  mov     r9d, ebp
0x14000fe7c  call    WPP_SF_d
0x14000fe81  mov     rcx, [r15]; lpMem
0x14000fe84  call    pMemFree
0x14000fe89  mov     qword ptr [r15], 0
0x14000fe90  mov     ebx, 54Fh
0x14000fe95  mov     dword ptr [r14], 0
0x14000fe9c  mov     rcx, r12; lpMem
0x14000fe9f  call    pMemFree
0x14000fea4  test    rdi, rdi
0x14000fea7  jz      short loc_14000FEB1
0x14000fea9  mov     rcx, rsi; lpMem
0x14000feac  call    pMemFree
0x14000feb1  mov     eax, ebx
0x14000feb3  mov     rbx, [rsp+68h+arg_0]
0x14000feb8  mov     rbp, [rsp+68h+arg_8]
0x14000febd  add     rsp, 40h
0x14000fec1  pop     r15
0x14000fec3  pop     r14
0x14000fec5  pop     r12
0x14000fec7  pop     rdi
0x14000fec8  pop     rsi
0x14000fec9  retn
```
