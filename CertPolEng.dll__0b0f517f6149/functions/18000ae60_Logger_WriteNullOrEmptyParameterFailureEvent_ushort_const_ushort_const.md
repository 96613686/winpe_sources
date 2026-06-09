# Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)

- ea: `0x18000ae60`
- end: `0x18000aeb6`
- name: `?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z`
- size: `86`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `13`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800064e0`
- `0x180007ef0`
- `0x180008360`
- `0x180008950`
- `0x180009010`
- `0x18000ad2c`
- `0x18000afd0`
- `0x1800191fc`
- `0x18001943c`
- `0x180019618`
- `0x1800197a0`
- `0x180019e18`
- `0x18001a0a4`

## callees

- `0x18000ae60`
- `0x18000aebc`
- `0x18000b3c4`

## string_xrefs

- `0x18000ae8a`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x18000ae83`: `EventWriteNullOrEmptyParameterFailureEvent`

## pseudocode

```c
__int64 __fastcall Logger::WriteNullOrEmptyParameterFailureEvent(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2)
{
  unsigned int v2; // eax
  int v3; // ebx

  if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
  {
    v2 = McTemplateU0zz_EventWriteTransfer(a1, a2, a1, a2);
    v3 = v2;
    if ( v2 )
    {
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"Logger::WriteNullOrEmptyParameterFailureEvent",
        L"EventWriteNullOrEmptyParameterFailureEvent",
        v2);
      if ( v3 > 0 )
        return (unsigned __int16)v3 | 0x80070000;
    }
  }
  else
  {
    return 0;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000ae60  push    rbx
0x18000ae62  sub     rsp, 20h
0x18000ae66  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x18000ae6d  jz      short loc_18000AEAC
0x18000ae6f  mov     r9, rdx
0x18000ae72  mov     r8, rcx
0x18000ae75  call    McTemplateU0zz_EventWriteTransfer
0x18000ae7a  mov     ebx, eax
0x18000ae7c  test    eax, eax
0x18000ae7e  jz      short loc_18000AEAE
0x18000ae80  mov     r9d, eax
0x18000ae83  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x18000ae8a  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x18000ae91  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000ae98  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000ae9d  test    ebx, ebx
0x18000ae9f  jle     short loc_18000AEAE
0x18000aea1  movzx   ebx, bx
0x18000aea4  or      ebx, 80070000h
0x18000aeaa  jmp     short loc_18000AEAE
0x18000aeac  xor     ebx, ebx
0x18000aeae  mov     eax, ebx
0x18000aeb0  add     rsp, 20h
0x18000aeb4  pop     rbx
0x18000aeb5  retn
```
