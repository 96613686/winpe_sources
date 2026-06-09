# AccessCheckSecureAssessment(EnrollmentEnrollType)

- ea: `0x18004ab00`
- end: `0x18004abb9`
- name: `?AccessCheckSecureAssessment@@YAJW4EnrollmentEnrollType@@@Z`
- size: `185`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18005aec4`
- `0x18006890c`

## callees

- `0x180014af0`
- `0x180017284`
- `0x180018f88`
- `0x1800199f8`
- `0x18004ab00`
- `0x18004bb24`
- `0x180093684`
- `0x1800936e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ab4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ab4e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004ab44`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004ab44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004ab2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004ab2d`

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
0x18004ab00  push    rbx
0x18004ab02  sub     rsp, 30h
0x18004ab06  mov     [rsp+38h+var_18], 0
0x18004ab0b  mov     [rsp+38h+var_16], 0
0x18004ab10  lea     rcx, [rsp+38h+var_18]; this
0x18004ab15  call    ?ImpersonateClient@AutoImpersonate@@QEAAJXZ; AutoImpersonate::ImpersonateClient(void)
0x18004ab1a  mov     ebx, eax
0x18004ab1c  test    eax, eax
0x18004ab1e  js      loc_18004ABA7
0x18004ab24  mov     [rsp+38h+TokenHandle], 0
0x18004ab2d  call    cs:__imp_GetCurrentThread
0x18004ab33  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x18004ab38  mov     edx, 8; DesiredAccess
0x18004ab3d  lea     r8d, [rdx-7]; OpenAsSelf
0x18004ab41  mov     rcx, rax; ThreadHandle
0x18004ab44  call    cs:__imp_OpenThreadToken
0x18004ab4a  test    eax, eax
0x18004ab4c  jnz     short loc_18004AB65
0x18004ab4e  call    cs:__imp_GetLastError
0x18004ab54  mov     ebx, eax
0x18004ab56  test    eax, eax
0x18004ab58  jle     short loc_18004AB9C
0x18004ab5a  movzx   ebx, ax
0x18004ab5d  or      ebx, 80070000h
0x18004ab63  jmp     short loc_18004AB9C
0x18004ab65  lea     rcx, [rsp+38h+var_18]; this
0x18004ab6a  call    ?RevertToSelf@AutoImpersonate@@QEAAJXZ; AutoImpersonate::RevertToSelf(void)
0x18004ab6f  mov     rcx, [rsp+38h+TokenHandle]
0x18004ab74  call    CapabilityCheck_0
0x18004ab79  mov     ebx, eax
0x18004ab7b  test    eax, eax
0x18004ab7d  jns     short loc_18004AB9C
0x18004ab7f  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18004ab84  lea     r9, aSecureassessme; "secureAssessment"
0x18004ab8b  mov     r8d, 3; unsigned int
0x18004ab91  mov     edx, ebx; int
0x18004ab93  mov     rcx, rax; this
0x18004ab96  call    ?LogAccessCheckFailed@CEnrollmentLogger@@QEAAXJIPEBG@Z; CEnrollmentLogger::LogAccessCheckFailed(long,uint,ushort const *)
0x18004ab9b  nop
0x18004ab9c  lea     rcx, [rsp+38h+TokenHandle]
0x18004aba1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004aba6  nop
0x18004aba7  lea     rcx, [rsp+38h+var_18]; this
0x18004abac  call    ??1AutoImpersonate@@QEAA@XZ; AutoImpersonate::~AutoImpersonate(void)
0x18004abb1  mov     eax, ebx
0x18004abb3  add     rsp, 30h
0x18004abb7  pop     rbx
0x18004abb8  retn
```
