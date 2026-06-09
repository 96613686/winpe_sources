# NetSetupDevice::Uninstall(void)

- ea: `0x180050558`
- end: `0x1800505e4`
- name: `?Uninstall@NetSetupDevice@@QEAAXXZ`
- size: `140`
- prototype: `void __fastcall(NetSetupDevice *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x18004fea0`

## callees

- `0x180017814`
- `0x180050558`
- `0x1800505ec`
- `0x18005097c`
- `0x18005b034`
- `0x180065035`

## import_xrefs

- `api-ms-win-devices-config-l1-1-0!CM_Uninstall_DevNode` at `0x18005056d`
- `api-ms-win-devices-config-l1-1-0!CM_Uninstall_DevNode` at `0x18005056d`

## pseudocode

```c
void __fastcall NetSetupDevice::Uninstall(NetSetupDevice *this)
{
  unsigned int v2; // edx
  CONFIGRET v3; // ebx
  signed int v4; // eax
  _BYTE pExceptionObject[216]; // [rsp+20h] [rbp-D8h] BYREF

  NetSetupDevice::EnsureDeviceInstance(this);
  v3 = CM_Uninstall_DevNode(*(_DWORD *)this, 0);
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_dd4f85ff8caf3ef1f19e2c81dc211a8d_Traceguids, v3);
    v4 = My_CM_MapCrToWin32Err(v3, v2);
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    HResultException::HResultException((HResultException *)pExceptionObject, v4);
    throw (HResultException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180050558  push    rbx
0x18005055a  sub     rsp, 0F0h
0x180050561  mov     rbx, rcx
0x180050564  call    ?EnsureDeviceInstance@NetSetupDevice@@AEAAXXZ; NetSetupDevice::EnsureDeviceInstance(void)
0x180050569  mov     ecx, [rbx]; dnDevInst
0x18005056b  xor     edx, edx; ulFlags
0x18005056d  call    cs:__imp_CM_Uninstall_DevNode
0x180050573  mov     ebx, eax
0x180050575  test    eax, eax
0x180050577  jz      short loc_1800505DB
0x180050579  mov     rcx, cs:WPP_GLOBAL_Control
0x180050580  lea     rax, WPP_GLOBAL_Control
0x180050587  cmp     rcx, rax
0x18005058a  jz      short loc_1800505AA
0x18005058c  cmp     byte ptr [rcx+19h], 2
0x180050590  jb      short loc_1800505AA
0x180050592  mov     rcx, [rcx+10h]
0x180050596  lea     r8, WPP_dd4f85ff8caf3ef1f19e2c81dc211a8d_Traceguids
0x18005059d  mov     edx, 28h ; '('
0x1800505a2  mov     r9d, ebx
0x1800505a5  call    WPP_SF_d
0x1800505aa  mov     ecx, ebx; unsigned int
0x1800505ac  call    ?My_CM_MapCrToWin32Err@@YAKKK@Z; My_CM_MapCrToWin32Err(ulong,ulong)
0x1800505b1  test    eax, eax
0x1800505b3  jle     short loc_1800505BD
0x1800505b5  movzx   eax, ax
0x1800505b8  or      eax, 80070000h
0x1800505bd  mov     edx, eax; int
0x1800505bf  lea     rcx, [rsp+0F8h+pExceptionObject]; this
0x1800505c4  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x1800505c9  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x1800505d0  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x1800505d5  call    _CxxThrowException_0
0x1800505db  add     rsp, 0F0h
0x1800505e2  pop     rbx
0x1800505e3  retn
```
