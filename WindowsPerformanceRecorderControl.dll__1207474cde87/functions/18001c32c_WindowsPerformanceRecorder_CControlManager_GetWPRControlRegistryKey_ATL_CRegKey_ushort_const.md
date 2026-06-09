# WindowsPerformanceRecorder::CControlManager::GetWPRControlRegistryKey(ATL::CRegKey &,ushort const *)

- ea: `0x18001c32c`
- end: `0x18001c452`
- name: `?GetWPRControlRegistryKey@CControlManager@WindowsPerformanceRecorder@@AEBAJAEAVCRegKey@ATL@@PEBG@Z`
- size: `294`
- prototype: `int(WindowsPerformanceRecorder::CControlManager *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180007c40`
- `0x18001a61c`
- `0x18001bf98`
- `0x18003175c`
- `0x18004865c`

## callees

- `0x180008270`
- `0x18000829c`
- `0x18000eeb0`
- `0x1800102d8`
- `0x1800131a0`
- `0x18001a8c8`
- `0x18001c32c`
- `0x180030bd4`
- `0x180038cd4`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c3e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c3e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::GetWPRControlRegistryKey(
        WindowsPerformanceRecorder::CControlManager *this,
        struct ATL::CRegKey *a2,
        const unsigned __int16 *a3)
{
  const WCHAR *v5; // rax
  LPCWSTR v6; // rbx
  LSTATUS v7; // ecx
  __int64 result; // rax
  unsigned int v9; // edi
  HKEY phkResult; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v11[8]; // [rsp+38h] [rbp-20h] BYREF
  __int64 v12; // [rsp+40h] [rbp-18h]
  ATL::CAtlException *v13; // [rsp+48h] [rbp-10h] BYREF
  LPCWSTR lpSubKey; // [rsp+78h] [rbp+20h] BYREF

  v12 = -2;
  v5 = (const WCHAR *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  lpSubKey = v5;
  try
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &lpSubKey,
      L"%ws\\%ws");
    if ( a3 )
    {
      ATL::CSimpleStringT<unsigned short,0>::AppendChar(&lpSubKey, 92);
      ATL::CSimpleStringT<unsigned short,0>::Append(&lpSubKey, a3);
    }
    WindowsPerformanceRecorder::CControlManager::SaveEventSession_::_64_::CPerfEventMacro::CPerfEventMacro(v11);
    phkResult = 0;
    v6 = lpSubKey;
    v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2001Fu, &phkResult);
    if ( v7 || (v7 = ATL::CRegKey::Close(a2), *(_QWORD *)a2 = phkResult, v7) )
    {
      v9 = ATL::AtlHresultFromWin32(v7);
      WindowsPerformanceRecorder::CControlManager::SaveStateInRegistry_::_14_::CPerfEventMacro::_CPerfEventMacro(v11);
      ATL::CStringData::Release((ATL::CStringData *)(v6 - 12));
      result = v9;
    }
    else
    {
      WindowsPerformanceRecorder::CControlManager::SaveStateInRegistry_::_14_::CPerfEventMacro::_CPerfEventMacro(v11);
      ATL::CStringData::Release((ATL::CStringData *)(v6 - 12));
      result = 0;
    }
  }
  catch ( ATL::CAtlException *v13 )
  {
    return *(unsigned int *)v13;
  }
  return result;
}

```

## disassembly

```asm
0x18001c32c  push    rdi
0x18001c32e  sub     rsp, 50h
0x18001c332  mov     [rsp+58h+var_18], 0FFFFFFFFFFFFFFFEh
0x18001c33b  mov     [rsp+58h+arg_0], rbx
0x18001c340  mov     [rsp+58h+arg_8], rsi
0x18001c345  mov     rbx, r8
0x18001c348  mov     rdi, rdx
0x18001c34b  mov     rsi, rcx
0x18001c34e  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001c355  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001c35c  mov     rax, [rax+18h]
0x18001c360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c365  add     rax, 18h
0x18001c369  mov     [rsp+58h+lpSubKey], rax
0x18001c36e  mov     r9, [rsi+0E0h]
0x18001c375  lea     r8, ?sc_wchWPRControlRegistryKey@CControlManager@WindowsPerformanceRecorder@@0QBGB; "Software\\Microsoft\\Windows Performanc"...
0x18001c37c  lea     rdx, aWsWs_5; "%ws\\%ws"
0x18001c383  lea     rcx, [rsp+58h+lpSubKey]
0x18001c388  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18001c38d  test    rbx, rbx
0x18001c390  jz      short loc_18001C3AE
0x18001c392  mov     edx, 5Ch ; '\'
0x18001c397  lea     rcx, [rsp+58h+lpSubKey]
0x18001c39c  call    ?AppendChar@?$CSimpleStringT@G$0A@@ATL@@QEAAXG@Z; ATL::CSimpleStringT<ushort,0>::AppendChar(ushort)
0x18001c3a1  mov     rdx, rbx
0x18001c3a4  lea     rcx, [rsp+58h+lpSubKey]
0x18001c3a9  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18001c3ae  lea     rcx, [rsp+58h+var_20]
0x18001c3b3  call    _WindowsPerformanceRecorder__CControlManager__SaveEventSession____64___CPerfEventMacro__CPerfEventMacro
0x18001c3b8  mov     [rsp+58h+var_28], 0
0x18001c3c1  lea     rax, [rsp+58h+var_28]
0x18001c3c6  mov     [rsp+58h+phkResult], rax; phkResult
0x18001c3cb  mov     r9d, 2001Fh; samDesired
0x18001c3d1  xor     r8d, r8d; ulOptions
0x18001c3d4  mov     rbx, [rsp+58h+lpSubKey]
0x18001c3d9  mov     rdx, rbx; lpSubKey
0x18001c3dc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c3e3  call    cs:__imp_RegOpenKeyExW
0x18001c3e9  mov     ecx, eax; unsigned int
0x18001c3eb  test    eax, eax
0x18001c3ed  jnz     short loc_18001C41E
0x18001c3ef  mov     rcx, rdi; this
0x18001c3f2  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001c3f7  mov     ecx, eax
0x18001c3f9  mov     rax, [rsp+58h+var_28]
0x18001c3fe  mov     [rdi], rax
0x18001c401  test    ecx, ecx
0x18001c403  jnz     short loc_18001C41E
0x18001c405  lea     rcx, [rsp+58h+var_20]
0x18001c40a  call    _WindowsPerformanceRecorder__CControlManager__SaveStateInRegistry____14___CPerfEventMacro___CPerfEventMacro
0x18001c40f  nop
0x18001c410  lea     rcx, [rbx-18h]; this
0x18001c414  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001c419  nop
0x18001c41a  xor     eax, eax
0x18001c41c  jmp     short loc_18001C441
0x18001c41e  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18001c423  mov     edi, eax
0x18001c425  lea     rcx, [rsp+58h+var_20]
0x18001c42a  call    _WindowsPerformanceRecorder__CControlManager__SaveStateInRegistry____14___CPerfEventMacro___CPerfEventMacro
0x18001c42f  nop
0x18001c430  lea     rcx, [rbx-18h]; this
0x18001c434  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001c439  mov     eax, edi
0x18001c43b  jmp     short loc_18001C441
0x18001c43d  mov     eax, dword ptr [rsp+58h+lpSubKey]
0x18001c441  mov     rbx, [rsp+58h+arg_0]
0x18001c446  mov     rsi, [rsp+58h+arg_8]
0x18001c44b  add     rsp, 50h
0x18001c44f  pop     rdi
0x18001c450  retn
```
