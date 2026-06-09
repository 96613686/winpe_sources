# DdcDeviceInfoHelper::FmdDisabledByPolicy(int *)

- ea: `0x18001505c`
- end: `0x180015118`
- name: `?FmdDisabledByPolicy@DdcDeviceInfoHelper@@SAJPEAH@Z`
- size: `188`
- prototype: `__int64 __fastcall(int *, int)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005b34`
- `0x1800063f4`
- `0x180006da4`
- `0x18000c034`
- `0x18000ca4c`

## callees

- `0x1800050b8`
- `0x18001505c`

## import_xrefs

- `MdmCommon!MdmIsFindMyDeviceEnabled` at `0x1800150c3`
- `MdmCommon!MdmIsFindMyDeviceEnabled` at `0x1800150c3`

## string_xrefs

- `0x1800150a2`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`

## pseudocode

```c
__int64 __fastcall DdcDeviceInfoHelper::FmdDisabledByPolicy(int *a1, int a2)
{
  int MyDeviceEnabled; // ebx
  int v4; // edx
  int v5; // ecx
  BOOL v6; // eax
  int v8; // [rsp+40h] [rbp+8h] BYREF
  int v9; // [rsp+48h] [rbp+10h] BYREF

  v9 = 0;
  v8 = 0;
  if ( a1 )
  {
    *a1 = 0;
    MyDeviceEnabled = MdmIsFindMyDeviceEnabled(&v8, &v9);
    if ( MyDeviceEnabled >= 0 )
    {
      v6 = !v8 && v9;
      *a1 = v6;
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v5,
        v4,
        MyDeviceEnabled,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        129,
        "CHR(hr)");
    }
  }
  else
  {
    MyDeviceEnabled = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        125,
        "CPR(pfFmdDisabledByPolicy)");
  }
  return (unsigned int)MyDeviceEnabled;
}

```

## disassembly

```asm
0x18001505c  mov     [rsp+arg_10], rbx
0x180015061  push    rdi
0x180015062  sub     rsp, 30h
0x180015066  mov     [rsp+38h+arg_8], 0
0x18001506e  mov     rdi, rcx
0x180015071  mov     [rsp+38h+arg_0], 0
0x180015079  test    rcx, rcx
0x18001507c  jnz     short loc_1800150B3
0x18001507e  lea     eax, [rcx+1]
0x180015081  mov     ebx, 80070057h
0x180015086  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, al
0x18001508c  jz      short loc_18001510B
0x18001508e  lea     rax, aCprPffmddisabl; "CPR(pfFmdDisabledByPolicy)"
0x180015095  mov     [rsp+38h+var_10], rax
0x18001509a  mov     [rsp+38h+var_18], 37Dh
0x1800150a2  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800150a9  mov     r8d, ebx
0x1800150ac  call    McTemplateU0dsqs_EventWriteTransfer
0x1800150b1  jmp     short loc_18001510B
0x1800150b3  mov     dword ptr [rcx], 0
0x1800150b9  lea     rdx, [rsp+38h+arg_8]
0x1800150be  lea     rcx, [rsp+38h+arg_0]
0x1800150c3  call    cs:__imp_?MdmIsFindMyDeviceEnabled@@YAJPEAH0@Z; MdmIsFindMyDeviceEnabled(int *,int *)
0x1800150c9  mov     ebx, eax
0x1800150cb  test    eax, eax
0x1800150cd  jns     short loc_1800150F2
0x1800150cf  mov     eax, 1
0x1800150d4  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, al
0x1800150da  jz      short loc_18001510B
0x1800150dc  lea     rax, aChrHr; "CHR(hr)"
0x1800150e3  mov     [rsp+38h+var_10], rax
0x1800150e8  mov     [rsp+38h+var_18], 381h
0x1800150f0  jmp     short loc_1800150A2
0x1800150f2  cmp     [rsp+38h+arg_0], 0
0x1800150f7  jnz     short loc_180015107
0x1800150f9  cmp     [rsp+38h+arg_8], 0
0x1800150fe  jz      short loc_180015107
0x180015100  mov     eax, 1
0x180015105  jmp     short loc_180015109
0x180015107  xor     eax, eax
0x180015109  mov     [rdi], eax
0x18001510b  mov     eax, ebx
0x18001510d  mov     rbx, [rsp+38h+arg_10]
0x180015112  add     rsp, 30h
0x180015116  pop     rdi
0x180015117  retn
```
