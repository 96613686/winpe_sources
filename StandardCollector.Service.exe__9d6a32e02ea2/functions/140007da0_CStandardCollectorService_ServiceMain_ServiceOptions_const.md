# CStandardCollectorService::ServiceMain(ServiceOptions const &)

- ea: `0x140007da0`
- end: `0x140007f38`
- name: `?ServiceMain@CStandardCollectorService@@AEAAXAEBUServiceOptions@@@Z`
- size: `408`
- prototype: `void __fastcall(CStandardCollectorService *__hidden this, const struct ServiceOptions *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x140007c28`
- `0x140007d50`

## callees

- `0x140007da0`
- `0x140007f38`
- `0x140008364`

## import_xrefs

- `KERNEL32!OpenEventW` at `0x140007e75`
- `KERNEL32!OpenEventW` at `0x140007e75`
- `KERNEL32!SetEvent` at `0x140007ee9`
- `KERNEL32!SetEvent` at `0x140007ee9`
- `KERNEL32!WaitForSingleObject` at `0x140007ebd`
- `KERNEL32!WaitForSingleObject` at `0x140007ed3`
- `KERNEL32!WaitForSingleObject` at `0x140007f02`
- `KERNEL32!WaitForSingleObject` at `0x140007ebd`
- `KERNEL32!WaitForSingleObject` at `0x140007ed3`
- `KERNEL32!WaitForSingleObject` at `0x140007f02`
- `KERNEL32!GetLastError` at `0x140007e83`
- `KERNEL32!GetLastError` at `0x140007ede`
- `KERNEL32!GetLastError` at `0x140007e83`
- `KERNEL32!GetLastError` at `0x140007ede`
- `KERNEL32!CloseHandle` at `0x140007eac`
- `KERNEL32!CloseHandle` at `0x140007eac`
- `ole32!CoInitializeEx` at `0x140007e20`
- `ole32!CoInitializeEx` at `0x140007e20`
- `ole32!CoUninitialize` at `0x140007f21`
- `ole32!CoUninitialize` at `0x140007f21`
- `ADVAPI32!RegisterServiceCtrlHandlerExW` at `0x140007df0`
- `ADVAPI32!RegisterServiceCtrlHandlerExW` at `0x140007df0`
- `ADVAPI32!SetServiceStatus` at `0x140007e0c`
- `ADVAPI32!SetServiceStatus` at `0x140007e0c`
- `api-ms-win-crt-runtime-l1-1-0!set_terminate` at `0x140007e3b`
- `api-ms-win-crt-runtime-l1-1-0!set_terminate` at `0x140007f0b`
- `api-ms-win-crt-runtime-l1-1-0!set_terminate` at `0x140007e3b`
- `api-ms-win-crt-runtime-l1-1-0!set_terminate` at `0x140007f0b`

## string_xrefs

- `0x140007de9`: `VsStandardCollectorService170`

## pseudocode

```c
void __fastcall CStandardCollectorService::ServiceMain(
        CStandardCollectorService *this,
        const struct ServiceOptions *a2)
{
  SERVICE_STATUS_HANDLE v4; // rax
  char v5; // bl
  __int64 v6; // r15
  const WCHAR *v7; // r8
  signed int v8; // ebp
  __int64 v9; // rsi
  signed int LastError; // eax
  void *v11; // rcx
  void *v12; // rcx

  if ( *(_DWORD *)a2 != 5
    || (*((_DWORD *)this + 2) = 48,
        *(_QWORD *)((char *)this + 12) = 1,
        *(_QWORD *)((char *)this + 20) = 0,
        *(_QWORD *)((char *)this + 28) = 0,
        v4 = RegisterServiceCtrlHandlerExW(
               L"VsStandardCollectorService170",
               CStandardCollectorService::ServiceControlHandlerStatic,
               this),
        (*(_QWORD *)this = v4) != 0)
    && (*((_DWORD *)this + 3) = 2, SetServiceStatus(v4, (LPSERVICE_STATUS)((char *)this + 8))) )
  {
    v5 = 0;
    if ( CoInitializeEx(0, 0) >= 0 )
    {
      v5 = 1;
      v6 = set_terminate(anonymous_namespace_::TerminateExceptionHandler);
      if ( CStandardCollectorService::OnStart(this, a2) >= 0 )
      {
        _mm_lfence();
        if ( *((_QWORD *)a2 + 3) )
        {
          v7 = (const WCHAR *)((char *)a2 + 8);
          if ( *((_QWORD *)a2 + 4) > 7u )
            v7 = *(const WCHAR **)v7;
          v8 = 0;
          v9 = (__int64)OpenEventW(2u, 0, v7);
          if ( !v9 )
          {
            LastError = GetLastError();
            v8 = (unsigned __int16)LastError | 0x80070000;
            if ( LastError <= 0 )
              v8 = LastError;
            v9 = -1;
          }
          if ( v8 >= 0 )
            SetEvent((HANDLE)v9);
          if ( v9 != -1 )
            CloseHandle((HANDLE)v9);
        }
        v11 = (void *)*((_QWORD *)this + 11);
        if ( v11 && WaitForSingleObject(v11, 0) )
        {
          v12 = (void *)*((_QWORD *)this + 11);
          if ( v12 && WaitForSingleObject(v12, 0xFFFFFFFF) == -1 )
            GetLastError();
        }
        else if ( *((int *)this + 14) >= 0 )
        {
          WaitForSingleObject(*((HANDLE *)this + 6), 0xFFFFFFFF);
        }
        set_terminate(v6);
        CStandardCollectorService::OnStop(this, a2);
      }
    }
    if ( v5 )
      CoUninitialize();
  }
}

```

## disassembly

```asm
0x140007da0  mov     [rsp+arg_10], rbx
0x140007da5  push    rbp
0x140007da6  push    rsi
0x140007da7  push    rdi
0x140007da8  push    r14
0x140007daa  push    r15
0x140007dac  sub     rsp, 30h
0x140007db0  mov     r14, rdx
0x140007db3  mov     rdi, rcx
0x140007db6  mov     esi, 2
0x140007dbb  cmp     dword ptr [rdx], 5
0x140007dbe  jnz     short loc_140007E1A
0x140007dc0  mov     dword ptr [rcx+8], 30h ; '0'
0x140007dc7  mov     qword ptr [rcx+0Ch], 1
0x140007dcf  mov     qword ptr [rcx+14h], 0
0x140007dd7  mov     qword ptr [rcx+1Ch], 0
0x140007ddf  mov     r8, rcx; lpContext
0x140007de2  lea     rdx, ?ServiceControlHandlerStatic@CStandardCollectorService@@CAKKKPEAX0@Z; lpHandlerProc
0x140007de9  lea     rcx, ?WZ_SERVICENAME@@3QBGB; "VsStandardCollectorService170"
0x140007df0  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x140007df6  mov     [rdi], rax
0x140007df9  test    rax, rax
0x140007dfc  jz      loc_140007F27
0x140007e02  mov     [rdi+0Ch], esi
0x140007e05  lea     rdx, [rdi+8]; lpServiceStatus
0x140007e09  mov     rcx, rax; hServiceStatus
0x140007e0c  call    cs:__imp_SetServiceStatus
0x140007e12  test    eax, eax
0x140007e14  jz      loc_140007F27
0x140007e1a  xor     bl, bl
0x140007e1c  xor     edx, edx; dwCoInit
0x140007e1e  xor     ecx, ecx; pvReserved
0x140007e20  call    cs:__imp_CoInitializeEx
0x140007e26  test    eax, eax
0x140007e28  js      loc_140007F1D
0x140007e2e  mov     bl, 1
0x140007e30  mov     [rsp+58h+var_38], bl
0x140007e34  lea     rcx, _anonymous_namespace___TerminateExceptionHandler
0x140007e3b  call    cs:__imp_set_terminate
0x140007e41  mov     r15, rax
0x140007e44  mov     rdx, r14; struct ServiceOptions *
0x140007e47  mov     rcx, rdi; this
0x140007e4a  call    ?OnStart@CStandardCollectorService@@AEAAJAEBUServiceOptions@@@Z; CStandardCollectorService::OnStart(ServiceOptions const &)
0x140007e4f  test    eax, eax
0x140007e51  js      loc_140007F1D
0x140007e57  lfence
0x140007e5a  cmp     qword ptr [r14+18h], 0
0x140007e5f  jz      short loc_140007EB2
0x140007e61  lea     r8, [r14+8]
0x140007e65  cmp     qword ptr [r8+18h], 7
0x140007e6a  jbe     short loc_140007E6F
0x140007e6c  mov     r8, [r8]; lpName
0x140007e6f  xor     ebp, ebp
0x140007e71  xor     edx, edx; bInheritHandle
0x140007e73  mov     ecx, esi; dwDesiredAccess
0x140007e75  call    cs:__imp_OpenEventW
0x140007e7b  mov     rsi, rax
0x140007e7e  test    rax, rax
0x140007e81  jnz     short loc_140007E9B
0x140007e83  call    cs:__imp_GetLastError
0x140007e89  movzx   ebp, ax
0x140007e8c  or      ebp, 80070000h
0x140007e92  test    eax, eax
0x140007e94  cmovle  ebp, eax
0x140007e97  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140007e9b  shr     ebp, 1Fh
0x140007e9e  test    bpl, bpl
0x140007ea1  jz      short loc_140007EE6
0x140007ea3  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x140007ea7  jz      short loc_140007EB2
0x140007ea9  mov     rcx, rsi; hObject
0x140007eac  call    cs:__imp_CloseHandle
0x140007eb2  mov     rcx, [rdi+58h]; hHandle
0x140007eb6  test    rcx, rcx
0x140007eb9  jz      short loc_140007EF1
0x140007ebb  xor     edx, edx; dwMilliseconds
0x140007ebd  call    cs:__imp_WaitForSingleObject
0x140007ec3  test    eax, eax
0x140007ec5  jz      short loc_140007EF1
0x140007ec7  mov     rcx, [rdi+58h]; hHandle
0x140007ecb  test    rcx, rcx
0x140007ece  jz      short loc_140007F08
0x140007ed0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140007ed3  call    cs:__imp_WaitForSingleObject
0x140007ed9  cmp     eax, 0FFFFFFFFh
0x140007edc  jnz     short loc_140007F08
0x140007ede  call    cs:__imp_GetLastError
0x140007ee4  jmp     short loc_140007F08
0x140007ee6  mov     rcx, rsi; hEvent
0x140007ee9  call    cs:__imp_SetEvent
0x140007eef  jmp     short loc_140007EA3
0x140007ef1  mov     eax, [rdi+38h]
0x140007ef4  shr     eax, 1Fh
0x140007ef7  test    al, al
0x140007ef9  jnz     short loc_140007F08
0x140007efb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140007efe  mov     rcx, [rdi+30h]; hHandle
0x140007f02  call    cs:__imp_WaitForSingleObject
0x140007f08  mov     rcx, r15
0x140007f0b  call    cs:__imp_set_terminate
0x140007f11  mov     rdx, r14; struct ServiceOptions *
0x140007f14  mov     rcx, rdi; this
0x140007f17  call    ?OnStop@CStandardCollectorService@@AEAAJAEBUServiceOptions@@@Z; CStandardCollectorService::OnStop(ServiceOptions const &)
0x140007f1c  nop
0x140007f1d  test    bl, bl
0x140007f1f  jz      short loc_140007F27
0x140007f21  call    cs:__imp_CoUninitialize
0x140007f27  mov     rbx, [rsp+58h+arg_10]
0x140007f2c  add     rsp, 30h
0x140007f30  pop     r15
0x140007f32  pop     r14
0x140007f34  pop     rdi
0x140007f35  pop     rsi
0x140007f36  pop     rbp
0x140007f37  retn
```
