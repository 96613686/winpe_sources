# FwGetGlobalConfig

- ea: `0x1800032b0`
- end: `0x18000367a`
- name: `FwGetGlobalConfig`
- size: `970`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x180003248`

## callees

- `0x1800032b0`
- `0x180003680`
- `0x180003b94`
- `0x1800042c4`
- `0x180004958`
- `0x180014280`
- `0x180014570`
- `0x18001f650`
- `0x18003b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800034c0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800034c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003534`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003534`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800033e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800033e1`
- `fwbase!FwLicensingIsXbox` at `0x180003499`
- `fwbase!FwLicensingIsXbox` at `0x180003499`

## string_xrefs

- `0x1800034b2`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy`
- `0x180003666`: `FwGetGlobalConfig`
- `0x1800034b9`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Parameters\FirewallPolicy`

## pseudocode

```c
__int64 __fastcall FwGetGlobalConfig(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, __int64 a5, _DWORD *a6)
{
  unsigned int v8; // edi
  LPCOLESTR v9; // rcx
  __int64 v10; // rsi
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r9
  __int64 v17; // r9
  __int64 v18; // rdx
  signed int LastError; // eax
  __int64 v20; // [rsp+40h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-18h] BYREF

  v8 = a2;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 141, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  hKey = 0;
  v10 = 0;
  v20 = 0;
  if ( v8 - 1 > 0xB || a4 - 1 > 0x11 )
  {
    v17 = 2147942487LL;
    v12 = -2147024809;
    if ( v9 == (LPCOLESTR)&WPP_GLOBAL_Control )
      return v12;
    if ( (v9[14] & 1) == 0 )
      goto LABEL_25;
    v18 = 142;
    goto LABEL_21;
  }
  if ( v8 == 6 && !a3 )
  {
    v17 = 2147942487LL;
    v12 = -2147024809;
    if ( v9 == (LPCOLESTR)&WPP_GLOBAL_Control )
      return v12;
    if ( (v9[14] & 1) == 0 )
      goto LABEL_25;
    v18 = 143;
    goto LABEL_21;
  }
  if ( !a5 && *a6 )
  {
    v17 = 2147942487LL;
    v12 = -2147024809;
    if ( v9 == (LPCOLESTR)&WPP_GLOBAL_Control )
      return v12;
    if ( (v9[14] & 1) == 0 )
      goto LABEL_25;
    v18 = 144;
    goto LABEL_21;
  }
  if ( v8 != 1 || (v10 = FWGPLock(v9, a2, a3)) != 0 )
  {
    v11 = ProcessGlobalConfigParams(v8, a3, a4, 1u, 0, &hKey, (__int64)&v20, 0);
    v12 = v11;
    if ( v11 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
        goto LABEL_13;
      if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_25;
      v18 = 146;
    }
    else
    {
      v12 = (*(__int64 (__fastcall **)(HKEY, _QWORD, __int64, _DWORD *))(v20 + 24))(hKey, *(_QWORD *)(v20 + 16), a5, a6);
      if ( v12 != -2147024894 )
      {
LABEL_11:
        v9 = WPP_GLOBAL_Control;
        goto LABEL_12;
      }
      if ( (unsigned int)FwLicensingIsXbox(v14, v13, a3, v15)
        || !(unsigned int)_o__wcsnicmp(
                            g_FwPersistentStoreRootKey,
                            L"SYSTEM\\CurrentControlSet\\Services\\SharedAccess\\Parameters\\FirewallPolicy",
                            73) )
      {
        goto LABEL_22;
      }
      v11 = ProcessGlobalConfigParams(v8, a3, a4, 1u, 0, &hKey, (__int64)&v20, 1);
      v12 = v11;
      if ( v11 >= 0 )
      {
        v11 = (*(__int64 (__fastcall **)(HKEY, _QWORD, __int64, _DWORD *))(v20 + 24))(
                hKey,
                *(_QWORD *)(v20 + 16),
                a5,
                a6);
        v12 = v11;
        if ( v11 >= 0 )
          goto LABEL_13;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
          goto LABEL_13;
        if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_25;
        v18 = 148;
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
          goto LABEL_13;
        if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_25;
        v18 = 147;
      }
    }
    v17 = (unsigned int)v11;
LABEL_21:
    WPP_SF_d(*((_QWORD *)v9 + 2), v18, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, v17);
LABEL_22:
    v9 = WPP_GLOBAL_Control;
    goto LABEL_25;
  }
  LastError = GetLastError();
  v12 = LastError;
  if ( LastError > 0 )
    v12 = (unsigned __int16)LastError | 0x80070000;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, v12);
    goto LABEL_11;
  }
LABEL_12:
  if ( (v12 & 0x80000000) != 0 )
  {
LABEL_25:
    if ( v9 != (LPCOLESTR)&WPP_GLOBAL_Control && (v9[14] & 1) != 0 )
      WPP_SF_ddd(*((_QWORD *)v9 + 2), 149, a3, v8, a4, v12);
  }
LABEL_13:
  if ( v10 )
    FWGPUnlockEx(v10, "FwGetGlobalConfig");
  if ( hKey )
    RegCloseKey(hKey);
  return v12;
}

```

## disassembly

```asm
0x1800032b0  mov     [rsp-38h+arg_0], rbx
0x1800032b5  push    rbp
0x1800032b6  push    rsi
0x1800032b7  push    rdi
0x1800032b8  push    r12
0x1800032ba  push    r13
0x1800032bc  push    r14
0x1800032be  push    r15
0x1800032c0  mov     rbp, rsp
0x1800032c3  sub     rsp, 60h
0x1800032c7  mov     rax, cs:__security_cookie
0x1800032ce  xor     rax, rsp
0x1800032d1  mov     [rbp+var_10], rax
0x1800032d5  mov     r15, [rbp+arg_20]
0x1800032d9  mov     r13d, r9d
0x1800032dc  mov     r12, [rbp+arg_28]
0x1800032e0  mov     r14, r8
0x1800032e3  mov     edi, edx
0x1800032e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800032ec  lea     rax, WPP_GLOBAL_Control
0x1800032f3  cmp     rcx, rax
0x1800032f6  jz      short loc_18000331A
0x1800032f8  test    byte ptr [rcx+1Ch], 8
0x1800032fc  jz      short loc_18000331A
0x1800032fe  mov     rcx, [rcx+10h]
0x180003302  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x180003309  mov     edx, 8Dh
0x18000330e  call    WPP_SF_
0x180003313  mov     rcx, cs:WPP_GLOBAL_Control
0x18000331a  xor     ebx, ebx
0x18000331c  lea     eax, [rdi-1]
0x18000331f  mov     [rbp+hKey], rbx
0x180003323  mov     esi, ebx
0x180003325  mov     [rbp+var_20], rbx
0x180003329  cmp     eax, 0Bh
0x18000332c  ja      loc_18000340D
0x180003332  lea     eax, [r13-1]
0x180003336  cmp     eax, 11h
0x180003339  ja      loc_18000340D
0x18000333f  cmp     edi, 6
0x180003342  jz      loc_180003587
0x180003348  test    r15, r15
0x18000334b  jz      loc_1800035BD
0x180003351  cmp     edi, 1
0x180003354  jz      loc_1800035F4
0x18000335a  mov     [rsp+60h+var_28], ebx
0x18000335e  lea     rax, [rbp+var_20]
0x180003362  mov     [rsp+60h+var_30], rax
0x180003367  mov     r9d, 1
0x18000336d  lea     rax, [rbp+hKey]
0x180003371  mov     r8d, r13d
0x180003374  mov     [rsp+60h+var_38], rax
0x180003379  mov     rdx, r14
0x18000337c  mov     ecx, edi
0x18000337e  mov     [rsp+60h+var_40], ebx
0x180003382  call    ?ProcessGlobalConfigParams@@YAJW4_tag_FW_STORE_TYPE@@PEAUHKEY__@@KKHPEAPEAU2@PEAPEAU_tag_WF_CONFIG_DESCRIPTOR@@H@Z; ProcessGlobalConfigParams(_tag_FW_STORE_TYPE,HKEY__ *,ulong,ulong,int,HKEY__ * *,_tag_WF_CONFIG_DESCRIPTOR * *,int)
0x180003387  mov     ebx, eax
0x180003389  test    eax, eax
0x18000338b  js      loc_180003446
0x180003391  mov     rdx, [rbp+var_20]
0x180003395  mov     r9, r12
0x180003398  mov     rcx, [rbp+hKey]
0x18000339c  mov     r8, r15
0x18000339f  mov     rax, [rdx+18h]
0x1800033a3  mov     rdx, [rdx+10h]
0x1800033a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033ac  mov     ebx, eax
0x1800033ae  cmp     eax, 80070002h
0x1800033b3  jz      loc_180003499
0x1800033b9  lea     r14, WPP_GLOBAL_Control
0x1800033c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033c7  test    ebx, ebx
0x1800033c9  js      loc_180003467
0x1800033cf  test    rsi, rsi
0x1800033d2  jnz     loc_180003666
0x1800033d8  mov     rcx, [rbp+hKey]; hKey
0x1800033dc  test    rcx, rcx
0x1800033df  jz      short loc_1800033E7
0x1800033e1  call    cs:__imp_RegCloseKey
0x1800033e7  mov     eax, ebx
0x1800033e9  mov     rcx, [rbp+var_10]
0x1800033ed  xor     rcx, rsp; StackCookie
0x1800033f0  call    __security_check_cookie
0x1800033f5  mov     rbx, [rsp+60h+arg_0]
0x1800033fd  add     rsp, 60h
0x180003401  pop     r15
0x180003403  pop     r14
0x180003405  pop     r13
0x180003407  pop     r12
0x180003409  pop     rdi
0x18000340a  pop     rsi
0x18000340b  pop     rbp
0x18000340c  retn
0x18000340d  mov     r9d, 80070057h
0x180003413  mov     ebx, r9d
0x180003416  lea     r14, WPP_GLOBAL_Control
0x18000341d  cmp     rcx, r14
0x180003420  jz      short loc_1800033E7
0x180003422  test    byte ptr [rcx+1Ch], 1
0x180003426  jz      short loc_180003467
0x180003428  mov     edx, 8Eh
0x18000342d  mov     rcx, [rcx+10h]
0x180003431  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x180003438  call    WPP_SF_d
0x18000343d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003444  jmp     short loc_180003467
0x180003446  mov     rcx, cs:WPP_GLOBAL_Control
0x18000344d  lea     r14, WPP_GLOBAL_Control
0x180003454  cmp     rcx, r14
0x180003457  jz      loc_1800033CF
0x18000345d  test    byte ptr [rcx+1Ch], 1
0x180003461  jnz     loc_18000360A
0x180003467  cmp     rcx, r14
0x18000346a  jz      loc_1800033CF
0x180003470  test    byte ptr [rcx+1Ch], 1
0x180003474  jz      loc_1800033CF
0x18000347a  mov     rcx, [rcx+10h]
0x18000347e  mov     edx, 95h
0x180003483  mov     dword ptr [rsp+60h+var_38], ebx
0x180003487  mov     r9d, edi
0x18000348a  mov     [rsp+60h+var_40], r13d
0x18000348f  call    WPP_SF_ddd
0x180003494  jmp     loc_1800033CF
0x180003499  call    cs:__imp_FwLicensingIsXbox
0x18000349f  test    eax, eax
0x1800034a1  jz      short loc_1800034AC
0x1800034a3  lea     r14, WPP_GLOBAL_Control
0x1800034aa  jmp     short loc_18000343D
0x1800034ac  mov     r8d, 49h ; 'I'
0x1800034b2  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x1800034b9  lea     rcx, ?g_FwPersistentStoreRootKey@@3PAGA; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x1800034c0  call    cs:__imp__o__wcsnicmp
0x1800034c6  test    eax, eax
0x1800034c8  jz      short loc_1800034A3
0x1800034ca  mov     [rsp+60h+var_28], 1
0x1800034d2  lea     rax, [rbp+var_20]
0x1800034d6  mov     [rsp+60h+var_30], rax
0x1800034db  mov     r9d, 1
0x1800034e1  lea     rax, [rbp+hKey]
0x1800034e5  mov     r8d, r13d
0x1800034e8  mov     [rsp+60h+var_38], rax
0x1800034ed  mov     rdx, r14
0x1800034f0  mov     ecx, edi
0x1800034f2  mov     [rsp+60h+var_40], 0
0x1800034fa  call    ?ProcessGlobalConfigParams@@YAJW4_tag_FW_STORE_TYPE@@PEAUHKEY__@@KKHPEAPEAU2@PEAPEAU_tag_WF_CONFIG_DESCRIPTOR@@H@Z; ProcessGlobalConfigParams(_tag_FW_STORE_TYPE,HKEY__ *,ulong,ulong,int,HKEY__ * *,_tag_WF_CONFIG_DESCRIPTOR * *,int)
0x1800034ff  mov     ebx, eax
0x180003501  test    eax, eax
0x180003503  jns     loc_18000361E
0x180003509  mov     rcx, cs:WPP_GLOBAL_Control
0x180003510  lea     r14, WPP_GLOBAL_Control
0x180003517  cmp     rcx, r14
0x18000351a  jz      loc_1800033CF
0x180003520  test    byte ptr [rcx+1Ch], 1
0x180003524  jz      loc_180003467
0x18000352a  mov     edx, 93h
0x18000352f  jmp     loc_180003616
0x180003534  call    cs:__imp_GetLastError
0x18000353a  mov     ebx, eax
0x18000353c  test    eax, eax
0x18000353e  jle     short loc_180003549
0x180003540  movzx   ebx, ax
0x180003543  or      ebx, 80070000h
0x180003549  mov     rcx, cs:WPP_GLOBAL_Control
0x180003550  lea     r14, WPP_GLOBAL_Control
0x180003557  cmp     rcx, r14
0x18000355a  jz      loc_1800033C7
0x180003560  test    byte ptr [rcx+1Ch], 1
0x180003564  jz      loc_1800033C7
0x18000356a  mov     rcx, [rcx+10h]
0x18000356e  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x180003575  mov     edx, 91h
0x18000357a  mov     r9d, ebx
0x18000357d  call    WPP_SF_d
0x180003582  jmp     loc_1800033C0
0x180003587  test    r14, r14
0x18000358a  jnz     loc_180003348
0x180003590  mov     r9d, 80070057h
0x180003596  mov     ebx, r9d
0x180003599  lea     r14, WPP_GLOBAL_Control
0x1800035a0  cmp     rcx, r14
0x1800035a3  jz      loc_1800033E7
0x1800035a9  test    byte ptr [rcx+1Ch], 1
0x1800035ad  jz      loc_180003467
0x1800035b3  mov     edx, 8Fh
0x1800035b8  jmp     loc_18000342D
0x1800035bd  cmp     [r12], ebx
0x1800035c1  jz      loc_180003351
0x1800035c7  mov     r9d, 80070057h
0x1800035cd  mov     ebx, r9d
0x1800035d0  lea     r14, WPP_GLOBAL_Control
0x1800035d7  cmp     rcx, r14
0x1800035da  jz      loc_1800033E7
0x1800035e0  test    byte ptr [rcx+1Ch], 1
0x1800035e4  jz      loc_180003467
0x1800035ea  mov     edx, 90h
0x1800035ef  jmp     loc_18000342D
0x1800035f4  call    FWGPLock
0x1800035f9  mov     rsi, rax
0x1800035fc  test    rax, rax
0x1800035ff  jnz     loc_18000335A
0x180003605  jmp     loc_180003534
0x18000360a  mov     edx, 92h
0x18000360f  jmp     short loc_180003616
0x180003611  mov     edx, 94h
0x180003616  mov     r9d, eax
0x180003619  jmp     loc_18000342D
0x18000361e  mov     rdx, [rbp+var_20]
0x180003622  mov     r9, r12
0x180003625  mov     rcx, [rbp+hKey]
0x180003629  mov     r8, r15
0x18000362c  mov     rax, [rdx+18h]
0x180003630  mov     rdx, [rdx+10h]
0x180003634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003639  mov     ebx, eax
0x18000363b  test    eax, eax
0x18000363d  jns     loc_1800033CF
0x180003643  mov     rcx, cs:WPP_GLOBAL_Control
0x18000364a  lea     r14, WPP_GLOBAL_Control
0x180003651  cmp     rcx, r14
0x180003654  jz      loc_1800033CF
0x18000365a  test    byte ptr [rcx+1Ch], 1
0x18000365e  jz      loc_180003467
0x180003664  jmp     short loc_180003611
0x180003666  lea     rdx, aFwgetglobalcon_1; "FwGetGlobalConfig"
0x18000366d  mov     rcx, rsi
0x180003670  call    FWGPUnlockEx
0x180003675  jmp     loc_1800033D8
```
