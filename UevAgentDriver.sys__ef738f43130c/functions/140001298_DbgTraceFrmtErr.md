# DbgTraceFrmtErr

- ea: `0x140001298`
- end: `0x140001371`
- name: `DbgTraceFrmtErr`
- size: `217`
- prototype: `ULONG(char *Format, ...)`
- caller_count: `13`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400016ac`
- `0x14000a120`
- `0x14000a284`
- `0x14000a55c`
- `0x14000aca0`
- `0x14000aec4`
- `0x14000b160`
- `0x14000b418`
- `0x14000b614`
- `0x14000c078`
- `0x14000c1bc`
- `0x14000c55c`
- `0x14000c614`

## callees

- `0x140001298`
- `0x140001544`
- `0x140001a30`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140001326`
- `ntoskrnl!DbgPrintEx` at `0x140001326`
- `ntoskrnl!_vsnprintf` at `0x1400012de`
- `ntoskrnl!_vsnprintf` at `0x1400012de`

## pseudocode

```c
ULONG DbgTraceFrmtErr(char *Format, ...)
{
  ULONG result; // eax
  __int64 v2; // rcx
  __int64 v3; // r8
  char Dest[511]; // [rsp+30h] [rbp-218h] BYREF
  char v5; // [rsp+22Fh] [rbp-19h]
  __int64 v6; // [rsp+258h] [rbp+10h] BYREF
  va_list va; // [rsp+258h] [rbp+10h]
  __int64 v8; // [rsp+260h] [rbp+18h]
  va_list va1; // [rsp+268h] [rbp+20h] BYREF

  va_start(va1, Format);
  va_start(va, Format);
  v6 = va_arg(va1, _QWORD);
  v8 = va_arg(va1, _QWORD);
  result = _vsnprintf(Dest, 0x1FFu, Format, va);
  if ( result >= 0x200 )
  {
    v5 = 0;
    if ( (Microsoft_User_Experience_Virtualization_Agent_DriverEnableBits & 4) != 0 )
      return McTemplateK0s_EtwWriteTransfer(
               v2,
               Trace_Error,
               v3,
               "StringCchPrintfA() in DbgTraceFrmtErr() failed: Insufficient buffer");
  }
  else
  {
    if ( result == 511 )
      v5 = 0;
    if ( (Microsoft_User_Experience_Virtualization_Agent_DriverEnableBits & 4) != 0 )
      McTemplateK0s_EtwWriteTransfer(v2, Trace_Error, v3, Dest);
    return DbgPrintEx(0x4Du, 2u, Dest);
  }
  return result;
}

```

## disassembly

```asm
0x140001298  mov     r11, rsp
0x14000129b  mov     [r11+8], rcx
0x14000129f  mov     [r11+10h], rdx
0x1400012a3  mov     [r11+18h], r8
0x1400012a7  mov     [r11+20h], r9
0x1400012ab  sub     rsp, 248h
0x1400012b2  mov     rax, cs:__security_cookie
0x1400012b9  xor     rax, rsp
0x1400012bc  mov     [rsp+248h+var_18], rax
0x1400012c4  mov     r8, rcx; Format
0x1400012c7  mov     [rsp+248h+var_228], 0
0x1400012d0  lea     rcx, [rsp+248h+Dest]; Dest
0x1400012d5  mov     edx, 1FFh; Count
0x1400012da  lea     r9, [r11+10h]; Args
0x1400012de  call    cs:__imp__vsnprintf
0x1400012e5  nop     dword ptr [rax+rax+00h]
0x1400012ea  test    eax, eax
0x1400012ec  js      short loc_140001334
0x1400012ee  cmp     eax, 1FFh
0x1400012f3  ja      short loc_140001334
0x1400012f5  jnz     short loc_1400012FF
0x1400012f7  mov     [rsp+248h+var_19], 0
0x1400012ff  test    cs:Microsoft_User_Experience_Virtualization_Agent_DriverEnableBits, 4
0x140001306  jz      short loc_140001319
0x140001308  lea     r9, [rsp+248h+Dest]
0x14000130d  lea     rdx, Trace_Error
0x140001314  call    McTemplateK0s_EtwWriteTransfer
0x140001319  mov     edx, 2; Level
0x14000131e  lea     r8, [rsp+248h+Dest]; Format
0x140001323  lea     ecx, [rdx+4Bh]; ComponentId
0x140001326  call    cs:__imp_DbgPrintEx
0x14000132d  nop     dword ptr [rax+rax+00h]
0x140001332  jmp     short loc_140001358
0x140001334  test    cs:Microsoft_User_Experience_Virtualization_Agent_DriverEnableBits, 4
0x14000133b  mov     [rsp+248h+var_19], 0
0x140001343  jz      short loc_140001358
0x140001345  lea     r9, aStringcchprint; "StringCchPrintfA() in DbgTraceFrmtErr()"...
0x14000134c  lea     rdx, Trace_Error
0x140001353  call    McTemplateK0s_EtwWriteTransfer
0x140001358  mov     rcx, [rsp+248h+var_18]
0x140001360  xor     rcx, rsp; StackCookie
0x140001363  call    __security_check_cookie
0x140001368  add     rsp, 248h
0x14000136f  retn
```
