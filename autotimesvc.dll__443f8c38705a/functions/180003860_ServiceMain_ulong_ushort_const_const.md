# ServiceMain(ulong,ushort const * * const)

- ea: `0x180003860`
- end: `0x1800039e7`
- name: `?ServiceMain@@YAXKQEAPEBG@Z`
- size: `391`
- prototype: `void __fastcall(unsigned int, const unsigned __int16 **const)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x180003860`
- `0x180003a64`
- `0x180003b00`
- `0x18000b264`
- `0x18000b3b8`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800038fa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800038fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800038bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800038bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800039ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003999`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003999`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800038ad`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800038ad`

## pseudocode

```c
void __fastcall ServiceMain(unsigned int a1, const unsigned __int16 **const a2)
{
  signed int v4; // eax
  int v5; // ebx
  int v6; // eax
  signed int LastError; // eax

  if ( a1 )
  {
    SvcLogEventFromServiceEngine(0, 0);
    xmmword_18001C30C = 0;
    qword_18001C31C = 0;
    dword_18001C308 = 32;
    qword_18001C328 = (__int64)RegisterServiceCtrlHandlerExW(*a2, ServiceHandler, 0);
    if ( qword_18001C328 )
    {
      SvcFrameworkUpdateServiceStatus(2u, 0, 0x32u);
      hObject = CreateEventW(0, 0, 0, 0);
      if ( hObject )
      {
        v5 = SvcInitialize(a1, a2);
        if ( v5 >= 0 )
        {
          DWORD1(xmmword_18001C30C) |= 1u;
          SvcFrameworkUpdateServiceStatus(4u, 0, 0);
          SvcLogEventFromServiceEngine(1, 0);
          v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, HANDLE, __int64 (__fastcall *)(), _QWORD, int))(qword_18001C300 + 208))(
                 &qword_18001C2F8,
                 *a2,
                 hObject,
                 StopService,
                 0,
                 8);
          v5 = v6;
          if ( !v6 )
            return;
          if ( v6 > 0 )
            v5 = (unsigned __int16)v6 | 0x80070000;
          UninitializeService(v5);
        }
        CloseHandle(hObject);
        hObject = 0;
      }
      else
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
      }
      SvcLogEventFromServiceEngine(3, (unsigned int)v5);
      SvcFrameworkUpdateServiceStatus(1u, v5, 0);
    }
    else
    {
      v4 = GetLastError();
      if ( v4 > 0 )
        v4 = (unsigned __int16)v4 | 0x80070000;
      SvcLogEventFromServiceEngine(3, (unsigned int)v4);
    }
  }
}

```

## disassembly

```asm
0x180003860  test    ecx, ecx
0x180003862  jz      locret_1800039E6
0x180003868  mov     [rsp+arg_0], rbx
0x18000386d  push    rdi
0x18000386e  sub     rsp, 40h
0x180003872  mov     rdi, rdx
0x180003875  mov     ebx, ecx
0x180003877  xor     edx, edx
0x180003879  xor     ecx, ecx
0x18000387b  call    ?SvcLogEventFromServiceEngine@@YAXW4SvcLogPoint@@J@Z; SvcLogEventFromServiceEngine(SvcLogPoint,long)
0x180003880  xorps   xmm0, xmm0
0x180003883  movdqu  cs:xmmword_18001C30C, xmm0
0x18000388b  mov     cs:qword_18001C31C, 0
0x180003896  mov     cs:dword_18001C308, 20h ; ' '
0x1800038a0  xor     r8d, r8d; lpContext
0x1800038a3  lea     rdx, ServiceHandler; lpHandlerProc
0x1800038aa  mov     rcx, [rdi]; lpServiceName
0x1800038ad  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800038b3  mov     cs:qword_18001C328, rax
0x1800038ba  test    rax, rax
0x1800038bd  jnz     short loc_1800038E2
0x1800038bf  call    cs:__imp_GetLastError
0x1800038c5  test    eax, eax
0x1800038c7  jle     short loc_1800038D1
0x1800038c9  movzx   eax, ax
0x1800038cc  or      eax, 80070000h
0x1800038d1  mov     edx, eax
0x1800038d3  mov     ecx, 3
0x1800038d8  call    ?SvcLogEventFromServiceEngine@@YAXW4SvcLogPoint@@J@Z; SvcLogEventFromServiceEngine(SvcLogPoint,long)
0x1800038dd  jmp     loc_1800039DC
0x1800038e2  xor     edx, edx; unsigned int
0x1800038e4  lea     ecx, [rdx+2]; unsigned int
0x1800038e7  lea     r8d, [rdx+32h]; unsigned int
0x1800038eb  call    ?SvcFrameworkUpdateServiceStatus@@YAXKKK@Z; SvcFrameworkUpdateServiceStatus(ulong,ulong,ulong)
0x1800038f0  xor     r9d, r9d; lpName
0x1800038f3  xor     r8d, r8d; bInitialState
0x1800038f6  xor     edx, edx; bManualReset
0x1800038f8  xor     ecx, ecx; lpEventAttributes
0x1800038fa  call    cs:__imp_CreateEventW
0x180003900  mov     cs:hObject, rax
0x180003907  test    rax, rax
0x18000390a  jz      loc_1800039AC
0x180003910  mov     rdx, rdi; unsigned __int16 **
0x180003913  mov     ecx, ebx; unsigned int
0x180003915  call    ?SvcInitialize@@YAJKQEAPEBG@Z; SvcInitialize(ulong,ushort const * * const)
0x18000391a  mov     ebx, eax
0x18000391c  test    eax, eax
0x18000391e  js      short loc_180003992
0x180003920  or      dword ptr cs:xmmword_18001C30C+4, 1
0x180003927  xor     r8d, r8d; unsigned int
0x18000392a  xor     edx, edx; unsigned int
0x18000392c  lea     ecx, [rdx+4]; unsigned int
0x18000392f  call    ?SvcFrameworkUpdateServiceStatus@@YAXKKK@Z; SvcFrameworkUpdateServiceStatus(ulong,ulong,ulong)
0x180003934  xor     edx, edx
0x180003936  lea     ecx, [rdx+1]
0x180003939  call    ?SvcLogEventFromServiceEngine@@YAXW4SvcLogPoint@@J@Z; SvcLogEventFromServiceEngine(SvcLogPoint,long)
0x18000393e  mov     rax, cs:qword_18001C300
0x180003945  mov     [rsp+48h+var_20], 8
0x18000394d  mov     [rsp+48h+var_28], 0
0x180003956  lea     r9, StopService
0x18000395d  mov     r8, cs:hObject
0x180003964  mov     rdx, [rdi]
0x180003967  lea     rcx, qword_18001C2F8
0x18000396e  mov     rax, [rax+0D0h]
0x180003975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000397a  mov     ebx, eax
0x18000397c  test    eax, eax
0x18000397e  jz      short loc_1800039DC
0x180003980  jle     short loc_18000398B
0x180003982  movzx   ebx, ax
0x180003985  or      ebx, 80070000h
0x18000398b  mov     ecx, ebx; int
0x18000398d  call    ?UninitializeService@@YAXJ@Z; UninitializeService(long)
0x180003992  mov     rcx, cs:hObject; hObject
0x180003999  call    cs:__imp_CloseHandle
0x18000399f  mov     cs:hObject, 0
0x1800039aa  jmp     short loc_1800039C1
0x1800039ac  call    cs:__imp_GetLastError
0x1800039b2  mov     ebx, eax
0x1800039b4  test    eax, eax
0x1800039b6  jle     short loc_1800039C1
0x1800039b8  movzx   ebx, ax
0x1800039bb  or      ebx, 80070000h
0x1800039c1  mov     edx, ebx
0x1800039c3  mov     ecx, 3
0x1800039c8  call    ?SvcLogEventFromServiceEngine@@YAXW4SvcLogPoint@@J@Z; SvcLogEventFromServiceEngine(SvcLogPoint,long)
0x1800039cd  xor     r8d, r8d; unsigned int
0x1800039d0  mov     edx, ebx; unsigned int
0x1800039d2  lea     ecx, [r8+1]; unsigned int
0x1800039d6  call    ?SvcFrameworkUpdateServiceStatus@@YAXKKK@Z; SvcFrameworkUpdateServiceStatus(ulong,ulong,ulong)
0x1800039db  nop
0x1800039dc  mov     rbx, [rsp+48h+arg_0]
0x1800039e1  add     rsp, 40h
0x1800039e5  pop     rdi
0x1800039e6  retn
```
