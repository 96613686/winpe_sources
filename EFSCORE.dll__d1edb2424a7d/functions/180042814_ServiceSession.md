# ServiceSession

- ea: `0x180042814`
- end: `0x180042a35`
- name: `ServiceSession`
- size: `545`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180042710`

## callees

- `0x180005045`
- `0x1800254d4`
- `0x180025694`
- `0x180042814`
- `0x180042a3c`
- `0x180043bd8`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800428be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042906`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042955`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800428be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042906`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042955`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800429a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042a18`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800429a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042a18`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004294b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180042994`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004294b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180042994`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800428b4`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800428b4`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18004286f`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18004286f`

## pseudocode

```c
__int64 __fastcall ServiceSession(_QWORD *a1)
{
  int v2; // ecx
  unsigned int v3; // ebx
  signed int LastError; // eax
  signed int v5; // eax
  signed int v6; // eax
  int v7; // eax
  _BYTE v9[24]; // [rsp+40h] [rbp-19h] BYREF
  unsigned __int16 *v10; // [rsp+58h] [rbp-1h]
  HANDLE hToken; // [rsp+C0h] [rbp+67h] BYREF

  hToken = 0;
  memset_0(v9, 0, 0x70u);
  fnEfsLogTrace1Strings(v2, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 33, 130);
  v3 = UMgrQueryUserToken(*a1, &hToken);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v3,
              33,
              130) < 0 )
    goto LABEL_20;
  if ( !ImpersonateLoggedOnUser(hToken) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v3, 33, 139);
    goto LABEL_20;
  }
  if ( !(unsigned __int8)EfsGetUserInfo((struct _EFS_USER_INFO *)v9) )
  {
    v5 = GetLastError();
    v3 = v5;
    if ( v5 > 0 )
      v3 = (unsigned __int16)v5 | 0x80070000;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v3, 33, 145);
LABEL_14:
    RevertToSelf();
    goto LABEL_20;
  }
  ServiceUserQueue(v9, hToken);
  if ( !RevertToSelf() )
  {
    v6 = GetLastError();
    v3 = v6;
    if ( v6 > 0 )
      v3 = (unsigned __int16)v6 | 0x80070000;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v3, 33, 160);
    EfsFreeUserInfo(v9);
    goto LABEL_14;
  }
  if ( hToken )
  {
    CloseHandle(hToken);
    hToken = 0;
  }
  v7 = EfspLockAndWriteUserFEQueueToFile(v10);
  v3 = v7;
  if ( v7 < 0 )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v7, 33, 178);
    v3 = 0;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 0, 33, 179);
  }
  EfsFreeUserInfo(v9);
LABEL_20:
  if ( hToken )
    CloseHandle(hToken);
  return v3;
}

```

## disassembly

```asm
0x180042814  mov     [rsp-8+arg_8], rbx
0x180042819  mov     [rsp-8+arg_10], rsi
0x18004281e  push    rbp
0x18004281f  lea     rbp, [rsp-57h]
0x180042824  sub     rsp, 0B0h
0x18004282b  xor     edx, edx; Val
0x18004282d  mov     [rbp+57h+hToken], 0
0x180042835  mov     rbx, rcx
0x180042838  lea     rcx, [rbp+57h+var_70]; void *
0x18004283c  lea     r8d, [rdx+70h]; Size
0x180042840  call    memset_0
0x180042845  mov     esi, 21h ; '!'
0x18004284a  mov     [rsp+0B0h+var_90], 182h
0x180042852  mov     r9d, esi
0x180042855  lea     r8, sourceString
0x18004285c  lea     rdx, EFS_TRACE_START_EVENT
0x180042863  call    fnEfsLogTrace1Strings
0x180042868  mov     rcx, [rbx]
0x18004286b  lea     rdx, [rbp+57h+hToken]
0x18004286f  call    cs:__imp_UMgrQueryUserToken
0x180042875  mov     rcx, cs:g_hPublisher
0x18004287c  lea     r9, sourceString
0x180042883  mov     [rsp+0B0h+var_80], 182h
0x18004288b  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180042892  mov     [rsp+0B0h+var_88], esi
0x180042896  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x18004289d  mov     ebx, eax
0x18004289f  mov     [rsp+0B0h+var_90], eax
0x1800428a3  call    fnEfsLogTrace1String1Dword
0x1800428a8  test    eax, eax
0x1800428aa  js      loc_180042A0F
0x1800428b0  mov     rcx, [rbp+57h+hToken]; hToken
0x1800428b4  call    cs:__imp_ImpersonateLoggedOnUser
0x1800428ba  test    eax, eax
0x1800428bc  jnz     short loc_1800428F9
0x1800428be  call    cs:__imp_GetLastError
0x1800428c4  mov     ebx, eax
0x1800428c6  test    eax, eax
0x1800428c8  jle     short loc_1800428D3
0x1800428ca  movzx   ebx, ax
0x1800428cd  or      ebx, 80070000h
0x1800428d3  mov     rcx, cs:g_hPublisher
0x1800428da  lea     rdx, EFS_TRACE_ERROR
0x1800428e1  mov     r9d, esi
0x1800428e4  mov     [rsp+0B0h+var_90], 18Bh
0x1800428ec  mov     r8d, ebx
0x1800428ef  call    fnEfsLogTrace1
0x1800428f4  jmp     loc_180042A0F
0x1800428f9  lea     rcx, [rbp+57h+var_70]
0x1800428fd  call    EfsGetUserInfo
0x180042902  test    al, al
0x180042904  jnz     short loc_18004293E
0x180042906  call    cs:__imp_GetLastError
0x18004290c  mov     ebx, eax
0x18004290e  test    eax, eax
0x180042910  jle     short loc_18004291B
0x180042912  movzx   ebx, ax
0x180042915  or      ebx, 80070000h
0x18004291b  mov     rcx, cs:g_hPublisher
0x180042922  lea     rdx, EFS_TRACE_ERROR
0x180042929  mov     r9d, esi
0x18004292c  mov     [rsp+0B0h+var_90], 191h
0x180042934  mov     r8d, ebx
0x180042937  call    fnEfsLogTrace1
0x18004293c  jmp     short loc_180042994
0x18004293e  mov     rdx, [rbp+57h+hToken]
0x180042942  lea     rcx, [rbp+57h+var_70]
0x180042946  call    ServiceUserQueue
0x18004294b  call    cs:__imp_RevertToSelf
0x180042951  test    eax, eax
0x180042953  jnz     short loc_18004299C
0x180042955  call    cs:__imp_GetLastError
0x18004295b  mov     ebx, eax
0x18004295d  test    eax, eax
0x18004295f  jle     short loc_18004296A
0x180042961  movzx   ebx, ax
0x180042964  or      ebx, 80070000h
0x18004296a  mov     rcx, cs:g_hPublisher
0x180042971  lea     rdx, EFS_TRACE_ERROR
0x180042978  mov     r9d, esi
0x18004297b  mov     [rsp+0B0h+var_90], 1A0h
0x180042983  mov     r8d, ebx
0x180042986  call    fnEfsLogTrace1
0x18004298b  lea     rcx, [rbp+57h+var_70]
0x18004298f  call    EfsFreeUserInfo
0x180042994  call    cs:__imp_RevertToSelf
0x18004299a  jmp     short loc_180042A0F
0x18004299c  mov     rcx, [rbp+57h+hToken]; hObject
0x1800429a0  test    rcx, rcx
0x1800429a3  jz      short loc_1800429B3
0x1800429a5  call    cs:__imp_CloseHandle
0x1800429ab  mov     [rbp+57h+hToken], 0
0x1800429b3  mov     rcx, [rbp+57h+var_58]; unsigned __int16 *
0x1800429b7  call    ?EfspLockAndWriteUserFEQueueToFile@@YAJPEBG@Z; EfspLockAndWriteUserFEQueueToFile(ushort const *)
0x1800429bc  mov     ebx, eax
0x1800429be  test    eax, eax
0x1800429c0  jns     short loc_180042A06
0x1800429c2  mov     rcx, cs:g_hPublisher
0x1800429c9  lea     rdx, EFS_API_ERROR
0x1800429d0  mov     r9d, esi
0x1800429d3  mov     [rsp+0B0h+var_90], 1B2h
0x1800429db  mov     r8d, eax
0x1800429de  call    fnEfsLogTrace1
0x1800429e3  mov     rcx, cs:g_hPublisher
0x1800429ea  lea     rdx, EFS_TRACE_STATUS
0x1800429f1  mov     r9d, esi
0x1800429f4  mov     [rsp+0B0h+var_90], 1B3h
0x1800429fc  xor     r8d, r8d
0x1800429ff  xor     ebx, ebx
0x180042a01  call    fnEfsLogTrace1
0x180042a06  lea     rcx, [rbp+57h+var_70]
0x180042a0a  call    EfsFreeUserInfo
0x180042a0f  mov     rcx, [rbp+57h+hToken]; hObject
0x180042a13  test    rcx, rcx
0x180042a16  jz      short loc_180042A1E
0x180042a18  call    cs:__imp_CloseHandle
0x180042a1e  lea     r11, [rsp+0B0h+var_s0]
0x180042a26  mov     eax, ebx
0x180042a28  mov     rbx, [r11+18h]
0x180042a2c  mov     rsi, [r11+20h]
0x180042a30  mov     rsp, r11
0x180042a33  pop     rbp
0x180042a34  retn
```
