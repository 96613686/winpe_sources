# ScheduledTasksRegistration::SaveTaskDefinitionInRootFolder(ushort const *,ITaskService *,ITaskDefinition *)

- ea: `0x180020c58`
- end: `0x180020f75`
- name: `?SaveTaskDefinitionInRootFolder@ScheduledTasksRegistration@@AEAAJPEBGPEAUITaskService@@PEAUITaskDefinition@@@Z`
- size: `797`
- prototype: `__int64 __fastcall(ScheduledTasksRegistration *__hidden this, const unsigned __int16 *, struct ITaskService *, struct ITaskDefinition *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180020350`
- `0x180020760`

## callees

- `0x180007134`
- `0x18000a5c8`
- `0x18000a5e8`
- `0x18001136c`
- `0x180015478`
- `0x180018268`
- `0x180018c78`
- `0x18001cf50`
- `0x18001fad4`
- `0x18002027c`
- `0x180020c58`
- `0x18004e010`

## string_xrefs

- `0x180020c9c`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`
- `0x180020cda`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`
- `0x180020d16`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`
- `0x180020d97`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`
- `0x180020dda`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`
- `0x180020e91`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`
- `0x180020edb`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall ScheduledTasksRegistration::SaveTaskDefinitionInRootFolder(
        ScheduledTasksRegistration *this,
        const unsigned __int16 *a2,
        struct ITaskService *a3,
        struct ITaskDefinition *a4)
{
  unsigned int v8; // ebx
  struct ITaskServiceVtbl *lpVtbl; // rax
  int v10; // eax
  int CurrentUserSidString; // eax
  __int64 v12; // rdx
  unsigned int v13; // r14d
  int v14; // eax
  HRESULT (__stdcall *RegisterTaskDefinition)(ITaskFolder *, BSTR, ITaskDefinition *, LONG, VARIANT, VARIANT, TASK_LOGON_TYPE, VARIANT, IRegisteredTask **); // r10
  int v16; // eax
  int v17; // eax
  __int64 v18; // rdx
  int v20; // [rsp+20h] [rbp-99h]
  int v21; // [rsp+20h] [rbp-99h]
  struct ITaskFolder *v22; // [rsp+50h] [rbp-69h] BYREF
  LPWSTR StringSid; // [rsp+58h] [rbp-61h] BYREF
  __int64 v24; // [rsp+60h] [rbp-59h] BYREF
  __int64 v25; // [rsp+68h] [rbp-51h] BYREF
  unsigned __int16 *v26; // [rsp+70h] [rbp-49h] BYREF
  __int64 v27; // [rsp+78h] [rbp-41h] BYREF
  _QWORD v28[3]; // [rsp+80h] [rbp-39h] BYREF
  __int16 v29; // [rsp+A0h] [rbp-19h]
  _BYTE v30[22]; // [rsp+A2h] [rbp-17h]
  __int16 v31; // [rsp+C0h] [rbp+7h]
  _OWORD v32[4]; // [rsp+C2h] [rbp+9h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  __int64 v34; // [rsp+120h] [rbp+67h] BYREF

  wil::make_bstr_nothrow(&v27, *((_QWORD *)this + 2));
  if ( v27 )
  {
    lpVtbl = a3->lpVtbl;
    v22 = 0;
    v10 = ((__int64 (__fastcall *)(struct ITaskService *, __int64, struct ITaskFolder **))lpVtbl->GetFolder)(
            a3,
            v27,
            &v22);
    v8 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEB,
        (unsigned int)"shell\\oobe\\user\\dll\\scheduledtasksregistration.cpp",
        (const char *)(unsigned int)v10,
        v20);
LABEL_5:
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v22);
      goto LABEL_27;
    }
    StringSid = 0;
    CurrentUserSidString = GetCurrentUserSidString(&StringSid);
    v8 = CurrentUserSidString;
    if ( CurrentUserSidString >= 0 )
    {
      LODWORD(v34) = 0;
      CurrentUserSidString = ScheduledTasksRegistration::DeletePreviouslyRegisteredTaskIfPresent(
                               this,
                               a2,
                               StringSid,
                               v22,
                               (unsigned int *)&v34);
      v8 = CurrentUserSidString;
      if ( CurrentUserSidString >= 0 )
      {
        v24 = 0;
        v13 = v34;
        v21 = v34;
        v14 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                &v24,
                *((_QWORD *)this + 5),
                a2,
                StringSid);
        v8 = v14;
        if ( v14 >= 0 )
        {
          wil::make_bstr_nothrow(&v34, v24);
          if ( v34 )
          {
            v25 = 0;
            RegisterTaskDefinition = v22->lpVtbl->RegisterTaskDefinition;
            v25 = 0;
            v29 = 0;
            *(_OWORD *)v30 = *(_OWORD *)((char *)v28 + 2);
            *(_QWORD *)&v30[14] = v28[2];
            v31 = 0;
            v32[0] = *(_OWORD *)((char *)v28 + 2);
            *(_QWORD *)((char *)v32 + 14) = v28[2];
            LOWORD(v28[0]) = 0;
            v16 = ((__int64 (__fastcall *)(struct ITaskFolder *, __int64, struct ITaskDefinition *, __int64))RegisterTaskDefinition)(
                    v22,
                    v34,
                    a4,
                    6);
            v8 = v16;
            if ( v16 >= 0 )
            {
              v26 = 0;
              v17 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                      &v26,
                      L"%s\\%s",
                      *((_QWORD *)this + 3),
                      a2);
              v8 = v17;
              if ( v17 >= 0 )
              {
                v17 = SHRegSetDWORD(HKEY_CURRENT_USER, v26, *((const unsigned __int16 **)this + 4), v13);
                v8 = v17;
                if ( v17 >= 0 )
                {
                  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v26);
                  wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v25);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v34);
                  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v24);
                  wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(&StringSid);
                  wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v22);
                  v8 = 0;
                  goto LABEL_27;
                }
                v18 = 255;
              }
              else
              {
                v18 = 254;
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v18,
                (unsigned int)"shell\\oobe\\user\\dll\\scheduledtasksregistration.cpp",
                (const char *)(unsigned int)v17,
                (int)v28);
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v26);
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xFA,
                (unsigned int)"shell\\oobe\\user\\dll\\scheduledtasksregistration.cpp",
                (const char *)(unsigned int)v16,
                (int)v28);
            }
            wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v25);
          }
          else
          {
            v8 = -2147024882;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xF5,
              (unsigned int)"shell\\oobe\\user\\dll\\scheduledtasksregistration.cpp",
              (const char *)0x8007000ELL,
              v21);
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v34);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xF3,
            (unsigned int)"shell\\oobe\\user\\dll\\scheduledtasksregistration.cpp",
            (const char *)(unsigned int)v14,
            v21);
        }
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v24);
        goto LABEL_9;
      }
      v12 = 241;
    }
    else
    {
      v12 = 239;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"shell\\oobe\\user\\dll\\scheduledtasksregistration.cpp",
      (const char *)(unsigned int)CurrentUserSidString,
      v20);
LABEL_9:
    wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(&StringSid);
    goto LABEL_5;
  }
  v8 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE9,
    (unsigned int)"shell\\oobe\\user\\dll\\scheduledtasksregistration.cpp",
    (const char *)0x8007000ELL,
    v20);
LABEL_27:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v27);
  return v8;
}

```

## disassembly

```asm
0x180020c58  push    rbp
0x180020c5a  push    rbx
0x180020c5b  push    rsi
0x180020c5c  push    rdi
0x180020c5d  push    r14
0x180020c5f  push    r15
0x180020c61  lea     rbp, [rsp-2Fh]
0x180020c66  sub     rsp, 0E8h
0x180020c6d  mov     r15, r9
0x180020c70  mov     rbx, r8
0x180020c73  mov     rsi, rdx
0x180020c76  mov     rdi, rcx
0x180020c79  mov     rdx, [rcx+10h]
0x180020c7d  lea     rcx, [rbp+57h+var_98]
0x180020c81  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x180020c86  nop
0x180020c87  mov     rdx, [rbp+57h+var_98]
0x180020c8b  test    rdx, rdx
0x180020c8e  jnz     short loc_180020CB2
0x180020c90  mov     rcx, [rbp+5Fh]; this
0x180020c94  mov     ebx, 8007000Eh
0x180020c99  mov     r9d, ebx; char *
0x180020c9c  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x180020ca3  mov     edx, 0E9h; void *
0x180020ca8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020cad  jmp     loc_180020F5A
0x180020cb2  mov     rax, [rbx]
0x180020cb5  mov     [rbp+57h+var_C0], 0
0x180020cbd  lea     r8, [rbp+57h+var_C0]
0x180020cc1  mov     rcx, rbx
0x180020cc4  mov     rax, [rax+38h]
0x180020cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ccd  mov     ebx, eax
0x180020ccf  test    eax, eax
0x180020cd1  jns     short loc_180020CFA
0x180020cd3  mov     rcx, [rbp+5Fh]; this
0x180020cd7  mov     r9d, eax; char *
0x180020cda  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x180020ce1  mov     edx, 0EBh; void *
0x180020ce6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020ceb  nop
0x180020cec  lea     rcx, [rbp+57h+var_C0]
0x180020cf0  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180020cf5  jmp     loc_180020F5A
0x180020cfa  mov     [rbp+57h+StringSid], 0
0x180020d02  lea     rcx, [rbp+57h+StringSid]; StringSid
0x180020d06  call    ?GetCurrentUserSidString@@YAJPEAPEAG@Z; GetCurrentUserSidString(ushort * *)
0x180020d0b  mov     ebx, eax
0x180020d0d  test    eax, eax
0x180020d0f  jns     short loc_180020D35
0x180020d11  mov     edx, 0EFh; void *
0x180020d16  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x180020d1d  mov     r9d, eax; char *
0x180020d20  mov     rcx, [rbp+5Fh]; this
0x180020d24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020d29  nop
0x180020d2a  lea     rcx, [rbp+57h+StringSid]
0x180020d2e  call    ??1?$unique_storage@U?$resource_policy@PEAU_TOKEN_GROUPS@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(void)
0x180020d33  jmp     short loc_180020CEC
0x180020d35  mov     dword ptr [rbp+57h+arg_0], 0
0x180020d3c  lea     rax, [rbp+57h+arg_0]
0x180020d40  mov     [rsp+110h+var_F0], rax; unsigned int *
0x180020d45  mov     r9, [rbp+57h+var_C0]; struct ITaskFolder *
0x180020d49  mov     r8, [rbp+57h+StringSid]; unsigned __int16 *
0x180020d4d  mov     rdx, rsi; unsigned __int16 *
0x180020d50  mov     rcx, rdi; this
0x180020d53  call    ?DeletePreviouslyRegisteredTaskIfPresent@ScheduledTasksRegistration@@AEAAJPEBG0PEAUITaskFolder@@PEAK@Z; ScheduledTasksRegistration::DeletePreviouslyRegisteredTaskIfPresent(ushort const *,ushort const *,ITaskFolder *,ulong *)
0x180020d58  mov     ebx, eax
0x180020d5a  test    eax, eax
0x180020d5c  jns     short loc_180020D65
0x180020d5e  mov     edx, 0F1h
0x180020d63  jmp     short loc_180020D16
0x180020d65  mov     [rbp+57h+var_B0], 0
0x180020d6d  mov     r14d, dword ptr [rbp+57h+arg_0]
0x180020d71  mov     dword ptr [rsp+110h+var_F0], r14d; int
0x180020d76  mov     r9, [rbp+57h+StringSid]
0x180020d7a  mov     r8, rsi
0x180020d7d  mov     rdx, [rdi+28h]
0x180020d81  lea     rcx, [rbp+57h+var_B0]
0x180020d85  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180020d8a  mov     ebx, eax
0x180020d8c  test    eax, eax
0x180020d8e  jns     short loc_180020DB7
0x180020d90  mov     rcx, [rbp+5Fh]; this
0x180020d94  mov     r9d, eax; char *
0x180020d97  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x180020d9e  mov     edx, 0F3h; void *
0x180020da3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020da8  nop
0x180020da9  lea     rcx, [rbp+57h+var_B0]
0x180020dad  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180020db2  jmp     loc_180020D2A
0x180020db7  mov     rdx, [rbp+57h+var_B0]
0x180020dbb  lea     rcx, [rbp+57h+arg_0]
0x180020dbf  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x180020dc4  nop
0x180020dc5  mov     rdx, [rbp+57h+arg_0]
0x180020dc9  test    rdx, rdx
0x180020dcc  jnz     short loc_180020DF7
0x180020dce  mov     rcx, [rbp+5Fh]; this
0x180020dd2  mov     ebx, 8007000Eh
0x180020dd7  mov     r9d, ebx; char *
0x180020dda  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x180020de1  mov     edx, 0F5h; void *
0x180020de6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020deb  nop
0x180020dec  lea     rcx, [rbp+57h+arg_0]
0x180020df0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180020df5  jmp     short loc_180020DA9
0x180020df7  mov     [rbp+57h+var_A8], 0
0x180020dff  mov     rcx, [rbp+57h+var_C0]
0x180020e03  mov     rax, [rcx]
0x180020e06  mov     r10, [rax+88h]
0x180020e0d  mov     [rbp+57h+var_A8], 0
0x180020e15  xor     eax, eax
0x180020e17  mov     [rbp+57h+var_70], ax
0x180020e1b  movups  xmm1, xmmword ptr [rbp+57h+var_90+2]
0x180020e1f  movups  xmmword ptr [rbp+57h+var_6E], xmm1
0x180020e23  movsd   xmm0, qword ptr [rbp+57h+var_90+10h]
0x180020e28  movsd   qword ptr [rbp+57h+var_6E+0Eh], xmm0
0x180020e2d  mov     [rbp+57h+var_50], ax
0x180020e31  movups  [rbp+57h+var_4E], xmm1
0x180020e35  movsd   qword ptr [rbp+57h+var_4E+0Eh], xmm0
0x180020e3a  mov     word ptr [rbp+57h+var_90], ax
0x180020e3e  movups  xmmword ptr [rbp+57h+var_90+2], xmm1
0x180020e42  movsd   qword ptr [rbp+57h+var_90+10h], xmm0
0x180020e47  lea     rax, [rbp+57h+var_A8]
0x180020e4b  mov     [rsp+110h+var_D0], rax
0x180020e50  lea     rax, [rbp+57h+var_70]
0x180020e54  mov     [rsp+110h+var_D8], rax
0x180020e59  mov     [rsp+110h+var_E0], 3
0x180020e61  lea     rax, [rbp+57h+var_50]
0x180020e65  mov     [rsp+110h+var_E8], rax
0x180020e6a  lea     rax, [rbp+57h+var_90]
0x180020e6e  mov     [rsp+110h+var_F0], rax; int
0x180020e73  mov     r9d, 6
0x180020e79  mov     r8, r15
0x180020e7c  mov     rax, r10
0x180020e7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e84  mov     ebx, eax
0x180020e86  test    eax, eax
0x180020e88  jns     short loc_180020EB1
0x180020e8a  mov     rcx, [rbp+5Fh]; this
0x180020e8e  mov     r9d, eax; char *
0x180020e91  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x180020e98  mov     edx, 0FAh; void *
0x180020e9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020ea2  nop
0x180020ea3  lea     rcx, [rbp+57h+var_A8]
0x180020ea7  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180020eac  jmp     loc_180020DEC
0x180020eb1  mov     [rbp+57h+var_A0], 0
0x180020eb9  mov     r9, rsi
0x180020ebc  mov     r8, [rdi+18h]
0x180020ec0  lea     rdx, aSS_0; "%s\\%s"
0x180020ec7  lea     rcx, [rbp+57h+var_A0]
0x180020ecb  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180020ed0  mov     ebx, eax
0x180020ed2  test    eax, eax
0x180020ed4  jns     short loc_180020EF9
0x180020ed6  mov     edx, 0FEh; void *
0x180020edb  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x180020ee2  mov     r9d, eax; char *
0x180020ee5  mov     rcx, [rbp+5Fh]; this
0x180020ee9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020eee  lea     rcx, [rbp+57h+var_A0]
0x180020ef2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180020ef7  jmp     short loc_180020EA3
0x180020ef9  mov     r9d, r14d; unsigned int
0x180020efc  mov     r8, [rdi+20h]; unsigned __int16 *
0x180020f00  mov     rdx, [rbp+57h+var_A0]; unsigned __int16 *
0x180020f04  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x180020f0b  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180020f10  mov     ebx, eax
0x180020f12  test    eax, eax
0x180020f14  jns     short loc_180020F1D
0x180020f16  mov     edx, 0FFh
0x180020f1b  jmp     short loc_180020EDB
0x180020f1d  lea     rcx, [rbp+57h+var_A0]
0x180020f21  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180020f26  nop
0x180020f27  lea     rcx, [rbp+57h+var_A8]
0x180020f2b  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180020f30  nop
0x180020f31  lea     rcx, [rbp+57h+arg_0]
0x180020f35  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180020f3a  nop
0x180020f3b  lea     rcx, [rbp+57h+var_B0]
0x180020f3f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180020f44  nop
0x180020f45  lea     rcx, [rbp+57h+StringSid]
0x180020f49  call    ??1?$unique_storage@U?$resource_policy@PEAU_TOKEN_GROUPS@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(void)
0x180020f4e  nop
0x180020f4f  lea     rcx, [rbp+57h+var_C0]
0x180020f53  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180020f58  xor     ebx, ebx
0x180020f5a  lea     rcx, [rbp+57h+var_98]
0x180020f5e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180020f63  mov     eax, ebx
0x180020f65  add     rsp, 0E8h
0x180020f6c  pop     r15
0x180020f6e  pop     r14
0x180020f70  pop     rdi
0x180020f71  pop     rsi
0x180020f72  pop     rbx
0x180020f73  pop     rbp
0x180020f74  retn
```
