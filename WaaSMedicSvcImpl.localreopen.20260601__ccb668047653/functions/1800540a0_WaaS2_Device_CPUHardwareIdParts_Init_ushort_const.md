# WaaS2::Device::CPUHardwareIdParts::Init(ushort const *)

- ea: `0x1800540a0`
- end: `0x1800541c0`
- name: `?Init@CPUHardwareIdParts@Device@WaaS2@@QEAAJPEBG@Z`
- size: `288`
- prototype: `int(WaaS2::Device::CPUHardwareIdParts *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callers

- `0x18004db30`

## callees

- `0x180008aac`
- `0x180008b14`
- `0x18002cbc4`
- `0x18003e630`
- `0x18004df48`
- `0x1800540a0`
- `0x180055894`
- `0x1800603e0`
- `0x1800608e0`
- `0x180060b6c`
- `0x180061164`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800540f9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800540f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005411f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005411f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WaaS2::Device::CPUHardwareIdParts::Init(
        WaaS2::Device::CPUHardwareIdParts *this,
        const unsigned __int16 *a2)
{
  int v4; // eax
  __int64 v5; // rdx
  __int64 v7; // rdx
  int phkResult; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  v4 = WaaS2::Device::CPUHardwareIdParts::EnumerateProcessorTopology(this);
  if ( v4 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x386,
      (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator2.h",
      (const char *)(unsigned int)v4,
      phkResult);
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20119u, &hKey) )
    WaaS2::Device::ReadRegDwordAsString(hKey, v5, (char *)this + 352);
  if ( hKey )
    RegCloseKey(hKey);
  if ( dword_1800A5B20 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 16LL) )
  {
    Init_thread_header(&dword_1800A5B20);
    if ( dword_1800A5B20 == -1 )
    {
      LODWORD(hKey) = 21792356;
      LOBYTE(v7) = 1;
      byte_1800A5B1C = WaaS2::Device::IsNativeArch_2_(&hKey, v7);
      Init_thread_footer(&dword_1800A5B20);
    }
  }
  if ( byte_1800A5B1C )
  {
    WaaS2::Device::CPUHardwareIdParts::ReadCpuInfoFromCpuid(this);
  }
  else if ( (unsigned __int8)WaaS2::Device::IsNativeArchARM() )
  {
    WaaS2::Device::CPUHardwareIdParts::ReadCpuInfoFromMidrRegistry((wchar_t *)this, a2);
  }
  else
  {
    WaaS2::Device::CPUHardwareIdParts::ReadCpuInfoFromRegistryIdentifier((wchar_t *)this, a2);
  }
  return 0;
}

```

## disassembly

```asm
0x1800540a0  mov     [rsp+arg_0], rbx
0x1800540a5  push    rdi
0x1800540a6  sub     rsp, 30h
0x1800540aa  mov     rdi, rdx
0x1800540ad  mov     rbx, rcx
0x1800540b0  call    ?EnumerateProcessorTopology@CPUHardwareIdParts@Device@WaaS2@@AEAAJXZ; WaaS2::Device::CPUHardwareIdParts::EnumerateProcessorTopology(void)
0x1800540b5  mov     rcx, [rsp+38h]; this
0x1800540ba  test    eax, eax
0x1800540bc  jns     short loc_1800540D3
0x1800540be  mov     r9d, eax; char *
0x1800540c1  lea     r8, aOnecoreInterna_3; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x1800540c8  mov     edx, 386h; void *
0x1800540cd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800540d2  nop
0x1800540d3  mov     [rsp+38h+hKey], 0
0x1800540dc  lea     rax, [rsp+38h+hKey]
0x1800540e1  mov     qword ptr [rsp+38h+phkResult], rax; phkResult
0x1800540e6  mov     r9d, 20119h; samDesired
0x1800540ec  xor     r8d, r8d; ulOptions
0x1800540ef  mov     rdx, rdi; lpSubKey
0x1800540f2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800540f9  call    cs:__imp_RegOpenKeyExW
0x1800540ff  test    eax, eax
0x180054101  jnz     short loc_180054115
0x180054103  lea     r8, [rbx+160h]
0x18005410a  mov     rcx, [rsp+38h+hKey]
0x18005410f  call    WaaS2__Device__ReadRegDwordAsString
0x180054114  nop
0x180054115  mov     rcx, [rsp+38h+hKey]; hKey
0x18005411a  test    rcx, rcx
0x18005411d  jz      short loc_180054125
0x18005411f  call    cs:__imp_RegCloseKey
0x180054125  mov     ecx, cs:_tls_index
0x18005412b  mov     rax, gs:58h
0x180054134  mov     edx, 10h
0x180054139  mov     rax, [rax+rcx*8]
0x18005413d  mov     eax, [rdx+rax]
0x180054140  cmp     cs:dword_1800A5B20, eax
0x180054146  jg      short loc_180054183
0x180054148  cmp     cs:byte_1800A5B1C, 0
0x18005414f  jz      short loc_18005415B
0x180054151  mov     rcx, rbx; this
0x180054154  call    ?ReadCpuInfoFromCpuid@CPUHardwareIdParts@Device@WaaS2@@AEAAXXZ; WaaS2::Device::CPUHardwareIdParts::ReadCpuInfoFromCpuid(void)
0x180054159  jmp     short loc_180054176
0x18005415b  call    WaaS2__Device__IsNativeArchARM
0x180054160  mov     rdx, rdi; unsigned __int16 *
0x180054163  mov     rcx, rbx; this
0x180054166  test    al, al
0x180054168  jz      short loc_180054171
0x18005416a  call    ?ReadCpuInfoFromMidrRegistry@CPUHardwareIdParts@Device@WaaS2@@AEAAXPEBG@Z; WaaS2::Device::CPUHardwareIdParts::ReadCpuInfoFromMidrRegistry(ushort const *)
0x18005416f  jmp     short loc_180054176
0x180054171  call    ?ReadCpuInfoFromRegistryIdentifier@CPUHardwareIdParts@Device@WaaS2@@AEAAXPEBG@Z; WaaS2::Device::CPUHardwareIdParts::ReadCpuInfoFromRegistryIdentifier(ushort const *)
0x180054176  xor     eax, eax
0x180054178  mov     rbx, [rsp+38h+arg_0]
0x18005417d  add     rsp, 30h
0x180054181  pop     rdi
0x180054182  retn
0x180054183  lea     rcx, dword_1800A5B20
0x18005418a  call    _Init_thread_header
0x18005418f  cmp     cs:dword_1800A5B20, 0FFFFFFFFh
0x180054196  jnz     short loc_180054148
0x180054198  mov     dword ptr [rsp+38h+hKey], 14C8664h
0x1800541a0  mov     dl, 1
0x1800541a2  lea     rcx, [rsp+38h+hKey]
0x1800541a7  call    WaaS2__Device__IsNativeArch_2_
0x1800541ac  mov     cs:byte_1800A5B1C, al
0x1800541b2  lea     rcx, dword_1800A5B20
0x1800541b9  call    _Init_thread_footer
0x1800541be  jmp     short loc_180054148
```
