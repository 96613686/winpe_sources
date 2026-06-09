# SuspRaiseNotification(_SUS_NOTIFICATION)

- ea: `0x180003478`
- end: `0x180003607`
- name: `?SuspRaiseNotification@@YAJW4_SUS_NOTIFICATION@@@Z`
- size: `399`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001940`
- `0x180003610`

## callees

- `0x180001bc0`
- `0x180003478`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000354f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800035b1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000354f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800035b1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800034d2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800034d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800035f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800035f4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180003580`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180003580`

## pseudocode

```c
__int64 __fastcall SuspRaiseNotification(int a1)
{
  int v2; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  int Data; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  Data = 0;
  v2 = RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\StartupNotify",
         0,
         0,
         0,
         0x20006u,
         0,
         &hKey,
         0);
  if ( v2 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 20;
LABEL_5:
      WPP_SF_D(v3[2], v4, WPP_91e8665fb8f03560ae482285a745ac49_Traceguids, 16389);
    }
  }
  else
  {
    v2 = RegSetValueExW(hKey, L"EnableStartupAppNotification", 0, 4u, (const BYTE *)&Data, 4u);
    if ( v2 )
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v4 = 21;
        goto LABEL_5;
      }
    }
    else
    {
      Sleep(0x1F4u);
      Data = a1;
      v2 = RegSetValueExW(hKey, L"EnableStartupAppNotification", 0, 4u, (const BYTE *)&Data, 4u);
      if ( !v2 )
      {
        v2 = 0;
        goto LABEL_17;
      }
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v4 = 22;
        goto LABEL_5;
      }
    }
  }
  if ( v2 > 0 )
    v2 = (unsigned __int16)v2 | 0x80070000;
LABEL_17:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180003478  mov     r11, rsp
0x18000347b  mov     [r11+8], rbx
0x18000347f  push    rdi
0x180003480  sub     rsp, 50h
0x180003484  mov     qword ptr [r11-18h], 0
0x18000348c  lea     rax, [r11+18h]
0x180003490  mov     [r11-20h], rax
0x180003494  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000349b  mov     qword ptr [r11-28h], 0
0x1800034a3  mov     edi, ecx
0x1800034a5  mov     [rsp+58h+samDesired], 20006h; samDesired
0x1800034ad  xor     r9d, r9d; lpClass
0x1800034b0  xor     r8d, r8d; Reserved
0x1800034b3  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800034bb  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800034c2  mov     qword ptr [r11+18h], 0
0x1800034ca  mov     [rsp+58h+Data], 0
0x1800034d2  call    cs:__imp_RegCreateKeyExW
0x1800034d8  mov     ebx, eax
0x1800034da  test    eax, eax
0x1800034dc  jz      short loc_180003528
0x1800034de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034e5  lea     rax, WPP_GLOBAL_Control
0x1800034ec  cmp     rcx, rax
0x1800034ef  jz      short loc_180003512
0x1800034f1  test    byte ptr [rcx+1Ch], 1
0x1800034f5  jz      short loc_180003512
0x1800034f7  mov     edx, 14h
0x1800034fc  mov     rcx, [rcx+10h]
0x180003500  lea     r8, WPP_91e8665fb8f03560ae482285a745ac49_Traceguids
0x180003507  mov     r9d, 4005h
0x18000350d  call    WPP_SF_D
0x180003512  test    ebx, ebx
0x180003514  jle     loc_1800035EA
0x18000351a  movzx   ebx, bx
0x18000351d  or      ebx, 80070000h
0x180003523  jmp     loc_1800035EA
0x180003528  mov     rcx, [rsp+58h+hKey]; hKey
0x18000352d  lea     rax, [rsp+58h+Data]
0x180003532  mov     [rsp+58h+samDesired], 4; cbData
0x18000353a  lea     rdx, ValueName; "EnableStartupAppNotification"
0x180003541  mov     r9d, 4; dwType
0x180003547  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x18000354c  xor     r8d, r8d; Reserved
0x18000354f  call    cs:__imp_RegSetValueExW
0x180003555  mov     ebx, eax
0x180003557  test    eax, eax
0x180003559  jz      short loc_18000357B
0x18000355b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003562  lea     rax, WPP_GLOBAL_Control
0x180003569  cmp     rcx, rax
0x18000356c  jz      short loc_180003512
0x18000356e  test    byte ptr [rcx+1Ch], 1
0x180003572  jz      short loc_180003512
0x180003574  mov     edx, 15h
0x180003579  jmp     short loc_1800034FC
0x18000357b  mov     ecx, 1F4h; dwMilliseconds
0x180003580  call    cs:__imp_Sleep
0x180003586  mov     rcx, [rsp+58h+hKey]; hKey
0x18000358b  lea     rax, [rsp+58h+Data]
0x180003590  mov     [rsp+58h+samDesired], 4; cbData
0x180003598  lea     rdx, ValueName; "EnableStartupAppNotification"
0x18000359f  mov     r9d, 4; dwType
0x1800035a5  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1800035aa  xor     r8d, r8d; Reserved
0x1800035ad  mov     [rsp+58h+Data], edi
0x1800035b1  call    cs:__imp_RegSetValueExW
0x1800035b7  mov     ebx, eax
0x1800035b9  test    eax, eax
0x1800035bb  jz      short loc_1800035E8
0x1800035bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800035c4  lea     rax, WPP_GLOBAL_Control
0x1800035cb  cmp     rcx, rax
0x1800035ce  jz      loc_180003512
0x1800035d4  test    byte ptr [rcx+1Ch], 1
0x1800035d8  jz      loc_180003512
0x1800035de  mov     edx, 16h
0x1800035e3  jmp     loc_1800034FC
0x1800035e8  xor     ebx, ebx
0x1800035ea  mov     rcx, [rsp+58h+hKey]; hKey
0x1800035ef  test    rcx, rcx
0x1800035f2  jz      short loc_1800035FA
0x1800035f4  call    cs:__imp_RegCloseKey
0x1800035fa  mov     eax, ebx
0x1800035fc  mov     rbx, [rsp+58h+arg_0]
0x180003601  add     rsp, 50h
0x180003605  pop     rdi
0x180003606  retn
```
