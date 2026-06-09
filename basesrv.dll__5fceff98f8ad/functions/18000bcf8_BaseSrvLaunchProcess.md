# BaseSrvLaunchProcess

- ea: `0x18000bcf8`
- end: `0x18000bff7`
- name: `BaseSrvLaunchProcess`
- size: `767`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, __int64, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000ba74`

## callees

- `0x180008220`
- `0x18000b42c`
- `0x18000bcf8`
- `0x18000db1d`
- `0x18000db40`

## import_xrefs

- `ntdll!NtClose` at `0x18000bfbe`
- `ntdll!NtClose` at `0x18000bfbe`
- `ntdll!NtQueryInformationProcess` at `0x18000bdf8`
- `ntdll!NtQueryInformationProcess` at `0x18000bdf8`
- `ntdll!NtQueryInformationToken` at `0x18000bdb5`
- `ntdll!NtQueryInformationToken` at `0x18000bdb5`
- `ntdll!NtSetInformationThread` at `0x18000bfa6`
- `ntdll!NtSetInformationThread` at `0x18000bfa6`
- `ntdll!RtlCreateProcessParametersEx` at `0x18000bf0a`
- `ntdll!RtlCreateProcessParametersEx` at `0x18000bf0a`
- `ntdll!NtCreateUserProcess` at `0x18000bf5c`
- `ntdll!NtCreateUserProcess` at `0x18000bf5c`
- `ntdll!RtlDestroyProcessParameters` at `0x18000bf81`
- `ntdll!RtlDestroyProcessParameters` at `0x18000bf81`

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
  __int64 v21; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v22[88]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v23[18]; // [rsp+100h] [rbp+0h] BYREF

  memset_0(&v21, 0, 0x58u);
  memset_0(v23, 0, 0x88u);
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
          memset_0(v22, 0, 0x50u);
          v21 = 88;
          v23[4] = 0;
          v23[8] = 0;
          v23[12] = 0;
          v23[16] = 0;
          v23[3] = *((_QWORD *)a1 + 1);
          v23[2] = *a1;
          v23[6] = 8;
          v23[10] = 8;
          v23[11] = TokenHandle;
          v23[0] = 136;
          v23[1] = 131077;
          v23[5] = 393216;
          v23[7] = v12;
          v23[9] = 393218;
          v23[13] = 65539;
          v23[14] = 16;
          v23[15] = a4;
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
              v11 = NtCreateUserProcess(&v19, &v18, 0x2000000, 0x2000000, 0, 0, 0, 1, ProcessParameters, &v21, v23);
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
0x18000bcf8  mov     [rsp-8+arg_18], rbx
0x18000bcfd  push    rbp
0x18000bcfe  push    rsi
0x18000bcff  push    rdi
0x18000bd00  push    r12
0x18000bd02  push    r13
0x18000bd04  push    r14
0x18000bd06  push    r15
0x18000bd08  lea     rbp, [rsp-0A0h]
0x18000bd10  sub     rsp, 1A0h
0x18000bd17  mov     rax, cs:__security_cookie
0x18000bd1e  xor     rax, rsp
0x18000bd21  mov     [rbp+0D0h+var_40], rax
0x18000bd28  mov     r14, [rbp+0D0h+arg_20]
0x18000bd2f  mov     r12, rdx
0x18000bd32  mov     r15, [rbp+0D0h+arg_28]
0x18000bd39  xor     edx, edx; Val
0x18000bd3b  mov     rbx, r8
0x18000bd3e  mov     rsi, rcx
0x18000bd41  lea     rcx, [rbp+0D0h+var_130]; void *
0x18000bd45  mov     r13, r9
0x18000bd48  lea     r8d, [rdx+58h]; Size
0x18000bd4c  call    memset_0
0x18000bd51  xor     edx, edx; Val
0x18000bd53  lea     rcx, [rbp+0D0h+var_D0]; void *
0x18000bd57  mov     r8d, 88h; Size
0x18000bd5d  call    memset_0
0x18000bd62  xor     edi, edi
0x18000bd64  lea     r8, [rsp+1D0h+TokenHandle]
0x18000bd69  mov     rcx, rbx
0x18000bd6c  mov     [rbp+0D0h+var_148], rdi
0x18000bd70  mov     [rsp+1D0h+ProcessParameters], rdi
0x18000bd75  mov     [rbp+0D0h+var_150], rdi
0x18000bd79  lea     edx, [rdi+1]
0x18000bd7c  mov     [rsp+1D0h+TokenHandle], rdi
0x18000bd81  mov     [rsp+1D0h+TokenInformation], edi
0x18000bd85  mov     [rsp+1D0h+ProcessInformation], edi
0x18000bd89  mov     [rsp+1D0h+var_170], edi
0x18000bd8d  call    BaseSrvGetUserToken
0x18000bd92  test    eax, eax
0x18000bd94  js      loc_18000BFCC
0x18000bd9a  mov     rcx, [rsp+1D0h+TokenHandle]; TokenHandle
0x18000bd9f  lea     rax, [rsp+1D0h+var_170]
0x18000bda4  lea     r9d, [rdi+4]; TokenInformationLength
0x18000bda8  mov     [rsp+1D0h+ReturnLength], rax; ReturnLength
0x18000bdad  lea     r8, [rsp+1D0h+TokenInformation]; TokenInformation
0x18000bdb2  lea     edx, [rdi+0Ch]; TokenInformationClass
0x18000bdb5  call    cs:__imp_NtQueryInformationToken
0x18000bdbc  nop     dword ptr [rax+rax+00h]
0x18000bdc1  mov     ebx, eax
0x18000bdc3  test    eax, eax
0x18000bdc5  js      loc_18000BFB9
0x18000bdcb  mov     rax, gs:70h
0x18000bdd4  lea     r8, [rsp+1D0h+ProcessInformation]; ProcessInformation
0x18000bdd9  mov     r9d, 4; ProcessInformationLength
0x18000bddf  mov     rcx, [rax+38h]
0x18000bde3  lea     rax, [rsp+1D0h+var_170]
0x18000bde8  lea     edx, [r9+14h]; ProcessInformationClass
0x18000bdec  mov     [rsp+1D0h+ReturnLength], rax; ReturnLength
0x18000bdf1  mov     rdi, [rcx+50h]
0x18000bdf5  mov     rcx, rdi; ProcessHandle
0x18000bdf8  call    cs:__imp_NtQueryInformationProcess
0x18000bdff  nop     dword ptr [rax+rax+00h]
0x18000be04  mov     ebx, eax
0x18000be06  test    eax, eax
0x18000be08  js      loc_18000BFB9
0x18000be0e  mov     eax, [rsp+1D0h+ProcessInformation]
0x18000be12  cmp     [rsp+1D0h+TokenInformation], eax
0x18000be16  jz      short loc_18000BE22
0x18000be18  mov     ebx, 0C0000022h
0x18000be1d  jmp     loc_18000BFB9
0x18000be22  xor     edx, edx; Val
0x18000be24  lea     rcx, [rbp+0D0h+var_128]; void *
0x18000be28  lea     r8d, [rdx+50h]; Size
0x18000be2c  call    memset_0
0x18000be31  xor     eax, eax
0x18000be33  mov     [rbp+0D0h+var_130], 58h ; 'X'
0x18000be3b  mov     [rbp+0D0h+var_B0], rax
0x18000be3f  mov     rcx, rdi
0x18000be42  mov     [rbp+0D0h+var_90], rax
0x18000be46  mov     [rbp+0D0h+var_70], rax
0x18000be4a  mov     [rbp+0D0h+var_50], rax
0x18000be51  mov     rax, [rsi+8]
0x18000be55  mov     [rbp+0D0h+var_B8], rax
0x18000be59  movzx   eax, word ptr [rsi]
0x18000be5c  mov     [rbp+0D0h+var_C0], rax
0x18000be60  mov     eax, 8
0x18000be65  mov     [rbp+0D0h+var_A0], rax
0x18000be69  mov     [rbp+0D0h+var_80], rax
0x18000be6d  mov     rax, [rsp+1D0h+TokenHandle]
0x18000be72  mov     [rbp+0D0h+var_78], rax
0x18000be76  mov     [rbp+0D0h+var_D0], 88h
0x18000be7e  mov     [rbp+0D0h+var_C8], 20005h
0x18000be86  mov     [rbp+0D0h+var_A8], 60000h
0x18000be8e  mov     [rbp+0D0h+var_98], rdi
0x18000be92  mov     [rbp+0D0h+var_88], 60002h
0x18000be9a  mov     [rbp+0D0h+var_68], 10003h
0x18000bea2  mov     [rbp+0D0h+var_60], 10h
0x18000beaa  mov     [rbp+0D0h+var_58], r13
0x18000beae  call    BasepImpersonateClientProcess
0x18000beb3  xor     edi, edi
0x18000beb5  test    eax, eax
0x18000beb7  js      loc_18000BFB4
0x18000bebd  mov     rax, gs:60h
0x18000bec6  lea     r13d, [rdi+1]
0x18000beca  mov     dword ptr [rsp+1D0h+var_180], r13d
0x18000becf  lea     r9, BaseSrvWindowsSystemDirectory
0x18000bed6  mov     [rsp+1D0h+var_188], rdi
0x18000bedb  xor     r8d, r8d
0x18000bede  mov     [rsp+1D0h+var_190], rdi
0x18000bee3  mov     rdx, rsi
0x18000bee6  mov     rcx, [rax+20h]
0x18000beea  add     rcx, 0C0h
0x18000bef1  mov     [rsp+1D0h+var_198], rcx
0x18000bef6  lea     rcx, [rsp+1D0h+ProcessParameters]
0x18000befb  mov     [rsp+1D0h+var_1A0], rdi
0x18000bf00  mov     [rsp+1D0h+var_1A8], rdi
0x18000bf05  mov     [rsp+1D0h+ReturnLength], r12
0x18000bf0a  call    cs:__imp_RtlCreateProcessParametersEx
0x18000bf11  nop     dword ptr [rax+rax+00h]
0x18000bf16  mov     ebx, eax
0x18000bf18  test    eax, eax
0x18000bf1a  js      short loc_18000BF8D
0x18000bf1c  lea     rax, [rbp+0D0h+var_D0]
0x18000bf20  mov     r8d, 2000000h
0x18000bf26  mov     [rsp+1D0h+var_180], rax
0x18000bf2b  lea     rdx, [rbp+0D0h+var_150]
0x18000bf2f  lea     rax, [rbp+0D0h+var_130]
0x18000bf33  mov     r9d, r8d
0x18000bf36  mov     [rsp+1D0h+var_188], rax
0x18000bf3b  lea     rcx, [rbp+0D0h+var_148]
0x18000bf3f  mov     rax, [rsp+1D0h+ProcessParameters]
0x18000bf44  mov     [rsp+1D0h+var_190], rax
0x18000bf49  mov     dword ptr [rsp+1D0h+var_198], r13d
0x18000bf4e  mov     dword ptr [rsp+1D0h+var_1A0], edi
0x18000bf52  mov     [rsp+1D0h+var_1A8], rdi
0x18000bf57  mov     [rsp+1D0h+ReturnLength], rdi
0x18000bf5c  call    cs:__imp_NtCreateUserProcess
0x18000bf63  nop     dword ptr [rax+rax+00h]
0x18000bf68  mov     ebx, eax
0x18000bf6a  test    eax, eax
0x18000bf6c  js      short loc_18000BF7C
0x18000bf6e  mov     rax, [rbp+0D0h+var_150]
0x18000bf72  mov     [r14], rax
0x18000bf75  mov     rax, [rbp+0D0h+var_148]
0x18000bf79  mov     [r15], rax
0x18000bf7c  mov     rcx, [rsp+1D0h+ProcessParameters]; ProcessParameters
0x18000bf81  call    cs:__imp_RtlDestroyProcessParameters
0x18000bf88  nop     dword ptr [rax+rax+00h]
0x18000bf8d  mov     r9d, 8; ThreadInformationLength
0x18000bf93  mov     [rbp+0D0h+ThreadInformation], rdi
0x18000bf97  lea     r8, [rbp+0D0h+ThreadInformation]; ThreadInformation
0x18000bf9b  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000bfa2  lea     edx, [r9-3]; ThreadInformationClass
0x18000bfa6  call    cs:__imp_NtSetInformationThread
0x18000bfad  nop     dword ptr [rax+rax+00h]
0x18000bfb2  jmp     short loc_18000BFB9
0x18000bfb4  mov     ebx, 0C00000A5h
0x18000bfb9  mov     rcx, [rsp+1D0h+TokenHandle]; Handle
0x18000bfbe  call    cs:__imp_NtClose
0x18000bfc5  nop     dword ptr [rax+rax+00h]
0x18000bfca  mov     eax, ebx
0x18000bfcc  mov     rcx, [rbp+0D0h+var_40]
0x18000bfd3  xor     rcx, rsp; StackCookie
0x18000bfd6  call    __security_check_cookie
0x18000bfdb  mov     rbx, [rsp+1D0h+arg_18]
0x18000bfe3  add     rsp, 1A0h
0x18000bfea  pop     r15
0x18000bfec  pop     r14
0x18000bfee  pop     r13
0x18000bff0  pop     r12
0x18000bff2  pop     rdi
0x18000bff3  pop     rsi
0x18000bff4  pop     rbp
0x18000bff5  retn
```
