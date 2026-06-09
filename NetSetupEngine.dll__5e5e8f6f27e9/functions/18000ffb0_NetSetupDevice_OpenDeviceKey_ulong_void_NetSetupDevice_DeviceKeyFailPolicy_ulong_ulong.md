# NetSetupDevice::OpenDeviceKey(ulong,void *,NetSetupDevice::DeviceKeyFailPolicy,ulong,ulong)

- ea: `0x18000ffb0`
- end: `0x1800101f3`
- name: `?OpenDeviceKey@NetSetupDevice@@AEAA?AVRegistryKey@@KPEAXW4DeviceKeyFailPolicy@1@KK@Z`
- size: `579`
- prototype: `struct RegistryKey __high(unsigned int, void *, enum NetSetupDevice::DeviceKeyFailPolicy, unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x18000f62c`
- `0x18000f670`
- `0x1800163d0`
- `0x180028c28`
- `0x180041334`

## callees

- `0x18000ffb0`
- `0x180010200`
- `0x180028720`
- `0x1800505ec`
- `0x18005097c`
- `0x180052620`
- `0x180065035`
- `0x180067750`
- `0x18006c3a4`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800100ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800100ae`
- `api-ms-win-devices-config-l1-1-0!CM_Locate_DevNodeW` at `0x180010006`
- `api-ms-win-devices-config-l1-1-0!CM_Locate_DevNodeW` at `0x180010006`
- `api-ms-win-devices-config-l1-1-0!CM_Open_DevNode_Key` at `0x180010040`
- `api-ms-win-devices-config-l1-1-0!CM_Open_DevNode_Key` at `0x180010040`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HKEY __fastcall NetSetupDevice::OpenDeviceKey(
        __int64 a1,
        HKEY a2,
        REGSAM a3,
        char *a4,
        char a5,
        REGDISPOSITION Disposition,
        ULONG ulFlags)
{
  CONFIGRET DevNodeW; // r14d
  CONFIGRET v12; // edi
  int v14; // eax
  int v15; // eax
  HKEY hKey[3]; // [rsp+40h] [rbp-138h] BYREF
  _BYTE pExceptionObject[208]; // [rsp+58h] [rbp-120h] BYREF
  HKEY phkDevice; // [rsp+128h] [rbp-50h] BYREF

  hKey[2] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  hKey[0] = a2;
  phkDevice = 0;
  if ( *(_DWORD *)a1 == -1 )
  {
    DevNodeW = CM_Locate_DevNodeW((PDEVINST)a1, *(DEVINSTID_W *)(a1 + 8), 1u);
    if ( DevNodeW )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          41,
          (unsigned int)WPP_dd4f85ff8caf3ef1f19e2c81dc211a8d_Traceguids,
          *(_QWORD *)(a1 + 8),
          DevNodeW);
      v14 = My_CM_MapCrToWin32Err(DevNodeW);
      if ( v14 > 0 )
        v14 = (unsigned __int16)v14 | 0x80070000;
      HResultException::HResultException((HResultException *)pExceptionObject, v14);
      throw (HResultException *)pExceptionObject;
    }
  }
  v12 = CM_Open_DevNode_Key(*(_DWORD *)a1, a3, 0, Disposition, &phkDevice, ulFlags);
  if ( a5 == 1 && v12 == 46 )
  {
    *(_QWORD *)a2 = 0;
  }
  else
  {
    if ( v12 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_dd4f85ff8caf3ef1f19e2c81dc211a8d_Traceguids,
          ulFlags,
          v12);
      v15 = My_CM_MapCrToWin32Err(v12);
      if ( v15 > 0 )
        v15 = (unsigned __int16)v15 | 0x80070000;
      HResultException::HResultException((HResultException *)pExceptionObject, v15);
      throw (HResultException *)pExceptionObject;
    }
    if ( (unsigned __int64)(a4 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegistryKey::RegistryKey((RegistryKey *)a2, phkDevice);
    }
    else
    {
      if ( !phkDevice )
        Win32Exception::ThrowLastError();
      hKey[0] = phkDevice;
      RegistryKey::CreateSubKey(hKey, a2, &Data, a3, a4, 0);
      if ( hKey[0] )
        RegCloseKey(hKey[0]);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18000ffb0  push    rbx
0x18000ffb2  push    rbp
0x18000ffb3  push    rsi
0x18000ffb4  push    rdi
0x18000ffb5  push    r14
0x18000ffb7  push    r15
0x18000ffb9  sub     rsp, 148h
0x18000ffc0  mov     [rsp+178h+var_128], 0FFFFFFFFFFFFFFFEh
0x18000ffc9  mov     rax, cs:__security_cookie
0x18000ffd0  xor     rax, rsp
0x18000ffd3  mov     [rsp+178h+var_48], rax
0x18000ffdb  mov     rsi, r9
0x18000ffde  mov     ebp, r8d
0x18000ffe1  mov     rbx, rdx
0x18000ffe4  mov     rdi, rcx
0x18000ffe7  mov     [rsp+178h+hKey], rdx
0x18000ffec  xor     r15d, r15d
0x18000ffef  mov     [rsp+178h+var_50], r15
0x18000fff7  cmp     dword ptr [rcx], 0FFFFFFFFh
0x18000fffa  jnz     short loc_180010017
0x18000fffc  mov     r8d, 1; ulFlags
0x180010002  mov     rdx, [rcx+8]; pDeviceID
0x180010006  call    cs:__imp_CM_Locate_DevNodeW
0x18001000c  mov     r14d, eax
0x18001000f  test    eax, eax
0x180010011  jnz     loc_180010140
0x180010017  mov     r14d, [rsp+178h+arg_30]
0x18001001f  mov     [rsp+178h+ulFlags], r14d; ulFlags
0x180010024  lea     rax, [rsp+178h+var_50]
0x18001002c  mov     [rsp+178h+phkDevice], rax; phkDevice
0x180010031  mov     r9d, [rsp+178h+Disposition]; Disposition
0x180010039  xor     r8d, r8d; ulHardwareProfile
0x18001003c  mov     edx, ebp; samDesired
0x18001003e  mov     ecx, [rdi]; dnDevNode
0x180010040  call    cs:__imp_CM_Open_DevNode_Key
0x180010046  mov     edi, eax
0x180010048  cmp     [rsp+178h+arg_20], 1
0x180010050  jz      loc_1800100D7
0x180010056  test    edi, edi
0x180010058  jnz     loc_180010189
0x18001005e  lea     rax, [rsi-1]
0x180010062  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180010066  ja      loc_1800101DE
0x18001006c  mov     rax, [rsp+178h+var_50]
0x180010074  test    rax, rax
0x180010077  jz      loc_1800101D8
0x18001007d  mov     [rsp+178h+hKey], rax
0x180010082  mov     qword ptr [rsp+178h+ulFlags], r15
0x180010087  mov     [rsp+178h+phkDevice], rsi
0x18001008c  mov     r9d, ebp
0x18001008f  lea     r8, Data
0x180010096  mov     rdx, rbx
0x180010099  lea     rcx, [rsp+178h+hKey]
0x18001009e  call    ?CreateSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAXPEAKK@Z; RegistryKey::CreateSubKey(wchar_t const *,ulong,void *,ulong *,ulong)
0x1800100a3  nop
0x1800100a4  mov     rcx, [rsp+178h+hKey]; hKey
0x1800100a9  test    rcx, rcx
0x1800100ac  jz      short loc_1800100B4
0x1800100ae  call    cs:__imp_RegCloseKey
0x1800100b4  mov     rax, rbx
0x1800100b7  mov     rcx, [rsp+178h+var_48]
0x1800100bf  xor     rcx, rsp; StackCookie
0x1800100c2  call    __security_check_cookie
0x1800100c7  add     rsp, 148h
0x1800100ce  pop     r15
0x1800100d0  pop     r14
0x1800100d2  pop     rdi
0x1800100d3  pop     rsi
0x1800100d4  pop     rbp
0x1800100d5  pop     rbx
0x1800100d6  retn
0x1800100d7  cmp     edi, 2Eh ; '.'
0x1800100da  jnz     loc_180010056
0x1800100e0  mov     [rbx], r15
0x1800100e3  jmp     short loc_1800100B4
0x1800100e5  mov     ecx, r14d; unsigned int
0x1800100e8  call    ?My_CM_MapCrToWin32Err@@YAKKK@Z; My_CM_MapCrToWin32Err(ulong,ulong)
0x1800100ed  test    eax, eax
0x1800100ef  jg      loc_18001017C
0x1800100f5  mov     edx, eax; int
0x1800100f7  lea     rcx, [rsp+178h+pExceptionObject]; this
0x1800100fc  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180010101  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180010108  lea     rcx, [rsp+178h+pExceptionObject]; pExceptionObject
0x18001010d  call    _CxxThrowException_0
0x180010113  mov     ecx, edi; unsigned int
0x180010115  call    ?My_CM_MapCrToWin32Err@@YAKKK@Z; My_CM_MapCrToWin32Err(ulong,ulong)
0x18001011a  test    eax, eax
0x18001011c  jg      loc_1800101CB
0x180010122  mov     edx, eax; int
0x180010124  lea     rcx, [rsp+178h+pExceptionObject]; this
0x180010129  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18001012e  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180010135  lea     rcx, [rsp+178h+pExceptionObject]; pExceptionObject
0x18001013a  call    _CxxThrowException_0
0x180010140  lea     rax, WPP_GLOBAL_Control
0x180010147  mov     rcx, cs:WPP_GLOBAL_Control
0x18001014e  cmp     rcx, rax
0x180010151  jz      short loc_1800100E5
0x180010153  cmp     byte ptr [rcx+19h], 2
0x180010157  jb      short loc_1800100E5
0x180010159  mov     edx, 29h ; ')'
0x18001015e  mov     dword ptr [rsp+178h+phkDevice], r14d
0x180010163  mov     r9, [rdi+8]
0x180010167  lea     r8, WPP_dd4f85ff8caf3ef1f19e2c81dc211a8d_Traceguids
0x18001016e  mov     rcx, [rcx+10h]
0x180010172  call    WPP_SF_Sd
0x180010177  jmp     loc_1800100E5
0x18001017c  movzx   eax, ax
0x18001017f  or      eax, 80070000h
0x180010184  jmp     loc_1800100F5
0x180010189  lea     rax, WPP_GLOBAL_Control
0x180010190  mov     rcx, cs:WPP_GLOBAL_Control
0x180010197  cmp     rcx, rax
0x18001019a  jz      loc_180010113
0x1800101a0  cmp     byte ptr [rcx+19h], 2
0x1800101a4  jb      loc_180010113
0x1800101aa  mov     edx, 0Bh
0x1800101af  mov     dword ptr [rsp+178h+phkDevice], edi
0x1800101b3  mov     r9d, r14d
0x1800101b6  lea     r8, WPP_dd4f85ff8caf3ef1f19e2c81dc211a8d_Traceguids
0x1800101bd  mov     rcx, [rcx+10h]
0x1800101c1  call    WPP_SF_DD
0x1800101c6  jmp     loc_180010113
0x1800101cb  movzx   eax, ax
0x1800101ce  or      eax, 80070000h
0x1800101d3  jmp     loc_180010122
0x1800101d8  call    ?ThrowLastError@Win32Exception@@SAXXZ; Win32Exception::ThrowLastError(void)
0x1800101de  mov     rdx, [rsp+178h+var_50]; HKEY
0x1800101e6  mov     rcx, rbx; this
0x1800101e9  call    ??0RegistryKey@@QEAA@PEAUHKEY__@@@Z; RegistryKey::RegistryKey(HKEY__ *)
0x1800101ee  jmp     loc_1800100B4
```
