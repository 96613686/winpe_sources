# NetSetupDevice::IsDeviceInstalled(wchar_t const *)

- ea: `0x180005edc`
- end: `0x180005fb3`
- name: `?IsDeviceInstalled@NetSetupDevice@@SA_NPEB_W@Z`
- size: `215`
- prototype: `char __fastcall(DEVINSTID_W pDeviceID)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180006af8`

## callees

- `0x180005edc`
- `0x180006360`
- `0x180006608`
- `0x18000895c`
- `0x18000fbfc`
- `0x1800119f0`

## import_xrefs

- `api-ms-win-devices-config-l1-1-0!CM_Locate_DevNodeW` at `0x180005f15`
- `api-ms-win-devices-config-l1-1-0!CM_Locate_DevNodeW` at `0x180005f15`

## pseudocode

```c
char __fastcall NetSetupDevice::IsDeviceInstalled(DEVINSTID_W pDeviceID)
{
  int v1; // edi
  unsigned int v2; // edx
  CONFIGRET v3; // ebx
  signed int v5; // eax
  _BYTE pExceptionObject[208]; // [rsp+30h] [rbp-E8h] BYREF
  DEVNODE v7; // [rsp+100h] [rbp-18h] BYREF

  v1 = (int)pDeviceID;
  v7 = 0;
  v3 = CM_Locate_DevNodeW(&v7, pDeviceID, 1u);
  if ( v3 == 13 )
    return 0;
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)WPP_dd4f85ff8caf3ef1f19e2c81dc211a8d_Traceguids,
        v1,
        v3);
    v5 = My_CM_MapCrToWin32Err(v3, v2);
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    HResultException::HResultException((HResultException *)pExceptionObject, v5);
    throw (HResultException *)pExceptionObject;
  }
  return 1;
}

```

## disassembly

```asm
0x180005edc  mov     r11, rsp
0x180005edf  mov     [r11+10h], rbx
0x180005ee3  push    rdi
0x180005ee4  sub     rsp, 110h
0x180005eeb  mov     rax, cs:__security_cookie
0x180005ef2  xor     rax, rsp
0x180005ef5  mov     [rsp+118h+var_10], rax
0x180005efd  mov     rdi, rcx
0x180005f00  mov     dword ptr [r11-18h], 0
0x180005f08  mov     rdx, rcx; pDeviceID
0x180005f0b  mov     r8d, 1; ulFlags
0x180005f11  lea     rcx, [r11-18h]; pdnDevInst
0x180005f15  call    cs:__imp_CM_Locate_DevNodeW
0x180005f1b  mov     ebx, eax
0x180005f1d  cmp     eax, 0Dh
0x180005f20  jnz     short loc_180005F26
0x180005f22  xor     al, al
0x180005f24  jmp     short loc_180005F92
0x180005f26  test    ebx, ebx
0x180005f28  jz      short loc_180005F90
0x180005f2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f31  lea     rax, WPP_GLOBAL_Control
0x180005f38  cmp     rcx, rax
0x180005f3b  jz      short loc_180005F5F
0x180005f3d  cmp     byte ptr [rcx+19h], 2
0x180005f41  jb      short loc_180005F5F
0x180005f43  mov     rcx, [rcx+10h]
0x180005f47  lea     r8, WPP_dd4f85ff8caf3ef1f19e2c81dc211a8d_Traceguids
0x180005f4e  mov     edx, 0Ah
0x180005f53  mov     [rsp+118h+var_F8], ebx
0x180005f57  mov     r9, rdi
0x180005f5a  call    WPP_SF_SD
0x180005f5f  mov     ecx, ebx; unsigned int
0x180005f61  call    ?My_CM_MapCrToWin32Err@@YAKKK@Z; My_CM_MapCrToWin32Err(ulong,ulong)
0x180005f66  test    eax, eax
0x180005f68  jle     short loc_180005F72
0x180005f6a  movzx   eax, ax
0x180005f6d  or      eax, 80070000h
0x180005f72  mov     edx, eax; int
0x180005f74  lea     rcx, [rsp+118h+pExceptionObject]; this
0x180005f79  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180005f7e  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180005f85  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x180005f8a  call    _CxxThrowException_0
0x180005f90  mov     al, 1
0x180005f92  mov     rcx, [rsp+118h+var_10]
0x180005f9a  xor     rcx, rsp; StackCookie
0x180005f9d  call    __security_check_cookie
0x180005fa2  mov     rbx, [rsp+118h+arg_8]
0x180005faa  add     rsp, 110h
0x180005fb1  pop     rdi
0x180005fb2  retn
```
