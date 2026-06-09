# RegUtil::WaitForHive(ushort const *,ulong,void *,HKEY__ * *)

- ea: `0x140062b3c`
- end: `0x140062fb2`
- name: `?WaitForHive@RegUtil@@YAJPEBGKPEAXPEAPEAUHKEY__@@@Z`
- size: `1142`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, const unsigned __int16 *, unsigned int, void *, HKEY *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001edf0`

## callees

- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140062b3c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140062c7b`
- `ADVAPI32!RegOpenKeyExW` at `0x140062d06`
- `ADVAPI32!RegOpenKeyExW` at `0x140062c7b`
- `ADVAPI32!RegOpenKeyExW` at `0x140062d06`
- `ADVAPI32!RegCloseKey` at `0x140062f91`
- `ADVAPI32!RegCloseKey` at `0x140062f91`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140062ca7`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140062ca7`
- `KERNEL32!CloseHandle` at `0x140062f7e`
- `KERNEL32!CloseHandle` at `0x140062f7e`
- `KERNEL32!WaitForMultipleObjects` at `0x140062cc4`
- `KERNEL32!WaitForMultipleObjects` at `0x140062cc4`
- `KERNEL32!CreateEventW` at `0x140062b85`
- `KERNEL32!CreateEventW` at `0x140062b85`
- `KERNEL32!GetLastError` at `0x140062b97`
- `KERNEL32!GetLastError` at `0x140062de4`
- `KERNEL32!GetLastError` at `0x140062b97`
- `KERNEL32!GetLastError` at `0x140062de4`
- `KERNEL32!IsDebuggerPresent` at `0x140062bf2`
- `KERNEL32!IsDebuggerPresent` at `0x140062d60`
- `KERNEL32!IsDebuggerPresent` at `0x140062dd0`
- `KERNEL32!IsDebuggerPresent` at `0x140062e3f`
- `KERNEL32!IsDebuggerPresent` at `0x140062eda`
- `KERNEL32!IsDebuggerPresent` at `0x140062bf2`
- `KERNEL32!IsDebuggerPresent` at `0x140062d60`
- `KERNEL32!IsDebuggerPresent` at `0x140062dd0`
- `KERNEL32!IsDebuggerPresent` at `0x140062e3f`
- `KERNEL32!IsDebuggerPresent` at `0x140062eda`

## string_xrefs

- `0x140062bba`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x140062d42`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x140062db8`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x140062e14`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x140062e6c`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x140062ec2`: `termsrv\wms\src\common\srcutils\registry.cpp`
- `0x140062d8f`: `dwWait == ((((DWORD )0x00000000L) ) + 0 ) + EWH_REGISTRY_CHANGE`
- `0x140062dd8`: `dwWait == ((((DWORD )0x00000000L) ) + 0 ) + EWH_REGISTRY_CHANGE`
- `0x140062f53`: `RegUtil::WaitForHive - opened HKEY_USERS\%s\n`

## pseudocode

```c
__int64 __fastcall RegUtil::WaitForHive(LPCWSTR lpSubKey, const unsigned __int16 *a2, __int64 a3, HKEY *a4)
{
  HANDLE EventW; // r15
  signed int v7; // eax
  signed int v8; // ebx
  LSTATUS v9; // eax
  DWORD v10; // eax
  unsigned int v11; // r13d
  bool v12; // zf
  const unsigned __int16 *v13; // rax
  signed int LastError; // eax
  __int128 Handles; // [rsp+40h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+18h] BYREF

  hKey = 0;
  Handles = 0;
  DEBUGMSG(L"RegUtil::WaitForHive - waiting for HKEY_USERS\\%s\n", lpSubKey);
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    *(_QWORD *)&Handles = EventW;
    if ( RegOpenKeyExW(HKEY_USERS, lpSubKey, 0, 0x2001Fu, &hKey) == 2 )
    {
      while ( 1 )
      {
        v9 = RegNotifyChangeKeyValue(HKEY_USERS, 1, 1u, EventW, 1);
        v8 = v9;
        if ( v9 )
          break;
        v10 = WaitForMultipleObjects(1u, (const HANDLE *)&Handles, 0, 0xFFFFFFFF);
        if ( v10 == 1 )
        {
          v8 = -2147467260;
          DEBUGMSGLEVEL(
            4u,
            L"%s(%d) - %s - Test failed:  %s\n",
            L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
            719,
            L"RegUtil::WaitForHive",
            L"RegUtil::WaitForHive - exiting, hAbort was signalled\n");
          goto LABEL_33;
        }
        if ( v10 == -1 )
        {
          LastError = GetLastError();
          v8 = LastError;
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
          v11 = 720;
          if ( v8 >= 0 )
            v8 = -2147467259;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
            0x2D0u,
            L"RegUtil::WaitForHive",
            L"CBRAEx",
            L"dwWait != ((DWORD)0xFFFFFFFF)",
            v8);
          v12 = !IsDebuggerPresent();
          v13 = L"dwWait != ((DWORD)0xFFFFFFFF)";
          goto LABEL_28;
        }
        if ( v10 )
        {
          v8 = -2147418113;
          v11 = 721;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
            0x2D1u,
            L"RegUtil::WaitForHive",
            L"CBRAEx",
            L"dwWait == ((((DWORD )0x00000000L) ) + 0 ) + EWH_REGISTRY_CHANGE",
            -2147418113);
          v12 = !IsDebuggerPresent();
          v13 = L"dwWait == ((((DWORD )0x00000000L) ) + 0 ) + EWH_REGISTRY_CHANGE";
          goto LABEL_28;
        }
        if ( RegOpenKeyExW(HKEY_USERS, lpSubKey, 0, 0x2001Fu, &hKey) != 2 )
          goto LABEL_15;
      }
      if ( v9 > 0 )
        v8 = (unsigned __int16)v9 | 0x80070000;
      v11 = 716;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
        0x2CCu,
        L"RegUtil::WaitForHive",
        L"CBRAEx",
        L"lr == 0L",
        v8);
      v12 = !IsDebuggerPresent();
      v13 = L"lr == 0L";
LABEL_28:
      if ( v12 )
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
          v11,
          L"RegUtil::WaitForHive",
          L"CBRAEx",
          v13,
          v8);
      else
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
          v11,
          L"RegUtil::WaitForHive",
          L"CBRAEx",
          v13,
          v8,
          (_QWORD)Handles);
    }
    else
    {
LABEL_15:
      if ( hKey )
      {
        v8 = 0;
        DEBUGMSG(L"RegUtil::WaitForHive - opened HKEY_USERS\\%s\n", lpSubKey);
        *a4 = hKey;
        hKey = 0;
      }
      else
      {
        v8 = -2147467259;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
          0x2D4u,
          L"RegUtil::WaitForHive",
          L"CBRA",
          L"hKey",
          -2147467259);
        if ( IsDebuggerPresent() )
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
            724,
            L"RegUtil::WaitForHive",
            L"CBRA",
            L"hKey",
            -2147467259,
            (_QWORD)Handles);
        else
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
            L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
            724,
            L"RegUtil::WaitForHive",
            L"CBRA",
            L"hKey",
            -2147467259);
      }
    }
LABEL_33:
    if ( EventW != (HANDLE)-1LL )
      CloseHandle(EventW);
  }
  else
  {
    v7 = GetLastError();
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    if ( v8 >= 0 )
      v8 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
      0x2BAu,
      L"RegUtil::WaitForHive",
      L"CBRAEx",
      L"hRegNotifyEvent",
      v8);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
        698,
        L"RegUtil::WaitForHive",
        L"CBRAEx",
        L"hRegNotifyEvent",
        v8);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\registry.cpp",
        698,
        L"RegUtil::WaitForHive",
        L"CBRAEx",
        L"hRegNotifyEvent",
        v8);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140062b3c  mov     rax, rsp
0x140062b3f  mov     [rax+8], rbx
0x140062b43  mov     [rax+10h], rbp
0x140062b47  mov     [rax+18h], r8
0x140062b4b  push    rsi
0x140062b4c  push    rdi
0x140062b4d  push    r13
0x140062b4f  push    r14
0x140062b51  push    r15
0x140062b53  sub     rsp, 50h
0x140062b57  mov     rdi, rcx
0x140062b5a  mov     qword ptr [rax+18h], 0
0x140062b62  xorps   xmm0, xmm0
0x140062b65  mov     rdx, rcx
0x140062b68  lea     rcx, aRegutilWaitfor_1; "RegUtil::WaitForHive - waiting for HKEY"...
0x140062b6f  mov     rsi, r9
0x140062b72  movups  xmmword ptr [rax-38h], xmm0
0x140062b76  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140062b7b  xor     r9d, r9d; lpName
0x140062b7e  xor     r8d, r8d; bInitialState
0x140062b81  xor     edx, edx; bManualReset
0x140062b83  xor     ecx, ecx; lpEventAttributes
0x140062b85  call    cs:__imp_CreateEventW
0x140062b8b  mov     r15, rax
0x140062b8e  test    rax, rax
0x140062b91  jnz     loc_140062C53
0x140062b97  call    cs:__imp_GetLastError
0x140062b9d  mov     ebx, eax
0x140062b9f  test    eax, eax
0x140062ba1  jle     short loc_140062BAC
0x140062ba3  movzx   ebx, ax
0x140062ba6  or      ebx, 80070000h
0x140062bac  mov     ebp, 80004005h
0x140062bb1  lea     rsi, aRegutilWaitfor_0; "RegUtil::WaitForHive"
0x140062bb8  test    ebx, ebx
0x140062bba  lea     rdi, aTermsrvWmsSrcC_21; "termsrv\\wms\\src\\common\\srcutils\\re"...
0x140062bc1  mov     r14d, 2BAh
0x140062bc7  lea     r15, aHregnotifyeven; "hRegNotifyEvent"
0x140062bce  cmovns  ebx, ebp
0x140062bd1  mov     r8, rsi; unsigned __int16 *
0x140062bd4  lea     rbp, aCbraex; "CBRAEx"
0x140062bdb  mov     [rsp+78h+var_50], ebx; int
0x140062bdf  mov     r9, rbp; unsigned __int16 *
0x140062be2  mov     [rsp+78h+phkResult], r15; unsigned __int16 *
0x140062be7  mov     edx, r14d; unsigned int
0x140062bea  mov     rcx, rdi; unsigned __int16 *
0x140062bed  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140062bf2  call    cs:__imp_IsDebuggerPresent
0x140062bf8  test    eax, eax
0x140062bfa  jz      short loc_140062C2B
0x140062bfc  mov     [rsp+78h+var_40], ebx
0x140062c00  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140062c07  mov     [rsp+78h+var_48], r15
0x140062c0c  mov     r9d, r14d
0x140062c0f  mov     qword ptr [rsp+78h+var_50], rbp
0x140062c14  mov     r8, rdi
0x140062c17  mov     ecx, 2; unsigned __int8
0x140062c1c  mov     [rsp+78h+phkResult], rsi
0x140062c21  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140062c26  jmp     loc_140062F84
0x140062c2b  mov     dword ptr [rsp+78h+var_48], ebx
0x140062c2f  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140062c36  mov     qword ptr [rsp+78h+var_50], r15
0x140062c3b  mov     r9, rsi
0x140062c3e  mov     r8d, r14d
0x140062c41  mov     [rsp+78h+phkResult], rbp
0x140062c46  mov     rdx, rdi
0x140062c49  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140062c4e  jmp     loc_140062F84
0x140062c53  lea     rax, [rsp+78h+hKey]
0x140062c5b  mov     qword ptr [rsp+78h+Handles], r15
0x140062c60  mov     rbx, 0FFFFFFFF80000003h
0x140062c67  mov     [rsp+78h+phkResult], rax; phkResult
0x140062c6c  mov     rcx, rbx; hKey
0x140062c6f  mov     r9d, 2001Fh; samDesired
0x140062c75  xor     r8d, r8d; ulOptions
0x140062c78  mov     rdx, rdi; lpSubKey
0x140062c7b  call    cs:__imp_RegOpenKeyExW
0x140062c81  mov     r14d, 2
0x140062c87  cmp     eax, r14d
0x140062c8a  jnz     loc_140062D11
0x140062c90  lea     ebp, [r14-1]
0x140062c94  or      r13d, 0FFFFFFFFh
0x140062c98  mov     r9, r15; hEvent
0x140062c9b  mov     dword ptr [rsp+78h+phkResult], ebp; fAsynchronous
0x140062c9f  mov     r8d, ebp; dwNotifyFilter
0x140062ca2  mov     edx, ebp; bWatchSubtree
0x140062ca4  mov     rcx, rbx; hKey
0x140062ca7  call    cs:__imp_RegNotifyChangeKeyValue
0x140062cad  mov     ebx, eax
0x140062caf  test    eax, eax
0x140062cb1  jnz     loc_140062E93
0x140062cb7  mov     r9d, r13d; dwMilliseconds
0x140062cba  lea     rdx, [rsp+78h+Handles]; lpHandles
0x140062cbf  xor     r8d, r8d; bWaitAll
0x140062cc2  mov     ecx, ebp; nCount
0x140062cc4  call    cs:__imp_WaitForMultipleObjects
0x140062cca  cmp     eax, ebp
0x140062ccc  jz      loc_140062E53
0x140062cd2  cmp     eax, r13d
0x140062cd5  jz      loc_140062DE4
0x140062cdb  test    eax, eax
0x140062cdd  jnz     loc_140062D8F
0x140062ce3  lea     rax, [rsp+78h+hKey]
0x140062ceb  mov     rbx, 0FFFFFFFF80000003h
0x140062cf2  mov     rcx, rbx; hKey
0x140062cf5  mov     [rsp+78h+phkResult], rax; phkResult
0x140062cfa  mov     r9d, 2001Fh; samDesired
0x140062d00  xor     r8d, r8d; ulOptions
0x140062d03  mov     rdx, rdi; lpSubKey
0x140062d06  call    cs:__imp_RegOpenKeyExW
0x140062d0c  cmp     eax, r14d
0x140062d0f  jz      short loc_140062C98
0x140062d11  cmp     [rsp+78h+hKey], 0
0x140062d1a  jnz     loc_140062F51
0x140062d20  mov     ebp, 80004005h
0x140062d25  lea     rax, aHkey; "hKey"
0x140062d2c  lea     rsi, aRegutilWaitfor_0; "RegUtil::WaitForHive"
0x140062d33  mov     [rsp+78h+var_50], ebp; int
0x140062d37  mov     r13d, 2D4h
0x140062d3d  mov     [rsp+78h+phkResult], rax; unsigned __int16 *
0x140062d42  lea     rdi, aTermsrvWmsSrcC_21; "termsrv\\wms\\src\\common\\srcutils\\re"...
0x140062d49  mov     r8, rsi; unsigned __int16 *
0x140062d4c  mov     edx, r13d; unsigned int
0x140062d4f  lea     r9, aCbra; "CBRA"
0x140062d56  mov     rcx, rdi; unsigned __int16 *
0x140062d59  mov     ebx, ebp
0x140062d5b  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140062d60  call    cs:__imp_IsDebuggerPresent
0x140062d66  test    eax, eax
0x140062d68  lea     rax, aHkey; "hKey"
0x140062d6f  jz      loc_140062F3A
0x140062d75  mov     [rsp+78h+var_40], ebp
0x140062d79  mov     [rsp+78h+var_48], rax
0x140062d7e  lea     rax, aCbra; "CBRA"
0x140062d85  mov     qword ptr [rsp+78h+var_50], rax
0x140062d8a  jmp     loc_140062EF9
0x140062d8f  lea     rax, aDwwaitDword0x0_0; "dwWait == ((((DWORD )0x00000000L) ) + 0"...
0x140062d96  mov     ebx, 8000FFFFh
0x140062d9b  lea     rbp, aCbraex; "CBRAEx"
0x140062da2  mov     [rsp+78h+var_50], ebx; int
0x140062da6  lea     rsi, aRegutilWaitfor_0; "RegUtil::WaitForHive"
0x140062dad  mov     [rsp+78h+phkResult], rax; unsigned __int16 *
0x140062db2  mov     r13d, 2D1h
0x140062db8  lea     rdi, aTermsrvWmsSrcC_21; "termsrv\\wms\\src\\common\\srcutils\\re"...
0x140062dbf  mov     r9, rbp; unsigned __int16 *
0x140062dc2  mov     r8, rsi; unsigned __int16 *
0x140062dc5  mov     edx, r13d; unsigned int
0x140062dc8  mov     rcx, rdi; unsigned __int16 *
0x140062dcb  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140062dd0  call    cs:__imp_IsDebuggerPresent
0x140062dd6  test    eax, eax
0x140062dd8  lea     rax, aDwwaitDword0x0_0; "dwWait == ((((DWORD )0x00000000L) ) + 0"...
0x140062ddf  jmp     loc_140062EE9
0x140062de4  call    cs:__imp_GetLastError
0x140062dea  mov     ebx, eax
0x140062dec  test    eax, eax
0x140062dee  jle     short loc_140062DF9
0x140062df0  movzx   ebx, ax
0x140062df3  or      ebx, 80070000h
0x140062df9  mov     ebp, 80004005h
0x140062dfe  lea     rax, aDwwaitDword0xf; "dwWait != ((DWORD)0xFFFFFFFF)"
0x140062e05  test    ebx, ebx
0x140062e07  lea     rsi, aRegutilWaitfor_0; "RegUtil::WaitForHive"
0x140062e0e  mov     r13d, 2D0h
0x140062e14  lea     rdi, aTermsrvWmsSrcC_21; "termsrv\\wms\\src\\common\\srcutils\\re"...
0x140062e1b  cmovns  ebx, ebp
0x140062e1e  mov     r8, rsi; unsigned __int16 *
0x140062e21  lea     rbp, aCbraex; "CBRAEx"
0x140062e28  mov     [rsp+78h+var_50], ebx; int
0x140062e2c  mov     r9, rbp; unsigned __int16 *
0x140062e2f  mov     [rsp+78h+phkResult], rax; unsigned __int16 *
0x140062e34  mov     edx, r13d; unsigned int
0x140062e37  mov     rcx, rdi; unsigned __int16 *
0x140062e3a  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140062e3f  call    cs:__imp_IsDebuggerPresent
0x140062e45  test    eax, eax
0x140062e47  lea     rax, aDwwaitDword0xf; "dwWait != ((DWORD)0xFFFFFFFF)"
0x140062e4e  jmp     loc_140062EE9
0x140062e53  lea     rax, aRegutilWaitfor_2; "RegUtil::WaitForHive - exiting, hAbort "...
0x140062e5a  mov     r9d, 2CFh
0x140062e60  mov     qword ptr [rsp+78h+var_50], rax
0x140062e65  lea     rsi, aRegutilWaitfor_0; "RegUtil::WaitForHive"
0x140062e6c  lea     r8, aTermsrvWmsSrcC_21; "termsrv\\wms\\src\\common\\srcutils\\re"...
0x140062e73  mov     [rsp+78h+phkResult], rsi
0x140062e78  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x140062e7f  mov     ecx, 4; unsigned __int8
0x140062e84  mov     ebx, 80004004h
0x140062e89  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140062e8e  jmp     loc_140062F75
0x140062e93  jle     short loc_140062E9E
0x140062e95  movzx   ebx, ax
0x140062e98  or      ebx, 80070000h
0x140062e9e  lea     rax, aLr0l; "lr == 0L"
0x140062ea5  mov     [rsp+78h+var_50], ebx; int
0x140062ea9  lea     rbp, aCbraex; "CBRAEx"
0x140062eb0  mov     [rsp+78h+phkResult], rax; unsigned __int16 *
0x140062eb5  lea     rsi, aRegutilWaitfor_0; "RegUtil::WaitForHive"
0x140062ebc  mov     r13d, 2CCh
0x140062ec2  lea     rdi, aTermsrvWmsSrcC_21; "termsrv\\wms\\src\\common\\srcutils\\re"...
0x140062ec9  mov     r9, rbp; unsigned __int16 *
0x140062ecc  mov     r8, rsi; unsigned __int16 *
0x140062ecf  mov     edx, r13d; unsigned int
0x140062ed2  mov     rcx, rdi; unsigned __int16 *
0x140062ed5  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140062eda  call    cs:__imp_IsDebuggerPresent
0x140062ee0  test    eax, eax
0x140062ee2  lea     rax, aLr0l; "lr == 0L"
0x140062ee9  jz      short loc_140062F15
0x140062eeb  mov     [rsp+78h+var_40], ebx
0x140062eef  mov     [rsp+78h+var_48], rax
0x140062ef4  mov     qword ptr [rsp+78h+var_50], rbp
0x140062ef9  mov     r9d, r13d
0x140062efc  mov     [rsp+78h+phkResult], rsi
0x140062f01  mov     r8, rdi
0x140062f04  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140062f0b  mov     ecx, r14d; unsigned __int8
0x140062f0e  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140062f13  jmp     short loc_140062F75
0x140062f15  mov     dword ptr [rsp+78h+var_48], ebx
0x140062f19  mov     qword ptr [rsp+78h+var_50], rax
0x140062f1e  mov     [rsp+78h+phkResult], rbp
0x140062f23  mov     r9, rsi
0x140062f26  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140062f2d  mov     r8d, r13d
0x140062f30  mov     rdx, rdi
0x140062f33  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140062f38  jmp     short loc_140062F75
0x140062f3a  mov     dword ptr [rsp+78h+var_48], ebp
0x140062f3e  mov     qword ptr [rsp+78h+var_50], rax
0x140062f43  lea     rax, aCbra; "CBRA"
0x140062f4a  mov     [rsp+78h+phkResult], rax
0x140062f4f  jmp     short loc_140062F23
0x140062f51  xor     ebx, ebx
0x140062f53  lea     rcx, aRegutilWaitfor; "RegUtil::WaitForHive - opened HKEY_USER"...
0x140062f5a  mov     rdx, rdi
0x140062f5d  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140062f62  mov     rax, [rsp+78h+hKey]
0x140062f6a  mov     [rsi], rax
0x140062f6d  mov     [rsp+78h+hKey], rbx
0x140062f75  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x140062f79  jz      short loc_140062F84
0x140062f7b  mov     rcx, r15; hObject
0x140062f7e  call    cs:__imp_CloseHandle
0x140062f84  mov     rcx, [rsp+78h+hKey]; hKey
0x140062f8c  test    rcx, rcx
0x140062f8f  jz      short loc_140062F97
0x140062f91  call    cs:__imp_RegCloseKey
0x140062f97  lea     r11, [rsp+78h+var_28]
0x140062f9c  mov     eax, ebx
0x140062f9e  mov     rbx, [r11+30h]
0x140062fa2  mov     rbp, [r11+38h]
0x140062fa6  mov     rsp, r11
0x140062fa9  pop     r15
0x140062fab  pop     r14
0x140062fad  pop     r13
0x140062faf  pop     rdi
0x140062fb0  pop     rsi
0x140062fb1  retn
```
