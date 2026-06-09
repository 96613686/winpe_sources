# CWSManGroupPolicyManager::GetStringInternal(IRequestContext *,WSManGroupPolicySetting,ulong,ulong,ushort *,ulong *,WSManGroupPolicySettingState *)

- ea: `0x180041eb0`
- end: `0x1800427c0`
- name: `?GetStringInternal@CWSManGroupPolicyManager@@AEAAHPEAVIRequestContext@@W4WSManGroupPolicySetting@@KKPEAGPEAKPEAW4WSManGroupPolicySettingState@@@Z`
- size: `2320`
- prototype: `__int64 __fastcall(CWSManGroupPolicyManager *, struct IRequestContext *, unsigned int, int, DWORD cbData, LPBYTE lpData, DWORD *, _DWORD *)`
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800418d0`
- `0x180041b20`
- `0x180041b60`
- `0x180043c10`

## callees

- `0x180005d10`
- `0x180041eb0`
- `0x1800e8e90`
- `0x180112380`
- `0x1801123a8`
- `0x1801133b0`
- `0x18012352c`
- `0x18012a93c`
- `0x180193af4`
- `0x180193bb8`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042289`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004233b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042359`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800424f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042640`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800426a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800426be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004276b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042289`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004233b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042359`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800424f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180042640`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800426a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800426be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004276b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041ff3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041ff3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800421f7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800421f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041f9e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180041f9e`

## string_xrefs

- `0x180041f67`: `SOFTWARE\Policies\Microsoft\Windows\WinRM\Service`
- `0x180042188`: `SOFTWARE\Policies\Microsoft\Windows\WinRM\Service\WinRS`
- `0x180042150`: `onecore\admin\wmi\wmx\config\wsmangrouppolicymanager.cpp`
- `0x18004238c`: `onecore\admin\wmi\wmx\config\wsmangrouppolicymanager.cpp`
- `0x1800423af`: `onecore\admin\wmi\wmx\config\wsmangrouppolicymanager.cpp`
- `0x1800423f2`: `onecore\admin\wmi\wmx\config\configutils.cpp`
- `0x18004241f`: `onecore\admin\wmi\wmx\config\configutils.cpp`
- `0x18004250e`: `RegOpenKeyEx`
- `0x180042799`: `onecore\admin\wmi\wmx\config\wsmangrouppolicysetting.cpp`

## pseudocode

```c
__int64 __fastcall CWSManGroupPolicyManager::GetStringInternal(
        CWSManGroupPolicyManager *a1,
        struct IRequestContext *a2,
        unsigned int a3,
        int a4,
        DWORD cbData,
        LPBYTE lpData,
        DWORD *a7,
        _DWORD *a8)
{
  struct IRequestContext *v10; // r13
  CWSManGroupPolicyManager *v11; // r8
  unsigned __int16 *v12; // rdi
  unsigned __int64 v13; // r12
  DWORD *v14; // r15
  unsigned int i; // eax
  const struct _WSMAN_POLICY_INFO near *const *v16; // rbx
  int v17; // eax
  const WCHAR *v18; // rdx
  DWORD v19; // r13d
  __int64 v20; // rcx
  LSTATUS v21; // eax
  DWORD v22; // ebp
  PVOID *v23; // r10
  struct IRequestContext *v24; // r14
  HKEY v25; // rcx
  unsigned __int16 *v26; // rcx
  __int64 v27; // rax
  unsigned int v28; // eax
  unsigned __int64 v29; // r8
  __int64 v30; // rax
  unsigned __int16 v31; // dx
  unsigned __int16 *v32; // rcx
  const unsigned __int16 *v34; // r8
  __int64 v35; // rdx
  HKEY v36; // rbp
  const WCHAR *v37; // r15
  LSTATUS v38; // eax
  const unsigned __int16 *v39; // r8
  __int64 v40; // rdx
  const unsigned __int16 *v41; // r8
  __int64 v42; // rdx
  __int64 v43; // rdx
  const unsigned __int16 *v44; // r8
  DWORD Type; // [rsp+30h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-40h] BYREF

  v10 = a2;
  v11 = a1;
  v12 = (unsigned __int16 *)lpData;
  v13 = cbData;
  if ( !cbData )
  {
    v14 = a7;
    goto LABEL_3;
  }
  if ( !lpData )
  {
    v34 = L"886";
    v35 = 886;
    goto LABEL_129;
  }
  v14 = a7;
  if ( !a7 )
  {
    v34 = L"887";
    v35 = 887;
LABEL_129:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\wsmangrouppolicymanager.cpp", v35, v34, 0x54Fu, v10);
    return 0;
  }
LABEL_3:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids, a3);
    v11 = a1;
  }
  *v14 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= 0x1B )
    {
      v43 = 312;
      v44 = L"312";
      goto LABEL_128;
    }
    v16 = &g_GroupPolicySettings + 6 * i;
    if ( a3 == *(_DWORD *)v16 )
      break;
  }
  if ( (a4 & (_DWORD)v16[2]) == 0 )
  {
    v43 = 307;
    v44 = L"307";
LABEL_128:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\wsmangrouppolicysetting.cpp", v43, v44, 0x54Fu, v10);
    v34 = L"897";
    v35 = 897;
    goto LABEL_129;
  }
  Type = 0;
  if ( 2 * (_DWORD)v13 && !v12 )
  {
    v39 = L"1124";
    v40 = 1124;
    goto LABEL_87;
  }
  v17 = *((_DWORD *)v16 + 5);
  switch ( v17 )
  {
    case 1:
      v18 = L"SOFTWARE\\Policies\\Microsoft\\Windows\\WinRM\\Service";
      goto LABEL_12;
    case 2:
      v18 = L"SOFTWARE\\Policies\\Microsoft\\Windows\\WinRM\\Client";
LABEL_12:
      v19 = 0;
      hKey = 0;
      v20 = *((_QWORD *)v11 + 26);
      if ( !v20 )
        v20 = -2147483646;
      v21 = RegOpenKeyExW((HKEY)v20, v18, 0, 0x20119u, &hKey);
      v22 = v21;
      if ( v21 )
      {
        if ( v21 == 2 )
        {
          v23 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
          {
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              55,
              WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids,
              *((_QWORD *)v16 + 1));
            v23 = (PVOID *)WPP_GLOBAL_Control;
          }
          goto LABEL_19;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
          WPP_SF_dS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            56,
            (unsigned int)WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids,
            v21,
            *((_QWORD *)v16 + 1));
        SetLastError(v22);
        v24 = a2;
        if ( a2 )
          (*(void (__fastcall **)(struct IRequestContext *, __int64, const wchar_t *, _QWORD))(*(_QWORD *)a2 + 88LL))(
            a2,
            1077134176,
            L"RegOpenKeyEx",
            v22);
        v23 = (PVOID *)WPP_GLOBAL_Control;
LABEL_20:
        v25 = hKey;
        hKey = 0;
        if ( v25 )
        {
          RegCloseKey(v25);
          v23 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( !v22 )
        {
          if ( Type != 1 )
          {
            if ( v23 != &WPP_GLOBAL_Control && (*((_DWORD *)v23 + 7) & 0x400000) != 0 )
              WPP_SF_dSd(
                (unsigned int)v23[2],
                52,
                (unsigned int)WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids,
                a3,
                *((_QWORD *)v16 + 1),
                Type);
            if ( v24 )
              (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, _QWORD))(*(_QWORD *)v24 + 64LL))(
                v24,
                2150858888LL,
                1077134330,
                *((_QWORD *)v16 + 1));
            SetLastError(0x80338005);
            *v14 = 0;
            return 0;
          }
          if ( v23 != &WPP_GLOBAL_Control && (*((_DWORD *)v23 + 7) & 0x200000) != 0 )
          {
            WPP_SF_dSS((TRACEHANDLE)v23[2], *((_QWORD *)v16 + 1), (__int64)v12);
            v23 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v19 >= 2 && *((_BYTE *)v12 + v19 - 1) && *((_BYTE *)v12 + v19 - 2) )
          {
            if ( v23 != &WPP_GLOBAL_Control && (*((_DWORD *)v23 + 7) & 0x400000) != 0 )
              WPP_SF_(v23[2], 50, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids);
            SetLastError(0x7Au);
            *v14 = (v19 >> 1) + 1;
            return 0;
          }
          if ( !CWSManGroupPolicyManager::ValidateString(a1, v24, (const struct _WSMAN_POLICY_INFO *)v16, v12) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
              WPP_SF_dSS(*((_QWORD *)WPP_GLOBAL_Control + 2), *((_QWORD *)v16 + 1), (__int64)v12);
            if ( v24 )
              (*(void (__fastcall **)(struct IRequestContext *, __int64, __int64, _QWORD))(*(_QWORD *)v24 + 64LL))(
                v24,
                2150858888LL,
                1077134331,
                *((_QWORD *)v16 + 1));
            SetLastError(0x80338088);
            return 0;
          }
          *v14 = v19 >> 1;
          if ( a8 )
            *a8 = 3;
          return 1;
        }
        if ( v22 == 122 )
        {
          SetLastError(0x7Au);
          *v14 = v19 >> 1;
          return 0;
        }
        if ( v22 != 2 )
        {
          v10 = a2;
          goto LABEL_120;
        }
        if ( v23 != &WPP_GLOBAL_Control && (*((_DWORD *)v23 + 7) & 0x200000) != 0 )
          WPP_SF_SdS(
            (unsigned int)v23[2],
            53,
            (unsigned int)WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids,
            *((_QWORD *)v16 + 5),
            a3,
            *((_QWORD *)v16 + 1));
        v26 = (unsigned __int16 *)*((_QWORD *)v16 + 5);
        v27 = -1;
        do
          ++v27;
        while ( v26[v27] );
        if ( (unsigned int)v27 >= 0x200 )
        {
          WSManError(
            (wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\wsmangrouppolicymanager.cpp",
            986,
            L"986",
            0x54Fu,
            0);
          return 0;
        }
        v28 = v27 + 1;
        *v14 = v28;
        if ( (unsigned int)v13 >= v28 )
        {
          v29 = v13;
          if ( (_DWORD)v13 )
          {
            if ( v13 <= 0x7FFFFFFF )
            {
              v30 = 2147483646;
              do
              {
                if ( !v30 )
                  break;
                v31 = *v26;
                if ( !*v26 )
                  break;
                ++v26;
                *v12++ = v31;
                --v30;
                --v29;
              }
              while ( v29 );
              v32 = v12 - 1;
              if ( v29 )
                v32 = v12;
              *v32 = 0;
              if ( v29 )
              {
                if ( a8 )
                  *a8 = 0;
                return 1;
              }
              goto LABEL_84;
            }
            *v12 = 0;
          }
          WSManError(
            (wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\wsmangrouppolicymanager.cpp",
            1007,
            L"1007",
            0x54Fu,
            0);
          return 0;
        }
LABEL_84:
        SetLastError(0x7Au);
        return 0;
      }
      if ( 2 * (_DWORD)v13 && !v12 )
      {
        v41 = L"505";
        v42 = 505;
LABEL_89:
        v24 = a2;
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configutils.cpp", v42, v41, 0x54Fu, a2);
LABEL_91:
        v23 = (PVOID *)WPP_GLOBAL_Control;
        v22 = 1359;
        goto LABEL_20;
      }
      v36 = hKey;
      if ( !hKey )
      {
        v41 = L"508";
        v42 = 508;
        goto LABEL_89;
      }
      v37 = (const WCHAR *)*((_QWORD *)v16 + 1);
      if ( !v37 )
      {
        v24 = a2;
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configutils.cpp", 509, L"509", 0x54Fu, a2);
        v14 = a7;
        goto LABEL_91;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200000) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          &WPP_56614427bb63350db5b96d546a520a16_Traceguids,
          *((_QWORD *)v16 + 1));
      cbData = 2 * v13;
      v38 = RegQueryValueExW(v36, v37, 0, &Type, (LPBYTE)v12, &cbData);
      v22 = v38;
      if ( v38 )
      {
        v23 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
          goto LABEL_61;
        WPP_SF_dS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          (unsigned int)&WPP_56614427bb63350db5b96d546a520a16_Traceguids,
          v38,
          (__int64)v37);
      }
      else
      {
        v19 = cbData;
        if ( !v12 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_56614427bb63350db5b96d546a520a16_Traceguids, v37);
          v22 = 122;
          SetLastError(0x7Au);
        }
      }
      v23 = (PVOID *)WPP_GLOBAL_Control;
LABEL_61:
      v14 = a7;
LABEL_19:
      v24 = a2;
      goto LABEL_20;
    case 3:
      v18 = L"SOFTWARE\\Policies\\Microsoft\\Windows\\WinRM\\Service\\WinRS";
      goto LABEL_12;
  }
  WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\wsmangrouppolicymanager.cpp", 1087, L"1087", 0x54Fu, 0);
  v39 = L"1129";
  v40 = 1129;
LABEL_87:
  WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\wsmangrouppolicymanager.cpp", v40, v39, 0x54Fu, v10);
  v22 = 1359;
  v23 = (PVOID *)WPP_GLOBAL_Control;
LABEL_120:
  if ( v23 != &WPP_GLOBAL_Control && (*((_DWORD *)v23 + 7) & 0x400000) != 0 )
    WPP_SF_d(v23[2], 54, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids, v22);
  if ( v10 )
    (*(void (__fastcall **)(struct IRequestContext *, _QWORD, __int64, _QWORD))(*(_QWORD *)v10 + 64LL))(
      v10,
      v22,
      1077134331,
      *((_QWORD *)v16 + 1));
  SetLastError(v22);
  return 0;
}

```

## disassembly

```asm
0x180041eb0  mov     [rsp+arg_10], rbx
0x180041eb5  mov     [rsp+arg_8], rdx
0x180041eba  mov     [rsp+arg_0], rcx
0x180041ebf  push    rbp
0x180041ec0  push    rsi
0x180041ec1  push    rdi
0x180041ec2  push    r12
0x180041ec4  push    r13
0x180041ec6  push    r14
0x180041ec8  push    r15
0x180041eca  sub     rsp, 40h
0x180041ece  mov     ebp, r9d
0x180041ed1  mov     esi, r8d
0x180041ed4  mov     r13, rdx
0x180041ed7  mov     r8, rcx
0x180041eda  mov     rdi, [rsp+78h+lpData]
0x180041ee2  mov     r12d, [rsp+78h+cbData]
0x180041eea  test    r12d, r12d
0x180041eed  jnz     loc_18004210A
0x180041ef3  mov     r15, [rsp+78h+arg_30]
0x180041efb  lea     rax, WPP_GLOBAL_Control
0x180041f02  mov     rcx, cs:WPP_GLOBAL_Control
0x180041f09  cmp     rcx, rax
0x180041f0c  jnz     loc_1800420D8
0x180041f12  xor     r10d, r10d
0x180041f15  mov     [r15], r10d
0x180041f18  mov     eax, r10d
0x180041f1b  lea     r9, ?g_GroupPolicySettings@@3QBU_WSMAN_POLICY_INFO@@B; _WSMAN_POLICY_INFO const near * const g_GroupPolicySettings
0x180041f22  cmp     eax, 1Bh
0x180041f25  jnb     loc_180042784
0x180041f2b  mov     ecx, eax
0x180041f2d  lea     rbx, [rcx+rcx*2]
0x180041f31  shl     rbx, 4
0x180041f35  add     rbx, r9
0x180041f38  cmp     esi, [rbx]
0x180041f3a  jz      short loc_180041F40
0x180041f3c  inc     eax
0x180041f3e  jmp     short loc_180041F22
0x180041f40  test    [rbx+10h], ebp
0x180041f43  jz      loc_180042776
0x180041f49  mov     [rsp+78h+Type], r10d
0x180041f4e  lea     r14d, [r12+r12]
0x180041f52  test    r14d, r14d
0x180041f55  jnz     loc_1800422D3
0x180041f5b  mov     eax, [rbx+14h]
0x180041f5e  cmp     eax, 1
0x180041f61  jnz     loc_180042176
0x180041f67  lea     rdx, SubKey; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180041f6e  mov     r13d, r10d
0x180041f71  mov     [rsp+78h+hKey], r10
0x180041f76  mov     rcx, [r8+0D0h]
0x180041f7d  mov     rax, 0FFFFFFFF80000002h
0x180041f84  test    rcx, rcx
0x180041f87  cmovz   rcx, rax; hKey
0x180041f8b  lea     rax, [rsp+78h+hKey]
0x180041f90  mov     [rsp+78h+phkResult], rax; phkResult
0x180041f95  mov     r9d, 20119h; samDesired
0x180041f9b  xor     r8d, r8d; ulOptions
0x180041f9e  call    cs:__imp_RegOpenKeyExW
0x180041fa4  mov     ebp, eax
0x180041fa6  test    eax, eax
0x180041fa8  jz      loc_180042194
0x180041fae  cmp     eax, 2
0x180041fb1  jnz     loc_1800424B6
0x180041fb7  mov     r10, cs:WPP_GLOBAL_Control
0x180041fbe  lea     rdx, WPP_GLOBAL_Control
0x180041fc5  cmp     r10, rdx
0x180041fc8  jz      short loc_180041FD8
0x180041fca  test    dword ptr [r10+1Ch], 400000h
0x180041fd2  jnz     loc_18004248A
0x180041fd8  mov     r14, [rsp+78h+arg_8]
0x180041fe0  mov     rcx, [rsp+78h+hKey]; hKey
0x180041fe5  mov     [rsp+78h+hKey], 0
0x180041fee  test    rcx, rcx
0x180041ff1  jz      short loc_180042007
0x180041ff3  call    cs:__imp_RegCloseKey
0x180041ff9  mov     r10, cs:WPP_GLOBAL_Control
0x180042000  lea     rdx, WPP_GLOBAL_Control
0x180042007  test    ebp, ebp
0x180042009  jz      loc_180042235
0x18004200f  cmp     ebp, 7Ah ; 'z'
0x180042012  jz      loc_1800426B9
0x180042018  cmp     ebp, 2
0x18004201b  jnz     loc_180042719
0x180042021  cmp     r10, rdx
0x180042024  jz      short loc_180042034
0x180042026  test    dword ptr [r10+1Ch], 200000h
0x18004202e  jnz     loc_1800426CF
0x180042034  mov     rcx, [rbx+28h]
0x180042038  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18004203f  nop
0x180042040  inc     rax
0x180042043  cmp     word ptr [rcx+rax*2], 0
0x180042048  jnz     short loc_180042040
0x18004204a  cmp     eax, 200h
0x18004204f  jnb     loc_180042135
0x180042055  inc     eax
0x180042057  mov     [r15], eax
0x18004205a  cmp     r12d, eax
0x18004205d  jb      loc_180042354
0x180042063  mov     r8, r12
0x180042066  test    r12d, r12d
0x180042069  jz      loc_1800426FF
0x18004206f  cmp     r12, 7FFFFFFFh
0x180042076  ja      loc_1800426FA
0x18004207c  mov     eax, 7FFFFFFEh
0x180042081  test    rax, rax
0x180042084  jz      short loc_1800420A2
0x180042086  movzx   edx, word ptr [rcx]
0x180042089  test    dx, dx
0x18004208c  jz      short loc_1800420A2
0x18004208e  add     rcx, 2
0x180042092  mov     [rdi], dx
0x180042095  add     rdi, 2
0x180042099  dec     rax
0x18004209c  sub     r8, 1
0x1800420a0  jnz     short loc_180042081
0x1800420a2  lea     rcx, [rdi-2]
0x1800420a6  test    r8, r8
0x1800420a9  cmovnz  rcx, rdi
0x1800420ad  xor     eax, eax
0x1800420af  mov     [rcx], ax
0x1800420b2  test    r8, r8
0x1800420b5  jz      loc_180042354
0x1800420bb  mov     rax, [rsp+78h+arg_38]
0x1800420c3  test    rax, rax
0x1800420c6  jz      short loc_1800420CE
0x1800420c8  mov     dword ptr [rax], 0
0x1800420ce  mov     eax, 1
0x1800420d3  jmp     loc_18004215E
0x1800420d8  test    dword ptr [rcx+1Ch], 200000h
0x1800420df  jz      loc_180041F12
0x1800420e5  mov     edx, 30h ; '0'
0x1800420ea  mov     r9d, esi
0x1800420ed  lea     r8, WPP_f70e972d993d3b5c7751a89ee7db7ab3_Traceguids
0x1800420f4  mov     rcx, [rcx+10h]
0x1800420f8  call    WPP_SF_d
0x1800420fd  mov     r8, [rsp+78h+arg_0]
0x180042105  jmp     loc_180041F12
0x18004210a  test    rdi, rdi
0x18004210d  jz      loc_180042364
0x180042113  mov     r15, [rsp+78h+arg_30]
0x18004211b  test    r15, r15
0x18004211e  jnz     loc_180041EFB
0x180042124  lea     r8, a887; "887"
0x18004212b  mov     edx, 377h
0x180042130  jmp     loc_1800427B6
0x180042135  mov     [rsp+78h+phkResult], 0; struct IRequestContext *
0x18004213e  lea     r8, a986; "986"
0x180042145  mov     edx, 3DAh; unsigned int
0x18004214a  mov     r9d, 54Fh; unsigned int
0x180042150  lea     rcx, aOnecoreAdminWm_41; "onecore\\admin\\wmi\\wmx\\config\\wsman"...
0x180042157  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18004215c  xor     eax, eax
0x18004215e  mov     rbx, [rsp+78h+arg_10]
0x180042166  add     rsp, 40h
0x18004216a  pop     r15
0x18004216c  pop     r14
0x18004216e  pop     r13
0x180042170  pop     r12
0x180042172  pop     rdi
0x180042173  pop     rsi
0x180042174  pop     rbp
0x180042175  retn
0x180042176  cmp     eax, 2
0x180042179  jz      loc_1800422C7
0x18004217f  cmp     eax, 3
0x180042182  jnz     loc_180042375
0x180042188  lea     rdx, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18004218f  jmp     loc_180041F6E
0x180042194  test    r14d, r14d
0x180042197  jnz     loc_1800422ED
0x18004219d  mov     rbp, [rsp+78h+hKey]
0x1800421a2  test    rbp, rbp
0x1800421a5  jz      loc_1800423D3
0x1800421ab  mov     r15, [rbx+8]
0x1800421af  test    r15, r15
0x1800421b2  jz      loc_180042400
0x1800421b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800421bf  lea     rax, WPP_GLOBAL_Control
0x1800421c6  cmp     rcx, rax
0x1800421c9  jnz     loc_18004229D
0x1800421cf  mov     [rsp+78h+cbData], r14d
0x1800421d7  lea     rax, [rsp+78h+cbData]
0x1800421df  mov     [rsp+78h+lpcbData], rax; lpcbData
0x1800421e4  mov     [rsp+78h+phkResult], rdi; lpData
0x1800421e9  lea     r9, [rsp+78h+Type]; lpType
0x1800421ee  xor     r8d, r8d; lpReserved
0x1800421f1  mov     rdx, r15; lpValueName
0x1800421f4  mov     rcx, rbp; hKey
0x1800421f7  call    cs:__imp_RegQueryValueExW
0x1800421fd  mov     ebp, eax
0x1800421ff  test    eax, eax
0x180042201  jz      loc_180042307
0x180042207  mov     r10, cs:WPP_GLOBAL_Control
0x18004220e  lea     rdx, WPP_GLOBAL_Control
0x180042215  cmp     r10, rdx
0x180042218  jz      short loc_180042228
0x18004221a  test    dword ptr [r10+1Ch], 400000h
0x180042222  jnz     loc_180042468
0x180042228  mov     r15, [rsp+78h+arg_30]
0x180042230  jmp     loc_180041FD8
0x180042235  mov     eax, [rsp+78h+Type]
0x180042239  cmp     eax, 1
0x18004223c  jnz     loc_18004264B
0x180042242  cmp     r10, rdx
0x180042245  jz      short loc_180042255
0x180042247  test    dword ptr [r10+1Ch], 200000h
0x18004224f  jnz     loc_180042539
0x180042255  cmp     r13d, 2
0x180042259  jb      loc_18004259A
0x18004225f  lea     eax, [r13-1]
0x180042263  cmp     byte ptr [rax+rdi], 0
0x180042267  jz      loc_18004259A
0x18004226d  lea     eax, [r13-2]
0x180042271  cmp     byte ptr [rax+rdi], 0
0x180042275  jz      loc_18004259A
0x18004227b  cmp     r10, rdx
0x18004227e  jnz     loc_180042572
0x180042284  mov     ecx, 7Ah ; 'z'; dwErrCode
0x180042289  call    cs:__imp_SetLastError
0x18004228f  shr     r13d, 1
0x180042292  inc     r13d
0x180042295  mov     [r15], r13d
0x180042298  jmp     loc_18004215C
0x18004229d  test    dword ptr [rcx+1Ch], 200000h
0x1800422a4  jz      loc_1800421CF
0x1800422aa  mov     edx, 1Dh
0x1800422af  mov     r9, r15
0x1800422b2  lea     r8, WPP_56614427bb63350db5b96d546a520a16_Traceguids
0x1800422b9  mov     rcx, [rcx+10h]
0x1800422bd  call    WPP_SF_S
0x1800422c2  jmp     loc_1800421CF
0x1800422c7  lea     rdx, aSoftwarePolici_2; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x1800422ce  jmp     loc_180041F6E
0x1800422d3  test    rdi, rdi
0x1800422d6  jnz     loc_180041F5B
0x1800422dc  lea     r8, a1124; "1124"
0x1800422e3  mov     edx, 464h
0x1800422e8  jmp     loc_1800423A4
0x1800422ed  test    rdi, rdi
0x1800422f0  jnz     loc_18004219D
0x1800422f6  lea     r8, a505; "505"
0x1800422fd  mov     edx, 1F9h
0x180042302  jmp     loc_1800423DF
0x180042307  mov     r13d, [rsp+78h+cbData]
0x18004230f  test    rdi, rdi
0x180042312  jnz     short loc_180042341
0x180042314  mov     rcx, cs:WPP_GLOBAL_Control
0x18004231b  lea     rax, WPP_GLOBAL_Control
0x180042322  cmp     rcx, rax
0x180042325  jz      short loc_180042334
0x180042327  test    dword ptr [rcx+1Ch], 400000h
0x18004232e  jnz     loc_18004244B
0x180042334  mov     ebp, 7Ah ; 'z'
0x180042339  mov     ecx, ebp; dwErrCode
0x18004233b  call    cs:__imp_SetLastError
0x180042341  mov     r10, cs:WPP_GLOBAL_Control
0x180042348  lea     rdx, WPP_GLOBAL_Control
0x18004234f  jmp     loc_180042228
0x180042354  mov     ecx, 7Ah ; 'z'; dwErrCode
0x180042359  call    cs:__imp_SetLastError
0x18004235f  jmp     loc_18004215C
0x180042364  lea     r8, a886; "886"
0x18004236b  mov     edx, 376h
0x180042370  jmp     loc_1800427B6
0x180042375  mov     [rsp+78h+phkResult], r10; struct IRequestContext *
0x18004237a  mov     r9d, 54Fh; unsigned int
0x180042380  lea     r8, a1087; "1087"
0x180042387  mov     edx, 43Fh; unsigned int
0x18004238c  lea     rcx, aOnecoreAdminWm_41; "onecore\\admin\\wmi\\wmx\\config\\wsman"...
0x180042393  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180042398  lea     r8, a1129; "1129"
0x18004239f  mov     edx, 469h; unsigned int
0x1800423a4  mov     r9d, 54Fh; unsigned int
0x1800423aa  mov     [rsp+78h+phkResult], r13; struct IRequestContext *
0x1800423af  lea     rcx, aOnecoreAdminWm_41; "onecore\\admin\\wmi\\wmx\\config\\wsman"...
0x1800423b6  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800423bb  mov     ebp, 54Fh
0x1800423c0  mov     r10, cs:WPP_GLOBAL_Control
0x1800423c7  lea     rdx, WPP_GLOBAL_Control
0x1800423ce  jmp     loc_180042721
0x1800423d3  lea     r8, a508; "508"
0x1800423da  mov     edx, 1FCh; unsigned int
0x1800423df  mov     r14, [rsp+78h+arg_8]
0x1800423e7  mov     r9d, 54Fh; unsigned int
0x1800423ed  mov     [rsp+78h+phkResult], r14; struct IRequestContext *
0x1800423f2  lea     rcx, aOnecoreAdminWm_22; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x1800423f9  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1800423fe  jmp     short loc_180042433
0x180042400  mov     r14, [rsp+78h+arg_8]
0x180042408  mov     [rsp+78h+phkResult], r14; struct IRequestContext *
0x18004240d  mov     r9d, 54Fh; unsigned int
0x180042413  lea     r8, a509; "509"
0x18004241a  mov     edx, 1FDh; unsigned int
0x18004241f  lea     rcx, aOnecoreAdminWm_22; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x180042426  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18004242b  mov     r15, [rsp+78h+arg_30]
0x180042433  mov     r10, cs:WPP_GLOBAL_Control
0x18004243a  mov     ebp, 54Fh
  ... truncated ...
```
