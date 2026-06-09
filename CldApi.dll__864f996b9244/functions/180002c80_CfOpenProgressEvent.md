# CfOpenProgressEvent

- ea: `0x180002c80`
- end: `0x180002d18`
- name: `CfOpenProgressEvent`
- size: `152`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002c80`
- `0x180011338`
- `0x18001b9b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002cd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ce5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002cd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002ce5`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180002cca`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180002cca`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180002ca7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180002ca7`

## pseudocode

```c
__int64 __fastcall CfOpenProgressEvent(_QWORD *a1)
{
  int v2; // edi
  int v3; // eax
  __int64 v4; // rcx
  unsigned int v5; // ebx
  HANDLE v6; // rdi
  DWORD LastError; // eax
  __int64 v8; // rcx
  signed int v9; // eax

  v2 = 0;
  v3 = GlobalPortInit(0);
  while ( 1 )
  {
    v5 = v3;
    if ( v3 >= 0 )
      break;
    if ( v2 >= 3 )
    {
      MicrosoftTelemetryAssertTriggeredArgs(v4, (unsigned int)v3);
      return v5;
    }
    Sleep(0x1Eu);
    v3 = GlobalPortInit(0);
    ++v2;
  }
  v6 = OpenEventW(0x100000u, 0, L"Global\\CfProgressEvent");
  if ( !v6 )
  {
    LastError = GetLastError();
    MicrosoftTelemetryAssertTriggeredArgs(v8, LastError);
    v9 = GetLastError();
    v5 = v9;
    if ( v9 > 0 )
      v5 = (unsigned __int16)v9 | 0x80070000;
  }
  *a1 = v6;
  return v5;
}

```

## disassembly

```asm
0x180002c80  mov     [rsp+arg_0], rbx
0x180002c85  mov     [rsp+arg_8], rsi
0x180002c8a  push    rdi
0x180002c8b  sub     rsp, 20h
0x180002c8f  mov     rsi, rcx
0x180002c92  xor     edi, edi
0x180002c94  xor     ecx, ecx
0x180002c96  call    GlobalPortInit
0x180002c9b  jmp     short loc_180002CB6
0x180002c9d  cmp     edi, 3
0x180002ca0  jge     short loc_180002D0F
0x180002ca2  mov     ecx, 1Eh; dwMilliseconds
0x180002ca7  call    cs:__imp_Sleep
0x180002cad  xor     ecx, ecx
0x180002caf  call    GlobalPortInit
0x180002cb4  inc     edi
0x180002cb6  mov     ebx, eax
0x180002cb8  test    eax, eax
0x180002cba  js      short loc_180002C9D
0x180002cbc  lea     r8, Name; "Global\\CfProgressEvent"
0x180002cc3  xor     edx, edx; bInheritHandle
0x180002cc5  mov     ecx, 100000h; dwDesiredAccess
0x180002cca  call    cs:__imp_OpenEventW
0x180002cd0  mov     rdi, rax
0x180002cd3  test    rax, rax
0x180002cd6  jnz     short loc_180002CFA
0x180002cd8  call    cs:__imp_GetLastError
0x180002cde  mov     edx, eax
0x180002ce0  call    MicrosoftTelemetryAssertTriggeredArgs
0x180002ce5  call    cs:__imp_GetLastError
0x180002ceb  mov     ebx, eax
0x180002ced  test    eax, eax
0x180002cef  jle     short loc_180002CFA
0x180002cf1  movzx   ebx, ax
0x180002cf4  or      ebx, 80070000h
0x180002cfa  mov     [rsi], rdi
0x180002cfd  mov     rsi, [rsp+28h+arg_8]
0x180002d02  mov     eax, ebx
0x180002d04  mov     rbx, [rsp+28h+arg_0]
0x180002d09  add     rsp, 20h
0x180002d0d  pop     rdi
0x180002d0e  retn
0x180002d0f  mov     edx, ebx
0x180002d11  call    MicrosoftTelemetryAssertTriggeredArgs
0x180002d16  jmp     short loc_180002CFD
```
