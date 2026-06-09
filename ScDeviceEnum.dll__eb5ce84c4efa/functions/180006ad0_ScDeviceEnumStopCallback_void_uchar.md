# ScDeviceEnumStopCallback(void *,uchar)

- ea: `0x180006ad0`
- end: `0x180006c7a`
- name: `?ScDeviceEnumStopCallback@@YAXPEAXE@Z`
- size: `426`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006034`

## callees

- `0x180005ea0`
- `0x180005fd8`
- `0x180006ad0`
- `0x180006d40`
- `0x1800070f0`
- `0x180007120`
- `0x1800071d4`
- `0x180007b54`
- `0x180008b24`
- `0x18000a0c4`
- `0x18000bd74`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006c05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006ba0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006ba0`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006bd4`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006bd4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180006b57`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180006b57`

## pseudocode

```c
void __fastcall ScDeviceEnumStopCallback(void *a1)
{
  signed __int64 v1; // rax
  signed __int64 v2; // rtt
  signed __int64 v3; // rtt
  PVOID *v4; // rcx
  __int64 v5; // r8
  char LastError; // al
  int v7; // [rsp+30h] [rbp-9h] BYREF
  _QWORD *v8; // [rsp+38h] [rbp-1h] BYREF
  _QWORD v9[2]; // [rsp+40h] [rbp+7h] BYREF
  _BYTE v10[16]; // [rsp+50h] [rbp+17h] BYREF
  char v11[32]; // [rsp+60h] [rbp+27h] BYREF

  v7 = 0;
  strcpy(v11, "ScDeviceEnumStopCallback");
  v9[0] = v11;
  v9[1] = &v7;
  lambda_9efe97b5e8b49363dd7c16181ecef4ad_::operator()(v9);
  v7 = 1;
  v8 = v9;
  _m_prefetchw(&qword_18002BD40);
  v1 = qword_18002BD40;
  do
  {
    v2 = v1;
    v1 = _InterlockedCompareExchange64(&qword_18002BD40, v1 & 3, v1);
  }
  while ( v2 != v1 );
  while ( (v1 & 2) != 0 )
  {
    Sleep(0x64u);
    _m_prefetchw(&qword_18002BD40);
    v1 = qword_18002BD40;
    do
    {
      v3 = v1;
      v1 = _InterlockedCompareExchange64(&qword_18002BD40, v1 & 3, v1);
    }
    while ( v3 != v1 );
  }
  CSessionManager::RemoveAll();
  CRpcManager::Stop();
  CTaskCounter::Cleanup();
  CBusNode::Cleanup();
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  ServiceStatus.dwCurrentState = 1;
  *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
  if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
  {
    WppTraceIndent(v4, 2);
    v4 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        (unsigned int)&WPP_cc5e31c4c3a13497f43cc016dcb7f87d_Traceguids,
        (_DWORD)WPP_pszIndent,
        LastError);
    }
  }
  if ( (Microsoft_Windows_SmartCard_DeviceEnumEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(v4, SCDEVICEENUM_SERVICE_STOP, v5, 1, v10);
  McGenEventUnregister_EventUnregister();
  WppTraceUnwinder__lambda_9efe97b5e8b49363dd7c16181ecef4ad____::_WppTraceUnwinder__lambda_9efe97b5e8b49363dd7c16181ecef4ad____(&v8);
}

```

## disassembly

```asm
0x180006ad0  push    rbp
0x180006ad2  lea     rbp, [rsp-57h]
0x180006ad7  sub     rsp, 90h
0x180006ade  mov     rax, cs:__security_cookie
0x180006ae5  xor     rax, rsp
0x180006ae8  mov     [rbp+57h+var_10], rax
0x180006aec  mov     [rbp+57h+var_60], 0
0x180006af3  movups  xmm0, xmmword ptr cs:aScdeviceenumst; "ScDeviceEnumStopCallback"
0x180006afa  movups  xmmword ptr [rbp+57h+var_30], xmm0
0x180006afe  movups  xmm1, xmmword ptr cs:aScdeviceenumst+9; "numStopCallback"
0x180006b05  movups  xmmword ptr [rbp+57h+var_30+9], xmm1
0x180006b09  lea     rax, [rbp+57h+var_30]
0x180006b0d  mov     [rbp+57h+var_50], rax
0x180006b11  lea     rax, [rbp+57h+var_60]
0x180006b15  mov     [rbp+57h+var_48], rax
0x180006b19  lea     rcx, [rbp+57h+var_50]
0x180006b1d  call    _lambda_9efe97b5e8b49363dd7c16181ecef4ad___operator__
0x180006b22  mov     [rbp+57h+var_60], 1
0x180006b29  lea     rax, [rbp+57h+var_50]
0x180006b2d  mov     [rbp+57h+var_58], rax
0x180006b31  prefetchw byte ptr cs:qword_18002BD40
0x180006b38  mov     rax, cs:qword_18002BD40
0x180006b3f  mov     rcx, rax
0x180006b42  and     ecx, 3
0x180006b45  lock cmpxchg cs:qword_18002BD40, rcx
0x180006b4e  jnz     short loc_180006B3F
0x180006b50  jmp     short loc_180006B7C
0x180006b52  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180006b57  call    cs:__imp_Sleep
0x180006b5d  prefetchw byte ptr cs:qword_18002BD40
0x180006b64  mov     rax, cs:qword_18002BD40
0x180006b6b  mov     rcx, rax
0x180006b6e  and     ecx, 3
0x180006b71  lock cmpxchg cs:qword_18002BD40, rcx
0x180006b7a  jnz     short loc_180006B6B
0x180006b7c  test    al, 2
0x180006b7e  jnz     short loc_180006B52
0x180006b80  call    ?RemoveAll@CSessionManager@@SAXXZ; CSessionManager::RemoveAll(void)
0x180006b85  call    ?Stop@CRpcManager@@SAXXZ; CRpcManager::Stop(void)
0x180006b8a  call    ?Cleanup@CTaskCounter@@SAXXZ; CTaskCounter::Cleanup(void)
0x180006b8f  call    ?Cleanup@CBusNode@@SAXXZ; CBusNode::Cleanup(void)
0x180006b94  mov     rcx, cs:hObject; hObject
0x180006b9b  test    rcx, rcx
0x180006b9e  jz      short loc_180006BB1
0x180006ba0  call    cs:__imp_CloseHandle
0x180006ba6  mov     cs:hObject, 0
0x180006bb1  mov     cs:ServiceStatus.dwCurrentState, 1
0x180006bbb  mov     qword ptr cs:ServiceStatus.dwCheckPoint, 0
0x180006bc6  lea     rdx, ServiceStatus; lpServiceStatus
0x180006bcd  mov     rcx, qword ptr cs:hServiceStatus; hServiceStatus
0x180006bd4  call    cs:__imp_SetServiceStatus
0x180006bda  test    eax, eax
0x180006bdc  jnz     short loc_180006C32
0x180006bde  lea     edx, [rax+2]
0x180006be1  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180006be6  lea     rcx, WPP_GLOBAL_Control
0x180006bed  mov     rax, cs:WPP_GLOBAL_Control
0x180006bf4  cmp     rax, rcx
0x180006bf7  jz      short loc_180006C32
0x180006bf9  test    byte ptr [rax+1Ch], 1
0x180006bfd  jz      short loc_180006C32
0x180006bff  cmp     byte ptr [rax+19h], 2
0x180006c03  jb      short loc_180006C32
0x180006c05  call    cs:__imp_GetLastError
0x180006c0b  mov     edx, 1Ah
0x180006c10  mov     dword ptr [rsp+90h+var_70], eax
0x180006c14  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180006c1b  lea     r8, WPP_cc5e31c4c3a13497f43cc016dcb7f87d_Traceguids
0x180006c22  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c29  mov     rcx, [rcx+10h]
0x180006c2d  call    WPP_SF_sd
0x180006c32  test    cs:Microsoft_Windows_SmartCard_DeviceEnumEnableBits, 2
0x180006c39  jz      short loc_180006C56
0x180006c3b  lea     rax, [rbp+57h+var_40]
0x180006c3f  mov     [rsp+90h+var_70], rax
0x180006c44  mov     r9d, 1
0x180006c4a  lea     rdx, SCDEVICEENUM_SERVICE_STOP
0x180006c51  call    McGenEventWrite_EventWriteTransfer
0x180006c56  call    McGenEventUnregister_EventUnregister
0x180006c5b  nop
0x180006c5c  lea     rcx, [rbp+57h+var_58]
0x180006c60  call    WppTraceUnwinder__lambda_9efe97b5e8b49363dd7c16181ecef4ad_______WppTraceUnwinder__lambda_9efe97b5e8b49363dd7c16181ecef4ad____
0x180006c65  mov     rcx, [rbp+57h+var_10]
0x180006c69  xor     rcx, rsp; StackCookie
0x180006c6c  call    __security_check_cookie
0x180006c71  add     rsp, 90h
0x180006c78  pop     rbp
0x180006c79  retn
```
