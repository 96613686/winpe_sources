# Logger::WriteRegistryFailureEventEx(ulong,ushort const *,ushort const *,...)

- ea: `0x18000aa90`
- end: `0x18000ab55`
- name: `?WriteRegistryFailureEventEx@Logger@@SAJKPEBG0ZZ`
- size: `197`
- prototype: `__int64(int, const unsigned __int16 *, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019c88`

## callees

- `0x1800088f0`
- `0x18000aa90`
- `0x18000b3c4`
- `0x180019a54`
- `0x180019cc0`

## string_xrefs

- `0x18000aae0`: `Logger::WriteRegistryFailureEventEx`
- `0x18000ab1e`: `Logger::WriteRegistryFailureEventEx`
- `0x18000ab17`: `EventWriteRegistryFailureEvent`

## pseudocode

```c
__int64 Logger::WriteRegistryFailureEventEx(int a1, const unsigned __int16 *a2, const unsigned __int16 *a3, ...)
{
  int v3; // edi
  int v5; // eax
  int v6; // edx
  int v7; // ecx
  void *v8; // rsi
  unsigned int v9; // ebx
  unsigned int v10; // eax
  int v11; // edi
  void *v13[7]; // [rsp+30h] [rbp-38h] BYREF
  va_list va; // [rsp+88h] [rbp+20h] BYREF

  va_start(va, a3);
  v13[0] = 0;
  v3 = (int)a2;
  v13[1] = 0;
  v5 = Logger::FormatString((unsigned __int16 **)v13, a3, va);
  v8 = v13[0];
  v9 = v5;
  if ( v5 >= 0 )
  {
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 1) != 0 )
    {
      v10 = McTemplateU0qzz_EventWriteTransfer(v7, v6, a1, v3, (__int64)v13[0]);
      v11 = v10;
      if ( v10 )
      {
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteRegistryFailureEventEx",
          L"EventWriteRegistryFailureEvent",
          v10);
        if ( v11 > 0 )
          v9 = (unsigned __int16)v11 | 0x80070000;
        else
          v9 = v11;
      }
    }
  }
  else
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"Logger::WriteRegistryFailureEventEx",
      L"FormatString",
      (unsigned int)v5);
  }
  SafeFree(v8);
  return v9;
}

```

## disassembly

```asm
0x18000aa90  mov     r11, rsp
0x18000aa93  mov     [r11+18h], r8
0x18000aa97  mov     [r11+20h], r9
0x18000aa9b  push    rbx
0x18000aa9c  push    rbp
0x18000aa9d  push    rsi
0x18000aa9e  push    rdi
0x18000aa9f  sub     rsp, 48h
0x18000aaa3  mov     rax, r8
0x18000aaa6  mov     qword ptr [r11-38h], 0
0x18000aaae  mov     rdi, rdx
0x18000aab1  mov     qword ptr [r11-30h], 0
0x18000aab9  mov     ebp, ecx
0x18000aabb  lea     r8, [r11+20h]; char *
0x18000aabf  mov     rdx, rax; unsigned __int16 *
0x18000aac2  lea     rcx, [r11-38h]; unsigned __int16 **
0x18000aac6  call    ?FormatString@Logger@@CAJAEAPEAGPEBGPEAD@Z; Logger::FormatString(ushort * &,ushort const *,char *)
0x18000aacb  mov     rsi, [rsp+68h+var_38]
0x18000aad0  mov     ebx, eax
0x18000aad2  test    eax, eax
0x18000aad4  jns     short loc_18000AAF5
0x18000aad6  mov     r9d, eax
0x18000aad9  lea     r8, aFormatstring; "FormatString"
0x18000aae0  lea     rdx, aLoggerWritereg; "Logger::WriteRegistryFailureEventEx"
0x18000aae7  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x18000aaee  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000aaf3  jmp     short loc_18000AB42
0x18000aaf5  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 1
0x18000aafc  jz      short loc_18000AB42
0x18000aafe  mov     r9, rdi
0x18000ab01  mov     [rsp+68h+var_48], rsi
0x18000ab06  mov     r8d, ebp
0x18000ab09  call    McTemplateU0qzz_EventWriteTransfer
0x18000ab0e  mov     edi, eax
0x18000ab10  test    eax, eax
0x18000ab12  jz      short loc_18000AB42
0x18000ab14  mov     r9d, eax
0x18000ab17  lea     r8, aEventwriteregi; "EventWriteRegistryFailureEvent"
0x18000ab1e  lea     rdx, aLoggerWritereg; "Logger::WriteRegistryFailureEventEx"
0x18000ab25  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000ab2c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000ab31  test    edi, edi
0x18000ab33  jg      short loc_18000AB39
0x18000ab35  mov     ebx, edi
0x18000ab37  jmp     short loc_18000AB42
0x18000ab39  movzx   ebx, di
0x18000ab3c  or      ebx, 80070000h
0x18000ab42  mov     rcx, rsi; void *
0x18000ab45  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000ab4a  mov     eax, ebx
0x18000ab4c  add     rsp, 48h
0x18000ab50  pop     rdi
0x18000ab51  pop     rsi
0x18000ab52  pop     rbp
0x18000ab53  pop     rbx
0x18000ab54  retn
```
