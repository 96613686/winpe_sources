# NotificationPlatform::DeleteMMF(void)

- ea: `0x1800cb030`
- end: `0x1800cb2e5`
- name: `?DeleteMMF@NotificationPlatform@@AEAAJXZ`
- size: `693`
- prototype: `__int64 __fastcall(NotificationPlatform *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x18007c1f4`

## callees

- `0x18002ee38`
- `0x1800516d0`
- `0x1800af0a4`
- `0x1800b99f0`
- `0x1800cb030`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb095`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb163`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb095`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cb163`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800cb159`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800cb159`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cb1ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cb1ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cb2b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cb2b8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800cb24c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800cb24c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800cb081`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800cb081`

## pseudocode

```c
__int64 __fastcall NotificationPlatform::DeleteMMF(NotificationPlatform *this)
{
  const WCHAR *v2; // rax
  signed int LastError; // eax
  signed int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  int v7; // eax
  signed int v8; // eax
  const WCHAR *v9; // rax
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  int phkResult; // [rsp+20h] [rbp-248h]
  int phkResulta; // [rsp+20h] [rbp-248h]
  HKEY hKey; // [rsp+30h] [rbp-238h] BYREF
  WCHAR Dst[264]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  hKey = 0;
  v2 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 40LL))(*((_QWORD *)this + 42));
  if ( ExpandEnvironmentStringsW(v2, Dst, 0x104u) - 1 <= 0x103 )
    goto LABEL_8;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( v4 >= 0 )
  {
LABEL_8:
    v7 = StringCchCatW(Dst, 0x104u, L"\\appdb.dat");
    v4 = v7;
    if ( v7 >= 0 )
    {
      if ( DeleteFileW(Dst) )
        goto LABEL_19;
      v8 = GetLastError();
      v4 = v8;
      if ( v8 > 0 )
        v4 = (unsigned __int16)v8 | 0x80070000;
      if ( v4 >= 0 )
      {
LABEL_19:
        v9 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 24LL))(*((_QWORD *)this + 42));
        v10 = RegOpenKeyExW(HKEY_CURRENT_USER, v9, 0, 0xF003Fu, &hKey);
        v4 = v10;
        if ( v10 > 0 )
          v4 = (unsigned __int16)v10 | 0x80070000;
        if ( v4 >= 0 )
        {
          v11 = RegDeleteValueW(hKey, L"AppDB");
          v4 = v11;
          if ( v11 > 0 )
            v4 = (unsigned __int16)v11 | 0x80070000;
          if ( v4 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x2C0,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
              (const char *)(unsigned int)v4,
              phkResulta);
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
            {
              v6 = 16;
              goto LABEL_31;
            }
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x2BC,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
            (const char *)(unsigned int)v4,
            phkResulta);
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v6 = 15;
            goto LABEL_31;
          }
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2B0,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
          (const char *)(unsigned int)v4,
          phkResult);
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v6 = 14;
          goto LABEL_31;
        }
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2AA,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
        (const char *)(unsigned int)v7,
        phkResult);
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v6 = 13;
        goto LABEL_31;
      }
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2A3,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\platform.cpp",
      (const char *)(unsigned int)v4,
      phkResult);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v6 = 12;
LABEL_31:
      WPP_SF_d(v5[2], v6, WPP_b132aec85c7a33d18315e66004c9e479_Traceguids, (unsigned int)v4);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800cb030  mov     [rsp+arg_8], rbx
0x1800cb035  mov     [rsp+arg_10], rsi
0x1800cb03a  push    rdi
0x1800cb03b  sub     rsp, 260h
0x1800cb042  mov     rax, cs:__security_cookie
0x1800cb049  xor     rax, rsp
0x1800cb04c  mov     [rsp+268h+var_18], rax
0x1800cb054  mov     rdi, rcx
0x1800cb057  mov     [rsp+268h+hKey], 0
0x1800cb060  mov     rcx, [rcx+150h]
0x1800cb067  mov     rax, [rcx]
0x1800cb06a  mov     rax, [rax+28h]
0x1800cb06e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb073  mov     rcx, rax; lpSrc
0x1800cb076  lea     rdx, [rsp+268h+Dst]; lpDst
0x1800cb07b  mov     r8d, 104h; nSize
0x1800cb081  call    cs:__imp_ExpandEnvironmentStringsW
0x1800cb087  dec     eax
0x1800cb089  mov     esi, 80070000h
0x1800cb08e  cmp     eax, 103h
0x1800cb093  jbe     short loc_1800CB0F1
0x1800cb095  call    cs:__imp_GetLastError
0x1800cb09b  mov     ebx, eax
0x1800cb09d  test    eax, eax
0x1800cb09f  jle     short loc_1800CB0A6
0x1800cb0a1  movzx   ebx, ax
0x1800cb0a4  or      ebx, esi
0x1800cb0a6  test    ebx, ebx
0x1800cb0a8  jns     short loc_1800CB0F1
0x1800cb0aa  mov     rcx, [rsp+268h]; this
0x1800cb0b2  lea     r8, aOnecoreuapBase_161; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800cb0b9  mov     r9d, ebx; char *
0x1800cb0bc  mov     edx, 2A3h; void *
0x1800cb0c1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cb0c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb0cd  lea     rax, WPP_GLOBAL_Control
0x1800cb0d4  cmp     rcx, rax
0x1800cb0d7  jz      loc_1800CB2AE
0x1800cb0dd  test    byte ptr [rcx+1Ch], 80h
0x1800cb0e1  jz      loc_1800CB2AE
0x1800cb0e7  mov     edx, 0Ch
0x1800cb0ec  jmp     loc_1800CB29B
0x1800cb0f1  lea     r8, aAppdbDat; "\\appdb.dat"
0x1800cb0f8  mov     edx, 104h; unsigned __int64
0x1800cb0fd  lea     rcx, [rsp+268h+Dst]; unsigned __int16 *
0x1800cb102  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800cb107  mov     ebx, eax
0x1800cb109  test    eax, eax
0x1800cb10b  jns     short loc_1800CB154
0x1800cb10d  mov     rcx, [rsp+268h]; this
0x1800cb115  lea     r8, aOnecoreuapBase_161; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800cb11c  mov     r9d, eax; char *
0x1800cb11f  mov     edx, 2AAh; void *
0x1800cb124  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cb129  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb130  lea     rax, WPP_GLOBAL_Control
0x1800cb137  cmp     rcx, rax
0x1800cb13a  jz      loc_1800CB2AE
0x1800cb140  test    byte ptr [rcx+1Ch], 80h
0x1800cb144  jz      loc_1800CB2AE
0x1800cb14a  mov     edx, 0Dh
0x1800cb14f  jmp     loc_1800CB29B
0x1800cb154  lea     rcx, [rsp+268h+Dst]; lpFileName
0x1800cb159  call    cs:__imp_DeleteFileW
0x1800cb15f  test    eax, eax
0x1800cb161  jnz     short loc_1800CB1BF
0x1800cb163  call    cs:__imp_GetLastError
0x1800cb169  mov     ebx, eax
0x1800cb16b  test    eax, eax
0x1800cb16d  jle     short loc_1800CB174
0x1800cb16f  movzx   ebx, ax
0x1800cb172  or      ebx, esi
0x1800cb174  test    ebx, ebx
0x1800cb176  jns     short loc_1800CB1BF
0x1800cb178  mov     rcx, [rsp+268h]; this
0x1800cb180  lea     r8, aOnecoreuapBase_161; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800cb187  mov     r9d, ebx; char *
0x1800cb18a  mov     edx, 2B0h; void *
0x1800cb18f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cb194  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb19b  lea     rax, WPP_GLOBAL_Control
0x1800cb1a2  cmp     rcx, rax
0x1800cb1a5  jz      loc_1800CB2AE
0x1800cb1ab  test    byte ptr [rcx+1Ch], 80h
0x1800cb1af  jz      loc_1800CB2AE
0x1800cb1b5  mov     edx, 0Eh
0x1800cb1ba  jmp     loc_1800CB29B
0x1800cb1bf  mov     rcx, [rdi+150h]
0x1800cb1c6  mov     rax, [rcx]
0x1800cb1c9  mov     rax, [rax+18h]
0x1800cb1cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb1d2  mov     rdx, rax; lpSubKey
0x1800cb1d5  mov     r9d, 0F003Fh; samDesired
0x1800cb1db  lea     rax, [rsp+268h+hKey]
0x1800cb1e0  xor     r8d, r8d; ulOptions
0x1800cb1e3  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800cb1ea  mov     qword ptr [rsp+268h+phkResult], rax; int
0x1800cb1ef  call    cs:__imp_RegOpenKeyExW
0x1800cb1f5  mov     ebx, eax
0x1800cb1f7  test    eax, eax
0x1800cb1f9  jle     short loc_1800CB200
0x1800cb1fb  movzx   ebx, ax
0x1800cb1fe  or      ebx, esi
0x1800cb200  test    ebx, ebx
0x1800cb202  jns     short loc_1800CB240
0x1800cb204  mov     rcx, [rsp+268h]; this
0x1800cb20c  lea     r8, aOnecoreuapBase_161; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800cb213  mov     r9d, ebx; char *
0x1800cb216  mov     edx, 2BCh; void *
0x1800cb21b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cb220  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb227  lea     rax, WPP_GLOBAL_Control
0x1800cb22e  cmp     rcx, rax
0x1800cb231  jz      short loc_1800CB2AE
0x1800cb233  test    byte ptr [rcx+1Ch], 80h
0x1800cb237  jz      short loc_1800CB2AE
0x1800cb239  mov     edx, 0Fh
0x1800cb23e  jmp     short loc_1800CB29B
0x1800cb240  mov     rcx, [rsp+268h+hKey]; hKey
0x1800cb245  lea     rdx, aAppdb; "AppDB"
0x1800cb24c  call    cs:__imp_RegDeleteValueW
0x1800cb252  mov     ebx, eax
0x1800cb254  test    eax, eax
0x1800cb256  jle     short loc_1800CB25D
0x1800cb258  movzx   ebx, ax
0x1800cb25b  or      ebx, esi
0x1800cb25d  test    ebx, ebx
0x1800cb25f  jns     short loc_1800CB2AE
0x1800cb261  mov     rcx, [rsp+268h]; this
0x1800cb269  lea     r8, aOnecoreuapBase_161; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800cb270  mov     r9d, ebx; char *
0x1800cb273  mov     edx, 2C0h; void *
0x1800cb278  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cb27d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb284  lea     rax, WPP_GLOBAL_Control
0x1800cb28b  cmp     rcx, rax
0x1800cb28e  jz      short loc_1800CB2AE
0x1800cb290  test    byte ptr [rcx+1Ch], 80h
0x1800cb294  jz      short loc_1800CB2AE
0x1800cb296  mov     edx, 10h
0x1800cb29b  mov     rcx, [rcx+10h]
0x1800cb29f  lea     r8, WPP_b132aec85c7a33d18315e66004c9e479_Traceguids
0x1800cb2a6  mov     r9d, ebx
0x1800cb2a9  call    WPP_SF_d
0x1800cb2ae  mov     rcx, [rsp+268h+hKey]; hKey
0x1800cb2b3  test    rcx, rcx
0x1800cb2b6  jz      short loc_1800CB2BE
0x1800cb2b8  call    cs:__imp_RegCloseKey
0x1800cb2be  mov     eax, ebx
0x1800cb2c0  mov     rcx, [rsp+268h+var_18]
0x1800cb2c8  xor     rcx, rsp; StackCookie
0x1800cb2cb  call    __security_check_cookie
0x1800cb2d0  lea     r11, [rsp+268h+var_8]
0x1800cb2d8  mov     rbx, [r11+18h]
0x1800cb2dc  mov     rsi, [r11+20h]
0x1800cb2e0  mov     rsp, r11
0x1800cb2e3  pop     rdi
0x1800cb2e4  retn
```
