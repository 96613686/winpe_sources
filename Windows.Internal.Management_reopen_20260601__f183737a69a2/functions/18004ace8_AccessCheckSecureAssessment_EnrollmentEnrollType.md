# AccessCheckSecureAssessment(EnrollmentEnrollType)

- ea: `0x18004ace8`
- end: `0x18004adb4`
- name: `?AccessCheckSecureAssessment@@YAJW4EnrollmentEnrollType@@@Z`
- size: `204`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18005b964`
- `0x180069a94`

## callees

- `0x1800151e0`
- `0x180017a88`
- `0x1800181cc`
- `0x1800183bc`
- `0x18004ace8`
- `0x18004bd64`
- `0x180095efc`
- `0x180095f5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ad42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ad42`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004ad32`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004ad32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004ad15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004ad15`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 AccessCheckSecureAssessment()
{
  signed int v0; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  CEnrollmentLogger *Logger; // rax
  _BYTE v5[24]; // [rsp+20h] [rbp-18h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+10h] BYREF

  v5[0] = 0;
  v5[2] = 0;
  v0 = AutoImpersonate::ImpersonateClient((AutoImpersonate *)v5);
  if ( v0 >= 0 )
  {
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      AutoImpersonate::RevertToSelf((AutoImpersonate *)v5);
      v0 = CapabilityCheck_0(TokenHandle);
      if ( v0 < 0 )
      {
        Logger = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogAccessCheckFailed(Logger, v0, 3u, L"secureAssessment");
      }
    }
    else
    {
      LastError = GetLastError();
      v0 = LastError;
      if ( LastError > 0 )
        v0 = (unsigned __int16)LastError | 0x80070000;
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  }
  AutoImpersonate::~AutoImpersonate((AutoImpersonate *)v5);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x18004ace8  push    rbx
0x18004acea  sub     rsp, 30h
0x18004acee  mov     [rsp+38h+var_18], 0
0x18004acf3  mov     [rsp+38h+var_16], 0
0x18004acf8  lea     rcx, [rsp+38h+var_18]; this
0x18004acfd  call    ?ImpersonateClient@AutoImpersonate@@QEAAJXZ; AutoImpersonate::ImpersonateClient(void)
0x18004ad02  mov     ebx, eax
0x18004ad04  test    eax, eax
0x18004ad06  js      loc_18004ADA1
0x18004ad0c  mov     [rsp+38h+TokenHandle], 0
0x18004ad15  call    cs:__imp_GetCurrentThread
0x18004ad1c  nop     dword ptr [rax+rax+00h]
0x18004ad21  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x18004ad26  mov     edx, 8; DesiredAccess
0x18004ad2b  lea     r8d, [rdx-7]; OpenAsSelf
0x18004ad2f  mov     rcx, rax; ThreadHandle
0x18004ad32  call    cs:__imp_OpenThreadToken
0x18004ad39  nop     dword ptr [rax+rax+00h]
0x18004ad3e  test    eax, eax
0x18004ad40  jnz     short loc_18004AD5F
0x18004ad42  call    cs:__imp_GetLastError
0x18004ad49  nop     dword ptr [rax+rax+00h]
0x18004ad4e  mov     ebx, eax
0x18004ad50  test    eax, eax
0x18004ad52  jle     short loc_18004AD96
0x18004ad54  movzx   ebx, ax
0x18004ad57  or      ebx, 80070000h
0x18004ad5d  jmp     short loc_18004AD96
0x18004ad5f  lea     rcx, [rsp+38h+var_18]; this
0x18004ad64  call    ?RevertToSelf@AutoImpersonate@@QEAAJXZ; AutoImpersonate::RevertToSelf(void)
0x18004ad69  mov     rcx, [rsp+38h+TokenHandle]
0x18004ad6e  call    CapabilityCheck_0
0x18004ad73  mov     ebx, eax
0x18004ad75  test    eax, eax
0x18004ad77  jns     short loc_18004AD96
0x18004ad79  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18004ad7e  lea     r9, aSecureassessme; "secureAssessment"
0x18004ad85  mov     r8d, 3; unsigned int
0x18004ad8b  mov     edx, ebx; int
0x18004ad8d  mov     rcx, rax; this
0x18004ad90  call    ?LogAccessCheckFailed@CEnrollmentLogger@@QEAAXJIPEBG@Z; CEnrollmentLogger::LogAccessCheckFailed(long,uint,ushort const *)
0x18004ad95  nop
0x18004ad96  lea     rcx, [rsp+38h+TokenHandle]
0x18004ad9b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004ada0  nop
0x18004ada1  lea     rcx, [rsp+38h+var_18]; this
0x18004ada6  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18004adab  mov     eax, ebx
0x18004adad  add     rsp, 30h
0x18004adb1  pop     rbx
0x18004adb2  retn
```
