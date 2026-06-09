# Logger::TraceVerbose(ushort const *,...)

- ea: `0x18000b32c`
- end: `0x18000b3be`
- name: `?TraceVerbose@Logger@@SAJPEBGZZ`
- size: `146`
- prototype: `__int64(const unsigned __int16 *, ...)`
- caller_count: `11`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800064e0`
- `0x180007ef0`
- `0x180008950`
- `0x180009010`
- `0x180009390`
- `0x18000ab5c`
- `0x18000afd0`
- `0x18000b08c`
- `0x18001943c`
- `0x180019e18`
- `0x18001a0a4`

## callees

- `0x18000b32c`
- `0x180019a54`
- `0x180019d98`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b3a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b3a0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b3b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b3b0`

## pseudocode

```c
__int64 Logger::TraceVerbose(const unsigned __int16 *a1, ...)
{
  int v1; // ebx
  HANDLE ProcessHeap; // rax
  LPVOID lpMem; // [rsp+20h] [rbp-18h] BYREF
  va_list va; // [rsp+48h] [rbp+10h] BYREF

  va_start(va, a1);
  v1 = 0;
  lpMem = 0;
  if ( UserDeviceRegistrationEventProvider_Context )
  {
    v1 = Logger::FormatString((unsigned __int16 **)&lpMem, a1, va);
    if ( v1 >= 0 )
    {
      if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 0x40) != 0 )
        v1 = McTemplateU0z_EventWriteTransfer(&UserDeviceRegistrationEventProvider_Context, VerboseDebugEvent, lpMem);
      else
        v1 = 0;
    }
  }
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18000b32c  mov     rax, rsp
0x18000b32f  mov     [rax+8], rcx
0x18000b333  mov     [rax+10h], rdx
0x18000b337  mov     [rax+18h], r8
0x18000b33b  mov     [rax+20h], r9
0x18000b33f  push    rbx
0x18000b340  sub     rsp, 30h
0x18000b344  xor     ebx, ebx
0x18000b346  mov     qword ptr [rax-18h], 0
0x18000b34e  cmp     cs:UserDeviceRegistrationEventProvider_Context, rbx
0x18000b355  lea     r8, [rax+10h]; char *
0x18000b359  mov     [rax-18h], rbx
0x18000b35d  jz      short loc_18000B398
0x18000b35f  mov     rdx, rcx; unsigned __int16 *
0x18000b362  lea     rcx, [rax-18h]; unsigned __int16 **
0x18000b366  call    ?FormatString@Logger@@CAJAEAPEAGPEBGPEAD@Z; Logger::FormatString(ushort * &,ushort const *,char *)
0x18000b36b  mov     ebx, eax
0x18000b36d  test    eax, eax
0x18000b36f  js      short loc_18000B398
0x18000b371  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 40h
0x18000b378  jz      short loc_18000B396
0x18000b37a  mov     r8, [rsp+38h+lpMem]
0x18000b37f  lea     rdx, VerboseDebugEvent
0x18000b386  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x18000b38d  call    McTemplateU0z_EventWriteTransfer
0x18000b392  mov     ebx, eax
0x18000b394  jmp     short loc_18000B398
0x18000b396  xor     ebx, ebx
0x18000b398  cmp     [rsp+38h+lpMem], 0
0x18000b39e  jz      short loc_18000B3B6
0x18000b3a0  call    cs:__imp_GetProcessHeap
0x18000b3a6  mov     r8, [rsp+38h+lpMem]; lpMem
0x18000b3ab  xor     edx, edx; dwFlags
0x18000b3ad  mov     rcx, rax; hHeap
0x18000b3b0  call    cs:__imp_HeapFree
0x18000b3b6  mov     eax, ebx
0x18000b3b8  add     rsp, 30h
0x18000b3bc  pop     rbx
0x18000b3bd  retn
```
