# ScheduledTasksRegistration::RegisterRegistrationTriggeredTask(HSTRING__ *,HSTRING__ *,HSTRING__ *)

- ea: `0x180020350`
- end: `0x18002075a`
- name: `?RegisterRegistrationTriggeredTask@ScheduledTasksRegistration@@UEAAJPEAUHSTRING__@@00@Z`
- size: `1034`
- prototype: `int(ScheduledTasksRegistration *__hidden this, HSTRING, HSTRING, HSTRING)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180007134`
- `0x18001136c`
- `0x180018c78`
- `0x18001cf50`
- `0x18001fa48`
- `0x18001fed4`
- `0x180020350`
- `0x180020b70`
- `0x180020c58`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180020378`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002058a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180020639`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180020378`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002058a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180020639`

## string_xrefs

- `0x18002040e`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`
- `0x18002044d`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`
- `0x1800204a6`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`
- `0x18002050e`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`
- `0x180020567`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`
- `0x1800205b2`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`
- `0x180020614`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`
- `0x180020662`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`
- `0x1800206a0`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall ScheduledTasksRegistration::RegisterRegistrationTriggeredTask(
        ScheduledTasksRegistration *this,
        HSTRING a2,
        HSTRING a3,
        HSTRING a4)
{
  const unsigned __int16 *StringRawBuffer; // rsi
  const unsigned __int16 *v8; // rdx
  const unsigned __int16 *v9; // rcx
  const struct _GUID *v10; // r8
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  ScheduledTasksRegistration *v14; // rcx
  int v15; // eax
  struct ITaskDefinition *v16; // rbx
  struct ITaskDefinitionVtbl *lpVtbl; // rax
  int v18; // eax
  int v19; // edi
  __int64 v20; // rax
  int v21; // eax
  __int64 (__fastcall **v22)(_QWORD, GUID *, __int64 *); // rax
  int v23; // eax
  PCWSTR v24; // rax
  int v25; // eax
  PCWSTR v26; // rax
  __int64 v27; // r9
  __int64 v28; // rdx
  ScheduledTasksRegistration *v29; // rcx
  __int64 v30; // rdx
  int v31; // eax
  _QWORD *v33; // [rsp+20h] [rbp-A9h]
  __int64 *v34; // [rsp+30h] [rbp-99h] BYREF
  struct ITaskDefinition *v35; // [rsp+38h] [rbp-91h] BYREF
  __int64 v36; // [rsp+40h] [rbp-89h] BYREF
  __int64 (__fastcall ***v37)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-81h] BYREF
  __int64 v38; // [rsp+50h] [rbp-79h] BYREF
  __int64 v39; // [rsp+58h] [rbp-71h] BYREF
  struct ITaskService *v40[2]; // [rsp+60h] [rbp-69h] BYREF
  __int16 v41; // [rsp+70h] [rbp-59h] BYREF
  _BYTE v42[22]; // [rsp+72h] [rbp-57h]
  _QWORD v43[4]; // [rsp+90h] [rbp-39h] BYREF
  __int16 v44; // [rsp+B0h] [rbp-19h] BYREF
  _BYTE v45[22]; // [rsp+B2h] [rbp-17h]
  __int16 v46; // [rsp+D0h] [rbp+7h] BYREF
  _OWORD v47[4]; // [rsp+D2h] [rbp+9h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  v40[0] = 0;
  v11 = SHExtCoCreateFromRegKey(v9, v8, v10, (void **)v40);
  v12 = v11;
  if ( v11 >= 0 )
  {
    LOWORD(v43[0]) = 0;
    *(_OWORD *)((char *)v43 + 2) = *(_OWORD *)v42;
    v43[2] = *(_QWORD *)&v42[14];
    v44 = 0;
    *(_OWORD *)v45 = *(_OWORD *)v42;
    *(_QWORD *)&v45[14] = *(_QWORD *)&v42[14];
    v46 = 0;
    v47[0] = *(_OWORD *)v42;
    *(_QWORD *)((char *)v47 + 14) = *(_QWORD *)&v42[14];
    v41 = 0;
    v33 = v43;
    v11 = ((__int64 (__fastcall *)(struct ITaskService *, __int16 *, __int16 *, __int16 *))v40[0]->lpVtbl->Connect)(
            v40[0],
            &v41,
            &v46,
            &v44);
    v12 = v11;
    if ( v11 < 0 )
    {
      v13 = 62;
      goto LABEL_5;
    }
    v35 = 0;
    v15 = ScheduledTasksRegistration::GenerateTaskDefinitionForCurrentUser(v14, StringRawBuffer, v40[0], &v35);
    v12 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x42,
        (unsigned int)"shell\\oobe\\user\\dll\\scheduledtasksregistration.cpp",
        (const char *)(unsigned int)v15,
        (int)v43);
LABEL_8:
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v35);
      goto LABEL_35;
    }
    v34 = 0;
    v16 = v35;
    lpVtbl = v35->lpVtbl;
    v34 = 0;
    v18 = ((__int64 (__fastcall *)(struct ITaskDefinition *, __int64 **))lpVtbl->get_Triggers)(v35, &v34);
    v19 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x44,
        (unsigned int)"shell\\oobe\\user\\dll\\scheduledtasksregistration.cpp",
        (const char *)(unsigned int)v18,
        (int)v43);
LABEL_11:
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v34);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v35);
      v12 = v19;
      goto LABEL_35;
    }
    v37 = 0;
    v20 = *v34;
    v37 = 0;
    v21 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD))(v20 + 80))(v34, 7, &v37);
    v19 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x46,
        (unsigned int)"shell\\oobe\\user\\dll\\scheduledtasksregistration.cpp",
        (const char *)(unsigned int)v21,
        (int)v43);
LABEL_14:
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v37);
      goto LABEL_11;
    }
    v36 = 0;
    v22 = *v37;
    v36 = 0;
    v23 = (*v22)(v37, &GUID_4c8fec3a_c218_4e0c_b23d_629024db91a2, &v36);
    v19 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x48,
        (unsigned int)"shell\\oobe\\user\\dll\\scheduledtasksregistration.cpp",
        (const char *)(unsigned int)v23,
        (int)v43);
LABEL_17:
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v36);
      goto LABEL_14;
    }
    v24 = WindowsGetStringRawBuffer(a3, 0);
    wil::make_bstr_nothrow(&v38, v24);
    if ( !v38 )
    {
      v12 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4A,
        (unsigned int)"shell\\oobe\\user\\dll\\scheduledtasksregistration.cpp",
        (const char *)0x8007000ELL,
        (int)v43);
LABEL_20:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v38);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v36);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v37);
      wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v34);
      goto LABEL_8;
    }
    v25 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 168LL))(v36);
    v19 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4B,
        (unsigned int)"shell\\oobe\\user\\dll\\scheduledtasksregistration.cpp",
        (const char *)(unsigned int)v25,
        (int)v43);
LABEL_23:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v38);
      goto LABEL_17;
    }
    v26 = WindowsGetStringRawBuffer(a4, 0);
    wil::make_bstr_nothrow(&v39, v26);
    if ( !v39 )
    {
      v12 = -2147024882;
      v27 = 2147942414LL;
      v28 = 77;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"shell\\oobe\\user\\dll\\scheduledtasksregistration.cpp",
        (const char *)v27,
        (int)v43);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v39);
      goto LABEL_20;
    }
    v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 136LL))(v36);
    if ( v19 >= 0 )
    {
      v19 = ScheduledTasksRegistration::DeleteExpiredTaskImmediately(v29, v16);
      if ( v19 >= 0 )
      {
        v31 = ScheduledTasksRegistration::SaveTaskDefinitionInRootFolder(this, StringRawBuffer, v40[0], v16);
        v12 = v31;
        if ( v31 >= 0 )
        {
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v39);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v38);
          wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v36);
          wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v37);
          wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v34);
          wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v35);
          v12 = 0;
          goto LABEL_35;
        }
        v27 = (unsigned int)v31;
        v28 = 82;
        goto LABEL_26;
      }
      v30 = 79;
    }
    else
    {
      v30 = 78;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v30,
      (unsigned int)"shell\\oobe\\user\\dll\\scheduledtasksregistration.cpp",
      (const char *)(unsigned int)v19,
      (int)v43);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v39);
    goto LABEL_23;
  }
  v13 = 60;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v13,
    (unsigned int)"shell\\oobe\\user\\dll\\scheduledtasksregistration.cpp",
    (const char *)(unsigned int)v11,
    (int)v33);
LABEL_35:
  wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(v40);
  return v12;
}

```

## disassembly

```asm
0x180020350  push    rbp
0x180020352  push    rbx
0x180020353  push    rsi
0x180020354  push    rdi
0x180020355  push    r12
0x180020357  push    r14
0x180020359  push    r15
0x18002035b  lea     rbp, [rsp-27h]
0x180020360  sub     rsp, 0F0h
0x180020367  mov     r15, r9
0x18002036a  mov     r14, r8
0x18002036d  mov     rax, rdx
0x180020370  mov     r12, rcx
0x180020373  xor     edx, edx; length
0x180020375  mov     rcx, rax; string
0x180020378  call    cs:__imp_WindowsGetStringRawBuffer
0x18002037e  mov     rsi, rax
0x180020381  mov     [rbp+57h+var_C0], 0
0x180020389  lea     r9, [rbp+57h+var_C0]; void **
0x18002038d  call    ?SHExtCoCreateFromRegKey@@YAJPEBG0AEBU_GUID@@PEAPEAX@Z; SHExtCoCreateFromRegKey(ushort const *,ushort const *,_GUID const &,void * *)
0x180020392  mov     ebx, eax
0x180020394  test    eax, eax
0x180020396  jns     short loc_18002039F
0x180020398  mov     edx, 3Ch ; '<'
0x18002039d  jmp     short loc_18002040E
0x18002039f  mov     rcx, [rbp+57h+var_C0]
0x1800203a3  xor     eax, eax
0x1800203a5  mov     word ptr [rbp+57h+var_90], ax
0x1800203a9  movups  xmm1, xmmword ptr [rbp+57h+var_AE]
0x1800203ad  movups  xmmword ptr [rbp+57h+var_90+2], xmm1
0x1800203b1  movsd   xmm0, qword ptr [rbp+57h+var_AE+0Eh]
0x1800203b6  movsd   qword ptr [rbp+57h+var_90+10h], xmm0
0x1800203bb  mov     [rbp+57h+var_70], ax
0x1800203bf  movups  xmmword ptr [rbp+57h+var_6E], xmm1
0x1800203c3  movsd   qword ptr [rbp+57h+var_6E+0Eh], xmm0
0x1800203c8  mov     [rbp+57h+var_50], ax
0x1800203cc  movups  [rbp+57h+var_4E], xmm1
0x1800203d0  movsd   qword ptr [rbp+57h+var_4E+0Eh], xmm0
0x1800203d5  mov     [rbp+57h+var_B0], ax
0x1800203d9  movups  xmmword ptr [rbp+57h+var_AE], xmm1
0x1800203dd  movsd   qword ptr [rbp+57h+var_AE+0Eh], xmm0
0x1800203e2  mov     rax, [rcx]
0x1800203e5  lea     rdx, [rbp+57h+var_90]
0x1800203e9  mov     qword ptr [rsp+120h+var_100], rdx; int
0x1800203ee  lea     r9, [rbp+57h+var_70]
0x1800203f2  lea     r8, [rbp+57h+var_50]
0x1800203f6  lea     rdx, [rbp+57h+var_B0]
0x1800203fa  mov     rax, [rax+50h]
0x1800203fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020403  mov     ebx, eax
0x180020405  test    eax, eax
0x180020407  jns     short loc_180020426
0x180020409  mov     edx, 3Eh ; '>'; void *
0x18002040e  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x180020415  mov     r9d, eax; char *
0x180020418  mov     rcx, [rbp+5Fh]; this
0x18002041c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020421  jmp     loc_18002073D
0x180020426  mov     [rsp+120h+var_E8], 0
0x18002042f  lea     r9, [rsp+120h+var_E8]; struct ITaskDefinition **
0x180020434  mov     r8, [rbp+57h+var_C0]; struct ITaskService *
0x180020438  mov     rdx, rsi; unsigned __int16 *
0x18002043b  call    ?GenerateTaskDefinitionForCurrentUser@ScheduledTasksRegistration@@AEAAJPEBGPEAUITaskService@@PEAPEAUITaskDefinition@@@Z; ScheduledTasksRegistration::GenerateTaskDefinitionForCurrentUser(ushort const *,ITaskService *,ITaskDefinition * *)
0x180020440  mov     ebx, eax
0x180020442  test    eax, eax
0x180020444  jns     short loc_18002046E
0x180020446  mov     rcx, [rbp+5Fh]; this
0x18002044a  mov     r9d, eax; char *
0x18002044d  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x180020454  mov     edx, 42h ; 'B'; void *
0x180020459  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002045e  nop
0x18002045f  lea     rcx, [rsp+120h+var_E8]
0x180020464  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180020469  jmp     loc_18002073D
0x18002046e  mov     [rsp+120h+var_F0], 0
0x180020477  mov     rbx, [rsp+120h+var_E8]
0x18002047c  mov     rax, [rbx]
0x18002047f  mov     [rsp+120h+var_F0], 0
0x180020488  lea     rdx, [rsp+120h+var_F0]
0x18002048d  mov     rcx, rbx
0x180020490  mov     rax, [rax+48h]
0x180020494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020499  mov     edi, eax
0x18002049b  test    eax, eax
0x18002049d  jns     short loc_1800204D4
0x18002049f  mov     rcx, [rbp+5Fh]; this
0x1800204a3  mov     r9d, eax; char *
0x1800204a6  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x1800204ad  mov     edx, 44h ; 'D'; void *
0x1800204b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800204b7  nop
0x1800204b8  lea     rcx, [rsp+120h+var_F0]
0x1800204bd  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x1800204c2  nop
0x1800204c3  lea     rcx, [rsp+120h+var_E8]
0x1800204c8  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x1800204cd  mov     ebx, edi
0x1800204cf  jmp     loc_18002073D
0x1800204d4  mov     [rsp+120h+var_D8], 0
0x1800204dd  mov     rcx, [rsp+120h+var_F0]
0x1800204e2  mov     rax, [rcx]
0x1800204e5  mov     [rsp+120h+var_D8], 0
0x1800204ee  lea     r8, [rsp+120h+var_D8]
0x1800204f3  mov     edx, 7
0x1800204f8  mov     rax, [rax+50h]
0x1800204fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020501  mov     edi, eax
0x180020503  test    eax, eax
0x180020505  jns     short loc_18002052C
0x180020507  mov     rcx, [rbp+5Fh]; this
0x18002050b  mov     r9d, eax; char *
0x18002050e  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x180020515  mov     edx, 46h ; 'F'; void *
0x18002051a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002051f  nop
0x180020520  lea     rcx, [rsp+120h+var_D8]
0x180020525  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18002052a  jmp     short loc_1800204B8
0x18002052c  mov     [rsp+120h+var_E0], 0
0x180020535  mov     rcx, [rsp+120h+var_D8]
0x18002053a  mov     rax, [rcx]
0x18002053d  mov     [rsp+120h+var_E0], 0
0x180020546  lea     r8, [rsp+120h+var_E0]
0x18002054b  lea     rdx, _GUID_4c8fec3a_c218_4e0c_b23d_629024db91a2
0x180020552  mov     rax, [rax]
0x180020555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002055a  mov     edi, eax
0x18002055c  test    eax, eax
0x18002055e  jns     short loc_180020585
0x180020560  mov     rcx, [rbp+5Fh]; this
0x180020564  mov     r9d, eax; char *
0x180020567  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x18002056e  mov     edx, 48h ; 'H'; void *
0x180020573  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020578  nop
0x180020579  lea     rcx, [rsp+120h+var_E0]
0x18002057e  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180020583  jmp     short loc_180020520
0x180020585  xor     edx, edx; length
0x180020587  mov     rcx, r14; string
0x18002058a  call    cs:__imp_WindowsGetStringRawBuffer
0x180020590  mov     rdx, rax
0x180020593  lea     rcx, [rbp+57h+var_D0]
0x180020597  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x18002059c  nop
0x18002059d  mov     rdx, [rbp+57h+var_D0]
0x1800205a1  test    rdx, rdx
0x1800205a4  jnz     short loc_1800205F3
0x1800205a6  mov     rcx, [rbp+5Fh]; this
0x1800205aa  mov     ebx, 8007000Eh
0x1800205af  mov     r9d, ebx; char *
0x1800205b2  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x1800205b9  mov     edx, 4Ah ; 'J'; void *
0x1800205be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800205c3  nop
0x1800205c4  lea     rcx, [rbp+57h+var_D0]
0x1800205c8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800205cd  nop
0x1800205ce  lea     rcx, [rsp+120h+var_E0]
0x1800205d3  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x1800205d8  nop
0x1800205d9  lea     rcx, [rsp+120h+var_D8]
0x1800205de  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x1800205e3  nop
0x1800205e4  lea     rcx, [rsp+120h+var_F0]
0x1800205e9  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x1800205ee  jmp     loc_18002045F
0x1800205f3  mov     rcx, [rsp+120h+var_E0]
0x1800205f8  mov     rax, [rcx]
0x1800205fb  mov     rax, [rax+0A8h]
0x180020602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020607  mov     edi, eax
0x180020609  test    eax, eax
0x18002060b  jns     short loc_180020634
0x18002060d  mov     rcx, [rbp+5Fh]; this
0x180020611  mov     r9d, eax; char *
0x180020614  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x18002061b  mov     edx, 4Bh ; 'K'; void *
0x180020620  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020625  nop
0x180020626  lea     rcx, [rbp+57h+var_D0]
0x18002062a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002062f  jmp     loc_180020579
0x180020634  xor     edx, edx; length
0x180020636  mov     rcx, r15; string
0x180020639  call    cs:__imp_WindowsGetStringRawBuffer
0x18002063f  mov     rdx, rax
0x180020642  lea     rcx, [rbp+57h+var_C8]
0x180020646  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x18002064b  nop
0x18002064c  mov     rdx, [rbp+57h+var_C8]
0x180020650  test    rdx, rdx
0x180020653  jnz     short loc_180020681
0x180020655  mov     ebx, 8007000Eh
0x18002065a  mov     r9d, ebx; char *
0x18002065d  mov     edx, 4Dh ; 'M'; void *
0x180020662  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x180020669  mov     rcx, [rbp+5Fh]; this
0x18002066d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020672  nop
0x180020673  lea     rcx, [rbp+57h+var_C8]
0x180020677  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002067c  jmp     loc_1800205C4
0x180020681  mov     rcx, [rsp+120h+var_E0]
0x180020686  mov     rax, [rcx]
0x180020689  mov     rax, [rax+88h]
0x180020690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020695  mov     edi, eax
0x180020697  test    eax, eax
0x180020699  jns     short loc_1800206C2
0x18002069b  mov     edx, 4Eh ; 'N'; void *
0x1800206a0  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x1800206a7  mov     r9d, edi; char *
0x1800206aa  mov     rcx, [rbp+5Fh]; this
0x1800206ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800206b3  nop
0x1800206b4  lea     rcx, [rbp+57h+var_C8]
0x1800206b8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800206bd  jmp     loc_180020626
0x1800206c2  mov     rdx, rbx; struct ITaskDefinition *
0x1800206c5  call    ?DeleteExpiredTaskImmediately@ScheduledTasksRegistration@@AEAAJPEAUITaskDefinition@@@Z; ScheduledTasksRegistration::DeleteExpiredTaskImmediately(ITaskDefinition *)
0x1800206ca  mov     edi, eax
0x1800206cc  test    eax, eax
0x1800206ce  jns     short loc_1800206D7
0x1800206d0  mov     edx, 4Fh ; 'O'
0x1800206d5  jmp     short loc_1800206A0
0x1800206d7  mov     r9, rbx; struct ITaskDefinition *
0x1800206da  mov     r8, [rbp+57h+var_C0]; struct ITaskService *
0x1800206de  mov     rdx, rsi; unsigned __int16 *
0x1800206e1  mov     rcx, r12; this
0x1800206e4  call    ?SaveTaskDefinitionInRootFolder@ScheduledTasksRegistration@@AEAAJPEBGPEAUITaskService@@PEAUITaskDefinition@@@Z; ScheduledTasksRegistration::SaveTaskDefinitionInRootFolder(ushort const *,ITaskService *,ITaskDefinition *)
0x1800206e9  mov     ebx, eax
0x1800206eb  test    eax, eax
0x1800206ed  jns     short loc_1800206FC
0x1800206ef  mov     r9d, eax
0x1800206f2  mov     edx, 52h ; 'R'
0x1800206f7  jmp     loc_180020662
0x1800206fc  lea     rcx, [rbp+57h+var_C8]
0x180020700  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180020705  nop
0x180020706  lea     rcx, [rbp+57h+var_D0]
0x18002070a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002070f  nop
0x180020710  lea     rcx, [rsp+120h+var_E0]
0x180020715  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18002071a  nop
0x18002071b  lea     rcx, [rsp+120h+var_D8]
0x180020720  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180020725  nop
0x180020726  lea     rcx, [rsp+120h+var_F0]
0x18002072b  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180020730  nop
0x180020731  lea     rcx, [rsp+120h+var_E8]
0x180020736  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18002073b  xor     ebx, ebx
0x18002073d  lea     rcx, [rbp+57h+var_C0]
0x180020741  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180020746  mov     eax, ebx
0x180020748  add     rsp, 0F0h
0x18002074f  pop     r15
0x180020751  pop     r14
0x180020753  pop     r12
0x180020755  pop     rdi
0x180020756  pop     rsi
0x180020757  pop     rbx
0x180020758  pop     rbp
0x180020759  retn
```
