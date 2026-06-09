# HttpDeclarePush

- ea: `0x180005d60`
- end: `0x180005e3e`
- name: `HttpDeclarePush`
- size: `222`
- prototype: `ULONG __stdcall(HANDLE RequestQueueHandle, HTTP_REQUEST_ID RequestId, HTTP_VERB Verb, PCWSTR Path, PCSTR Query, PHTTP_REQUEST_HEADERS Headers)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180002b40`
- `0x180005d60`
- `0x18000b718`

## import_xrefs

- `ntdll!RtlInitAnsiStringEx` at `0x180005dfe`
- `ntdll!RtlInitAnsiStringEx` at `0x180005dfe`
- `ntdll!RtlNtStatusToDosError` at `0x180005dee`
- `ntdll!RtlNtStatusToDosError` at `0x180005dee`
- `ntdll!RtlInitUnicodeStringEx` at `0x180005de0`
- `ntdll!RtlInitUnicodeStringEx` at `0x180005de0`

## pseudocode

```c
ULONG __stdcall HttpDeclarePush(
        HANDLE RequestQueueHandle,
        HTTP_REQUEST_ID RequestId,
        HTTP_VERB Verb,
        PCWSTR Path,
        PCSTR Query,
        PHTTP_REQUEST_HEADERS Headers)
{
  int inited; // eax
  __int128 InputBuffer; // [rsp+40h] [rbp-78h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-68h] BYREF
  _STRING v14; // [rsp+60h] [rbp-58h] BYREF
  PHTTP_REQUEST_HEADERS v15; // [rsp+70h] [rbp-48h]

  InputBuffer = 0;
  v15 = 0;
  DestinationString = 0;
  v14 = 0;
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_IdqSs(
      (_DWORD)RequestQueueHandle,
      RequestId,
      Verb,
      RequestId,
      Verb,
      (char)Headers,
      (__int64)Path,
      (__int64)Query);
  *(_QWORD *)&InputBuffer = RequestId;
  DWORD2(InputBuffer) = Verb;
  v15 = Headers;
  inited = RtlInitUnicodeStringEx(&DestinationString, Path);
  if ( inited < 0 )
    return RtlNtStatusToDosError(inited);
  inited = RtlInitAnsiStringEx(&v14, Query);
  if ( inited < 0 )
    return RtlNtStatusToDosError(inited);
  else
    return HttpApiSynchronousDeviceControl(RequestQueueHandle, 0x124070u, &InputBuffer, 0x38u, 0, 0, 0);
}

```

## disassembly

```asm
0x180005d60  push    rbx
0x180005d62  push    rbp
0x180005d63  push    rsi
0x180005d64  push    rdi
0x180005d65  push    r14
0x180005d67  push    r15
0x180005d69  sub     rsp, 88h
0x180005d70  xorps   xmm0, xmm0
0x180005d73  xor     eax, eax
0x180005d75  movups  [rsp+0B8h+InputBuffer], xmm0
0x180005d7a  mov     [rsp+0B8h+var_48], rax
0x180005d7f  mov     rdi, r9
0x180005d82  movups  xmmword ptr [rsp+0B8h+DestinationString.Length], xmm0
0x180005d87  mov     esi, r8d
0x180005d8a  mov     rbp, rdx
0x180005d8d  movups  xmmword ptr [rsp+0B8h+var_58.Length], xmm0
0x180005d92  mov     r15, rcx
0x180005d95  test    cs:byte_1800126A3, 4
0x180005d9c  mov     r14, [rsp+0B8h+Headers]
0x180005da4  mov     rbx, [rsp+0B8h+Query]
0x180005dac  jz      short loc_180005DCA
0x180005dae  mov     [rsp+0B8h+var_80], rbx
0x180005db3  mov     [rsp+0B8h+var_88], r9
0x180005db8  mov     r9, rdx
0x180005dbb  mov     qword ptr [rsp+0B8h+var_90], r14
0x180005dc0  mov     dword ptr [rsp+0B8h+var_98], r8d
0x180005dc5  call    WPP_SF_IdqSs
0x180005dca  mov     rdx, rdi; SourceString
0x180005dcd  mov     qword ptr [rsp+0B8h+InputBuffer], rbp
0x180005dd2  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x180005dd7  mov     dword ptr [rsp+0B8h+InputBuffer+8], esi
0x180005ddb  mov     [rsp+0B8h+var_48], r14
0x180005de0  call    cs:__imp_RtlInitUnicodeStringEx
0x180005de6  xor     edi, edi
0x180005de8  test    eax, eax
0x180005dea  jns     short loc_180005DF6
0x180005dec  mov     ecx, eax; Status
0x180005dee  call    cs:__imp_RtlNtStatusToDosError
0x180005df4  jmp     short loc_180005E2E
0x180005df6  mov     rdx, rbx; SourceString
0x180005df9  lea     rcx, [rsp+0B8h+var_58]; DestinationString
0x180005dfe  call    cs:__imp_RtlInitAnsiStringEx
0x180005e04  test    eax, eax
0x180005e06  js      short loc_180005DEC
0x180005e08  mov     [rsp+0B8h+var_88], rdi; __int64
0x180005e0d  lea     r8, [rsp+0B8h+InputBuffer]; InputBuffer
0x180005e12  mov     [rsp+0B8h+var_90], edi; ULONG
0x180005e16  mov     r9d, 38h ; '8'; InputBufferLength
0x180005e1c  mov     edx, 124070h; IoControlCode
0x180005e21  mov     [rsp+0B8h+var_98], rdi; PVOID
0x180005e26  mov     rcx, r15; FileHandle
0x180005e29  call    HttpApiSynchronousDeviceControl
0x180005e2e  add     rsp, 88h
0x180005e35  pop     r15
0x180005e37  pop     r14
0x180005e39  pop     rdi
0x180005e3a  pop     rsi
0x180005e3b  pop     rbp
0x180005e3c  pop     rbx
0x180005e3d  retn
```
