# ScheduledTasksRegistration::DeletePreviouslyRegisteredTaskIfPresent(ushort const *,ushort const *,ITaskFolder *,ulong *)

- ea: `0x18001fad4`
- end: `0x18001fcb8`
- name: `?DeletePreviouslyRegisteredTaskIfPresent@ScheduledTasksRegistration@@AEAAJPEBG0PEAUITaskFolder@@PEAK@Z`
- size: `484`
- prototype: `__int64 __fastcall(ScheduledTasksRegistration *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct ITaskFolder *, unsigned int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18001fcc0`
- `0x180020c58`

## callees

- `0x180007134`
- `0x18000a5c8`
- `0x18000e270`
- `0x180018268`
- `0x180018c78`
- `0x18001b5d4`
- `0x18001cf50`
- `0x18001fad4`
- `0x18004e010`

## string_xrefs

- `0x18001fb67`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`
- `0x18001fb80`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`
- `0x18001fbd1`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`
- `0x18001fc14`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`
- `0x18001fc68`: `shell\oobe\user\dll\scheduledtasksregistration.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ScheduledTasksRegistration::DeletePreviouslyRegisteredTaskIfPresent(
        ScheduledTasksRegistration *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct ITaskFolder *a4,
        unsigned int *a5)
{
  int v9; // eax
  unsigned int v10; // ebx
  unsigned __int64 v11; // r9
  __int64 v12; // rdx
  int DWORD; // eax
  char v14; // di
  int v15; // esi
  unsigned int v16; // ebx
  int v17; // eax
  int v18; // eax
  int v20; // [rsp+20h] [rbp-28h]
  __int64 v21; // [rsp+30h] [rbp-18h] BYREF
  unsigned __int16 *v22[2]; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]
  void *v24; // [rsp+90h] [rbp+48h] BYREF

  v22[0] = 0;
  v9 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
         v22,
         L"%s\\%s",
         *((_QWORD *)this + 3),
         a2);
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = (unsigned int)v9;
    v12 = 202;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"shell\\oobe\\user\\dll\\scheduledtasksregistration.cpp",
      (const char *)v11,
      v20);
    goto LABEL_25;
  }
  LODWORD(v24) = 0;
  DWORD = SHRegGetDWORD(HKEY_CURRENT_USER, v22[0], *((const unsigned __int16 **)this + 4), (unsigned int *)&v24);
  v10 = DWORD;
  v14 = 1;
  if ( DWORD >= 0 )
  {
    v15 = (int)v24;
  }
  else
  {
    v15 = 0;
    if ( (unsigned int)(DWORD + 2147024894) > 1 && DWORD != -2147023728 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBD,
        (unsigned int)"shell\\oobe\\user\\dll\\scheduledtasksregistration.cpp",
        (const char *)(unsigned int)DWORD,
        v20);
      v11 = v10;
      v12 = 205;
      goto LABEL_7;
    }
  }
  v16 = 0;
  if ( DWORD >= 0 )
  {
    v24 = 0;
    v17 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &v24,
            *((_QWORD *)this + 5),
            a2,
            a3);
    v10 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD3,
        (unsigned int)"shell\\oobe\\user\\dll\\scheduledtasksregistration.cpp",
        (const char *)(unsigned int)v17,
        v15);
LABEL_12:
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v24);
      goto LABEL_25;
    }
    wil::make_bstr_nothrow(&v21, v24);
    if ( !v21 )
    {
      v10 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD5,
        (unsigned int)"shell\\oobe\\user\\dll\\scheduledtasksregistration.cpp",
        (const char *)0x8007000ELL,
        v15);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
      goto LABEL_12;
    }
    v18 = ((__int64 (__fastcall *)(struct ITaskFolder *, __int64, _QWORD))a4->lpVtbl->DeleteTask)(a4, v21, 0);
    if ( v18 == -2147023728 || (unsigned int)(v18 + 2147024894) <= 1 || v18 >= 0 )
      v14 = 0;
    if ( v14 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xD7,
        (unsigned int)"shell\\oobe\\user\\dll\\scheduledtasksregistration.cpp",
        (const char *)(unsigned int)v18,
        v15);
    v16 = v15 + 1;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v24);
  }
  if ( a5 )
    *a5 = v16;
  v10 = 0;
LABEL_25:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)v22);
  return v10;
}

```

## disassembly

```asm
0x18001fad4  push    rbp
0x18001fad6  push    rbx
0x18001fad7  push    rsi
0x18001fad8  push    rdi
0x18001fad9  push    r12
0x18001fadb  push    r13
0x18001fadd  push    r14
0x18001fadf  push    r15
0x18001fae1  mov     rbp, rsp
0x18001fae4  sub     rsp, 48h
0x18001fae8  mov     r12, r9
0x18001faeb  mov     r13, r8
0x18001faee  mov     r15, rdx
0x18001faf1  mov     r14, rcx
0x18001faf4  mov     [rbp+var_10], 0
0x18001fafc  mov     r9, rdx
0x18001faff  mov     r8, [rcx+18h]
0x18001fb03  lea     rdx, aSS_0; "%s\\%s"
0x18001fb0a  lea     rcx, [rbp+var_10]
0x18001fb0e  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18001fb13  mov     ebx, eax
0x18001fb15  test    eax, eax
0x18001fb17  jns     short loc_18001FB23
0x18001fb19  mov     r9d, eax
0x18001fb1c  mov     edx, 0CAh
0x18001fb21  jmp     short loc_18001FB80
0x18001fb23  mov     dword ptr [rbp+arg_0], 0
0x18001fb2a  lea     r9, [rbp+arg_0]; unsigned int *
0x18001fb2e  mov     r8, [r14+20h]; unsigned __int16 *
0x18001fb32  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x18001fb36  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x18001fb3d  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18001fb42  mov     ebx, eax
0x18001fb44  mov     edi, 1
0x18001fb49  test    eax, eax
0x18001fb4b  jns     short loc_18001FB95
0x18001fb4d  xor     esi, esi
0x18001fb4f  lea     ecx, [rax+7FF8FFFEh]
0x18001fb55  cmp     ecx, edi
0x18001fb57  jbe     short loc_18001FB98
0x18001fb59  cmp     eax, 80070490h
0x18001fb5e  jz      short loc_18001FB98
0x18001fb60  mov     rcx, [rbp+40h]; this
0x18001fb64  mov     r9d, eax; char *
0x18001fb67  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x18001fb6e  mov     edx, 0BDh; void *
0x18001fb73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fb78  mov     r9d, ebx; char *
0x18001fb7b  mov     edx, 0CDh; void *
0x18001fb80  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x18001fb87  mov     rcx, [rbp+40h]; this
0x18001fb8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fb90  jmp     loc_18001FC9C
0x18001fb95  mov     esi, dword ptr [rbp+arg_0]
0x18001fb98  shr     ebx, 1Fh
0x18001fb9b  xor     bl, dil
0x18001fb9e  mov     ebx, 0
0x18001fba3  jz      loc_18001FC8F
0x18001fba9  mov     [rbp+arg_0], rbx
0x18001fbad  mov     [rsp+48h+var_28], esi; int
0x18001fbb1  mov     r9, r13
0x18001fbb4  mov     r8, r15
0x18001fbb7  mov     rdx, [r14+28h]
0x18001fbbb  lea     rcx, [rbp+arg_0]
0x18001fbbf  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18001fbc4  mov     ebx, eax
0x18001fbc6  test    eax, eax
0x18001fbc8  jns     short loc_18001FBF1
0x18001fbca  mov     rcx, [rbp+40h]; this
0x18001fbce  mov     r9d, eax; char *
0x18001fbd1  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x18001fbd8  mov     edx, 0D3h; void *
0x18001fbdd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fbe2  nop
0x18001fbe3  lea     rcx, [rbp+arg_0]
0x18001fbe7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001fbec  jmp     loc_18001FC9C
0x18001fbf1  mov     rdx, [rbp+arg_0]
0x18001fbf5  lea     rcx, [rbp+var_18]
0x18001fbf9  call    ?make_bstr_nothrow@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr_nothrow(ushort const *)
0x18001fbfe  nop
0x18001fbff  mov     rdx, [rbp+var_18]
0x18001fc03  test    rdx, rdx
0x18001fc06  jnz     short loc_18001FC31
0x18001fc08  mov     rcx, [rbp+40h]; this
0x18001fc0c  mov     ebx, 8007000Eh
0x18001fc11  mov     r9d, ebx; char *
0x18001fc14  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x18001fc1b  mov     edx, 0D5h; void *
0x18001fc20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fc25  nop
0x18001fc26  lea     rcx, [rbp+var_18]
0x18001fc2a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001fc2f  jmp     short loc_18001FBE3
0x18001fc31  mov     rax, [r12]
0x18001fc35  xor     r8d, r8d
0x18001fc38  mov     rcx, r12
0x18001fc3b  mov     rax, [rax+78h]
0x18001fc3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc44  cmp     eax, 80070490h
0x18001fc49  jz      short loc_18001FC59
0x18001fc4b  lea     ecx, [rax+7FF8FFFEh]
0x18001fc51  cmp     ecx, edi
0x18001fc53  jbe     short loc_18001FC59
0x18001fc55  test    eax, eax
0x18001fc57  js      short loc_18001FC5C
0x18001fc59  xor     dil, dil
0x18001fc5c  mov     rcx, [rbp+40h]; this
0x18001fc60  test    dil, dil
0x18001fc63  jz      short loc_18001FC79
0x18001fc65  mov     r9d, eax; char *
0x18001fc68  lea     r8, aShellOobeUserD_7; "shell\\oobe\\user\\dll\\scheduledtasksr"...
0x18001fc6f  mov     edx, 0D7h; void *
0x18001fc74  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001fc79  lea     ebx, [rsi+1]
0x18001fc7c  lea     rcx, [rbp+var_18]
0x18001fc80  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001fc85  nop
0x18001fc86  lea     rcx, [rbp+arg_0]
0x18001fc8a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001fc8f  mov     rax, [rbp+arg_20]
0x18001fc93  test    rax, rax
0x18001fc96  jz      short loc_18001FC9A
0x18001fc98  mov     [rax], ebx
0x18001fc9a  xor     ebx, ebx
0x18001fc9c  lea     rcx, [rbp+var_10]
0x18001fca0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001fca5  mov     eax, ebx
0x18001fca7  add     rsp, 48h
0x18001fcab  pop     r15
0x18001fcad  pop     r14
0x18001fcaf  pop     r13
0x18001fcb1  pop     r12
0x18001fcb3  pop     rdi
0x18001fcb4  pop     rsi
0x18001fcb5  pop     rbx
0x18001fcb6  pop     rbp
0x18001fcb7  retn
```
