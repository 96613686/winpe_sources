# RegistrarHost::RegistrarThreadProc(void *)

- ea: `0x1800a3a10`
- end: `0x1800a3aca`
- name: `?RegistrarThreadProc@RegistrarHost@@CAKPEAX@Z`
- size: `186`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18003950c`
- `0x18008cc78`
- `0x18009d670`
- `0x1800a23fc`
- `0x1800a3a10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a3a4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800a3a4d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800a3a5b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800a3a5b`

## pseudocode

```c
__int64 __fastcall RegistrarHost::RegistrarThreadProc(_QWORD *Parameter, __int64 a2, __int64 a3)
{
  HANDLE CurrentThread; // rax
  int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // r8
  _BYTE v9[16]; // [rsp+30h] [rbp-28h] BYREF

  if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(Parameter, &CoreUIService_ServerThread_Started, a3, 1, v9);
  CurrentThread = GetCurrentThread();
  SetThreadPriority(CurrentThread, 15);
  v5 = CoreUIRunRegistrarServer(
         Parameter[7],
         Parameter[8],
         *((unsigned int *)Parameter + 2),
         (char *)Parameter + 12,
         (char *)Parameter + 28);
  if ( v5 < 0 )
    CFlat::Abandonment::FailWithHR(v5, 0, 0);
  if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(v6, &CoreUIService_ServerThread_Exiting, v7, 1, v9);
  return 0;
}

```

## disassembly

```asm
0x1800a3a10  push    rbx
0x1800a3a12  sub     rsp, 50h
0x1800a3a16  mov     rax, cs:__security_cookie
0x1800a3a1d  xor     rax, rsp
0x1800a3a20  mov     [rsp+58h+var_18], rax
0x1800a3a25  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits, 4
0x1800a3a2c  mov     rbx, rcx
0x1800a3a2f  jz      short loc_1800A3A4D
0x1800a3a31  lea     rax, [rsp+58h+var_28]
0x1800a3a36  mov     r9d, 1
0x1800a3a3c  lea     rdx, CoreUIService_ServerThread_Started
0x1800a3a43  mov     [rsp+58h+var_38], rax
0x1800a3a48  call    McGenEventWrite_EventWriteTransfer
0x1800a3a4d  call    cs:__imp_GetCurrentThread
0x1800a3a53  mov     rcx, rax; hThread
0x1800a3a56  mov     edx, 0Fh; nPriority
0x1800a3a5b  call    cs:__imp_SetThreadPriority
0x1800a3a61  mov     r8d, [rbx+8]
0x1800a3a65  lea     rax, [rbx+1Ch]
0x1800a3a69  mov     rdx, [rbx+40h]
0x1800a3a6d  lea     r9, [rbx+0Ch]
0x1800a3a71  mov     rcx, [rbx+38h]
0x1800a3a75  mov     [rsp+58h+var_38], rax
0x1800a3a7a  call    ?CoreUIRunRegistrarServer@@YAJPEAX0W4ServiceRunMode@Registrar@CoreUI@Microsoft@@AEBU_GUID@@2@Z; CoreUIRunRegistrarServer(void *,void *,Microsoft::CoreUI::Registrar::ServiceRunMode,_GUID const &,_GUID const &)
0x1800a3a7f  test    eax, eax
0x1800a3a81  jns     short loc_1800A3A90
0x1800a3a83  xor     r8d, r8d; int
0x1800a3a86  xor     edx, edx; void *
0x1800a3a88  mov     ecx, eax; int
0x1800a3a8a  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x1800a3a90  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits, 4
0x1800a3a97  jz      short loc_1800A3AB5
0x1800a3a99  lea     rax, [rsp+58h+var_28]
0x1800a3a9e  mov     r9d, 1
0x1800a3aa4  lea     rdx, CoreUIService_ServerThread_Exiting
0x1800a3aab  mov     [rsp+58h+var_38], rax
0x1800a3ab0  call    McGenEventWrite_EventWriteTransfer
0x1800a3ab5  xor     eax, eax
0x1800a3ab7  mov     rcx, [rsp+58h+var_18]
0x1800a3abc  xor     rcx, rsp; StackCookie
0x1800a3abf  call    __security_check_cookie
0x1800a3ac4  add     rsp, 50h
0x1800a3ac8  pop     rbx
0x1800a3ac9  retn
```
