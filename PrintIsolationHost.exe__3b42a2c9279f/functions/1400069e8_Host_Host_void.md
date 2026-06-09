# Host::Host(void)

- ea: `0x1400069e8`
- end: `0x140006baa`
- name: `??0Host@@QEAA@XZ`
- size: `450`
- prototype: `Host *__fastcall(Host *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140001900`

## callees

- `0x140005dec`
- `0x1400069e8`
- `0x140008010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140006b3d`
- `ADVAPI32!RegOpenKeyExW` at `0x140006b3d`
- `ADVAPI32!RegQueryValueExW` at `0x140006b79`
- `ADVAPI32!RegQueryValueExW` at `0x140006b79`
- `ADVAPI32!RegCloseKey` at `0x140006b96`
- `ADVAPI32!RegCloseKey` at `0x140006b96`
- `KERNEL32!GetCurrentThreadId` at `0x140006a57`
- `KERNEL32!GetCurrentThreadId` at `0x140006a57`
- `KERNEL32!GetModuleHandleW` at `0x140006aac`
- `KERNEL32!GetModuleHandleW` at `0x140006aac`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140006a94`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140006a94`

## string_xrefs

- `0x140006aa5`: `Mscoree.dll`

## pseudocode

```c
Host *__fastcall Host::Host(Host *this)
{
  DWORD CurrentThreadId; // eax
  HRESULT v2; // eax
  __int64 v3; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v4; // rbx
  __int64 *v5; // rax
  Host *Data; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  Data = this;
  qword_14000C558 = 0;
  qword_14000C528 = 0;
  xmmword_14000C538 = 0;
  qword_14000C530 = 0;
  xmmword_14000C548 = 0;
  ATL::_pAtlModule = (struct ATL::CAtlModule *)&_AtlModule;
  qword_14000C560 = 0;
  if ( (int)ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)&xmmword_14000C538) >= 0 )
    LODWORD(qword_14000C528) = 56;
  else
    ATL::CAtlBaseModule::m_bInitFailed = 1;
  CurrentThreadId = GetCurrentThreadId();
  hEvent = 0;
  dword_14000C568 = CurrentThreadId;
  dwMilliseconds = 5000;
  dword_14000C57C = 1000;
  byte_14000C580 = 1;
  byte_14000C582 = 0;
  v2 = CoInitializeEx(0, 0);
  if ( v2 >= 0 )
  {
    byte_14000C582 = 1;
  }
  else if ( v2 != -2147417850 || !GetModuleHandleW(L"Mscoree.dll") )
  {
    ATL::CAtlBaseModule::m_bInitFailed = 1;
    goto LABEL_14;
  }
  v4 = off_14000C0E0;
  v5 = off_14000C0E8;
  while ( v4 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v5 )
  {
    if ( *v4 )
    {
      LOBYTE(v3) = 1;
      (*((void (__fastcall **)(__int64))*v4 + 8))(v3);
      v5 = off_14000C0E8;
    }
    ++v4;
  }
LABEL_14:
  hKey = 0;
  _AtlModule = &Host::`vftable';
  dwMilliseconds = 30000;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Print", 0, 0x20019u, &hKey) )
  {
    LODWORD(Data) = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"PrintIsolationIdleTimeout", 0, 0, (LPBYTE)&Data, &cbData)
      && (unsigned int)Data > 0x7530 )
    {
      dwMilliseconds = (unsigned int)Data;
    }
    RegCloseKey(hKey);
  }
  return (Host *)&_AtlModule;
}

```

## disassembly

```asm
0x1400069e8  mov     [rsp+arg_18], rbx
0x1400069ed  mov     [rsp+Data], rcx
0x1400069f2  push    rsi
0x1400069f3  sub     rsp, 30h
0x1400069f7  xor     eax, eax
0x1400069f9  lea     rsi, ?_AtlModule@@3VHost@@A; Host _AtlModule
0x140006a00  xorps   xmm0, xmm0
0x140006a03  mov     cs:qword_14000C558, rax
0x140006a0a  lea     rcx, xmmword_14000C538; this
0x140006a11  mov     cs:qword_14000C528, rax
0x140006a18  movups  cs:xmmword_14000C538, xmm0
0x140006a1f  mov     cs:qword_14000C530, rax
0x140006a26  movups  cs:xmmword_14000C548, xmm0
0x140006a2d  mov     cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA, rsi; ATL::CAtlModule * ATL::_pAtlModule
0x140006a34  mov     cs:qword_14000C560, rax
0x140006a3b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x140006a40  test    eax, eax
0x140006a42  jns     short loc_140006A4D
0x140006a44  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x140006a4b  jmp     short loc_140006A57
0x140006a4d  mov     dword ptr cs:qword_14000C528, 38h ; '8'
0x140006a57  call    cs:__imp_GetCurrentThreadId
0x140006a5d  xor     edx, edx; dwCoInit
0x140006a5f  mov     cs:hEvent, 0
0x140006a6a  xor     ecx, ecx; pvReserved
0x140006a6c  mov     cs:dword_14000C568, eax
0x140006a72  mov     cs:dwMilliseconds, 1388h
0x140006a7c  mov     cs:dword_14000C57C, 3E8h
0x140006a86  mov     cs:byte_14000C580, 1
0x140006a8d  mov     cs:byte_14000C582, 0
0x140006a94  call    cs:__imp_CoInitializeEx
0x140006a9a  test    eax, eax
0x140006a9c  jns     short loc_140006AC0
0x140006a9e  cmp     eax, 80010106h
0x140006aa3  jnz     short loc_140006AB7
0x140006aa5  lea     rcx, aMscoreeDll; "Mscoree.dll"
0x140006aac  call    cs:__imp_GetModuleHandleW
0x140006ab2  test    rax, rax
0x140006ab5  jnz     short loc_140006AC7
0x140006ab7  mov     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 1; bool ATL::CAtlBaseModule::m_bInitFailed
0x140006abe  jmp     short loc_140006AFA
0x140006ac0  mov     cs:byte_14000C582, 1
0x140006ac7  mov     rbx, cs:off_14000C0E0
0x140006ace  mov     rax, cs:off_14000C0E8
0x140006ad5  jmp     short loc_140006AF5
0x140006ad7  mov     rdx, [rbx]
0x140006ada  test    rdx, rdx
0x140006add  jz      short loc_140006AF1
0x140006adf  mov     rax, [rdx+40h]
0x140006ae3  mov     cl, 1
0x140006ae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006aea  mov     rax, cs:off_14000C0E8
0x140006af1  add     rbx, 8
0x140006af5  cmp     rbx, rax
0x140006af8  jb      short loc_140006AD7
0x140006afa  lea     rax, ??_7Host@@6B@; const Host::`vftable'
0x140006b01  mov     [rsp+38h+hKey], 0
0x140006b0a  mov     cs:?_AtlModule@@3VHost@@A, rax; Host _AtlModule
0x140006b11  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Pri"...
0x140006b18  lea     rax, [rsp+38h+hKey]
0x140006b1d  mov     ebx, 7530h
0x140006b22  mov     r9d, 20019h; samDesired
0x140006b28  mov     [rsp+38h+phkResult], rax; phkResult
0x140006b2d  xor     r8d, r8d; ulOptions
0x140006b30  mov     cs:dwMilliseconds, ebx
0x140006b36  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140006b3d  call    cs:__imp_RegOpenKeyExW
0x140006b43  test    eax, eax
0x140006b45  jnz     short loc_140006B9C
0x140006b47  mov     rcx, [rsp+38h+hKey]; hKey
0x140006b4c  lea     rdx, aPrintisolation_0; "PrintIsolationIdleTimeout"
0x140006b53  mov     dword ptr [rsp+38h+Data], eax
0x140006b57  xor     r9d, r9d; lpType
0x140006b5a  lea     rax, [rsp+38h+cbData]
0x140006b5f  mov     [rsp+38h+cbData], 4
0x140006b67  mov     [rsp+38h+lpcbData], rax; lpcbData
0x140006b6c  xor     r8d, r8d; lpReserved
0x140006b6f  lea     rax, [rsp+38h+Data]
0x140006b74  mov     [rsp+38h+phkResult], rax; lpData
0x140006b79  call    cs:__imp_RegQueryValueExW
0x140006b7f  test    eax, eax
0x140006b81  jnz     short loc_140006B91
0x140006b83  mov     ecx, dword ptr [rsp+38h+Data]
0x140006b87  cmp     ecx, ebx
0x140006b89  jbe     short loc_140006B91
0x140006b8b  mov     cs:dwMilliseconds, ecx
0x140006b91  mov     rcx, [rsp+38h+hKey]; hKey
0x140006b96  call    cs:__imp_RegCloseKey
0x140006b9c  mov     rbx, [rsp+38h+arg_18]
0x140006ba1  mov     rax, rsi
0x140006ba4  add     rsp, 30h
0x140006ba8  pop     rsi
0x140006ba9  retn
```
