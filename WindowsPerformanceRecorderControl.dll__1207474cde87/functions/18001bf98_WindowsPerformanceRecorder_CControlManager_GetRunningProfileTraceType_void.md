# WindowsPerformanceRecorder::CControlManager::GetRunningProfileTraceType(void)

- ea: `0x18001bf98`
- end: `0x18001c326`
- name: `?GetRunningProfileTraceType@CControlManager@WindowsPerformanceRecorder@@AEAAJXZ`
- size: `910`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CControlManager *__hidden this)`
- caller_count: `12`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18001c8bc`
- `0x180031374`
- `0x180032adc`
- `0x18003a1f0`
- `0x18004ac00`
- `0x180058800`
- `0x180059060`
- `0x18005d1bc`
- `0x18005deb0`
- `0x18005f068`
- `0x180061780`
- `0x1800629a0`

## callees

- `0x180008270`
- `0x18000eeb0`
- `0x18000fe14`
- `0x1800102d8`
- `0x18001bf98`
- `0x18001c32c`
- `0x18001c458`
- `0x18001e6e0`
- `0x180038a70`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c048`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c219`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c048`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c219`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001c0e4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001c0e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c1b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c28b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c2fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c1b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c28b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c2fb`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::GetRunningProfileTraceType(
        WindowsPerformanceRecorder::CControlManager *this)
{
  unsigned int v2; // r14d
  __int64 v3; // rax
  HKEY v4; // rdi
  LSTATUS v5; // ecx
  int v6; // eax
  HKEY v7; // rdi
  HKEY v8; // rsi
  LSTATUS v9; // ecx
  int v10; // eax
  __int64 result; // rax
  const char *lpcbData; // [rsp+28h] [rbp-80h]
  ATL::CAtlException *v13; // [rsp+48h] [rbp-60h] BYREF
  HKEY hKey[3]; // [rsp+50h] [rbp-58h] BYREF
  HKEY v15; // [rsp+68h] [rbp-40h] BYREF
  __int64 v16; // [rsp+70h] [rbp-38h]
  __int64 v17; // [rsp+78h] [rbp-30h]
  HKEY phkResult; // [rsp+B0h] [rbp+8h] BYREF
  DWORD Type; // [rsp+B8h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+C0h] [rbp+18h] BYREF
  __int64 v21; // [rsp+C8h] [rbp+20h] BYREF

  v2 = 0;
  *((_DWORD *)this + 142) = 0;
  memset(hKey, 0, sizeof(hKey));
  v3 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
  try
  {
    v21 = v3 + 24;
    if ( WindowsPerformanceRecorder::CControlManager::GetWPRControlRegistryKey(
           this,
           (struct ATL::CRegKey *)hKey,
           L"Normal") < 0 )
    {
LABEL_16:
      if ( WindowsPerformanceRecorder::CControlManager::GetWPRControlRegistryKey(
             this,
             (struct ATL::CRegKey *)hKey,
             L"Boot") < 0 )
      {
        v8 = hKey[0];
      }
      else
      {
        v7 = 0;
        v15 = 0;
        v16 = 0;
        v17 = 0;
        phkResult = 0;
        v8 = hKey[0];
        v9 = RegOpenKeyExW(hKey[0], L"SystemRunning", 0, 0x2001Fu, &phkResult);
        if ( !v9 )
        {
          v9 = ATL::CRegKey::Close((ATL::CRegKey *)&v15);
          v7 = phkResult;
          v15 = phkResult;
        }
        v10 = *((_DWORD *)this + 142);
        if ( v9 )
        {
          *((_DWORD *)this + 142) = v10 | 8;
          ATL::CSimpleStringT<unsigned short,0>::Append(&v21, L" Boot");
        }
        else
        {
          *((_DWORD *)this + 142) = v10 | 4;
          ATL::CSimpleStringT<unsigned short,0>::Append(&v21, L" PreBoot", 8);
        }
        if ( v7 )
          RegCloseKey(v7);
      }
      if ( *((_DWORD *)this + 142) )
      {
        LODWORD(lpcbData) = *((_DWORD *)this + 142);
        WindowsPerformanceRecorder::TraceHR(
          (WindowsPerformanceRecorder *)4,
          (unsigned __int8)"GetRunningProfileTraceType",
          (const char *)0x14F4,
          0,
          "Current m_TraceType(0x%x): %ws",
          lpcbData,
          v21);
      }
      else
      {
        v2 = -984076288;
      }
      ATL::CStringData::Release((ATL::CStringData *)(v21 - 24));
      if ( v8 )
        RegCloseKey(v8);
      return v2;
    }
    v4 = 0;
    v15 = 0;
    v16 = 0;
    v17 = 0;
    phkResult = 0;
    v5 = RegOpenKeyExW(hKey[0], L"SystemRunning", 0, 0x2001Fu, &phkResult);
    if ( !v5 )
    {
      v5 = ATL::CRegKey::Close((ATL::CRegKey *)&v15);
      v4 = phkResult;
      v15 = phkResult;
    }
    v6 = *((_DWORD *)this + 142);
    if ( v5 )
    {
      *((_DWORD *)this + 142) = v6 | 2;
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v21, L"LastShutdown");
      LODWORD(phkResult) = 0;
      if ( !(unsigned int)ATL::CRegKey::QueryDWORDValue((ATL::CRegKey *)hKey, L"Shutdown", (unsigned int *)&phkResult)
        && (_DWORD)phkResult == 2 )
      {
        goto LABEL_13;
      }
    }
    else
    {
      *((_DWORD *)this + 142) = v6 | 1;
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v21, L"Normal");
      LODWORD(phkResult) = 0;
      Type = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey[0], L"Shutdown", 0, &Type, (LPBYTE)&phkResult, &cbData) && Type == 4 )
      {
        if ( (_DWORD)phkResult )
        {
          *((_DWORD *)this + 142) |= 0x10u;
          ATL::CSimpleStringT<unsigned short,0>::Append(&v21, L" PreShutdown");
          if ( (_DWORD)phkResult == 2 )
          {
LABEL_13:
            *((_DWORD *)this + 142) |= 0x20u;
            ATL::CSimpleStringT<unsigned short,0>::Append(&v21, L"(KSR)");
          }
        }
      }
    }
    if ( v4 )
      RegCloseKey(v4);
    goto LABEL_16;
  }
  catch ( ATL::CAtlException *v13 )
  {
    LODWORD(phkResult) = *(_DWORD *)v13;
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
    return (unsigned int)phkResult;
  }
  return result;
}

```

## disassembly

```asm
0x18001bf98  mov     rax, rsp
0x18001bf9b  push    rbx
0x18001bf9c  push    rsi
0x18001bf9d  push    rdi
0x18001bf9e  push    r14
0x18001bfa0  push    r15
0x18001bfa2  sub     rsp, 80h
0x18001bfa9  mov     qword ptr [rax-68h], 0FFFFFFFFFFFFFFFEh
0x18001bfb1  mov     rbx, rcx
0x18001bfb4  xor     r15d, r15d
0x18001bfb7  mov     r14d, r15d
0x18001bfba  mov     [rcx+238h], r15d
0x18001bfc1  mov     [rax-58h], r15
0x18001bfc5  mov     [rax-50h], r15
0x18001bfc9  mov     [rax-48h], r15
0x18001bfcd  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001bfd4  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001bfdb  mov     rax, [rax+18h]
0x18001bfdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bfe4  add     rax, 18h
0x18001bfe8  mov     [rsp+0A8h+arg_18], rax
0x18001bff0  lea     r8, ?sc_wchWPRNormalRegistryKey@CControlManager@WindowsPerformanceRecorder@@0QBGB; "Normal"
0x18001bff7  lea     rdx, [rsp+0A8h+hKey]; struct ATL::CRegKey *
0x18001bffc  mov     rcx, rbx; this
0x18001bfff  call    ?GetWPRControlRegistryKey@CControlManager@WindowsPerformanceRecorder@@AEBAJAEAVCRegKey@ATL@@PEBG@Z; WindowsPerformanceRecorder::CControlManager::GetWPRControlRegistryKey(ATL::CRegKey &,ushort const *)
0x18001c004  test    eax, eax
0x18001c006  js      loc_18001C1BE
0x18001c00c  mov     edi, r15d
0x18001c00f  mov     [rsp+0A8h+var_40], r15
0x18001c014  mov     [rsp+0A8h+var_38], r15
0x18001c019  mov     [rsp+0A8h+var_30], r15
0x18001c01e  mov     [rsp+0A8h+arg_0], r15
0x18001c026  lea     rax, [rsp+0A8h+arg_0]
0x18001c02e  mov     [rsp+0A8h+phkResult], rax; phkResult
0x18001c033  mov     r9d, 2001Fh; samDesired
0x18001c039  xor     r8d, r8d; ulOptions
0x18001c03c  lea     rdx, ?sc_wchWPRSystemRunningRegistryKey@CControlManager@WindowsPerformanceRecorder@@0QBGB; "SystemRunning"
0x18001c043  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18001c048  call    cs:__imp_RegOpenKeyExW
0x18001c04e  mov     ecx, eax
0x18001c050  test    eax, eax
0x18001c052  jnz     short loc_18001C06D
0x18001c054  lea     rcx, [rsp+0A8h+var_40]; this
0x18001c059  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001c05e  mov     ecx, eax
0x18001c060  mov     rdi, [rsp+0A8h+arg_0]
0x18001c068  mov     [rsp+0A8h+var_40], rdi
0x18001c06d  mov     eax, [rbx+238h]
0x18001c073  test    ecx, ecx
0x18001c075  lea     rcx, [rsp+0A8h+arg_18]
0x18001c07d  jnz     loc_18001C150
0x18001c083  or      eax, 1
0x18001c086  mov     [rbx+238h], eax
0x18001c08c  lea     rdx, ?sc_wchWPRNormalRegistryKey@CControlManager@WindowsPerformanceRecorder@@0QBGB; "Normal"
0x18001c093  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18001c098  mov     dword ptr [rsp+0A8h+arg_0], r15d
0x18001c0a0  mov     [rsp+0A8h+Type], r15d
0x18001c0a8  mov     [rsp+0A8h+cbData], 4
0x18001c0b3  lea     rax, [rsp+0A8h+cbData]
0x18001c0bb  mov     [rsp+0A8h+lpcbData], rax; lpcbData
0x18001c0c0  lea     rax, [rsp+0A8h+arg_0]
0x18001c0c8  mov     [rsp+0A8h+phkResult], rax; lpData
0x18001c0cd  lea     r9, [rsp+0A8h+Type]; lpType
0x18001c0d5  xor     r8d, r8d; lpReserved
0x18001c0d8  lea     rdx, ?sc_wchShutdownFileNameTag@CControlManager@WindowsPerformanceRecorder@@0QBGB; "Shutdown"
0x18001c0df  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18001c0e4  call    cs:__imp_RegQueryValueExW
0x18001c0ea  test    eax, eax
0x18001c0ec  jnz     loc_18001C1B0
0x18001c0f2  cmp     [rsp+0A8h+Type], 4
0x18001c0fa  jnz     loc_18001C1B0
0x18001c100  cmp     dword ptr [rsp+0A8h+arg_0], r15d
0x18001c108  jbe     loc_18001C1B0
0x18001c10e  or      dword ptr [rbx+238h], 10h
0x18001c115  lea     rdx, aPreshutdown; " PreShutdown"
0x18001c11c  lea     rcx, [rsp+0A8h+arg_18]
0x18001c124  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18001c129  cmp     dword ptr [rsp+0A8h+arg_0], 2
0x18001c131  jnz     short loc_18001C1B0
0x18001c133  or      dword ptr [rbx+238h], 20h
0x18001c13a  lea     rdx, aKsr; "(KSR)"
0x18001c141  lea     rcx, [rsp+0A8h+arg_18]
0x18001c149  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18001c14e  jmp     short loc_18001C1B0
0x18001c150  or      eax, 2
0x18001c153  mov     [rbx+238h], eax
0x18001c159  lea     rdx, aLastshutdown; "LastShutdown"
0x18001c160  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18001c165  mov     dword ptr [rsp+0A8h+arg_0], r15d
0x18001c16d  lea     r8, [rsp+0A8h+arg_0]; unsigned int *
0x18001c175  lea     rdx, ?sc_wchShutdownFileNameTag@CControlManager@WindowsPerformanceRecorder@@0QBGB; "Shutdown"
0x18001c17c  lea     rcx, [rsp+0A8h+hKey]; this
0x18001c181  call    ?QueryDWORDValue@CRegKey@ATL@@QEAAJPEBGAEAK@Z; ATL::CRegKey::QueryDWORDValue(ushort const *,ulong &)
0x18001c186  test    eax, eax
0x18001c188  jnz     short loc_18001C1B0
0x18001c18a  cmp     dword ptr [rsp+0A8h+arg_0], 2
0x18001c192  jnz     short loc_18001C1B0
0x18001c194  or      dword ptr [rbx+238h], 20h
0x18001c19b  lea     rdx, aKsr; "(KSR)"
0x18001c1a2  lea     rcx, [rsp+0A8h+arg_18]
0x18001c1aa  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18001c1af  nop
0x18001c1b0  test    rdi, rdi
0x18001c1b3  jz      short loc_18001C1BE
0x18001c1b5  mov     rcx, rdi; hKey
0x18001c1b8  call    cs:__imp_RegCloseKey
0x18001c1be  lea     r8, ?sc_wchWPRBootRegistryKey@CControlManager@WindowsPerformanceRecorder@@0QBGB; "Boot"
0x18001c1c5  lea     rdx, [rsp+0A8h+hKey]; struct ATL::CRegKey *
0x18001c1ca  mov     rcx, rbx; this
0x18001c1cd  call    ?GetWPRControlRegistryKey@CControlManager@WindowsPerformanceRecorder@@AEBAJAEAVCRegKey@ATL@@PEBG@Z; WindowsPerformanceRecorder::CControlManager::GetWPRControlRegistryKey(ATL::CRegKey &,ushort const *)
0x18001c1d2  test    eax, eax
0x18001c1d4  js      loc_18001C293
0x18001c1da  mov     rdi, r15
0x18001c1dd  mov     [rsp+0A8h+var_40], r15
0x18001c1e2  mov     [rsp+0A8h+var_38], r15
0x18001c1e7  mov     [rsp+0A8h+var_30], r15
0x18001c1ec  mov     [rsp+0A8h+arg_0], r15
0x18001c1f4  lea     rax, [rsp+0A8h+arg_0]
0x18001c1fc  mov     [rsp+0A8h+phkResult], rax; phkResult
0x18001c201  mov     r9d, 2001Fh; samDesired
0x18001c207  xor     r8d, r8d; ulOptions
0x18001c20a  lea     rdx, ?sc_wchWPRSystemRunningRegistryKey@CControlManager@WindowsPerformanceRecorder@@0QBGB; "SystemRunning"
0x18001c211  mov     rsi, [rsp+0A8h+hKey]
0x18001c216  mov     rcx, rsi; hKey
0x18001c219  call    cs:__imp_RegOpenKeyExW
0x18001c21f  mov     ecx, eax
0x18001c221  test    eax, eax
0x18001c223  jnz     short loc_18001C23E
0x18001c225  lea     rcx, [rsp+0A8h+var_40]; this
0x18001c22a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001c22f  mov     ecx, eax
0x18001c231  mov     rdi, [rsp+0A8h+arg_0]
0x18001c239  mov     [rsp+0A8h+var_40], rdi
0x18001c23e  mov     eax, [rbx+238h]
0x18001c244  test    ecx, ecx
0x18001c246  lea     rcx, [rsp+0A8h+arg_18]
0x18001c24e  jnz     short loc_18001C26D
0x18001c250  or      eax, 4
0x18001c253  mov     [rbx+238h], eax
0x18001c259  mov     r8d, 8
0x18001c25f  lea     rdx, aPreboot; " PreBoot"
0x18001c266  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18001c26b  jmp     short loc_18001C283
0x18001c26d  or      eax, 8
0x18001c270  mov     [rbx+238h], eax
0x18001c276  lea     rdx, aBoot; " Boot"
0x18001c27d  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18001c282  nop
0x18001c283  test    rdi, rdi
0x18001c286  jz      short loc_18001C298
0x18001c288  mov     rcx, rdi; hKey
0x18001c28b  call    cs:__imp_RegCloseKey
0x18001c291  jmp     short loc_18001C298
0x18001c293  mov     rsi, [rsp+0A8h+hKey]
0x18001c298  mov     ecx, [rbx+238h]
0x18001c29e  test    ecx, ecx
0x18001c2a0  jnz     short loc_18001C2AA
0x18001c2a2  mov     r14d, 0C5583000h
0x18001c2a8  jmp     short loc_18001C2E1
0x18001c2aa  mov     rax, [rsp+0A8h+arg_18]
0x18001c2b2  mov     [rsp+0A8h+var_78], rax
0x18001c2b7  mov     dword ptr [rsp+0A8h+lpcbData], ecx; char *
0x18001c2bb  lea     rax, aCurrentMTracet; "Current m_TraceType(0x%x): %ws"
0x18001c2c2  mov     [rsp+0A8h+phkResult], rax; Format
0x18001c2c7  xor     r9d, r9d; unsigned int
0x18001c2ca  mov     r8d, 14F4h; char *
0x18001c2d0  lea     rdx, aGetrunningprof; "GetRunningProfileTraceType"
0x18001c2d7  lea     ecx, [r9+4]; this
0x18001c2db  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18001c2e0  nop
0x18001c2e1  mov     rcx, [rsp+0A8h+arg_18]
0x18001c2e9  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001c2ed  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001c2f2  nop
0x18001c2f3  test    rsi, rsi
0x18001c2f6  jz      short loc_18001C301
0x18001c2f8  mov     rcx, rsi; hKey
0x18001c2fb  call    cs:__imp_RegCloseKey
0x18001c301  mov     eax, r14d
0x18001c304  jmp     short loc_18001C317
0x18001c306  lea     rcx, [rsp+0A8h+hKey]; this
0x18001c30b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001c310  mov     eax, dword ptr [rsp+0A8h+arg_0]
0x18001c317  add     rsp, 80h
0x18001c31e  pop     r15
0x18001c320  pop     r14
0x18001c322  pop     rdi
0x18001c323  pop     rsi
0x18001c324  pop     rbx
0x18001c325  retn
```
