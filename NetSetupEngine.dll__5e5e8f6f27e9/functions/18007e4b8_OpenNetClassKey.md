# OpenNetClassKey

- ea: `0x18007e4b8`
- end: `0x18007e5f1`
- name: `OpenNetClassKey`
- size: `313`
- prototype: `__int64 __fastcall(RegistryKey *this, NetSetup2::TransactionObject *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x1800163d0`

## callees

- `0x180027b38`
- `0x180028720`
- `0x18005097c`
- `0x18005b034`
- `0x180065035`
- `0x18007e4b8`
- `0x18007e658`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007e58c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007e58c`

## pseudocode

```c
RegistryKey *__fastcall OpenNetClassKey(RegistryKey *this, NetSetup2::TransactionObject *a2, __int64 a3)
{
  unsigned int PnpDeviceClass; // eax
  HKEY CurrentControlSetRegistryHandle; // rax
  int v8; // eax
  int v10; // [rsp+30h] [rbp-108h] BYREF
  _BYTE pExceptionObject[208]; // [rsp+38h] [rbp-100h] BYREF
  HKEY phkResult; // [rsp+108h] [rbp-30h] BYREF

  phkResult = (HKEY)this;
  if ( (unsigned int)NetSetup2::NetworkInterface::get_PnpDeviceClass(a3) >= 2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      PnpDeviceClass = NetSetup2::NetworkInterface::get_PnpDeviceClass(a3);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_a2b45cfeeb593995be62c67c465d3517_Traceguids, PnpDeviceClass);
    }
    HResultException::HResultException((HResultException *)pExceptionObject, -2147024809);
    throw (HResultException *)pExceptionObject;
  }
  CurrentControlSetRegistryHandle = NetSetup2::TransactionObject::get_CurrentControlSetRegistryHandle(a2);
  phkResult = 0;
  v8 = RegOpenKeyExW(
         CurrentControlSetRegistryHandle,
         L"Control\\Class\\{4d36e972-e325-11ce-bfc1-08002be10318}",
         0,
         0x20019u,
         &phkResult);
  if ( phkResult )
  {
    RegistryKey::RegistryKey(this, phkResult);
  }
  else
  {
    if ( v8 != 2 )
    {
      if ( v8 > 0 )
        v8 = (unsigned __int16)v8 | 0x80070000;
      v10 = v8;
      throw (long *)&v10;
    }
    *(_QWORD *)this = phkResult;
  }
  return this;
}

```

## disassembly

```asm
0x18007e4b8  push    rbx
0x18007e4ba  push    rsi
0x18007e4bb  push    rdi
0x18007e4bc  sub     rsp, 120h
0x18007e4c3  mov     rax, cs:__security_cookie
0x18007e4ca  xor     rax, rsp
0x18007e4cd  mov     [rsp+138h+var_28], rax
0x18007e4d5  mov     rbx, rcx
0x18007e4d8  mov     [rsp+138h+var_30], rcx
0x18007e4e0  mov     rcx, r8
0x18007e4e3  mov     rdi, r8
0x18007e4e6  mov     rsi, rdx
0x18007e4e9  call    ?get_PnpDeviceClass@NetworkInterface@NetSetup2@@QEBA?AW4_NETSETUP_PNP_DEVICE_CLASS@@XZ; NetSetup2::NetworkInterface::get_PnpDeviceClass(void)
0x18007e4ee  test    eax, eax
0x18007e4f0  jz      short loc_18007E558
0x18007e4f2  cmp     eax, 1
0x18007e4f5  jz      short loc_18007E558
0x18007e4f7  mov     rax, cs:WPP_GLOBAL_Control
0x18007e4fe  lea     rcx, WPP_GLOBAL_Control
0x18007e505  cmp     rax, rcx
0x18007e508  jz      short loc_18007E537
0x18007e50a  cmp     byte ptr [rax+19h], 2
0x18007e50e  jb      short loc_18007E537
0x18007e510  mov     rcx, rdi
0x18007e513  call    ?get_PnpDeviceClass@NetworkInterface@NetSetup2@@QEBA?AW4_NETSETUP_PNP_DEVICE_CLASS@@XZ; NetSetup2::NetworkInterface::get_PnpDeviceClass(void)
0x18007e518  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e51f  lea     r8, WPP_a2b45cfeeb593995be62c67c465d3517_Traceguids
0x18007e526  mov     edx, 0Bh
0x18007e52b  mov     r9d, eax
0x18007e52e  mov     rcx, [rcx+10h]
0x18007e532  call    WPP_SF_d
0x18007e537  mov     edx, 80070057h; int
0x18007e53c  lea     rcx, [rsp+138h+pExceptionObject]; this
0x18007e541  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18007e546  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18007e54d  lea     rcx, [rsp+138h+pExceptionObject]; pExceptionObject
0x18007e552  call    _CxxThrowException_0
0x18007e558  mov     rcx, rsi; this
0x18007e55b  call    ?get_CurrentControlSetRegistryHandle@TransactionObject@NetSetup2@@QEBAPEAUHKEY__@@XZ; NetSetup2::TransactionObject::get_CurrentControlSetRegistryHandle(void)
0x18007e560  lea     rcx, [rsp+138h+var_30]
0x18007e568  mov     [rsp+138h+var_30], 0
0x18007e574  mov     [rsp+138h+phkResult], rcx; phkResult
0x18007e579  lea     rdx, SubKey; "Control\\Class\\{4d36e972-e325-11ce-bfc"...
0x18007e580  mov     rcx, rax; hKey
0x18007e583  mov     r9d, 20019h; samDesired
0x18007e589  xor     r8d, r8d; ulOptions
0x18007e58c  call    cs:__imp_RegOpenKeyExW
0x18007e592  mov     rdx, [rsp+138h+var_30]; HKEY
0x18007e59a  test    rdx, rdx
0x18007e59d  jnz     short loc_18007E5CB
0x18007e59f  cmp     eax, 2
0x18007e5a2  jnz     short loc_18007E5A9
0x18007e5a4  mov     [rbx], rdx
0x18007e5a7  jmp     short loc_18007E5D3
0x18007e5a9  test    eax, eax
0x18007e5ab  jle     short loc_18007E5B5
0x18007e5ad  movzx   eax, ax
0x18007e5b0  or      eax, 80070000h
0x18007e5b5  lea     rdx, _TI1J; pThrowInfo
0x18007e5bc  mov     [rsp+138h+var_108], eax
0x18007e5c0  lea     rcx, [rsp+138h+var_108]; pExceptionObject
0x18007e5c5  call    _CxxThrowException_0
0x18007e5cb  mov     rcx, rbx; this
0x18007e5ce  call    ??0RegistryKey@@QEAA@PEAUHKEY__@@@Z; RegistryKey::RegistryKey(HKEY__ *)
0x18007e5d3  mov     rax, rbx
0x18007e5d6  mov     rcx, [rsp+138h+var_28]
0x18007e5de  xor     rcx, rsp; StackCookie
0x18007e5e1  call    __security_check_cookie
0x18007e5e6  add     rsp, 120h
0x18007e5ed  pop     rdi
0x18007e5ee  pop     rsi
0x18007e5ef  pop     rbx
0x18007e5f0  retn
```
