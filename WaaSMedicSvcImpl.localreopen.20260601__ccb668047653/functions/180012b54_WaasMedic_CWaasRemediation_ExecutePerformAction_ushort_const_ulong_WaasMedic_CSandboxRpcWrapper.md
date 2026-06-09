# WaasMedic::CWaasRemediation::ExecutePerformAction(ushort const *,ulong,WaasMedic::CSandboxRpcWrapper &)

- ea: `0x180012b54`
- end: `0x180012d69`
- name: `?ExecutePerformAction@CWaasRemediation@WaasMedic@@CAJPEBGKAEAVCSandboxRpcWrapper@2@@Z`
- size: `533`
- prototype: `__int64 __fastcall(WaasMedic *this, unsigned int, struct WaasMedic::CSandboxRpcWrapper *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180018d3c`

## callees

- `0x1800050a0`
- `0x180008d99`
- `0x180009cd0`
- `0x18000ea1c`
- `0x180012b54`
- `0x18002a4e4`
- `0x18002e81c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012c72`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180012c72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012cfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012c8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012cfe`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180012c21`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180012c21`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180012cf4`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180012cf4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012d41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012d41`

## string_xrefs

- `0x180012baa`: `Launching perform action thread for %s!`
- `0x180012c4a`: `Failed to create thread to execute action for %s! hr = 0x%08x`
- `0x180012cd9`: `Perform action thread for %s was signaled!`
- `0x180012cd0`: `Perform action thread for %s abandoned the mutex!`
- `0x180012ca7`: `Failed to wait for the perform action thread for %s! hr=0x%08X`
- `0x180012cc7`: `Perform action thread for %s failed to complete in the given timeout: hr=0x%08X`
- `0x180012d16`: `Failed to get thread exit code! hr = 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WaasMedic::CWaasRemediation::ExecutePerformAction(
        WaasMedic *this,
        int a2,
        struct WaasMedic::CSandboxRpcWrapper *a3)
{
  unsigned __int64 v6; // rdx
  __int64 v7; // rbx
  char *Thread; // rax
  char *v9; // rbx
  int LastError; // eax
  void *v11; // rdx
  DWORD v12; // eax
  int v13; // eax
  int v14; // eax
  DWORD v15; // edi
  DWORD ExitCode; // [rsp+30h] [rbp-40h] BYREF
  __int64 v18; // [rsp+38h] [rbp-38h]
  void *Parameter[2]; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int64 v20; // [rsp+50h] [rbp-20h]
  unsigned __int64 v21; // [rsp+58h] [rbp-18h]
  struct WaasMedic::CSandboxRpcWrapper *v22; // [rsp+60h] [rbp-10h]

  ExitCode = 0;
  v18 = 0;
  *(_OWORD *)Parameter = 0;
  v20 = 0;
  v21 = 7;
  LOWORD(Parameter[0]) = 0;
  LogLevelW(4u, L"Launching perform action thread for %s!", this);
  v22 = a3;
  v6 = -1;
  do
    ++v6;
  while ( *((_WORD *)this + v6) );
  if ( v6 > v21 )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(Parameter);
  }
  else
  {
    v20 = v6;
    v7 = 2 * v6;
    memmove_0(Parameter, this, 2 * v6);
    *(_WORD *)((char *)Parameter + v7) = 0;
  }
  Thread = (char *)CreateThread(0, 0, WaasMedic::CWaasRemediation::PerformActionThread, Parameter, 0, 0);
  v9 = Thread;
  if ( !Thread )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    ExitCode = LastError;
    LogLevelW(2u, L"Failed to create thread to execute action for %s! hr = 0x%08x", this, (unsigned int)LastError);
    WaasMedic::SafeFree(this, v11);
    goto LABEL_24;
  }
  v12 = WaitForSingleObject(Thread, 1000 * a2);
  if ( v12 )
  {
    switch ( v12 )
    {
      case 0x80u:
        LogLevelW(4u, L"Perform action thread for %s abandoned the mutex!", this);
        break;
      case 0x102u:
        ExitCode = -2147023436;
        LogLevelW(
          2u,
          L"Perform action thread for %s failed to complete in the given timeout: hr=0x%08X",
          this,
          2147943860LL);
        goto LABEL_24;
      case 0xFFFFFFFF:
        v13 = GetLastError();
        if ( v13 > 0 )
          v13 = (unsigned __int16)v13 | 0x80070000;
        ExitCode = v13;
        LogLevelW(2u, L"Failed to wait for the perform action thread for %s! hr=0x%08X", this, (unsigned int)v13);
        goto LABEL_24;
    }
  }
  else
  {
    LogLevelW(4u, L"Perform action thread for %s was signaled!", this);
  }
  if ( !GetExitCodeThread(v9, &ExitCode) )
  {
    v14 = GetLastError();
    if ( v14 > 0 )
      v14 = (unsigned __int16)v14 | 0x80070000;
    ExitCode = v14;
    LogLevelW(2u, L"Failed to get thread exit code! hr = 0x%08x", (unsigned int)v14);
  }
LABEL_24:
  v15 = ExitCode;
  std::wstring::~wstring(Parameter);
  if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v9);
  return v15;
}

```

## disassembly

```asm
0x180012b54  mov     [rsp-28h+arg_18], rbx
0x180012b59  push    rbp
0x180012b5a  push    rsi
0x180012b5b  push    rdi
0x180012b5c  push    r14
0x180012b5e  push    r15
0x180012b60  mov     rbp, rsp
0x180012b63  sub     rsp, 70h
0x180012b67  mov     rax, cs:__security_cookie
0x180012b6e  xor     rax, rsp
0x180012b71  mov     [rbp+var_8], rax
0x180012b75  mov     rbx, r8
0x180012b78  mov     r14d, edx
0x180012b7b  mov     rsi, rcx
0x180012b7e  xor     r15d, r15d
0x180012b81  mov     [rbp+ExitCode], r15d
0x180012b85  mov     [rbp+var_38], r15
0x180012b89  xorps   xmm0, xmm0
0x180012b8c  movups  xmmword ptr [rbp+Parameter], xmm0
0x180012b90  mov     [rbp+var_20], r15
0x180012b94  mov     [rbp+var_18], 7
0x180012b9c  mov     word ptr [rbp+Parameter], r15w
0x180012ba1  xor     eax, eax
0x180012ba3  mov     [rbp+var_10], rax
0x180012ba7  mov     r8, rcx
0x180012baa  lea     rdx, aLaunchingPerfo; "Launching perform action thread for %s!"
0x180012bb1  lea     ecx, [rax+4]; unsigned __int8
0x180012bb4  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180012bb9  mov     [rbp+var_10], rbx
0x180012bbd  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180012bc1  inc     rdx
0x180012bc4  cmp     [rsi+rdx*2], r15w
0x180012bc9  jnz     short loc_180012BC1
0x180012bcb  cmp     rdx, [rbp+var_18]
0x180012bcf  ja      short loc_180012BFC
0x180012bd1  lea     rdi, [rbp+Parameter]
0x180012bd5  cmp     [rbp+var_18], 7
0x180012bda  cmova   rdi, [rbp+Parameter]
0x180012bdf  mov     [rbp+var_20], rdx
0x180012be3  lea     rbx, [rdx+rdx]
0x180012be7  mov     r8, rbx; Size
0x180012bea  mov     rdx, rsi; Src
0x180012bed  mov     rcx, rdi; void *
0x180012bf0  call    memmove_0
0x180012bf5  mov     [rbx+rdi], r15w
0x180012bfa  jmp     short loc_180012C08
0x180012bfc  mov     r9, rsi
0x180012bff  lea     rcx, [rbp+Parameter]
0x180012c03  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180012c08  mov     [rsp+70h+lpThreadId], r15; lpThreadId
0x180012c0d  mov     [rsp+70h+dwCreationFlags], r15d; dwCreationFlags
0x180012c12  lea     r9, [rbp+Parameter]; lpParameter
0x180012c16  lea     r8, ?PerformActionThread@CWaasRemediation@WaasMedic@@CAKPEAX@Z; lpStartAddress
0x180012c1d  xor     edx, edx; dwStackSize
0x180012c1f  xor     ecx, ecx; lpThreadAttributes
0x180012c21  call    cs:__imp_CreateThread
0x180012c27  mov     rbx, rax
0x180012c2a  test    rax, rax
0x180012c2d  jnz     short loc_180012C68
0x180012c2f  call    cs:__imp_GetLastError
0x180012c35  test    eax, eax
0x180012c37  jle     short loc_180012C41
0x180012c39  movzx   eax, ax
0x180012c3c  or      eax, 80070000h
0x180012c41  mov     [rbp+ExitCode], eax
0x180012c44  mov     r9d, eax
0x180012c47  mov     r8, rsi
0x180012c4a  lea     rdx, aFailedToCreate_0; "Failed to create thread to execute acti"...
0x180012c51  mov     ecx, 2; unsigned __int8
0x180012c56  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180012c5b  mov     rcx, rsi; this
0x180012c5e  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x180012c63  jmp     loc_180012D27
0x180012c68  imul    edx, r14d, 3E8h; dwMilliseconds
0x180012c6f  mov     rcx, rbx; hHandle
0x180012c72  call    cs:__imp_WaitForSingleObject
0x180012c78  test    eax, eax
0x180012c7a  jz      short loc_180012CD9
0x180012c7c  cmp     eax, 80h
0x180012c81  jz      short loc_180012CD0
0x180012c83  cmp     eax, 102h
0x180012c88  jz      short loc_180012CBD
0x180012c8a  cmp     eax, 0FFFFFFFFh
0x180012c8d  jnz     short loc_180012CED
0x180012c8f  call    cs:__imp_GetLastError
0x180012c95  test    eax, eax
0x180012c97  jle     short loc_180012CA1
0x180012c99  movzx   eax, ax
0x180012c9c  or      eax, 80070000h
0x180012ca1  mov     [rbp+ExitCode], eax
0x180012ca4  mov     r9d, eax
0x180012ca7  lea     rdx, aFailedToWaitFo_2; "Failed to wait for the perform action t"...
0x180012cae  mov     r8, rsi
0x180012cb1  mov     ecx, 2; unsigned __int8
0x180012cb6  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180012cbb  jmp     short loc_180012D27
0x180012cbd  mov     r9d, 800705B4h
0x180012cc3  mov     [rbp+ExitCode], r9d
0x180012cc7  lea     rdx, aPerformActionT; "Perform action thread for %s failed to "...
0x180012cce  jmp     short loc_180012CAE
0x180012cd0  lea     rdx, aPerformActionT_1; "Perform action thread for %s abandoned "...
0x180012cd7  jmp     short loc_180012CE0
0x180012cd9  lea     rdx, aPerformActionT_0; "Perform action thread for %s was signal"...
0x180012ce0  mov     r8, rsi
0x180012ce3  mov     ecx, 4; unsigned __int8
0x180012ce8  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180012ced  lea     rdx, [rbp+ExitCode]; lpExitCode
0x180012cf1  mov     rcx, rbx; hThread
0x180012cf4  call    cs:__imp_GetExitCodeThread
0x180012cfa  test    eax, eax
0x180012cfc  jnz     short loc_180012D27
0x180012cfe  call    cs:__imp_GetLastError
0x180012d04  test    eax, eax
0x180012d06  jle     short loc_180012D10
0x180012d08  movzx   eax, ax
0x180012d0b  or      eax, 80070000h
0x180012d10  mov     [rbp+ExitCode], eax
0x180012d13  mov     r8d, eax
0x180012d16  lea     rdx, aFailedToGetThr; "Failed to get thread exit code! hr = 0x"...
0x180012d1d  mov     ecx, 2; unsigned __int8
0x180012d22  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180012d27  mov     edi, [rbp+ExitCode]
0x180012d2a  lea     rcx, [rbp+Parameter]; void *
0x180012d2e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180012d33  nop
0x180012d34  lea     rcx, [rbx-1]
0x180012d38  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180012d3c  ja      short loc_180012D47
0x180012d3e  mov     rcx, rbx; hObject
0x180012d41  call    cs:__imp_CloseHandle
0x180012d47  mov     eax, edi
0x180012d49  mov     rcx, [rbp+var_8]
0x180012d4d  xor     rcx, rsp; StackCookie
0x180012d50  call    __security_check_cookie
0x180012d55  mov     rbx, [rsp+70h+arg_18]
0x180012d5d  add     rsp, 70h
0x180012d61  pop     r15
0x180012d63  pop     r14
0x180012d65  pop     rdi
0x180012d66  pop     rsi
0x180012d67  pop     rbp
0x180012d68  retn
```
