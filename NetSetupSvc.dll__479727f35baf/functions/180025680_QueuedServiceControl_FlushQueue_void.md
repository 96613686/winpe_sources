# QueuedServiceControl::FlushQueue(void)

- ea: `0x180025680`
- end: `0x1800259c7`
- name: `?FlushQueue@QueuedServiceControl@@QEAAXXZ`
- size: `839`
- prototype: `void __fastcall(QueuedServiceControl *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x180023560`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x180008854`
- `0x18000d384`
- `0x18000d954`
- `0x18000df60`
- `0x1800255dc`
- `0x180025620`
- `0x180025680`
- `0x180025a48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002579e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800257de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800258d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025916`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002579e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800257de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800258d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025916`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800258cc`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800258cc`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800256d8`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800256d8`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180025794`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180025794`

## pseudocode

```c
void __fastcall QueuedServiceControl::FlushQueue(QueuedServiceControl *this)
{
  QueuedServiceControl *v1; // rsi
  QueuedServiceControl **v2; // rdi
  SC_HANDLE v3; // rax
  _BYTE *v4; // rdx
  __int64 v5; // r8
  QueuedServiceControl *v6; // rbx
  QueuedServiceControl *v7; // r15
  const wchar_t *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rax
  __int64 v12; // r10
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // r10
  signed int LastError; // eax
  QueuedServiceControl *v18; // rsi
  QueuedServiceControl *v19; // r15
  const wchar_t *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rax
  __int64 v24; // r10
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rax
  __int64 v28; // r10
  signed int v29; // eax
  QueuedServiceControl *v30; // rbx
  int v31; // eax
  __int64 v32; // r10
  _BYTE v33[48]; // [rsp+0h] [rbp-258h] BYREF
  QueuedServiceControl *v34; // [rsp+30h] [rbp-228h]
  QueuedServiceControl *v35; // [rsp+38h] [rbp-220h]
  QueuedServiceControl *v36; // [rsp+40h] [rbp-218h]
  QueuedServiceControl **v37; // [rsp+48h] [rbp-210h]
  HResultException *v38; // [rsp+50h] [rbp-208h] BYREF
  _BYTE pExceptionObject[208]; // [rsp+60h] [rbp-1F8h] BYREF
  _BYTE v40[208]; // [rsp+130h] [rbp-128h] BYREF
  SC_HANDLE hService; // [rsp+200h] [rbp-58h] BYREF
  SC_HANDLE v42; // [rsp+208h] [rbp-50h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+210h] [rbp-48h] BYREF

  v1 = this;
  v36 = this;
  v2 = (QueuedServiceControl **)((char *)this + 32);
  v37 = (QueuedServiceControl **)((char *)this + 32);
  if ( *((_QWORD *)this + 4) != *((_QWORD *)this + 5) || *((_QWORD *)this + 1) != *((_QWORD *)this + 2) )
  {
    v3 = OpenSCManagerW(0, 0, 1u);
    if ( !v3 )
      Win32Exception::ThrowLastError();
    v42 = v3;
    v6 = *v2;
    v7 = v2[1];
    v35 = v7;
    while ( 1 )
    {
      v34 = v6;
      if ( v6 == v7 )
        break;
      v8 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v6, v4, v5);
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        SafeServiceHandle::SafeServiceHandle((SafeServiceHandle *)&hService, (struct SafeScmHandle *)&v42, v8, 0x20u);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v11 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v6, v9, v10);
          WPP_SF_S(*(_QWORD *)(v12 + 16), 10, WPP_3cacea0dcce83e086de39fd1f3b9e0cb_Traceguids, v11);
        }
        memset(&ServiceStatus, 0, sizeof(ServiceStatus));
        if ( !ControlService(hService, 1u, &ServiceStatus) && GetLastError() != 1062 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v15 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v6, v13, v14);
            WPP_SF_S(*(_QWORD *)(v16 + 16), 11, WPP_3cacea0dcce83e086de39fd1f3b9e0cb_Traceguids, v15);
          }
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          HResultException::HResultException((HResultException *)pExceptionObject, LastError);
          throw (HResultException *)pExceptionObject;
        }
        std::unique_ptr<void,SafeHandleCleanupIsCloseServiceHandle>::~unique_ptr<void,SafeHandleCleanupIsCloseServiceHandle>(&hService);
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &HResultException `RTTI Type Descriptor', &v38) )
        {
          v4 = v33;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            v31 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v34, v33, v5);
            WPP_SF_Sd(
              *(_QWORD *)(v32 + 16),
              12,
              (int)WPP_3cacea0dcce83e086de39fd1f3b9e0cb_Traceguids,
              v31,
              *((_DWORD *)v38 + 8));
          }
          v6 = v34;
          v7 = v35;
          v1 = v36;
          v2 = v37;
          __eh34_try_continuation(0, &HResultException `RTTI Type Descriptor', &loc_18002581E);
        }
      }
      v6 = (QueuedServiceControl *)((char *)v6 + 32);
    }
    v18 = (QueuedServiceControl *)((char *)v1 + 8);
    v35 = v18;
    v30 = *(QueuedServiceControl **)v18;
    v19 = (QueuedServiceControl *)*((_QWORD *)v18 + 1);
    v36 = v19;
    while ( 1 )
    {
      v34 = v30;
      if ( v30 == v19 )
        break;
      v20 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v30, v4, v5);
      SafeServiceHandle::SafeServiceHandle((SafeServiceHandle *)&hService, (struct SafeScmHandle *)&v42, v20, 0x10u);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v23 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v30, v21, v22);
        WPP_SF_S(*(_QWORD *)(v24 + 16), 13, WPP_3cacea0dcce83e086de39fd1f3b9e0cb_Traceguids, v23);
      }
      if ( !StartServiceW(hService, 0, 0) && GetLastError() != 1056 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v27 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v30, v25, v26);
          WPP_SF_S(*(_QWORD *)(v28 + 16), 14, WPP_3cacea0dcce83e086de39fd1f3b9e0cb_Traceguids, v27);
        }
        v29 = GetLastError();
        if ( v29 > 0 )
          v29 = (unsigned __int16)v29 | 0x80070000;
        HResultException::HResultException((HResultException *)v40, v29);
        throw (HResultException *)v40;
      }
      std::unique_ptr<void,SafeHandleCleanupIsCloseServiceHandle>::~unique_ptr<void,SafeHandleCleanupIsCloseServiceHandle>(&hService);
      v30 = (QueuedServiceControl *)((char *)v30 + 32);
    }
    std::vector<std::wstring>::clear(v18);
    std::vector<std::wstring>::clear(v2);
    std::unique_ptr<void,SafeHandleCleanupIsCloseServiceHandle>::~unique_ptr<void,SafeHandleCleanupIsCloseServiceHandle>(&v42);
  }
}

```

## disassembly

```asm
0x180025680  mov     [rsp+arg_8], rbx
0x180025685  mov     [rsp+arg_10], rsi
0x18002568a  push    rdi
0x18002568b  push    r14
0x18002568d  push    r15
0x18002568f  sub     rsp, 240h
0x180025696  mov     rax, cs:__security_cookie
0x18002569d  xor     rax, rsp
0x1800256a0  mov     [rsp+258h+var_28], rax
0x1800256a8  mov     rsi, rcx
0x1800256ab  mov     [rsp+258h+var_218], rcx
0x1800256b0  lea     rdi, [rcx+20h]
0x1800256b4  mov     [rsp+258h+var_210], rdi
0x1800256b9  mov     rax, [rdi+8]
0x1800256bd  cmp     [rdi], rax
0x1800256c0  jnz     short loc_1800256D0
0x1800256c2  mov     rax, [rcx+10h]
0x1800256c6  cmp     [rcx+8], rax
0x1800256ca  jz      loc_18002599E
0x1800256d0  xor     edx, edx; lpDatabaseName
0x1800256d2  xor     ecx, ecx; lpMachineName
0x1800256d4  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800256d8  call    cs:__imp_OpenSCManagerW
0x1800256de  test    rax, rax
0x1800256e1  jnz     short loc_1800256E9
0x1800256e3  call    ?ThrowLastError@Win32Exception@@SAXXZ; Win32Exception::ThrowLastError(void)
0x1800256e9  mov     [rsp+258h+var_50], rax
0x1800256f1  mov     rbx, [rdi]
0x1800256f4  mov     r15, [rdi+8]
0x1800256f8  mov     [rsp+258h+var_220], r15
0x1800256fd  lea     r14, WPP_GLOBAL_Control
0x180025704  mov     [rsp+258h+var_228], rbx
0x180025709  cmp     rbx, r15
0x18002570c  jz      loc_180025842
0x180025712  mov     rcx, rbx
0x180025715  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002571a  mov     r9d, 20h ; ' '; unsigned int
0x180025720  mov     r8, rax; wchar_t *
0x180025723  lea     rdx, [rsp+258h+var_50]; struct SafeScmHandle *
0x18002572b  lea     rcx, [rsp+258h+hService]; this
0x180025733  call    ??0SafeServiceHandle@@QEAA@AEAVSafeScmHandle@@PEB_WK@Z; SafeServiceHandle::SafeServiceHandle(SafeScmHandle &,wchar_t const *,ulong)
0x180025738  nop
0x180025739  mov     r10, cs:WPP_GLOBAL_Control
0x180025740  cmp     r10, r14
0x180025743  jz      short loc_18002576C
0x180025745  cmp     byte ptr [r10+19h], 4
0x18002574a  jb      short loc_18002576C
0x18002574c  mov     rcx, rbx
0x18002574f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180025754  mov     edx, 0Ah
0x180025759  mov     r9, rax
0x18002575c  lea     r8, WPP_3cacea0dcce83e086de39fd1f3b9e0cb_Traceguids
0x180025763  mov     rcx, [r10+10h]
0x180025767  call    WPP_SF_S
0x18002576c  xorps   xmm0, xmm0
0x18002576f  movups  xmmword ptr [rsp+258h+ServiceStatus.dwServiceType], xmm0
0x180025777  movups  xmmword ptr [rsp+258h+ServiceStatus.dwWin32ExitCode], xmm0
0x18002577f  lea     r8, [rsp+258h+ServiceStatus]; lpServiceStatus
0x180025787  mov     edx, 1; dwControl
0x18002578c  mov     rcx, [rsp+258h+hService]; hService
0x180025794  call    cs:__imp_ControlService
0x18002579a  test    eax, eax
0x18002579c  jnz     short loc_18002580E
0x18002579e  call    cs:__imp_GetLastError
0x1800257a4  cmp     eax, 426h
0x1800257a9  jz      short loc_18002580E
0x1800257ab  mov     r10, cs:WPP_GLOBAL_Control
0x1800257b2  cmp     r10, r14
0x1800257b5  jz      short loc_1800257DE
0x1800257b7  cmp     byte ptr [r10+19h], 2
0x1800257bc  jb      short loc_1800257DE
0x1800257be  mov     rcx, rbx
0x1800257c1  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800257c6  mov     edx, 0Bh
0x1800257cb  mov     r9, rax
0x1800257ce  lea     r8, WPP_3cacea0dcce83e086de39fd1f3b9e0cb_Traceguids
0x1800257d5  mov     rcx, [r10+10h]
0x1800257d9  call    WPP_SF_S
0x1800257de  call    cs:__imp_GetLastError
0x1800257e4  test    eax, eax
0x1800257e6  jle     short loc_1800257F0
0x1800257e8  movzx   eax, ax
0x1800257eb  or      eax, 80070000h
0x1800257f0  mov     edx, eax; int
0x1800257f2  lea     rcx, [rsp+258h+pExceptionObject]; this
0x1800257f7  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x1800257fc  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180025803  lea     rcx, [rsp+258h+pExceptionObject]; pExceptionObject
0x180025808  call    _CxxThrowException_0
0x18002580e  lea     rcx, [rsp+258h+hService]
0x180025816  call    ??1?$unique_ptr@XUSafeHandleCleanupIsCloseServiceHandle@@@std@@QEAA@XZ; std::unique_ptr<void,SafeHandleCleanupIsCloseServiceHandle>::~unique_ptr<void,SafeHandleCleanupIsCloseServiceHandle>(void)
0x18002581b  nop
0x18002581c  jmp     short loc_180025839
0x18002581e  lea     r14, WPP_GLOBAL_Control
0x180025825  mov     rbx, [rsp+258h+var_228]
0x18002582a  mov     r15, [rsp+258h+var_220]
0x18002582f  mov     rsi, [rsp+258h+var_218]
0x180025834  mov     rdi, [rsp+258h+var_210]
0x180025839  add     rbx, 20h ; ' '
0x18002583d  jmp     loc_180025704
0x180025842  add     rsi, 8
0x180025846  mov     [rsp+258h+var_220], rsi
0x18002584b  mov     rbx, [rsi]
0x18002584e  mov     r15, [rsi+8]
0x180025852  mov     [rsp+258h+var_218], r15
0x180025857  mov     [rsp+258h+var_228], rbx
0x18002585c  cmp     rbx, r15
0x18002585f  jz      loc_180025980
0x180025865  mov     rcx, rbx
0x180025868  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002586d  mov     r9d, 10h; unsigned int
0x180025873  mov     r8, rax; wchar_t *
0x180025876  lea     rdx, [rsp+258h+var_50]; struct SafeScmHandle *
0x18002587e  lea     rcx, [rsp+258h+hService]; this
0x180025886  call    ??0SafeServiceHandle@@QEAA@AEAVSafeScmHandle@@PEB_WK@Z; SafeServiceHandle::SafeServiceHandle(SafeScmHandle &,wchar_t const *,ulong)
0x18002588b  nop
0x18002588c  mov     r10, cs:WPP_GLOBAL_Control
0x180025893  cmp     r10, r14
0x180025896  jz      short loc_1800258BF
0x180025898  cmp     byte ptr [r10+19h], 4
0x18002589d  jb      short loc_1800258BF
0x18002589f  mov     rcx, rbx
0x1800258a2  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800258a7  mov     edx, 0Dh
0x1800258ac  mov     r9, rax
0x1800258af  lea     r8, WPP_3cacea0dcce83e086de39fd1f3b9e0cb_Traceguids
0x1800258b6  mov     rcx, [r10+10h]
0x1800258ba  call    WPP_SF_S
0x1800258bf  xor     r8d, r8d; lpServiceArgVectors
0x1800258c2  xor     edx, edx; dwNumServiceArgs
0x1800258c4  mov     rcx, [rsp+258h+hService]; hService
0x1800258cc  call    cs:__imp_StartServiceW
0x1800258d2  test    eax, eax
0x1800258d4  jnz     short loc_18002594C
0x1800258d6  call    cs:__imp_GetLastError
0x1800258dc  cmp     eax, 420h
0x1800258e1  jz      short loc_18002594C
0x1800258e3  mov     r10, cs:WPP_GLOBAL_Control
0x1800258ea  cmp     r10, r14
0x1800258ed  jz      short loc_180025916
0x1800258ef  cmp     byte ptr [r10+19h], 2
0x1800258f4  jb      short loc_180025916
0x1800258f6  mov     rcx, rbx
0x1800258f9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800258fe  mov     edx, 0Eh
0x180025903  mov     r9, rax
0x180025906  lea     r8, WPP_3cacea0dcce83e086de39fd1f3b9e0cb_Traceguids
0x18002590d  mov     rcx, [r10+10h]
0x180025911  call    WPP_SF_S
0x180025916  call    cs:__imp_GetLastError
0x18002591c  test    eax, eax
0x18002591e  jle     short loc_180025928
0x180025920  movzx   eax, ax
0x180025923  or      eax, 80070000h
0x180025928  mov     edx, eax; int
0x18002592a  lea     rcx, [rsp+258h+var_128]; this
0x180025932  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180025937  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18002593e  lea     rcx, [rsp+258h+var_128]; pExceptionObject
0x180025946  call    _CxxThrowException_0
0x18002594c  lea     rcx, [rsp+258h+hService]
0x180025954  call    ??1?$unique_ptr@XUSafeHandleCleanupIsCloseServiceHandle@@@std@@QEAA@XZ; std::unique_ptr<void,SafeHandleCleanupIsCloseServiceHandle>::~unique_ptr<void,SafeHandleCleanupIsCloseServiceHandle>(void)
0x180025959  nop
0x18002595a  jmp     short loc_180025977
0x18002595c  lea     r14, WPP_GLOBAL_Control
0x180025963  mov     rbx, [rsp+258h+var_228]
0x180025968  mov     r15, [rsp+258h+var_218]
0x18002596d  mov     rdi, [rsp+258h+var_210]
0x180025972  mov     rsi, [rsp+258h+var_220]
0x180025977  add     rbx, 20h ; ' '
0x18002597b  jmp     loc_180025857
0x180025980  mov     rcx, rsi
0x180025983  call    ?clear@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x180025988  mov     rcx, rdi
0x18002598b  call    ?clear@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x180025990  nop
0x180025991  lea     rcx, [rsp+258h+var_50]
0x180025999  call    ??1?$unique_ptr@XUSafeHandleCleanupIsCloseServiceHandle@@@std@@QEAA@XZ; std::unique_ptr<void,SafeHandleCleanupIsCloseServiceHandle>::~unique_ptr<void,SafeHandleCleanupIsCloseServiceHandle>(void)
0x18002599e  mov     rcx, [rsp+258h+var_28]
0x1800259a6  xor     rcx, rsp; StackCookie
0x1800259a9  call    __security_check_cookie
0x1800259ae  lea     r11, [rsp+258h+var_18]
0x1800259b6  mov     rbx, [r11+28h]
0x1800259ba  mov     rsi, [r11+30h]
0x1800259be  mov     rsp, r11
0x1800259c1  pop     r15
0x1800259c3  pop     r14
0x1800259c5  pop     rdi
0x1800259c6  retn
```
