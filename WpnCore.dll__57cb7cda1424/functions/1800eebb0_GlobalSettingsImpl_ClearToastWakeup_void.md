# GlobalSettingsImpl::ClearToastWakeup(void)

- ea: `0x1800eebb0`
- end: `0x1800eed04`
- name: `?ClearToastWakeup@GlobalSettingsImpl@@UEAAXXZ`
- size: `340`
- prototype: `void __fastcall(GlobalSettingsImpl *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18002ee38`
- `0x18006db94`
- `0x1800af0a4`
- `0x1800eebb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800eebe1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800eebe1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eece3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eece3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eec1f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eec1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eecf3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800eecf3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800eec7d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800eec7d`

## pseudocode

```c
void __fastcall GlobalSettingsImpl::ClearToastWakeup(NotificationPlatform **this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  LSTATUS v3; // eax
  signed int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  LSTATUS v7; // eax
  int phkResult; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  if ( !(unsigned int)NotificationPlatform::CheckPrivilege(this[34]) )
    goto LABEL_17;
  v2 = (struct _RTL_CRITICAL_SECTION *)(this + 1);
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 1));
  if ( *((_DWORD *)this + 65) )
  {
    *((_DWORD *)this + 65) = 0;
    v3 = RegOpenKeyExW(
           HKEY_CURRENT_USER,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\PushNotifications",
           0,
           0x20019u,
           &hKey);
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    if ( v4 >= 0 )
    {
      v7 = RegDeleteValueW(hKey, L"ToastWakeupTime");
      v4 = v7;
      if ( v7 > 0 )
        v4 = (unsigned __int16)v7 | 0x80070000;
      if ( v4 >= 0 )
        goto LABEL_16;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5ED,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\settings\\globalsettingsimpl.cpp",
        (const char *)(unsigned int)v4,
        phkResult);
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_16;
      v6 = 43;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5E8,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\settings\\globalsettingsimpl.cpp",
        (const char *)(unsigned int)v4,
        phkResult);
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_16;
      v6 = 42;
    }
    WPP_SF_d(v5[2], v6, WPP_d4570d0b4e21373141bb2483f6e88313_Traceguids, (unsigned int)v4);
  }
LABEL_16:
  LeaveCriticalSection(v2);
LABEL_17:
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x1800eebb0  mov     [rsp+arg_8], rbx
0x1800eebb5  push    rdi
0x1800eebb6  sub     rsp, 30h
0x1800eebba  mov     rbx, rcx
0x1800eebbd  mov     [rsp+38h+hKey], 0
0x1800eebc6  mov     rcx, [rcx+110h]; this
0x1800eebcd  call    ?CheckPrivilege@NotificationPlatform@@QEAAHXZ; NotificationPlatform::CheckPrivilege(void)
0x1800eebd2  test    eax, eax
0x1800eebd4  jz      loc_1800EECE9
0x1800eebda  lea     rdi, [rbx+8]
0x1800eebde  mov     rcx, rdi; lpCriticalSection
0x1800eebe1  call    cs:__imp_EnterCriticalSection
0x1800eebe7  cmp     dword ptr [rbx+104h], 0
0x1800eebee  jz      loc_1800EECE0
0x1800eebf4  mov     rdx, cs:lpSubKey; lpSubKey
0x1800eebfb  lea     rax, [rsp+38h+hKey]
0x1800eec00  mov     r9d, 20019h; samDesired
0x1800eec06  mov     qword ptr [rsp+38h+phkResult], rax; int
0x1800eec0b  xor     r8d, r8d; ulOptions
0x1800eec0e  mov     dword ptr [rbx+104h], 0
0x1800eec18  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800eec1f  call    cs:__imp_RegOpenKeyExW
0x1800eec25  mov     ebx, eax
0x1800eec27  test    eax, eax
0x1800eec29  jle     short loc_1800EEC34
0x1800eec2b  movzx   ebx, ax
0x1800eec2e  or      ebx, 80070000h
0x1800eec34  test    ebx, ebx
0x1800eec36  jns     short loc_1800EEC71
0x1800eec38  mov     rcx, [rsp+38h]; this
0x1800eec3d  lea     r8, aOnecoreuapBase_33; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800eec44  mov     r9d, ebx; char *
0x1800eec47  mov     edx, 5E8h; void *
0x1800eec4c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800eec51  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eec58  lea     rax, WPP_GLOBAL_Control
0x1800eec5f  cmp     rcx, rax
0x1800eec62  jz      short loc_1800EECE0
0x1800eec64  test    byte ptr [rcx+1Ch], 80h
0x1800eec68  jz      short loc_1800EECE0
0x1800eec6a  mov     edx, 2Ah ; '*'
0x1800eec6f  jmp     short loc_1800EECCD
0x1800eec71  mov     rcx, [rsp+38h+hKey]; hKey
0x1800eec76  lea     rdx, aToastwakeuptim; "ToastWakeupTime"
0x1800eec7d  call    cs:__imp_RegDeleteValueW
0x1800eec83  mov     ebx, eax
0x1800eec85  test    eax, eax
0x1800eec87  jle     short loc_1800EEC92
0x1800eec89  movzx   ebx, ax
0x1800eec8c  or      ebx, 80070000h
0x1800eec92  test    ebx, ebx
0x1800eec94  jns     short loc_1800EECE0
0x1800eec96  mov     rcx, [rsp+38h]; this
0x1800eec9b  lea     r8, aOnecoreuapBase_33; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800eeca2  mov     r9d, ebx; char *
0x1800eeca5  mov     edx, 5EDh; void *
0x1800eecaa  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800eecaf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800eecb6  lea     rax, WPP_GLOBAL_Control
0x1800eecbd  cmp     rcx, rax
0x1800eecc0  jz      short loc_1800EECE0
0x1800eecc2  test    byte ptr [rcx+1Ch], 80h
0x1800eecc6  jz      short loc_1800EECE0
0x1800eecc8  mov     edx, 2Bh ; '+'
0x1800eeccd  mov     rcx, [rcx+10h]
0x1800eecd1  lea     r8, WPP_d4570d0b4e21373141bb2483f6e88313_Traceguids
0x1800eecd8  mov     r9d, ebx
0x1800eecdb  call    WPP_SF_d
0x1800eece0  mov     rcx, rdi; lpCriticalSection
0x1800eece3  call    cs:__imp_LeaveCriticalSection
0x1800eece9  mov     rcx, [rsp+38h+hKey]; hKey
0x1800eecee  test    rcx, rcx
0x1800eecf1  jz      short loc_1800EECF9
0x1800eecf3  call    cs:__imp_RegCloseKey
0x1800eecf9  mov     rbx, [rsp+38h+arg_8]
0x1800eecfe  add     rsp, 30h
0x1800eed02  pop     rdi
0x1800eed03  retn
```
