# DdcDeviceInfoHelper::DeviceBatteryCapable(int *)

- ea: `0x180014b14`
- end: `0x180014c0d`
- name: `?DeviceBatteryCapable@DdcDeviceInfoHelper@@SAJPEAH@Z`
- size: `249`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180016aa4`

## callees

- `0x1800024c0`
- `0x180002fc0`
- `0x1800050b8`
- `0x180014b14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b99`
- `api-ms-win-power-base-l1-1-0!GetPwrCapabilities` at `0x180014b8f`
- `api-ms-win-power-base-l1-1-0!GetPwrCapabilities` at `0x180014b8f`

## string_xrefs

- `0x180014b73`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`

## pseudocode

```c
__int64 __fastcall DdcDeviceInfoHelper::DeviceBatteryCapable(int *a1)
{
  int v2; // edx
  int v3; // ecx
  unsigned int v4; // ebx
  signed int LastError; // eax
  int v6; // edx
  int v7; // ecx
  BOOL v8; // eax
  _SYSTEM_POWER_CAPABILITIES spc; // [rsp+30h] [rbp-68h] BYREF

  memset_0(&spc, 0, sizeof(spc));
  if ( a1 )
  {
    *a1 = 0;
    if ( GetPwrCapabilities(&spc) )
    {
      v4 = 0;
      v8 = spc.SystemBatteriesPresent || spc.UpsPresent;
      *a1 = v8;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v7,
          v6,
          v4,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          186,
          "CBR(GetPwrCapabilities(&spc) != 0)");
    }
  }
  else
  {
    v4 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v3,
        v2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        183,
        "CPR(pfCapable)");
  }
  return v4;
}

```

## disassembly

```asm
0x180014b14  mov     [rsp+arg_8], rbx
0x180014b19  push    rdi
0x180014b1a  sub     rsp, 90h
0x180014b21  mov     rax, cs:__security_cookie
0x180014b28  xor     rax, rsp
0x180014b2b  mov     [rsp+98h+var_18], rax
0x180014b33  xor     edx, edx; Val
0x180014b35  mov     rdi, rcx
0x180014b38  lea     rcx, [rsp+98h+spc]; void *
0x180014b3d  lea     r8d, [rdx+4Ch]; Size
0x180014b41  call    memset_0
0x180014b46  test    rdi, rdi
0x180014b49  jnz     short loc_180014B84
0x180014b4b  lea     eax, [rdi+1]
0x180014b4e  mov     ebx, 80070057h
0x180014b53  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, al
0x180014b59  jz      loc_180014BEA
0x180014b5f  lea     rax, aCprPfcapable; "CPR(pfCapable)"
0x180014b66  mov     [rsp+98h+var_70], rax
0x180014b6b  mov     [rsp+98h+var_78], 3B7h
0x180014b73  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180014b7a  mov     r8d, ebx
0x180014b7d  call    McTemplateU0dsqs_EventWriteTransfer
0x180014b82  jmp     short loc_180014BEA
0x180014b84  lea     rcx, [rsp+98h+spc]; lpspc
0x180014b89  mov     dword ptr [rdi], 0
0x180014b8f  call    cs:__imp_GetPwrCapabilities
0x180014b95  test    al, al
0x180014b97  jnz     short loc_180014BD1
0x180014b99  call    cs:__imp_GetLastError
0x180014b9f  mov     ebx, eax
0x180014ba1  test    eax, eax
0x180014ba3  jle     short loc_180014BAE
0x180014ba5  movzx   ebx, ax
0x180014ba8  or      ebx, 80070000h
0x180014bae  mov     eax, 1
0x180014bb3  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, al
0x180014bb9  jz      short loc_180014BEA
0x180014bbb  lea     rax, aCbrGetpwrcapab; "CBR(GetPwrCapabilities(&spc) != 0)"
0x180014bc2  mov     [rsp+98h+var_70], rax
0x180014bc7  mov     [rsp+98h+var_78], 3BAh
0x180014bcf  jmp     short loc_180014B73
0x180014bd1  xor     ebx, ebx
0x180014bd3  cmp     [rsp+98h+spc.SystemBatteriesPresent], bl
0x180014bd7  jnz     short loc_180014BE3
0x180014bd9  cmp     [rsp+98h+spc.UpsPresent], bl
0x180014bdd  jnz     short loc_180014BE3
0x180014bdf  xor     eax, eax
0x180014be1  jmp     short loc_180014BE8
0x180014be3  mov     eax, 1
0x180014be8  mov     [rdi], eax
0x180014bea  mov     eax, ebx
0x180014bec  mov     rcx, [rsp+98h+var_18]
0x180014bf4  xor     rcx, rsp; StackCookie
0x180014bf7  call    __security_check_cookie
0x180014bfc  mov     rbx, [rsp+98h+arg_8]
0x180014c04  add     rsp, 90h
0x180014c0b  pop     rdi
0x180014c0c  retn
```
