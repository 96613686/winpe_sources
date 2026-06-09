# WaaS2::Device::CPUHardwareIdParts::ReadCpuInfoFromMidrRegistry(ushort const *)

- ea: `0x1800608e0`
- end: `0x180060b66`
- name: `?ReadCpuInfoFromMidrRegistry@CPUHardwareIdParts@Device@WaaS2@@AEAAXPEBG@Z`
- size: `646`
- prototype: `void __fastcall(WaaS2::Device::CPUHardwareIdParts *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x1800540a0`

## callees

- `0x1800050a0`
- `0x180009cd0`
- `0x180010db4`
- `0x18005218c`
- `0x1800608e0`
- `0x180060b6c`
- `0x180061268`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006092b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006092b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006096f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006096f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060b3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060b3d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WaaS2::Device::CPUHardwareIdParts::ReadCpuInfoFromMidrRegistry(
        wchar_t *this,
        const unsigned __int16 *a2)
{
  __int64 v4; // rdi
  __int64 v5; // rsi
  unsigned int v6; // r14d
  unsigned int v7; // ebx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  DWORD Type; // [rsp+30h] [rbp-50h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-48h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-40h] BYREF
  BYTE Data[8]; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v22[32]; // [rsp+50h] [rbp-30h] BYREF

  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20119u, &hKey) )
  {
    *(_QWORD *)Data = 0;
    cbData = 8;
    Type = 0;
    if ( RegQueryValueExW(hKey, L"CP 4000", 0, &Type, Data, &cbData) || Type != 11 )
    {
      WaaS2::Device::CPUHardwareIdParts::ReadCpuInfoFromRegistryIdentifier(this, a2);
    }
    else
    {
      v4 = (*(_QWORD *)Data >> 20) & 0xFLL;
      v5 = (*(_QWORD *)Data >> 16) & 0xFLL;
      v6 = *(_WORD *)Data >> 4;
      v7 = Data[0] & 0xF;
      v8 = WaaS2::Device::FormatUInt32AsHex(v22, Data[3]);
      std::wstring::operator=(this, v8);
      std::wstring::~wstring(v22);
      WaaS2::Device::ReadRegString(hKey, L"VendorIdentifier", this + 16);
      v9 = WaaS2::Device::FormatUInt32AsHex(v22, (unsigned int)v4);
      std::wstring::operator=(this + 32, v9);
      std::wstring::~wstring(v22);
      v10 = WaaS2::Device::FormatUInt32AsHex(v22, v7);
      std::wstring::operator=(this + 48, v10);
      std::wstring::~wstring(v22);
      v11 = WaaS2::Device::FormatUInt32AsHex(v22, v7 | ((_DWORD)v4 << 8));
      std::wstring::operator=(this + 64, v11);
      std::wstring::~wstring(v22);
      v12 = WaaS2::Device::FormatUInt32AsHex(v22, (unsigned int)v5);
      std::wstring::operator=(this + 112, v12);
      std::wstring::~wstring(v22);
      v13 = WaaS2::Device::FormatUInt32AsHex(v22, v6);
      std::wstring::operator=(this + 160, v13);
      std::wstring::~wstring(v22);
      v14 = WaaS2::Device::FormatUInt32AsHex(v22, (unsigned int)v5);
      std::wstring::operator=(this + 80, v14);
      std::wstring::~wstring(v22);
      v15 = WaaS2::Device::FormatUInt32AsHex(v22, v6);
      std::wstring::operator=(this + 128, v15);
      std::wstring::~wstring(v22);
      v16 = WaaS2::Device::FormatUInt32AsHex(v22, 0);
      std::wstring::operator=(this + 96, v16);
      std::wstring::~wstring(v22);
      v17 = WaaS2::Device::FormatUInt32AsHex(v22, 0);
      std::wstring::operator=(this + 144, v17);
      std::wstring::~wstring(v22);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x1800608e0  mov     [rsp-28h+arg_10], rbx
0x1800608e5  push    rbp
0x1800608e6  push    rsi
0x1800608e7  push    rdi
0x1800608e8  push    r14
0x1800608ea  push    r15
0x1800608ec  mov     rbp, rsp
0x1800608ef  sub     rsp, 80h
0x1800608f6  mov     rax, cs:__security_cookie
0x1800608fd  xor     rax, rsp
0x180060900  mov     [rbp+var_10], rax
0x180060904  mov     rbx, rdx
0x180060907  mov     r15, rcx
0x18006090a  mov     [rbp+hKey], 0
0x180060912  lea     rax, [rbp+hKey]
0x180060916  mov     [rsp+80h+phkResult], rax; phkResult
0x18006091b  mov     r9d, 20119h; samDesired
0x180060921  xor     r8d, r8d; ulOptions
0x180060924  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006092b  call    cs:__imp_RegOpenKeyExW
0x180060931  test    eax, eax
0x180060933  jnz     loc_180060B34
0x180060939  mov     qword ptr [rbp+Data], 0
0x180060941  mov     [rbp+cbData], 8
0x180060948  mov     [rbp+Type], eax
0x18006094b  lea     rax, [rbp+cbData]
0x18006094f  mov     [rsp+80h+lpcbData], rax; lpcbData
0x180060954  lea     rax, [rbp+Data]
0x180060958  mov     [rsp+80h+phkResult], rax; lpData
0x18006095d  lea     r9, [rbp+Type]; lpType
0x180060961  xor     r8d, r8d; lpReserved
0x180060964  lea     rdx, ValueName; "CP 4000"
0x18006096b  mov     rcx, [rbp+hKey]; hKey
0x18006096f  call    cs:__imp_RegQueryValueExW
0x180060975  test    eax, eax
0x180060977  jnz     loc_180060B28
0x18006097d  cmp     [rbp+Type], 0Bh
0x180060981  jnz     loc_180060B28
0x180060987  mov     rax, qword ptr [rbp+Data]
0x18006098b  mov     rdi, rax
0x18006098e  shr     rdi, 14h
0x180060992  and     edi, 0Fh
0x180060995  mov     rsi, rax
0x180060998  shr     rsi, 10h
0x18006099c  and     esi, 0Fh
0x18006099f  mov     r14, rax
0x1800609a2  shr     r14, 4
0x1800609a6  and     r14d, 0FFFh
0x1800609ad  mov     ebx, eax
0x1800609af  and     ebx, 0Fh
0x1800609b2  shr     rax, 18h
0x1800609b6  movzx   edx, al
0x1800609b9  lea     rcx, [rbp+var_30]
0x1800609bd  call    WaaS2__Device__FormatUInt32AsHex
0x1800609c2  mov     rdx, rax
0x1800609c5  mov     rcx, r15
0x1800609c8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800609cd  lea     rcx, [rbp+var_30]; void *
0x1800609d1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800609d6  lea     r8, [r15+20h]; void *
0x1800609da  lea     rdx, aVendoridentifi; "VendorIdentifier"
0x1800609e1  mov     rcx, [rbp+hKey]; hKey
0x1800609e5  call    WaaS2__Device__ReadRegString
0x1800609ea  mov     edx, edi
0x1800609ec  lea     rcx, [rbp+var_30]
0x1800609f0  call    WaaS2__Device__FormatUInt32AsHex
0x1800609f5  lea     rcx, [r15+40h]
0x1800609f9  mov     rdx, rax
0x1800609fc  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180060a01  lea     rcx, [rbp+var_30]; void *
0x180060a05  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180060a0a  mov     edx, ebx
0x180060a0c  lea     rcx, [rbp+var_30]
0x180060a10  call    WaaS2__Device__FormatUInt32AsHex
0x180060a15  lea     rcx, [r15+60h]
0x180060a19  mov     rdx, rax
0x180060a1c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180060a21  lea     rcx, [rbp+var_30]; void *
0x180060a25  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180060a2a  shl     edi, 8
0x180060a2d  or      edi, ebx
0x180060a2f  mov     edx, edi
0x180060a31  lea     rcx, [rbp+var_30]
0x180060a35  call    WaaS2__Device__FormatUInt32AsHex
0x180060a3a  lea     rcx, [r15+80h]
0x180060a41  mov     rdx, rax
0x180060a44  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180060a49  lea     rcx, [rbp+var_30]; void *
0x180060a4d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180060a52  mov     edx, esi
0x180060a54  lea     rcx, [rbp+var_30]
0x180060a58  call    WaaS2__Device__FormatUInt32AsHex
0x180060a5d  lea     rcx, [r15+0E0h]
0x180060a64  mov     rdx, rax
0x180060a67  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180060a6c  lea     rcx, [rbp+var_30]; void *
0x180060a70  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180060a75  mov     edx, r14d
0x180060a78  lea     rcx, [rbp+var_30]
0x180060a7c  call    WaaS2__Device__FormatUInt32AsHex
0x180060a81  lea     rcx, [r15+140h]
0x180060a88  mov     rdx, rax
0x180060a8b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180060a90  lea     rcx, [rbp+var_30]; void *
0x180060a94  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180060a99  mov     edx, esi
0x180060a9b  lea     rcx, [rbp+var_30]
0x180060a9f  call    WaaS2__Device__FormatUInt32AsHex
0x180060aa4  lea     rcx, [r15+0A0h]
0x180060aab  mov     rdx, rax
0x180060aae  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180060ab3  lea     rcx, [rbp+var_30]; void *
0x180060ab7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180060abc  mov     edx, r14d
0x180060abf  lea     rcx, [rbp+var_30]
0x180060ac3  call    WaaS2__Device__FormatUInt32AsHex
0x180060ac8  lea     rcx, [r15+100h]
0x180060acf  mov     rdx, rax
0x180060ad2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180060ad7  lea     rcx, [rbp+var_30]; void *
0x180060adb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180060ae0  xor     edx, edx
0x180060ae2  lea     rcx, [rbp+var_30]
0x180060ae6  call    WaaS2__Device__FormatUInt32AsHex
0x180060aeb  lea     rcx, [r15+0C0h]
0x180060af2  mov     rdx, rax
0x180060af5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180060afa  lea     rcx, [rbp+var_30]; void *
0x180060afe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180060b03  xor     edx, edx
0x180060b05  lea     rcx, [rbp+var_30]
0x180060b09  call    WaaS2__Device__FormatUInt32AsHex
0x180060b0e  lea     rcx, [r15+120h]
0x180060b15  mov     rdx, rax
0x180060b18  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180060b1d  lea     rcx, [rbp+var_30]; void *
0x180060b21  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180060b26  jmp     short loc_180060B34
0x180060b28  mov     rdx, rbx; unsigned __int16 *
0x180060b2b  mov     rcx, r15; this
0x180060b2e  call    ?ReadCpuInfoFromRegistryIdentifier@CPUHardwareIdParts@Device@WaaS2@@AEAAXPEBG@Z; WaaS2::Device::CPUHardwareIdParts::ReadCpuInfoFromRegistryIdentifier(ushort const *)
0x180060b33  nop
0x180060b34  mov     rcx, [rbp+hKey]; hKey
0x180060b38  test    rcx, rcx
0x180060b3b  jz      short loc_180060B43
0x180060b3d  call    cs:__imp_RegCloseKey
0x180060b43  mov     rcx, [rbp+var_10]
0x180060b47  xor     rcx, rsp; StackCookie
0x180060b4a  call    __security_check_cookie
0x180060b4f  mov     rbx, [rsp+80h+arg_10]
0x180060b57  add     rsp, 80h
0x180060b5e  pop     r15
0x180060b60  pop     r14
0x180060b62  pop     rdi
0x180060b63  pop     rsi
0x180060b64  pop     rbp
0x180060b65  retn
```
