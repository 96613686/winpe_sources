# EfsSsopGetMyDocumentsPath(_EFS_USER_INFO *,ulong,ushort *)

- ea: `0x18002710c`
- end: `0x1800273a7`
- name: `?EfsSsopGetMyDocumentsPath@@YAKPEAU_EFS_USER_INFO@@KPEAG@Z`
- size: `667`
- prototype: `unsigned int(struct _EFS_USER_INFO *, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180026da4`

## callees

- `0x180004ca8`
- `0x180005045`
- `0x18000b884`
- `0x18002710c`
- `0x180063698`
- `0x18006389c`
- `0x1800dca3c`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027292`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800272c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027292`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800272c5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180027288`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180027288`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180027271`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180027271`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027377`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027377`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027357`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027367`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027357`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027367`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180027237`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180027237`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027193`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800271ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027193`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800271ea`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x1800272b7`
- `USERENV!ExpandEnvironmentStringsForUserW` at `0x1800272b7`

## pseudocode

```c
__int64 __fastcall EfsSsopGetMyDocumentsPath(LPCWSTR *a1, __int64 a2, unsigned __int16 *a3)
{
  int ValueW; // eax
  unsigned int v6; // edi
  char v7; // si
  int v8; // eax
  unsigned __int64 v9; // rcx
  bool v10; // zf
  HANDLE CurrentThread; // rax
  int v12; // ecx
  DWORD pdwType; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Src[264]; // [rsp+60h] [rbp-A0h] BYREF

  pcbData = 0;
  pdwType = 0;
  TokenHandle = 0;
  hkey = 0;
  hKey = 0;
  memset_0(a3, 0, 0x1001u);
  ValueW = RegOpenKeyExW(HKEY_USERS, a1[3], 0, 0x80000000, &hKey);
  v6 = ValueW;
  if ( ValueW )
  {
    v7 = 35;
  }
  else
  {
    ValueW = RegOpenKeyExW(
               hKey,
               L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\User Shell Folders",
               0,
               0x80000000,
               &hkey);
    v6 = ValueW;
    if ( ValueW )
    {
      v7 = 44;
    }
    else
    {
      pcbData = 261;
      ValueW = RegGetValueW(hkey, 0, L"Personal", 0x10000006u, &pdwType, Src, &pcbData);
      v6 = ValueW;
      if ( ValueW )
      {
        v7 = 58;
      }
      else
      {
        v9 = 2LL * (pcbData - 1);
        if ( v9 >= 0x20A )
          _report_rangecheckfailure();
        v10 = pdwType == 2;
        Src[pcbData - 1] = 0;
        if ( v10 )
        {
          CurrentThread = GetCurrentThread();
          if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
          {
            if ( ExpandEnvironmentStringsForUserW(TokenHandle, Src, a3, 0x1001u) )
              goto LABEL_19;
            ValueW = GetLastError();
            v6 = ValueW;
            v7 = 86;
          }
          else
          {
            ValueW = GetLastError();
            v6 = ValueW;
            v7 = 76;
          }
        }
        else
        {
          if ( pdwType != 1 )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs(v9);
            v6 = 1015;
            v7 = 102;
            v8 = fnEfsLogTrace2(v12, (unsigned int)EFS_API_ERROR_1, 1015, pdwType, 7, 102);
            goto LABEL_18;
          }
          ValueW = StringCchCopyW(a3, 0x1001u, Src);
          if ( ValueW >= 0 )
            goto LABEL_19;
          v6 = ValueW;
          v7 = 95;
        }
      }
    }
  }
  v8 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, ValueW, 7, v7);
LABEL_18:
  fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v8, 7, v7);
LABEL_19:
  if ( hkey )
    RegCloseKey(hkey);
  if ( hKey )
    RegCloseKey(hKey);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v6;
}

```

## disassembly

```asm
0x18002710c  mov     [rsp-8+arg_8], rbx
0x180027111  push    rbp
0x180027112  push    rsi
0x180027113  push    rdi
0x180027114  lea     rbp, [rsp-180h]
0x18002711c  sub     rsp, 280h
0x180027123  mov     rax, cs:__security_cookie
0x18002712a  xor     rax, rsp
0x18002712d  mov     [rbp+190h+var_20], rax
0x180027134  mov     rsi, r8
0x180027137  mov     [rsp+290h+var_24C], 0
0x18002713f  mov     rbx, rcx
0x180027142  mov     [rsp+290h+pdwType], 0
0x18002714a  mov     rcx, rsi; void *
0x18002714d  mov     [rsp+290h+TokenHandle], 0
0x180027156  xor     edx, edx; Val
0x180027158  mov     [rsp+290h+hkey], 0
0x180027161  mov     r8d, 1001h; Size
0x180027167  mov     [rsp+290h+hKey], 0
0x180027170  call    memset_0
0x180027175  mov     rdx, [rbx+18h]; lpSubKey
0x180027179  lea     rax, [rsp+290h+hKey]
0x18002717e  mov     r9d, 80000000h; samDesired
0x180027184  mov     [rsp+290h+phkResult], rax; phkResult
0x180027189  xor     r8d, r8d; ulOptions
0x18002718c  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180027193  call    cs:__imp_RegOpenKeyExW
0x180027199  mov     edi, eax
0x18002719b  test    eax, eax
0x18002719d  jz      short loc_1800271CB
0x18002719f  mov     esi, 523h
0x1800271a4  mov     rcx, cs:g_hPublisher
0x1800271ab  lea     rdx, EFS_API_ERROR
0x1800271b2  mov     ebx, 7
0x1800271b7  mov     dword ptr [rsp+290h+phkResult], esi
0x1800271bb  mov     r9d, ebx
0x1800271be  mov     r8d, eax
0x1800271c1  call    fnEfsLogTrace1
0x1800271c6  jmp     loc_180027330
0x1800271cb  mov     rcx, [rsp+290h+hKey]; hKey
0x1800271d0  lea     rax, [rsp+290h+hkey]
0x1800271d5  mov     r9d, 80000000h; samDesired
0x1800271db  mov     [rsp+290h+phkResult], rax; phkResult
0x1800271e0  xor     r8d, r8d; ulOptions
0x1800271e3  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800271ea  call    cs:__imp_RegOpenKeyExW
0x1800271f0  mov     edi, eax
0x1800271f2  test    eax, eax
0x1800271f4  jz      short loc_1800271FD
0x1800271f6  mov     esi, 52Ch
0x1800271fb  jmp     short loc_1800271A4
0x1800271fd  mov     rcx, [rsp+290h+hkey]; hkey
0x180027202  lea     rax, [rsp+290h+var_24C]
0x180027207  mov     [rsp+290h+pcbData], rax; pcbData
0x18002720c  lea     r8, aPersonal; "Personal"
0x180027213  lea     rax, [rsp+290h+Src]
0x180027218  mov     [rsp+290h+var_24C], 105h
0x180027220  mov     [rsp+290h+pvData], rax; pvData
0x180027225  mov     r9d, 10000006h; dwFlags
0x18002722b  lea     rax, [rsp+290h+pdwType]
0x180027230  xor     edx, edx; lpSubKey
0x180027232  mov     [rsp+290h+phkResult], rax; pdwType
0x180027237  call    cs:__imp_RegGetValueW
0x18002723d  mov     edi, eax
0x18002723f  test    eax, eax
0x180027241  jz      short loc_18002724D
0x180027243  mov     esi, 53Ah
0x180027248  jmp     loc_1800271A4
0x18002724d  mov     ecx, [rsp+290h+var_24C]
0x180027251  dec     ecx
0x180027253  add     rcx, rcx
0x180027256  cmp     rcx, 20Ah
0x18002725d  jnb     loc_1800273A1
0x180027263  xor     eax, eax
0x180027265  cmp     [rsp+290h+pdwType], 2
0x18002726a  mov     [rsp+rcx+290h+Src], ax
0x18002726f  jnz     short loc_1800272D7
0x180027271  call    cs:__imp_GetCurrentThread
0x180027277  mov     edx, 0Ch; DesiredAccess
0x18002727c  lea     r9, [rsp+290h+TokenHandle]; TokenHandle
0x180027281  mov     rcx, rax; ThreadHandle
0x180027284  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x180027288  call    cs:__imp_OpenThreadToken
0x18002728e  test    eax, eax
0x180027290  jnz     short loc_1800272A4
0x180027292  call    cs:__imp_GetLastError
0x180027298  mov     edi, eax
0x18002729a  mov     esi, 54Ch
0x18002729f  jmp     loc_1800271A4
0x1800272a4  mov     rcx, [rsp+290h+TokenHandle]; hToken
0x1800272a9  lea     rdx, [rsp+290h+Src]; lpSrc
0x1800272ae  mov     r9d, 1001h; dwSize
0x1800272b4  mov     r8, rsi; lpDest
0x1800272b7  call    cs:__imp_ExpandEnvironmentStringsForUserW
0x1800272bd  test    eax, eax
0x1800272bf  jnz     loc_18002734D
0x1800272c5  call    cs:__imp_GetLastError
0x1800272cb  mov     edi, eax
0x1800272cd  mov     esi, 556h
0x1800272d2  jmp     loc_1800271A4
0x1800272d7  cmp     [rsp+290h+pdwType], 1
0x1800272dc  jnz     short loc_180027300
0x1800272de  lea     r8, [rsp+290h+Src]; unsigned __int16 *
0x1800272e3  mov     edx, 1001h; unsigned __int64
0x1800272e8  mov     rcx, rsi; unsigned __int16 *
0x1800272eb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800272f0  test    eax, eax
0x1800272f2  jns     short loc_18002734D
0x1800272f4  mov     edi, eax
0x1800272f6  mov     esi, 55Fh
0x1800272fb  jmp     loc_1800271A4
0x180027300  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "FALSE")
0x180027305  mov     r9d, [rsp+290h+pdwType]
0x18002730a  lea     rdx, EFS_API_ERROR_1
0x180027311  mov     edi, 3F7h
0x180027316  mov     esi, 566h
0x18002731b  mov     ebx, 7
0x180027320  mov     dword ptr [rsp+290h+pvData], esi
0x180027324  mov     r8d, edi
0x180027327  mov     dword ptr [rsp+290h+phkResult], ebx
0x18002732b  call    fnEfsLogTrace2
0x180027330  mov     rcx, cs:g_hPublisher
0x180027337  lea     rdx, EFS_TRACE_ERROR
0x18002733e  mov     r9d, ebx
0x180027341  mov     dword ptr [rsp+290h+phkResult], esi
0x180027345  mov     r8d, eax
0x180027348  call    fnEfsLogTrace1
0x18002734d  mov     rcx, [rsp+290h+hkey]; hKey
0x180027352  test    rcx, rcx
0x180027355  jz      short loc_18002735D
0x180027357  call    cs:__imp_RegCloseKey
0x18002735d  mov     rcx, [rsp+290h+hKey]; hKey
0x180027362  test    rcx, rcx
0x180027365  jz      short loc_18002736D
0x180027367  call    cs:__imp_RegCloseKey
0x18002736d  mov     rcx, [rsp+290h+TokenHandle]; hObject
0x180027372  test    rcx, rcx
0x180027375  jz      short loc_18002737D
0x180027377  call    cs:__imp_CloseHandle
0x18002737d  mov     eax, edi
0x18002737f  mov     rcx, [rbp+190h+var_20]
0x180027386  xor     rcx, rsp; StackCookie
0x180027389  call    __security_check_cookie
0x18002738e  mov     rbx, [rsp+290h+arg_8]
0x180027396  add     rsp, 280h
0x18002739d  pop     rdi
0x18002739e  pop     rsi
0x18002739f  pop     rbp
0x1800273a0  retn
0x1800273a1  call    __report_rangecheckfailure
```
