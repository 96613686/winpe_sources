# ScDeviceEnumInitiateShutdown(ulong)

- ea: `0x1800064c4`
- end: `0x18000665d`
- name: `?ScDeviceEnumInitiateShutdown@@YAXK@Z`
- size: `409`
- prototype: `void __fastcall()`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x1800081f0`

## callees

- `0x180005e68`
- `0x180005f20`
- `0x1800064c4`
- `0x180006d40`
- `0x180007178`
- `0x1800071d4`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006639`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006639`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006605`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006605`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800065d4`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800065d4`

## pseudocode

```c
void __fastcall ScDeviceEnumInitiateShutdown()
{
  __int64 v0; // rcx
  __int64 v1; // rcx
  char LastError; // al
  int v3; // [rsp+30h] [rbp-50h] BYREF
  _QWORD *v4; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v5[2]; // [rsp+40h] [rbp-40h] BYREF
  char v6[32]; // [rsp+50h] [rbp-30h] BYREF

  v3 = 0;
  v5[0] = v6;
  strcpy(v6, "ScDeviceEnumInitiateShutdown");
  v5[1] = &v3;
  lambda_0fbd9787660fd35480020bdc79185fc1_::operator()(v5);
  v3 = 1;
  v4 = v5;
  _m_prefetchw(&qword_18002BD40);
  if ( (_InterlockedOr64(&qword_18002BD40, 1u) & 1) != 0 )
  {
    WppTraceIndent(v0, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_cc5e31c4c3a13497f43cc016dcb7f87d_Traceguids, WPP_pszIndent);
    }
  }
  else
  {
    *(_QWORD *)&ServiceStatus.dwCurrentState = 3;
    ServiceStatus.dwCheckPoint = 0;
    ServiceStatus.dwWaitHint = 1000;
    ServiceStatus.dwWin32ExitCode = 0;
    if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
    {
      WppTraceIndent(v1, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          (unsigned int)&WPP_cc5e31c4c3a13497f43cc016dcb7f87d_Traceguids,
          (_DWORD)WPP_pszIndent,
          LastError);
      }
    }
    SetEvent(hObject);
  }
  WppTraceUnwinder__lambda_0fbd9787660fd35480020bdc79185fc1____::_WppTraceUnwinder__lambda_0fbd9787660fd35480020bdc79185fc1____(&v4);
}

```

## disassembly

```asm
0x1800064c4  push    rbp
0x1800064c6  mov     rbp, rsp
0x1800064c9  sub     rsp, 80h
0x1800064d0  mov     rax, cs:__security_cookie
0x1800064d7  xor     rax, rsp
0x1800064da  mov     [rbp+var_10], rax
0x1800064de  movups  xmm0, xmmword ptr cs:aScdeviceenumin; "ScDeviceEnumInitiateShutdown"
0x1800064e5  lea     rax, [rbp+var_30]
0x1800064e9  mov     [rbp+var_50], 0
0x1800064f0  movups  xmm1, xmmword ptr cs:aScdeviceenumin+0Dh; "nitiateShutdown"
0x1800064f7  mov     [rbp+var_40], rax
0x1800064fb  lea     rcx, [rbp+var_40]
0x1800064ff  lea     rax, [rbp+var_50]
0x180006503  movups  xmmword ptr [rbp+var_30], xmm0
0x180006507  mov     [rbp+var_38], rax
0x18000650b  movups  xmmword ptr [rbp+var_30+0Dh], xmm1
0x18000650f  call    _lambda_0fbd9787660fd35480020bdc79185fc1___operator__
0x180006514  lea     rax, [rbp+var_40]
0x180006518  mov     [rbp+var_50], 1
0x18000651f  mov     [rbp+var_48], rax
0x180006523  prefetchw byte ptr cs:qword_18002BD40
0x18000652a  mov     rax, cs:qword_18002BD40
0x180006531  mov     rcx, rax
0x180006534  or      rcx, 1
0x180006538  lock cmpxchg cs:qword_18002BD40, rcx
0x180006541  jnz     short loc_180006531
0x180006543  test    al, 1
0x180006545  jz      short loc_18000659D
0x180006547  mov     edx, 2
0x18000654c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180006551  mov     rcx, cs:WPP_GLOBAL_Control
0x180006558  lea     rdx, WPP_GLOBAL_Control
0x18000655f  cmp     rcx, rdx
0x180006562  jz      loc_18000663F
0x180006568  test    byte ptr [rcx+1Ch], 1
0x18000656c  jz      loc_18000663F
0x180006572  cmp     byte ptr [rcx+19h], 4
0x180006576  jb      loc_18000663F
0x18000657c  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180006583  lea     r8, WPP_cc5e31c4c3a13497f43cc016dcb7f87d_Traceguids
0x18000658a  mov     rcx, [rcx+10h]
0x18000658e  mov     edx, 1Ch
0x180006593  call    WPP_SF_s
0x180006598  jmp     loc_18000663F
0x18000659d  mov     rcx, qword ptr cs:hServiceStatus; hServiceStatus
0x1800065a4  lea     rdx, ServiceStatus; lpServiceStatus
0x1800065ab  mov     qword ptr cs:ServiceStatus.dwCurrentState, 3
0x1800065b6  mov     cs:ServiceStatus.dwCheckPoint, 0
0x1800065c0  mov     cs:ServiceStatus.dwWaitHint, 3E8h
0x1800065ca  mov     cs:ServiceStatus.dwWin32ExitCode, 0
0x1800065d4  call    cs:__imp_SetServiceStatus
0x1800065da  test    eax, eax
0x1800065dc  jnz     short loc_180006632
0x1800065de  lea     edx, [rax+2]
0x1800065e1  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800065e6  mov     rax, cs:WPP_GLOBAL_Control
0x1800065ed  lea     rdx, WPP_GLOBAL_Control
0x1800065f4  cmp     rax, rdx
0x1800065f7  jz      short loc_180006632
0x1800065f9  test    byte ptr [rax+1Ch], 1
0x1800065fd  jz      short loc_180006632
0x1800065ff  cmp     byte ptr [rax+19h], 2
0x180006603  jb      short loc_180006632
0x180006605  call    cs:__imp_GetLastError
0x18000660b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006612  lea     r8, WPP_cc5e31c4c3a13497f43cc016dcb7f87d_Traceguids
0x180006619  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180006620  mov     edx, 1Dh
0x180006625  mov     [rsp+80h+var_60], eax
0x180006629  mov     rcx, [rcx+10h]
0x18000662d  call    WPP_SF_sd
0x180006632  mov     rcx, cs:hObject; hEvent
0x180006639  call    cs:__imp_SetEvent
0x18000663f  lea     rcx, [rbp+var_48]
0x180006643  call    WppTraceUnwinder__lambda_0fbd9787660fd35480020bdc79185fc1_______WppTraceUnwinder__lambda_0fbd9787660fd35480020bdc79185fc1____
0x180006648  mov     rcx, [rbp+var_10]
0x18000664c  xor     rcx, rsp; StackCookie
0x18000664f  call    __security_check_cookie
0x180006654  add     rsp, 80h
0x18000665b  pop     rbp
0x18000665c  retn
```
