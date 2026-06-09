# NetSetupDevice::OpenDeviceKey(ulong,void *,NetSetupDevice::DeviceKeyFailPolicy,ulong,ulong)

- ea: `0x1800296fc`
- end: `0x18002983a`
- name: `?OpenDeviceKey@NetSetupDevice@@AEAA?AVRegistryKey@@KPEAXW4DeviceKeyFailPolicy@1@KK@Z`
- size: `318`
- prototype: `RegistryKey *__fastcall(NetSetupDevice *, RegistryKey *, REGSAM, char *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x180029840`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x180008854`
- `0x180008e3c`
- `0x18000de84`
- `0x180026958`
- `0x180026a10`
- `0x18002900c`
- `0x180029664`
- `0x1800296fc`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x18002975c`
- `api-ms-win-devices-config-l1-1-1!CM_Open_DevNode_Key` at `0x18002975c`

## pseudocode

```c
RegistryKey *__fastcall NetSetupDevice::OpenDeviceKey(NetSetupDevice *a1, RegistryKey *a2, REGSAM a3, char *a4)
{
  CONFIGRET v8; // ebx
  int v9; // eax
  HKEY *v10; // rax
  HKEY v12[2]; // [rsp+40h] [rbp-118h] BYREF
  _BYTE pExceptionObject[208]; // [rsp+50h] [rbp-108h] BYREF
  HKEY phkDevice; // [rsp+120h] [rbp-38h] BYREF

  v12[0] = (HKEY)a2;
  phkDevice = 0;
  NetSetupDevice::EnsureDeviceInstance(a1);
  v8 = CM_Open_DevNode_Key(*(_DWORD *)a1, a3, 0, 1u, &phkDevice, 1u);
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_68b10d64b8793bc8381a9fd0e6d1dc39_Traceguids, 1, v8);
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
    v10 = (HKEY *)RegistryKey::RegistryKey((RegistryKey *)v12, phkDevice);
    RegistryKey::CreateSubKey(v10, a2, (const WCHAR *)&qword_180037068, a3, a4);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v12);
  }
  return a2;
}

```

## disassembly

```asm
0x1800296fc  mov     r11, rsp
0x1800296ff  push    rbx
0x180029700  push    rbp
0x180029701  push    rsi
0x180029702  push    rdi
0x180029703  sub     rsp, 138h
0x18002970a  mov     rax, cs:__security_cookie
0x180029711  xor     rax, rsp
0x180029714  mov     [rsp+158h+var_30], rax
0x18002971c  mov     rsi, r9
0x18002971f  mov     ebp, r8d
0x180029722  mov     rdi, rdx
0x180029725  mov     rbx, rcx
0x180029728  mov     [rsp+158h+var_118], rdx
0x18002972d  mov     qword ptr [r11-38h], 0
0x180029735  call    ?EnsureDeviceInstance@NetSetupDevice@@AEAAXXZ; NetSetupDevice::EnsureDeviceInstance(void)
0x18002973a  mov     [rsp+158h+ulFlags], 1; ulFlags
0x180029742  lea     rax, [rsp+158h+var_38]
0x18002974a  mov     [rsp+158h+phkDevice], rax; phkDevice
0x18002974f  mov     r9d, 1; Disposition
0x180029755  xor     r8d, r8d; ulHardwareProfile
0x180029758  mov     edx, ebp; samDesired
0x18002975a  mov     ecx, [rbx]; dnDevNode
0x18002975c  call    cs:__imp_CM_Open_DevNode_Key
0x180029762  mov     ebx, eax
0x180029764  test    eax, eax
0x180029766  jz      short loc_1800297CF
0x180029768  lea     rax, WPP_GLOBAL_Control
0x18002976f  mov     rcx, cs:WPP_GLOBAL_Control
0x180029776  cmp     rcx, rax
0x180029779  jz      short loc_18002979E
0x18002977b  cmp     byte ptr [rcx+19h], 2
0x18002977f  jb      short loc_18002979E
0x180029781  mov     edx, 0Bh
0x180029786  mov     dword ptr [rsp+158h+phkDevice], ebx
0x18002978a  lea     r9d, [rdx-0Ah]
0x18002978e  lea     r8, WPP_68b10d64b8793bc8381a9fd0e6d1dc39_Traceguids
0x180029795  mov     rcx, [rcx+10h]
0x180029799  call    WPP_SF_DD
0x18002979e  mov     ecx, ebx; unsigned int
0x1800297a0  call    ?My_CM_MapCrToWin32Err@@YAKKK@Z; My_CM_MapCrToWin32Err(ulong,ulong)
0x1800297a5  test    eax, eax
0x1800297a7  jle     short loc_1800297B1
0x1800297a9  movzx   eax, ax
0x1800297ac  or      eax, 80070000h
0x1800297b1  mov     edx, eax; int
0x1800297b3  lea     rcx, [rsp+158h+pExceptionObject]; this
0x1800297b8  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x1800297bd  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x1800297c4  lea     rcx, [rsp+158h+pExceptionObject]; pExceptionObject
0x1800297c9  call    _CxxThrowException_0
0x1800297cf  lea     rax, [rsi-1]
0x1800297d3  mov     rdx, [rsp+158h+var_38]; HKEY
0x1800297db  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800297df  ja      short loc_180029813
0x1800297e1  lea     rcx, [rsp+158h+var_118]; this
0x1800297e6  call    ??0RegistryKey@@QEAA@PEAUHKEY__@@@Z; RegistryKey::RegistryKey(HKEY__ *)
0x1800297eb  nop
0x1800297ec  mov     [rsp+158h+phkDevice], rsi
0x1800297f1  mov     r9d, ebp
0x1800297f4  lea     r8, qword_180037068
0x1800297fb  mov     rdx, rdi
0x1800297fe  mov     rcx, rax
0x180029801  call    ?CreateSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAXPEAKK@Z; RegistryKey::CreateSubKey(wchar_t const *,ulong,void *,ulong *,ulong)
0x180029806  nop
0x180029807  lea     rcx, [rsp+158h+var_118]
0x18002980c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180029811  jmp     short loc_18002981B
0x180029813  mov     rcx, rdi; this
0x180029816  call    ??0RegistryKey@@QEAA@PEAUHKEY__@@@Z; RegistryKey::RegistryKey(HKEY__ *)
0x18002981b  mov     rax, rdi
0x18002981e  mov     rcx, [rsp+158h+var_30]
0x180029826  xor     rcx, rsp; StackCookie
0x180029829  call    __security_check_cookie
0x18002982e  add     rsp, 138h
0x180029835  pop     rdi
0x180029836  pop     rsi
0x180029837  pop     rbp
0x180029838  pop     rbx
0x180029839  retn
```
