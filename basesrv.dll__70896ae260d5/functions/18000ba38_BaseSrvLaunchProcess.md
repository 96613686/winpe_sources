# BaseSrvLaunchProcess

- ea: `0x18000ba38`
- end: `0x18000bd13`
- name: `BaseSrvLaunchProcess`
- size: `731`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, __int64, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000b7ac`

## callees

- `0x180007f20`
- `0x18000b18c`
- `0x18000ba38`
- `0x18000d713`
- `0x18000d730`

## import_xrefs

- `ntdll!NtClose` at `0x18000bcda`
- `ntdll!NtClose` at `0x18000bcda`
- `ntdll!NtQueryInformationProcess` at `0x18000bb38`
- `ntdll!NtQueryInformationProcess` at `0x18000bb38`
- `ntdll!NtQueryInformationToken` at `0x18000baf5`
- `ntdll!NtQueryInformationToken` at `0x18000baf5`
- `ntdll!NtSetInformationThread` at `0x18000bcc2`
- `ntdll!NtSetInformationThread` at `0x18000bcc2`
- `ntdll!RtlCreateProcessParametersEx` at `0x18000bc26`
- `ntdll!RtlCreateProcessParametersEx` at `0x18000bc26`
- `ntdll!NtCreateUserProcess` at `0x18000bc78`
- `ntdll!NtCreateUserProcess` at `0x18000bc78`
- `ntdll!RtlDestroyProcessParameters` at `0x18000bc9d`
- `ntdll!RtlDestroyProcessParameters` at `0x18000bc9d`

## pseudocode

```c
__int64 __fastcall BaseSrvLaunchProcess(
        unsigned __int16 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        _QWORD *a6)
{
  __int64 result; // rax
  NTSTATUS v11; // ebx
  void *v12; // rdi
  ULONG ReturnLength; // [rsp+60h] [rbp-A0h] BYREF
  int ProcessInformation; // [rsp+64h] [rbp-9Ch] BYREF
  int TokenInformation; // [rsp+68h] [rbp-98h] BYREF
  HANDLE TokenHandle; // [rsp+70h] [rbp-90h] BYREF
  PRTL_USER_PROCESS_PARAMETERS ProcessParameters; // [rsp+78h] [rbp-88h] BYREF
  __int64 v18; // [rsp+80h] [rbp-80h] BYREF
  __int64 v19; // [rsp+88h] [rbp-78h] BYREF
  __int64 ThreadInformation; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v21[12]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v22[18]; // [rsp+100h] [rbp+0h] BYREF

  memset_0(v21, 0, 0x58u);
  memset_0(v22, 0, 0x88u);
  v19 = 0;
  ProcessParameters = 0;
  v18 = 0;
  TokenHandle = 0;
  TokenInformation = 0;
  ProcessInformation = 0;
  ReturnLength = 0;
  result = BaseSrvGetUserToken(a3, 1, &TokenHandle);
  if ( (int)result >= 0 )
  {
    v11 = NtQueryInformationToken(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength);
    if ( v11 >= 0 )
    {
      v12 = *(void **)(*((_QWORD *)NtCurrentTeb()->CsrClientThread + 7) + 80LL);
      v11 = NtQueryInformationProcess(v12, ProcessSessionInformation, &ProcessInformation, 4u, &ReturnLength);
      if ( v11 >= 0 )
      {
        if ( TokenInformation == ProcessInformation )
        {
          v22[3] = *((_QWORD *)a1 + 1);
          v22[2] = *a1;
          v22[6] = 8;
          v22[10] = 8;
          v22[11] = TokenHandle;
          v21[0] = 88;
          v22[0] = 136;
          v22[1] = 131077;
          v22[5] = 393216;
          v22[7] = v12;
          v22[9] = 393218;
          v22[13] = 65539;
          v22[14] = 16;
          v22[15] = a4;
          if ( (int)BasepImpersonateClientProcess(v12) < 0 )
          {
            v11 = -1073741659;
          }
          else
          {
            v11 = RtlCreateProcessParametersEx(
                    &ProcessParameters,
                    a1,
                    0,
                    &BaseSrvWindowsSystemDirectory,
                    a2,
                    0,
                    0,
                    &NtCurrentPeb()->ProcessParameters->DesktopInfo,
                    0,
                    0,
                    1);
            if ( v11 >= 0 )
            {
              v11 = NtCreateUserProcess(&v19, &v18, 0x2000000, 0x2000000, 0, 0, 0, 1, ProcessParameters, v21, v22);
              if ( v11 >= 0 )
              {
                *a5 = v18;
                *a6 = v19;
              }
              RtlDestroyProcessParameters(ProcessParameters);
            }
            ThreadInformation = 0;
            NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
          }
        }
        else
        {
          v11 = -1073741790;
        }
      }
    }
    NtClose(TokenHandle);
    return (unsigned int)v11;
  }
  return result;
}

```

## disassembly

```asm
0x18000ba38  mov     [rsp-8+arg_18], rbx
0x18000ba3d  push    rbp
0x18000ba3e  push    rsi
0x18000ba3f  push    rdi
0x18000ba40  push    r12
0x18000ba42  push    r13
0x18000ba44  push    r14
0x18000ba46  push    r15
0x18000ba48  lea     rbp, [rsp-0A0h]
0x18000ba50  sub     rsp, 1A0h
0x18000ba57  mov     rax, cs:__security_cookie
0x18000ba5e  xor     rax, rsp
0x18000ba61  mov     [rbp+0D0h+var_40], rax
0x18000ba68  mov     r14, [rbp+0D0h+arg_20]
0x18000ba6f  mov     r13, rdx
0x18000ba72  mov     r15, [rbp+0D0h+arg_28]
0x18000ba79  xor     edx, edx; Val
0x18000ba7b  mov     rbx, r8
0x18000ba7e  mov     rsi, rcx
0x18000ba81  lea     rcx, [rbp+0D0h+var_130]; void *
0x18000ba85  mov     r12, r9
0x18000ba88  lea     r8d, [rdx+58h]; Size
0x18000ba8c  call    memset_0
0x18000ba91  xor     edx, edx; Val
0x18000ba93  lea     rcx, [rbp+0D0h+var_D0]; void *
0x18000ba97  mov     r8d, 88h; Size
0x18000ba9d  call    memset_0
0x18000baa2  xor     edi, edi
0x18000baa4  lea     r8, [rsp+1D0h+TokenHandle]
0x18000baa9  mov     rcx, rbx
0x18000baac  mov     [rbp+0D0h+var_148], rdi
0x18000bab0  mov     [rsp+1D0h+ProcessParameters], rdi
0x18000bab5  mov     [rbp+0D0h+var_150], rdi
0x18000bab9  lea     edx, [rdi+1]
0x18000babc  mov     [rsp+1D0h+TokenHandle], rdi
0x18000bac1  mov     [rsp+1D0h+TokenInformation], edi
0x18000bac5  mov     [rsp+1D0h+ProcessInformation], edi
0x18000bac9  mov     [rsp+1D0h+var_170], edi
0x18000bacd  call    BaseSrvGetUserToken
0x18000bad2  test    eax, eax
0x18000bad4  js      loc_18000BCE8
0x18000bada  mov     rcx, [rsp+1D0h+TokenHandle]; TokenHandle
0x18000badf  lea     rax, [rsp+1D0h+var_170]
0x18000bae4  lea     r9d, [rdi+4]; TokenInformationLength
0x18000bae8  mov     [rsp+1D0h+ReturnLength], rax; ReturnLength
0x18000baed  lea     r8, [rsp+1D0h+TokenInformation]; TokenInformation
0x18000baf2  lea     edx, [rdi+0Ch]; TokenInformationClass
0x18000baf5  call    cs:__imp_NtQueryInformationToken
0x18000bafc  nop     dword ptr [rax+rax+00h]
0x18000bb01  mov     ebx, eax
0x18000bb03  test    eax, eax
0x18000bb05  js      loc_18000BCD5
0x18000bb0b  mov     rax, gs:70h
0x18000bb14  lea     r8, [rsp+1D0h+ProcessInformation]; ProcessInformation
0x18000bb19  mov     r9d, 4; ProcessInformationLength
0x18000bb1f  mov     rcx, [rax+38h]
0x18000bb23  lea     rax, [rsp+1D0h+var_170]
0x18000bb28  lea     edx, [r9+14h]; ProcessInformationClass
0x18000bb2c  mov     [rsp+1D0h+ReturnLength], rax; ReturnLength
0x18000bb31  mov     rdi, [rcx+50h]
0x18000bb35  mov     rcx, rdi; ProcessHandle
0x18000bb38  call    cs:__imp_NtQueryInformationProcess
0x18000bb3f  nop     dword ptr [rax+rax+00h]
0x18000bb44  mov     ebx, eax
0x18000bb46  test    eax, eax
0x18000bb48  js      loc_18000BCD5
0x18000bb4e  mov     eax, [rsp+1D0h+ProcessInformation]
0x18000bb52  cmp     [rsp+1D0h+TokenInformation], eax
0x18000bb56  jz      short loc_18000BB62
0x18000bb58  mov     ebx, 0C0000022h
0x18000bb5d  jmp     loc_18000BCD5
0x18000bb62  mov     rax, [rsi+8]
0x18000bb66  mov     rcx, rdi
0x18000bb69  mov     [rbp+0D0h+var_B8], rax
0x18000bb6d  movzx   eax, word ptr [rsi]
0x18000bb70  mov     [rbp+0D0h+var_C0], rax
0x18000bb74  mov     eax, 8
0x18000bb79  mov     [rbp+0D0h+var_A0], rax
0x18000bb7d  mov     [rbp+0D0h+var_80], rax
0x18000bb81  mov     rax, [rsp+1D0h+TokenHandle]
0x18000bb86  mov     [rbp+0D0h+var_78], rax
0x18000bb8a  mov     [rbp+0D0h+var_130], 58h ; 'X'
0x18000bb92  mov     [rbp+0D0h+var_D0], 88h
0x18000bb9a  mov     [rbp+0D0h+var_C8], 20005h
0x18000bba2  mov     [rbp+0D0h+var_A8], 60000h
0x18000bbaa  mov     [rbp+0D0h+var_98], rdi
0x18000bbae  mov     [rbp+0D0h+var_88], 60002h
0x18000bbb6  mov     [rbp+0D0h+var_68], 10003h
0x18000bbbe  mov     [rbp+0D0h+var_60], 10h
0x18000bbc6  mov     [rbp+0D0h+var_58], r12
0x18000bbca  call    BasepImpersonateClientProcess
0x18000bbcf  xor     edi, edi
0x18000bbd1  test    eax, eax
0x18000bbd3  js      loc_18000BCD0
0x18000bbd9  mov     rax, gs:60h
0x18000bbe2  lea     r12d, [rdi+1]
0x18000bbe6  mov     dword ptr [rsp+1D0h+var_180], r12d
0x18000bbeb  lea     r9, BaseSrvWindowsSystemDirectory
0x18000bbf2  mov     [rsp+1D0h+var_188], rdi
0x18000bbf7  xor     r8d, r8d
0x18000bbfa  mov     [rsp+1D0h+var_190], rdi
0x18000bbff  mov     rdx, rsi
0x18000bc02  mov     rcx, [rax+20h]
0x18000bc06  add     rcx, 0C0h
0x18000bc0d  mov     [rsp+1D0h+var_198], rcx
0x18000bc12  lea     rcx, [rsp+1D0h+ProcessParameters]
0x18000bc17  mov     [rsp+1D0h+var_1A0], rdi
0x18000bc1c  mov     [rsp+1D0h+var_1A8], rdi
0x18000bc21  mov     [rsp+1D0h+ReturnLength], r13
0x18000bc26  call    cs:__imp_RtlCreateProcessParametersEx
0x18000bc2d  nop     dword ptr [rax+rax+00h]
0x18000bc32  mov     ebx, eax
0x18000bc34  test    eax, eax
0x18000bc36  js      short loc_18000BCA9
0x18000bc38  lea     rax, [rbp+0D0h+var_D0]
0x18000bc3c  mov     r8d, 2000000h
0x18000bc42  mov     [rsp+1D0h+var_180], rax
0x18000bc47  lea     rdx, [rbp+0D0h+var_150]
0x18000bc4b  lea     rax, [rbp+0D0h+var_130]
0x18000bc4f  mov     r9d, r8d
0x18000bc52  mov     [rsp+1D0h+var_188], rax
0x18000bc57  lea     rcx, [rbp+0D0h+var_148]
0x18000bc5b  mov     rax, [rsp+1D0h+ProcessParameters]
0x18000bc60  mov     [rsp+1D0h+var_190], rax
0x18000bc65  mov     dword ptr [rsp+1D0h+var_198], r12d
0x18000bc6a  mov     dword ptr [rsp+1D0h+var_1A0], edi
0x18000bc6e  mov     [rsp+1D0h+var_1A8], rdi
0x18000bc73  mov     [rsp+1D0h+ReturnLength], rdi
0x18000bc78  call    cs:__imp_NtCreateUserProcess
0x18000bc7f  nop     dword ptr [rax+rax+00h]
0x18000bc84  mov     ebx, eax
0x18000bc86  test    eax, eax
0x18000bc88  js      short loc_18000BC98
0x18000bc8a  mov     rax, [rbp+0D0h+var_150]
0x18000bc8e  mov     [r14], rax
0x18000bc91  mov     rax, [rbp+0D0h+var_148]
0x18000bc95  mov     [r15], rax
0x18000bc98  mov     rcx, [rsp+1D0h+ProcessParameters]; ProcessParameters
0x18000bc9d  call    cs:__imp_RtlDestroyProcessParameters
0x18000bca4  nop     dword ptr [rax+rax+00h]
0x18000bca9  mov     r9d, 8; ThreadInformationLength
0x18000bcaf  mov     [rbp+0D0h+ThreadInformation], rdi
0x18000bcb3  lea     r8, [rbp+0D0h+ThreadInformation]; ThreadInformation
0x18000bcb7  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000bcbe  lea     edx, [r9-3]; ThreadInformationClass
0x18000bcc2  call    cs:__imp_NtSetInformationThread
0x18000bcc9  nop     dword ptr [rax+rax+00h]
0x18000bcce  jmp     short loc_18000BCD5
0x18000bcd0  mov     ebx, 0C00000A5h
0x18000bcd5  mov     rcx, [rsp+1D0h+TokenHandle]; Handle
0x18000bcda  call    cs:__imp_NtClose
0x18000bce1  nop     dword ptr [rax+rax+00h]
0x18000bce6  mov     eax, ebx
0x18000bce8  mov     rcx, [rbp+0D0h+var_40]
0x18000bcef  xor     rcx, rsp; StackCookie
0x18000bcf2  call    __security_check_cookie
0x18000bcf7  mov     rbx, [rsp+1D0h+arg_18]
0x18000bcff  add     rsp, 1A0h
0x18000bd06  pop     r15
0x18000bd08  pop     r14
0x18000bd0a  pop     r13
0x18000bd0c  pop     r12
0x18000bd0e  pop     rdi
0x18000bd0f  pop     rsi
0x18000bd10  pop     rbp
0x18000bd11  retn
```
