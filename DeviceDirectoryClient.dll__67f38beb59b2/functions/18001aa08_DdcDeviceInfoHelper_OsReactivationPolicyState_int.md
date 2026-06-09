# DdcDeviceInfoHelper::OsReactivationPolicyState(int *)

- ea: `0x18001aa08`
- end: `0x18001aaa7`
- name: `?OsReactivationPolicyState@DdcDeviceInfoHelper@@CAJPEAH@Z`
- size: `159`
- prototype: `__int64 __fastcall(int *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016aa4`

## callees

- `0x18000310c`
- `0x1800050b8`
- `0x18001aa08`

## import_xrefs

- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18001aa76`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18001aa76`

## string_xrefs

- `0x18001aa3f`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`

## pseudocode

```c
__int64 __fastcall DdcDeviceInfoHelper::OsReactivationPolicyState(int *a1, int a2)
{
  int PolicyInt; // ebx
  int v5; // [rsp+40h] [rbp+8h] BYREF

  v5 = 0;
  if ( a1 )
  {
    PolicyInt = -2147467259;
    if ( (unsigned __int8)IsPolicyManager_GetPolicyIntPresent()
      && (PolicyInt = PolicyManager_GetPolicyInt(L"Licensing", L"AllowWindowsEntitlementReactivation", &v5),
          PolicyInt >= 0) )
    {
      *a1 = v5;
    }
    else
    {
      *a1 = -(PolicyInt != -2147024894) - 1;
      return 0;
    }
  }
  else
  {
    PolicyInt = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        130,
        "CPR(piPolicyState)");
  }
  return (unsigned int)PolicyInt;
}

```

## disassembly

```asm
0x18001aa08  mov     [rsp+arg_8], rbx
0x18001aa0d  push    rdi
0x18001aa0e  sub     rsp, 30h
0x18001aa12  mov     [rsp+38h+arg_0], 0
0x18001aa1a  mov     rdi, rcx
0x18001aa1d  test    rcx, rcx
0x18001aa20  jnz     short loc_18001AA55
0x18001aa22  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001aa29  mov     ebx, 80070057h
0x18001aa2e  jz      short loc_18001AA9A
0x18001aa30  lea     rax, aCprPipolicysta; "CPR(piPolicyState)"
0x18001aa37  mov     r8d, ebx
0x18001aa3a  mov     [rsp+38h+var_10], rax
0x18001aa3f  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001aa46  mov     [rsp+38h+var_18], 682h
0x18001aa4e  call    McTemplateU0dsqs_EventWriteTransfer
0x18001aa53  jmp     short loc_18001AA9A
0x18001aa55  mov     ebx, 80004005h
0x18001aa5a  call    IsPolicyManager_GetPolicyIntPresent
0x18001aa5f  test    al, al
0x18001aa61  jz      short loc_18001AA8A
0x18001aa63  lea     r8, [rsp+38h+arg_0]
0x18001aa68  lea     rdx, aAllowwindowsen; "AllowWindowsEntitlementReactivation"
0x18001aa6f  lea     rcx, aLicensing; "Licensing"
0x18001aa76  call    cs:__imp_PolicyManager_GetPolicyInt
0x18001aa7c  mov     ebx, eax
0x18001aa7e  test    eax, eax
0x18001aa80  js      short loc_18001AA8A
0x18001aa82  mov     ecx, [rsp+38h+arg_0]
0x18001aa86  mov     [rdi], ecx
0x18001aa88  jmp     short loc_18001AA9A
0x18001aa8a  sub     ebx, 80070002h
0x18001aa90  neg     ebx
0x18001aa92  sbb     eax, eax
0x18001aa94  dec     eax
0x18001aa96  mov     [rdi], eax
0x18001aa98  xor     ebx, ebx
0x18001aa9a  mov     eax, ebx
0x18001aa9c  mov     rbx, [rsp+38h+arg_8]
0x18001aaa1  add     rsp, 30h
0x18001aaa5  pop     rdi
0x18001aaa6  retn
```
