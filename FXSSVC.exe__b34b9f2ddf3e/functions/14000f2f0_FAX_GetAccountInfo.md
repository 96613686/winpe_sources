# FAX_GetAccountInfo

- ea: `0x14000f2f0`
- end: `0x14000f6ec`
- name: `FAX_GetAccountInfo`
- size: `1020`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140004ce4`
- `0x140004df0`
- `0x14000e434`
- `0x14000e8dc`
- `0x14000e964`
- `0x14000f2f0`
- `0x1400452ac`
- `0x140045798`
- `0x140065dbc`
- `0x14006f110`
- `0x140074f30`
- `0x140075928`

## import_xrefs

- `ADVAPI32!EqualSid` at `0x14000f4ab`
- `ADVAPI32!EqualSid` at `0x14000f4ab`
- `KERNEL32!GetLastError` at `0x14000f3d9`
- `KERNEL32!GetLastError` at `0x14000f3d9`
- `KERNEL32!EnterCriticalSection` at `0x14000f56f`
- `KERNEL32!EnterCriticalSection` at `0x14000f56f`
- `KERNEL32!LeaveCriticalSection` at `0x14000f5af`
- `KERNEL32!LeaveCriticalSection` at `0x14000f618`
- `KERNEL32!LeaveCriticalSection` at `0x14000f5af`
- `KERNEL32!LeaveCriticalSection` at `0x14000f618`

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
0x14000f2f0  mov     rax, rsp
0x14000f2f3  mov     [rax+8], rbx
0x14000f2f7  mov     [rax+10h], rbp
0x14000f2fb  push    rsi
0x14000f2fc  push    rdi
0x14000f2fd  push    r12
0x14000f2ff  push    r14
0x14000f301  push    r15
0x14000f303  sub     rsp, 40h
0x14000f307  xor     esi, esi
0x14000f309  mov     dword ptr [rax+18h], 0
0x14000f310  mov     [rax-38h], rsi
0x14000f314  mov     r15, r9
0x14000f317  mov     ebp, r8d
0x14000f31a  mov     rdi, rdx
0x14000f31d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f324  lea     rbx, WPP_GLOBAL_Control
0x14000f32b  lea     r12, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000f332  mov     r14b, 4
0x14000f335  cmp     rcx, rbx
0x14000f338  jz      short loc_14000F35C
0x14000f33a  test    [rcx+1Ch], r14b
0x14000f33e  jz      short loc_14000F35C
0x14000f340  cmp     byte ptr [rcx+19h], 5
0x14000f344  jb      short loc_14000F35C
0x14000f346  mov     rcx, [rcx+10h]
0x14000f34a  lea     edx, [rsi+67h]
0x14000f34d  mov     r8, r12
0x14000f350  call    WPP_SF_
0x14000f355  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f35c  test    ebp, ebp
0x14000f35e  jz      short loc_14000F387
0x14000f360  cmp     rcx, rbx
0x14000f363  jz      short loc_14000F3C2
0x14000f365  test    [rcx+1Ch], r14b
0x14000f369  jz      short loc_14000F3C2
0x14000f36b  cmp     byte ptr [rcx+19h], 2
0x14000f36f  jb      short loc_14000F3C2
0x14000f371  mov     rcx, [rcx+10h]
0x14000f375  mov     edx, 68h ; 'h'
0x14000f37a  mov     r9d, ebp
0x14000f37d  mov     r8, r12
0x14000f380  call    WPP_SF_d
0x14000f385  jmp     short loc_14000F3C2
0x14000f387  test    rdi, rdi
0x14000f38a  jz      short loc_14000F3CC
0x14000f38c  mov     rcx, rdi; Str
0x14000f38f  call    ValidFaxAccountName
0x14000f394  test    eax, eax
0x14000f396  jnz     short loc_14000F3CC
0x14000f398  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f39f  cmp     rcx, rbx
0x14000f3a2  jz      short loc_14000F3C2
0x14000f3a4  test    [rcx+1Ch], r14b
0x14000f3a8  jz      short loc_14000F3C2
0x14000f3aa  cmp     byte ptr [rcx+19h], 2
0x14000f3ae  jb      short loc_14000F3C2
0x14000f3b0  mov     rcx, [rcx+10h]
0x14000f3b4  lea     edx, [rax+69h]
0x14000f3b7  mov     r9, rdi
0x14000f3ba  mov     r8, r12
0x14000f3bd  call    WPP_SF_S
0x14000f3c2  mov     eax, 57h ; 'W'
0x14000f3c7  jmp     loc_14000F6D5
0x14000f3cc  call    ?GetClientUserSID@@YAPEAXXZ; GetClientUserSID(void)
0x14000f3d1  mov     r12, rax
0x14000f3d4  test    rax, rax
0x14000f3d7  jnz     short loc_14000F429
0x14000f3d9  call    cs:__imp_GetLastError
0x14000f3df  mov     ebx, eax
0x14000f3e1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f3e8  lea     rax, WPP_GLOBAL_Control
0x14000f3ef  cmp     rcx, rax
0x14000f3f2  jz      loc_14000F6BE
0x14000f3f8  test    [rcx+1Ch], r14b
0x14000f3fc  jz      loc_14000F6BE
0x14000f402  cmp     byte ptr [rcx+19h], 2
0x14000f406  jb      loc_14000F6BE
0x14000f40c  lea     edx, [r12+6Ah]
0x14000f411  mov     rcx, [rcx+10h]
0x14000f415  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000f41c  mov     r9d, ebx
0x14000f41f  call    WPP_SF_d
0x14000f424  jmp     loc_14000F6BE
0x14000f429  test    rdi, rdi
0x14000f42c  jnz     short loc_14000F433
0x14000f42e  mov     rsi, r12
0x14000f431  jmp     short loc_14000F49B
0x14000f433  xor     r8d, r8d
0x14000f436  lea     rdx, [rsp+68h+var_38]
0x14000f43b  mov     rcx, rdi; lpAccountName
0x14000f43e  call    ConvertUserNameToSid
0x14000f443  mov     ebx, eax
0x14000f445  test    eax, eax
0x14000f447  jz      short loc_14000F496
0x14000f449  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f450  lea     rax, WPP_GLOBAL_Control
0x14000f457  cmp     rcx, rax
0x14000f45a  jz      short loc_14000F484
0x14000f45c  test    [rcx+1Ch], r14b
0x14000f460  jz      short loc_14000F484
0x14000f462  cmp     byte ptr [rcx+19h], 2
0x14000f466  jb      short loc_14000F484
0x14000f468  mov     rcx, [rcx+10h]
0x14000f46c  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000f473  mov     edx, 6Bh ; 'k'
0x14000f478  mov     [rsp+68h+var_48], ebx
0x14000f47c  mov     r9, rdi
0x14000f47f  call    WPP_SF_Sd
0x14000f484  cmp     ebx, 534h
0x14000f48a  jz      short loc_14000F496
0x14000f48c  mov     rsi, [rsp+68h+var_38]
0x14000f491  jmp     loc_14000F6BE
0x14000f496  mov     rsi, [rsp+68h+var_38]
0x14000f49b  mov     ebx, 1
0x14000f4a0  test    rsi, rsi
0x14000f4a3  jz      short loc_14000F4B9
0x14000f4a5  mov     rdx, rsi; pSid2
0x14000f4a8  mov     rcx, r12; pSid1
0x14000f4ab  call    cs:__imp_EqualSid
0x14000f4b1  test    eax, eax
0x14000f4b3  jz      short loc_14000F4B9
0x14000f4b5  mov     eax, ebx
0x14000f4b7  jmp     short loc_14000F4BB
0x14000f4b9  xor     eax, eax
0x14000f4bb  neg     eax
0x14000f4bd  lea     rdx, [rsp+68h+arg_10]; int *
0x14000f4c5  mov     r9d, ebx; int
0x14000f4c8  sbb     ecx, ecx
0x14000f4ca  xor     r8d, r8d; unsigned int *
0x14000f4cd  and     ecx, 1FFFFE0h
0x14000f4d3  add     ecx, 20h ; ' '; unsigned int
0x14000f4d6  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x14000f4db  mov     ebx, eax
0x14000f4dd  test    eax, eax
0x14000f4df  jz      short loc_14000F516
0x14000f4e1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f4e8  lea     rax, WPP_GLOBAL_Control
0x14000f4ef  cmp     rcx, rax
0x14000f4f2  jz      loc_14000F6BE
0x14000f4f8  test    [rcx+1Ch], r14b
0x14000f4fc  jz      loc_14000F6BE
0x14000f502  cmp     byte ptr [rcx+19h], 2
0x14000f506  jb      loc_14000F6BE
0x14000f50c  mov     edx, 6Ch ; 'l'
0x14000f511  jmp     loc_14000F411
0x14000f516  cmp     [rsp+68h+arg_10], 0
0x14000f51e  jnz     short loc_14000F568
0x14000f520  mov     ebx, 5
0x14000f525  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f52c  lea     rax, WPP_GLOBAL_Control
0x14000f533  cmp     rcx, rax
0x14000f536  jz      loc_14000F6BE
0x14000f53c  test    [rcx+1Ch], r14b
0x14000f540  jz      loc_14000F6BE
0x14000f546  cmp     byte ptr [rcx+19h], 2
0x14000f54a  jb      loc_14000F6BE
0x14000f550  mov     rcx, [rcx+10h]
0x14000f554  lea     edx, [rbx+68h]
0x14000f557  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000f55e  call    WPP_SF_
0x14000f563  jmp     loc_14000F6BE
0x14000f568  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000f56f  call    cs:__imp_EnterCriticalSection
0x14000f575  mov     rcx, cs:?g_pAccountList@@3PEAVCFaxAccountList@@EA; CFaxAccountList * g_pAccountList
0x14000f57c  xor     r8d, r8d
0x14000f57f  test    rsi, rsi
0x14000f582  jz      short loc_14000F59B
0x14000f584  mov     rdx, rsi
0x14000f587  call    ?_FindAccountBySid@CFaxAccountList@@AEAAPEAVCFaxAccount@@PEAXPEAV?$_List_iterator@V?$_List_val@U?$_List_simple_types@PEAVCFaxAccount@@@std@@@std@@@std@@@Z; CFaxAccountList::_FindAccountBySid(void *,std::_List_iterator<std::_List_val<std::_List_simple_types<CFaxAccount *>>> *)
0x14000f58c  test    rax, rax
0x14000f58f  jnz     short loc_14000F5F6
0x14000f591  mov     rcx, cs:?g_pAccountList@@3PEAVCFaxAccountList@@EA; CFaxAccountList * g_pAccountList
0x14000f598  xor     r8d, r8d
0x14000f59b  mov     rdx, rdi
0x14000f59e  call    ?_FindAccountByName@CFaxAccountList@@AEAAPEAVCFaxAccount@@PEBGPEAV?$_List_iterator@V?$_List_val@U?$_List_simple_types@PEAVCFaxAccount@@@std@@@std@@@std@@@Z; CFaxAccountList::_FindAccountByName(ushort const *,std::_List_iterator<std::_List_val<std::_List_simple_types<CFaxAccount *>>> *)
0x14000f5a3  test    rax, rax
0x14000f5a6  jnz     short loc_14000F5F6
0x14000f5a8  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000f5af  call    cs:__imp_LeaveCriticalSection
0x14000f5b5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f5bc  lea     rax, WPP_GLOBAL_Control
0x14000f5c3  cmp     rcx, rax
0x14000f5c6  jz      short loc_14000F5EC
0x14000f5c8  test    [rcx+1Ch], r14b
0x14000f5cc  jz      short loc_14000F5EC
0x14000f5ce  cmp     byte ptr [rcx+19h], 2
0x14000f5d2  jb      short loc_14000F5EC
0x14000f5d4  mov     rcx, [rcx+10h]
0x14000f5d8  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000f5df  mov     edx, 6Eh ; 'n'
0x14000f5e4  mov     r9, rdi
0x14000f5e7  call    WPP_SF_S
0x14000f5ec  mov     ebx, 2
0x14000f5f1  jmp     loc_14000F6BE
0x14000f5f6  mov     r14, [rsp+68h+arg_20]
0x14000f5fe  mov     r8d, ebp; unsigned int
0x14000f601  mov     r9, r14; unsigned int *
0x14000f604  mov     rdx, r15; unsigned __int8 **
0x14000f607  mov     rcx, rax; this
0x14000f60a  call    ?Serialize@CFaxAccount@@QEBAKPEAPEAEKPEAK@Z; CFaxAccount::Serialize(uchar * *,ulong,ulong *)
0x14000f60f  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14000f616  mov     ebx, eax
0x14000f618  call    cs:__imp_LeaveCriticalSection
0x14000f61e  test    ebx, ebx
0x14000f620  jz      short loc_14000F64F
0x14000f622  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f629  lea     rax, WPP_GLOBAL_Control
0x14000f630  cmp     rcx, rax
0x14000f633  jz      loc_14000F6BE
0x14000f639  test    byte ptr [rcx+1Ch], 4
0x14000f63d  jz      short loc_14000F6BE
0x14000f63f  cmp     byte ptr [rcx+19h], 2
0x14000f643  jb      short loc_14000F6BE
0x14000f645  mov     edx, 6Fh ; 'o'
0x14000f64a  jmp     loc_14000F411
0x14000f64f  mov     rcx, [r15]; unsigned __int8 *
0x14000f652  lea     rdx, ?fax_account_info0_fields@@3PAU_FieldInfo@@A; struct _FieldInfo *
0x14000f659  mov     r9d, 1
0x14000f65f  lea     r8d, [r9+0Fh]; unsigned __int64
0x14000f663  call    MarshallDownStructure
0x14000f668  test    eax, eax
0x14000f66a  jnz     short loc_14000F6BE
0x14000f66c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f673  lea     rax, WPP_GLOBAL_Control
0x14000f67a  cmp     rcx, rax
0x14000f67d  jz      short loc_14000F6A3
0x14000f67f  test    byte ptr [rcx+1Ch], 4
0x14000f683  jz      short loc_14000F6A3
0x14000f685  cmp     byte ptr [rcx+19h], 2
0x14000f689  jb      short loc_14000F6A3
0x14000f68b  mov     rcx, [rcx+10h]
0x14000f68f  lea     r8, WPP_eb0000c6be0538bb238591c1d6c7686d_Traceguids
0x14000f696  mov     edx, 70h ; 'p'
0x14000f69b  mov     r9d, ebp
0x14000f69e  call    WPP_SF_d
0x14000f6a3  mov     rcx, [r15]; lpMem
0x14000f6a6  call    pMemFree
0x14000f6ab  mov     qword ptr [r15], 0
0x14000f6b2  mov     ebx, 54Fh
0x14000f6b7  mov     dword ptr [r14], 0
0x14000f6be  mov     rcx, r12; lpMem
0x14000f6c1  call    pMemFree
0x14000f6c6  test    rdi, rdi
0x14000f6c9  jz      short loc_14000F6D3
0x14000f6cb  mov     rcx, rsi; lpMem
0x14000f6ce  call    pMemFree
0x14000f6d3  mov     eax, ebx
0x14000f6d5  mov     rbx, [rsp+68h+arg_0]
0x14000f6da  mov     rbp, [rsp+68h+arg_8]
0x14000f6df  add     rsp, 40h
0x14000f6e3  pop     r15
0x14000f6e5  pop     r14
0x14000f6e7  pop     r12
0x14000f6e9  pop     rdi
0x14000f6ea  pop     rsi
0x14000f6eb  retn
```
