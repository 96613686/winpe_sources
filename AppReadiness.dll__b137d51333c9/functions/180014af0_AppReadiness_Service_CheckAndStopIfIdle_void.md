# AppReadiness::Service::CheckAndStopIfIdle(void)

- ea: `0x180014af0`
- end: `0x180014e23`
- name: `?CheckAndStopIfIdle@Service@AppReadiness@@QEAAXXZ`
- size: `819`
- prototype: `void __fastcall(AppReadiness::Service *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800148e0`

## callees

- `0x180002a48`
- `0x18000b488`
- `0x18001326c`
- `0x180014af0`
- `0x180021184`
- `0x1800239f0`
- `0x180026954`
- `0x180033138`
- `0x180034a7c`
- `0x180037780`
- `0x180038848`
- `0x18003e210`
- `0x18003eca8`
- `0x180047bf0`
- `0x180047e0c`
- `0x180048430`
- `0x18005a2b8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180014b95`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180014b95`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x180014cfc`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibraries` at `0x180014cfc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014be5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014be5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180014b47`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180014b47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180014dbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180014dbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014dc7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014dc7`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180014d94`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180014d94`
- `ntdll!RtlReportExceptionEx` at `0x180014de4`
- `ntdll!RtlReportExceptionEx` at `0x180014de4`

## string_xrefs

- `0x180014bf0`: `ProcessTasks`
- `0x180014daa`: `AppReadiness::Service::CheckAndStopIfIdle`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall AppReadiness::Service::CheckAndStopIfIdle(AppReadiness::Service *this)
{
  unsigned __int64 v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // rdx
  AppReadiness::User *v5; // rcx
  __int64 v6; // rsi
  __int64 v7; // r14
  const wchar_t *v8; // rsi
  unsigned __int8 v9; // r14
  char v10; // r15
  bool HasTasks; // r12
  AppReadiness::User **v12; // rdi
  __int64 v13; // r13
  char v14; // al
  unsigned int v15; // eax
  HANDLE CurrentThread; // rbx
  HANDLE CurrentProcess; // rax
  __int64 v18[3]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v19[3]; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v20[4]; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v21; // [rsp+70h] [rbp-90h]
  int v22; // [rsp+78h] [rbp-88h]
  CONTEXT ContextRecord; // [rsp+100h] [rbp+0h] BYREF

  if ( !AppReadiness::ServiceHandle::CheckState(this, 4u) )
    return;
  std::vector<std::pair<Microsoft::WRL::ComPtr<AppReadiness::ITask>,enum AppReadiness::Impl::BaseTaskGroup::TaskState>>::vector<std::pair<Microsoft::WRL::ComPtr<AppReadiness::ITask>,enum AppReadiness::Impl::BaseTaskGroup::TaskState>>(v18);
  AcquireSRWLockShared((PSRWLOCK)this + 19);
  v19[1] = (char *)this + 152;
  v2 = (__int64)(*((_QWORD *)this + 21) - *((_QWORD *)this + 20)) >> 3;
  v19[0] = v2;
  v3 = v18[0];
  if ( v2 > (v18[2] - v18[0]) >> 3 )
  {
    if ( v2 > 0x1FFFFFFFFFFFFFFFLL )
      std::_Xlength_error("vector too long");
    std::vector<Microsoft::WRL::ComPtr<AppReadiness::User>>::_Reallocate<0>(v18, v19);
    v3 = v18[0];
  }
  std::vector<Microsoft::WRL::ComPtr<AppReadiness::User>>::_Insert_counted_range<Microsoft::WRL::ComPtr<AppReadiness::User> *>(
    v18,
    v3,
    *((_QWORD *)this + 20),
    (__int64)(*((_QWORD *)this + 21) - *((_QWORD *)this + 20)) >> 3);
  v6 = *((_QWORD *)this + 23);
  v7 = *((_QWORD *)this + 24);
  if ( this != (AppReadiness::Service *)-152LL )
    ReleaseSRWLockShared((PSRWLOCK)this + 19);
  if ( v6 == v7 )
  {
    v8 = L"None";
    v9 = 1;
    if ( !*(_DWORD *)(Microsoft::WRL::Details::OutOfProcModuleBase<AppReadiness::AppReadinessModule>::Create() + 32) )
      goto LABEL_13;
    v8 = L"ExternalObjects";
  }
  else
  {
    v8 = L"ProcessTasks";
  }
  v9 = 0;
LABEL_13:
  v10 = 0;
  HasTasks = 0;
  v12 = (AppReadiness::User **)v18[0];
  v13 = v18[1];
  while ( v12 != (AppReadiness::User **)v13 )
  {
    if ( v9 && (AppReadiness::User::HasRunningTasks(*v12) || AppReadiness::User::HasPendingTasks(*v12)) )
    {
      v8 = (const wchar_t *)((char *)*v12 + 64);
      if ( *((_QWORD *)*v12 + 11) > 7u )
        v8 = *(const wchar_t **)v8;
      v9 = 0;
    }
    if ( !v10 )
    {
      v5 = *v12;
      v14 = *((_BYTE *)*v12 + 376);
      *((_BYTE *)*v12 + 376) = 0;
      if ( v14 || *((_BYTE *)v5 + 216) )
      {
        v10 = 1;
      }
      else if ( !HasTasks )
      {
        HasTasks = AppReadiness::User::HasTasks(*v12);
      }
    }
    if ( !v9 && v10 )
      break;
    ++v12;
  }
  if ( (Microsoft_Windows_AppReadinessEnableBits & 0x10) != 0 )
    McTemplateU0tz_EventWriteTransfer(v5, v4, v9, v8);
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_1a488d56553d326416ae367d34f06923_Traceguids);
    AppReadiness::Service::Stop(this);
  }
  else
  {
    CoFreeUnusedLibraries();
    if ( v10 || !HasTasks )
    {
      *((_DWORD *)this + 69) = 0;
    }
    else
    {
      v15 = *((_DWORD *)this + 69);
      *((_DWORD *)this + 69) = v15 + 1;
      if ( v15 > *((_DWORD *)this + 70) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_l(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_1a488d56553d326416ae367d34f06923_Traceguids);
        if ( (unsigned int)AppReadiness::GetRegistryIntWithDefault_0() == 1 )
        {
          memset_0(&ContextRecord, 0, sizeof(ContextRecord));
          memset_0(v20, 0, 0x98u);
          RtlCaptureContext(&ContextRecord);
          v20[0] = 1460;
          v20[1] = 1;
          v21 = L"AppReadiness::Service::CheckAndStopIfIdle";
          v22 = 0;
          CurrentThread = GetCurrentThread();
          CurrentProcess = GetCurrentProcess();
          RtlReportExceptionEx(v20, &ContextRecord, 14, CurrentProcess, CurrentThread);
        }
      }
    }
  }
  std::vector<Microsoft::WRL::ComPtr<AppReadiness::ITask>>::_Tidy(v18);
}

```

## disassembly

```asm
0x180014af0  push    rbp
0x180014af2  push    rbx
0x180014af3  push    rsi
0x180014af4  push    rdi
0x180014af5  push    r12
0x180014af7  push    r13
0x180014af9  push    r14
0x180014afb  push    r15
0x180014afd  lea     rbp, [rsp-4E8h]
0x180014b05  sub     rsp, 5E8h
0x180014b0c  mov     rax, cs:__security_cookie
0x180014b13  xor     rax, rsp
0x180014b16  mov     [rbp+520h+var_50], rax
0x180014b1d  mov     rbx, rcx
0x180014b20  mov     edx, 4; unsigned int
0x180014b25  call    ?CheckState@ServiceHandle@AppReadiness@@QEAA_NK@Z; AppReadiness::ServiceHandle::CheckState(ulong)
0x180014b2a  test    al, al
0x180014b2c  jz      loc_180014E00
0x180014b32  lea     rcx, [rsp+620h+var_5F0]
0x180014b37  call    ??0?$vector@U?$pair@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@W4TaskState@BaseTaskGroup@Impl@AppReadiness@@@std@@V?$allocator@U?$pair@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@W4TaskState@BaseTaskGroup@Impl@AppReadiness@@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<Microsoft::WRL::ComPtr<AppReadiness::ITask>,AppReadiness::Impl::BaseTaskGroup::TaskState>>::vector<std::pair<Microsoft::WRL::ComPtr<AppReadiness::ITask>,AppReadiness::Impl::BaseTaskGroup::TaskState>>(void)
0x180014b3c  nop
0x180014b3d  lea     rdi, [rbx+98h]
0x180014b44  mov     rcx, rdi; SRWLock
0x180014b47  call    cs:__imp_AcquireSRWLockShared
0x180014b4d  mov     [rsp+620h+var_5D0], rdi
0x180014b52  mov     rcx, [rbx+0A8h]
0x180014b59  sub     rcx, [rbx+0A0h]
0x180014b60  sar     rcx, 3
0x180014b64  mov     [rsp+620h+var_5D8], rcx
0x180014b69  mov     rax, [rsp+620h+var_5E0]
0x180014b6e  mov     rdx, [rsp+620h+var_5F0]
0x180014b73  sub     rax, rdx
0x180014b76  sar     rax, 3
0x180014b7a  cmp     rcx, rax
0x180014b7d  jbe     short loc_180014BB0
0x180014b7f  mov     rax, 1FFFFFFFFFFFFFFFh
0x180014b89  cmp     rcx, rax
0x180014b8c  jbe     short loc_180014B9C
0x180014b8e  lea     rcx, aVectorTooLong; "vector too long"
0x180014b95  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180014b9c  lea     rdx, [rsp+620h+var_5D8]
0x180014ba1  lea     rcx, [rsp+620h+var_5F0]
0x180014ba6  call    ??$_Reallocate@$0A@@?$vector@V?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@@std@@@std@@AEAAXAEA_K@Z; std::vector<Microsoft::WRL::ComPtr<AppReadiness::User>>::_Reallocate<0>(unsigned __int64 &)
0x180014bab  mov     rdx, [rsp+620h+var_5F0]
0x180014bb0  mov     r8, [rbx+0A0h]
0x180014bb7  mov     r9, [rbx+0A8h]
0x180014bbe  sub     r9, r8
0x180014bc1  sar     r9, 3
0x180014bc5  lea     rcx, [rsp+620h+var_5F0]
0x180014bca  call    ??$_Insert_counted_range@PEAV?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@@?$vector@V?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@@std@@@std@@@1@PEAV?$ComPtr@VUser@AppReadiness@@@WRL@Microsoft@@_K@Z; std::vector<Microsoft::WRL::ComPtr<AppReadiness::User>>::_Insert_counted_range<Microsoft::WRL::ComPtr<AppReadiness::User> *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<Microsoft::WRL::ComPtr<AppReadiness::User>>>>,Microsoft::WRL::ComPtr<AppReadiness::User> *,unsigned __int64)
0x180014bcf  mov     rsi, [rbx+0B8h]
0x180014bd6  mov     r14, [rbx+0C0h]
0x180014bdd  test    rdi, rdi
0x180014be0  jz      short loc_180014BEB
0x180014be2  mov     rcx, rdi; SRWLock
0x180014be5  call    cs:__imp_ReleaseSRWLockShared
0x180014beb  cmp     rsi, r14
0x180014bee  jz      short loc_180014BF9
0x180014bf0  lea     rsi, aProcesstasks; "ProcessTasks"
0x180014bf7  jmp     short loc_180014C15
0x180014bf9  lea     rsi, aNone_0; "None"
0x180014c00  mov     r14b, 1
0x180014c03  call    ?Create@?$OutOfProcModuleBase@VAppReadinessModule@AppReadiness@@@Details@WRL@Microsoft@@SAAEAVAppReadinessModule@AppReadiness@@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<AppReadiness::AppReadinessModule>::Create(void)
0x180014c08  cmp     dword ptr [rax+20h], 0
0x180014c0c  jz      short loc_180014C18
0x180014c0e  lea     rsi, aExternalobject; "ExternalObjects"
0x180014c15  xor     r14b, r14b
0x180014c18  xor     r15b, r15b
0x180014c1b  xor     r12b, r12b
0x180014c1e  mov     rdi, [rsp+620h+var_5F0]
0x180014c23  mov     r13, [rsp+620h+var_5E8]
0x180014c28  jmp     short loc_180014C9F
0x180014c2a  test    r14b, r14b
0x180014c2d  jz      short loc_180014C5B
0x180014c2f  mov     rcx, [rdi]; this
0x180014c32  call    ?HasRunningTasks@User@AppReadiness@@QEBA_NXZ; AppReadiness::User::HasRunningTasks(void)
0x180014c37  test    al, al
0x180014c39  jnz     short loc_180014C47
0x180014c3b  mov     rcx, [rdi]; this
0x180014c3e  call    ?HasPendingTasks@User@AppReadiness@@QEBA_NXZ; AppReadiness::User::HasPendingTasks(void)
0x180014c43  test    al, al
0x180014c45  jz      short loc_180014C5B
0x180014c47  mov     rsi, [rdi]
0x180014c4a  add     rsi, 40h ; '@'
0x180014c4e  cmp     qword ptr [rsi+18h], 7
0x180014c53  jbe     short loc_180014C58
0x180014c55  mov     rsi, [rsi]
0x180014c58  xor     r14b, r14b
0x180014c5b  test    r15b, r15b
0x180014c5e  jnz     short loc_180014C91
0x180014c60  mov     rcx, [rdi]
0x180014c63  mov     al, [rcx+178h]
0x180014c69  mov     [rcx+178h], r15b
0x180014c70  test    al, al
0x180014c72  jnz     short loc_180014C8E
0x180014c74  cmp     [rcx+0D8h], al
0x180014c7a  jnz     short loc_180014C8E
0x180014c7c  test    r12b, r12b
0x180014c7f  jnz     short loc_180014C91
0x180014c81  mov     rcx, [rdi]; this
0x180014c84  call    ?HasTasks@User@AppReadiness@@QEBA_NXZ; AppReadiness::User::HasTasks(void)
0x180014c89  mov     r12b, al
0x180014c8c  jmp     short loc_180014C91
0x180014c8e  mov     r15b, 1
0x180014c91  test    r14b, r14b
0x180014c94  jnz     short loc_180014C9B
0x180014c96  test    r15b, r15b
0x180014c99  jnz     short loc_180014CA4
0x180014c9b  add     rdi, 8
0x180014c9f  cmp     rdi, r13
0x180014ca2  jnz     short loc_180014C2A
0x180014ca4  test    byte ptr cs:Microsoft_Windows_AppReadinessEnableBits, 10h
0x180014cab  jz      short loc_180014CB9
0x180014cad  movzx   r8d, r14b
0x180014cb1  mov     r9, rsi
0x180014cb4  call    McTemplateU0tz_EventWriteTransfer
0x180014cb9  test    r14b, r14b
0x180014cbc  jz      short loc_180014CFC
0x180014cbe  lea     rax, WPP_GLOBAL_Control
0x180014cc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ccc  cmp     rcx, rax
0x180014ccf  jz      short loc_180014CEF
0x180014cd1  test    byte ptr [rcx+1Ch], 4
0x180014cd5  jz      short loc_180014CEF
0x180014cd7  mov     edx, 1Dh
0x180014cdc  mov     r9, rsi
0x180014cdf  lea     r8, WPP_1a488d56553d326416ae367d34f06923_Traceguids
0x180014ce6  mov     rcx, [rcx+10h]
0x180014cea  call    WPP_SF_S
0x180014cef  mov     rcx, rbx; this
0x180014cf2  call    ?Stop@Service@AppReadiness@@QEAAXXZ; AppReadiness::Service::Stop(void)
0x180014cf7  jmp     loc_180014DF6
0x180014cfc  call    cs:__imp_CoFreeUnusedLibraries
0x180014d02  test    r15b, r15b
0x180014d05  jnz     loc_180014DEC
0x180014d0b  test    r12b, r12b
0x180014d0e  jz      loc_180014DEC
0x180014d14  mov     eax, [rbx+114h]
0x180014d1a  lea     r9d, [rax+1]
0x180014d1e  mov     [rbx+114h], r9d
0x180014d25  cmp     eax, [rbx+118h]
0x180014d2b  jbe     loc_180014DF6
0x180014d31  lea     rax, WPP_GLOBAL_Control
0x180014d38  mov     rcx, cs:WPP_GLOBAL_Control
0x180014d3f  cmp     rcx, rax
0x180014d42  jz      short loc_180014D5F
0x180014d44  test    byte ptr [rcx+1Ch], 4
0x180014d48  jz      short loc_180014D5F
0x180014d4a  mov     edx, 1Eh
0x180014d4f  lea     r8, WPP_1a488d56553d326416ae367d34f06923_Traceguids
0x180014d56  mov     rcx, [rcx+10h]
0x180014d5a  call    WPP_SF_l
0x180014d5f  call    AppReadiness__GetRegistryIntWithDefault_0
0x180014d64  cmp     eax, 1
0x180014d67  jnz     loc_180014DF6
0x180014d6d  xor     edx, edx; Val
0x180014d6f  mov     r8d, 4D0h; Size
0x180014d75  lea     rcx, [rbp+520h+ContextRecord]; void *
0x180014d79  call    memset_0
0x180014d7e  xor     edx, edx; Val
0x180014d80  mov     r8d, 98h; Size
0x180014d86  lea     rcx, [rsp+620h+var_5C0]; void *
0x180014d8b  call    memset_0
0x180014d90  lea     rcx, [rbp+520h+ContextRecord]; ContextRecord
0x180014d94  call    cs:__imp_RtlCaptureContext
0x180014d9a  mov     [rsp+620h+var_5C0], 5B4h
0x180014da2  mov     [rsp+620h+var_5BC], 1
0x180014daa  lea     rax, aAppreadinessSe_8; "AppReadiness::Service::CheckAndStopIfId"...
0x180014db1  mov     [rsp+620h+var_5B0], rax
0x180014db6  mov     [rsp+620h+var_5A8], 0
0x180014dbe  call    cs:__imp_GetCurrentThread
0x180014dc4  mov     rbx, rax
0x180014dc7  call    cs:__imp_GetCurrentProcess
0x180014dcd  mov     [rsp+620h+var_600], rbx
0x180014dd2  mov     r9, rax
0x180014dd5  mov     r8d, 0Eh
0x180014ddb  lea     rdx, [rbp+520h+ContextRecord]
0x180014ddf  lea     rcx, [rsp+620h+var_5C0]
0x180014de4  call    cs:__imp_RtlReportExceptionEx
0x180014dea  jmp     short loc_180014DF6
0x180014dec  mov     dword ptr [rbx+114h], 0
0x180014df6  lea     rcx, [rsp+620h+var_5F0]
0x180014dfb  call    ?_Tidy@?$vector@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@@std@@@std@@AEAAXXZ; std::vector<Microsoft::WRL::ComPtr<AppReadiness::ITask>>::_Tidy(void)
0x180014e00  mov     rcx, [rbp+520h+var_50]
0x180014e07  xor     rcx, rsp; StackCookie
0x180014e0a  call    __security_check_cookie
0x180014e0f  add     rsp, 5E8h
0x180014e16  pop     r15
0x180014e18  pop     r14
0x180014e1a  pop     r13
0x180014e1c  pop     r12
0x180014e1e  pop     rdi
0x180014e1f  pop     rsi
0x180014e20  pop     rbx
0x180014e21  pop     rbp
0x180014e22  retn
```
