# HttpFlushResponseCache

- ea: `0x180001c40`
- end: `0x180001d16`
- name: `HttpFlushResponseCache`
- size: `214`
- prototype: `ULONG __stdcall(HANDLE RequestQueueHandle, PCWSTR UrlPrefix, ULONG Flags, LPOVERLAPPED Overlapped)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001c40`
- `0x1800029a0`
- `0x180002b40`
- `0x18000be2c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180001d0e`
- `ntdll!RtlNtStatusToDosError` at `0x180001d0e`
- `ntdll!RtlInitUnicodeStringEx` at `0x180001c79`
- `ntdll!RtlInitUnicodeStringEx` at `0x180001c79`

## pseudocode

```c
ULONG __stdcall HttpFlushResponseCache(
        HANDLE RequestQueueHandle,
        PCWSTR UrlPrefix,
        ULONG Flags,
        LPOVERLAPPED Overlapped)
{
  int inited; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-48h] BYREF
  __int64 v11; // [rsp+50h] [rbp-38h]

  DestinationString = 0;
  v11 = 0;
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_L(RequestQueueHandle, 15, WPP_88109d8d3e5b32c3c016118f2408fbcf_Traceguids);
  inited = RtlInitUnicodeStringEx((PUNICODE_STRING)&DestinationString.Buffer, UrlPrefix);
  if ( inited < 0 )
    return RtlNtStatusToDosError(inited);
  *(_DWORD *)&DestinationString.Length = Flags;
  if ( Overlapped )
    return HttpApiOverlappedDeviceControl(
             RequestQueueHandle,
             (struct _IO_STATUS_BLOCK *)Overlapped,
             0x124044u,
             &DestinationString,
             0x18u,
             0,
             0,
             0);
  else
    return HttpApiSynchronousDeviceControl(RequestQueueHandle, 0x124044u, &DestinationString, 0x18u, 0, 0, 0);
}

```

## disassembly

```asm
0x180001c40  push    rbx
0x180001c42  push    rbp
0x180001c43  push    rsi
0x180001c44  push    rdi
0x180001c45  sub     rsp, 68h
0x180001c49  xorps   xmm0, xmm0
0x180001c4c  xor     eax, eax
0x180001c4e  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x180001c53  mov     [rsp+88h+var_38], rax
0x180001c58  mov     rbx, r9
0x180001c5b  mov     edi, r8d
0x180001c5e  mov     rsi, rdx
0x180001c61  mov     rbp, rcx
0x180001c64  test    cs:byte_1800126A3, 4
0x180001c6b  jnz     loc_180001CF3
0x180001c71  mov     rdx, rsi; SourceString
0x180001c74  lea     rcx, [rsp+88h+DestinationString.Buffer]; DestinationString
0x180001c79  call    cs:__imp_RtlInitUnicodeStringEx
0x180001c7f  test    eax, eax
0x180001c81  js      loc_180001D0C
0x180001c87  xor     eax, eax
0x180001c89  mov     dword ptr [rsp+88h+DestinationString.Length], edi
0x180001c8d  mov     rcx, rbp; FileHandle
0x180001c90  test    rbx, rbx
0x180001c93  jz      short loc_180001CC7
0x180001c95  mov     [rsp+88h+var_50], rax; __int64
0x180001c9a  lea     r9, [rsp+88h+DestinationString]; InputBuffer
0x180001c9f  mov     [rsp+88h+var_58], eax; ULONG
0x180001ca3  mov     r8d, 124044h; IoControlCode
0x180001ca9  mov     [rsp+88h+var_60], rax; PVOID
0x180001cae  mov     rdx, rbx; ApcContext
0x180001cb1  mov     [rsp+88h+var_68], 18h; ULONG
0x180001cb9  call    HttpApiOverlappedDeviceControl
0x180001cbe  add     rsp, 68h
0x180001cc2  pop     rdi
0x180001cc3  pop     rsi
0x180001cc4  pop     rbp
0x180001cc5  pop     rbx
0x180001cc6  retn
0x180001cc7  mov     qword ptr [rsp+88h+var_58], rax; __int64
0x180001ccc  lea     r8, [rsp+88h+DestinationString]; InputBuffer
0x180001cd1  mov     dword ptr [rsp+88h+var_60], eax; ULONG
0x180001cd5  mov     r9d, 18h; InputBufferLength
0x180001cdb  mov     edx, 124044h; IoControlCode
0x180001ce0  mov     qword ptr [rsp+88h+var_68], rax; PVOID
0x180001ce5  call    HttpApiSynchronousDeviceControl
0x180001cea  add     rsp, 68h
0x180001cee  pop     rdi
0x180001cef  pop     rsi
0x180001cf0  pop     rbp
0x180001cf1  pop     rbx
0x180001cf2  retn
0x180001cf3  mov     edx, 0Fh
0x180001cf8  lea     r8, WPP_88109d8d3e5b32c3c016118f2408fbcf_Traceguids
0x180001cff  mov     r9d, edi
0x180001d02  call    WPP_SF_L
0x180001d07  jmp     loc_180001C71
0x180001d0c  mov     ecx, eax; Status
0x180001d0e  call    cs:__imp_RtlNtStatusToDosError
0x180001d14  jmp     short loc_180001CBE
```
