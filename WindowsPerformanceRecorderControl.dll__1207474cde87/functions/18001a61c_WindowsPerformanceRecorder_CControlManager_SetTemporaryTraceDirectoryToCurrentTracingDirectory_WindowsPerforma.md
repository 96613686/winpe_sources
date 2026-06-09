# WindowsPerformanceRecorder::CControlManager::SetTemporaryTraceDirectoryToCurrentTracingDirectory(WindowsPerformanceRecorder::Status::IControlInfo::CTraceType)

- ea: `0x18001a61c`
- end: `0x18001a6ca`
- name: `?SetTemporaryTraceDirectoryToCurrentTracingDirectory@CControlManager@WindowsPerformanceRecorder@@AEAAXUCTraceType@IControlInfo@Status@2@@Z`
- size: `174`
- prototype: `LSTATUS __fastcall(WindowsPerformanceRecorder::CControlManager *, char)`
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180031374`
- `0x18003a1f0`
- `0x180059060`
- `0x18005deb0`
- `0x180061780`

## callees

- `0x1800102a0`
- `0x1800138c0`
- `0x18001a61c`
- `0x18001c32c`
- `0x18002a6b4`
- `0x180036bfc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a6be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a6be`

## string_xrefs

- `0x18001a68f`: `TracePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
LSTATUS __fastcall WindowsPerformanceRecorder::CControlManager::SetTemporaryTraceDirectoryToCurrentTracingDirectory(
        WindowsPerformanceRecorder::CControlManager *a1,
        char a2)
{
  const unsigned __int16 *v3; // r8
  LSTATUS result; // eax
  char *v5; // rbx
  unsigned __int16 *v6; // rax
  HKEY hKey[4]; // [rsp+28h] [rbp-20h] BYREF
  unsigned int v8; // [rsp+58h] [rbp+10h] BYREF

  if ( (a2 & 1) != 0 || (v3 = L"Boot", (a2 & 2) != 0) )
    v3 = L"Normal";
  memset(hKey, 0, 24);
  result = WindowsPerformanceRecorder::CControlManager::GetWPRControlRegistryKey(a1, (struct ATL::CRegKey *)hKey, v3);
  if ( !result )
  {
    v8 = 260;
    v5 = (char *)a1 + 528;
    v6 = (unsigned __int16 *)ATL::CSimpleStringT<unsigned short,0>::PrepareWrite(v5, 260);
    if ( (unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)hKey, L"TracePath", v6, &v8) )
      result = ATL::CSimpleStringT<unsigned short,0>::Empty(v5);
    else
      result = ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(v5);
  }
  if ( hKey[0] )
    return RegCloseKey(hKey[0]);
  return result;
}

```

## disassembly

```asm
0x18001a61c  push    rbx
0x18001a61e  sub     rsp, 40h
0x18001a622  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x18001a62b  mov     rbx, rcx
0x18001a62e  test    dl, 1
0x18001a631  jnz     short loc_18001A63F
0x18001a633  test    dl, 2
0x18001a636  lea     r8, ?sc_wchWPRBootRegistryKey@CControlManager@WindowsPerformanceRecorder@@0QBGB; "Boot"
0x18001a63d  jz      short loc_18001A646
0x18001a63f  lea     r8, ?sc_wchWPRNormalRegistryKey@CControlManager@WindowsPerformanceRecorder@@0QBGB; "Normal"
0x18001a646  mov     [rsp+48h+hKey], 0
0x18001a64f  mov     [rsp+48h+var_18], 0
0x18001a658  mov     [rsp+48h+var_10], 0
0x18001a661  lea     rdx, [rsp+48h+hKey]; struct ATL::CRegKey *
0x18001a666  call    ?GetWPRControlRegistryKey@CControlManager@WindowsPerformanceRecorder@@AEBAJAEAVCRegKey@ATL@@PEBG@Z; WindowsPerformanceRecorder::CControlManager::GetWPRControlRegistryKey(ATL::CRegKey &,ushort const *)
0x18001a66b  test    eax, eax
0x18001a66d  jnz     short loc_18001A6B4
0x18001a66f  mov     edx, 104h
0x18001a674  mov     [rsp+48h+arg_8], edx
0x18001a678  add     rbx, 210h
0x18001a67f  mov     rcx, rbx
0x18001a682  call    ?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)
0x18001a687  lea     r9, [rsp+48h+arg_8]; unsigned int *
0x18001a68c  mov     r8, rax; unsigned __int16 *
0x18001a68f  lea     rdx, ?sc_wchWPRTracePath@CControlManager@WindowsPerformanceRecorder@@0QBGB; "TracePath"
0x18001a696  lea     rcx, [rsp+48h+hKey]; this
0x18001a69b  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x18001a6a0  mov     rcx, rbx
0x18001a6a3  test    eax, eax
0x18001a6a5  jnz     short loc_18001A6AE
0x18001a6a7  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x18001a6ac  jmp     short loc_18001A6B4
0x18001a6ae  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18001a6b3  nop
0x18001a6b4  mov     rcx, [rsp+48h+hKey]; hKey
0x18001a6b9  test    rcx, rcx
0x18001a6bc  jz      short loc_18001A6C4
0x18001a6be  call    cs:__imp_RegCloseKey
0x18001a6c4  add     rsp, 40h
0x18001a6c8  pop     rbx
0x18001a6c9  retn
```
