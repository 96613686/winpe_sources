# Windows::Globalization::Spelling::CHostModule::StartTimeoutMonitor(void)

- ea: `0x140005ba4`
- end: `0x140005c4b`
- name: `?StartTimeoutMonitor@CHostModule@Spelling@Globalization@Windows@@QEAAJXZ`
- size: `167`
- prototype: `__int64 __fastcall(Windows::Globalization::Spelling::CHostModule *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140004458`
- `0x14000584c`

## callees

- `0x140005ba4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140005c11`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140005c11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005bcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005c1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005bcc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005c1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005c3d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005c3d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140005bba`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140005bba`

## pseudocode

```c
__int64 __fastcall Windows::Globalization::Spelling::CHostModule::StartTimeoutMonitor(
        Windows::Globalization::Spelling::CHostModule *this)
{
  signed int v1; // ebx
  signed int LastError; // eax
  HANDLE Thread; // rax
  signed int v4; // eax
  void *v5; // rcx
  Windows::Globalization::Spelling::CHostModule *ThreadId; // [rsp+40h] [rbp+8h] BYREF

  ThreadId = this;
  v1 = 0;
  qword_14001C058 = (__int64)CreateEventW(0, 0, 0, 0);
  if ( !qword_14001C058 )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
  }
  LODWORD(ThreadId) = 0;
  if ( v1 >= 0 )
  {
    Thread = CreateThread(
               0,
               0,
               Windows::Globalization::Spelling::CHostModule::TimeoutMonitorProc,
               &Windows::Globalization::Spelling::_AtlModule,
               0,
               (LPDWORD)&ThreadId);
    if ( Thread )
    {
      v5 = Thread;
    }
    else
    {
      v4 = GetLastError();
      v1 = v4;
      if ( v4 > 0 )
        v1 = (unsigned __int16)v4 | 0x80070000;
      v5 = (void *)qword_14001C058;
    }
    CloseHandle(v5);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140005ba4  mov     [rsp+ThreadId], rcx
0x140005ba9  push    rbx
0x140005baa  sub     rsp, 30h
0x140005bae  xor     r9d, r9d; lpName
0x140005bb1  xor     r8d, r8d; bInitialState
0x140005bb4  xor     edx, edx; bManualReset
0x140005bb6  xor     ecx, ecx; lpEventAttributes
0x140005bb8  xor     ebx, ebx
0x140005bba  call    cs:__imp_CreateEventW
0x140005bc0  mov     cs:qword_14001C058, rax
0x140005bc7  test    rax, rax
0x140005bca  jnz     short loc_140005BE1
0x140005bcc  call    cs:__imp_GetLastError
0x140005bd2  mov     ebx, eax
0x140005bd4  test    eax, eax
0x140005bd6  jle     short loc_140005BE1
0x140005bd8  movzx   ebx, ax
0x140005bdb  or      ebx, 80070000h
0x140005be1  mov     dword ptr [rsp+38h+ThreadId], 0
0x140005be9  test    ebx, ebx
0x140005beb  js      short loc_140005C43
0x140005bed  lea     rax, [rsp+38h+ThreadId]
0x140005bf2  xor     edx, edx; dwStackSize
0x140005bf4  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x140005bf9  lea     r9, ?_AtlModule@Spelling@Globalization@Windows@@3VCHostModule@123@A; lpParameter
0x140005c00  lea     r8, ?TimeoutMonitorProc@CHostModule@Spelling@Globalization@Windows@@SAKPEAX@Z; lpStartAddress
0x140005c07  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x140005c0f  xor     ecx, ecx; lpThreadAttributes
0x140005c11  call    cs:__imp_CreateThread
0x140005c17  test    rax, rax
0x140005c1a  jnz     short loc_140005C3A
0x140005c1c  call    cs:__imp_GetLastError
0x140005c22  mov     ebx, eax
0x140005c24  test    eax, eax
0x140005c26  jle     short loc_140005C31
0x140005c28  movzx   ebx, ax
0x140005c2b  or      ebx, 80070000h
0x140005c31  mov     rcx, cs:qword_14001C058
0x140005c38  jmp     short loc_140005C3D
0x140005c3a  mov     rcx, rax; hObject
0x140005c3d  call    cs:__imp_CloseHandle
0x140005c43  mov     eax, ebx
0x140005c45  add     rsp, 30h
0x140005c49  pop     rbx
0x140005c4a  retn
```
