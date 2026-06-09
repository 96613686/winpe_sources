# Windows::UI::Input::InjectionBrokerImpl::UninitializePenInjection(unsigned __int64)

- ea: `0x180007340`
- end: `0x180007372`
- name: `?UninitializePenInjection@InjectionBrokerImpl@Input@UI@Windows@@UEAAJ_K@Z`
- size: `50`
- prototype: `__int64 __fastcall(Windows::UI::Input::InjectionBrokerImpl *this, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007340`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007355`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007355`
- `ext-ms-win-ntuser-rim-l1-1-0!RemoveInjectionDevice` at `0x18000734b`
- `ext-ms-win-ntuser-rim-l1-1-0!RemoveInjectionDevice` at `0x18000734b`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::InjectionBrokerImpl::UninitializePenInjection(
        Windows::UI::Input::InjectionBrokerImpl *this,
        __int64 a2)
{
  unsigned int v2; // ebx
  signed int LastError; // eax

  v2 = 0;
  if ( !(unsigned int)RemoveInjectionDevice(a2) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v2;
}

```

## disassembly

```asm
0x180007340  push    rbx
0x180007342  sub     rsp, 20h
0x180007346  mov     rcx, rdx
0x180007349  xor     ebx, ebx
0x18000734b  call    cs:__imp_RemoveInjectionDevice
0x180007351  test    eax, eax
0x180007353  jnz     short loc_18000736A
0x180007355  call    cs:__imp_GetLastError
0x18000735b  mov     ebx, eax
0x18000735d  test    eax, eax
0x18000735f  jle     short loc_18000736A
0x180007361  movzx   ebx, ax
0x180007364  or      ebx, 80070000h
0x18000736a  mov     eax, ebx
0x18000736c  add     rsp, 20h
0x180007370  pop     rbx
0x180007371  retn
```
