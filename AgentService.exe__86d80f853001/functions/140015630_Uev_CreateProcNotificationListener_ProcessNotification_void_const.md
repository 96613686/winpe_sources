# Uev::CreateProcNotificationListener::ProcessNotification(void const *)

- ea: `0x140015630`
- end: `0x14001586d`
- name: `?ProcessNotification@CreateProcNotificationListener@Uev@@MEAAXPEBX@Z`
- size: `573`
- prototype: `void __fastcall(Uev::CreateProcNotificationListener *this, _DWORD *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, service_task`

## callees

- `0x140003e50`
- `0x140004ab4`
- `0x14000ac28`
- `0x14000ac88`
- `0x14000acc4`
- `0x14000d1d8`
- `0x14000d260`
- `0x14000ef6c`
- `0x1400131ec`
- `0x140014b0c`
- `0x140014da0`
- `0x140015630`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x1400156e3`
- `ADVAPI32!OpenProcessToken` at `0x1400156e3`
- `KERNEL32!Sleep` at `0x140015738`
- `KERNEL32!Sleep` at `0x140015738`
- `KERNEL32!ProcessIdToSessionId` at `0x140015693`
- `KERNEL32!ProcessIdToSessionId` at `0x140015693`
- `KERNEL32!OpenProcess` at `0x1400156b5`
- `KERNEL32!OpenProcess` at `0x1400156b5`
- `KERNEL32!GetLastError` at `0x140015769`
- `KERNEL32!GetLastError` at `0x140015789`
- `KERNEL32!GetLastError` at `0x1400157b7`
- `KERNEL32!GetLastError` at `0x140015769`
- `KERNEL32!GetLastError` at `0x140015789`
- `KERNEL32!GetLastError` at `0x1400157b7`

## string_xrefs

- `0x14001580f`: `Attempting to use an invalid handle.`
- `0x14001583e`: `Attempting to use an invalid handle.`
- `0x140015658`: `AgentService.CreateProcNotificationListener::ProcessNotification: Entry`
- `0x140015679`: `AgentService.CreateProcNotificationListener::ProcessNotification: ProcessId = 0x%X`
- `0x140015710`: `AgentService.CreateProcNotificationListener::ProcessNotification: Injecting AppAgent into process (PID %lu)`
- `0x140015726`: `AgentService.CreateProcNotificationListener::ProcessNotification: Delaying %lu milliseconds before injecting AppAgent`
- `0x140015771`: `AgentService.CreateProcNotificationListener::ProcessNotification: Failed to open process token, error = 0x%X`
- `0x140015791`: `AgentService.CreateProcNotificationListener::ProcessNotification: Failed to open process handle, error = 0x%X`
- `0x1400157a9`: `AgentService.CreateProcNotificationListener::ProcessNotification: Skipping injection for process in isolated session, sessionId = %X`
- `0x1400157bf`: `AgentService.CreateProcNotificationListener::ProcessNotification: Failed to get session ID from ProcessId, error = 0x%X`
- `0x1400157ca`: `AgentService.CreateProcNotificationListener::ProcessNotification: Unexpected notification type, 0x%X`
- `0x1400157d8`: `AgentService.CreateProcNotificationListener::ProcessNotification: Invalid parameter`
- `0x1400157e4`: `AgentService.CreateProcNotificationListener::ProcessNotification: Exit`

## pseudocode

```c
void __fastcall Uev::CreateProcNotificationListener::ProcessNotification(
        Uev::CreateProcNotificationListener *this,
        _DWORD *a2)
{
  char *v4; // rbx
  Uev::CreateProcNotificationListener *v5; // rcx
  wchar_t *v6; // rcx
  char *v7; // [rsp+30h] [rbp-49h] BYREF
  _BYTE v8[40]; // [rsp+38h] [rbp-41h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+60h] [rbp-19h] BYREF
  DWORD pSessionId; // [rsp+A0h] [rbp+27h] BYREF
  HANDLE TokenHandle; // [rsp+A8h] [rbp+2Fh] BYREF

  DbgTrace<5>(L"AgentService.CreateProcNotificationListener::ProcessNotification: Entry");
  if ( !a2 )
  {
    DbgTrace<2>(L"AgentService.CreateProcNotificationListener::ProcessNotification: Invalid parameter");
    goto LABEL_22;
  }
  if ( *a2 != 1 )
  {
    v6 = (wchar_t *)L"AgentService.CreateProcNotificationListener::ProcessNotification: Unexpected notification type, 0x%X";
    goto LABEL_20;
  }
  DbgTraceFrmt<4,unsigned long>((wchar_t *)L"AgentService.CreateProcNotificationListener::ProcessNotification: ProcessId = 0x%X");
  pSessionId = 0;
  if ( !ProcessIdToSessionId(a2[1], &pSessionId) )
  {
    GetLastError();
    v6 = L"AgentService.CreateProcNotificationListener::ProcessNotification: Failed to get session ID from ProcessId, error = 0x%X";
LABEL_20:
    DbgTraceFrmtErr<long>(v6);
    goto LABEL_22;
  }
  if ( pSessionId )
  {
    v4 = (char *)OpenProcess(0x1FFFFFu, 0, a2[1]);
    v7 = v4;
    if ( (unsigned __int64)(v4 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      GetLastError();
      DbgTraceFrmtErr<long>((wchar_t *)L"AgentService.CreateProcNotificationListener::ProcessNotification: Failed to open "
                                        "process handle, error = 0x%X");
    }
    else
    {
      TokenHandle = (HANDLE)-1LL;
      if ( OpenProcessToken(v4, 0xBu, &TokenHandle) )
      {
        if ( (((unsigned __int64)TokenHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        {
          std::wstring::wstring(v8, L"Attempting to use an invalid handle.");
          Uev::SmartHandleException::SmartHandleException(pExceptionObject, v8);
          throw (Uev::SmartHandleException *)pExceptionObject;
        }
        if ( Uev::CreateProcNotificationListener::InjectIntoProcessNeeded(v5, v4, TokenHandle) )
        {
          DbgTraceFrmt<4,unsigned long>((wchar_t *)L"AgentService.CreateProcNotificationListener::ProcessNotification: Inj"
                                                    "ecting AppAgent into process (PID %lu)");
          if ( *((_DWORD *)this + 73) )
          {
            DbgTraceFrmt<4,unsigned long>((wchar_t *)L"AgentService.CreateProcNotificationListener::ProcessNotification: D"
                                                      "elaying %lu milliseconds before injecting AppAgent");
            Sleep(*((_DWORD *)this + 73));
          }
          if ( (((unsigned __int64)TokenHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
          {
            std::wstring::wstring(v8, L"Attempting to use an invalid handle.");
            Uev::SmartHandleException::SmartHandleException(pExceptionObject, v8);
            throw (Uev::SmartHandleException *)pExceptionObject;
          }
          Uev::CreateProcNotificationListener::InjectIntoProcess(this, a2[1], v4, TokenHandle, pSessionId);
        }
      }
      else
      {
        GetLastError();
        DbgTraceFrmtErr<long>((wchar_t *)L"AgentService.CreateProcNotificationListener::ProcessNotification: Failed to ope"
                                          "n process token, error = 0x%X");
      }
      Uev::SmartHandle<void *,&void Uev::CloseHandleWrapper(void *),-1>::~SmartHandle<void *,&void Uev::CloseHandleWrapper(void *),-1>(&TokenHandle);
    }
    Uev::SmartHandle<void *,&void Uev::CloseHandleWrapper(void *),-1>::~SmartHandle<void *,&void Uev::CloseHandleWrapper(void *),-1>(&v7);
  }
  else
  {
    DbgTraceFrmt<4,unsigned long>((wchar_t *)L"AgentService.CreateProcNotificationListener::ProcessNotification: Skipping "
                                              "injection for process in isolated session, sessionId = %X");
  }
LABEL_22:
  DbgTrace<5>(L"AgentService.CreateProcNotificationListener::ProcessNotification: Exit");
}

```

## disassembly

```asm
0x140015630  mov     [rsp-8+arg_10], rbx
0x140015635  push    rbp
0x140015636  push    rsi
0x140015637  push    rdi
0x140015638  lea     rbp, [rsp-47h]
0x14001563d  sub     rsp, 0C0h
0x140015644  mov     rax, cs:__security_cookie
0x14001564b  xor     rax, rsp
0x14001564e  mov     [rbp+57h+var_20], rax
0x140015652  mov     rdi, rdx
0x140015655  mov     rsi, rcx
0x140015658  lea     rcx, aAgentserviceCr; "AgentService.CreateProcNotificationList"...
0x14001565f  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x140015664  test    rdi, rdi
0x140015667  jz      loc_1400157D8
0x14001566d  cmp     dword ptr [rdi], 1
0x140015670  jnz     loc_1400157C8
0x140015676  mov     edx, [rdi+4]
0x140015679  lea     rcx, aAgentserviceCr_28; "AgentService.CreateProcNotificationList"...
0x140015680  call    ??$DbgTraceFrmt@$03K@@YAXPEB_WK@Z; DbgTraceFrmt<4,ulong>(wchar_t const *,ulong)
0x140015685  mov     [rbp+57h+pSessionId], 0
0x14001568c  lea     rdx, [rbp+57h+pSessionId]; pSessionId
0x140015690  mov     ecx, [rdi+4]; dwProcessId
0x140015693  call    cs:__imp_ProcessIdToSessionId
0x140015699  test    eax, eax
0x14001569b  jz      loc_1400157B7
0x1400156a1  xor     edx, edx; bInheritHandle
0x1400156a3  cmp     [rbp+57h+pSessionId], edx
0x1400156a6  jz      loc_1400157A9
0x1400156ac  mov     r8d, [rdi+4]; dwProcessId
0x1400156b0  mov     ecx, 1FFFFFh; dwDesiredAccess
0x1400156b5  call    cs:__imp_OpenProcess
0x1400156bb  mov     rbx, rax
0x1400156be  mov     [rbp+57h+var_A0], rax
0x1400156c2  dec     rax
0x1400156c5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400156c9  ja      loc_140015789
0x1400156cf  mov     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1400156d7  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x1400156db  mov     edx, 0Bh; DesiredAccess
0x1400156e0  mov     rcx, rbx; ProcessHandle
0x1400156e3  call    cs:__imp_OpenProcessToken
0x1400156e9  test    eax, eax
0x1400156eb  jz      short loc_140015769
0x1400156ed  mov     r8, [rbp+57h+TokenHandle]; void *
0x1400156f1  lea     rax, [r8+1]
0x1400156f5  test    rax, 0FFFFFFFFFFFFFFFEh
0x1400156fb  jz      loc_14001583E
0x140015701  mov     rdx, rbx; void *
0x140015704  call    ?InjectIntoProcessNeeded@CreateProcNotificationListener@Uev@@AEAA_NQEAX0@Z; Uev::CreateProcNotificationListener::InjectIntoProcessNeeded(void * const,void * const)
0x140015709  test    al, al
0x14001570b  jz      short loc_14001577E
0x14001570d  mov     edx, [rdi+4]
0x140015710  lea     rcx, aAgentserviceCr_30; "AgentService.CreateProcNotificationList"...
0x140015717  call    ??$DbgTraceFrmt@$03K@@YAXPEB_WK@Z; DbgTraceFrmt<4,ulong>(wchar_t const *,ulong)
0x14001571c  mov     edx, [rsi+124h]
0x140015722  test    edx, edx
0x140015724  jz      short loc_14001573E
0x140015726  lea     rcx, aAgentserviceCr_6; "AgentService.CreateProcNotificationList"...
0x14001572d  call    ??$DbgTraceFrmt@$03K@@YAXPEB_WK@Z; DbgTraceFrmt<4,ulong>(wchar_t const *,ulong)
0x140015732  mov     ecx, [rsi+124h]; dwMilliseconds
0x140015738  call    cs:__imp_Sleep
0x14001573e  mov     r9, [rbp+57h+TokenHandle]; void *
0x140015742  lea     rax, [r9+1]
0x140015746  test    rax, 0FFFFFFFFFFFFFFFEh
0x14001574c  jz      loc_14001580F
0x140015752  mov     eax, [rbp+57h+pSessionId]
0x140015755  mov     [rsp+0D0h+var_B0], eax; unsigned int
0x140015759  mov     r8, rbx; void *
0x14001575c  mov     edx, [rdi+4]; unsigned int
0x14001575f  mov     rcx, rsi; this
0x140015762  call    ?InjectIntoProcess@CreateProcNotificationListener@Uev@@AEAAXKQEAX0K@Z; Uev::CreateProcNotificationListener::InjectIntoProcess(ulong,void * const,void * const,ulong)
0x140015767  jmp     short loc_14001577E
0x140015769  call    cs:__imp_GetLastError
0x14001576f  mov     edx, eax
0x140015771  lea     rcx, aAgentserviceCr_15; "AgentService.CreateProcNotificationList"...
0x140015778  call    ??$DbgTraceFrmtErr@J@@YAXPEB_WJ@Z; DbgTraceFrmtErr<long>(wchar_t const *,long)
0x14001577d  nop
0x14001577e  lea     rcx, [rbp+57h+TokenHandle]
0x140015782  call    ??1?$SmartHandle@PEAX$1?CloseHandleWrapper@Uev@@YAXPEAX@Z$0?0@Uev@@QEAA@XZ; Uev::SmartHandle<void *,&Uev::CloseHandleWrapper(void *),-1>::~SmartHandle<void *,&Uev::CloseHandleWrapper(void *),-1>(void)
0x140015787  jmp     short loc_14001579E
0x140015789  call    cs:__imp_GetLastError
0x14001578f  mov     edx, eax
0x140015791  lea     rcx, aAgentserviceCr_19; "AgentService.CreateProcNotificationList"...
0x140015798  call    ??$DbgTraceFrmtErr@J@@YAXPEB_WJ@Z; DbgTraceFrmtErr<long>(wchar_t const *,long)
0x14001579d  nop
0x14001579e  lea     rcx, [rbp+57h+var_A0]
0x1400157a2  call    ??1?$SmartHandle@PEAX$1?CloseHandleWrapper@Uev@@YAXPEAX@Z$0?0@Uev@@QEAA@XZ; Uev::SmartHandle<void *,&Uev::CloseHandleWrapper(void *),-1>::~SmartHandle<void *,&Uev::CloseHandleWrapper(void *),-1>(void)
0x1400157a7  jmp     short loc_1400157E4
0x1400157a9  lea     rcx, aAgentserviceCr_3; "AgentService.CreateProcNotificationList"...
0x1400157b0  call    ??$DbgTraceFrmt@$03K@@YAXPEB_WK@Z; DbgTraceFrmt<4,ulong>(wchar_t const *,ulong)
0x1400157b5  jmp     short loc_1400157E4
0x1400157b7  call    cs:__imp_GetLastError
0x1400157bd  mov     edx, eax
0x1400157bf  lea     rcx, aAgentserviceCr_21; "AgentService.CreateProcNotificationList"...
0x1400157c6  jmp     short loc_1400157D1
0x1400157c8  mov     edx, [rdi]
0x1400157ca  lea     rcx, aAgentserviceCr_41; "AgentService.CreateProcNotificationList"...
0x1400157d1  call    ??$DbgTraceFrmtErr@J@@YAXPEB_WJ@Z; DbgTraceFrmtErr<long>(wchar_t const *,long)
0x1400157d6  jmp     short loc_1400157E4
0x1400157d8  lea     rcx, aAgentserviceCr_13; "AgentService.CreateProcNotificationList"...
0x1400157df  call    ??$DbgTrace@$01@@YAXPEB_W@Z; DbgTrace<2>(wchar_t const *)
0x1400157e4  lea     rcx, aAgentserviceCr_0; "AgentService.CreateProcNotificationList"...
0x1400157eb  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x1400157f0  mov     rcx, [rbp+57h+var_20]
0x1400157f4  xor     rcx, rsp; StackCookie
0x1400157f7  call    __security_check_cookie
0x1400157fc  mov     rbx, [rsp+0D0h+arg_10]
0x140015804  add     rsp, 0C0h
0x14001580b  pop     rdi
0x14001580c  pop     rsi
0x14001580d  pop     rbp
0x14001580e  retn
0x14001580f  lea     rdx, aAttemptingToUs; "Attempting to use an invalid handle."
0x140015816  lea     rcx, [rbp+57h+var_98]
0x14001581a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14001581f  nop
0x140015820  lea     rdx, [rbp+57h+var_98]
0x140015824  lea     rcx, [rbp+57h+pExceptionObject]
0x140015828  call    ??0SmartHandleException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::SmartHandleException::SmartHandleException(std::wstring const &)
0x14001582d  lea     rdx, _TI3?AVSmartHandleException@Uev@@; pThrowInfo
0x140015834  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140015838  call    _CxxThrowException_0
0x14001583e  lea     rdx, aAttemptingToUs; "Attempting to use an invalid handle."
0x140015845  lea     rcx, [rbp+57h+var_98]
0x140015849  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14001584e  nop
0x14001584f  lea     rdx, [rbp+57h+var_98]
0x140015853  lea     rcx, [rbp+57h+pExceptionObject]
0x140015857  call    ??0SmartHandleException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::SmartHandleException::SmartHandleException(std::wstring const &)
0x14001585c  lea     rdx, _TI3?AVSmartHandleException@Uev@@; pThrowInfo
0x140015863  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140015867  call    _CxxThrowException_0
```
