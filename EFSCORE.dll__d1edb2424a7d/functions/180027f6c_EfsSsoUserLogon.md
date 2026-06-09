# EfsSsoUserLogon

- ea: `0x180027f6c`
- end: `0x18002802f`
- name: `EfsSsoUserLogon`
- size: `195`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180027764`
- `0x180028620`

## callees

- `0x1800274b8`
- `0x180027f6c`
- `0x180063698`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027fbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027fed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027fbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027fed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028021`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028021`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180027fe3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180027fe3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180027fb4`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180027fb4`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180027f80`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180027f80`

## pseudocode

```c
__int64 __fastcall EfsSsoUserLogon(__int64 a1)
{
  int v1; // eax
  unsigned int v2; // ebx
  DWORD LastError; // eax
  __int64 *v4; // rdx
  char v6; // [rsp+20h] [rbp-18h]
  HANDLE hToken; // [rsp+48h] [rbp+10h] BYREF

  hToken = 0;
  v1 = UMgrQueryUserToken(a1, &hToken);
  v2 = v1;
  if ( v1 >= 0 )
  {
    if ( ImpersonateLoggedOnUser(hToken) )
    {
      v2 = EfsSsopOnNotification(1u);
      if ( RevertToSelf() )
        goto LABEL_10;
      LastError = GetLastError();
      v4 = (__int64 *)&EFS_API_ERROR;
      v6 = 93;
    }
    else
    {
      LastError = GetLastError();
      v6 = 77;
      v4 = EFS_TRACE_ERROR;
      v2 = LastError;
    }
    fnEfsLogTrace1(g_hPublisher, (_DWORD)v4, LastError, 7, v6);
  }
  else
  {
    if ( (v1 & 0x1FFF0000) == 0x70000 )
      v2 = (unsigned __int16)v1;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v2, 7, 72);
  }
LABEL_10:
  if ( hToken )
    CloseHandle(hToken);
  return v2;
}

```

## disassembly

```asm
0x180027f6c  push    rbx
0x180027f6e  sub     rsp, 30h
0x180027f72  lea     rdx, [rsp+38h+hToken]
0x180027f77  mov     [rsp+38h+hToken], 0
0x180027f80  call    cs:__imp_UMgrQueryUserToken
0x180027f86  mov     ebx, eax
0x180027f88  test    eax, eax
0x180027f8a  jns     short loc_180027FAF
0x180027f8c  and     eax, 1FFF0000h
0x180027f91  cmp     eax, 70000h
0x180027f96  jnz     short loc_180027F9B
0x180027f98  movzx   ebx, bx
0x180027f9b  mov     dword ptr [rsp+38h+var_18], 148h
0x180027fa3  lea     rdx, EFS_TRACE_ERROR
0x180027faa  mov     r8d, ebx
0x180027fad  jmp     short loc_180028005
0x180027faf  mov     rcx, [rsp+38h+hToken]; hToken
0x180027fb4  call    cs:__imp_ImpersonateLoggedOnUser
0x180027fba  test    eax, eax
0x180027fbc  jnz     short loc_180027FD7
0x180027fbe  call    cs:__imp_GetLastError
0x180027fc4  mov     dword ptr [rsp+38h+var_18], 14Dh
0x180027fcc  lea     rdx, EFS_TRACE_ERROR
0x180027fd3  mov     ebx, eax
0x180027fd5  jmp     short loc_180028002
0x180027fd7  mov     ecx, 1; unsigned int
0x180027fdc  call    ?EfsSsopOnNotification@@YAKK@Z; EfsSsopOnNotification(ulong)
0x180027fe1  mov     ebx, eax
0x180027fe3  call    cs:__imp_RevertToSelf
0x180027fe9  test    eax, eax
0x180027feb  jnz     short loc_180028017
0x180027fed  call    cs:__imp_GetLastError
0x180027ff3  lea     rdx, EFS_API_ERROR
0x180027ffa  mov     dword ptr [rsp+38h+var_18], 15Dh
0x180028002  mov     r8d, eax
0x180028005  mov     rcx, cs:g_hPublisher
0x18002800c  mov     r9d, 7
0x180028012  call    fnEfsLogTrace1
0x180028017  mov     rcx, [rsp+38h+hToken]; hObject
0x18002801c  test    rcx, rcx
0x18002801f  jz      short loc_180028027
0x180028021  call    cs:__imp_CloseHandle
0x180028027  mov     eax, ebx
0x180028029  add     rsp, 30h
0x18002802d  pop     rbx
0x18002802e  retn
```
