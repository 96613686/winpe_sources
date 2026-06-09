# NetSetupDevice::OpenDeviceKey(ulong,void *,NetSetupDevice::DeviceKeyFailPolicy,ulong,ulong)

- ea: `0x180006208`
- end: `0x180006359`
- name: `?OpenDeviceKey@NetSetupDevice@@AEAA?AVRegistryKey@@KPEAXW4DeviceKeyFailPolicy@1@KK@Z`
- size: `337`
- prototype: `RegistryKey *__fastcall(NetSetupDevice *, RegistryKey *, REGSAM, char *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x180006af8`

## callees

- `0x180005308`
- `0x180005328`
- `0x180005fbc`
- `0x180006208`
- `0x180006360`
- `0x180006608`
- `0x18000895c`
- `0x18000fa94`
- `0x1800102e8`
- `0x1800119f0`

## import_xrefs

- `api-ms-win-devices-config-l1-1-0!CM_Open_DevNode_Key` at `0x180006271`
- `api-ms-win-devices-config-l1-1-0!CM_Open_DevNode_Key` at `0x180006271`

## pseudocode

```c
RegistryKey *__fastcall NetSetupDevice::OpenDeviceKey(NetSetupDevice *a1, RegistryKey *a2, REGSAM a3, char *a4)
{
  CONFIGRET v8; // ebx
  int v9; // eax
  HKEY *v10; // rax
  __int64 v11; // r8
  HKEY v13[3]; // [rsp+40h] [rbp-128h] BYREF
  _BYTE pExceptionObject[208]; // [rsp+58h] [rbp-110h] BYREF
  HKEY phkDevice; // [rsp+128h] [rbp-40h] BYREF

  v13[2] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  v13[0] = (HKEY)a2;
  phkDevice = 0;
  NetSetupDevice::EnsureDeviceInstance(a1);
  v8 = CM_Open_DevNode_Key(*(_DWORD *)a1, a3, 0, 1u, &phkDevice, 1u);
  if ( v8 == 46 )
  {
    *(_QWORD *)a2 = 0;
  }
  else
  {
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_dd4f85ff8caf3ef1f19e2c81dc211a8d_Traceguids, 1, v8);
      v9 = My_CM_MapCrToWin32Err(v8);
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      HResultException::HResultException((HResultException *)pExceptionObject, v9);
      throw (HResultException *)pExceptionObject;
    }
    if ( (unsigned __int64)(a4 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegistryKey::RegistryKey(a2, phkDevice);
    }
    else
    {
      v10 = (HKEY *)RegistryKey::RegistryKey((RegistryKey *)v13, phkDevice);
      RegistryKey::CreateSubKey(v10, a2, v11, a3, a4);
      RegistryKey::~RegistryKey(v13);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180006208  mov     r11, rsp
0x18000620b  push    rbx
0x18000620c  push    rbp
0x18000620d  push    rsi
0x18000620e  push    rdi
0x18000620f  sub     rsp, 148h
0x180006216  mov     [rsp+168h+var_118], 0FFFFFFFFFFFFFFFEh
0x18000621f  mov     rax, cs:__security_cookie
0x180006226  xor     rax, rsp
0x180006229  mov     [rsp+168h+var_38], rax
0x180006231  mov     rsi, r9
0x180006234  mov     ebp, r8d
0x180006237  mov     rdi, rdx
0x18000623a  mov     rbx, rcx
0x18000623d  mov     [rsp+168h+var_128], rdx
0x180006242  mov     qword ptr [r11-40h], 0
0x18000624a  call    ?EnsureDeviceInstance@NetSetupDevice@@AEAAXXZ; NetSetupDevice::EnsureDeviceInstance(void)
0x18000624f  mov     [rsp+168h+ulFlags], 1; ulFlags
0x180006257  lea     rax, [rsp+168h+var_40]
0x18000625f  mov     [rsp+168h+phkDevice], rax; phkDevice
0x180006264  mov     r9d, 1; Disposition
0x18000626a  xor     r8d, r8d; ulHardwareProfile
0x18000626d  mov     edx, ebp; samDesired
0x18000626f  mov     ecx, [rbx]; dnDevNode
0x180006271  call    cs:__imp_CM_Open_DevNode_Key
0x180006277  mov     ebx, eax
0x180006279  cmp     eax, 2Eh ; '.'
0x18000627c  jnz     short loc_18000628A
0x18000627e  mov     qword ptr [rdi], 0
0x180006285  jmp     loc_18000633A
0x18000628a  test    ebx, ebx
0x18000628c  jz      short loc_1800062F5
0x18000628e  lea     rax, WPP_GLOBAL_Control
0x180006295  mov     rcx, cs:WPP_GLOBAL_Control
0x18000629c  cmp     rcx, rax
0x18000629f  jz      short loc_1800062C4
0x1800062a1  cmp     byte ptr [rcx+19h], 2
0x1800062a5  jb      short loc_1800062C4
0x1800062a7  mov     edx, 0Bh
0x1800062ac  mov     dword ptr [rsp+168h+phkDevice], ebx
0x1800062b0  lea     r9d, [rdx-0Ah]
0x1800062b4  lea     r8, WPP_dd4f85ff8caf3ef1f19e2c81dc211a8d_Traceguids
0x1800062bb  mov     rcx, [rcx+10h]
0x1800062bf  call    WPP_SF_DD
0x1800062c4  mov     ecx, ebx; unsigned int
0x1800062c6  call    ?My_CM_MapCrToWin32Err@@YAKKK@Z; My_CM_MapCrToWin32Err(ulong,ulong)
0x1800062cb  test    eax, eax
0x1800062cd  jle     short loc_1800062D7
0x1800062cf  movzx   eax, ax
0x1800062d2  or      eax, 80070000h
0x1800062d7  mov     edx, eax; int
0x1800062d9  lea     rcx, [rsp+168h+pExceptionObject]; this
0x1800062de  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x1800062e3  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x1800062ea  lea     rcx, [rsp+168h+pExceptionObject]; pExceptionObject
0x1800062ef  call    _CxxThrowException_0
0x1800062f5  lea     rax, [rsi-1]
0x1800062f9  mov     rdx, [rsp+168h+var_40]; HKEY
0x180006301  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180006305  ja      short loc_180006332
0x180006307  lea     rcx, [rsp+168h+var_128]; this
0x18000630c  call    ??0RegistryKey@@QEAA@PEAUHKEY__@@@Z; RegistryKey::RegistryKey(HKEY__ *)
0x180006311  nop
0x180006312  mov     [rsp+168h+phkDevice], rsi
0x180006317  mov     r9d, ebp
0x18000631a  mov     rdx, rdi
0x18000631d  mov     rcx, rax
0x180006320  call    ?CreateSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAXPEAKK@Z; RegistryKey::CreateSubKey(wchar_t const *,ulong,void *,ulong *,ulong)
0x180006325  nop
0x180006326  lea     rcx, [rsp+168h+var_128]; this
0x18000632b  call    ??1RegistryKey@@QEAA@XZ; RegistryKey::~RegistryKey(void)
0x180006330  jmp     short loc_18000633A
0x180006332  mov     rcx, rdi; this
0x180006335  call    ??0RegistryKey@@QEAA@PEAUHKEY__@@@Z; RegistryKey::RegistryKey(HKEY__ *)
0x18000633a  mov     rax, rdi
0x18000633d  mov     rcx, [rsp+168h+var_38]
0x180006345  xor     rcx, rsp; StackCookie
0x180006348  call    __security_check_cookie
0x18000634d  add     rsp, 148h
0x180006354  pop     rdi
0x180006355  pop     rsi
0x180006356  pop     rbp
0x180006357  pop     rbx
0x180006358  retn
```
