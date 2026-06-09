# CWSManGroupPolicyManager::GetInt(IRequestContext *,WSManGroupPolicySetting,ulong *,WSManGroupPolicySettingState *)

- ea: `0x180046200`
- end: `0x180046867`
- name: `?GetInt@CWSManGroupPolicyManager@@QEAAHPEAVIRequestContext@@W4WSManGroupPolicySetting@@PEAKPEAW4WSManGroupPolicySettingState@@@Z`
- size: `1639`
- prototype: `int __high(struct IRequestContext *, enum WSManGroupPolicySetting, unsigned int *, enum WSManGroupPolicySettingState *)`
- caller_count: `8`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180042970`
- `0x180043330`
- `0x180043c10`
- `0x180045670`
- `0x180045b10`
- `0x180046140`
- `0x180046e50`
- `0x1800be198`

## callees

- `0x180005d10`
- `0x180046200`
- `0x1800da9d0`
- `0x180112380`
- `0x1801123a8`
- `0x1801133b0`
- `0x180125ec4`
- `0x18012a93c`
- `0x180193bb8`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800464dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800465d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180046801`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800464dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800465d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180046801`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046309`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046309`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180046408`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180046408`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800462c5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800462c5`

## string_xrefs

- `0x180046291`: `SOFTWARE\Policies\Microsoft\Windows\WinRM\Service`
- `0x1800463a1`: `SOFTWARE\Policies\Microsoft\Windows\WinRM\Service\WinRS`
- `0x180046785`: `onecore\admin\wmi\wmx\config\wsmangrouppolicymanager.cpp`
- `0x1800467a5`: `onecore\admin\wmi\wmx\config\wsmangrouppolicymanager.cpp`
- `0x180046856`: `onecore\admin\wmi\wmx\config\wsmangrouppolicymanager.cpp`
- `0x18004651a`: `onecore\admin\wmi\wmx\config\configutils.cpp`
- `0x180046544`: `onecore\admin\wmi\wmx\config\configutils.cpp`
- `0x1800465ea`: `RegOpenKeyEx`
- `0x180046831`: `onecore\admin\wmi\wmx\config\wsmangrouppolicysetting.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWSManGroupPolicyManager::GetInt(
        CWSManGroupPolicyManager *a1,
        struct IRequestContext *a2,
        unsigned int a3,
        _DWORD *a4,
        _DWORD *a5)
{
  unsigned int i; // eax
  const struct _WSMAN_POLICY_INFO near *const *v10; // rbx
  int v11; // eax
  const WCHAR *v12; // rdx
  __int64 v13; // rcx
  LSTATUS v14; // eax
  unsigned int v15; // esi
  PVOID *v16; // rcx
  HKEY v17; // rax
  HKEY v19; // rsi
  const WCHAR *v20; // rbp
  const unsigned __int16 *v21; // r8
  __int64 v22; // rdx
  unsigned int v23; // eax
  __int64 v24; // r8
  __int64 v25; // rdx
  const unsigned __int16 *v26; // r8
  DWORD Type; // [rsp+30h] [rbp-58h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-54h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-50h] BYREF
  unsigned int Data; // [rsp+A8h] [rbp+20h] BYREF

  if ( !a4 )
  {
    v21 = L"689";
    v22 = 689;
LABEL_87:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\wsmangrouppolicymanager.cpp", v22, v21, 0x54Fu, a2);
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids, a3);
  for ( i = 0; ; ++i )
  {
    if ( i >= 0x1B )
    {
      v25 = 312;
      v26 = L"312";
      goto LABEL_86;
    }
    v10 = &g_GroupPolicySettings + 6 * i;
    if ( a3 == *(_DWORD *)v10 )
      break;
  }
  if ( ((_BYTE)v10[2] & 3) == 0 )
  {
    v25 = 307;
    v26 = L"307";
LABEL_86:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\wsmangrouppolicysetting.cpp", v25, v26, 0x54Fu, a2);
    v21 = L"696";
    v22 = 696;
    goto LABEL_87;
  }
  Type = 0;
  Data = 0;
  v11 = *((_DWORD *)v10 + 5);
  switch ( v11 )
  {
    case 1:
      v12 = L"SOFTWARE\\Policies\\Microsoft\\Windows\\WinRM\\Service";
      goto LABEL_10;
    case 2:
      v12 = L"SOFTWARE\\Policies\\Microsoft\\Windows\\WinRM\\Client";
LABEL_10:
      hKey = 0;
      v13 = *((_QWORD *)a1 + 26);
      if ( !v13 )
        v13 = -2147483646;
      v14 = RegOpenKeyExW((HKEY)v13, v12, 0, 0x20119u, &hKey);
      v15 = v14;
      if ( v14 )
      {
        if ( v14 == 2 )
        {
          v16 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
            goto LABEL_16;
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            55,
            WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids,
            *((_QWORD *)v10 + 1));
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
            WPP_SF_dS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              56,
              (unsigned int)WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids,
              v14,
              *((_QWORD *)v10 + 1));
          SetLastError(v15);
          if ( a2 )
            (*(void (__fastcall **)(struct IRequestContext *, __int64, const wchar_t *, _QWORD))(*(_QWORD *)a2 + 88LL))(
              a2,
              1077134176,
              L"RegOpenKeyEx",
              v15);
        }
      }
      else
      {
        v19 = hKey;
        if ( hKey )
        {
          v20 = (const WCHAR *)*((_QWORD *)v10 + 1);
          if ( v20 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                29,
                &WPP_56614427bb63350db5b96d546a520a16_Traceguids,
                *((_QWORD *)v10 + 1));
            cbData = 4;
            v15 = RegQueryValueExW(v19, v20, 0, &Type, (LPBYTE)&Data, &cbData);
            if ( v15 )
            {
              v16 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
              {
LABEL_16:
                v17 = hKey;
                hKey = 0;
                if ( v17 )
                {
                  RegCloseKey(v17);
                  v16 = (PVOID *)WPP_GLOBAL_Control;
                }
                if ( v15 )
                {
                  if ( v15 == 2 )
                  {
                    if ( v16 != &WPP_GLOBAL_Control && (*((_DWORD *)v16 + 7) & 0x200000) != 0 )
                      WPP_SF_ddS(
                        (unsigned int)v16[2],
                        44,
                        (unsigned int)WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids,
                        *((_DWORD *)v10 + 6),
                        a3,
                        *((_QWORD *)v10 + 1));
                    *a4 = *((_DWORD *)v10 + 6);
                    if ( a5 )
                      *a5 = 0;
                    return 1;
                  }
                  if ( v15 != 234 )
                    goto LABEL_78;
                  if ( v16 != &WPP_GLOBAL_Control && (*((_DWORD *)v16 + 7) & 0x400000) != 0 )
                    WPP_SF_(v16[2], 45, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids);
                  if ( a2 )
                  {
                    v24 = 1077134331;
                    goto LABEL_76;
                  }
                }
                else
                {
                  if ( Type == 4 )
                  {
                    if ( v16 != &WPP_GLOBAL_Control && (*((_DWORD *)v16 + 7) & 0x200000) != 0 )
                      WPP_SF_dSd(
                        (unsigned int)v16[2],
                        41,
                        (unsigned int)WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids,
                        a3,
                        *((_QWORD *)v10 + 1),
                        Data);
                    if ( !CWSManGroupPolicyManager::ValidateInt(a1, a2, (const struct _WSMAN_POLICY_INFO *)v10, Data) )
                    {
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
                      {
                        WPP_SF_dSd(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          42,
                          (unsigned int)WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids,
                          a3,
                          *((_QWORD *)v10 + 1),
                          Data);
                      }
                      return 0;
                    }
                    v23 = Data;
                    *a4 = Data;
                    if ( a5 )
                      *a5 = 2 - (v23 != 0);
                    return 1;
                  }
                  if ( v16 != &WPP_GLOBAL_Control && (*((_DWORD *)v16 + 7) & 0x400000) != 0 )
                    WPP_SF_dSd(
                      (unsigned int)v16[2],
                      43,
                      (unsigned int)WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids,
                      a3,
                      *((_QWORD *)v10 + 1),
                      Type);
                  if ( a2 )
                  {
                    v24 = 1077134330;
LABEL_76:
                    (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, _QWORD))(*(_QWORD *)a2 + 64LL))(
                      a2,
                      2150858888LL,
                      v24,
                      *((_QWORD *)v10 + 1));
                  }
                }
                SetLastError(0x80338005);
                return 0;
              }
              WPP_SF_dS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                31,
                (unsigned int)&WPP_56614427bb63350db5b96d546a520a16_Traceguids,
                v15,
                (__int64)v20);
            }
            v16 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_16;
          }
          v15 = 1359;
          WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configutils.cpp", 509, L"509", 0x54Fu, a2);
        }
        else
        {
          v15 = 1359;
          WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configutils.cpp", 508, L"508", 0x54Fu, a2);
        }
      }
      v16 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_16;
    case 3:
      v12 = L"SOFTWARE\\Policies\\Microsoft\\Windows\\WinRM\\Service\\WinRS";
      goto LABEL_10;
  }
  v15 = 1359;
  WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\wsmangrouppolicymanager.cpp", 1087, L"1087", 0x54Fu, 0);
  WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\wsmangrouppolicymanager.cpp", 1129, L"1129", 0x54Fu, a2);
  v16 = (PVOID *)WPP_GLOBAL_Control;
LABEL_78:
  if ( v16 != &WPP_GLOBAL_Control && (*((_DWORD *)v16 + 7) & 0x400000) != 0 )
    WPP_SF_d(v16[2], 46, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids, v15);
  if ( a2 )
    (*(void (__fastcall **)(struct IRequestContext *, _QWORD, __int64, _QWORD))(*(_QWORD *)a2 + 64LL))(
      a2,
      v15,
      1077134331,
      *((_QWORD *)v10 + 1));
  SetLastError(v15);
  return 0;
}

```

## disassembly

```asm
0x180046200  push    rbx
0x180046202  push    rbp
0x180046203  push    rsi
0x180046204  push    rdi
0x180046205  push    r12
0x180046207  push    r13
0x180046209  push    r14
0x18004620b  push    r15
0x18004620d  sub     rsp, 48h
0x180046211  mov     r14, r9
0x180046214  mov     edi, r8d
0x180046217  mov     r12, rdx
0x18004621a  mov     r15, rcx
0x18004621d  test    r9, r9
0x180046220  jz      loc_1800464EA
0x180046226  lea     rbp, WPP_GLOBAL_Control
0x18004622d  mov     rcx, cs:WPP_GLOBAL_Control
0x180046234  cmp     rcx, rbp
0x180046237  jnz     loc_180046365
0x18004623d  xor     r13d, r13d
0x180046240  mov     eax, r13d
0x180046243  lea     r8, ?g_GroupPolicySettings@@3QBU_WSMAN_POLICY_INFO@@B; _WSMAN_POLICY_INFO const near * const g_GroupPolicySettings
0x18004624a  nop     word ptr [rax+rax+00h]
0x180046250  cmp     eax, 1Bh
0x180046253  jnb     loc_18004681A
0x180046259  mov     ecx, eax
0x18004625b  lea     rbx, [rcx+rcx*2]
0x18004625f  shl     rbx, 4
0x180046263  add     rbx, r8
0x180046266  cmp     edi, [rbx]
0x180046268  jz      short loc_18004626E
0x18004626a  inc     eax
0x18004626c  jmp     short loc_180046250
0x18004626e  test    byte ptr [rbx+10h], 3
0x180046272  jz      loc_18004680C
0x180046278  mov     [rsp+88h+Type], r13d
0x18004627d  mov     [rsp+88h+Data], r13d
0x180046285  mov     eax, [rbx+14h]
0x180046288  cmp     eax, 1
0x18004628b  jnz     loc_18004638F
0x180046291  lea     rdx, SubKey; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180046298  mov     [rsp+88h+hKey], r13
0x18004629d  mov     rcx, [r15+0D0h]
0x1800462a4  mov     rax, 0FFFFFFFF80000002h
0x1800462ab  test    rcx, rcx
0x1800462ae  cmovz   rcx, rax; hKey
0x1800462b2  lea     rax, [rsp+88h+hKey]
0x1800462b7  mov     [rsp+88h+phkResult], rax; phkResult
0x1800462bc  mov     r9d, 20119h; samDesired
0x1800462c2  xor     r8d, r8d; ulOptions
0x1800462c5  call    cs:__imp_RegOpenKeyExW
0x1800462cb  mov     esi, eax
0x1800462cd  test    eax, eax
0x1800462cf  jz      loc_1800463AD
0x1800462d5  cmp     eax, 2
0x1800462d8  jnz     loc_1800465A0
0x1800462de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800462e5  cmp     rcx, rbp
0x1800462e8  jz      short loc_1800462F7
0x1800462ea  test    dword ptr [rcx+1Ch], 400000h
0x1800462f1  jnz     loc_180046585
0x1800462f7  mov     rax, [rsp+88h+hKey]
0x1800462fc  mov     [rsp+88h+hKey], r13
0x180046301  test    rax, rax
0x180046304  jz      short loc_180046316
0x180046306  mov     rcx, rax; hKey
0x180046309  call    cs:__imp_RegCloseKey
0x18004630f  mov     rcx, cs:WPP_GLOBAL_Control
0x180046316  test    esi, esi
0x180046318  jz      loc_180046476
0x18004631e  cmp     esi, 2
0x180046321  jnz     loc_180046710
0x180046327  cmp     rcx, rbp
0x18004632a  jz      short loc_180046339
0x18004632c  test    dword ptr [rcx+1Ch], 200000h
0x180046333  jnz     loc_1800466E5
0x180046339  mov     eax, [rbx+18h]
0x18004633c  mov     [r14], eax
0x18004633f  mov     rax, [rsp+88h+arg_20]
0x180046347  test    rax, rax
0x18004634a  jz      short loc_18004634F
0x18004634c  mov     [rax], r13d
0x18004634f  mov     eax, 1
0x180046354  add     rsp, 48h
0x180046358  pop     r15
0x18004635a  pop     r14
0x18004635c  pop     r13
0x18004635e  pop     r12
0x180046360  pop     rdi
0x180046361  pop     rsi
0x180046362  pop     rbp
0x180046363  pop     rbx
0x180046364  retn
0x180046365  test    dword ptr [rcx+1Ch], 200000h
0x18004636c  jz      loc_18004623D
0x180046372  mov     edx, 28h ; '('
0x180046377  mov     r9d, edi
0x18004637a  lea     r8, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids
0x180046381  mov     rcx, [rcx+10h]
0x180046385  call    WPP_SF_d
0x18004638a  jmp     loc_18004623D
0x18004638f  cmp     eax, 2
0x180046392  jz      loc_18004646A
0x180046398  cmp     eax, 3
0x18004639b  jnz     loc_18004676C
0x1800463a1  lea     rdx, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x1800463a8  jmp     loc_180046298
0x1800463ad  mov     rsi, [rsp+88h+hKey]
0x1800463b2  test    rsi, rsi
0x1800463b5  jz      loc_180046501
0x1800463bb  mov     rbp, [rbx+8]
0x1800463bf  test    rbp, rbp
0x1800463c2  jz      loc_18004652B
0x1800463c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800463cf  lea     rax, WPP_GLOBAL_Control
0x1800463d6  cmp     rcx, rax
0x1800463d9  jnz     short loc_180046444
0x1800463db  mov     [rsp+88h+cbData], 4
0x1800463e3  lea     rax, [rsp+88h+cbData]
0x1800463e8  mov     [rsp+88h+lpcbData], rax; lpcbData
0x1800463ed  lea     rax, [rsp+88h+Data]
0x1800463f5  mov     [rsp+88h+phkResult], rax; lpData
0x1800463fa  lea     r9, [rsp+88h+Type]; lpType
0x1800463ff  xor     r8d, r8d; lpReserved
0x180046402  mov     rdx, rbp; lpValueName
0x180046405  mov     rcx, rsi; hKey
0x180046408  call    cs:__imp_RegQueryValueExW
0x18004640e  mov     esi, eax
0x180046410  test    eax, eax
0x180046412  jz      loc_180046579
0x180046418  mov     rcx, cs:WPP_GLOBAL_Control
0x18004641f  lea     rax, WPP_GLOBAL_Control
0x180046426  cmp     rcx, rax
0x180046429  jz      short loc_180046438
0x18004642b  test    dword ptr [rcx+1Ch], 400000h
0x180046432  jnz     loc_18004655C
0x180046438  lea     rbp, WPP_GLOBAL_Control
0x18004643f  jmp     loc_1800462F7
0x180046444  test    dword ptr [rcx+1Ch], 200000h
0x18004644b  jz      short loc_1800463DB
0x18004644d  mov     edx, 1Dh
0x180046452  mov     r9, rbp
0x180046455  lea     r8, WPP_56614427bb63350db5b96d546a520a16_Traceguids
0x18004645c  mov     rcx, [rcx+10h]
0x180046460  call    WPP_SF_S
0x180046465  jmp     loc_1800463DB
0x18004646a  lea     rdx, aSoftwarePolici_2; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180046471  jmp     loc_180046298
0x180046476  mov     eax, [rsp+88h+Type]
0x18004647a  cmp     eax, 4
0x18004647d  jnz     short loc_1800464C6
0x18004647f  cmp     rcx, rbp
0x180046482  jz      short loc_180046491
0x180046484  test    dword ptr [rcx+1Ch], 200000h
0x18004648b  jnz     loc_18004660E
0x180046491  mov     r9d, [rsp+88h+Data]; unsigned int
0x180046499  mov     r8, rbx; struct _WSMAN_POLICY_INFO *
0x18004649c  mov     rdx, r12; struct IRequestContext *
0x18004649f  mov     rcx, r15; this
0x1800464a2  call    ?ValidateInt@CWSManGroupPolicyManager@@AEAAHPEAVIRequestContext@@PEBU_WSMAN_POLICY_INFO@@K@Z; CWSManGroupPolicyManager::ValidateInt(IRequestContext *,_WSMAN_POLICY_INFO const *,ulong)
0x1800464a7  test    eax, eax
0x1800464a9  jnz     loc_18004663F
0x1800464af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800464b6  cmp     rcx, rbp
0x1800464b9  jnz     loc_180046668
0x1800464bf  xor     eax, eax
0x1800464c1  jmp     loc_180046354
0x1800464c6  cmp     rcx, rbp
0x1800464c9  jnz     loc_1800466A6
0x1800464cf  test    r12, r12
0x1800464d2  jnz     loc_1800466DD
0x1800464d8  mov     ecx, 80338005h; dwErrCode
0x1800464dd  call    cs:__imp_SetLastError
0x1800464e3  xor     eax, eax
0x1800464e5  jmp     loc_180046354
0x1800464ea  mov     r9d, 54Fh
0x1800464f0  lea     r8, a689; "689"
0x1800464f7  mov     edx, 2B1h
0x1800464fc  jmp     loc_180046851
0x180046501  mov     [rsp+88h+phkResult], r12; struct IRequestContext *
0x180046506  mov     esi, 54Fh
0x18004650b  mov     r9d, esi; unsigned int
0x18004650e  lea     r8, a508; "508"
0x180046515  mov     edx, 1FCh; unsigned int
0x18004651a  lea     rcx, aOnecoreAdminWm_22; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x180046521  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180046526  jmp     loc_180046602
0x18004652b  mov     [rsp+88h+phkResult], r12; struct IRequestContext *
0x180046530  mov     esi, 54Fh
0x180046535  mov     r9d, esi; unsigned int
0x180046538  lea     r8, a509; "509"
0x18004653f  mov     edx, 1FDh; unsigned int
0x180046544  lea     rcx, aOnecoreAdminWm_22; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x18004654b  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180046550  lea     rbp, WPP_GLOBAL_Control
0x180046557  jmp     loc_180046602
0x18004655c  mov     edx, 1Fh
0x180046561  mov     [rsp+88h+phkResult], rbp
0x180046566  mov     r9d, esi
0x180046569  lea     r8, WPP_56614427bb63350db5b96d546a520a16_Traceguids
0x180046570  mov     rcx, [rcx+10h]
0x180046574  call    WPP_SF_dS
0x180046579  mov     rcx, cs:WPP_GLOBAL_Control
0x180046580  jmp     loc_180046438
0x180046585  mov     edx, 37h ; '7'
0x18004658a  mov     r9, [rbx+8]
0x18004658e  lea     r8, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids
0x180046595  mov     rcx, [rcx+10h]
0x180046599  call    WPP_SF_S
0x18004659e  jmp     short loc_180046602
0x1800465a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800465a7  cmp     rcx, rbp
0x1800465aa  jz      short loc_1800465D6
0x1800465ac  test    dword ptr [rcx+1Ch], 400000h
0x1800465b3  jz      short loc_1800465D6
0x1800465b5  mov     edx, 38h ; '8'
0x1800465ba  mov     rax, [rbx+8]
0x1800465be  mov     [rsp+88h+phkResult], rax
0x1800465c3  mov     r9d, esi
0x1800465c6  lea     r8, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids
0x1800465cd  mov     rcx, [rcx+10h]
0x1800465d1  call    WPP_SF_dS
0x1800465d6  mov     ecx, esi; dwErrCode
0x1800465d8  call    cs:__imp_SetLastError
0x1800465de  test    r12, r12
0x1800465e1  jz      short loc_180046602
0x1800465e3  mov     rax, [r12]
0x1800465e7  mov     r9d, esi
0x1800465ea  lea     r8, aRegopenkeyex; "RegOpenKeyEx"
0x1800465f1  mov     edx, 4033C360h
0x1800465f6  mov     rcx, r12
0x1800465f9  mov     rax, [rax+58h]
0x1800465fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046602  mov     rcx, cs:WPP_GLOBAL_Control
0x180046609  jmp     loc_1800462F7
0x18004660e  mov     edx, 29h ; ')'
0x180046613  mov     eax, [rsp+88h+Data]
0x18004661a  mov     dword ptr [rsp+88h+lpcbData], eax
0x18004661e  mov     rax, [rbx+8]
0x180046622  mov     [rsp+88h+phkResult], rax
0x180046627  mov     r9d, edi
0x18004662a  lea     r8, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids
0x180046631  mov     rcx, [rcx+10h]
0x180046635  call    WPP_SF_dSd
0x18004663a  jmp     loc_180046491
0x18004663f  mov     eax, [rsp+88h+Data]
0x180046646  mov     [r14], eax
0x180046649  mov     rcx, [rsp+88h+arg_20]
0x180046651  test    rcx, rcx
0x180046654  jz      loc_18004634F
0x18004665a  neg     eax
0x18004665c  sbb     eax, eax
0x18004665e  add     eax, 2
0x180046661  mov     [rcx], eax
0x180046663  jmp     loc_18004634F
0x180046668  test    dword ptr [rcx+1Ch], 400000h
0x18004666f  jz      loc_1800464BF
0x180046675  mov     edx, 2Ah ; '*'
0x18004667a  mov     eax, [rsp+88h+Data]
0x180046681  mov     dword ptr [rsp+88h+lpcbData], eax
0x180046685  mov     rax, [rbx+8]
0x180046689  mov     [rsp+88h+phkResult], rax
0x18004668e  mov     r9d, edi
0x180046691  lea     r8, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids
0x180046698  mov     rcx, [rcx+10h]
0x18004669c  call    WPP_SF_dSd
0x1800466a1  jmp     loc_1800464BF
0x1800466a6  test    dword ptr [rcx+1Ch], 400000h
0x1800466ad  jz      loc_1800464CF
0x1800466b3  mov     edx, 2Bh ; '+'
0x1800466b8  mov     dword ptr [rsp+88h+lpcbData], eax
0x1800466bc  mov     rax, [rbx+8]
0x1800466c0  mov     [rsp+88h+phkResult], rax
0x1800466c5  mov     r9d, edi
0x1800466c8  lea     r8, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids
0x1800466cf  mov     rcx, [rcx+10h]
0x1800466d3  call    WPP_SF_dSd
0x1800466d8  jmp     loc_1800464CF
0x1800466dd  mov     r8d, 4033C3FAh
0x1800466e3  jmp     short loc_18004674E
0x1800466e5  mov     edx, 2Ch ; ','
0x1800466ea  mov     rax, [rbx+8]
0x1800466ee  mov     [rsp+88h+lpcbData], rax
0x1800466f3  mov     dword ptr [rsp+88h+phkResult], edi
0x1800466f7  mov     r9d, [rbx+18h]
0x1800466fb  lea     r8, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids
0x180046702  mov     rcx, [rcx+10h]
0x180046706  call    WPP_SF_ddS
0x18004670b  jmp     loc_180046339
0x180046710  cmp     esi, 0EAh
0x180046716  jnz     loc_1800467B8
0x18004671c  cmp     rcx, rbp
0x18004671f  jz      short loc_18004673F
0x180046721  test    dword ptr [rcx+1Ch], 400000h
0x180046728  jz      short loc_18004673F
0x18004672a  mov     edx, 2Dh ; '-'
0x18004672f  lea     r8, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids
0x180046736  mov     rcx, [rcx+10h]
0x18004673a  call    WPP_SF_
0x18004673f  test    r12, r12
  ... truncated ...
```
