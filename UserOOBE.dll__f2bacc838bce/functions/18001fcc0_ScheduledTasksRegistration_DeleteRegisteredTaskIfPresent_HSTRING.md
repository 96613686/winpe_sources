# ScheduledTasksRegistration::DeleteRegisteredTaskIfPresent(HSTRING__ *)

- ea: `0x18001fcc0`
- end: `0x18001fecd`
- name: `?DeleteRegisteredTaskIfPresent@ScheduledTasksRegistration@@UEAAJPEAUHSTRING__@@@Z`
- size: `525`
- prototype: `__int64 __fastcall(ScheduledTasksRegistration *__hidden this, HSTRING string)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180007134`
- `0x18000a5e8`
- `0x18001136c`
- `0x180018c78`
- `0x18001cf50`
- `0x18001fad4`
- `0x18001fcc0`
- `0x18002027c`
- `0x180020b70`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001fe5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001fe5e`

## string_xrefs

- `0x18001fd6d`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`
- `0x18001fda8`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`
- `0x18001fdf9`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`
- `0x18001fe32`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ScheduledTasksRegistration::DeleteRegisteredTaskIfPresent(
        ScheduledTasksRegistration *this,
        unsigned __int16 *string,
        const struct _GUID *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rax
  int v9; // eax
  int CurrentUserSidString; // eax
  __int64 v11; // rdx
  struct ITaskFolder *v12; // rbx
  const unsigned __int16 *v13; // rdi
  const unsigned __int16 *StringRawBuffer; // rax
  unsigned int *v16; // [rsp+20h] [rbp-59h]
  LPWSTR StringSid; // [rsp+30h] [rbp-49h] BYREF
  void *v18; // [rsp+38h] [rbp-41h] BYREF
  __int16 v19; // [rsp+40h] [rbp-39h] BYREF
  _BYTE v20[22]; // [rsp+42h] [rbp-37h]
  _QWORD v21[4]; // [rsp+60h] [rbp-19h] BYREF
  __int16 v22; // [rsp+80h] [rbp+7h] BYREF
  _BYTE v23[22]; // [rsp+82h] [rbp+9h]
  __int16 v24; // [rsp+A0h] [rbp+27h] BYREF
  _BYTE v25[22]; // [rsp+A2h] [rbp+29h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  struct ITaskFolder *v27; // [rsp+F0h] [rbp+77h] BYREF
  __int64 v28; // [rsp+F8h] [rbp+7Fh] BYREF

  v18 = 0;
  v5 = SHExtCoCreateFromRegKey((const unsigned __int16 *)this, string, a3, &v18);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 90;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"shell\\oobe\\user\\dll\\scheduledtasksregistration.cpp",
      (const char *)(unsigned int)v5,
      (int)v16);
    goto LABEL_18;
  }
  LOWORD(v21[0]) = 0;
  *(_OWORD *)((char *)v21 + 2) = *(_OWORD *)v20;
  v21[2] = *(_QWORD *)&v20[14];
  v22 = 0;
  *(_OWORD *)v23 = *(_OWORD *)v20;
  *(_QWORD *)&v23[14] = *(_QWORD *)&v20[14];
  v24 = 0;
  *(_OWORD *)v25 = *(_OWORD *)v20;
  *(_QWORD *)&v25[14] = *(_QWORD *)&v20[14];
  v19 = 0;
  v16 = (unsigned int *)v21;
  v5 = (*(__int64 (__fastcall **)(void *, __int16 *, __int16 *, __int16 *))(*(_QWORD *)v18 + 80LL))(
         v18,
         &v19,
         &v24,
         &v22);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 92;
    goto LABEL_5;
  }
  wil::make_bstr_nothrow(&v28, *((_QWORD *)this + 2));
  if ( v28 )
  {
    v27 = 0;
    v8 = *(_QWORD *)v18;
    v27 = 0;
    v9 = (*(__int64 (__fastcall **)(void *, __int64, struct ITaskFolder **))(v8 + 56))(v18, v28, &v27);
    v6 = v9;
    if ( v9 >= 0 )
    {
      StringSid = 0;
      CurrentUserSidString = GetCurrentUserSidString(&StringSid);
      v6 = CurrentUserSidString;
      if ( CurrentUserSidString >= 0 )
      {
        v12 = v27;
        v13 = StringSid;
        StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)string, 0);
        CurrentUserSidString = ScheduledTasksRegistration::DeletePreviouslyRegisteredTaskIfPresent(
                                 this,
                                 StringRawBuffer,
                                 v13,
                                 v12,
                                 0);
        v6 = CurrentUserSidString;
        if ( CurrentUserSidString >= 0 )
        {
          wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(&StringSid);
          wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v27);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
          v6 = 0;
          goto LABEL_18;
        }
        v11 = 103;
      }
      else
      {
        v11 = 102;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"shell\\oobe\\user\\dll\\scheduledtasksregistration.cpp",
        (const char *)(unsigned int)CurrentUserSidString,
        (int)v16);
      wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(&StringSid);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x62,
        (unsigned int)"shell\\oobe\\user\\dll\\scheduledtasksregistration.cpp",
        (const char *)(unsigned int)v9,
        (int)v21);
    }
    wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v27);
  }
  else
  {
    v6 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x60,
      (unsigned int)"shell\\oobe\\user\\dll\\scheduledtasksregistration.cpp",
      (const char *)0x8007000ELL,
      (int)v21);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
LABEL_18:
  wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&v18);
  return v6;
}

```

## disassembly

```asm
0x18001fcc0  mov     [rsp-8+arg_0], rbx
0x18001fcc5  mov     [rsp-8+arg_8], rsi
0x18001fcca  push    rbp
0x18001fccb  push    rdi
0x18001fccc  push    r14
0x18001fcce  lea     rbp, [rsp-47h]
0x18001fcd3  sub     rsp, 0C0h
0x18001fcda  mov     r14, rdx
0x18001fcdd  mov     rsi, rcx
0x18001fce0  mov     [rbp+57h+var_98], 0
0x18001fce8  lea     r9, [rbp+57h+var_98]; void **
0x18001fcec  call    ?SHExtCoCreateFromRegKey@@YAJPEBG0AEBU_GUID@@PEAPEAX@Z; SHExtCoCreateFromRegKey(ushort const *,ushort const *,_GUID const &,void * *)
0x18001fcf1  mov     ebx, eax
0x18001fcf3  test    eax, eax
0x18001fcf5  jns     short loc_18001FCFE
0x18001fcf7  mov     edx, 5Ah ; 'Z'
0x18001fcfc  jmp     short loc_18001FD6D
0x18001fcfe  mov     rcx, [rbp+57h+var_98]
0x18001fd02  xor     eax, eax
0x18001fd04  mov     word ptr [rbp+57h+var_70], ax
0x18001fd08  movups  xmm1, xmmword ptr [rbp+57h+var_8E]
0x18001fd0c  movups  xmmword ptr [rbp+57h+var_70+2], xmm1
0x18001fd10  movsd   xmm0, qword ptr [rbp+57h+var_8E+0Eh]
0x18001fd15  movsd   qword ptr [rbp+57h+var_70+10h], xmm0
0x18001fd1a  mov     [rbp+57h+var_50], ax
0x18001fd1e  movups  xmmword ptr [rbp+57h+var_4E], xmm1
0x18001fd22  movsd   qword ptr [rbp+57h+var_4E+0Eh], xmm0
0x18001fd27  mov     [rbp+57h+var_30], ax
0x18001fd2b  movups  xmmword ptr [rbp+57h+var_2E], xmm1
0x18001fd2f  movsd   qword ptr [rbp+57h+var_2E+0Eh], xmm0
0x18001fd34  mov     [rbp+57h+var_90], ax
0x18001fd38  movups  xmmword ptr [rbp+57h+var_8E], xmm1
0x18001fd3c  movsd   qword ptr [rbp+57h+var_8E+0Eh], xmm0
0x18001fd41  mov     rax, [rcx]
0x18001fd44  lea     rdx, [rbp+57h+var_70]
0x18001fd48  mov     [rsp+0D0h+var_B0], rdx; int
0x18001fd4d  lea     r9, [rbp+57h+var_50]
0x18001fd51  lea     r8, [rbp+57h+var_30]
0x18001fd55  lea     rdx, [rbp+57h+var_90]
0x18001fd59  mov     rax, [rax+50h]
0x18001fd5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd62  mov     ebx, eax
0x18001fd64  test    eax, eax
0x18001fd66  jns     short loc_18001FD85
0x18001fd68  mov     edx, 5Ch ; '\'; void *
0x18001fd6d  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x18001fd74  mov     r9d, eax; char *
0x18001fd77  mov     rcx, [rbp+5Fh]; this
0x18001fd7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fd80  jmp     loc_18001FEAA
0x18001fd85  mov     rdx, [rsi+10h]
0x18001fd89  lea     rcx, [rbp+57h+arg_18]
0x18001fd8d  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x18001fd92  nop
0x18001fd93  mov     rdx, [rbp+57h+arg_18]
0x18001fd97  test    rdx, rdx
0x18001fd9a  jnz     short loc_18001FDC8
0x18001fd9c  mov     rcx, [rbp+5Fh]; this
0x18001fda0  mov     ebx, 8007000Eh
0x18001fda5  mov     r9d, ebx; char *
0x18001fda8  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x18001fdaf  mov     edx, 60h ; '`'; void *
0x18001fdb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fdb9  nop
0x18001fdba  lea     rcx, [rbp+57h+arg_18]
0x18001fdbe  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001fdc3  jmp     loc_18001FEAA
0x18001fdc8  mov     [rbp+57h+arg_10], 0
0x18001fdd0  mov     rcx, [rbp+57h+var_98]
0x18001fdd4  mov     rax, [rcx]
0x18001fdd7  mov     [rbp+57h+arg_10], 0
0x18001fddf  lea     r8, [rbp+57h+arg_10]
0x18001fde3  mov     rax, [rax+38h]
0x18001fde7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fdec  mov     ebx, eax
0x18001fdee  test    eax, eax
0x18001fdf0  jns     short loc_18001FE16
0x18001fdf2  mov     rcx, [rbp+5Fh]; this
0x18001fdf6  mov     r9d, eax; char *
0x18001fdf9  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x18001fe00  mov     edx, 62h ; 'b'; void *
0x18001fe05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fe0a  nop
0x18001fe0b  lea     rcx, [rbp+57h+arg_10]
0x18001fe0f  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18001fe14  jmp     short loc_18001FDBA
0x18001fe16  mov     [rbp+57h+StringSid], 0
0x18001fe1e  lea     rcx, [rbp+57h+StringSid]; StringSid
0x18001fe22  call    ?GetCurrentUserSidString@@YAJPEAPEAG@Z; GetCurrentUserSidString(ushort * *)
0x18001fe27  mov     ebx, eax
0x18001fe29  test    eax, eax
0x18001fe2b  jns     short loc_18001FE51
0x18001fe2d  mov     edx, 66h ; 'f'; void *
0x18001fe32  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x18001fe39  mov     r9d, eax; char *
0x18001fe3c  mov     rcx, [rbp+5Fh]; this
0x18001fe40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fe45  nop
0x18001fe46  lea     rcx, [rbp+57h+StringSid]
0x18001fe4a  call    ??1?$unique_storage@U?$resource_policy@PEAU_TOKEN_GROUPS@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(void)
0x18001fe4f  jmp     short loc_18001FE0B
0x18001fe51  mov     rbx, [rbp+57h+arg_10]
0x18001fe55  mov     rdi, [rbp+57h+StringSid]
0x18001fe59  xor     edx, edx; length
0x18001fe5b  mov     rcx, r14; string
0x18001fe5e  call    cs:__imp_WindowsGetStringRawBuffer
0x18001fe64  mov     [rsp+0D0h+var_B0], 0; unsigned int *
0x18001fe6d  mov     r9, rbx; struct ITaskFolder *
0x18001fe70  mov     r8, rdi; unsigned __int16 *
0x18001fe73  mov     rdx, rax; unsigned __int16 *
0x18001fe76  mov     rcx, rsi; this
0x18001fe79  call    ?DeletePreviouslyRegisteredTaskIfPresent@ScheduledTasksRegistration@@AEAAJPEBG0PEAUITaskFolder@@PEAK@Z; ScheduledTasksRegistration::DeletePreviouslyRegisteredTaskIfPresent(ushort const *,ushort const *,ITaskFolder *,ulong *)
0x18001fe7e  mov     ebx, eax
0x18001fe80  test    eax, eax
0x18001fe82  jns     short loc_18001FE8B
0x18001fe84  mov     edx, 67h ; 'g'
0x18001fe89  jmp     short loc_18001FE32
0x18001fe8b  lea     rcx, [rbp+57h+StringSid]
0x18001fe8f  call    ??1?$unique_storage@U?$resource_policy@PEAU_TOKEN_GROUPS@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(void)
0x18001fe94  nop
0x18001fe95  lea     rcx, [rbp+57h+arg_10]
0x18001fe99  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18001fe9e  nop
0x18001fe9f  lea     rcx, [rbp+57h+arg_18]
0x18001fea3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001fea8  xor     ebx, ebx
0x18001feaa  lea     rcx, [rbp+57h+var_98]
0x18001feae  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18001feb3  mov     eax, ebx
0x18001feb5  lea     r11, [rsp+0D0h+var_10]
0x18001febd  mov     rbx, [r11+20h]
0x18001fec1  mov     rsi, [r11+28h]
0x18001fec5  mov     rsp, r11
0x18001fec8  pop     r14
0x18001feca  pop     rdi
0x18001fecb  pop     rbp
0x18001fecc  retn
```
