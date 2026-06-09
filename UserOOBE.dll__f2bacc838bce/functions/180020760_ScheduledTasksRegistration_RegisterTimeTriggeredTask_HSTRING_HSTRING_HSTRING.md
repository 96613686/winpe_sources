# ScheduledTasksRegistration::RegisterTimeTriggeredTask(HSTRING__ *,HSTRING__ *,HSTRING__ *)

- ea: `0x180020760`
- end: `0x180020b67`
- name: `?RegisterTimeTriggeredTask@ScheduledTasksRegistration@@UEAAJPEAUHSTRING__@@00@Z`
- size: `1031`
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
- `0x180020760`
- `0x180020b70`
- `0x180020c58`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180020788`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002099a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180020a46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180020788`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002099a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180020a46`

## string_xrefs

- `0x18002081e`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`
- `0x18002085d`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`
- `0x1800208b6`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`
- `0x18002091e`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`
- `0x180020977`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`
- `0x1800209c2`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`
- `0x180020a21`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`
- `0x180020a6f`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`
- `0x180020aad`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall ScheduledTasksRegistration::RegisterTimeTriggeredTask(
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
      v13 = 30;
      goto LABEL_5;
    }
    v35 = 0;
    v15 = ScheduledTasksRegistration::GenerateTaskDefinitionForCurrentUser(v14, StringRawBuffer, v40[0], &v35);
    v12 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22,
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
        (void *)0x24,
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
    v21 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD))(v20 + 80))(v34, 1, &v37);
    v19 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x26,
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
    v23 = (*v22)(v37, &GUID_b45747e0_eba7_4276_9f29_85c5bb300006, &v36);
    v19 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x28,
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
        (void *)0x2A,
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
    v25 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 120LL))(v36);
    v19 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B,
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
      v28 = 45;
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
        v28 = 50;
        goto LABEL_26;
      }
      v30 = 47;
    }
    else
    {
      v30 = 46;
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
  v13 = 28;
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
0x180020760  push    rbp
0x180020762  push    rbx
0x180020763  push    rsi
0x180020764  push    rdi
0x180020765  push    r12
0x180020767  push    r14
0x180020769  push    r15
0x18002076b  lea     rbp, [rsp-27h]
0x180020770  sub     rsp, 0F0h
0x180020777  mov     r15, r9
0x18002077a  mov     r14, r8
0x18002077d  mov     rax, rdx
0x180020780  mov     r12, rcx
0x180020783  xor     edx, edx; length
0x180020785  mov     rcx, rax; string
0x180020788  call    cs:__imp_WindowsGetStringRawBuffer
0x18002078e  mov     rsi, rax
0x180020791  mov     [rbp+57h+var_C0], 0
0x180020799  lea     r9, [rbp+57h+var_C0]; void **
0x18002079d  call    ?SHExtCoCreateFromRegKey@@YAJPEBG0AEBU_GUID@@PEAPEAX@Z; SHExtCoCreateFromRegKey(ushort const *,ushort const *,_GUID const &,void * *)
0x1800207a2  mov     ebx, eax
0x1800207a4  test    eax, eax
0x1800207a6  jns     short loc_1800207AF
0x1800207a8  mov     edx, 1Ch
0x1800207ad  jmp     short loc_18002081E
0x1800207af  mov     rcx, [rbp+57h+var_C0]
0x1800207b3  xor     eax, eax
0x1800207b5  mov     word ptr [rbp+57h+var_90], ax
0x1800207b9  movups  xmm1, xmmword ptr [rbp+57h+var_AE]
0x1800207bd  movups  xmmword ptr [rbp+57h+var_90+2], xmm1
0x1800207c1  movsd   xmm0, qword ptr [rbp+57h+var_AE+0Eh]
0x1800207c6  movsd   qword ptr [rbp+57h+var_90+10h], xmm0
0x1800207cb  mov     [rbp+57h+var_70], ax
0x1800207cf  movups  xmmword ptr [rbp+57h+var_6E], xmm1
0x1800207d3  movsd   qword ptr [rbp+57h+var_6E+0Eh], xmm0
0x1800207d8  mov     [rbp+57h+var_50], ax
0x1800207dc  movups  [rbp+57h+var_4E], xmm1
0x1800207e0  movsd   qword ptr [rbp+57h+var_4E+0Eh], xmm0
0x1800207e5  mov     [rbp+57h+var_B0], ax
0x1800207e9  movups  xmmword ptr [rbp+57h+var_AE], xmm1
0x1800207ed  movsd   qword ptr [rbp+57h+var_AE+0Eh], xmm0
0x1800207f2  mov     rax, [rcx]
0x1800207f5  lea     rdx, [rbp+57h+var_90]
0x1800207f9  mov     qword ptr [rsp+120h+var_100], rdx; int
0x1800207fe  lea     r9, [rbp+57h+var_70]
0x180020802  lea     r8, [rbp+57h+var_50]
0x180020806  lea     rdx, [rbp+57h+var_B0]
0x18002080a  mov     rax, [rax+50h]
0x18002080e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020813  mov     ebx, eax
0x180020815  test    eax, eax
0x180020817  jns     short loc_180020836
0x180020819  mov     edx, 1Eh; void *
0x18002081e  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x180020825  mov     r9d, eax; char *
0x180020828  mov     rcx, [rbp+5Fh]; this
0x18002082c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020831  jmp     loc_180020B4A
0x180020836  mov     [rsp+120h+var_E8], 0
0x18002083f  lea     r9, [rsp+120h+var_E8]; struct ITaskDefinition **
0x180020844  mov     r8, [rbp+57h+var_C0]; struct ITaskService *
0x180020848  mov     rdx, rsi; unsigned __int16 *
0x18002084b  call    ?GenerateTaskDefinitionForCurrentUser@ScheduledTasksRegistration@@AEAAJPEBGPEAUITaskService@@PEAPEAUITaskDefinition@@@Z; ScheduledTasksRegistration::GenerateTaskDefinitionForCurrentUser(ushort const *,ITaskService *,ITaskDefinition * *)
0x180020850  mov     ebx, eax
0x180020852  test    eax, eax
0x180020854  jns     short loc_18002087E
0x180020856  mov     rcx, [rbp+5Fh]; this
0x18002085a  mov     r9d, eax; char *
0x18002085d  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x180020864  mov     edx, 22h ; '"'; void *
0x180020869  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002086e  nop
0x18002086f  lea     rcx, [rsp+120h+var_E8]
0x180020874  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180020879  jmp     loc_180020B4A
0x18002087e  mov     [rsp+120h+var_F0], 0
0x180020887  mov     rbx, [rsp+120h+var_E8]
0x18002088c  mov     rax, [rbx]
0x18002088f  mov     [rsp+120h+var_F0], 0
0x180020898  lea     rdx, [rsp+120h+var_F0]
0x18002089d  mov     rcx, rbx
0x1800208a0  mov     rax, [rax+48h]
0x1800208a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208a9  mov     edi, eax
0x1800208ab  test    eax, eax
0x1800208ad  jns     short loc_1800208E4
0x1800208af  mov     rcx, [rbp+5Fh]; this
0x1800208b3  mov     r9d, eax; char *
0x1800208b6  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x1800208bd  mov     edx, 24h ; '$'; void *
0x1800208c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800208c7  nop
0x1800208c8  lea     rcx, [rsp+120h+var_F0]
0x1800208cd  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x1800208d2  nop
0x1800208d3  lea     rcx, [rsp+120h+var_E8]
0x1800208d8  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x1800208dd  mov     ebx, edi
0x1800208df  jmp     loc_180020B4A
0x1800208e4  mov     [rsp+120h+var_D8], 0
0x1800208ed  mov     rcx, [rsp+120h+var_F0]
0x1800208f2  mov     rax, [rcx]
0x1800208f5  mov     [rsp+120h+var_D8], 0
0x1800208fe  lea     r8, [rsp+120h+var_D8]
0x180020903  mov     edx, 1
0x180020908  mov     rax, [rax+50h]
0x18002090c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020911  mov     edi, eax
0x180020913  test    eax, eax
0x180020915  jns     short loc_18002093C
0x180020917  mov     rcx, [rbp+5Fh]; this
0x18002091b  mov     r9d, eax; char *
0x18002091e  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x180020925  mov     edx, 26h ; '&'; void *
0x18002092a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002092f  nop
0x180020930  lea     rcx, [rsp+120h+var_D8]
0x180020935  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18002093a  jmp     short loc_1800208C8
0x18002093c  mov     [rsp+120h+var_E0], 0
0x180020945  mov     rcx, [rsp+120h+var_D8]
0x18002094a  mov     rax, [rcx]
0x18002094d  mov     [rsp+120h+var_E0], 0
0x180020956  lea     r8, [rsp+120h+var_E0]
0x18002095b  lea     rdx, _GUID_b45747e0_eba7_4276_9f29_85c5bb300006
0x180020962  mov     rax, [rax]
0x180020965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002096a  mov     edi, eax
0x18002096c  test    eax, eax
0x18002096e  jns     short loc_180020995
0x180020970  mov     rcx, [rbp+5Fh]; this
0x180020974  mov     r9d, eax; char *
0x180020977  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x18002097e  mov     edx, 28h ; '('; void *
0x180020983  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020988  nop
0x180020989  lea     rcx, [rsp+120h+var_E0]
0x18002098e  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180020993  jmp     short loc_180020930
0x180020995  xor     edx, edx; length
0x180020997  mov     rcx, r14; string
0x18002099a  call    cs:__imp_WindowsGetStringRawBuffer
0x1800209a0  mov     rdx, rax
0x1800209a3  lea     rcx, [rbp+57h+var_D0]
0x1800209a7  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x1800209ac  nop
0x1800209ad  mov     rdx, [rbp+57h+var_D0]
0x1800209b1  test    rdx, rdx
0x1800209b4  jnz     short loc_180020A03
0x1800209b6  mov     rcx, [rbp+5Fh]; this
0x1800209ba  mov     ebx, 8007000Eh
0x1800209bf  mov     r9d, ebx; char *
0x1800209c2  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x1800209c9  mov     edx, 2Ah ; '*'; void *
0x1800209ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800209d3  nop
0x1800209d4  lea     rcx, [rbp+57h+var_D0]
0x1800209d8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800209dd  nop
0x1800209de  lea     rcx, [rsp+120h+var_E0]
0x1800209e3  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x1800209e8  nop
0x1800209e9  lea     rcx, [rsp+120h+var_D8]
0x1800209ee  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x1800209f3  nop
0x1800209f4  lea     rcx, [rsp+120h+var_F0]
0x1800209f9  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x1800209fe  jmp     loc_18002086F
0x180020a03  mov     rcx, [rsp+120h+var_E0]
0x180020a08  mov     rax, [rcx]
0x180020a0b  mov     rax, [rax+78h]
0x180020a0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a14  mov     edi, eax
0x180020a16  test    eax, eax
0x180020a18  jns     short loc_180020A41
0x180020a1a  mov     rcx, [rbp+5Fh]; this
0x180020a1e  mov     r9d, eax; char *
0x180020a21  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x180020a28  mov     edx, 2Bh ; '+'; void *
0x180020a2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020a32  nop
0x180020a33  lea     rcx, [rbp+57h+var_D0]
0x180020a37  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180020a3c  jmp     loc_180020989
0x180020a41  xor     edx, edx; length
0x180020a43  mov     rcx, r15; string
0x180020a46  call    cs:__imp_WindowsGetStringRawBuffer
0x180020a4c  mov     rdx, rax
0x180020a4f  lea     rcx, [rbp+57h+var_C8]
0x180020a53  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x180020a58  nop
0x180020a59  mov     rdx, [rbp+57h+var_C8]
0x180020a5d  test    rdx, rdx
0x180020a60  jnz     short loc_180020A8E
0x180020a62  mov     ebx, 8007000Eh
0x180020a67  mov     r9d, ebx; char *
0x180020a6a  mov     edx, 2Dh ; '-'; void *
0x180020a6f  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x180020a76  mov     rcx, [rbp+5Fh]; this
0x180020a7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020a7f  nop
0x180020a80  lea     rcx, [rbp+57h+var_C8]
0x180020a84  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180020a89  jmp     loc_1800209D4
0x180020a8e  mov     rcx, [rsp+120h+var_E0]
0x180020a93  mov     rax, [rcx]
0x180020a96  mov     rax, [rax+88h]
0x180020a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020aa2  mov     edi, eax
0x180020aa4  test    eax, eax
0x180020aa6  jns     short loc_180020ACF
0x180020aa8  mov     edx, 2Eh ; '.'; void *
0x180020aad  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x180020ab4  mov     r9d, edi; char *
0x180020ab7  mov     rcx, [rbp+5Fh]; this
0x180020abb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020ac0  nop
0x180020ac1  lea     rcx, [rbp+57h+var_C8]
0x180020ac5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180020aca  jmp     loc_180020A33
0x180020acf  mov     rdx, rbx; struct ITaskDefinition *
0x180020ad2  call    ?DeleteExpiredTaskImmediately@ScheduledTasksRegistration@@AEAAJPEAUITaskDefinition@@@Z; ScheduledTasksRegistration::DeleteExpiredTaskImmediately(ITaskDefinition *)
0x180020ad7  mov     edi, eax
0x180020ad9  test    eax, eax
0x180020adb  jns     short loc_180020AE4
0x180020add  mov     edx, 2Fh ; '/'
0x180020ae2  jmp     short loc_180020AAD
0x180020ae4  mov     r9, rbx; struct ITaskDefinition *
0x180020ae7  mov     r8, [rbp+57h+var_C0]; struct ITaskService *
0x180020aeb  mov     rdx, rsi; unsigned __int16 *
0x180020aee  mov     rcx, r12; this
0x180020af1  call    ?SaveTaskDefinitionInRootFolder@ScheduledTasksRegistration@@AEAAJPEBGPEAUITaskService@@PEAUITaskDefinition@@@Z; ScheduledTasksRegistration::SaveTaskDefinitionInRootFolder(ushort const *,ITaskService *,ITaskDefinition *)
0x180020af6  mov     ebx, eax
0x180020af8  test    eax, eax
0x180020afa  jns     short loc_180020B09
0x180020afc  mov     r9d, eax
0x180020aff  mov     edx, 32h ; '2'
0x180020b04  jmp     loc_180020A6F
0x180020b09  lea     rcx, [rbp+57h+var_C8]
0x180020b0d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180020b12  nop
0x180020b13  lea     rcx, [rbp+57h+var_D0]
0x180020b17  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180020b1c  nop
0x180020b1d  lea     rcx, [rsp+120h+var_E0]
0x180020b22  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180020b27  nop
0x180020b28  lea     rcx, [rsp+120h+var_D8]
0x180020b2d  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180020b32  nop
0x180020b33  lea     rcx, [rsp+120h+var_F0]
0x180020b38  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180020b3d  nop
0x180020b3e  lea     rcx, [rsp+120h+var_E8]
0x180020b43  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180020b48  xor     ebx, ebx
0x180020b4a  lea     rcx, [rbp+57h+var_C0]
0x180020b4e  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x180020b53  mov     eax, ebx
0x180020b55  add     rsp, 0F0h
0x180020b5c  pop     r15
0x180020b5e  pop     r14
0x180020b60  pop     r12
0x180020b62  pop     rdi
0x180020b63  pop     rsi
0x180020b64  pop     rbx
0x180020b65  pop     rbp
0x180020b66  retn
```
