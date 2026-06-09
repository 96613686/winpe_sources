# CUpdateDeploymentJob::Pause(void)

- ea: `0x180031940`
- end: `0x180031afa`
- name: `?Pause@CUpdateDeploymentJob@@UEAAJXZ`
- size: `442`
- prototype: `__int64 __fastcall(CUpdateDeploymentJob *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002214`
- `0x180003180`
- `0x180007b6c`
- `0x1800110fc`
- `0x180011b44`
- `0x180031940`
- `0x18003843c`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003196a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003196a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031ad9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031ad9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180031a10`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180031a10`

## string_xrefs

- `0x1800319e2`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180031a22`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180031a63`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180031aa8`: `Deployment job Id %ws : Pause request processing complete. Job Status = %ws`

## pseudocode

```c
__int64 __fastcall CUpdateDeploymentJob::Pause(CUpdateDeploymentJob *this)
{
  char *v1; // rbx
  int v3; // edi
  unsigned int LastError; // edi
  const char *v5; // r9
  __int64 v6; // rcx
  int v7; // eax
  wchar_t v9[40]; // [rsp+40h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v1 = (char *)this + 880;
  if ( this != (CUpdateDeploymentJob *)-880LL )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 888));
  GetDeploymentJobStatusAsString(*((unsigned int *)this + 218));
  Trace::GuidToString::GuidToString(v9, (const struct _GUID *)this + 1);
  WUTrace(0, 0, 0x1000000, 4);
  v3 = *((_DWORD *)this + 218);
  if ( v3 == 2 )
  {
    if ( !ResetEvent(*((HANDLE *)this + 98)) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xFC3,
                    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
                    v5);
      goto LABEL_14;
    }
    v6 = *((_QWORD *)this + 105);
    if ( v6 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 72LL))(v6);
      if ( v7 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xFCA,
          (int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
          (const char *)(unsigned int)v7);
    }
    *((_DWORD *)this + 218) = 7;
    Trace::GuidToString::GuidToString(v9, (const struct _GUID *)this + 1);
    GetDeploymentJobStatusAsString(7);
    WUTrace(0, 0, 0x1000000, 4);
  }
  else if ( v3 && v3 != 7 )
  {
    LastError = -2145124298;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFBF,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)0x80240036LL,
      0);
    goto LABEL_14;
  }
  LastError = 0;
LABEL_14:
  if ( v1 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v1 + 8));
  return LastError;
}

```

## disassembly

```asm
0x180031940  mov     [rsp+arg_8], rbx
0x180031945  mov     [rsp+arg_10], rbp
0x18003194a  mov     [rsp+arg_18], rsi
0x18003194f  push    rdi
0x180031950  sub     rsp, 90h
0x180031957  lea     rbx, [rcx+370h]
0x18003195e  mov     rsi, rcx
0x180031961  test    rbx, rbx
0x180031964  jz      short loc_180031970
0x180031966  lea     rcx, [rbx+8]; lpCriticalSection
0x18003196a  call    cs:__imp_EnterCriticalSection
0x180031970  mov     ecx, [rsi+368h]
0x180031976  call    GetDeploymentJobStatusAsString
0x18003197b  lea     rcx, [rsp+98h+var_58]; this
0x180031980  mov     rdi, rax
0x180031983  lea     rdx, [rsi+10h]; struct _GUID *
0x180031987  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x18003198c  mov     [rsp+98h+var_60], rdi
0x180031991  xor     edx, edx
0x180031993  mov     [rsp+98h+var_68], rax
0x180031998  xor     ecx, ecx
0x18003199a  lea     rax, aDeploymentJobI_2; "Deployment job Id %ws : Pause request r"...
0x1800319a1  mov     r8d, 1000000h
0x1800319a7  mov     [rsp+98h+var_70], rax
0x1800319ac  lea     r9d, [rdx+4]
0x1800319b0  mov     qword ptr [rsp+98h+var_78], 0; int
0x1800319b9  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800319be  mov     edi, [rsi+368h]
0x1800319c4  cmp     edi, 2
0x1800319c7  jz      short loc_180031A00
0x1800319c9  test    edi, edi
0x1800319cb  jz      loc_180031ACE
0x1800319d1  cmp     edi, 7
0x1800319d4  jz      loc_180031ACE
0x1800319da  mov     rcx, [rsp+98h]; this
0x1800319e2  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x1800319e9  mov     edi, 80240036h
0x1800319ee  mov     edx, 0FBFh; void *
0x1800319f3  mov     r9d, edi; char *
0x1800319f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800319fb  jmp     loc_180031AD0
0x180031a00  cmp     edi, 7
0x180031a03  jz      loc_180031ACE
0x180031a09  mov     rcx, [rsi+310h]; hEvent
0x180031a10  call    cs:__imp_ResetEvent
0x180031a16  test    eax, eax
0x180031a18  jnz     short loc_180031A3A
0x180031a1a  mov     rcx, [rsp+98h]; this
0x180031a22  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180031a29  mov     edx, 0FC3h; void *
0x180031a2e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180031a33  mov     edi, eax
0x180031a35  jmp     loc_180031AD0
0x180031a3a  cmp     edi, 2
0x180031a3d  jnz     short loc_180031A77
0x180031a3f  mov     rcx, [rsi+348h]
0x180031a46  test    rcx, rcx
0x180031a49  jz      short loc_180031A77
0x180031a4b  mov     rax, [rcx]
0x180031a4e  mov     rax, [rax+48h]
0x180031a52  call    _guard_dispatch_icall
0x180031a57  test    eax, eax
0x180031a59  jns     short loc_180031A77
0x180031a5b  mov     rcx, [rsp+98h]; this
0x180031a63  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180031a6a  mov     r9d, eax; char *
0x180031a6d  mov     edx, 0FCAh; void *
0x180031a72  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180031a77  lea     rdx, [rsi+10h]; struct _GUID *
0x180031a7b  mov     dword ptr [rsi+368h], 7
0x180031a85  lea     rcx, [rsp+98h+var_58]; this
0x180031a8a  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180031a8f  mov     ecx, 7
0x180031a94  mov     rdx, rax
0x180031a97  call    GetDeploymentJobStatusAsString
0x180031a9c  mov     [rsp+98h+var_60], rax
0x180031aa1  xor     ecx, ecx
0x180031aa3  mov     [rsp+98h+var_68], rdx
0x180031aa8  lea     rax, aDeploymentJobI_12; "Deployment job Id %ws : Pause request p"...
0x180031aaf  xor     edx, edx
0x180031ab1  mov     [rsp+98h+var_70], rax
0x180031ab6  mov     r8d, 1000000h
0x180031abc  mov     qword ptr [rsp+98h+var_78], 0
0x180031ac5  lea     r9d, [rdx+4]
0x180031ac9  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180031ace  xor     edi, edi
0x180031ad0  test    rbx, rbx
0x180031ad3  jz      short loc_180031ADF
0x180031ad5  lea     rcx, [rbx+8]; lpCriticalSection
0x180031ad9  call    cs:__imp_LeaveCriticalSection
0x180031adf  lea     r11, [rsp+98h+var_8]
0x180031ae7  mov     eax, edi
0x180031ae9  mov     rbx, [r11+18h]
0x180031aed  mov     rbp, [r11+20h]
0x180031af1  mov     rsi, [r11+28h]
0x180031af5  mov     rsp, r11
0x180031af8  pop     rdi
0x180031af9  retn
```
