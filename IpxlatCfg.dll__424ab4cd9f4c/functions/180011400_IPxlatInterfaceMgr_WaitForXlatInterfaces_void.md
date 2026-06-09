# IPxlatInterfaceMgr::WaitForXlatInterfaces(void)

- ea: `0x180011400`
- end: `0x1800116b4`
- name: `?WaitForXlatInterfaces@IPxlatInterfaceMgr@@QEAAKXZ`
- size: `692`
- prototype: `__int64 __fastcall(IPxlatInterfaceMgr *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ba4c`

## callees

- `0x180001d40`
- `0x18000c224`
- `0x18000f4f8`
- `0x180011400`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001145c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011537`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011617`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001145c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011537`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011617`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180011452`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180011529`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180011452`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x180011529`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800114e8`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800114e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011673`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011673`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800114f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800114f5`

## string_xrefs

- `0x180011474`: `Could not set timer for service stop`
- `0x180011553`: `Could not set timer for service stop after xlat is disabled on all interfaces`
- `0x1800115a5`: `Service stopping due to timeout`
- `0x1800115f4`: `Service stopping due explicit shutdown`
- `0x180011632`: `Service stopping due to error`

## pseudocode

```c
__int64 __fastcall IPxlatInterfaceMgr::WaitForXlatInterfaces(IPxlatInterfaceMgr *this)
{
  DWORD v2; // eax
  __int64 v3; // rcx
  __int64 v4; // r8
  DWORD v5; // ebx
  DWORD v7; // esi
  char v8; // di
  DWORD v9; // r14d
  __int64 v10; // rcx
  __int64 v11; // r8
  DWORD v12; // eax
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 *v15; // rdx
  __int64 v16; // r9
  DWORD LastError; // eax
  DWORD v18; // [rsp+30h] [rbp-29h] BYREF
  LARGE_INTEGER DueTime; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v20[16]; // [rsp+40h] [rbp-19h] BYREF
  const char *v21; // [rsp+50h] [rbp-9h]
  __int64 v22; // [rsp+58h] [rbp-1h]
  DWORD *v23; // [rsp+60h] [rbp+7h]
  __int64 v24; // [rsp+68h] [rbp+Fh]
  HANDLE Handles[3]; // [rsp+70h] [rbp+17h] BYREF

  DueTime.QuadPart = -1200000000;
  if ( SetWaitableTimer(*((HANDLE *)this + 6), &DueTime, 0, 0, 0, 0) )
  {
    v7 = 0;
    Handles[0] = *((HANDLE *)this + 5);
    v8 = 1;
    Handles[1] = *((HANDLE *)this + 6);
    Handles[2] = *((HANDLE *)this + 4);
    while ( 1 )
    {
      v9 = WaitForMultipleObjectsEx(3u, Handles, 0, 0xFFFFFFFF, 1);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
      if ( v9 )
      {
        if ( v9 != 1 )
        {
          if ( v9 == 2 )
          {
            if ( (Microsoft_Windows_IPxlatCfgEnableBits & 2) != 0 )
            {
              v22 = 39;
              v21 = "Service stopping due explicit shutdown";
              v15 = IPXLATCFG_INFO_EVENT;
              v16 = 2;
              goto LABEL_24;
            }
          }
          else
          {
            LastError = GetLastError();
            v7 = LastError;
            if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
            {
              v18 = LastError;
              v15 = IPXLATCFG_ERROR_EVENT;
              v22 = 30;
              v21 = "Service stopping due to error";
              v16 = 3;
              v24 = 4;
              v23 = &v18;
LABEL_24:
              McGenEventWrite_EventWriteTransfer(v10, v15, v11, v16, v20);
            }
          }
          v8 = 0;
LABEL_26:
          *(_BYTE *)this = 1;
          goto LABEL_27;
        }
        if ( !*((_QWORD *)this + 17) )
        {
          if ( (Microsoft_Windows_IPxlatCfgEnableBits & 2) != 0 )
          {
            v22 = 32;
            v21 = "Service stopping due to timeout";
            McGenEventWrite_EventWriteTransfer(v10, IPXLATCFG_INFO_EVENT, v11, 2, v20);
          }
          v7 = 0;
          goto LABEL_16;
        }
      }
      else if ( !*((_QWORD *)this + 17) && !SetWaitableTimer(*((HANDLE *)this + 6), &DueTime, 0, 0, 0, 0) )
      {
        v12 = GetLastError();
        v7 = v12;
        if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
        {
          v18 = v12;
          v22 = 78;
          v21 = "Could not set timer for service stop after xlat is disabled on all interfaces";
          v24 = 4;
          v23 = &v18;
          McGenEventWrite_EventWriteTransfer(v13, IPXLATCFG_ERROR_EVENT, v14, 3, v20);
        }
LABEL_16:
        v8 = 0;
      }
      if ( !v8 )
        goto LABEL_26;
LABEL_27:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
      if ( !v8 )
      {
        IPxlatInterfaceMgr::Cleanup(this);
        return v7;
      }
    }
  }
  v2 = GetLastError();
  v5 = v2;
  if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
  {
    v18 = v2;
    v22 = 37;
    v21 = "Could not set timer for service stop";
    v24 = 4;
    v23 = &v18;
    McGenEventWrite_EventWriteTransfer(v3, IPXLATCFG_ERROR_EVENT, v4, 3, v20);
  }
  return v5;
}

```

## disassembly

```asm
0x180011400  mov     [rsp-8+arg_8], rbx
0x180011405  mov     [rsp-8+arg_10], rsi
0x18001140a  push    rbp
0x18001140b  push    rdi
0x18001140c  push    r12
0x18001140e  push    r13
0x180011410  push    r14
0x180011412  lea     rbp, [rsp-37h]
0x180011417  sub     rsp, 90h
0x18001141e  mov     rax, cs:__security_cookie
0x180011425  xor     rax, rsp
0x180011428  mov     [rbp+57h+var_28], rax
0x18001142c  xor     r13d, r13d
0x18001142f  mov     qword ptr [rbp+57h+DueTime], 0FFFFFFFFB8797400h
0x180011437  mov     rbx, rcx
0x18001143a  mov     [rsp+0B0h+fResume], r13d; fResume
0x18001143f  mov     rcx, [rcx+30h]; hTimer
0x180011443  lea     rdx, [rbp+57h+DueTime]; lpDueTime
0x180011447  xor     r9d, r9d; pfnCompletionRoutine
0x18001144a  mov     [rsp+0B0h+lpArgToCompletionRoutine], r13; lpArgToCompletionRoutine
0x18001144f  xor     r8d, r8d; lPeriod
0x180011452  call    cs:__imp_SetWaitableTimer
0x180011458  test    eax, eax
0x18001145a  jnz     short loc_1800114B3
0x18001145c  call    cs:__imp_GetLastError
0x180011462  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 1
0x180011469  mov     ebx, eax
0x18001146b  jz      short loc_1800114AC
0x18001146d  mov     [rbp+57h+var_80], eax
0x180011470  lea     r9d, [r13+3]
0x180011474  lea     rax, aCouldNotSetTim_0; "Could not set timer for service stop"
0x18001147b  mov     [rbp+57h+var_58], 25h ; '%'
0x180011483  mov     [rbp+57h+var_60], rax
0x180011487  lea     rdx, IPXLATCFG_ERROR_EVENT
0x18001148e  lea     rax, [rbp+57h+var_80]
0x180011492  mov     [rbp+57h+var_48], 4
0x18001149a  mov     [rbp+57h+var_50], rax
0x18001149e  lea     rax, [rbp+57h+var_70]
0x1800114a2  mov     [rsp+0B0h+lpArgToCompletionRoutine], rax
0x1800114a7  call    McGenEventWrite_EventWriteTransfer
0x1800114ac  mov     eax, ebx
0x1800114ae  jmp     loc_18001168C
0x1800114b3  mov     rax, [rbx+28h]
0x1800114b7  mov     esi, r13d
0x1800114ba  mov     [rbp+57h+Handles], rax
0x1800114be  mov     dil, 1
0x1800114c1  mov     rax, [rbx+30h]
0x1800114c5  mov     [rbp+57h+var_38], rax
0x1800114c9  mov     rax, [rbx+20h]
0x1800114cd  mov     [rbp+57h+var_30], rax
0x1800114d1  xor     r8d, r8d; bWaitAll
0x1800114d4  mov     dword ptr [rsp+0B0h+lpArgToCompletionRoutine], 1; bAlertable
0x1800114dc  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800114e0  lea     rdx, [rbp+57h+Handles]; lpHandles
0x1800114e4  lea     ecx, [r8+3]; nCount
0x1800114e8  call    cs:__imp_WaitForMultipleObjectsEx
0x1800114ee  lea     rcx, [rbx+38h]; lpCriticalSection
0x1800114f2  mov     r14d, eax
0x1800114f5  call    cs:__imp_EnterCriticalSection
0x1800114fb  test    r14d, r14d
0x1800114fe  jnz     loc_18001158D
0x180011504  cmp     [rbx+88h], r13
0x18001150b  jnz     loc_1800115D7
0x180011511  mov     rcx, [rbx+30h]; hTimer
0x180011515  lea     rdx, [rbp+57h+DueTime]; lpDueTime
0x180011519  mov     [rsp+0B0h+fResume], r13d; fResume
0x18001151e  xor     r9d, r9d; pfnCompletionRoutine
0x180011521  xor     r8d, r8d; lPeriod
0x180011524  mov     [rsp+0B0h+lpArgToCompletionRoutine], r13; lpArgToCompletionRoutine
0x180011529  call    cs:__imp_SetWaitableTimer
0x18001152f  test    eax, eax
0x180011531  jnz     loc_1800115D7
0x180011537  call    cs:__imp_GetLastError
0x18001153d  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 1
0x180011544  mov     esi, eax
0x180011546  jz      loc_1800115D4
0x18001154c  mov     [rbp+57h+var_80], eax
0x18001154f  lea     r9d, [r14+3]
0x180011553  lea     rax, aCouldNotSetTim; "Could not set timer for service stop af"...
0x18001155a  mov     [rbp+57h+var_58], 4Eh ; 'N'
0x180011562  mov     [rbp+57h+var_60], rax
0x180011566  lea     rdx, IPXLATCFG_ERROR_EVENT
0x18001156d  lea     rax, [rbp+57h+var_80]
0x180011571  mov     [rbp+57h+var_48], 4
0x180011579  mov     [rbp+57h+var_50], rax
0x18001157d  lea     rax, [rbp+57h+var_70]
0x180011581  mov     [rsp+0B0h+lpArgToCompletionRoutine], rax
0x180011586  call    McGenEventWrite_EventWriteTransfer
0x18001158b  jmp     short loc_1800115D4
0x18001158d  cmp     r14d, 1
0x180011591  jnz     short loc_1800115E5
0x180011593  cmp     [rbx+88h], r13
0x18001159a  jnz     short loc_1800115D7
0x18001159c  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 2
0x1800115a3  jz      short loc_1800115D1
0x1800115a5  lea     rax, aServiceStoppin_0; "Service stopping due to timeout"
0x1800115ac  mov     [rbp+57h+var_58], 20h ; ' '
0x1800115b4  mov     [rbp+57h+var_60], rax
0x1800115b8  lea     r9d, [r14+1]
0x1800115bc  lea     rax, [rbp+57h+var_70]
0x1800115c0  lea     rdx, IPXLATCFG_INFO_EVENT
0x1800115c7  mov     [rsp+0B0h+lpArgToCompletionRoutine], rax
0x1800115cc  call    McGenEventWrite_EventWriteTransfer
0x1800115d1  mov     esi, r13d
0x1800115d4  mov     dil, r13b
0x1800115d7  test    dil, dil
0x1800115da  jnz     loc_18001166F
0x1800115e0  jmp     loc_18001166C
0x1800115e5  cmp     r14d, 2
0x1800115e9  jnz     short loc_180011617
0x1800115eb  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, r14b
0x1800115f2  jz      short loc_180011669
0x1800115f4  lea     rax, aServiceStoppin_1; "Service stopping due explicit shutdown"
0x1800115fb  mov     [rbp+57h+var_58], 27h ; '''
0x180011603  mov     [rbp+57h+var_60], rax
0x180011607  lea     rdx, IPXLATCFG_INFO_EVENT
0x18001160e  lea     rax, [rbp+57h+var_70]
0x180011612  mov     r9d, r14d
0x180011615  jmp     short loc_18001165F
0x180011617  call    cs:__imp_GetLastError
0x18001161d  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 1
0x180011624  mov     esi, eax
0x180011626  jz      short loc_180011669
0x180011628  mov     [rbp+57h+var_80], eax
0x18001162b  lea     rdx, IPXLATCFG_ERROR_EVENT
0x180011632  lea     rax, aServiceStoppin; "Service stopping due to error"
0x180011639  mov     [rbp+57h+var_58], 1Eh
0x180011641  mov     [rbp+57h+var_60], rax
0x180011645  mov     r9d, 3
0x18001164b  lea     rax, [rbp+57h+var_80]
0x18001164f  mov     [rbp+57h+var_48], 4
0x180011657  mov     [rbp+57h+var_50], rax
0x18001165b  lea     rax, [rbp+57h+var_70]
0x18001165f  mov     [rsp+0B0h+lpArgToCompletionRoutine], rax
0x180011664  call    McGenEventWrite_EventWriteTransfer
0x180011669  mov     dil, r13b
0x18001166c  mov     byte ptr [rbx], 1
0x18001166f  lea     rcx, [rbx+38h]; lpCriticalSection
0x180011673  call    cs:__imp_LeaveCriticalSection
0x180011679  test    dil, dil
0x18001167c  jnz     loc_1800114D1
0x180011682  mov     rcx, rbx; this
0x180011685  call    ?Cleanup@IPxlatInterfaceMgr@@AEAAXXZ; IPxlatInterfaceMgr::Cleanup(void)
0x18001168a  mov     eax, esi
0x18001168c  mov     rcx, [rbp+57h+var_28]
0x180011690  xor     rcx, rsp; StackCookie
0x180011693  call    __security_check_cookie
0x180011698  lea     r11, [rsp+0B0h+var_20]
0x1800116a0  mov     rbx, [r11+38h]
0x1800116a4  mov     rsi, [r11+40h]
0x1800116a8  mov     rsp, r11
0x1800116ab  pop     r14
0x1800116ad  pop     r13
0x1800116af  pop     r12
0x1800116b1  pop     rdi
0x1800116b2  pop     rbp
0x1800116b3  retn
```
