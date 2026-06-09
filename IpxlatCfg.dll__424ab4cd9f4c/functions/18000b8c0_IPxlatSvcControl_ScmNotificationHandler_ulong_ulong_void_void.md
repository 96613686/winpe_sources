# IPxlatSvcControl::ScmNotificationHandler(ulong,ulong,void *,void *)

- ea: `0x18000b8c0`
- end: `0x18000ba44`
- name: `?ScmNotificationHandler@IPxlatSvcControl@@CAKKKPEAX0@Z`
- size: `388`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, char *lpContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001d40`
- `0x18000b8c0`
- `0x18000c224`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b968`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b968`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b9de`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000b9de`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000b9c8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000b9c8`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000b95e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000b95e`

## string_xrefs

- `0x18000b9f3`: `Service already stopping`
- `0x18000b917`: `Service stop notification from SCM`
- `0x18000b987`: `Could not update service status to stop pending.`

## pseudocode

```c
__int64 __fastcall IPxlatSvcControl::ScmNotificationHandler(
        DWORD dwControl,
        DWORD dwEventType,
        LPVOID lpEventData,
        char *lpContext)
{
  DWORD v4; // esi
  __int64 v6; // rcx
  DWORD LastError; // eax
  __int64 *v8; // rdx
  __int64 v9; // r9
  DWORD v11; // [rsp+30h] [rbp-40h] BYREF
  _BYTE v12[16]; // [rsp+38h] [rbp-38h] BYREF
  const char *v13; // [rsp+48h] [rbp-28h]
  __int64 v14; // [rsp+50h] [rbp-20h]
  DWORD *v15; // [rsp+58h] [rbp-18h]
  __int64 v16; // [rsp+60h] [rbp-10h]

  v4 = 0;
  v6 = dwControl - 1;
  if ( (_DWORD)v6 && (_DWORD)v6 != 4 )
    return v4;
  if ( ((*((_DWORD *)lpContext + 3) - 1) & 0xFFFFFFFD) == 0 )
  {
    if ( (Microsoft_Windows_IPxlatCfgEnableBits & 2) != 0 )
    {
      v14 = 25;
      v13 = "Service already stopping";
      v8 = IPXLATCFG_INFO_EVENT;
      v9 = 2;
      goto LABEL_16;
    }
    return v4;
  }
  if ( (Microsoft_Windows_IPxlatCfgEnableBits & 2) != 0 )
  {
    v14 = 35;
    v13 = "Service stop notification from SCM";
    McGenEventWrite_EventWriteTransfer(v6, IPXLATCFG_INFO_EVENT, lpEventData, 2, v12);
  }
  *(_QWORD *)(lpContext + 12) = 3;
  *((_DWORD *)lpContext + 7) = 1;
  *((_DWORD *)lpContext + 8) = 10000;
  if ( !SetServiceStatus(*((SERVICE_STATUS_HANDLE *)lpContext + 5), (LPSERVICE_STATUS)(lpContext + 8)) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
    {
      v11 = LastError;
      v8 = IPXLATCFG_ERROR_EVENT;
      v14 = 49;
      v13 = "Could not update service status to stop pending.";
      v9 = 3;
      v16 = 4;
      v15 = &v11;
LABEL_16:
      McGenEventWrite_EventWriteTransfer(v6, v8, lpEventData, v9, v12);
      return v4;
    }
    return v4;
  }
  while ( 1 )
  {
    if ( _InterlockedCompareExchange((volatile signed __int32 *)lpContext + 12, 1, 1) )
    {
      SetEvent(*(HANDLE *)lpContext);
      return v4;
    }
    if ( _InterlockedCompareExchange((volatile signed __int32 *)lpContext + 13, 1, 1) )
      break;
    Sleep(0x1F4u);
  }
  return 0;
}

```

## disassembly

```asm
0x18000b8c0  mov     [rsp-18h+arg_0], rbx
0x18000b8c5  mov     [rsp-18h+arg_8], rsi
0x18000b8ca  push    rbp
0x18000b8cb  push    rdi
0x18000b8cc  push    r15
0x18000b8ce  mov     rbp, rsp
0x18000b8d1  sub     rsp, 70h
0x18000b8d5  mov     rax, cs:__security_cookie
0x18000b8dc  xor     rax, rsp
0x18000b8df  mov     [rbp+var_8], rax
0x18000b8e3  xor     esi, esi
0x18000b8e5  mov     rbx, r9
0x18000b8e8  sub     ecx, 1
0x18000b8eb  jz      short loc_18000B8F6
0x18000b8ed  cmp     ecx, 4
0x18000b8f0  jnz     loc_18000BA21
0x18000b8f6  mov     eax, [r9+0Ch]
0x18000b8fa  mov     r15d, 1
0x18000b900  sub     eax, r15d
0x18000b903  test    eax, 0FFFFFFFDh
0x18000b908  jz      loc_18000B9EA
0x18000b90e  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 2
0x18000b915  jz      short loc_18000B943
0x18000b917  lea     rax, aServiceStopNot; "Service stop notification from SCM"
0x18000b91e  mov     [rbp+var_20], 23h ; '#'
0x18000b926  mov     [rbp+var_28], rax
0x18000b92a  lea     r9d, [r15+1]
0x18000b92e  lea     rax, [rbp+var_38]
0x18000b932  lea     rdx, IPXLATCFG_INFO_EVENT
0x18000b939  mov     [rsp+70h+var_50], rax
0x18000b93e  call    McGenEventWrite_EventWriteTransfer
0x18000b943  mov     qword ptr [rbx+0Ch], 3
0x18000b94b  lea     rdx, [rbx+8]; lpServiceStatus
0x18000b94f  mov     [rbx+1Ch], r15d
0x18000b953  mov     dword ptr [rbx+20h], 2710h
0x18000b95a  mov     rcx, [rbx+28h]; hServiceStatus
0x18000b95e  call    cs:__imp_SetServiceStatus
0x18000b964  test    eax, eax
0x18000b966  jnz     short loc_18000B9CE
0x18000b968  call    cs:__imp_GetLastError
0x18000b96e  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, r15b
0x18000b975  mov     esi, eax
0x18000b977  jz      loc_18000BA21
0x18000b97d  mov     [rbp+var_40], eax
0x18000b980  lea     rdx, IPXLATCFG_ERROR_EVENT
0x18000b987  lea     rax, aCouldNotUpdate; "Could not update service status to stop"...
0x18000b98e  mov     [rbp+var_20], 31h ; '1'
0x18000b996  mov     [rbp+var_28], rax
0x18000b99a  mov     r9d, 3
0x18000b9a0  lea     rax, [rbp+var_40]
0x18000b9a4  mov     [rbp+var_10], 4
0x18000b9ac  mov     [rbp+var_18], rax
0x18000b9b0  lea     rax, [rbp+var_38]
0x18000b9b4  jmp     short loc_18000BA17
0x18000b9b6  mov     eax, r15d
0x18000b9b9  lock cmpxchg [rbx+34h], r15d
0x18000b9bf  test    eax, eax
0x18000b9c1  jnz     short loc_18000B9E6
0x18000b9c3  mov     ecx, 1F4h; dwMilliseconds
0x18000b9c8  call    cs:__imp_Sleep
0x18000b9ce  mov     eax, r15d
0x18000b9d1  lock cmpxchg [rbx+30h], r15d
0x18000b9d7  test    eax, eax
0x18000b9d9  jz      short loc_18000B9B6
0x18000b9db  mov     rcx, [rbx]; hEvent
0x18000b9de  call    cs:__imp_SetEvent
0x18000b9e4  jmp     short loc_18000BA21
0x18000b9e6  xor     eax, eax
0x18000b9e8  jmp     short loc_18000BA23
0x18000b9ea  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 2
0x18000b9f1  jz      short loc_18000BA21
0x18000b9f3  lea     rax, aServiceAlready; "Service already stopping"
0x18000b9fa  mov     [rbp+var_20], 19h
0x18000ba02  mov     [rbp+var_28], rax
0x18000ba06  lea     rdx, IPXLATCFG_INFO_EVENT
0x18000ba0d  lea     rax, [rbp+var_38]
0x18000ba11  mov     r9d, 2
0x18000ba17  mov     [rsp+70h+var_50], rax
0x18000ba1c  call    McGenEventWrite_EventWriteTransfer
0x18000ba21  mov     eax, esi
0x18000ba23  mov     rcx, [rbp+var_8]
0x18000ba27  xor     rcx, rsp; StackCookie
0x18000ba2a  call    __security_check_cookie
0x18000ba2f  lea     r11, [rsp+70h+var_s0]
0x18000ba34  mov     rbx, [r11+20h]
0x18000ba38  mov     rsi, [r11+28h]
0x18000ba3c  mov     rsp, r11
0x18000ba3f  pop     r15
0x18000ba41  pop     rdi
0x18000ba42  pop     rbp
0x18000ba43  retn
```
