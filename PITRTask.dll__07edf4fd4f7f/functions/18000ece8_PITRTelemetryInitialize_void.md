# PITRTelemetryInitialize(void)

- ea: `0x18000ece8`
- end: `0x18000ee32`
- name: `?PITRTelemetryInitialize@@YAJXZ`
- size: `330`
- prototype: `__int64(void)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a4f0`
- `0x18000d4c0`
- `0x18000d750`
- `0x18000dc90`
- `0x18000de04`
- `0x18000e16c`
- `0x18000e804`
- `0x18000f180`
- `0x18000f624`
- `0x18000ff50`

## callees

- `0x180001008`
- `0x18000ece8`
- `0x1800107c0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000ed57`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000ed57`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000ed8f`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000ed8f`

## pseudocode

```c
__int64 PITRTelemetryInitialize(void)
{
  signed int v1; // eax
  unsigned int v2; // ebx
  GUID ProviderId; // [rsp+30h] [rbp-58h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v4; // [rsp+40h] [rbp-48h] BYREF
  GUID *p_ProviderId; // [rsp+60h] [rbp-28h]
  __int64 v6; // [rsp+68h] [rbp-20h]

  if ( dword_18001BFA0 )
    return 0;
  ProviderId = (GUID)*((_OWORD *)off_18001B008 - 1);
  if ( RegHandle )
    __fastfail(5u);
  xmmword_18001B028 = 0;
  v1 = EventRegister(&ProviderId, tlgEnableCallback, &dword_18001B000, &RegHandle);
  v2 = v1;
  if ( v1 )
  {
    if ( v1 > 0 )
      v2 = (unsigned __int16)v1 | 0x80070000;
    if ( (v2 & 0x80000000) != 0 )
      return v2;
  }
  else
  {
    EventSetInformation(RegHandle, 2, off_18001B008, *(unsigned __int16 *)off_18001B008);
  }
  dword_18001BFA0 = 1;
  if ( (unsigned int)dword_18001B000 > 5
    && (qword_18001B010 & 0x800000000000LL) != 0
    && (qword_18001B018 & 0x800000000000LL) == qword_18001B018 )
  {
    v6 = 8;
    *(_QWORD *)&ProviderId.Data1 = 0x80000000LL;
    p_ProviderId = &ProviderId;
    tlgWriteTransfer_EventWriteTransfer((int)&dword_18001B000, (int)&byte_1800173B7, 0, 0, 3u, &v4);
  }
  return v2;
}

```

## disassembly

```asm
0x18000ece8  push    rbx
0x18000ecea  sub     rsp, 80h
0x18000ecf1  mov     rax, cs:__security_cookie
0x18000ecf8  xor     rax, rsp
0x18000ecfb  mov     [rsp+88h+var_18], rax
0x18000ed00  cmp     cs:dword_18001BFA0, 0
0x18000ed07  jz      short loc_18000ED10
0x18000ed09  xor     eax, eax
0x18000ed0b  jmp     loc_18000EE1C
0x18000ed10  cmp     cs:RegHandle, 0
0x18000ed18  mov     rax, cs:off_18001B008
0x18000ed1f  movups  xmm0, xmmword ptr [rax-10h]
0x18000ed23  movdqu  xmmword ptr [rsp+88h+ProviderId.Data1], xmm0
0x18000ed29  jz      short loc_18000ED32
0x18000ed2b  mov     ecx, 5
0x18000ed30  int     29h; Win8: RtlFailFast(ecx)
0x18000ed32  xorps   xmm0, xmm0
0x18000ed35  lea     r9, RegHandle; RegHandle
0x18000ed3c  lea     r8, dword_18001B000; CallbackContext
0x18000ed43  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000ed4a  lea     rcx, [rsp+88h+ProviderId]; ProviderId
0x18000ed4f  movdqu  cs:xmmword_18001B028, xmm0
0x18000ed57  call    cs:__imp_EventRegister
0x18000ed5d  mov     ebx, eax
0x18000ed5f  test    eax, eax
0x18000ed61  jz      short loc_18000ED78
0x18000ed63  jle     short loc_18000ED6E
0x18000ed65  movzx   ebx, ax
0x18000ed68  or      ebx, 80070000h
0x18000ed6e  test    ebx, ebx
0x18000ed70  js      loc_18000EE1A
0x18000ed76  jmp     short loc_18000ED95
0x18000ed78  mov     r8, cs:off_18001B008
0x18000ed7f  mov     edx, 2
0x18000ed84  mov     rcx, cs:RegHandle
0x18000ed8b  movzx   r9d, word ptr [r8]
0x18000ed8f  call    cs:__imp_EventSetInformation
0x18000ed95  mov     eax, cs:dword_18001B000
0x18000ed9b  mov     cs:dword_18001BFA0, 1
0x18000eda5  cmp     eax, 5
0x18000eda8  jbe     short loc_18000EE1A
0x18000edaa  mov     rcx, cs:qword_18001B018
0x18000edb1  mov     rdx, 800000000000h
0x18000edbb  mov     rax, cs:qword_18001B010
0x18000edc2  test    rdx, rax
0x18000edc5  jz      short loc_18000EE1A
0x18000edc7  mov     rax, rcx
0x18000edca  and     rax, rdx
0x18000edcd  cmp     rax, rcx
0x18000edd0  jnz     short loc_18000EE1A
0x18000edd2  mov     eax, 80000000h
0x18000edd7  mov     [rsp+88h+var_20], 8
0x18000ede0  mov     qword ptr [rsp+88h+ProviderId.Data1], rax
0x18000ede5  lea     rdx, byte_1800173B7; int
0x18000edec  lea     rax, [rsp+88h+ProviderId]
0x18000edf1  xor     r9d, r9d; int
0x18000edf4  mov     [rsp+88h+var_28], rax
0x18000edf9  lea     rcx, dword_18001B000; int
0x18000ee00  lea     rax, [rsp+88h+var_48]
0x18000ee05  xor     r8d, r8d; int
0x18000ee08  mov     [rsp+88h+var_60], rax; PEVENT_DATA_DESCRIPTOR
0x18000ee0d  mov     [rsp+88h+var_68], 3; ULONG
0x18000ee15  call    _tlgWriteTransfer_EventWriteTransfer
0x18000ee1a  mov     eax, ebx
0x18000ee1c  mov     rcx, [rsp+88h+var_18]
0x18000ee21  xor     rcx, rsp; StackCookie
0x18000ee24  call    __security_check_cookie
0x18000ee29  add     rsp, 80h
0x18000ee30  pop     rbx
0x18000ee31  retn
```
