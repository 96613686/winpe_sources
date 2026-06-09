# AppActivation::ActivateExtensionWithDCOM(Windows::Foundation::IExtensionRegistration *,Windows::ApplicationModel::Core::IActivatableApplication * *)

- ea: `0x18002fe80`
- end: `0x1800300b7`
- name: `?ActivateExtensionWithDCOM@AppActivation@@AEAAJPEAUIExtensionRegistration@Foundation@Windows@@PEAPEAUIActivatableApplication@Core@ApplicationModel@4@@Z`
- size: `567`
- prototype: `int(AppActivation *__hidden this, struct Windows::Foundation::IExtensionRegistration *, struct Windows::ApplicationModel::Core::IActivatableApplication **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800300c0`

## callees

- `0x18000b5c0`
- `0x18000cbc0`
- `0x180027ce8`
- `0x18002fe80`
- `0x18005e96c`
- `0x180067e64`
- `0x180083810`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030033`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030033`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030046`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180030046`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003003e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003003e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002ffc9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002ffc9`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessHandleForAccess` at `0x180030072`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessHandleForAccess` at `0x180030072`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall AppActivation::ActivateExtensionWithDCOM(
        AppActivation *this,
        struct Windows::Foundation::IExtensionRegistration *a2,
        struct Windows::ApplicationModel::Core::IActivatableApplication **a3)
{
  int v5; // ebx
  __int64 v6; // rcx
  int v8; // eax
  char *v9; // rsi
  DWORD v10; // ebx
  int v11; // ebx
  DWORD LastError; // ebx
  int v13; // eax
  int v14; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  char *v16; // [rsp+48h] [rbp+10h] BYREF
  __int64 v17; // [rsp+50h] [rbp+18h] BYREF

  *a3 = 0;
  v16 = 0;
  v5 = (*(__int64 (__fastcall **)(struct Windows::Foundation::IExtensionRegistration *, char **))(*(_QWORD *)a2 + 152LL))(
         a2,
         &v16);
  if ( v5 < 0
    || (v5 = (**(__int64 (__fastcall ***)(HANDLE, GUID *, struct Windows::ApplicationModel::Core::IActivatableApplication **))v16)(
               v16,
               &GUID_92696c00_7578_48e1_ac1a_2ca909e2c8cf,
               a3),
        (*(void (__fastcall **)(char *))(*(_QWORD *)v16 + 16LL))(v16),
        v5 < 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x39E,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      (const char *)(unsigned int)v5,
      v14);
    return (unsigned int)v5;
  }
  *((_DWORD *)this + 62) = 0;
  v17 = 0;
  if ( (**(int (__fastcall ***)(_QWORD, GUID *, __int64 *))*a3)(*a3, &GUID_5524fe34_8da7_40a8_8165_e8b37a8b4a4b, &v17) >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v17 + 24LL))(v17, (char *)this + 248);
    if ( v8 >= 0 )
    {
      v9 = (char *)*((_QWORD *)this + 32);
      if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        LastError = GetLastError();
        CloseHandle(v9);
        SetLastError(LastError);
      }
      v10 = *((_DWORD *)this + 62);
      *((_QWORD *)this + 32) = 0;
      v16 = (char *)OpenProcess(0x101000u, 0, v10);
      if ( ((unsigned __int64)(v16 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0
        || !(unsigned __int8)IsUMgrOpenProcessHandleForAccessPresent()
        || (wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
              &v16,
              0),
            v13 = UMgrOpenProcessHandleForAccess(1052672, v10, &v16),
            v11 = v13,
            v13 >= 0) )
      {
        if ( (unsigned __int64)(v16 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          *((_QWORD *)this + 32) = v16;
        v11 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC3,
          (unsigned int)"onecoreuap\\internal\\base\\inc\\UserAwareCallerIdentity.h",
          (const char *)(unsigned int)v13,
          v14);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v16);
      }
      if ( v11 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x3A5,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
          (const char *)(unsigned int)v11,
          v14);
      goto LABEL_5;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3A2,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\appactivation.cpp",
      (const char *)(unsigned int)v8,
      v14);
  }
  AAMTraceProvider::DCOMActivationProcessIdQueryFailed<unsigned short const * &,unsigned short const * &>(
    (__int64 *)this + 2,
    (__int64 *)this + 3);
LABEL_5:
  v6 = v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return 0;
}

```

## disassembly

```asm
0x18002fe80  mov     [rsp+arg_0], rbx
0x18002fe85  mov     [rsp+arg_18], rbp
0x18002fe8a  push    rsi
0x18002fe8b  push    rdi
0x18002fe8c  push    r14; int
0x18002fe8e  sub     rsp, 20h
0x18002fe92  mov     rsi, r8
0x18002fe95  mov     r9, rdx
0x18002fe98  mov     rdi, rcx
0x18002fe9b  xor     ebp, ebp
0x18002fe9d  mov     [r8], rbp
0x18002fea0  mov     [rsp+38h+arg_8], rbp
0x18002fea5  mov     rax, [rdx]
0x18002fea8  lea     rdx, [rsp+38h+arg_8]
0x18002fead  mov     rcx, r9
0x18002feb0  mov     rax, [rax+98h]
0x18002feb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002febc  mov     ebx, eax
0x18002febe  test    eax, eax
0x18002fec0  js      loc_18002FF5F
0x18002fec6  mov     rcx, [rsp+38h+arg_8]
0x18002fecb  mov     rax, [rcx]
0x18002fece  mov     r8, rsi
0x18002fed1  lea     rdx, _GUID_92696c00_7578_48e1_ac1a_2ca909e2c8cf
0x18002fed8  mov     rax, [rax]
0x18002fedb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fee0  mov     ebx, eax
0x18002fee2  mov     rcx, [rsp+38h+arg_8]
0x18002fee7  mov     rax, [rcx]
0x18002feea  mov     rax, [rax+10h]
0x18002feee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fef3  test    ebx, ebx
0x18002fef5  js      short loc_18002FF5F
0x18002fef7  mov     [rdi+0F8h], ebp
0x18002fefd  mov     [rsp+38h+arg_10], rbp
0x18002ff02  mov     rcx, [rsi]
0x18002ff05  mov     rax, [rcx]
0x18002ff08  lea     r8, [rsp+38h+arg_10]
0x18002ff0d  lea     rdx, _GUID_5524fe34_8da7_40a8_8165_e8b37a8b4a4b
0x18002ff14  mov     rax, [rax]
0x18002ff17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff1c  test    eax, eax
0x18002ff1e  jns     short loc_18002FF7C
0x18002ff20  lea     rdx, [rdi+18h]
0x18002ff24  lea     rcx, [rdi+10h]
0x18002ff28  call    ??$DCOMActivationProcessIdQueryFailed@AEAPEBGAEAPEBG@AAMTraceProvider@@SAXAEAPEBG0@Z; AAMTraceProvider::DCOMActivationProcessIdQueryFailed<ushort const * &,ushort const * &>(ushort const * &,ushort const * &)
0x18002ff2d  nop
0x18002ff2e  mov     rcx, [rsp+38h+arg_10]
0x18002ff33  test    rcx, rcx
0x18002ff36  jz      short loc_18002FF4A
0x18002ff38  mov     [rsp+38h+arg_10], rbp
0x18002ff3d  mov     rax, [rcx]
0x18002ff40  mov     rax, [rax+10h]
0x18002ff44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff49  nop
0x18002ff4a  xor     eax, eax
0x18002ff4c  mov     rbx, [rsp+38h+arg_0]
0x18002ff51  mov     rbp, [rsp+38h+arg_18]
0x18002ff56  add     rsp, 20h
0x18002ff5a  pop     r14
0x18002ff5c  pop     rdi
0x18002ff5d  pop     rsi
0x18002ff5e  retn
0x18002ff5f  mov     rcx, [rsp+38h]; this
0x18002ff64  mov     r9d, ebx; char *
0x18002ff67  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18002ff6e  mov     edx, 39Eh; void *
0x18002ff73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ff78  mov     eax, ebx
0x18002ff7a  jmp     short loc_18002FF4C
0x18002ff7c  mov     rcx, [rsp+38h+arg_10]
0x18002ff81  mov     rax, [rcx]
0x18002ff84  lea     rdx, [rdi+0F8h]
0x18002ff8b  mov     rax, [rax+18h]
0x18002ff8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff94  mov     rcx, [rsp+38h]; this
0x18002ff99  test    eax, eax
0x18002ff9b  js      short loc_18003001A
0x18002ff9d  mov     rsi, [rdi+100h]
0x18002ffa4  lea     rax, [rsi-1]
0x18002ffa8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002ffac  jbe     loc_180030033
0x18002ffb2  mov     ebx, [rdi+0F8h]
0x18002ffb8  mov     [rdi+100h], rbp
0x18002ffbf  mov     r8d, ebx; dwProcessId
0x18002ffc2  xor     edx, edx; bInheritHandle
0x18002ffc4  mov     ecx, 101000h; dwDesiredAccess
0x18002ffc9  call    cs:__imp_OpenProcess
0x18002ffcf  mov     [rsp+38h+arg_8], rax
0x18002ffd4  inc     rax
0x18002ffd7  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002ffdd  jz      short loc_180030051
0x18002ffdf  mov     rcx, [rsp+38h+arg_8]
0x18002ffe4  lea     rax, [rcx-1]
0x18002ffe8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002ffec  jbe     loc_1800300AA
0x18002fff2  mov     ebx, ebp
0x18002fff4  mov     rcx, [rsp+38h]; this
0x18002fff9  test    ebx, ebx
0x18002fffb  jns     loc_18002FF2E
0x180030001  mov     r9d, ebx; char *
0x180030004  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18003000b  mov     edx, 3A5h; void *
0x180030010  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180030015  jmp     loc_18002FF2E
0x18003001a  mov     r9d, eax; char *
0x18003001d  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180030024  mov     edx, 3A2h; void *
0x180030029  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003002e  jmp     loc_18002FF20
0x180030033  call    cs:__imp_GetLastError
0x180030039  mov     ebx, eax
0x18003003b  mov     rcx, rsi; hObject
0x18003003e  call    cs:__imp_CloseHandle
0x180030044  mov     ecx, ebx; dwErrCode
0x180030046  call    cs:__imp_SetLastError
0x18003004c  jmp     loc_18002FFB2
0x180030051  call    IsUMgrOpenProcessHandleForAccessPresent
0x180030056  test    al, al
0x180030058  jz      short loc_18002FFDF
0x18003005a  xor     edx, edx
0x18003005c  lea     rcx, [rsp+38h+arg_8]
0x180030061  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180030066  lea     r8, [rsp+38h+arg_8]
0x18003006b  mov     edx, ebx
0x18003006d  mov     ecx, 101000h
0x180030072  call    cs:__imp_UMgrOpenProcessHandleForAccess
0x180030078  mov     ebx, eax
0x18003007a  test    eax, eax
0x18003007c  jns     loc_18002FFDF
0x180030082  mov     rcx, [rsp+38h]; this
0x180030087  mov     r9d, eax; char *
0x18003008a  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\base\\inc\\UserAw"...
0x180030091  mov     edx, 0C3h; void *
0x180030096  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003009b  lea     rcx, [rsp+38h+arg_8]
0x1800300a0  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800300a5  jmp     loc_18002FFF4
0x1800300aa  mov     [rdi+100h], rcx
0x1800300b1  jmp     loc_18002FFF2
```
