# Logger::TraceError(ushort const *,...)

- ea: `0x18000b3c4`
- end: `0x18000b442`
- name: `?TraceError@Logger@@SAJPEBGZZ`
- size: `126`
- prototype: `__int64(const unsigned __int16 *, ...)`
- caller_count: `22`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800064e0`
- `0x180007ef0`
- `0x180008360`
- `0x180008950`
- `0x180009010`
- `0x18000aa90`
- `0x18000ab5c`
- `0x18000ad2c`
- `0x18000ae60`
- `0x18000af7c`
- `0x18000afd0`
- `0x18000b08c`
- `0x180018f50`
- `0x180019024`
- `0x1800191fc`
- `0x1800193b4`
- `0x18001943c`
- `0x180019618`
- `0x1800197a0`
- `0x18001995c`
- `0x180019e18`
- `0x18001a0a4`

## callees

- `0x1800088f0`
- `0x18000b3c4`
- `0x180019a54`
- `0x180019d98`

## pseudocode

```c
__int64 Logger::TraceError(const unsigned __int16 *a1, ...)
{
  int v1; // ebx
  void *v3; // [rsp+20h] [rbp-18h] BYREF
  va_list va; // [rsp+48h] [rbp+10h] BYREF

  va_start(va, a1);
  v1 = 0;
  v3 = 0;
  if ( UserDeviceRegistrationEventProvider_Context )
  {
    v1 = Logger::FormatString((unsigned __int16 **)&v3, a1, va);
    if ( v1 >= 0 )
    {
      if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 0x20) != 0 )
        v1 = McTemplateU0z_EventWriteTransfer(&UserDeviceRegistrationEventProvider_Context, ErrorDebugEvent, v3);
      else
        v1 = 0;
    }
  }
  SafeFree(v3);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18000b3c4  mov     rax, rsp
0x18000b3c7  mov     [rax+8], rcx
0x18000b3cb  mov     [rax+10h], rdx
0x18000b3cf  mov     [rax+18h], r8
0x18000b3d3  mov     [rax+20h], r9
0x18000b3d7  push    rbx
0x18000b3d8  sub     rsp, 30h
0x18000b3dc  xor     ebx, ebx
0x18000b3de  mov     qword ptr [rax-18h], 0
0x18000b3e6  cmp     cs:UserDeviceRegistrationEventProvider_Context, rbx
0x18000b3ed  lea     r8, [rax+10h]; char *
0x18000b3f1  mov     [rax-18h], rbx
0x18000b3f5  jz      short loc_18000B430
0x18000b3f7  mov     rdx, rcx; unsigned __int16 *
0x18000b3fa  lea     rcx, [rax-18h]; unsigned __int16 **
0x18000b3fe  call    ?FormatString@Logger@@CAJAEAPEAGPEBGPEAD@Z; Logger::FormatString(ushort * &,ushort const *,char *)
0x18000b403  mov     ebx, eax
0x18000b405  test    eax, eax
0x18000b407  js      short loc_18000B430
0x18000b409  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 20h
0x18000b410  jz      short loc_18000B42E
0x18000b412  mov     r8, [rsp+38h+var_18]
0x18000b417  lea     rdx, ErrorDebugEvent
0x18000b41e  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x18000b425  call    McTemplateU0z_EventWriteTransfer
0x18000b42a  mov     ebx, eax
0x18000b42c  jmp     short loc_18000B430
0x18000b42e  xor     ebx, ebx
0x18000b430  mov     rcx, [rsp+38h+var_18]; void *
0x18000b435  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000b43a  mov     eax, ebx
0x18000b43c  add     rsp, 30h
0x18000b440  pop     rbx
0x18000b441  retn
```
