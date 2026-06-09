# HttpReadFragmentFromCache

- ea: `0x180008390`
- end: `0x180008471`
- name: `HttpReadFragmentFromCache`
- size: `225`
- prototype: `ULONG __stdcall(HANDLE RequestQueueHandle, PCWSTR UrlPrefix, PHTTP_BYTE_RANGE ByteRange, PVOID Buffer, ULONG BufferLength, PULONG BytesRead, LPOVERLAPPED Overlapped)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002940`
- `0x180008390`
- `0x18000a5f0`
- `0x18000c16c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800083ec`
- `ntdll!RtlNtStatusToDosError` at `0x1800083ec`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800083e0`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800083e0`

## pseudocode

```c
ULONG __stdcall HttpReadFragmentFromCache(
        HANDLE RequestQueueHandle,
        PCWSTR UrlPrefix,
        PHTTP_BYTE_RANGE ByteRange,
        PVOID Buffer,
        ULONG BufferLength,
        PULONG BytesRead,
        LPOVERLAPPED Overlapped)
{
  int inited; // eax
  __int64 v11; // rcx
  ULARGE_INTEGER StartingOffset; // r9
  ULARGE_INTEGER Length; // rax
  __int64 v15; // [rsp+20h] [rbp-78h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-58h] BYREF
  __int128 v17; // [rsp+50h] [rbp-48h]

  DestinationString = 0;
  v17 = 0;
  if ( BytesRead )
    *BytesRead = 0;
  inited = RtlInitUnicodeStringEx(&DestinationString, UrlPrefix);
  if ( inited < 0 )
    return RtlNtStatusToDosError(inited);
  if ( ByteRange )
  {
    StartingOffset = ByteRange->StartingOffset;
    Length = ByteRange->Length;
  }
  else
  {
    StartingOffset.QuadPart = 0;
    Length.QuadPart = -1;
  }
  *((ULARGE_INTEGER *)&v17 + 1) = Length;
  *(ULARGE_INTEGER *)&v17 = StartingOffset;
  if ( (byte_1800126A3 & 4) != 0 )
  {
    HIDWORD(v15) = Length.HighPart;
    WPP_SF_II(v11);
  }
  LODWORD(v15) = 32;
  return ((__int64 (__fastcall *)(HANDLE, LPOVERLAPPED, __int64, struct _UNICODE_STRING *, __int64, PVOID, ULONG, PULONG))HttpApiDeviceControl)(
           RequestQueueHandle,
           Overlapped,
           1196127,
           &DestinationString,
           v15,
           Buffer,
           BufferLength,
           BytesRead);
}

```

## disassembly

```asm
0x180008390  push    rbx
0x180008392  push    rbp
0x180008393  push    rsi
0x180008394  push    rdi
0x180008395  push    r14
0x180008397  sub     rsp, 70h
0x18000839b  mov     rax, cs:__security_cookie
0x1800083a2  xor     rax, rsp
0x1800083a5  mov     [rsp+98h+var_38], rax
0x1800083aa  mov     rdi, [rsp+98h+BytesRead]
0x1800083b2  xorps   xmm0, xmm0
0x1800083b5  mov     r14, [rsp+98h+Overlapped]
0x1800083bd  mov     rbp, r9
0x1800083c0  mov     rbx, r8
0x1800083c3  mov     rsi, rcx
0x1800083c6  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x1800083cb  movups  [rsp+98h+var_48], xmm0
0x1800083d0  test    rdi, rdi
0x1800083d3  jz      short loc_1800083DB
0x1800083d5  mov     dword ptr [rdi], 0
0x1800083db  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x1800083e0  call    cs:__imp_RtlInitUnicodeStringEx
0x1800083e6  test    eax, eax
0x1800083e8  jns     short loc_1800083F4
0x1800083ea  mov     ecx, eax; Status
0x1800083ec  call    cs:__imp_RtlNtStatusToDosError
0x1800083f2  jmp     short loc_180008459
0x1800083f4  test    rbx, rbx
0x1800083f7  jz      short loc_180008402
0x1800083f9  mov     r9, [rbx]
0x1800083fc  mov     rax, [rbx+8]
0x180008400  jmp     short loc_180008409
0x180008402  xor     r9d, r9d
0x180008405  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008409  mov     qword ptr [rsp+98h+var_48+8], rax
0x18000840e  mov     qword ptr [rsp+98h+var_48], r9
0x180008413  test    cs:byte_1800126A3, 4
0x18000841a  jz      short loc_180008426
0x18000841c  mov     [rsp+98h+var_78], rax
0x180008421  call    WPP_SF_II
0x180008426  mov     eax, [rsp+98h+BufferLength]
0x18000842d  lea     r9, [rsp+98h+DestinationString]
0x180008432  mov     [rsp+98h+var_60], rdi
0x180008437  mov     r8d, 12405Fh
0x18000843d  mov     [rsp+98h+var_68], eax
0x180008441  mov     rdx, r14
0x180008444  mov     [rsp+98h+var_70], rbp
0x180008449  mov     rcx, rsi
0x18000844c  mov     dword ptr [rsp+98h+var_78], 20h ; ' '
0x180008454  call    HttpApiDeviceControl
0x180008459  mov     rcx, [rsp+98h+var_38]
0x18000845e  xor     rcx, rsp; StackCookie
0x180008461  call    __security_check_cookie
0x180008466  add     rsp, 70h
0x18000846a  pop     r14
0x18000846c  pop     rdi
0x18000846d  pop     rsi
0x18000846e  pop     rbp
0x18000846f  pop     rbx
0x180008470  retn
```
