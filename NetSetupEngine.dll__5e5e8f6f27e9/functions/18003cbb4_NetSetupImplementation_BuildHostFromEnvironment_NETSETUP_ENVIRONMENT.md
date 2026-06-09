# NetSetupImplementation::BuildHostFromEnvironment(_NETSETUP_ENVIRONMENT *)

- ea: `0x18003cbb4`
- end: `0x18003ccf5`
- name: `?BuildHostFromEnvironment@NetSetupImplementation@@AEAAPEAUINetSetupHost@@PEAU_NETSETUP_ENVIRONMENT@@@Z`
- size: `321`
- prototype: `struct INetSetupHost *__fastcall(NetSetupImplementation *__hidden this, struct _NETSETUP_ENVIRONMENT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x18003cb00`

## callees

- `0x18003cbb4`
- `0x18003e1d0`
- `0x180052698`
- `0x18005b034`
- `0x1800646b8`
- `0x180065035`
- `0x180067a2c`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003cc49`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003cc49`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct INetSetupHost *__fastcall NetSetupImplementation::BuildHostFromEnvironment(
        NetSetupImplementation *this,
        struct _NETSETUP_ENVIRONMENT *a2)
{
  struct INetSetupHost *result; // rax
  __int64 v4; // rsi
  unsigned int v5; // eax
  int v6; // ebx
  NetSetupImplementation::OFFLINE_HOST *v7; // rax
  __int64 v8; // rbx
  _BYTE pExceptionObject[208]; // [rsp+40h] [rbp-E8h] BYREF
  HKEY phkResult; // [rsp+110h] [rbp-18h] BYREF

  if ( *(_DWORD *)a2 != 6 && *(_DWORD *)a2 != 8 )
    return (struct INetSetupHost *)*((_QWORD *)a2 + 1);
  phkResult = 0;
  v4 = *((_QWORD *)a2 + 1);
  v5 = RegOpenKeyExW(*(HKEY *)(v4 + 8), &Data, 0, 4u, &phkResult);
  v6 = v5;
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_c0c528d9fee138df7b9d71ef59966413_Traceguids, v5);
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v6);
    throw (Win32Exception *)pExceptionObject;
  }
  try
  {
    v7 = (NetSetupImplementation::OFFLINE_HOST *)operator new(0x80u);
    if ( v7 )
      v8 = NetSetupImplementation::OFFLINE_HOST::OFFLINE_HOST(v7, phkResult, *(const wchar_t **)(v4 + 16));
    else
      v8 = 0;
    if ( v8 == *((_QWORD *)this + 1) )
    {
      v8 = *((_QWORD *)this + 1);
    }
    else
    {
      std::unique_ptr<NetSetupImplementation::OFFLINE_HOST>::_Delete((char *)this + 8);
      *((_QWORD *)this + 1) = v8;
    }
    result = (struct INetSetupHost *)(v8 + 8);
  }
  catch ( ... )
  {
    RegCloseKey(phkResult);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18003cbb4  mov     rax, rsp
0x18003cbb7  push    rdi
0x18003cbb8  sub     rsp, 120h
0x18003cbbf  mov     [rsp+128h+var_F8], 0FFFFFFFFFFFFFFFEh
0x18003cbc8  mov     [rax+18h], rbx
0x18003cbcc  mov     [rax+20h], rsi
0x18003cbd0  mov     rax, cs:__security_cookie
0x18003cbd7  xor     rax, rsp
0x18003cbda  mov     [rsp+128h+var_10], rax
0x18003cbe2  mov     rdi, rcx
0x18003cbe5  cmp     dword ptr [rdx], 6
0x18003cbe8  jz      short loc_18003CC18
0x18003cbea  cmp     dword ptr [rdx], 8
0x18003cbed  jz      short loc_18003CC18
0x18003cbef  mov     rax, [rdx+8]
0x18003cbf3  mov     rcx, [rsp+128h+var_10]
0x18003cbfb  xor     rcx, rsp; StackCookie
0x18003cbfe  call    __security_check_cookie
0x18003cc03  lea     r11, [rsp+128h+var_8]
0x18003cc0b  mov     rbx, [r11+20h]
0x18003cc0f  mov     rsi, [r11+28h]
0x18003cc13  mov     rsp, r11
0x18003cc16  pop     rdi
0x18003cc17  retn
0x18003cc18  mov     [rsp+128h+var_18], 0
0x18003cc24  mov     rsi, [rdx+8]
0x18003cc28  lea     rax, [rsp+128h+var_18]
0x18003cc30  mov     [rsp+128h+phkResult], rax; phkResult
0x18003cc35  mov     r9d, 4; samDesired
0x18003cc3b  xor     r8d, r8d; ulOptions
0x18003cc3e  lea     rdx, Data; lpSubKey
0x18003cc45  mov     rcx, [rsi+8]; hKey
0x18003cc49  call    cs:__imp_RegOpenKeyExW
0x18003cc4f  mov     ebx, eax
0x18003cc51  test    eax, eax
0x18003cc53  jz      short loc_18003CCA4
0x18003cc55  lea     rax, WPP_GLOBAL_Control
0x18003cc5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003cc63  cmp     rcx, rax
0x18003cc66  jz      short loc_18003CC86
0x18003cc68  cmp     byte ptr [rcx+19h], 2
0x18003cc6c  jb      short loc_18003CC86
0x18003cc6e  mov     edx, 0Bh
0x18003cc73  mov     r9d, ebx
0x18003cc76  lea     r8, WPP_c0c528d9fee138df7b9d71ef59966413_Traceguids
0x18003cc7d  mov     rcx, [rcx+10h]
0x18003cc81  call    WPP_SF_d
0x18003cc86  mov     edx, ebx; int
0x18003cc88  lea     rcx, [rsp+128h+pExceptionObject]; this
0x18003cc8d  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x18003cc92  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x18003cc99  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x18003cc9e  call    _CxxThrowException_0
0x18003cca4  mov     ecx, 80h; Size
0x18003cca9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003ccae  mov     [rsp+128h+var_F0], rax
0x18003ccb3  test    rax, rax
0x18003ccb6  jz      short loc_18003CCD1
0x18003ccb8  mov     r8, [rsi+10h]; wchar_t *
0x18003ccbc  mov     rdx, [rsp+128h+var_18]; HKEY
0x18003ccc4  mov     rcx, rax; this
0x18003ccc7  call    ??0OFFLINE_HOST@NetSetupImplementation@@QEAA@PEAUHKEY__@@PEB_W@Z; NetSetupImplementation::OFFLINE_HOST::OFFLINE_HOST(HKEY__ *,wchar_t const *)
0x18003cccc  mov     rbx, rax
0x18003cccf  jmp     short loc_18003CCD3
0x18003ccd1  xor     ebx, ebx
0x18003ccd3  cmp     rbx, [rdi+8]
0x18003ccd7  jz      short loc_18003CCE8
0x18003ccd9  lea     rcx, [rdi+8]
0x18003ccdd  call    ?_Delete@?$unique_ptr@UOFFLINE_HOST@NetSetupImplementation@@U?$default_delete@UOFFLINE_HOST@NetSetupImplementation@@@std@@@std@@AEAAXXZ; std::unique_ptr<NetSetupImplementation::OFFLINE_HOST>::_Delete(void)
0x18003cce2  mov     [rdi+8], rbx
0x18003cce6  jmp     short loc_18003CCEC
0x18003cce8  mov     rbx, [rdi+8]
0x18003ccec  lea     rax, [rbx+8]
0x18003ccf0  jmp     loc_18003CBF3
```
