# CUpdateDeploymentJob::Resume(void)

- ea: `0x180031b00`
- end: `0x180031cbe`
- name: `?Resume@CUpdateDeploymentJob@@UEAAJXZ`
- size: `446`
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
- `0x180031b00`
- `0x18003843c`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180031c15`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180031c15`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031b2a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180031b2a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031c9d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031c9d`

## string_xrefs

- `0x180031bb8`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180031bfa`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180031c27`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180031c6e`: `Deployment job Id %ws : Resume request processing complete. Job Status = %ws`

## pseudocode

```c
__int64 __fastcall CUpdateDeploymentJob::Resume(CUpdateDeploymentJob *this)
{
  char *v1; // rbx
  int v3; // eax
  __int64 v4; // rdx
  unsigned int LastError; // edi
  __int64 v6; // rcx
  int v7; // eax
  const char *v8; // r9
  wchar_t v10[40]; // [rsp+40h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v1 = (char *)this + 880;
  if ( this != (CUpdateDeploymentJob *)-880LL )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 888));
  GetDeploymentJobStatusAsString(*((unsigned int *)this + 218));
  Trace::GuidToString::GuidToString(v10, (const struct _GUID *)this + 1);
  WUTrace(0, 0, 0x1000000, 4);
  v3 = *((_DWORD *)this + 218);
  if ( v3 == 7 || !v3 )
  {
    if ( !*((_QWORD *)this + 98) )
    {
      v4 = 4076;
      goto LABEL_9;
    }
    if ( v3 == 7 )
    {
      v6 = *((_QWORD *)this + 105);
      if ( v6 )
      {
        v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 80LL))(v6);
        if ( v7 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xFF3,
            (int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
            (const char *)(unsigned int)v7);
      }
    }
    if ( !SetEvent(*((HANDLE *)this + 98)) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xFF7,
                    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
                    v8);
      goto LABEL_18;
    }
    *((_DWORD *)this + 218) = 2;
    Trace::GuidToString::GuidToString(v10, (const struct _GUID *)this + 1);
    GetDeploymentJobStatusAsString(2);
    WUTrace(0, 0, 0x1000000, 4);
  }
  else if ( v3 != 2 )
  {
    v4 = 4074;
LABEL_9:
    LastError = -2145124298;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)0x80240036LL,
      0);
    goto LABEL_18;
  }
  LastError = 0;
LABEL_18:
  if ( v1 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v1 + 8));
  return LastError;
}

```

## disassembly

```asm
0x180031b00  mov     [rsp+arg_8], rbx
0x180031b05  mov     [rsp+arg_10], rbp
0x180031b0a  mov     [rsp+arg_18], rsi
0x180031b0f  push    rdi
0x180031b10  sub     rsp, 90h
0x180031b17  lea     rbx, [rcx+370h]
0x180031b1e  mov     rsi, rcx
0x180031b21  test    rbx, rbx
0x180031b24  jz      short loc_180031B30
0x180031b26  lea     rcx, [rbx+8]; lpCriticalSection
0x180031b2a  call    cs:__imp_EnterCriticalSection
0x180031b30  mov     ecx, [rsi+368h]
0x180031b36  call    GetDeploymentJobStatusAsString
0x180031b3b  lea     rcx, [rsp+98h+var_58]; this
0x180031b40  mov     rdi, rax
0x180031b43  lea     rdx, [rsi+10h]; struct _GUID *
0x180031b47  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180031b4c  mov     [rsp+98h+var_60], rdi
0x180031b51  xor     edx, edx
0x180031b53  mov     [rsp+98h+var_68], rax
0x180031b58  mov     edi, 4
0x180031b5d  lea     rax, aDeploymentJobI_53; "Deployment job Id %ws : Resume request "...
0x180031b64  mov     r9d, edi
0x180031b67  mov     [rsp+98h+var_70], rax
0x180031b6c  xor     ecx, ecx
0x180031b6e  mov     r8d, 1000000h
0x180031b74  mov     qword ptr [rsp+98h+var_78], 0; int
0x180031b7d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180031b82  mov     eax, [rsi+368h]
0x180031b88  cmp     eax, 7
0x180031b8b  jz      short loc_180031BA1
0x180031b8d  test    eax, eax
0x180031b8f  jz      short loc_180031BA1
0x180031b91  cmp     eax, 2
0x180031b94  jz      loc_180031C92
0x180031b9a  mov     edx, 0FEAh
0x180031b9f  jmp     short loc_180031BB0
0x180031ba1  cmp     qword ptr [rsi+310h], 0
0x180031ba9  jnz     short loc_180031BD1
0x180031bab  mov     edx, 0FECh; void *
0x180031bb0  mov     rcx, [rsp+98h]; this
0x180031bb8  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180031bbf  mov     edi, 80240036h
0x180031bc4  mov     r9d, edi; char *
0x180031bc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031bcc  jmp     loc_180031C94
0x180031bd1  cmp     eax, 7
0x180031bd4  jnz     short loc_180031C0E
0x180031bd6  mov     rcx, [rsi+348h]
0x180031bdd  test    rcx, rcx
0x180031be0  jz      short loc_180031C0E
0x180031be2  mov     rax, [rcx]
0x180031be5  mov     rax, [rax+50h]
0x180031be9  call    _guard_dispatch_icall
0x180031bee  test    eax, eax
0x180031bf0  jns     short loc_180031C0E
0x180031bf2  mov     rcx, [rsp+98h]; this
0x180031bfa  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180031c01  mov     r9d, eax; char *
0x180031c04  mov     edx, 0FF3h; void *
0x180031c09  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180031c0e  mov     rcx, [rsi+310h]; hEvent
0x180031c15  call    cs:__imp_SetEvent
0x180031c1b  test    eax, eax
0x180031c1d  jnz     short loc_180031C3C
0x180031c1f  mov     rcx, [rsp+98h]; this
0x180031c27  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180031c2e  mov     edx, 0FF7h; void *
0x180031c33  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180031c38  mov     edi, eax
0x180031c3a  jmp     short loc_180031C94
0x180031c3c  lea     rdx, [rsi+10h]; struct _GUID *
0x180031c40  mov     dword ptr [rsi+368h], 2
0x180031c4a  lea     rcx, [rsp+98h+var_58]; this
0x180031c4f  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x180031c54  mov     ecx, 2
0x180031c59  mov     rdx, rax
0x180031c5c  call    GetDeploymentJobStatusAsString
0x180031c61  mov     [rsp+98h+var_60], rax
0x180031c66  mov     r9d, edi
0x180031c69  mov     [rsp+98h+var_68], rdx
0x180031c6e  lea     rax, aDeploymentJobI_19; "Deployment job Id %ws : Resume request "...
0x180031c75  mov     [rsp+98h+var_70], rax
0x180031c7a  xor     edx, edx
0x180031c7c  xor     ecx, ecx
0x180031c7e  mov     qword ptr [rsp+98h+var_78], 0
0x180031c87  mov     r8d, 1000000h
0x180031c8d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180031c92  xor     edi, edi
0x180031c94  test    rbx, rbx
0x180031c97  jz      short loc_180031CA3
0x180031c99  lea     rcx, [rbx+8]; lpCriticalSection
0x180031c9d  call    cs:__imp_LeaveCriticalSection
0x180031ca3  lea     r11, [rsp+98h+var_8]
0x180031cab  mov     eax, edi
0x180031cad  mov     rbx, [r11+18h]
0x180031cb1  mov     rbp, [r11+20h]
0x180031cb5  mov     rsi, [r11+28h]
0x180031cb9  mov     rsp, r11
0x180031cbc  pop     rdi
0x180031cbd  retn
```
