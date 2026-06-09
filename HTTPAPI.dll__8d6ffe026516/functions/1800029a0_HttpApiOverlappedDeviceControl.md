# HttpApiOverlappedDeviceControl

- ea: `0x1800029a0`
- end: `0x180002b2f`
- name: `HttpApiOverlappedDeviceControl`
- size: `399`
- prototype: `ULONG __fastcall(HANDLE FileHandle, struct _IO_STATUS_BLOCK *ApcContext, ULONG IoControlCode, PVOID InputBuffer, ULONG InputBufferLength, PVOID OutputBuffer, ULONG, _DWORD *)`
- caller_count: `7`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180001330`
- `0x180001a30`
- `0x180001c40`
- `0x180001d20`
- `0x180002610`
- `0x180002820`
- `0x180002940`

## callees

- `0x1800029a0`
- `0x18000b080`
- `0x18000be2c`
- `0x18000c0ac`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x180002a34`
- `ntdll!NtDeviceIoControlFile` at `0x180002a34`
- `ntdll!RtlNtStatusToDosError` at `0x180002a59`
- `ntdll!RtlNtStatusToDosError` at `0x180002a59`

## pseudocode

```c
ULONG __fastcall HttpApiOverlappedDeviceControl(
        HANDLE FileHandle,
        struct _IO_STATUS_BLOCK *ApcContext,
        ULONG IoControlCode,
        PVOID InputBuffer,
        ULONG InputBufferLength,
        PVOID OutputBuffer,
        ULONG a7,
        _DWORD *a8)
{
  HANDLE v11; // rax
  struct _IO_STATUS_BLOCK *v12; // r9
  void *Information; // rdx
  NTSTATUS v14; // eax
  unsigned int v15; // esi
  __int64 v17; // rcx

  v11 = FileHandle;
  if ( (byte_1800126A3 & 4) != 0 )
  {
    WPP_SF_qqLqLqL(
      (_DWORD)FileHandle,
      (_DWORD)ApcContext,
      IoControlCode,
      (_DWORD)FileHandle,
      (char)ApcContext,
      IoControlCode,
      (char)InputBuffer,
      InputBufferLength,
      OutputBuffer,
      a7);
    v11 = FileHandle;
  }
  ApcContext->Status = 259;
  v12 = 0;
  if ( a8 )
    *a8 = 0;
  Information = (void *)ApcContext[1].Information;
  if ( ((unsigned __int8)Information & 1) == 0 )
    v12 = ApcContext;
  v14 = NtDeviceIoControlFile(
          v11,
          Information,
          0,
          v12,
          ApcContext,
          IoControlCode,
          InputBuffer,
          InputBufferLength,
          OutputBuffer,
          a7);
  v15 = v14;
  if ( v14 != 259 )
  {
    v17 = v14 & 0xC0000000;
    if ( (_DWORD)v17 != -1073741824 )
    {
      if ( a8 )
      {
        *a8 = ApcContext->Information;
        if ( (byte_1800126A3 & 4) != 0 )
          WPP_SF_L(v17, 14, WPP_f0d88ac2d9fc3a89569733988c3b753d_Traceguids);
      }
    }
  }
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_d(1050, 16, WPP_f0d88ac2d9fc3a89569733988c3b753d_Traceguids, v15);
  return RtlNtStatusToDosError(v15);
}

```

## disassembly

```asm
0x1800029a0  mov     [rsp+arg_8], rbx
0x1800029a5  mov     [rsp+arg_10], rsi
0x1800029aa  mov     [rsp+arg_0], rcx
0x1800029af  push    rdi
0x1800029b0  push    r12
0x1800029b2  push    r13
0x1800029b4  push    r14
0x1800029b6  push    r15
0x1800029b8  sub     rsp, 50h
0x1800029bc  mov     r12, r9
0x1800029bf  mov     r13d, r8d
0x1800029c2  mov     rbx, rdx
0x1800029c5  mov     rax, rcx
0x1800029c8  mov     esi, [rsp+78h+arg_30]
0x1800029cf  mov     r14, [rsp+78h+arg_28]
0x1800029d7  mov     r15d, [rsp+78h+arg_20]
0x1800029df  test    cs:byte_1800126A3, 4
0x1800029e6  jnz     loc_180002ADF
0x1800029ec  mov     dword ptr [rbx], 103h
0x1800029f2  mov     rdi, [rsp+78h+arg_38]
0x1800029fa  xor     r9d, r9d
0x1800029fd  test    rdi, rdi
0x180002a00  jz      short loc_180002A05
0x180002a02  mov     [rdi], r9d
0x180002a05  mov     rdx, [rbx+18h]; Event
0x180002a09  test    dl, 1
0x180002a0c  jnz     short loc_180002A11
0x180002a0e  mov     r9, rbx; ApcContext
0x180002a11  mov     [rsp+78h+OutputBufferLength], esi; OutputBufferLength
0x180002a15  mov     [rsp+78h+OutputBuffer], r14; OutputBuffer
0x180002a1a  mov     [rsp+78h+InputBufferLength], r15d; InputBufferLength
0x180002a1f  mov     [rsp+78h+InputBuffer], r12; InputBuffer
0x180002a24  mov     [rsp+78h+IoControlCode], r13d; IoControlCode
0x180002a29  mov     [rsp+78h+IoStatusBlock], rbx; IoStatusBlock
0x180002a2e  xor     r8d, r8d; ApcRoutine
0x180002a31  mov     rcx, rax; FileHandle
0x180002a34  call    cs:__imp_NtDeviceIoControlFile
0x180002a3a  mov     esi, eax
0x180002a3c  mov     dword ptr [rsp+78h+arg_38], eax
0x180002a43  cmp     eax, 103h
0x180002a48  jnz     short loc_180002A79
0x180002a4a  test    cs:byte_1800126A3, 4
0x180002a51  jnz     loc_180002B11
0x180002a57  mov     ecx, esi; Status
0x180002a59  call    cs:__imp_RtlNtStatusToDosError
0x180002a5f  lea     r11, [rsp+78h+var_28]
0x180002a64  mov     rbx, [r11+38h]
0x180002a68  mov     rsi, [r11+40h]
0x180002a6c  mov     rsp, r11
0x180002a6f  pop     r15
0x180002a71  pop     r14
0x180002a73  pop     r13
0x180002a75  pop     r12
0x180002a77  pop     rdi
0x180002a78  retn
0x180002a79  mov     ecx, eax
0x180002a7b  and     ecx, 0C0000000h
0x180002a81  cmp     ecx, 0C0000000h
0x180002a87  jz      short loc_180002A4A
0x180002a89  test    rdi, rdi
0x180002a8c  jz      short loc_180002A4A
0x180002a8e  mov     r9d, [rbx+8]
0x180002a92  mov     [rdi], r9d
0x180002a95  test    cs:byte_1800126A3, 4
0x180002a9c  jz      short loc_180002AAF
0x180002a9e  mov     edx, 0Eh
0x180002aa3  lea     r8, WPP_f0d88ac2d9fc3a89569733988c3b753d_Traceguids
0x180002aaa  call    WPP_SF_L
0x180002aaf  jmp     short loc_180002A4A
0x180002ab1  test    cs:byte_180012693, 4
0x180002ab8  jz      short loc_180002AD3
0x180002aba  mov     r9d, eax
0x180002abd  mov     edx, 0Fh
0x180002ac2  mov     ecx, 21Ah
0x180002ac7  lea     r8, WPP_f0d88ac2d9fc3a89569733988c3b753d_Traceguids
0x180002ace  call    WPP_SF_d
0x180002ad3  mov     esi, dword ptr [rsp+78h+arg_38]
0x180002ada  jmp     loc_180002A4A
0x180002adf  mov     [rsp+78h+OutputBufferLength], esi
0x180002ae3  mov     [rsp+78h+OutputBuffer], r14
0x180002ae8  mov     [rsp+78h+InputBufferLength], r15d
0x180002aed  mov     [rsp+78h+InputBuffer], r12
0x180002af2  mov     [rsp+78h+IoControlCode], r13d
0x180002af7  mov     [rsp+78h+IoStatusBlock], rbx
0x180002afc  mov     r9, rcx
0x180002aff  call    WPP_SF_qqLqLqL
0x180002b04  mov     rax, [rsp+78h+arg_0]
0x180002b0c  jmp     loc_1800029EC
0x180002b11  mov     edx, 10h
0x180002b16  mov     ecx, 41Ah
0x180002b1b  mov     r9d, esi
0x180002b1e  lea     r8, WPP_f0d88ac2d9fc3a89569733988c3b753d_Traceguids
0x180002b25  call    WPP_SF_d
0x180002b2a  jmp     loc_180002A57
```
