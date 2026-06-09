# CWorkspaceNotifier::SetDismissalTimeNow(void)

- ea: `0x180040024`
- end: `0x18004027b`
- name: `?SetDismissalTimeNow@CWorkspaceNotifier@@KAJXZ`
- size: `599`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003fbbc`

## callees

- `0x18000b1d8`
- `0x18000ec94`
- `0x18000ece0`
- `0x18003f338`
- `0x180040024`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180040263`
- `ADVAPI32!RegCloseKey` at `0x180040263`
- `ADVAPI32!RegSetValueExW` at `0x180040193`
- `ADVAPI32!RegSetValueExW` at `0x1800401ff`
- `ADVAPI32!RegSetValueExW` at `0x180040193`
- `ADVAPI32!RegSetValueExW` at `0x1800401ff`
- `ADVAPI32!RegCreateKeyExW` at `0x1800400f7`
- `ADVAPI32!RegCreateKeyExW` at `0x1800400f7`

## pseudocode

```c
__int64 CWorkspaceNotifier::SetDismissalTimeNow(void)
{
  int TimeNow; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v2; // esi
  unsigned int v3; // eax
  __int64 v4; // rdx
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF
  struct _FILETIME v7; // [rsp+68h] [rbp+10h] BYREF

  v7 = 0;
  hKey = 0;
  TimeNow = CWorkspaceNotifier::GetTimeNow(&v7);
  if ( TimeNow < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        (unsigned int)WPP_11e42980f3ff3eb00f98904b3d254f87_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"GetTimeNow failed",
        TimeNow);
    }
    goto LABEL_34;
  }
  TimeNow = RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Workspaces", 0, 0, 0, 0x20006u, 0, &hKey, 0);
  if ( TimeNow )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( TimeNow > 0 )
        v2 = (unsigned __int16)TimeNow | 0x80070000;
      else
        v2 = TimeNow;
      v3 = RdpWppGetCurrentThreadActivityIdPrefix();
      v4 = 40;
LABEL_14:
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, WPP_11e42980f3ff3eb00f98904b3d254f87_Traceguids, v3, v2);
    }
  }
  else
  {
    TimeNow = RegSetValueExW(hKey, L"NotificationDismissalTimeHigh", 0, 4u, (const BYTE *)&v7.dwHighDateTime, 4u);
    if ( !TimeNow )
    {
      TimeNow = RegSetValueExW(hKey, L"NotificationDismissalTimeLow", 0, 4u, (const BYTE *)&v7, 4u);
      if ( !TimeNow )
      {
        TimeNow = 0;
        goto LABEL_34;
      }
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_15;
      }
      if ( TimeNow > 0 )
        v2 = (unsigned __int16)TimeNow | 0x80070000;
      else
        v2 = TimeNow;
      v3 = RdpWppGetCurrentThreadActivityIdPrefix();
      v4 = 42;
      goto LABEL_14;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( TimeNow > 0 )
        v2 = (unsigned __int16)TimeNow | 0x80070000;
      else
        v2 = TimeNow;
      v3 = RdpWppGetCurrentThreadActivityIdPrefix();
      v4 = 41;
      goto LABEL_14;
    }
  }
LABEL_15:
  if ( TimeNow > 0 )
    TimeNow = (unsigned __int16)TimeNow | 0x80070000;
LABEL_34:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)TimeNow;
}

```

## disassembly

```asm
0x180040024  mov     rax, rsp
0x180040027  mov     [rax+18h], rbx
0x18004002b  mov     [rax+20h], rsi
0x18004002f  push    rdi
0x180040030  sub     rsp, 50h
0x180040034  lea     rcx, [rax+10h]; lpFileTime
0x180040038  mov     qword ptr [rax+10h], 0
0x180040040  mov     qword ptr [rax+8], 0
0x180040048  call    ?GetTimeNow@CWorkspaceNotifier@@KAJAEAU_FILETIME@@@Z; CWorkspaceNotifier::GetTimeNow(_FILETIME &)
0x18004004d  mov     ebx, eax
0x18004004f  test    eax, eax
0x180040051  jns     short loc_1800400B7
0x180040053  mov     rcx, cs:WPP_GLOBAL_Control
0x18004005a  lea     rax, WPP_GLOBAL_Control
0x180040061  cmp     rcx, rax
0x180040064  jz      loc_180040259
0x18004006a  test    byte ptr [rcx+1Ch], 8
0x18004006e  jz      loc_180040259
0x180040074  cmp     byte ptr [rcx+19h], 2
0x180040078  jb      loc_180040259
0x18004007e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180040083  lea     rcx, aGettimenowFail; "GetTimeNow failed"
0x18004008a  mov     [rsp+58h+samDesired], ebx
0x18004008e  mov     qword ptr [rsp+58h+dwOptions], rcx
0x180040093  lea     r8, WPP_11e42980f3ff3eb00f98904b3d254f87_Traceguids
0x18004009a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800400a1  mov     edx, 27h ; '''
0x1800400a6  mov     r9d, eax
0x1800400a9  mov     rcx, [rcx+10h]
0x1800400ad  call    WPP_SF_DsD
0x1800400b2  jmp     loc_180040259
0x1800400b7  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x1800400c0  lea     rax, [rsp+58h+hKey]
0x1800400c5  mov     [rsp+58h+phkResult], rax; phkResult
0x1800400ca  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Workspaces"
0x1800400d1  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800400da  xor     r9d, r9d; lpClass
0x1800400dd  mov     [rsp+58h+samDesired], 20006h; samDesired
0x1800400e5  xor     r8d, r8d; Reserved
0x1800400e8  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800400ef  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800400f7  call    cs:__imp_RegCreateKeyExW
0x1800400fd  mov     ebx, eax
0x1800400ff  test    eax, eax
0x180040101  jz      short loc_18004016E
0x180040103  mov     rcx, cs:WPP_GLOBAL_Control
0x18004010a  lea     rax, WPP_GLOBAL_Control
0x180040111  mov     edi, 80070000h
0x180040116  cmp     rcx, rax
0x180040119  jz      short loc_18004015C
0x18004011b  test    byte ptr [rcx+1Ch], 8
0x18004011f  jz      short loc_18004015C
0x180040121  cmp     byte ptr [rcx+19h], 2
0x180040125  jb      short loc_18004015C
0x180040127  test    ebx, ebx
0x180040129  jg      short loc_18004012F
0x18004012b  mov     esi, ebx
0x18004012d  jmp     short loc_180040134
0x18004012f  movzx   esi, bx
0x180040132  or      esi, edi
0x180040134  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180040139  mov     edx, 28h ; '('
0x18004013e  mov     rcx, cs:WPP_GLOBAL_Control
0x180040145  lea     r8, WPP_11e42980f3ff3eb00f98904b3d254f87_Traceguids
0x18004014c  mov     r9d, eax
0x18004014f  mov     [rsp+58h+dwOptions], esi
0x180040153  mov     rcx, [rcx+10h]
0x180040157  call    WPP_SF_Dd
0x18004015c  test    ebx, ebx
0x18004015e  jle     loc_180040259
0x180040164  movzx   ebx, bx
0x180040167  or      ebx, edi
0x180040169  jmp     loc_180040259
0x18004016e  mov     rcx, [rsp+58h+hKey]; hKey
0x180040173  lea     rax, [rsp+58h+Data]
0x180040178  mov     edi, 4
0x18004017d  lea     rdx, aNotificationdi; "NotificationDismissalTimeHigh"
0x180040184  mov     [rsp+58h+samDesired], edi; cbData
0x180040188  mov     r9d, edi; dwType
0x18004018b  xor     r8d, r8d; Reserved
0x18004018e  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180040193  call    cs:__imp_RegSetValueExW
0x180040199  mov     ebx, eax
0x18004019b  test    eax, eax
0x18004019d  jz      short loc_1800401DF
0x18004019f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800401a6  lea     rax, WPP_GLOBAL_Control
0x1800401ad  mov     edi, 80070000h
0x1800401b2  cmp     rcx, rax
0x1800401b5  jz      short loc_18004015C
0x1800401b7  test    byte ptr [rcx+1Ch], 8
0x1800401bb  jz      short loc_18004015C
0x1800401bd  cmp     byte ptr [rcx+19h], 2
0x1800401c1  jb      short loc_18004015C
0x1800401c3  test    ebx, ebx
0x1800401c5  jg      short loc_1800401CB
0x1800401c7  mov     esi, ebx
0x1800401c9  jmp     short loc_1800401D0
0x1800401cb  movzx   esi, bx
0x1800401ce  or      esi, edi
0x1800401d0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800401d5  mov     edx, 29h ; ')'
0x1800401da  jmp     loc_18004013E
0x1800401df  mov     rcx, [rsp+58h+hKey]; hKey
0x1800401e4  lea     rax, [rsp+58h+arg_8]
0x1800401e9  mov     [rsp+58h+samDesired], edi; cbData
0x1800401ed  lea     rdx, aNotificationdi_0; "NotificationDismissalTimeLow"
0x1800401f4  mov     r9d, edi; dwType
0x1800401f7  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1800401fc  xor     r8d, r8d; Reserved
0x1800401ff  call    cs:__imp_RegSetValueExW
0x180040205  mov     ebx, eax
0x180040207  test    eax, eax
0x180040209  jz      short loc_180040257
0x18004020b  mov     rcx, cs:WPP_GLOBAL_Control
0x180040212  lea     rax, WPP_GLOBAL_Control
0x180040219  mov     edi, 80070000h
0x18004021e  cmp     rcx, rax
0x180040221  jz      loc_18004015C
0x180040227  test    byte ptr [rcx+1Ch], 8
0x18004022b  jz      loc_18004015C
0x180040231  cmp     byte ptr [rcx+19h], 2
0x180040235  jb      loc_18004015C
0x18004023b  test    ebx, ebx
0x18004023d  jg      short loc_180040243
0x18004023f  mov     esi, ebx
0x180040241  jmp     short loc_180040248
0x180040243  movzx   esi, bx
0x180040246  or      esi, edi
0x180040248  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18004024d  mov     edx, 2Ah ; '*'
0x180040252  jmp     loc_18004013E
0x180040257  xor     ebx, ebx
0x180040259  mov     rcx, [rsp+58h+hKey]; hKey
0x18004025e  test    rcx, rcx
0x180040261  jz      short loc_180040269
0x180040263  call    cs:__imp_RegCloseKey
0x180040269  mov     rsi, [rsp+58h+arg_18]
0x18004026e  mov     eax, ebx
0x180040270  mov     rbx, [rsp+58h+arg_10]
0x180040275  add     rsp, 50h
0x180040279  pop     rdi
0x18004027a  retn
```
