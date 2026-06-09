# ChangeThreadPriorityState(void *,ThreadPriorityLevel,bool)

- ea: `0x18004a290`
- end: `0x18004a50d`
- name: `?ChangeThreadPriorityState@@YAJPEAXW4ThreadPriorityLevel@@_N@Z`
- size: `637`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180028c34`

## callees

- `0x180003180`
- `0x1800110fc`
- `0x18001ad1c`
- `0x180045c9c`
- `0x18004a290`
- `0x180061960`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18004a2cf`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18004a2cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a2e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a370`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a40e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a2e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a370`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a40e`
- `api-ms-win-core-processthreads-l1-1-2!SetThreadInformation` at `0x18004a366`
- `api-ms-win-core-processthreads-l1-1-2!SetThreadInformation` at `0x18004a404`
- `api-ms-win-core-processthreads-l1-1-2!SetThreadInformation` at `0x18004a366`
- `api-ms-win-core-processthreads-l1-1-2!SetThreadInformation` at `0x18004a404`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18004a330`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18004a330`

## string_xrefs

- `0x18004a3b8`: `Attempt to %ws thread EcoQos failed with hr=0x%08x`

## pseudocode

```c
__int64 __fastcall ChangeThreadPriorityState(void *a1, int a2)
{
  signed int LastError; // eax
  __int64 v5; // r9
  int v6; // esi
  signed int v7; // eax
  signed int v8; // ebx
  const wchar_t *v9; // rax
  WUSystemInterfaceHelper *v10; // rcx
  signed int v11; // eax
  __int64 v12; // r9
  int WUSystemInterface; // eax
  unsigned int v14; // ebx
  __int64 v15; // rdx
  int v17; // [rsp+20h] [rbp-40h]
  int v18; // [rsp+20h] [rbp-40h]
  int v19; // [rsp+20h] [rbp-40h]
  _DWORD v20[2]; // [rsp+40h] [rbp-20h] BYREF
  int v21; // [rsp+48h] [rbp-18h]
  int v22; // [rsp+50h] [rbp-10h] BYREF
  int v23; // [rsp+54h] [rbp-Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  if ( !SetThreadPriority(a1, a2 != 1 ? 0xFFFFFFFE : 0) )
  {
    LastError = GetLastError();
    v5 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v5 = (unsigned int)LastError;
    if ( (int)v5 >= 0 )
      v5 = 2147549183LL;
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0xC8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\util.cpp",
      (const char *)v5,
      v17);
  }
  v20[0] = 1;
  v20[1] = 1;
  v21 = 1;
  v22 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v22, 0);
  v6 = 5;
  if ( v22 != 5 && (unsigned int)(v22 - 11) >= 2 && !(unsigned int)SetThreadInformation(a1, 3, v20, 12) )
  {
    v7 = GetLastError();
    v8 = (unsigned __int16)v7 | 0x80070000;
    if ( v7 <= 0 )
      v8 = v7;
    if ( v8 >= 0 )
      v8 = -2147418113;
    v9 = L"disable";
    if ( v21 )
      v9 = L"enable";
    WUTrace(0, 0, 1, 3, 0, L"Attempt to %ws thread EcoQos failed with hr=0x%08x", v9, v8);
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0xDE,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\util.cpp",
      (const char *)(unsigned int)v8,
      v18);
  }
  if ( a2 != 1 )
    v6 = 1;
  v23 = v6;
  if ( !(unsigned int)SetThreadInformation(a1, 0, &v23, 4) )
  {
    v11 = GetLastError();
    v12 = (unsigned __int16)v11 | 0x80070000;
    if ( v11 <= 0 )
      v12 = (unsigned int)v11;
    if ( (int)v12 >= 0 )
      v12 = 2147549183LL;
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0xEE,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\util.cpp",
      (const char *)v12,
      v17);
  }
  WUSystemInterface = WUSystemInterfaceHelper::LoadWUSystemInterface(v10);
  v14 = WUSystemInterface;
  if ( a2 == 1 )
  {
    if ( WUSystemInterface < 0 )
    {
      v15 = 118;
      goto LABEL_28;
    }
    WUSystemInterface = (*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)g_WUSystemInterface + 64LL))(
                          g_WUSystemInterface,
                          a1);
    v14 = WUSystemInterface;
    if ( WUSystemInterface < 0 )
    {
      v15 = 119;
      goto LABEL_28;
    }
  }
  else
  {
    if ( WUSystemInterface < 0 )
    {
      v15 = 111;
LABEL_28:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusyshelper\\wusyshelper.cpp",
        (const char *)(unsigned int)WUSystemInterface,
        v17);
      goto LABEL_36;
    }
    WUSystemInterface = (*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)g_WUSystemInterface + 56LL))(
                          g_WUSystemInterface,
                          a1);
    v14 = WUSystemInterface;
    if ( WUSystemInterface < 0 )
    {
      v15 = 112;
      goto LABEL_28;
    }
  }
  v14 = 0;
LABEL_36:
  if ( (v14 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0xFB,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\util.cpp",
      (const char *)v14,
      v17);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFE,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\util.cpp",
      (const char *)v14,
      v19);
  }
  return v14;
}

```

## disassembly

```asm
0x18004a290  mov     [rsp-28h+arg_10], rbx
0x18004a295  mov     [rsp-28h+arg_18], rsi
0x18004a29a  push    rbp
0x18004a29b  push    rdi
0x18004a29c  push    r12
0x18004a29e  push    r13
0x18004a2a0  push    r14
0x18004a2a2  mov     rbp, rsp
0x18004a2a5  sub     rsp, 60h
0x18004a2a9  mov     rax, cs:__security_cookie
0x18004a2b0  xor     rax, rsp
0x18004a2b3  mov     [rbp+var_8], rax
0x18004a2b7  mov     r14d, edx
0x18004a2ba  mov     r12d, 1
0x18004a2c0  mov     eax, r12d
0x18004a2c3  mov     rdi, rcx
0x18004a2c6  sub     eax, edx
0x18004a2c8  neg     eax
0x18004a2ca  sbb     edx, edx
0x18004a2cc  and     edx, 0FFFFFFFEh; nPriority
0x18004a2cf  call    cs:__imp_SetThreadPriority
0x18004a2d5  mov     ebx, 8000FFFFh
0x18004a2da  lea     r13, aCW1SSrcClientL_9; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18004a2e1  test    eax, eax
0x18004a2e3  jnz     short loc_18004A314
0x18004a2e5  call    cs:__imp_GetLastError
0x18004a2eb  mov     rcx, [rbp+28h]; this
0x18004a2ef  mov     r8, r13; unsigned int
0x18004a2f2  movzx   r9d, ax
0x18004a2f6  mov     edx, 0C8h; void *
0x18004a2fb  or      r9d, 80070000h
0x18004a302  test    eax, eax
0x18004a304  cmovle  r9d, eax
0x18004a308  test    r9d, r9d
0x18004a30b  cmovns  r9d, ebx; char *
0x18004a30f  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18004a314  xor     r8d, r8d
0x18004a317  mov     [rbp+var_20], r12d
0x18004a31b  lea     rdx, [rbp+var_10]
0x18004a31f  mov     [rbp+var_1C], r12d
0x18004a323  xor     ecx, ecx
0x18004a325  mov     [rbp+var_18], r12d
0x18004a329  mov     [rbp+var_10], 0
0x18004a330  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18004a336  mov     eax, [rbp+var_10]
0x18004a339  mov     esi, 5
0x18004a33e  sub     eax, esi
0x18004a340  jz      loc_18004A3EB
0x18004a346  sub     eax, 6
0x18004a349  jz      loc_18004A3EB
0x18004a34f  cmp     eax, r12d
0x18004a352  jz      loc_18004A3EB
0x18004a358  lea     r9d, [rsi+7]
0x18004a35c  mov     rcx, rdi
0x18004a35f  lea     r8, [rbp+var_20]
0x18004a363  lea     edx, [rsi-2]
0x18004a366  call    cs:__imp_SetThreadInformation
0x18004a36c  test    eax, eax
0x18004a36e  jnz     short loc_18004A3EB
0x18004a370  call    cs:__imp_GetLastError
0x18004a376  movzx   ebx, ax
0x18004a379  lea     rcx, aEnable; "enable"
0x18004a380  lea     r9d, [rsi-2]
0x18004a384  mov     r8d, r12d
0x18004a387  or      ebx, 80070000h
0x18004a38d  test    eax, eax
0x18004a38f  cmovle  ebx, eax
0x18004a392  mov     eax, 8000FFFFh
0x18004a397  test    ebx, ebx
0x18004a399  cmovns  ebx, eax
0x18004a39c  cmp     [rbp+var_18], 0
0x18004a3a0  mov     [rsp+60h+var_28], ebx
0x18004a3a4  lea     rax, aDisable; "disable"
0x18004a3ab  cmovnz  rax, rcx
0x18004a3af  xor     edx, edx
0x18004a3b1  mov     [rsp+60h+var_30], rax
0x18004a3b6  xor     ecx, ecx
0x18004a3b8  lea     rax, aAttemptToWsThr; "Attempt to %ws thread EcoQos failed wit"...
0x18004a3bf  mov     [rsp+60h+var_38], rax
0x18004a3c4  mov     qword ptr [rsp+60h+var_40], 0; int
0x18004a3cd  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18004a3d2  mov     rcx, [rbp+28h]; this
0x18004a3d6  mov     r9d, ebx; char *
0x18004a3d9  mov     r8, r13; unsigned int
0x18004a3dc  mov     edx, 0DEh; void *
0x18004a3e1  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18004a3e6  mov     ebx, 8000FFFFh
0x18004a3eb  cmp     r14d, r12d
0x18004a3ee  lea     r8, [rbp+var_C]
0x18004a3f2  mov     r9d, 4
0x18004a3f8  mov     rcx, rdi
0x18004a3fb  cmovnz  esi, r12d
0x18004a3ff  xor     edx, edx
0x18004a401  mov     [rbp+var_C], esi
0x18004a404  call    cs:__imp_SetThreadInformation
0x18004a40a  test    eax, eax
0x18004a40c  jnz     short loc_18004A43D
0x18004a40e  call    cs:__imp_GetLastError
0x18004a414  mov     rcx, [rbp+28h]; this
0x18004a418  mov     r8, r13; unsigned int
0x18004a41b  movzx   r9d, ax
0x18004a41f  mov     edx, 0EEh; void *
0x18004a424  or      r9d, 80070000h
0x18004a42b  test    eax, eax
0x18004a42d  cmovle  r9d, eax
0x18004a431  test    r9d, r9d
0x18004a434  cmovns  r9d, ebx; char *
0x18004a438  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18004a43d  call    ?LoadWUSystemInterface@WUSystemInterfaceHelper@@YAJXZ; WUSystemInterfaceHelper::LoadWUSystemInterface(void)
0x18004a442  mov     ebx, eax
0x18004a444  cmp     r14d, r12d
0x18004a447  jz      short loc_18004A48A
0x18004a449  test    eax, eax
0x18004a44b  jns     short loc_18004A467
0x18004a44d  mov     edx, 6Fh ; 'o'; void *
0x18004a452  mov     rcx, [rbp+28h]; this
0x18004a456  lea     r8, aCW1SSrcClientL_13; "C:\\__w\\1\\s\\src\\Client\\lib\\wusysh"...
0x18004a45d  mov     r9d, eax; char *
0x18004a460  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a465  jmp     short loc_18004A4BA
0x18004a467  mov     rcx, cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x18004a46e  mov     rdx, rdi
0x18004a471  mov     rax, [rcx]
0x18004a474  mov     rax, [rax+38h]
0x18004a478  call    _guard_dispatch_icall
0x18004a47d  mov     ebx, eax
0x18004a47f  test    eax, eax
0x18004a481  jns     short loc_18004A4B8
0x18004a483  mov     edx, 70h ; 'p'
0x18004a488  jmp     short loc_18004A452
0x18004a48a  test    eax, eax
0x18004a48c  jns     short loc_18004A495
0x18004a48e  mov     edx, 76h ; 'v'
0x18004a493  jmp     short loc_18004A452
0x18004a495  mov     rcx, cs:?g_WUSystemInterface@@3V?$com_ptr_t@VIWUSystemInterface@@Uerr_returncode_policy@wil@@@wil@@A; wil::com_ptr_t<IWUSystemInterface,wil::err_returncode_policy> g_WUSystemInterface
0x18004a49c  mov     rdx, rdi
0x18004a49f  mov     rax, [rcx]
0x18004a4a2  mov     rax, [rax+40h]
0x18004a4a6  call    _guard_dispatch_icall
0x18004a4ab  mov     ebx, eax
0x18004a4ad  test    eax, eax
0x18004a4af  jns     short loc_18004A4B8
0x18004a4b1  mov     edx, 77h ; 'w'
0x18004a4b6  jmp     short loc_18004A452
0x18004a4b8  xor     ebx, ebx
0x18004a4ba  test    ebx, ebx
0x18004a4bc  jns     short loc_18004A4E6
0x18004a4be  mov     rcx, [rbp+28h]; this
0x18004a4c2  mov     r9d, ebx; char *
0x18004a4c5  mov     r8, r13; unsigned int
0x18004a4c8  mov     edx, 0FBh; void *
0x18004a4cd  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18004a4d2  mov     rcx, [rbp+28h]; this
0x18004a4d6  mov     r9d, ebx; char *
0x18004a4d9  mov     r8, r13; unsigned int
0x18004a4dc  mov     edx, 0FEh; void *
0x18004a4e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a4e6  mov     eax, ebx
0x18004a4e8  mov     rcx, [rbp+var_8]
0x18004a4ec  xor     rcx, rsp; StackCookie
0x18004a4ef  call    __security_check_cookie
0x18004a4f4  lea     r11, [rsp+60h+var_s0]
0x18004a4f9  mov     rbx, [r11+40h]
0x18004a4fd  mov     rsi, [r11+48h]
0x18004a501  mov     rsp, r11
0x18004a504  pop     r14
0x18004a506  pop     r13
0x18004a508  pop     r12
0x18004a50a  pop     rdi
0x18004a50b  pop     rbp
0x18004a50c  retn
```
