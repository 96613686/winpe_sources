# GetDriverNetworkKey(NetSetup2::Transaction &,NetSetup2::ActiveObject const &,ulong)

- ea: `0x1800425b4`
- end: `0x180042704`
- name: `?GetDriverNetworkKey@@YA?AVRegistryKey@@AEAVTransaction@NetSetup2@@AEBVActiveObject@3@K@Z`
- size: `336`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x1800418b4`
- `0x18007bd74`

## callees

- `0x180017320`
- `0x180027b38`
- `0x180028720`
- `0x1800425b4`
- `0x180052620`
- `0x180052698`
- `0x18005a538`
- `0x180065035`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180042673`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180042673`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
RegistryKey *__fastcall GetDriverNetworkKey(RegistryKey *a1, __int64 a2, const struct NetSetup2::ActiveObject *a3)
{
  HKEY CurrentControlSetRegistryHandle; // rbx
  LSTATUS v6; // ebx
  __int64 v8; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v9; // [rsp+68h] [rbp-A0h] BYREF
  int v10; // [rsp+70h] [rbp-98h]
  __int128 v11; // [rsp+74h] [rbp-94h]
  __int64 v12; // [rsp+88h] [rbp-80h]
  _BYTE pExceptionObject[208]; // [rsp+90h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+160h] [rbp+58h] BYREF
  WCHAR SubKey[264]; // [rsp+168h] [rbp+60h] BYREF

  v12 = -2;
  phkResult = (HKEY)a1;
  GetPathToDriverNetworkKey(a3, SubKey);
  v8 = a2;
  v9 = 0;
  v10 = 9;
  v11 = 0;
  CurrentControlSetRegistryHandle = NetSetup2::TransactionObject::get_CurrentControlSetRegistryHandle((NetSetup2::TransactionObject *)&v8);
  std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(&v9);
  phkResult = 0;
  v6 = RegCreateKeyExW(CurrentControlSetRegistryHandle, SubKey, 0, 0, 0, 6u, 0, &phkResult, 0);
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)WPP_a2b45cfeeb593995be62c67c465d3517_Traceguids,
        (unsigned int)SubKey,
        v6);
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v6);
    throw (Win32Exception *)pExceptionObject;
  }
  RegistryKey::RegistryKey(a1, phkResult);
  return a1;
}

```

## disassembly

```asm
0x1800425b4  mov     rax, rsp
0x1800425b7  push    rbp
0x1800425b8  lea     rbp, [rax-288h]
0x1800425bf  sub     rsp, 380h
0x1800425c6  mov     [rbp+280h+var_300], 0FFFFFFFFFFFFFFFEh
0x1800425ce  mov     [rax+10h], rbx
0x1800425d2  mov     [rax+20h], rdi
0x1800425d6  mov     rax, cs:__security_cookie
0x1800425dd  xor     rax, rsp
0x1800425e0  mov     [rbp+280h+var_10], rax
0x1800425e7  mov     rbx, rdx
0x1800425ea  mov     rdi, rcx
0x1800425ed  mov     [rbp+280h+var_228], rcx
0x1800425f1  lea     rdx, [rbp+280h+SubKey]; wchar_t *
0x1800425f5  mov     rcx, r8; struct NetSetup2::ActiveObject *
0x1800425f8  call    ?GetPathToDriverNetworkKey@@YAXAEBVActiveObject@NetSetup2@@PEA_W@Z; GetPathToDriverNetworkKey(NetSetup2::ActiveObject const &,wchar_t *)
0x1800425fd  xorps   xmm0, xmm0
0x180042600  mov     [rsp+380h+var_328], rbx
0x180042605  mov     qword ptr [rsp+380h+var_320], 0
0x18004260e  mov     dword ptr [rsp+380h+var_31C+4], 9
0x180042616  movdqu  xmmword ptr [rsp+380h+var_31C+8], xmm0
0x18004261c  lea     rcx, [rsp+380h+var_328]; this
0x180042621  call    ?get_CurrentControlSetRegistryHandle@TransactionObject@NetSetup2@@QEBAPEAUHKEY__@@XZ; NetSetup2::TransactionObject::get_CurrentControlSetRegistryHandle(void)
0x180042626  mov     rbx, rax
0x180042629  lea     rcx, [rsp+380h+var_320]
0x18004262e  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x180042633  mov     [rbp+280h+var_228], 0
0x18004263b  mov     [rsp+380h+lpdwDisposition], 0; lpdwDisposition
0x180042644  lea     rax, [rbp+280h+var_228]
0x180042648  mov     [rsp+380h+phkResult], rax; phkResult
0x18004264d  mov     [rsp+380h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180042656  mov     [rsp+380h+samDesired], 6; samDesired
0x18004265e  mov     [rsp+380h+dwOptions], 0; dwOptions
0x180042666  xor     r9d, r9d; lpClass
0x180042669  xor     r8d, r8d; Reserved
0x18004266c  lea     rdx, [rbp+280h+SubKey]; lpSubKey
0x180042670  mov     rcx, rbx; hKey
0x180042673  call    cs:__imp_RegCreateKeyExW
0x180042679  mov     ebx, eax
0x18004267b  test    eax, eax
0x18004267d  jz      short loc_1800426D1
0x18004267f  lea     rax, WPP_GLOBAL_Control
0x180042686  mov     rcx, cs:WPP_GLOBAL_Control
0x18004268d  cmp     rcx, rax
0x180042690  jz      short loc_1800426B5
0x180042692  cmp     byte ptr [rcx+19h], 2
0x180042696  jb      short loc_1800426B5
0x180042698  mov     edx, 0Ah
0x18004269d  mov     [rsp+380h+dwOptions], ebx
0x1800426a1  lea     r9, [rbp+280h+SubKey]
0x1800426a5  lea     r8, WPP_a2b45cfeeb593995be62c67c465d3517_Traceguids
0x1800426ac  mov     rcx, [rcx+10h]
0x1800426b0  call    WPP_SF_Sd
0x1800426b5  mov     edx, ebx; int
0x1800426b7  lea     rcx, [rbp+280h+pExceptionObject]; this
0x1800426bb  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x1800426c0  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x1800426c7  lea     rcx, [rbp+280h+pExceptionObject]; pExceptionObject
0x1800426cb  call    _CxxThrowException_0
0x1800426d1  mov     rdx, [rbp+280h+var_228]; HKEY
0x1800426d5  mov     rcx, rdi; this
0x1800426d8  call    ??0RegistryKey@@QEAA@PEAUHKEY__@@@Z; RegistryKey::RegistryKey(HKEY__ *)
0x1800426dd  mov     rax, rdi
0x1800426e0  mov     rcx, [rbp+280h+var_10]
0x1800426e7  xor     rcx, rsp; StackCookie
0x1800426ea  call    __security_check_cookie
0x1800426ef  lea     r11, [rsp+380h+var_s0]
0x1800426f7  mov     rbx, [r11+18h]
0x1800426fb  mov     rdi, [r11+28h]
0x1800426ff  mov     rsp, r11
0x180042702  pop     rbp
0x180042703  retn
```
