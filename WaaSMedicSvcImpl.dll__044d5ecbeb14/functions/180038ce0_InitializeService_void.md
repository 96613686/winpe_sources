# InitializeService(void *)

- ea: `0x180038ce0`
- end: `0x180038d8a`
- name: `?InitializeService@@YAJPEAX@Z`
- size: `170`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180038f10`

## callees

- `0x18002e81c`
- `0x18003832c`
- `0x180038ce0`

## import_xrefs

- `combase!__imp_CoGetSharedServiceId` at `0x180038d1c`
- `combase!__imp_CoGetSharedServiceId` at `0x180038d1c`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180038d39`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180038d39`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180038cf7`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180038cf7`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180038d72`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180038d72`

## string_xrefs

- `0x180038d59`: `Failed to create and register class factory. hr = 0x%08x`
- `0x180038d28`: `Failed to get shared service id. hr = 0x%08x`

## pseudocode

```c
__int64 __fastcall InitializeService(void *a1)
{
  int v2; // eax
  int v3; // ebx
  unsigned int v4; // edi
  int SharedServiceId; // eax
  const unsigned __int16 *v6; // rdx

  v2 = RoInitialize(1);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = v2;
    LogLevelW(2u, L"Call to RoInitialize failed. hr = 0x%08x", (unsigned int)v2);
    goto LABEL_10;
  }
  SharedServiceId = CoGetSharedServiceId(&dword_1800A5690);
  v4 = SharedServiceId;
  if ( SharedServiceId >= 0 )
  {
    SharedServiceId = CoRegisterServerShutdownDelay(a1, 60000);
    v4 = SharedServiceId;
    if ( SharedServiceId >= 0 )
    {
      SharedServiceId = CreateAndRegisterClassFactory();
      v4 = SharedServiceId;
      if ( SharedServiceId >= 0 )
        goto LABEL_10;
      v6 = L"Failed to create and register class factory. hr = 0x%08x";
    }
    else
    {
      v6 = L"Failed to register server shutdown delay. hr = 0x%08x";
    }
  }
  else
  {
    v6 = L"Failed to get shared service id. hr = 0x%08x";
  }
  LogLevelW(2u, v6, (unsigned int)SharedServiceId);
LABEL_10:
  if ( v3 >= 0 )
    RoUninitialize();
  return v4;
}

```

## disassembly

```asm
0x180038ce0  mov     [rsp+arg_0], rbx
0x180038ce5  mov     [rsp+arg_10], rsi
0x180038cea  push    rdi
0x180038ceb  sub     rsp, 20h
0x180038cef  mov     rsi, rcx
0x180038cf2  mov     ecx, 1
0x180038cf7  call    cs:__imp_RoInitialize
0x180038cfd  mov     ebx, eax
0x180038cff  mov     [rsp+28h+arg_8], eax
0x180038d03  test    eax, eax
0x180038d05  jns     short loc_180038D15
0x180038d07  mov     edi, eax
0x180038d09  mov     r8d, eax
0x180038d0c  lea     rdx, aCallToRoinitia; "Call to RoInitialize failed. hr = 0x%08"...
0x180038d13  jmp     short loc_180038D63
0x180038d15  lea     rcx, dword_1800A5690
0x180038d1c  call    cs:__imp_CoGetSharedServiceId
0x180038d22  mov     edi, eax
0x180038d24  test    eax, eax
0x180038d26  jns     short loc_180038D31
0x180038d28  lea     rdx, aFailedToGetSha; "Failed to get shared service id. hr = 0"...
0x180038d2f  jmp     short loc_180038D60
0x180038d31  mov     edx, 0EA60h
0x180038d36  mov     rcx, rsi
0x180038d39  call    cs:__imp_CoRegisterServerShutdownDelay
0x180038d3f  mov     edi, eax
0x180038d41  test    eax, eax
0x180038d43  jns     short loc_180038D4E
0x180038d45  lea     rdx, aFailedToRegist_0; "Failed to register server shutdown dela"...
0x180038d4c  jmp     short loc_180038D60
0x180038d4e  call    ?CreateAndRegisterClassFactory@@YAJXZ; CreateAndRegisterClassFactory(void)
0x180038d53  mov     edi, eax
0x180038d55  test    eax, eax
0x180038d57  jns     short loc_180038D6E
0x180038d59  lea     rdx, aFailedToCreate_18; "Failed to create and register class fac"...
0x180038d60  mov     r8d, eax
0x180038d63  mov     ecx, 2; unsigned __int8
0x180038d68  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180038d6d  nop
0x180038d6e  test    ebx, ebx
0x180038d70  js      short loc_180038D78
0x180038d72  call    cs:__imp_RoUninitialize
0x180038d78  mov     eax, edi
0x180038d7a  mov     rbx, [rsp+28h+arg_0]
0x180038d7f  mov     rsi, [rsp+28h+arg_10]
0x180038d84  add     rsp, 20h
0x180038d88  pop     rdi
0x180038d89  retn
```
