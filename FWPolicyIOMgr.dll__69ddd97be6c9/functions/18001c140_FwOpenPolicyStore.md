# FwOpenPolicyStore

- ea: `0x18001c140`
- end: `0x18001c765`
- name: `FwOpenPolicyStore`
- size: `1573`
- prototype: `__int64 __fastcall(int, int, HKEY, __int64 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x18002bc34`
- `0x18002bf6c`

## callees

- `0x180003248`
- `0x180003b94`
- `0x1800042c4`
- `0x180014280`
- `0x180014570`
- `0x180016930`
- `0x180016e14`
- `0x18001c140`
- `0x18001e9ac`
- `0x18001ed7c`
- `0x18001f650`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18001c4b8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18001c4b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c2e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c2e0`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001c1cc`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001c1cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c736`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c736`
- `fwbase!FwFree` at `0x18001c73f`
- `fwbase!FwFree` at `0x18001c73f`
- `fwbase!FwAlloc` at `0x18001c212`
- `fwbase!FwAlloc` at `0x18001c212`
- `fwbase!FwRegOpenKey` at `0x18001c50a`
- `fwbase!FwRegOpenKey` at `0x18001c5c1`
- `fwbase!FwRegOpenKey` at `0x18001c50a`
- `fwbase!FwRegOpenKey` at `0x18001c5c1`
- `fwbase!FwLicensingIsXbox` at `0x18001c386`
- `fwbase!FwLicensingIsXbox` at `0x18001c490`
- `fwbase!FwLicensingIsXbox` at `0x18001c386`
- `fwbase!FwLicensingIsXbox` at `0x18001c490`
- `fwbase!FwRegCreateKey` at `0x18001c348`
- `fwbase!FwRegCreateKey` at `0x18001c409`
- `fwbase!FwRegCreateKey` at `0x18001c562`
- `fwbase!FwRegCreateKey` at `0x18001c616`
- `fwbase!FwRegCreateKey` at `0x18001c348`
- `fwbase!FwRegCreateKey` at `0x18001c409`
- `fwbase!FwRegCreateKey` at `0x18001c562`
- `fwbase!FwRegCreateKey` at `0x18001c616`

## string_xrefs

- `0x18001c4aa`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy`
- `0x18001c3b8`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy\FirewallRules`
- `0x18001c64d`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy\FirewallRules`
- `0x18001c3a1`: `\Registry\Machine\SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy\RestrictedServices\AppIso\FirewallRules`
- `0x18001c6d9`: `FwOpenPolicyStore`
- `0x18001c4b1`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy`

## pseudocode

```c
__int64 __fastcall FwOpenPolicyStore(int a1, int a2, HKEY a3, __int64 *a4)
{
  __int64 v5; // r14
  __int64 v6; // rbp
  __int64 v7; // rdi
  unsigned int v8; // ebx
  LPCOLESTR v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  _OWORD *v12; // rdx
  struct _tag_WF_POLICY_STORE near **v13; // rax
  __int64 v14; // rcx
  __int128 v15; // xmm1
  __int64 v16; // r15
  signed int LastError; // eax
  HKEY v18; // rsi
  int v19; // eax
  const unsigned __int16 *v20; // rsi
  struct _tag_WF_POLICY_STORE_HIVE near **v21; // r8
  const wchar_t *v22; // r10
  int Key; // eax
  __int64 v24; // rdx
  __int64 v25; // rdx
  HKEY v26; // rcx
  int Parameter; // [rsp+38h] [rbp-60h] BYREF

  v5 = a2;
  v6 = a1;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 202, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
  v7 = 0;
  *a4 = 0;
  if ( (unsigned int)(v5 - 1) > 1 )
  {
    v8 = -2147024809;
    goto LABEL_83;
  }
  Parameter = 0;
  InitOnceExecuteOnce(&g_InitOnce, InitHandleFunction, &Parameter, 0);
  v8 = Parameter;
  if ( Parameter < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control )
    {
      if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v10 = 203;
LABEL_9:
        v11 = v8;
LABEL_10:
        WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, v11);
LABEL_83:
        v9 = WPP_GLOBAL_Control;
      }
LABEL_84:
      if ( v9 != (LPCOLESTR)&WPP_GLOBAL_Control && (v9[14] & 1) != 0 )
        WPP_SF_dd(*((_QWORD *)v9 + 2), 215, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, (unsigned int)v6, v8);
      goto LABEL_87;
    }
    goto LABEL_87;
  }
  v7 = FwAlloc(264);
  if ( !v7 )
  {
    v8 = -2147024882;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
      return v8;
    if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_84;
    v10 = 204;
    goto LABEL_9;
  }
  if ( (unsigned int)v6 >= 0xD )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v12 = (_OWORD *)v7;
  v13 = &PolicyStore + 33 * v6;
  v14 = 2;
  do
  {
    *v12 = *(_OWORD *)v13;
    v12[1] = *((_OWORD *)v13 + 1);
    v12[2] = *((_OWORD *)v13 + 2);
    v12[3] = *((_OWORD *)v13 + 3);
    v12[4] = *((_OWORD *)v13 + 4);
    v12[5] = *((_OWORD *)v13 + 5);
    v12[6] = *((_OWORD *)v13 + 6);
    v15 = *((_OWORD *)v13 + 7);
    v13 += 16;
    v12[7] = v15;
    v12 += 8;
    --v14;
  }
  while ( v14 );
  *(_QWORD *)v12 = *v13;
  *(_DWORD *)(v7 + 12) = v5;
  if ( (_DWORD)v6 == 1 )
  {
    v16 = FWGPLock(0, v12, 128);
    if ( !v16 )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      {
LABEL_80:
        if ( (v8 & 0x80000000) == 0 )
          return v8;
        goto LABEL_84;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 205, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, v8);
LABEL_79:
      v9 = WPP_GLOBAL_Control;
      goto LABEL_80;
    }
LABEL_31:
    if ( (unsigned int)FwLicensingIsXbox() )
    {
      if ( (_DWORD)v6 == 2 )
      {
        v20 = L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Services\\SharedAccess\\Parameters\\FirewallPolicy\\FirewallRules";
        v21 = &g_FwXboxLocalHives;
        v22 = L"OSDATA\\FwStore\\Local";
LABEL_36:
        *(_QWORD *)(v7 + 16) = v22;
        *(_DWORD *)(v7 + 56) = 2;
        *(_QWORD *)(v7 + 64) = v21;
        Key = FwRegCreateKey(-2147483646, v22, *((unsigned int *)&FWPolicyAcessRightMap + v5), v7 + 40);
        v8 = Key;
        if ( Key < 0 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_77;
          v24 = 207;
          goto LABEL_40;
        }
        Key = FwCreatePolicyStoreSymlink((struct _tag_WF_POLICY_STORE *)v7, v20);
        v8 = Key;
        if ( Key < 0 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_77;
          v24 = 208;
          goto LABEL_40;
        }
        goto LABEL_74;
      }
      if ( (_DWORD)v6 == 10 )
      {
        v20 = L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Services\\SharedAccess\\Parameters\\FirewallPolicy\\Restri"
               "ctedServices\\AppIso\\FirewallRules";
        v21 = &g_FwXboxAppIsoHives;
        v22 = L"OSDATA\\FwStore\\AppIso";
        goto LABEL_36;
      }
    }
    if ( !(unsigned int)FwLicensingIsXbox()
      && (_DWORD)v6 == 2
      && (unsigned int)_o__wcsnicmp(
                         g_FwPersistentStoreRootKey,
                         L"SYSTEM\\CurrentControlSet\\Services\\SharedAccess\\Parameters\\FirewallPolicy",
                         73) )
    {
      v25 = *(_QWORD *)(v7 + 16);
      *(_QWORD *)(v7 + 64) = &g_FwWCOSLocalHives;
      Parameter = 0;
      *(_DWORD *)(v7 + 56) = 2;
      Key = FwRegOpenKey(-2147483646, v25, *((unsigned int *)&FWPolicyAcessRightMap + v5), v7 + 40, &Parameter);
      v8 = Key;
      if ( Key < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_77;
        v24 = 209;
        goto LABEL_40;
      }
      if ( !Parameter )
      {
        Key = FwRegCreateKey(-2147483646, *(_QWORD *)(v7 + 16), *((unsigned int *)&FWPolicyAcessRightMap + v5), v7 + 40);
        v8 = Key;
        if ( Key < 0 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_77;
          v24 = 210;
          goto LABEL_40;
        }
      }
      Key = FwRegOpenKey(
              -2147483646,
              *(_QWORD *)(v7 + 32),
              *((unsigned int *)&FWPolicyAcessRightMap + *(int *)(v7 + 12)),
              v7 + 48,
              &Parameter);
      v8 = Key;
      if ( Key < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_77;
        v24 = 211;
        goto LABEL_40;
      }
      if ( !Parameter )
      {
        Key = FwRegCreateKey(
                -2147483646,
                *(_QWORD *)(v7 + 32),
                *((unsigned int *)&FWPolicyAcessRightMap + *(int *)(v7 + 12)),
                v7 + 48);
        v8 = Key;
        if ( Key < 0 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_77;
          v24 = 212;
          goto LABEL_40;
        }
      }
      Key = FwCreatePolicyStoreSymlink(
              (struct _tag_WF_POLICY_STORE *)v7,
              L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Services\\SharedAccess\\Parameters\\FirewallPolicy\\FirewallRules");
      v8 = Key;
      if ( Key < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_77;
        v24 = 213;
        goto LABEL_40;
      }
    }
    else
    {
      Key = FwPolicyStoreFillOfInternalKeys((struct _tag_WF_POLICY_STORE *)v7);
      v8 = Key;
      if ( Key < 0 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_77;
        v24 = 214;
LABEL_40:
        WPP_SF_d(*((_QWORD *)v9 + 2), v24, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, (unsigned int)Key);
LABEL_76:
        v9 = WPP_GLOBAL_Control;
LABEL_77:
        if ( !v16 )
          goto LABEL_80;
        FWGPUnlockEx(v16, "FwOpenPolicyStore");
        goto LABEL_79;
      }
    }
LABEL_74:
    v18 = a3;
    goto LABEL_75;
  }
  v16 = 0;
  if ( (_DWORD)v6 != 6 )
    goto LABEL_31;
  v18 = a3;
  v19 = FwRegCreateKey(a3, *(_QWORD *)(v7 + 16), *((unsigned int *)&FWPolicyAcessRightMap + v5), v7 + 40);
  v8 = v19;
  if ( v19 >= 0 )
  {
LABEL_75:
    *a4 = v7;
    CachePolicyVersion((struct _tag_WF_POLICY_STORE *)v7, v18);
    goto LABEL_76;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control )
  {
    if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v10 = 206;
      v11 = (unsigned int)v19;
      goto LABEL_10;
    }
    goto LABEL_84;
  }
LABEL_87:
  if ( v7 )
  {
    v26 = *(HKEY *)(v7 + 40);
    if ( v26 )
      RegCloseKey(v26);
    FwFree(v7);
  }
  return v8;
}

```

## disassembly

```asm
0x18001c140  push    rbx
0x18001c142  push    rbp
0x18001c143  push    rsi
0x18001c144  push    rdi
0x18001c145  push    r12
0x18001c147  push    r13
0x18001c149  push    r14
0x18001c14b  push    r15
0x18001c14d  sub     rsp, 58h
0x18001c151  mov     rax, cs:__security_cookie
0x18001c158  xor     rax, rsp
0x18001c15b  mov     [rsp+98h+var_58], rax
0x18001c160  mov     r13, r9
0x18001c163  mov     [rsp+98h+var_68], r8
0x18001c168  movsxd  r14, edx
0x18001c16b  movsxd  rbp, ecx
0x18001c16e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c175  lea     r12, WPP_GLOBAL_Control
0x18001c17c  lea     rsi, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18001c183  cmp     rcx, r12
0x18001c186  jz      short loc_18001C19F
0x18001c188  test    byte ptr [rcx+1Ch], 8
0x18001c18c  jz      short loc_18001C19F
0x18001c18e  mov     rcx, [rcx+10h]
0x18001c192  mov     edx, 0CAh
0x18001c197  mov     r8, rsi
0x18001c19a  call    WPP_SF_
0x18001c19f  xor     edi, edi
0x18001c1a1  lea     eax, [r14-1]
0x18001c1a5  mov     [r13+0], rdi
0x18001c1a9  cmp     eax, 1
0x18001c1ac  ja      loc_18001C6F5
0x18001c1b2  xor     r9d, r9d; Context
0x18001c1b5  mov     [rsp+98h+Parameter], edi
0x18001c1b9  lea     r8, [rsp+98h+Parameter]; Parameter
0x18001c1be  lea     rdx, ?InitHandleFunction@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18001c1c5  lea     rcx, ?g_InitOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x18001c1cc  call    cs:__imp_InitOnceExecuteOnce
0x18001c1d2  mov     ebx, [rsp+98h+Parameter]
0x18001c1d6  test    ebx, ebx
0x18001c1d8  jns     short loc_18001C20D
0x18001c1da  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c1e1  cmp     rcx, r12
0x18001c1e4  jz      loc_18001C728
0x18001c1ea  test    byte ptr [rcx+1Ch], 1
0x18001c1ee  jz      loc_18001C701
0x18001c1f4  mov     edx, 0CBh
0x18001c1f9  mov     r9d, ebx
0x18001c1fc  mov     r8, rsi
0x18001c1ff  mov     rcx, [rcx+10h]
0x18001c203  call    WPP_SF_d
0x18001c208  jmp     loc_18001C6FA
0x18001c20d  mov     ecx, 108h
0x18001c212  call    cs:__imp_FwAlloc
0x18001c218  mov     rdi, rax
0x18001c21b  test    rax, rax
0x18001c21e  jnz     short loc_18001C246
0x18001c220  mov     ebx, 8007000Eh
0x18001c225  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c22c  cmp     rcx, r12
0x18001c22f  jz      loc_18001C745
0x18001c235  test    byte ptr [rcx+1Ch], 1
0x18001c239  jz      loc_18001C701
0x18001c23f  mov     edx, 0CCh
0x18001c244  jmp     short loc_18001C1F9
0x18001c246  cmp     ebp, 0Dh
0x18001c249  jb      short loc_18001C250
0x18001c24b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001c250  imul    rcx, rbp, 108h
0x18001c257  mov     ebx, 2
0x18001c25c  lea     r10, __ImageBase
0x18001c263  lea     rax, rva ?PolicyStore@@3PAU_tag_WF_POLICY_STORE@@A[r10]; _tag_WF_POLICY_STORE near * PolicyStore ...
0x18001c26a  mov     rdx, rdi
0x18001c26d  add     rax, rcx
0x18001c270  mov     ecx, ebx
0x18001c272  lea     r8d, [rbx+7Eh]
0x18001c276  movups  xmm0, xmmword ptr [rax]
0x18001c279  movups  xmmword ptr [rdx], xmm0
0x18001c27c  movups  xmm1, xmmword ptr [rax+10h]
0x18001c280  movups  xmmword ptr [rdx+10h], xmm1
0x18001c284  movups  xmm0, xmmword ptr [rax+20h]
0x18001c288  movups  xmmword ptr [rdx+20h], xmm0
0x18001c28c  movups  xmm1, xmmword ptr [rax+30h]
0x18001c290  movups  xmmword ptr [rdx+30h], xmm1
0x18001c294  movups  xmm0, xmmword ptr [rax+40h]
0x18001c298  movups  xmmword ptr [rdx+40h], xmm0
0x18001c29c  movups  xmm1, xmmword ptr [rax+50h]
0x18001c2a0  movups  xmmword ptr [rdx+50h], xmm1
0x18001c2a4  movups  xmm0, xmmword ptr [rax+60h]
0x18001c2a8  movups  xmmword ptr [rdx+60h], xmm0
0x18001c2ac  movups  xmm1, xmmword ptr [rax+70h]
0x18001c2b0  add     rax, r8
0x18001c2b3  movups  xmmword ptr [rdx+70h], xmm1
0x18001c2b7  add     rdx, r8
0x18001c2ba  sub     rcx, 1
0x18001c2be  jnz     short loc_18001C276
0x18001c2c0  mov     rax, [rax]
0x18001c2c3  mov     [rdx], rax
0x18001c2c6  mov     [rdi+0Ch], r14d
0x18001c2ca  cmp     ebp, 1
0x18001c2cd  jnz     short loc_18001C328
0x18001c2cf  call    FWGPLock
0x18001c2d4  mov     r15, rax
0x18001c2d7  test    rax, rax
0x18001c2da  jnz     loc_18001C386
0x18001c2e0  call    cs:__imp_GetLastError
0x18001c2e6  mov     ebx, eax
0x18001c2e8  test    eax, eax
0x18001c2ea  jle     short loc_18001C2F5
0x18001c2ec  movzx   ebx, ax
0x18001c2ef  or      ebx, 80070000h
0x18001c2f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c2fc  cmp     rcx, r12
0x18001c2ff  jz      loc_18001C6EF
0x18001c305  test    byte ptr [rcx+1Ch], 1
0x18001c309  jz      loc_18001C6EF
0x18001c30f  mov     rcx, [rcx+10h]
0x18001c313  mov     edx, 0CDh
0x18001c318  mov     r9d, ebx
0x18001c31b  mov     r8, rsi
0x18001c31e  call    WPP_SF_d
0x18001c323  jmp     loc_18001C6E8
0x18001c328  xor     r15d, r15d
0x18001c32b  cmp     ebp, 6
0x18001c32e  jnz     short loc_18001C386
0x18001c330  mov     rsi, [rsp+98h+var_68]
0x18001c335  lea     r9, [rdi+28h]
0x18001c339  mov     r8d, ds:rva ?FWPolicyAcessRightMap@@3PAKA[r10+r14*4]; ulong near * FWPolicyAcessRightMap ...
0x18001c341  mov     rcx, rsi
0x18001c344  mov     rdx, [rdi+10h]
0x18001c348  call    cs:__imp_FwRegCreateKey
0x18001c34e  mov     ebx, eax
0x18001c350  test    eax, eax
0x18001c352  jns     loc_18001C6BE
0x18001c358  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c35f  cmp     rcx, r12
0x18001c362  jz      loc_18001C728
0x18001c368  test    byte ptr [rcx+1Ch], 1
0x18001c36c  jz      loc_18001C701
0x18001c372  mov     edx, 0CEh
0x18001c377  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18001c37e  mov     r9d, eax
0x18001c381  jmp     loc_18001C1FF
0x18001c386  call    cs:__imp_FwLicensingIsXbox
0x18001c38c  test    eax, eax
0x18001c38e  jz      loc_18001C490
0x18001c394  cmp     ebp, ebx
0x18001c396  jz      short loc_18001C3B8
0x18001c398  cmp     ebp, 0Ah
0x18001c39b  jnz     loc_18001C490
0x18001c3a1  lea     rsi, aRegistryMachin; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x18001c3a8  lea     r8, ?g_FwXboxAppIsoHives@@3PAU_tag_WF_POLICY_STORE_HIVE@@A; _tag_WF_POLICY_STORE_HIVE near * g_FwXboxAppIsoHives
0x18001c3af  lea     r10, aOsdataFwstoreA; "OSDATA\\FwStore\\AppIso"
0x18001c3b6  jmp     short loc_18001C3CD
0x18001c3b8  lea     rsi, aRegistryMachin_0; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x18001c3bf  lea     r8, ?g_FwXboxLocalHives@@3PAU_tag_WF_POLICY_STORE_HIVE@@A; _tag_WF_POLICY_STORE_HIVE near * g_FwXboxLocalHives
0x18001c3c6  lea     r10, aOsdataFwstoreL; "OSDATA\\FwStore\\Local"
0x18001c3cd  mov     edx, 10h
0x18001c3d2  mov     r9, rdi
0x18001c3d5  mov     r11, rdi
0x18001c3d8  lea     r9, [rdi+28h]
0x18001c3dc  mov     r12, rdi
0x18001c3df  mov     [rdi+rdx], r10
0x18001c3e3  lea     ecx, [rdx+28h]
0x18001c3e6  lea     eax, [rdx+30h]
0x18001c3e9  mov     [rdi+rcx], ebx
0x18001c3ec  mov     [rdi+rax], r8
0x18001c3f0  mov     rdx, r10
0x18001c3f3  lea     rax, __ImageBase
0x18001c3fa  mov     rcx, 0FFFFFFFF80000002h
0x18001c401  mov     r8d, ds:rva ?FWPolicyAcessRightMap@@3PAKA[rax+r14*4]; ulong near * FWPolicyAcessRightMap ...
0x18001c409  call    cs:__imp_FwRegCreateKey
0x18001c40f  mov     ebx, eax
0x18001c411  test    eax, eax
0x18001c413  jns     short loc_18001C453
0x18001c415  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c41c  lea     r12, WPP_GLOBAL_Control
0x18001c423  cmp     rcx, r12
0x18001c426  jz      loc_18001C6D4
0x18001c42c  test    byte ptr [rcx+1Ch], 1
0x18001c430  jz      loc_18001C6D4
0x18001c436  mov     edx, 0CFh
0x18001c43b  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18001c442  mov     rcx, [rcx+10h]
0x18001c446  mov     r9d, eax
0x18001c449  call    WPP_SF_d
0x18001c44e  jmp     loc_18001C6CD
0x18001c453  mov     rdx, rsi; unsigned __int16 *
0x18001c456  mov     rcx, rdi; struct _tag_WF_POLICY_STORE *
0x18001c459  call    ?FwCreatePolicyStoreSymlink@@YAJPEAU_tag_WF_POLICY_STORE@@PEBG@Z; FwCreatePolicyStoreSymlink(_tag_WF_POLICY_STORE *,ushort const *)
0x18001c45e  mov     ebx, eax
0x18001c460  test    eax, eax
0x18001c462  jns     loc_18001C6B2
0x18001c468  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c46f  lea     r12, WPP_GLOBAL_Control
0x18001c476  cmp     rcx, r12
0x18001c479  jz      loc_18001C6D4
0x18001c47f  test    byte ptr [rcx+1Ch], 1
0x18001c483  jz      loc_18001C6D4
0x18001c489  mov     edx, 0D0h
0x18001c48e  jmp     short loc_18001C43B
0x18001c490  call    cs:__imp_FwLicensingIsXbox
0x18001c496  test    eax, eax
0x18001c498  jnz     loc_18001C685
0x18001c49e  cmp     ebp, ebx
0x18001c4a0  jnz     loc_18001C685
0x18001c4a6  lea     r8d, [rax+49h]
0x18001c4aa  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x18001c4b1  lea     rcx, ?g_FwPersistentStoreRootKey@@3PAGA; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x18001c4b8  call    cs:__imp__o__wcsnicmp
0x18001c4be  test    eax, eax
0x18001c4c0  jz      loc_18001C685
0x18001c4c6  mov     rdx, [rdi+10h]
0x18001c4ca  lea     rax, ?g_FwWCOSLocalHives@@3PAU_tag_WF_POLICY_STORE_HIVE@@A; _tag_WF_POLICY_STORE_HIVE near * g_FwWCOSLocalHives
0x18001c4d1  mov     [rdi+40h], rax
0x18001c4d5  lea     r9, [rdi+28h]
0x18001c4d9  lea     rax, [rsp+98h+Parameter]
0x18001c4de  mov     [rsp+98h+Parameter], 0
0x18001c4e6  mov     [rsp+98h+var_78], rax
0x18001c4eb  mov     r12, r14
0x18001c4ee  lea     rax, __ImageBase
0x18001c4f5  mov     [rdi+38h], ebx
0x18001c4f8  mov     r8d, ds:rva ?FWPolicyAcessRightMap@@3PAKA[rax+r14*4]; ulong near * FWPolicyAcessRightMap ...
0x18001c500  mov     r14, 0FFFFFFFF80000002h
0x18001c507  mov     rcx, r14
0x18001c50a  call    cs:__imp_FwRegOpenKey
0x18001c510  mov     ebx, eax
0x18001c512  test    eax, eax
0x18001c514  jns     short loc_18001C541
0x18001c516  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c51d  lea     r12, WPP_GLOBAL_Control
0x18001c524  cmp     rcx, r12
0x18001c527  jz      loc_18001C6D4
0x18001c52d  test    byte ptr [rcx+1Ch], 1
0x18001c531  jz      loc_18001C6D4
0x18001c537  mov     edx, 0D1h
0x18001c53c  jmp     loc_18001C43B
0x18001c541  cmp     [rsp+98h+Parameter], 0
0x18001c546  jnz     short loc_18001C599
0x18001c548  mov     rdx, [rdi+10h]
0x18001c54c  lea     rax, __ImageBase
0x18001c553  mov     r8d, ds:rva ?FWPolicyAcessRightMap@@3PAKA[rax+r12*4]; ulong near * FWPolicyAcessRightMap ...
0x18001c55b  lea     r9, [rdi+28h]
0x18001c55f  mov     rcx, r14
0x18001c562  call    cs:__imp_FwRegCreateKey
0x18001c568  mov     ebx, eax
0x18001c56a  test    eax, eax
0x18001c56c  jns     short loc_18001C599
0x18001c56e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c575  lea     r12, WPP_GLOBAL_Control
0x18001c57c  cmp     rcx, r12
0x18001c57f  jz      loc_18001C6D4
0x18001c585  test    byte ptr [rcx+1Ch], 1
0x18001c589  jz      loc_18001C6D4
0x18001c58f  mov     edx, 0D2h
0x18001c594  jmp     loc_18001C43B
0x18001c599  movsxd  r8, dword ptr [rdi+0Ch]
0x18001c59d  lea     rax, [rsp+98h+Parameter]
0x18001c5a2  mov     rdx, [rdi+20h]
0x18001c5a6  lea     r12, __ImageBase
0x18001c5ad  lea     r9, [rdi+30h]
0x18001c5b1  mov     [rsp+98h+var_78], rax
0x18001c5b6  mov     rcx, r14
0x18001c5b9  mov     r8d, ds:rva ?FWPolicyAcessRightMap@@3PAKA[r12+r8*4]; ulong near * FWPolicyAcessRightMap ...
0x18001c5c1  call    cs:__imp_FwRegOpenKey
0x18001c5c7  mov     ebx, eax
0x18001c5c9  test    eax, eax
0x18001c5cb  jns     short loc_18001C5F8
0x18001c5cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c5d4  lea     r12, WPP_GLOBAL_Control
0x18001c5db  cmp     rcx, r12
0x18001c5de  jz      loc_18001C6D4
0x18001c5e4  test    byte ptr [rcx+1Ch], 1
0x18001c5e8  jz      loc_18001C6D4
0x18001c5ee  mov     edx, 0D3h
0x18001c5f3  jmp     loc_18001C43B
0x18001c5f8  cmp     [rsp+98h+Parameter], 0
0x18001c5fd  jnz     short loc_18001C64D
0x18001c5ff  movsxd  r8, dword ptr [rdi+0Ch]
0x18001c603  lea     r9, [rdi+30h]
0x18001c607  mov     rdx, [rdi+20h]
0x18001c60b  mov     rcx, r14
0x18001c60e  mov     r8d, ds:rva ?FWPolicyAcessRightMap@@3PAKA[r12+r8*4]; ulong near * FWPolicyAcessRightMap ...
0x18001c616  call    cs:__imp_FwRegCreateKey
0x18001c61c  mov     ebx, eax
0x18001c61e  test    eax, eax
0x18001c620  jns     short loc_18001C64D
0x18001c622  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c629  lea     r12, WPP_GLOBAL_Control
0x18001c630  cmp     rcx, r12
0x18001c633  jz      loc_18001C6D4
0x18001c639  test    byte ptr [rcx+1Ch], 1
0x18001c63d  jz      loc_18001C6D4
0x18001c643  mov     edx, 0D4h
0x18001c648  jmp     loc_18001C43B
0x18001c64d  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x18001c654  mov     rcx, rdi; struct _tag_WF_POLICY_STORE *
0x18001c657  call    ?FwCreatePolicyStoreSymlink@@YAJPEAU_tag_WF_POLICY_STORE@@PEBG@Z; FwCreatePolicyStoreSymlink(_tag_WF_POLICY_STORE *,ushort const *)
0x18001c65c  mov     ebx, eax
0x18001c65e  test    eax, eax
  ... truncated ...
```
