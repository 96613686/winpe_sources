# WriteSharedPbkOptions

- ea: `0x180065484`
- end: `0x1800658ef`
- name: `WriteSharedPbkOptions`
- size: `1131`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, LPCCH, HANDLE hToken)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180045f64`

## callees

- `0x180005e34`
- `0x180005f1c`
- `0x18005c020`
- `0x18005de1c`
- `0x1800638dc`
- `0x1800650a8`
- `0x1800653d4`
- `0x180065484`
- `0x180066c44`
- `0x1800697e0`
- `0x18007c5d8`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065728`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065875`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065728`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065875`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18006571e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18006571e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006586b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006586b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006582e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006582e`

## pseudocode

```c
__int64 __fastcall WriteSharedPbkOptions(LPCCH lpMultiByteStr, LPCCH a2, HANDLE hToken, __int64 a4)
{
  struct _LIST_ENTRY *v8; // rbx
  __int64 v9; // rcx
  LPCCH v10; // rax
  __int64 v12; // rcx
  LPCCH v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rsi
  struct _LIST_ENTRY *v16; // rcx
  unsigned int updated; // ebx
  __int64 v18; // rdx
  DWORD LastError; // eax
  struct _LIST_ENTRY *v20; // rcx
  __int64 v21; // rdx
  unsigned int PbkAndEntryName; // eax
  struct _LIST_ENTRY *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r9
  HGLOBAL hMem; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+38h] [rbp-C8h] BYREF
  _OWORD v28[3]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v29; // [rsp+70h] [rbp-90h]
  WCHAR v30[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v31[524]; // [rsp+84h] [rbp-7Ch] BYREF
  WCHAR WideCharStr[2]; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v33[524]; // [rsp+294h] [rbp+194h] BYREF

  if ( lpMultiByteStr && a2 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x1000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      WPP_SF_ssq(
        WPP_GLOBAL_Control[1].Flink,
        (_DWORD)a2,
        (_DWORD)hToken,
        (_DWORD)lpMultiByteStr,
        (__int64)a2,
        (char)hToken);
LABEL_11:
      v8 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x1000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 25, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, hToken);
      goto LABEL_11;
    }
  }
  v29 = 0;
  memset(v28, 0, sizeof(v28));
  v27 = 0;
  *(_DWORD *)WideCharStr = 0;
  memset_0(v33, 0, 0x204u);
  *(_DWORD *)v30 = 0;
  memset_0(v31, 0, 0x1FEu);
  hMem = 0;
  if ( !lpMultiByteStr )
  {
LABEL_23:
    if ( !a2 )
      goto LABEL_27;
    v12 = 1537;
    v13 = a2;
    while ( *v13 )
    {
      ++v13;
      if ( !--v12 )
        goto LABEL_27;
    }
    if ( !*a2 )
    {
LABEL_27:
      if ( v8 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(v8[1].Blink) & 0x1000) == 0
        || BYTE1(v8[1].Blink) < 2u )
      {
        return 87;
      }
      v14 = 27;
LABEL_31:
      WPP_SF_d(v8[1].Flink, v14, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, 87);
      return 87;
    }
    if ( !a4 )
    {
      if ( v8 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(v8[1].Blink) & 0x1000) == 0
        || BYTE1(v8[1].Blink) < 2u )
      {
        return 87;
      }
      v14 = 28;
      goto LABEL_31;
    }
    if ( lpMultiByteStr )
      StrncpyAtoW(WideCharStr, lpMultiByteStr);
    StrncpyAtoW(v30, a2);
    v15 = -(__int64)lpMultiByteStr;
    if ( !(unsigned int)IsExistingEntry((unsigned __int64)WideCharStr & -(__int64)(v15 != 0), v30) )
    {
      v16 = WPP_GLOBAL_Control;
      updated = 623;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x1000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        return updated;
      }
      v18 = 29;
LABEL_46:
      WPP_SF_d(v16[1].Flink, v18, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, updated);
      return updated;
    }
    RasUpdatePbkIpv6Info((unsigned __int64)WideCharStr & -(__int64)(v15 != 0), v30, a4);
    if ( !ImpersonateLoggedOnUser(hToken) )
    {
      LastError = GetLastError();
      updated = LastError;
      if ( !LastError )
        goto LABEL_80;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x1000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_80;
      }
      v21 = 30;
LABEL_79:
      WPP_SF_d(v20[1].Flink, v21, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, LastError);
LABEL_80:
      ClosePhonebookFile(v28);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x1000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 6u )
      {
        return updated;
      }
      v18 = 35;
      goto LABEL_46;
    }
    PbkAndEntryName = GetPbkAndEntryName(WideCharStr, (__int64)&v27);
    updated = PbkAndEntryName;
    if ( PbkAndEntryName )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x1000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_73;
      }
      v24 = 31;
    }
    else
    {
      if ( DWORD2(v28[0]) || (unsigned int)FIsUserAdminOrNCO() )
        goto LABEL_73;
      PbkAndEntryName = GetLUAPhonebookPath(WideCharStr, (__int64 *)&hMem);
      updated = PbkAndEntryName;
      if ( !PbkAndEntryName )
      {
        updated = RasUpdatePbkIpv6Info(hMem, v30, a4);
        GlobalFree(hMem);
        if ( !updated )
          goto LABEL_73;
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x1000) == 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_73;
        }
        v24 = 33;
        v25 = updated;
        goto LABEL_72;
      }
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x1000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_73;
      }
      v24 = 32;
    }
    v25 = PbkAndEntryName;
LABEL_72:
    WPP_SF_d(v23[1].Flink, v24, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, v25);
LABEL_73:
    if ( RevertToSelf() )
      goto LABEL_80;
    LastError = GetLastError();
    updated = LastError;
    if ( !LastError )
      goto LABEL_80;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x1000) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
    {
      goto LABEL_80;
    }
    v21 = 34;
    goto LABEL_79;
  }
  v9 = 261;
  v10 = lpMultiByteStr;
  while ( *v10 )
  {
    ++v10;
    if ( !--v9 )
      goto LABEL_18;
  }
  if ( *lpMultiByteStr )
    goto LABEL_23;
LABEL_18:
  if ( v8 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v8[1].Blink) & 0x1000) != 0
    && BYTE1(v8[1].Blink) >= 2u )
  {
    WPP_SF_d(v8[1].Flink, 26, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, 621);
  }
  return 621;
}

```

## disassembly

```asm
0x180065484  push    rbp
0x180065486  push    rbx
0x180065487  push    rsi
0x180065488  push    rdi
0x180065489  push    r12
0x18006548b  push    r14
0x18006548d  push    r15
0x18006548f  lea     rbp, [rsp-3B0h]
0x180065497  sub     rsp, 4B0h
0x18006549e  mov     rax, cs:__security_cookie
0x1800654a5  xor     rax, rsp
0x1800654a8  mov     [rbp+3E0h+var_40], rax
0x1800654af  mov     r12, r9
0x1800654b2  mov     r15, r8
0x1800654b5  mov     r14, rdx
0x1800654b8  mov     rsi, rcx
0x1800654bb  mov     eax, 1000h
0x1800654c0  test    rcx, rcx
0x1800654c3  jz      short loc_180065500
0x1800654c5  test    rdx, rdx
0x1800654c8  jz      short loc_180065500
0x1800654ca  mov     rbx, cs:WPP_GLOBAL_Control
0x1800654d1  lea     rdi, WPP_GLOBAL_Control
0x1800654d8  cmp     rbx, rdi
0x1800654db  jz      short loc_18006553D
0x1800654dd  test    [rbx+1Ch], eax
0x1800654e0  jz      short loc_18006553D
0x1800654e2  cmp     byte ptr [rbx+19h], 6
0x1800654e6  jb      short loc_18006553D
0x1800654e8  mov     r9, rcx
0x1800654eb  mov     [rsp+4E0h+var_4B8], r8
0x1800654f0  mov     rcx, [rbx+10h]
0x1800654f4  mov     [rsp+4E0h+var_4C0], rdx
0x1800654f9  call    WPP_SF_ssq
0x1800654fe  jmp     short loc_180065536
0x180065500  mov     rbx, cs:WPP_GLOBAL_Control
0x180065507  lea     rdi, WPP_GLOBAL_Control
0x18006550e  cmp     rbx, rdi
0x180065511  jz      short loc_18006553D
0x180065513  test    [rbx+1Ch], eax
0x180065516  jz      short loc_18006553D
0x180065518  cmp     byte ptr [rbx+19h], 6
0x18006551c  jb      short loc_18006553D
0x18006551e  mov     rcx, [rbx+10h]
0x180065522  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x180065529  mov     edx, 19h
0x18006552e  mov     r9, r15
0x180065531  call    WPP_SF_q
0x180065536  mov     rbx, cs:WPP_GLOBAL_Control
0x18006553d  xorps   xmm0, xmm0
0x180065540  lea     rcx, [rbp+3E0h+var_24C]; void *
0x180065547  xor     eax, eax
0x180065549  xor     edx, edx; Val
0x18006554b  mov     r8d, 204h; Size
0x180065551  mov     [rsp+4E0h+var_470], rax
0x180065556  movups  [rsp+4E0h+var_4A0], xmm0
0x18006555b  mov     [rsp+4E0h+var_4A8], rax
0x180065560  movups  [rsp+4E0h+var_490], xmm0
0x180065565  mov     dword ptr [rbp+3E0h+WideCharStr], eax
0x18006556b  movups  [rsp+4E0h+var_480], xmm0
0x180065570  call    memset_0
0x180065575  xor     edx, edx; Val
0x180065577  mov     dword ptr [rbp+3E0h+var_460], 0
0x18006557e  mov     r8d, 1FEh; Size
0x180065584  lea     rcx, [rbp+3E0h+var_45C]; void *
0x180065588  call    memset_0
0x18006558d  mov     [rsp+4E0h+hMem], 0
0x180065596  test    rsi, rsi
0x180065599  jz      short loc_1800655ED
0x18006559b  mov     ecx, 105h
0x1800655a0  mov     rax, rsi
0x1800655a3  cmp     byte ptr [rax], 0
0x1800655a6  jz      short loc_1800655B3
0x1800655a8  inc     rax
0x1800655ab  sub     rcx, 1
0x1800655af  jnz     short loc_1800655A3
0x1800655b1  jmp     short loc_1800655B8
0x1800655b3  cmp     byte ptr [rsi], 0
0x1800655b6  jnz     short loc_1800655ED
0x1800655b8  mov     esi, 26Dh
0x1800655bd  cmp     rbx, rdi
0x1800655c0  jz      short loc_1800655E9
0x1800655c2  test    dword ptr [rbx+1Ch], 1000h
0x1800655c9  jz      short loc_1800655E9
0x1800655cb  cmp     byte ptr [rbx+19h], 2
0x1800655cf  jb      short loc_1800655E9
0x1800655d1  mov     rcx, [rbx+10h]
0x1800655d5  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x1800655dc  mov     edx, 1Ah
0x1800655e1  mov     r9d, esi
0x1800655e4  call    WPP_SF_d
0x1800655e9  mov     eax, esi
0x1800655eb  jmp     short loc_18006563C
0x1800655ed  test    r14, r14
0x1800655f0  jz      short loc_180065608
0x1800655f2  mov     ecx, 601h
0x1800655f7  mov     rax, r14
0x1800655fa  cmp     byte ptr [rax], 0
0x1800655fd  jz      short loc_18006565D
0x1800655ff  inc     rax
0x180065602  sub     rcx, 1
0x180065606  jnz     short loc_1800655FA
0x180065608  cmp     rbx, rdi
0x18006560b  jz      short loc_180065637
0x18006560d  test    dword ptr [rbx+1Ch], 1000h
0x180065614  jz      short loc_180065637
0x180065616  cmp     byte ptr [rbx+19h], 2
0x18006561a  jb      short loc_180065637
0x18006561c  mov     edx, 1Bh
0x180065621  mov     rcx, [rbx+10h]
0x180065625  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x18006562c  mov     r9d, 57h ; 'W'
0x180065632  call    WPP_SF_d
0x180065637  mov     eax, 57h ; 'W'
0x18006563c  mov     rcx, [rbp+3E0h+var_40]
0x180065643  xor     rcx, rsp; StackCookie
0x180065646  call    __security_check_cookie
0x18006564b  add     rsp, 4B0h
0x180065652  pop     r15
0x180065654  pop     r14
0x180065656  pop     r12
0x180065658  pop     rdi
0x180065659  pop     rsi
0x18006565a  pop     rbx
0x18006565b  pop     rbp
0x18006565c  retn
0x18006565d  cmp     byte ptr [r14], 0
0x180065661  jz      short loc_180065608
0x180065663  test    r12, r12
0x180065666  jnz     short loc_180065683
0x180065668  cmp     rbx, rdi
0x18006566b  jz      short loc_180065637
0x18006566d  test    dword ptr [rbx+1Ch], 1000h
0x180065674  jz      short loc_180065637
0x180065676  cmp     byte ptr [rbx+19h], 2
0x18006567a  jb      short loc_180065637
0x18006567c  lea     edx, [r12+1Ch]
0x180065681  jmp     short loc_180065621
0x180065683  test    rsi, rsi
0x180065686  jz      short loc_18006569D
0x180065688  mov     r8d, 104h
0x18006568e  lea     rcx, [rbp+3E0h+WideCharStr]; lpWideCharStr
0x180065695  mov     rdx, rsi; lpMultiByteStr
0x180065698  call    StrncpyAtoW
0x18006569d  mov     r8d, 101h
0x1800656a3  lea     rcx, [rbp+3E0h+var_460]; lpWideCharStr
0x1800656a7  mov     rdx, r14; lpMultiByteStr
0x1800656aa  call    StrncpyAtoW
0x1800656af  lea     rax, [rbp+3E0h+WideCharStr]
0x1800656b6  neg     rsi
0x1800656b9  lea     rdx, [rbp+3E0h+var_460]
0x1800656bd  sbb     rbx, rbx
0x1800656c0  and     rbx, rax
0x1800656c3  mov     rcx, rbx
0x1800656c6  call    IsExistingEntry
0x1800656cb  test    eax, eax
0x1800656cd  jnz     short loc_18006570C
0x1800656cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800656d6  mov     ebx, 26Fh
0x1800656db  cmp     rcx, rdi
0x1800656de  jz      short loc_180065705
0x1800656e0  test    dword ptr [rcx+1Ch], 1000h
0x1800656e7  jz      short loc_180065705
0x1800656e9  cmp     byte ptr [rcx+19h], 2
0x1800656ed  jb      short loc_180065705
0x1800656ef  lea     edx, [rax+1Dh]
0x1800656f2  mov     rcx, [rcx+10h]
0x1800656f6  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x1800656fd  mov     r9d, ebx
0x180065700  call    WPP_SF_d
0x180065705  mov     eax, ebx
0x180065707  jmp     loc_18006563C
0x18006570c  mov     r8, r12
0x18006570f  lea     rdx, [rbp+3E0h+var_460]
0x180065713  mov     rcx, rbx
0x180065716  call    RasUpdatePbkIpv6Info
0x18006571b  mov     rcx, r15; hToken
0x18006571e  call    cs:__imp_ImpersonateLoggedOnUser
0x180065724  test    eax, eax
0x180065726  jnz     short loc_180065769
0x180065728  call    cs:__imp_GetLastError
0x18006572e  mov     ebx, eax
0x180065730  test    eax, eax
0x180065732  jz      loc_1800658B4
0x180065738  mov     rcx, cs:WPP_GLOBAL_Control
0x18006573f  cmp     rcx, rdi
0x180065742  jz      loc_1800658B4
0x180065748  test    dword ptr [rcx+1Ch], 1000h
0x18006574f  jz      loc_1800658B4
0x180065755  cmp     byte ptr [rcx+19h], 2
0x180065759  jb      loc_1800658B4
0x18006575f  mov     edx, 1Eh
0x180065764  jmp     loc_1800658A1
0x180065769  lea     rax, [rsp+4E0h+var_4A8]
0x18006576e  xor     r8d, r8d
0x180065771  lea     r9, [rsp+4E0h+var_4A0]
0x180065776  mov     [rsp+4E0h+var_4C0], rax
0x18006577b  lea     rdx, [rbp+3E0h+var_460]
0x18006577f  lea     rcx, [rbp+3E0h+WideCharStr]
0x180065786  call    GetPbkAndEntryName
0x18006578b  mov     ebx, eax
0x18006578d  test    eax, eax
0x18006578f  jz      short loc_1800657C5
0x180065791  mov     rcx, cs:WPP_GLOBAL_Control
0x180065798  cmp     rcx, rdi
0x18006579b  jz      loc_18006586B
0x1800657a1  test    dword ptr [rcx+1Ch], 1000h
0x1800657a8  jz      loc_18006586B
0x1800657ae  cmp     byte ptr [rcx+19h], 2
0x1800657b2  jb      loc_18006586B
0x1800657b8  mov     edx, 1Fh
0x1800657bd  mov     r9d, eax
0x1800657c0  jmp     loc_18006585B
0x1800657c5  cmp     dword ptr [rsp+4E0h+var_4A0+8], 0
0x1800657ca  jnz     loc_18006586B
0x1800657d0  call    FIsUserAdminOrNCO
0x1800657d5  test    eax, eax
0x1800657d7  jnz     loc_18006586B
0x1800657dd  lea     rdx, [rsp+4E0h+hMem]
0x1800657e2  lea     rcx, [rbp+3E0h+WideCharStr]; lpFileName
0x1800657e9  call    GetLUAPhonebookPath
0x1800657ee  mov     ebx, eax
0x1800657f0  test    eax, eax
0x1800657f2  jz      short loc_180065816
0x1800657f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800657fb  cmp     rcx, rdi
0x1800657fe  jz      short loc_18006586B
0x180065800  test    dword ptr [rcx+1Ch], 1000h
0x180065807  jz      short loc_18006586B
0x180065809  cmp     byte ptr [rcx+19h], 2
0x18006580d  jb      short loc_18006586B
0x18006580f  mov     edx, 20h ; ' '
0x180065814  jmp     short loc_1800657BD
0x180065816  mov     rcx, [rsp+4E0h+hMem]
0x18006581b  lea     rdx, [rbp+3E0h+var_460]
0x18006581f  mov     r8, r12
0x180065822  call    RasUpdatePbkIpv6Info
0x180065827  mov     rcx, [rsp+4E0h+hMem]; hMem
0x18006582c  mov     ebx, eax
0x18006582e  call    cs:__imp_GlobalFree
0x180065834  test    ebx, ebx
0x180065836  jz      short loc_18006586B
0x180065838  mov     rcx, cs:WPP_GLOBAL_Control
0x18006583f  cmp     rcx, rdi
0x180065842  jz      short loc_18006586B
0x180065844  test    dword ptr [rcx+1Ch], 1000h
0x18006584b  jz      short loc_18006586B
0x18006584d  cmp     byte ptr [rcx+19h], 2
0x180065851  jb      short loc_18006586B
0x180065853  mov     edx, 21h ; '!'
0x180065858  mov     r9d, ebx
0x18006585b  mov     rcx, [rcx+10h]
0x18006585f  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x180065866  call    WPP_SF_d
0x18006586b  call    cs:__imp_RevertToSelf
0x180065871  test    eax, eax
0x180065873  jnz     short loc_1800658B4
0x180065875  call    cs:__imp_GetLastError
0x18006587b  mov     ebx, eax
0x18006587d  test    eax, eax
0x18006587f  jz      short loc_1800658B4
0x180065881  mov     rcx, cs:WPP_GLOBAL_Control
0x180065888  cmp     rcx, rdi
0x18006588b  jz      short loc_1800658B4
0x18006588d  test    dword ptr [rcx+1Ch], 1000h
0x180065894  jz      short loc_1800658B4
0x180065896  cmp     byte ptr [rcx+19h], 2
0x18006589a  jb      short loc_1800658B4
0x18006589c  mov     edx, 22h ; '"'
0x1800658a1  mov     rcx, [rcx+10h]
0x1800658a5  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x1800658ac  mov     r9d, eax
0x1800658af  call    WPP_SF_d
0x1800658b4  lea     rcx, [rsp+4E0h+var_4A0]
0x1800658b9  call    ClosePhonebookFile
0x1800658be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800658c5  cmp     rcx, rdi
0x1800658c8  jz      loc_180065705
0x1800658ce  test    dword ptr [rcx+1Ch], 1000h
0x1800658d5  jz      loc_180065705
0x1800658db  cmp     byte ptr [rcx+19h], 6
0x1800658df  jb      loc_180065705
0x1800658e5  mov     edx, 23h ; '#'
0x1800658ea  jmp     loc_1800656F2
```
