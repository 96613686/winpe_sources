# ServiceMain(ulong,ushort * * const)

- ea: `0x18003c380`
- end: `0x18003c533`
- name: `?ServiceMain@@YAXKQEAPEAG@Z`
- size: `435`
- prototype: `void __fastcall(int, LPCWSTR *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x180037044`
- `0x1800370d8`
- `0x180037270`
- `0x18003c380`
- `0x18003c698`
- `0x18003c730`
- `0x18008a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x18003c3a2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x18003c3a2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003c502`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003c502`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003c410`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003c410`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c4e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c4e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c4d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003c4d3`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18003c3e3`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18003c3e3`

## pseudocode

```c
void __fastcall ServiceMain(int a1, LPCWSTR *a2)
{
  int v3; // ebx
  unsigned __int16 **v4; // rdx
  unsigned int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // eax
  signed int LastError; // eax

  ServiceStatus.dwControlsAccepted = 0;
  if ( a1 )
  {
    qword_1800C0918 = (void *)_o__wcsdup(*a2);
    if ( qword_1800C0918 )
    {
      ServiceStatus.dwServiceType = 16;
      *(_OWORD *)&ServiceStatus.dwCurrentState = 0;
      v3 = 0;
      *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
      hServiceStatus = RegisterServiceCtrlHandlerExW(*a2, ServiceHandler, 0);
      if ( hServiceStatus )
      {
        SvcFrameworkUpdateServiceStatus(2u, 0, 0);
        hEvent = CreateEventW(0, 0, 0, 0);
        if ( hEvent )
        {
          v3 = SvcInitialize(v5, v4);
          if ( v3 < 0 || (v3 = SvcRegisterRPCInterface(), v3 < 0) )
          {
            SvcUninitialize(v6);
          }
          else
          {
            ServiceStatus.dwControlsAccepted |= 1u;
            SvcFrameworkUpdateServiceStatus(4u, 0, 0);
            if ( !qword_1800C0970 || (v3 = qword_1800C0970(), v3 >= 0) )
            {
              v8 = (*(__int64 (__fastcall **)(HANDLE *, void *, HANDLE, __int64 (__fastcall *)(), _QWORD, int))(qword_1800C0980 + 192))(
                     &WaitHandle,
                     qword_1800C0918,
                     hEvent,
                     StopService,
                     0,
                     8);
              v3 = v8;
              if ( !v8 )
                return;
              if ( v8 > 0 )
                v3 = (unsigned __int16)v8 | 0x80070000;
            }
            UninitializeService(v7);
          }
          CloseHandle(hEvent);
          hEvent = 0;
        }
        else
        {
          LastError = GetLastError();
          v3 = LastError;
          if ( LastError > 0 )
            v3 = (unsigned __int16)LastError | 0x80070000;
        }
      }
      free(qword_1800C0918);
      qword_1800C0918 = 0;
    }
    else
    {
      v3 = -2147024882;
    }
    SvcFrameworkUpdateServiceStatus(1u, v3, 0);
  }
}

```

## disassembly

```asm
0x18003c380  mov     [rsp+arg_0], rbx
0x18003c385  push    rdi
0x18003c386  sub     rsp, 40h
0x18003c38a  mov     cs:ServiceStatus.dwControlsAccepted, 0
0x18003c394  mov     rdi, rdx
0x18003c397  test    ecx, ecx
0x18003c399  jz      loc_18003C528
0x18003c39f  mov     rcx, [rdx]
0x18003c3a2  call    cs:__imp__o__wcsdup
0x18003c3a8  mov     cs:qword_1800C0918, rax
0x18003c3af  test    rax, rax
0x18003c3b2  jz      loc_18003C515
0x18003c3b8  xorps   xmm0, xmm0
0x18003c3bb  mov     cs:ServiceStatus.dwServiceType, 10h
0x18003c3c5  movdqu  xmmword ptr cs:ServiceStatus.dwCurrentState, xmm0
0x18003c3cd  xor     ebx, ebx
0x18003c3cf  lea     rdx, ServiceHandler; lpHandlerProc
0x18003c3d6  mov     qword ptr cs:ServiceStatus.dwCheckPoint, rbx
0x18003c3dd  xor     r8d, r8d; lpContext
0x18003c3e0  mov     rcx, [rdi]; lpServiceName
0x18003c3e3  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18003c3e9  mov     cs:hServiceStatus, rax
0x18003c3f0  test    rax, rax
0x18003c3f3  jz      loc_18003C4FB
0x18003c3f9  xor     r8d, r8d; unsigned int
0x18003c3fc  lea     ecx, [rbx+2]; unsigned int
0x18003c3ff  xor     edx, edx; unsigned int
0x18003c401  call    ?SvcFrameworkUpdateServiceStatus@@YAJKKK@Z; SvcFrameworkUpdateServiceStatus(ulong,ulong,ulong)
0x18003c406  xor     r9d, r9d; lpName
0x18003c409  xor     r8d, r8d; bInitialState
0x18003c40c  xor     edx, edx; bManualReset
0x18003c40e  xor     ecx, ecx; lpEventAttributes
0x18003c410  call    cs:__imp_CreateEventW
0x18003c416  mov     cs:hEvent, rax
0x18003c41d  test    rax, rax
0x18003c420  jz      loc_18003C4E6
0x18003c426  call    ?SvcInitialize@@YAJKQEAPEAG@Z; SvcInitialize(ulong,ushort * * const)
0x18003c42b  mov     ebx, eax
0x18003c42d  test    eax, eax
0x18003c42f  js      loc_18003C4C7
0x18003c435  call    ?SvcRegisterRPCInterface@@YAJXZ; SvcRegisterRPCInterface(void)
0x18003c43a  mov     ebx, eax
0x18003c43c  test    eax, eax
0x18003c43e  js      loc_18003C4C7
0x18003c444  or      cs:ServiceStatus.dwControlsAccepted, 1
0x18003c44b  xor     edx, edx; unsigned int
0x18003c44d  xor     r8d, r8d; unsigned int
0x18003c450  lea     ecx, [rdx+4]; unsigned int
0x18003c453  call    ?SvcFrameworkUpdateServiceStatus@@YAJKKK@Z; SvcFrameworkUpdateServiceStatus(ulong,ulong,ulong)
0x18003c458  mov     rax, cs:qword_1800C0970
0x18003c45f  test    rax, rax
0x18003c462  jz      short loc_18003C46F
0x18003c464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c469  mov     ebx, eax
0x18003c46b  test    eax, eax
0x18003c46d  js      short loc_18003C4C0
0x18003c46f  mov     rax, cs:qword_1800C0980
0x18003c476  lea     r9, StopService
0x18003c47d  mov     r8, cs:hEvent
0x18003c484  lea     rcx, WaitHandle
0x18003c48b  mov     rdx, cs:qword_1800C0918
0x18003c492  mov     [rsp+48h+var_20], 8
0x18003c49a  mov     rax, [rax+0C0h]
0x18003c4a1  mov     [rsp+48h+var_28], 0
0x18003c4aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c4af  mov     ebx, eax
0x18003c4b1  test    eax, eax
0x18003c4b3  jz      short loc_18003C528
0x18003c4b5  jle     short loc_18003C4C0
0x18003c4b7  movzx   ebx, ax
0x18003c4ba  or      ebx, 80070000h
0x18003c4c0  call    ?UninitializeService@@YAJJ@Z; UninitializeService(long)
0x18003c4c5  jmp     short loc_18003C4CC
0x18003c4c7  call    ?SvcUninitialize@@YAJJ@Z; SvcUninitialize(long)
0x18003c4cc  mov     rcx, cs:hEvent; hObject
0x18003c4d3  call    cs:__imp_CloseHandle
0x18003c4d9  mov     cs:hEvent, 0
0x18003c4e4  jmp     short loc_18003C4FB
0x18003c4e6  call    cs:__imp_GetLastError
0x18003c4ec  mov     ebx, eax
0x18003c4ee  test    eax, eax
0x18003c4f0  jle     short loc_18003C4FB
0x18003c4f2  movzx   ebx, ax
0x18003c4f5  or      ebx, 80070000h
0x18003c4fb  mov     rcx, cs:qword_1800C0918; Block
0x18003c502  call    cs:__imp_free
0x18003c508  mov     cs:qword_1800C0918, 0
0x18003c513  jmp     short loc_18003C51A
0x18003c515  mov     ebx, 8007000Eh
0x18003c51a  xor     r8d, r8d; unsigned int
0x18003c51d  mov     edx, ebx; unsigned int
0x18003c51f  lea     ecx, [r8+1]; unsigned int
0x18003c523  call    ?SvcFrameworkUpdateServiceStatus@@YAJKKK@Z; SvcFrameworkUpdateServiceStatus(ulong,ulong,ulong)
0x18003c528  mov     rbx, [rsp+48h+arg_0]
0x18003c52d  add     rsp, 40h
0x18003c531  pop     rdi
0x18003c532  retn
```
