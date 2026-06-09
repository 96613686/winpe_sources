# HttpApiSynchronousDeviceControl

- ea: `0x180002b40`
- end: `0x180002cb5`
- name: `HttpApiSynchronousDeviceControl`
- size: `373`
- prototype: `__int64 __fastcall(HANDLE FileHandle, ULONG IoControlCode, PVOID InputBuffer, ULONG InputBufferLength, PVOID, ULONG, __int64)`
- caller_count: `41`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001130`
- `0x180001240`
- `0x180001330`
- `0x180001490`
- `0x1800015d0`
- `0x180001a30`
- `0x180001af0`
- `0x180001c40`
- `0x180001d20`
- `0x180002610`
- `0x180002820`
- `0x180002940`
- `0x180003890`
- `0x180003980`
- `0x180003bc0`
- `0x180004c00`
- `0x180004ca0`
- `0x180004d90`
- `0x180004f80`
- `0x180005050`
- `0x180005290`
- `0x180005320`
- `0x180005420`
- `0x180005520`
- `0x1800055b0`
- `0x1800056e0`
- `0x180005770`
- `0x180005810`
- `0x1800058b0`
- `0x180005ab0`
- `0x180005c70`
- `0x180005d60`
- `0x180005e50`
- `0x180005f00`
- `0x180005fe0`
- `0x1800082d0`
- `0x180008550`
- `0x180008610`
- `0x1800091c0`
- `0x180009280`
- `0x18000a150`

## callees

- `0x180002b40`
- `0x180002cc0`
- `0x18000b080`
- `0x18000be2c`
- `0x18000beb4`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x180002be0`
- `ntdll!NtDeviceIoControlFile` at `0x180002be0`
- `ntdll!NtWaitForSingleObject` at `0x180002c3d`
- `ntdll!NtWaitForSingleObject` at `0x180002c3d`
- `ntdll!RtlNtStatusToDosError` at `0x180002c0c`
- `ntdll!RtlNtStatusToDosError` at `0x180002c0c`

## pseudocode

```c
ULONG __fastcall HttpApiSynchronousDeviceControl(
        HANDLE FileHandle,
        ULONG IoControlCode,
        PVOID InputBuffer,
        ULONG InputBufferLength,
        PVOID a5,
        ULONG OutputBufferLength,
        _DWORD *a7)
{
  NTSTATUS Status; // ebx
  HANDLE v12; // rsi
  __int64 v13; // rcx
  ULONG InputBufferLengtha; // [rsp+38h] [rbp-80h]
  union _LARGE_INTEGER Timeout; // [rsp+50h] [rbp-68h] BYREF
  HANDLE Event; // [rsp+58h] [rbp-60h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-58h] BYREF

  IoStatusBlock = 0;
  Timeout.QuadPart = 0;
  Event = 0;
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_qLqLqL(
      (_DWORD)FileHandle,
      IoControlCode,
      (_DWORD)InputBuffer,
      (_DWORD)FileHandle,
      IoControlCode,
      (char)InputBuffer,
      InputBufferLength,
      a5,
      OutputBufferLength);
  if ( a7 )
    *a7 = 0;
  Status = HttpApiAcquireCachedEvent(&Event);
  if ( Status >= 0 )
  {
    InputBufferLengtha = InputBufferLength;
    v12 = Event;
    Status = NtDeviceIoControlFile(
               FileHandle,
               Event,
               0,
               0,
               &IoStatusBlock,
               IoControlCode,
               InputBuffer,
               InputBufferLengtha,
               a5,
               OutputBufferLength);
    if ( Status == 259 )
    {
      Timeout.QuadPart = 0x7FFFFFFFFFFFFFFFLL;
      NtWaitForSingleObject(v12, 0, &Timeout);
      Status = IoStatusBlock.Status;
    }
    if ( (Status & 0xC0000000) != 0xC0000000 && a7 )
    {
      *a7 = IoStatusBlock.Information;
      if ( (byte_1800126A3 & 4) == 0 )
        return RtlNtStatusToDosError(Status);
      WPP_SF_L(v13, 11, WPP_f0d88ac2d9fc3a89569733988c3b753d_Traceguids);
    }
  }
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_d(1050, 12, WPP_f0d88ac2d9fc3a89569733988c3b753d_Traceguids, (unsigned int)Status);
  return RtlNtStatusToDosError(Status);
}

```

## disassembly

```asm
0x180002b40  push    rbx
0x180002b42  push    rbp
0x180002b43  push    rsi
0x180002b44  push    rdi
0x180002b45  push    r12
0x180002b47  push    r13
0x180002b49  push    r14
0x180002b4b  push    r15
0x180002b4d  sub     rsp, 78h
0x180002b51  xor     ebx, ebx
0x180002b53  xorps   xmm0, xmm0
0x180002b56  movups  xmmword ptr [rsp+0B8h+var_58], xmm0
0x180002b5b  mov     qword ptr [rsp+0B8h+Timeout], rbx
0x180002b60  mov     esi, r9d
0x180002b63  mov     [rsp+0B8h+Event], rbx
0x180002b68  mov     rbp, r8
0x180002b6b  mov     r14d, edx
0x180002b6e  mov     r15, rcx
0x180002b71  test    cs:byte_1800126A3, 4
0x180002b78  mov     r12d, [rsp+0B8h+arg_28]
0x180002b80  mov     r13, [rsp+0B8h+arg_20]
0x180002b88  jnz     loc_180002C72
0x180002b8e  mov     rdi, [rsp+0B8h+arg_30]
0x180002b96  test    rdi, rdi
0x180002b99  jz      short loc_180002B9D
0x180002b9b  mov     [rdi], ebx
0x180002b9d  lea     rcx, [rsp+0B8h+Event]
0x180002ba2  call    HttpApiAcquireCachedEvent
0x180002ba7  mov     ebx, eax
0x180002ba9  test    eax, eax
0x180002bab  js      short loc_180002BFD
0x180002bad  mov     [rsp+0B8h+OutputBufferLength], r12d; OutputBufferLength
0x180002bb2  lea     rax, [rsp+0B8h+var_58]
0x180002bb7  mov     [rsp+0B8h+OutputBuffer], r13; OutputBuffer
0x180002bbc  xor     r9d, r9d; ApcContext
0x180002bbf  mov     [rsp+0B8h+InputBufferLength], esi; InputBufferLength
0x180002bc3  xor     r8d, r8d; ApcRoutine
0x180002bc6  mov     rsi, [rsp+0B8h+Event]
0x180002bcb  mov     rcx, r15; FileHandle
0x180002bce  mov     [rsp+0B8h+InputBuffer], rbp; InputBuffer
0x180002bd3  mov     rdx, rsi; Event
0x180002bd6  mov     [rsp+0B8h+IoControlCode], r14d; IoControlCode
0x180002bdb  mov     [rsp+0B8h+IoStatusBlock], rax; IoStatusBlock
0x180002be0  call    cs:__imp_NtDeviceIoControlFile
0x180002be6  mov     ebx, eax
0x180002be8  cmp     eax, 103h
0x180002bed  jz      short loc_180002C23
0x180002bef  mov     eax, ebx
0x180002bf1  and     eax, 0C0000000h
0x180002bf6  cmp     eax, 0C0000000h
0x180002bfb  jnz     short loc_180002C49
0x180002bfd  test    cs:byte_1800126A3, 4
0x180002c04  jnz     loc_180002C97
0x180002c0a  mov     ecx, ebx; Status
0x180002c0c  call    cs:__imp_RtlNtStatusToDosError
0x180002c12  add     rsp, 78h
0x180002c16  pop     r15
0x180002c18  pop     r14
0x180002c1a  pop     r13
0x180002c1c  pop     r12
0x180002c1e  pop     rdi
0x180002c1f  pop     rsi
0x180002c20  pop     rbp
0x180002c21  pop     rbx
0x180002c22  retn
0x180002c23  lea     r8, [rsp+0B8h+Timeout]; Timeout
0x180002c28  mov     dword ptr [rsp+0B8h+Timeout], 0FFFFFFFFh
0x180002c30  xor     edx, edx; Alertable
0x180002c32  mov     dword ptr [rsp+0B8h+Timeout+4], 7FFFFFFFh
0x180002c3a  mov     rcx, rsi; Handle
0x180002c3d  call    cs:__imp_NtWaitForSingleObject
0x180002c43  mov     ebx, dword ptr [rsp+0B8h+var_58]
0x180002c47  jmp     short loc_180002BEF
0x180002c49  test    rdi, rdi
0x180002c4c  jz      short loc_180002BFD
0x180002c4e  mov     r9d, dword ptr [rsp+0B8h+var_58.Information]
0x180002c53  mov     [rdi], r9d
0x180002c56  test    cs:byte_1800126A3, 4
0x180002c5d  jz      short loc_180002C0A
0x180002c5f  mov     edx, 0Bh
0x180002c64  lea     r8, WPP_f0d88ac2d9fc3a89569733988c3b753d_Traceguids
0x180002c6b  call    WPP_SF_L
0x180002c70  jmp     short loc_180002BFD
0x180002c72  mov     dword ptr [rsp+0B8h+OutputBuffer], r12d
0x180002c77  mov     r9, r15
0x180002c7a  mov     qword ptr [rsp+0B8h+InputBufferLength], r13
0x180002c7f  mov     dword ptr [rsp+0B8h+InputBuffer], esi
0x180002c83  mov     qword ptr [rsp+0B8h+IoControlCode], rbp
0x180002c88  mov     dword ptr [rsp+0B8h+IoStatusBlock], r14d
0x180002c8d  call    WPP_SF_qLqLqL
0x180002c92  jmp     loc_180002B8E
0x180002c97  mov     edx, 0Ch
0x180002c9c  lea     r8, WPP_f0d88ac2d9fc3a89569733988c3b753d_Traceguids
0x180002ca3  mov     ecx, 41Ah
0x180002ca8  mov     r9d, ebx
0x180002cab  call    WPP_SF_d
0x180002cb0  jmp     loc_180002C0A
```
