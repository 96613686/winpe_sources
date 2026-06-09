# Windows::Networking::UX::Internal::MBCategory::tp_EnumerateWwanDMProfileFromService(void)

- ea: `0x180008880`
- end: `0x180008c7e`
- name: `?tp_EnumerateWwanDMProfileFromService@MBCategory@Internal@UX@Networking@Windows@@AEAAJXZ`
- size: `1022`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::MBCategory *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000ea3c`

## callees

- `0x180008880`
- `0x180008c84`
- `0x180009200`
- `0x18000a460`
- `0x18000ad20`
- `0x18002cd20`
- `0x18002d8c8`
- `0x180055dd0`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180008a0e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180008ae4`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180008c3c`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180008c72`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180008a0e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180008ae4`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180008c3c`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180008c72`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetDMConfigProfile` at `0x180008a86`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetDMConfigProfile` at `0x180008a86`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetDMConfigProfileList` at `0x1800088e2`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanGetDMConfigProfileList` at `0x1800088e2`
- `WwanPrfl!WwanProfileLoadXml` at `0x180008ac3`
- `WwanPrfl!WwanProfileLoadXml` at `0x180008ac3`

## string_xrefs

- `0x1800089b5`: `Windows::Networking::UX::Internal::MBCategory::tp_EnumerateWwanDMProfileFromService`
- `0x1800089f7`: `Windows::Networking::UX::Internal::MBCategory::tp_EnumerateWwanDMProfileFromService`
- `0x180008bbc`: `Windows::Networking::UX::Internal::MBCategory::tp_EnumerateWwanDMProfileFromService`
- `0x180008bf1`: `Windows::Networking::UX::Internal::MBCategory::tp_EnumerateWwanDMProfileFromService`
- `0x180008c2c`: `Windows::Networking::UX::Internal::MBCategory::_ReadWwanProfileFromService`
- `0x180008c62`: `Windows::Networking::UX::Internal::MBCategory::_ReadWwanProfileFromService`
- `0x180008bb0`: `_ReadWwanProfileFromService failed. HRESULT=0x%x, _guidInterface=%hs, profileName=%ls`
- `0x180008be5`: `UpdateWwanProfile`
- `0x1800089a9`: `Failed to call WwanGetDMConfigProfileList. HRESULT=0x%x, _guidInterface=%hs`
- `0x180008c20`: `Failed to call WwanGetDMConfigProfile. profileName=%ls, HRESULT=0x%x`
- `0x180008c56`: `Failed to call WwanProfileLoadXml. profileName=%ls, HRESULT=0x%x, invalidReason=%d`
- `0x1800089eb`: `Complete. Number of DM profiles=%d, _isLTEAttached=%hs`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Networking::UX::Internal::MBCategory::tp_EnumerateWwanDMProfileFromService(
        Windows::Networking::UX::Internal::MBCategory *this)
{
  Windows::Networking::UX::Internal::MBCategory *v1; // r14
  _DWORD *v2; // r13
  int DMConfigProfileList; // eax
  signed int v4; // ebx
  const char *v5; // rax
  unsigned int v7; // r12d
  unsigned int *i; // rdi
  __int64 v9; // rsi
  const wchar_t *v10; // rdi
  int DMConfigProfile; // eax
  int v12; // eax
  const wchar_t *v13; // r15
  __int64 v14; // r9
  int v15; // [rsp+20h] [rbp-E0h]
  unsigned int *v16; // [rsp+70h] [rbp-90h] BYREF
  int v17; // [rsp+78h] [rbp-88h] BYREF
  __int64 v18; // [rsp+80h] [rbp-80h] BYREF
  char v19[16]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v20[19]; // [rsp+98h] [rbp-68h] BYREF
  Windows::Networking::UX::Internal::MBCategory *v21; // [rsp+B0h] [rbp-50h]
  unsigned int **v22; // [rsp+B8h] [rbp-48h]
  char v23; // [rsp+C0h] [rbp-40h]
  __int128 v24; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v25[19]; // [rsp+D8h] [rbp-28h]
  _BYTE v26[6320]; // [rsp+F0h] [rbp-10h] BYREF

  v1 = this;
  v21 = this;
  v16 = 0;
  v22 = &v16;
  v23 = 1;
  v2 = (_DWORD *)((char *)this + 24);
  DMConfigProfileList = WwanGetDMConfigProfileList(*((_QWORD *)this + 38), (char *)this + 24, &v16);
  v4 = DMConfigProfileList;
  if ( DMConfigProfileList > 0 )
    v4 = (unsigned __int16)DMConfigProfileList | 0x80070000;
  if ( v4 >= 0 )
  {
    v7 = 0;
    for ( i = v16; v7 < *v16; i = v16 )
    {
      memset_0(v26, 0, sizeof(v26));
      v9 = 129LL * v7;
      v10 = (const wchar_t *)&i[v9 + 1];
      v18 = 0;
      v17 = 0;
      DMConfigProfile = WwanGetDMConfigProfile(*((_QWORD *)v1 + 38), v2, v10, &v18);
      v4 = DMConfigProfile;
      if ( DMConfigProfile > 0 )
        v4 = (unsigned __int16)DMConfigProfile | 0x80070000;
      if ( v4 < 0 )
      {
        MBSettingUXLogging::Error(
          "Windows::Networking::UX::Internal::MBCategory::_ReadWwanProfileFromService",
          0x11E9u,
          "Failed to call WwanGetDMConfigProfile. profileName=%ls, HRESULT=0x%x",
          v10,
          v4);
        WwanFreeMemory(v18);
      }
      else
      {
        v12 = WwanProfileLoadXml(v26, v18, 0, 0, &v17, 1);
        v4 = v12;
        if ( v12 > 0 )
          v4 = (unsigned __int16)v12 | 0x80070000;
        if ( v4 < 0 )
        {
          MBSettingUXLogging::Error(
            "Windows::Networking::UX::Internal::MBCategory::_ReadWwanProfileFromService",
            0x11F5u,
            "Failed to call WwanProfileLoadXml. profileName=%ls, HRESULT=0x%x, invalidReason=%d",
            v10,
            v4,
            v17);
          WwanFreeMemory(v18);
        }
        else
        {
          WwanFreeMemory(v18);
          v4 = 0;
        }
      }
      if ( v4 >= 0 )
      {
        MBSettingUXLogging::Info(
          "Windows::Networking::UX::Internal::MBCategory::tp_EnumerateWwanDMProfileFromService",
          0x12A1u,
          "UpdateWwanProfile");
        LOBYTE(v15) = 0;
        LOBYTE(v14) = 1;
        Windows::Networking::UX::Internal::MBCategory::tp_UpdateWwanProfile(v1, v26, 3, v14, v15);
      }
      else
      {
        v13 = (const wchar_t *)&v16[v9 + 1];
        *(_OWORD *)v19 = 0;
        memset(v20, 0, sizeof(v20));
        StringCchPrintfA(
          v19,
          0x23u,
          "{%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}",
          *v2,
          *((unsigned __int16 *)v1 + 14),
          *((unsigned __int16 *)v1 + 15),
          *((unsigned __int8 *)v1 + 32),
          *((unsigned __int8 *)v1 + 33),
          *((unsigned __int8 *)v1 + 34),
          *((unsigned __int8 *)v1 + 35),
          *((unsigned __int8 *)v1 + 36),
          *((unsigned __int8 *)v1 + 37),
          *((unsigned __int8 *)v1 + 38),
          *((unsigned __int8 *)v1 + 39));
        v24 = *(_OWORD *)v19;
        *(_OWORD *)v25 = *(_OWORD *)v20;
        *(_DWORD *)&v25[15] = *(_DWORD *)&v20[15];
        MBSettingUXLogging::Error(
          "Windows::Networking::UX::Internal::MBCategory::tp_EnumerateWwanDMProfileFromService",
          0x129Du,
          "_ReadWwanProfileFromService failed. HRESULT=0x%x, _guidInterface=%hs, profileName=%ls",
          v4,
          (const char *)&v24,
          v13);
        v1 = v21;
      }
      ++v7;
    }
  }
  else
  {
    *(_OWORD *)v19 = 0;
    memset(v20, 0, sizeof(v20));
    StringCchPrintfA(
      v19,
      0x23u,
      "{%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}",
      *v2,
      *((unsigned __int16 *)v2 + 2),
      *((unsigned __int16 *)v2 + 3),
      *((unsigned __int8 *)v2 + 8),
      *((unsigned __int8 *)v2 + 9),
      *((unsigned __int8 *)v2 + 10),
      *((unsigned __int8 *)v2 + 11),
      *((unsigned __int8 *)v2 + 12),
      *((unsigned __int8 *)v2 + 13),
      *((unsigned __int8 *)v2 + 14),
      *((unsigned __int8 *)v2 + 15));
    v24 = *(_OWORD *)v19;
    *(_OWORD *)v25 = *(_OWORD *)v20;
    *(_DWORD *)&v25[15] = *(_DWORD *)&v20[15];
    MBSettingUXLogging::Error(
      "Windows::Networking::UX::Internal::MBCategory::tp_EnumerateWwanDMProfileFromService",
      0x12ACu,
      "Failed to call WwanGetDMConfigProfileList. HRESULT=0x%x, _guidInterface=%hs",
      v4,
      (const char *)&v24);
  }
  v5 = "true";
  if ( !*((_BYTE *)v21 + 628) )
    v5 = "false";
  MBSettingUXLogging::Info(
    "Windows::Networking::UX::Internal::MBCategory::tp_EnumerateWwanDMProfileFromService",
    0x12AFu,
    "Complete. Number of DM profiles=%d, _isLTEAttached=%hs",
    *((_QWORD *)v21 + 119),
    v5);
  if ( v16 )
    WwanFreeMemory(v16);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180008880  push    rbp
0x180008882  push    rbx
0x180008883  push    rsi
0x180008884  push    rdi
0x180008885  push    r12
0x180008887  push    r13
0x180008889  push    r14
0x18000888b  push    r15
0x18000888d  lea     rbp, [rsp-18B8h]
0x180008895  mov     eax, 19B8h
0x18000889a  call    _alloca_probe
0x18000889f  sub     rsp, rax
0x1800088a2  mov     rax, cs:__security_cookie
0x1800088a9  xor     rax, rsp
0x1800088ac  mov     [rbp+18F0h+var_50], rax
0x1800088b3  mov     r14, rcx
0x1800088b6  mov     [rbp+18F0h+var_1940], rcx
0x1800088ba  xor     r15d, r15d
0x1800088bd  mov     [rsp+19F0h+var_1980], r15
0x1800088c2  lea     rax, [rsp+19F0h+var_1980]
0x1800088c7  mov     [rbp+18F0h+var_1938], rax
0x1800088cb  mov     [rbp+18F0h+var_1930], 1
0x1800088cf  lea     r13, [rcx+18h]
0x1800088d3  lea     r8, [rsp+19F0h+var_1980]
0x1800088d8  mov     rdx, r13
0x1800088db  mov     rcx, [rcx+130h]
0x1800088e2  call    cs:__imp_WwanGetDMConfigProfileList
0x1800088e8  mov     ebx, eax
0x1800088ea  test    eax, eax
0x1800088ec  jle     short loc_1800088F7
0x1800088ee  movzx   ebx, ax
0x1800088f1  or      ebx, 80070000h
0x1800088f7  test    ebx, ebx
0x1800088f9  jns     loc_180008A39
0x1800088ff  xorps   xmm0, xmm0
0x180008902  xor     eax, eax
0x180008904  movups  xmmword ptr [rbp+18F0h+var_1968], xmm0
0x180008908  movups  xmmword ptr [rbp+18F0h+var_1958], xmm0
0x18000890c  mov     dword ptr [rbp+18F0h+var_1958+0Fh], eax
0x18000890f  movzx   eax, byte ptr [r13+0Fh]
0x180008914  movzx   ecx, byte ptr [r13+0Eh]
0x180008919  movzx   edx, byte ptr [r13+0Dh]
0x18000891e  movzx   r8d, byte ptr [r13+0Ch]
0x180008923  movzx   r10d, byte ptr [r13+0Bh]
0x180008928  movzx   r11d, byte ptr [r13+0Ah]
0x18000892d  movzx   edi, byte ptr [r13+9]
0x180008932  movzx   esi, byte ptr [r13+8]
0x180008937  movzx   r14d, word ptr [r13+6]
0x18000893c  movzx   r15d, word ptr [r13+4]
0x180008941  mov     [rsp+19F0h+var_1988], eax
0x180008945  mov     [rsp+19F0h+var_1990], ecx
0x180008949  mov     [rsp+19F0h+var_1998], edx
0x18000894d  mov     [rsp+19F0h+var_19A0], r8d
0x180008952  mov     [rsp+19F0h+var_19A8], r10d
0x180008957  mov     [rsp+19F0h+var_19B0], r11d
0x18000895c  mov     [rsp+19F0h+var_19B8], edi
0x180008960  mov     [rsp+19F0h+var_19C0], esi
0x180008964  mov     dword ptr [rsp+19F0h+var_19C8], r14d
0x180008969  mov     dword ptr [rsp+19F0h+var_19D0], r15d
0x18000896e  mov     r9d, [r13+0]
0x180008972  lea     r8, a08lx04hx04hx02; "{%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%"...
0x180008979  mov     edx, 23h ; '#'; unsigned __int64
0x18000897e  lea     rcx, [rbp+18F0h+var_1968]; char *
0x180008982  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180008987  movups  xmm0, xmmword ptr [rbp+18F0h+var_1968]
0x18000898b  movups  [rbp+18F0h+var_1928], xmm0
0x18000898f  movups  xmm1, xmmword ptr [rbp+18F0h+var_1958]
0x180008993  movups  xmmword ptr [rbp+18F0h+var_1918], xmm1
0x180008997  mov     eax, dword ptr [rbp+18F0h+var_1958+0Fh]
0x18000899a  mov     dword ptr [rbp+18F0h+var_1918+0Fh], eax
0x18000899d  lea     rax, [rbp+18F0h+var_1928]
0x1800089a1  mov     [rsp+19F0h+var_19D0], rax
0x1800089a6  mov     r9d, ebx
0x1800089a9  lea     r8, aFailedToCallWw_3; "Failed to call WwanGetDMConfigProfileLi"...
0x1800089b0  mov     edx, 12ACh; unsigned int
0x1800089b5  lea     rcx, aWindowsNetwork_108; "Windows::Networking::UX::Internal::MBCa"...
0x1800089bc  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x1800089c1  lea     rcx, aFalse; "false"
0x1800089c8  lea     rax, aTrue; "true"
0x1800089cf  mov     r9, [rbp+18F0h+var_1940]
0x1800089d3  cmp     byte ptr [r9+274h], 0
0x1800089db  cmovz   rax, rcx
0x1800089df  mov     [rsp+19F0h+var_19D0], rax
0x1800089e4  mov     r9, [r9+3B8h]
0x1800089eb  lea     r8, aCompleteNumber; "Complete. Number of DM profiles=%d, _is"...
0x1800089f2  mov     edx, 12AFh; unsigned int
0x1800089f7  lea     rcx, aWindowsNetwork_108; "Windows::Networking::UX::Internal::MBCa"...
0x1800089fe  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180008a03  nop
0x180008a04  mov     rcx, [rsp+19F0h+var_1980]
0x180008a09  test    rcx, rcx
0x180008a0c  jz      short loc_180008A14
0x180008a0e  call    cs:__imp_WwanFreeMemory
0x180008a14  mov     eax, ebx
0x180008a16  mov     rcx, [rbp+18F0h+var_50]
0x180008a1d  xor     rcx, rsp; StackCookie
0x180008a20  call    __security_check_cookie
0x180008a25  add     rsp, 19B8h
0x180008a2c  pop     r15
0x180008a2e  pop     r14
0x180008a30  pop     r13
0x180008a32  pop     r12
0x180008a34  pop     rdi
0x180008a35  pop     rsi
0x180008a36  pop     rbx
0x180008a37  pop     rbp
0x180008a38  retn
0x180008a39  mov     r12d, r15d
0x180008a3c  mov     rdi, [rsp+19F0h+var_1980]
0x180008a41  cmp     [rdi], r15d
0x180008a44  jbe     loc_1800089C1
0x180008a4a  xor     edx, edx; Val
0x180008a4c  mov     r8d, 18B0h; Size
0x180008a52  lea     rcx, [rbp+18F0h+var_1900]; void *
0x180008a56  call    memset_0
0x180008a5b  mov     eax, r12d
0x180008a5e  imul    rsi, rax, 204h
0x180008a65  add     rdi, 4
0x180008a69  add     rdi, rsi
0x180008a6c  mov     [rbp+18F0h+var_1970], r15
0x180008a70  mov     [rsp+19F0h+var_1978], r15d
0x180008a75  lea     r9, [rbp+18F0h+var_1970]
0x180008a79  mov     r8, rdi
0x180008a7c  mov     rdx, r13
0x180008a7f  mov     rcx, [r14+130h]
0x180008a86  call    cs:__imp_WwanGetDMConfigProfile
0x180008a8c  mov     ebx, eax
0x180008a8e  test    eax, eax
0x180008a90  jle     short loc_180008A9B
0x180008a92  movzx   ebx, ax
0x180008a95  or      ebx, 80070000h
0x180008a9b  test    ebx, ebx
0x180008a9d  js      loc_180008C19
0x180008aa3  mov     dword ptr [rsp+19F0h+var_19C8], 1
0x180008aab  lea     rax, [rsp+19F0h+var_1978]
0x180008ab0  mov     [rsp+19F0h+var_19D0], rax
0x180008ab5  xor     r9d, r9d
0x180008ab8  xor     r8d, r8d
0x180008abb  mov     rdx, [rbp+18F0h+var_1970]
0x180008abf  lea     rcx, [rbp+18F0h+var_1900]
0x180008ac3  call    cs:__imp_WwanProfileLoadXml
0x180008ac9  mov     ebx, eax
0x180008acb  test    eax, eax
0x180008acd  jle     short loc_180008AD8
0x180008acf  movzx   ebx, ax
0x180008ad2  or      ebx, 80070000h
0x180008ad8  test    ebx, ebx
0x180008ada  js      loc_180008C47
0x180008ae0  mov     rcx, [rbp+18F0h+var_1970]
0x180008ae4  call    cs:__imp_WwanFreeMemory
0x180008aea  mov     ebx, r15d
0x180008aed  test    ebx, ebx
0x180008aef  jns     loc_180008BE5
0x180008af5  mov     r15, [rsp+19F0h+var_1980]
0x180008afa  add     r15, 4
0x180008afe  add     r15, rsi
0x180008b01  xorps   xmm0, xmm0
0x180008b04  xor     eax, eax
0x180008b06  movups  xmmword ptr [rbp+18F0h+var_1968], xmm0
0x180008b0a  movups  xmmword ptr [rbp+18F0h+var_1958], xmm0
0x180008b0e  mov     dword ptr [rbp+18F0h+var_1958+0Fh], eax
0x180008b11  movzx   eax, byte ptr [r14+27h]
0x180008b16  movzx   ecx, byte ptr [r14+26h]
0x180008b1b  movzx   edx, byte ptr [r14+25h]
0x180008b20  movzx   r8d, byte ptr [r14+24h]
0x180008b25  movzx   r9d, byte ptr [r14+23h]
0x180008b2a  movzx   r10d, byte ptr [r14+22h]
0x180008b2f  movzx   r11d, byte ptr [r14+21h]
0x180008b34  movzx   edi, byte ptr [r14+20h]
0x180008b39  movzx   esi, word ptr [r14+1Eh]
0x180008b3e  movzx   r14d, word ptr [r14+1Ch]
0x180008b43  mov     [rsp+19F0h+var_1988], eax
0x180008b47  mov     [rsp+19F0h+var_1990], ecx
0x180008b4b  mov     [rsp+19F0h+var_1998], edx
0x180008b4f  mov     [rsp+19F0h+var_19A0], r8d
0x180008b54  mov     [rsp+19F0h+var_19A8], r9d
0x180008b59  mov     [rsp+19F0h+var_19B0], r10d
0x180008b5e  mov     [rsp+19F0h+var_19B8], r11d
0x180008b63  mov     [rsp+19F0h+var_19C0], edi
0x180008b67  mov     dword ptr [rsp+19F0h+var_19C8], esi
0x180008b6b  mov     dword ptr [rsp+19F0h+var_19D0], r14d
0x180008b70  mov     r9d, [r13+0]
0x180008b74  lea     r8, a08lx04hx04hx02; "{%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%"...
0x180008b7b  mov     edx, 23h ; '#'; unsigned __int64
0x180008b80  lea     rcx, [rbp+18F0h+var_1968]; char *
0x180008b84  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180008b89  movups  xmm0, xmmword ptr [rbp+18F0h+var_1968]
0x180008b8d  movups  [rbp+18F0h+var_1928], xmm0
0x180008b91  movups  xmm1, xmmword ptr [rbp+18F0h+var_1958]
0x180008b95  movups  xmmword ptr [rbp+18F0h+var_1918], xmm1
0x180008b99  mov     eax, dword ptr [rbp+18F0h+var_1958+0Fh]
0x180008b9c  mov     dword ptr [rbp+18F0h+var_1918+0Fh], eax
0x180008b9f  mov     [rsp+19F0h+var_19C8], r15
0x180008ba4  lea     rax, [rbp+18F0h+var_1928]
0x180008ba8  mov     [rsp+19F0h+var_19D0], rax
0x180008bad  mov     r9d, ebx
0x180008bb0  lea     r8, aReadwwanprofil_0; "_ReadWwanProfileFromService failed. HRE"...
0x180008bb7  mov     edx, 129Dh; unsigned int
0x180008bbc  lea     rcx, aWindowsNetwork_108; "Windows::Networking::UX::Internal::MBCa"...
0x180008bc3  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x180008bc8  mov     r14, [rbp+18F0h+var_1940]
0x180008bcc  xor     r15d, r15d
0x180008bcf  inc     r12d
0x180008bd2  mov     rdi, [rsp+19F0h+var_1980]
0x180008bd7  cmp     r12d, [rdi]
0x180008bda  jb      loc_180008A4A
0x180008be0  jmp     loc_1800089C1
0x180008be5  lea     r8, aUpdatewwanprof; "UpdateWwanProfile"
0x180008bec  mov     edx, 12A1h; unsigned int
0x180008bf1  lea     rcx, aWindowsNetwork_108; "Windows::Networking::UX::Internal::MBCa"...
0x180008bf8  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180008bfd  mov     byte ptr [rsp+19F0h+var_19D0], 0
0x180008c02  mov     r9b, 1
0x180008c05  mov     r8d, 3
0x180008c0b  lea     rdx, [rbp+18F0h+var_1900]
0x180008c0f  mov     rcx, r14
0x180008c12  call    ?tp_UpdateWwanProfile@MBCategory@Internal@UX@Networking@Windows@@AEAAXAEBUWWAN_PROFILE@@W4_WWAN_ACTIVATION_STATE@@_N2@Z; Windows::Networking::UX::Internal::MBCategory::tp_UpdateWwanProfile(WWAN_PROFILE const &,_WWAN_ACTIVATION_STATE,bool,bool)
0x180008c17  jmp     short loc_180008BCF
0x180008c19  mov     dword ptr [rsp+19F0h+var_19D0], ebx
0x180008c1d  mov     r9, rdi
0x180008c20  lea     r8, aFailedToCallWw_5; "Failed to call WwanGetDMConfigProfile. "...
0x180008c27  mov     edx, 11E9h; unsigned int
0x180008c2c  lea     rcx, aWindowsNetwork_186; "Windows::Networking::UX::Internal::MBCa"...
0x180008c33  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x180008c38  mov     rcx, [rbp+18F0h+var_1970]
0x180008c3c  call    cs:__imp_WwanFreeMemory
0x180008c42  jmp     loc_180008AED
0x180008c47  mov     eax, [rsp+19F0h+var_1978]
0x180008c4b  mov     dword ptr [rsp+19F0h+var_19C8], eax
0x180008c4f  mov     dword ptr [rsp+19F0h+var_19D0], ebx
0x180008c53  mov     r9, rdi
0x180008c56  lea     r8, aFailedToCallWw_0; "Failed to call WwanProfileLoadXml. prof"...
0x180008c5d  mov     edx, 11F5h; unsigned int
0x180008c62  lea     rcx, aWindowsNetwork_186; "Windows::Networking::UX::Internal::MBCa"...
0x180008c69  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x180008c6e  mov     rcx, [rbp+18F0h+var_1970]
0x180008c72  call    cs:__imp_WwanFreeMemory
0x180008c78  jmp     loc_180008AED
```
