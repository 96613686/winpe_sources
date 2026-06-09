# ShouldSecurebootSkipDBXUpdateOnHP(int *,ushort const * *)

- ea: `0x18003dce8`
- end: `0x18003de9d`
- name: `?ShouldSecurebootSkipDBXUpdateOnHP@@YAJPEAHPEAPEBG@Z`
- size: `437`
- prototype: `__int64 __fastcall(int *, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x18003d8e0`

## callees

- `0x1800394b0`
- `0x18003c0b8`
- `0x18003c688`
- `0x18003d0e8`
- `0x18003dce8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003de30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003de49`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003de62`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003de30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003de49`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003de62`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003de21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003de3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003de54`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003de21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003de3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003de54`
- `SHLWAPI!StrCmpIW` at `0x18003dd4d`
- `SHLWAPI!StrCmpIW` at `0x18003dd4d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18003ddbc`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18003ddbc`

## string_xrefs

- `0x18003dd2f`: `SystemManufacturerRegistryFailed`
- `0x18003dda9`: `SystemVersionRegistryFailed`
- `0x18003dd78`: `BaseBoardProductRegistryFailed`
- `0x18003ddca`: `This HP machine is updated with SBKPF, no need to skip DBX update SystemVersion %ls`
- `0x18003de6f`: `ShouldSecurebootSkipDBXUpdateOnHP failed with error %x actionString %ls`
- `0x18003de0e`: `Skipping DBX update on HP %ls due to known bad baseBoardProduct`
- `0x18003de80`: `ShouldSecurebootSkipDBXUpdateOnHP`

## pseudocode

```c
__int64 __fastcall ShouldSecurebootSkipDBXUpdateOnHP(int *a1, const unsigned __int16 **a2)
{
  unsigned __int16 *v2; // rbx
  WCHAR *v5; // rsi
  int HWSystemInformationFromRegistry; // edi
  const unsigned __int16 *v7; // r14
  int v8; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v10; // rax
  HANDLE v11; // rax
  unsigned __int16 *v13; // [rsp+60h] [rbp+40h] BYREF
  PCWSTR psz1; // [rsp+70h] [rbp+50h] BYREF
  PCWSTR pszFirst; // [rsp+78h] [rbp+58h] BYREF

  v2 = 0;
  *a1 = 0;
  v13 = 0;
  v5 = 0;
  psz1 = 0;
  pszFirst = 0;
  HWSystemInformationFromRegistry = GetHWSystemInformationFromRegistry(
                                      L"HARDWARE\\DESCRIPTION\\System\\BIOS",
                                      L"SystemManufacturer",
                                      (unsigned __int16 **)&psz1);
  if ( HWSystemInformationFromRegistry < 0 )
  {
    v7 = L"SystemManufacturerRegistryFailed";
    goto LABEL_13;
  }
  v7 = L"Passed";
  if ( !StrCmpIW(psz1, L"HP") )
  {
    HWSystemInformationFromRegistry = GetHWSystemInformationFromRegistry(
                                        L"HARDWARE\\DESCRIPTION\\System\\BIOS",
                                        L"BaseBoardProduct",
                                        &v13);
    if ( HWSystemInformationFromRegistry < 0 )
    {
      v7 = L"BaseBoardProductRegistryFailed";
LABEL_6:
      v2 = v13;
      goto LABEL_13;
    }
    v8 = GetHWSystemInformationFromRegistry(
           L"HARDWARE\\DESCRIPTION\\System\\BIOS",
           L"SystemVersion",
           (unsigned __int16 **)&pszFirst);
    v5 = (WCHAR *)pszFirst;
    HWSystemInformationFromRegistry = v8;
    if ( v8 < 0 )
    {
      v7 = L"SystemVersionRegistryFailed";
      goto LABEL_6;
    }
    if ( StrStrIW(pszFirst, L"SBKPF") )
    {
      SBServicingLogMessage(
        (wchar_t *)L"This HP machine is updated with SBKPF, no need to skip DBX update SystemVersion %ls",
        v5);
      HWSystemInformationFromRegistry = 0;
      goto LABEL_6;
    }
    v2 = v13;
    if ( LookupStringInArray((const unsigned __int16 *const *const)&g_HPBadBaseBoardProductList, 0x46u, v13, 0) )
    {
      *a1 = 1;
      *a2 = L"HPBadBaseBoardProductDBX";
      SBServicingLogMessage((wchar_t *)L"Skipping DBX update on HP %ls due to known bad baseBoardProduct", v2);
    }
  }
LABEL_13:
  if ( psz1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)psz1);
  }
  if ( v2 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v2);
  }
  if ( v5 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v5);
  }
  if ( HWSystemInformationFromRegistry < 0 )
  {
    SBServicingLogMessage(
      (wchar_t *)L"ShouldSecurebootSkipDBXUpdateOnHP failed with error %x actionString %ls",
      (unsigned int)HWSystemInformationFromRegistry,
      v7);
    SBServicingCoreTelemetryProvider::SBServicingCoreFunctionFailed(L"ShouldSecurebootSkipDBXUpdateOnHP", v7);
  }
  return (unsigned int)HWSystemInformationFromRegistry;
}

```

## disassembly

```asm
0x18003dce8  push    rbp
0x18003dcea  push    rbx
0x18003dceb  push    rsi
0x18003dcec  push    rdi
0x18003dced  push    r12
0x18003dcef  push    r13
0x18003dcf1  push    r14
0x18003dcf3  mov     rbp, rsp
0x18003dcf6  sub     rsp, 20h
0x18003dcfa  xor     ebx, ebx
0x18003dcfc  lea     r8, [rbp+psz1]; unsigned __int16 **
0x18003dd00  mov     [rcx], ebx
0x18003dd02  mov     r13, rdx
0x18003dd05  mov     r12, rcx
0x18003dd08  mov     [rbp+arg_0], rbx
0x18003dd0c  xor     esi, esi
0x18003dd0e  mov     [rbp+psz1], rbx
0x18003dd12  lea     rcx, aHardwareDescri; "HARDWARE\\DESCRIPTION\\System\\BIOS"
0x18003dd19  mov     [rbp+pszFirst], rsi
0x18003dd1d  lea     rdx, aSystemmanufact_0; "SystemManufacturer"
0x18003dd24  call    ?GetHWSystemInformationFromRegistry@@YAJPEBG0PEAPEAG@Z; GetHWSystemInformationFromRegistry(ushort const *,ushort const *,ushort * *)
0x18003dd29  mov     edi, eax
0x18003dd2b  test    eax, eax
0x18003dd2d  jns     short loc_18003DD3B
0x18003dd2f  lea     r14, aSystemmanufact_1; "SystemManufacturerRegistryFailed"
0x18003dd36  jmp     loc_18003DE1A
0x18003dd3b  mov     rcx, [rbp+psz1]; psz1
0x18003dd3f  lea     rdx, aHp; "HP"
0x18003dd46  lea     r14, aPassed; "Passed"
0x18003dd4d  call    cs:__imp_StrCmpIW
0x18003dd53  test    eax, eax
0x18003dd55  jnz     loc_18003DE1A
0x18003dd5b  lea     r8, [rbp+arg_0]; unsigned __int16 **
0x18003dd5f  lea     rdx, aBaseboardprodu_0; "BaseBoardProduct"
0x18003dd66  lea     rcx, aHardwareDescri; "HARDWARE\\DESCRIPTION\\System\\BIOS"
0x18003dd6d  call    ?GetHWSystemInformationFromRegistry@@YAJPEBG0PEAPEAG@Z; GetHWSystemInformationFromRegistry(ushort const *,ushort const *,ushort * *)
0x18003dd72  mov     edi, eax
0x18003dd74  test    eax, eax
0x18003dd76  jns     short loc_18003DD88
0x18003dd78  lea     r14, aBaseboardprodu; "BaseBoardProductRegistryFailed"
0x18003dd7f  mov     rbx, [rbp+arg_0]
0x18003dd83  jmp     loc_18003DE1A
0x18003dd88  lea     r8, [rbp+pszFirst]; unsigned __int16 **
0x18003dd8c  lea     rdx, aSystemversion; "SystemVersion"
0x18003dd93  lea     rcx, aHardwareDescri; "HARDWARE\\DESCRIPTION\\System\\BIOS"
0x18003dd9a  call    ?GetHWSystemInformationFromRegistry@@YAJPEBG0PEAPEAG@Z; GetHWSystemInformationFromRegistry(ushort const *,ushort const *,ushort * *)
0x18003dd9f  mov     rsi, [rbp+pszFirst]
0x18003dda3  mov     edi, eax
0x18003dda5  test    eax, eax
0x18003dda7  jns     short loc_18003DDB2
0x18003dda9  lea     r14, aSystemversionr; "SystemVersionRegistryFailed"
0x18003ddb0  jmp     short loc_18003DD7F
0x18003ddb2  lea     rdx, aSbkpf; "SBKPF"
0x18003ddb9  mov     rcx, rsi; pszFirst
0x18003ddbc  call    cs:__imp_StrStrIW
0x18003ddc2  test    rax, rax
0x18003ddc5  jz      short loc_18003DDDA
0x18003ddc7  mov     rdx, rsi
0x18003ddca  lea     rcx, aThisHpMachineI; "This HP machine is updated with SBKPF, "...
0x18003ddd1  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003ddd6  xor     edi, edi
0x18003ddd8  jmp     short loc_18003DD7F
0x18003ddda  mov     rbx, [rbp+arg_0]
0x18003ddde  lea     rcx, ?g_HPBadBaseBoardProductList@@3QBQEBGB; unsigned __int16 **
0x18003dde5  xor     r9d, r9d; int
0x18003dde8  mov     r8, rbx; unsigned __int16 *
0x18003ddeb  lea     edx, [r9+46h]; unsigned __int64
0x18003ddef  call    ?LookupStringInArray@@YAHQEBQEBG_KPEBGH@Z; LookupStringInArray(ushort const * const * const,unsigned __int64,ushort const *,int)
0x18003ddf4  test    eax, eax
0x18003ddf6  jz      short loc_18003DE1A
0x18003ddf8  lea     rax, aHpbadbaseboard; "HPBadBaseBoardProductDBX"
0x18003ddff  mov     dword ptr [r12], 1
0x18003de07  mov     rdx, rbx
0x18003de0a  mov     [r13+0], rax
0x18003de0e  lea     rcx, aSkippingDbxUpd; "Skipping DBX update on HP %ls due to kn"...
0x18003de15  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003de1a  cmp     [rbp+psz1], 0
0x18003de1f  jz      short loc_18003DE36
0x18003de21  call    cs:__imp_GetProcessHeap
0x18003de27  mov     r8, [rbp+psz1]; lpMem
0x18003de2b  xor     edx, edx; dwFlags
0x18003de2d  mov     rcx, rax; hHeap
0x18003de30  call    cs:__imp_HeapFree
0x18003de36  test    rbx, rbx
0x18003de39  jz      short loc_18003DE4F
0x18003de3b  call    cs:__imp_GetProcessHeap
0x18003de41  mov     r8, rbx; lpMem
0x18003de44  xor     edx, edx; dwFlags
0x18003de46  mov     rcx, rax; hHeap
0x18003de49  call    cs:__imp_HeapFree
0x18003de4f  test    rsi, rsi
0x18003de52  jz      short loc_18003DE68
0x18003de54  call    cs:__imp_GetProcessHeap
0x18003de5a  mov     r8, rsi; lpMem
0x18003de5d  xor     edx, edx; dwFlags
0x18003de5f  mov     rcx, rax; hHeap
0x18003de62  call    cs:__imp_HeapFree
0x18003de68  test    edi, edi
0x18003de6a  jns     short loc_18003DE8C
0x18003de6c  mov     r8, r14
0x18003de6f  lea     rcx, aShouldsecurebo_11; "ShouldSecurebootSkipDBXUpdateOnHP faile"...
0x18003de76  mov     edx, edi
0x18003de78  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003de7d  mov     rdx, r14; unsigned __int16 *
0x18003de80  lea     rcx, aShouldsecurebo_3; "ShouldSecurebootSkipDBXUpdateOnHP"
0x18003de87  call    ?SBServicingCoreFunctionFailed@SBServicingCoreTelemetryProvider@@SAXPEBG0@Z; SBServicingCoreTelemetryProvider::SBServicingCoreFunctionFailed(ushort const *,ushort const *)
0x18003de8c  mov     eax, edi
0x18003de8e  add     rsp, 20h
0x18003de92  pop     r14
0x18003de94  pop     r13
0x18003de96  pop     r12
0x18003de98  pop     rdi
0x18003de99  pop     rsi
0x18003de9a  pop     rbx
0x18003de9b  pop     rbp
0x18003de9c  retn
```
