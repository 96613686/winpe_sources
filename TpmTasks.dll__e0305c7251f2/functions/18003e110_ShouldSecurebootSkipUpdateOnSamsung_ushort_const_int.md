# ShouldSecurebootSkipUpdateOnSamsung(ushort const *,int *)

- ea: `0x18003e110`
- end: `0x18003e2c5`
- name: `?ShouldSecurebootSkipUpdateOnSamsung@@YAJPEBGPEAH@Z`
- size: `437`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003d8e0`

## callees

- `0x18003c0b8`
- `0x18003c254`
- `0x18003c688`
- `0x18003d0e8`
- `0x18003e110`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e27a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e293`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e2b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e27a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e293`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003e2b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e26c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e285`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e2a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e26c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e285`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003e2a1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003e1cb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003e1cb`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18003e140`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18003e140`

## string_xrefs

- `0x18003e24e`: `Skipping update on %ls %ls due to known bad SKU biosReleaseDate %ls`
- `0x18003e1ed`: `Skipping update on %ls %ls due to old BIOS version %ls (required: %ls)`

## pseudocode

```c
__int64 __fastcall ShouldSecurebootSkipUpdateOnSamsung(const unsigned __int16 *a1, int *a2)
{
  unsigned __int16 *v2; // rbx
  int HWSystemInformationFromRegistry; // edi
  WCHAR *v5; // rsi
  int v7; // eax
  int v8; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v10; // rax
  HANDLE v11; // rax
  LPVOID lpMem; // [rsp+68h] [rbp+10h] BYREF
  LPCWCH lpString1; // [rsp+70h] [rbp+18h] BYREF
  unsigned __int16 *v15; // [rsp+78h] [rbp+20h] BYREF

  v2 = 0;
  *a2 = 0;
  HWSystemInformationFromRegistry = 0;
  v5 = 0;
  lpMem = 0;
  v15 = 0;
  lpString1 = 0;
  if ( !StrStrIW(a1, L"SAMSUNG") )
    return (unsigned int)HWSystemInformationFromRegistry;
  HWSystemInformationFromRegistry = GetHWSystemInformationFromRegistry(
                                      L"HARDWARE\\DESCRIPTION\\System\\BIOS",
                                      L"SystemSKU",
                                      (unsigned __int16 **)&lpMem);
  if ( HWSystemInformationFromRegistry >= 0 )
  {
    if ( !LookupStringInArray(
            (const unsigned __int16 *const *const)&g_SamsungPRHCSKUList,
            1u,
            (const unsigned __int16 *)lpMem,
            0) )
      goto LABEL_9;
    v7 = GetHWSystemInformationFromRegistry(
           L"HARDWARE\\DESCRIPTION\\System\\BIOS",
           L"BIOSVersion",
           (unsigned __int16 **)&lpString1);
    v5 = (WCHAR *)lpString1;
    HWSystemInformationFromRegistry = v7;
    if ( v7 < 0 )
    {
LABEL_12:
      if ( v5 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v5);
      }
      if ( v2 )
      {
        v10 = GetProcessHeap();
        HeapFree(v10, 0, v2);
      }
      goto LABEL_16;
    }
    if ( CompareStringOrdinal(lpString1, -1, L"P11RHC", -1, 1) == 1 )
    {
      SBServicingLogMessage(
        (wchar_t *)L"Skipping update on %ls %ls due to old BIOS version %ls (required: %ls)",
        a1,
        lpMem,
        v5,
        L"P11RHC");
    }
    else
    {
LABEL_9:
      if ( !LookupStringInArray(
              (const unsigned __int16 *const *const)&g_SamsungSKUList,
              0x1Cu,
              (const unsigned __int16 *)lpMem,
              0) )
        goto LABEL_12;
      v8 = GetHWSystemInformationFromRegistry(L"HARDWARE\\DESCRIPTION\\System\\BIOS", L"BIOSReleaseDate", &v15);
      v2 = v15;
      HWSystemInformationFromRegistry = v8;
      if ( v8 < 0 || GetBiosYear(v15) >= 0x7EA )
        goto LABEL_12;
      SBServicingLogMessage(
        (wchar_t *)L"Skipping update on %ls %ls due to known bad SKU biosReleaseDate %ls",
        a1,
        lpMem,
        v2);
    }
    *a2 = 1;
    goto LABEL_12;
  }
LABEL_16:
  if ( lpMem )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, lpMem);
  }
  return (unsigned int)HWSystemInformationFromRegistry;
}

```

## disassembly

```asm
0x18003e110  push    rbx
0x18003e112  push    rsi
0x18003e113  push    rdi
0x18003e114  push    r14
0x18003e116  push    r15
0x18003e118  sub     rsp, 30h
0x18003e11c  xor     ebx, ebx
0x18003e11e  mov     r14, rdx
0x18003e121  mov     [rdx], ebx
0x18003e123  xor     edi, edi
0x18003e125  xor     esi, esi
0x18003e127  mov     [rsp+58h+lpMem], rdi
0x18003e12c  lea     rdx, aSamsung; "SAMSUNG"
0x18003e133  mov     [rsp+58h+arg_18], rbx
0x18003e138  mov     r15, rcx
0x18003e13b  mov     [rsp+58h+lpString1], rsi
0x18003e140  call    cs:__imp_StrStrIW
0x18003e146  test    rax, rax
0x18003e149  jz      loc_18003E2B7
0x18003e14f  lea     r8, [rsp+58h+lpMem]; unsigned __int16 **
0x18003e154  lea     rdx, aSystemsku; "SystemSKU"
0x18003e15b  lea     rcx, aHardwareDescri; "HARDWARE\\DESCRIPTION\\System\\BIOS"
0x18003e162  call    ?GetHWSystemInformationFromRegistry@@YAJPEBG0PEAPEAG@Z; GetHWSystemInformationFromRegistry(ushort const *,ushort const *,ushort * *)
0x18003e167  mov     edi, eax
0x18003e169  test    eax, eax
0x18003e16b  js      loc_18003E299
0x18003e171  mov     r8, [rsp+58h+lpMem]; unsigned __int16 *
0x18003e176  lea     edx, [rbx+1]; unsigned __int64
0x18003e179  xor     r9d, r9d; int
0x18003e17c  lea     rcx, ?g_SamsungPRHCSKUList@@3QBQEBGB; unsigned __int16 **
0x18003e183  call    ?LookupStringInArray@@YAHQEBQEBG_KPEBGH@Z; LookupStringInArray(ushort const * const * const,unsigned __int64,ushort const *,int)
0x18003e188  test    eax, eax
0x18003e18a  jz      short loc_18003E1FB
0x18003e18c  lea     r8, [rsp+58h+lpString1]; unsigned __int16 **
0x18003e191  lea     rdx, aBiosversion; "BIOSVersion"
0x18003e198  lea     rcx, aHardwareDescri; "HARDWARE\\DESCRIPTION\\System\\BIOS"
0x18003e19f  call    ?GetHWSystemInformationFromRegistry@@YAJPEBG0PEAPEAG@Z; GetHWSystemInformationFromRegistry(ushort const *,ushort const *,ushort * *)
0x18003e1a4  mov     rsi, [rsp+58h+lpString1]
0x18003e1a9  mov     edi, eax
0x18003e1ab  test    eax, eax
0x18003e1ad  js      loc_18003E267
0x18003e1b3  or      edx, 0FFFFFFFFh; cchCount1
0x18003e1b6  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x18003e1be  mov     r9d, edx; cchCount2
0x18003e1c1  lea     r8, aP11rhc; "P11RHC"
0x18003e1c8  mov     rcx, rsi; lpString1
0x18003e1cb  call    cs:__imp_CompareStringOrdinal
0x18003e1d1  cmp     eax, 1
0x18003e1d4  jnz     short loc_18003E1FB
0x18003e1d6  mov     r8, [rsp+58h+lpMem]
0x18003e1db  lea     rax, aP11rhc; "P11RHC"
0x18003e1e2  mov     r9, rsi
0x18003e1e5  mov     qword ptr [rsp+58h+bIgnoreCase], rax
0x18003e1ea  mov     rdx, r15
0x18003e1ed  lea     rcx, aSkippingUpdate; "Skipping update on %ls %ls due to old B"...
0x18003e1f4  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003e1f9  jmp     short loc_18003E260
0x18003e1fb  mov     r8, [rsp+58h+lpMem]; unsigned __int16 *
0x18003e200  lea     rcx, ?g_SamsungSKUList@@3QBQEBGB; unsigned __int16 **
0x18003e207  xor     r9d, r9d; int
0x18003e20a  lea     edx, [r9+1Ch]; unsigned __int64
0x18003e20e  call    ?LookupStringInArray@@YAHQEBQEBG_KPEBGH@Z; LookupStringInArray(ushort const * const * const,unsigned __int64,ushort const *,int)
0x18003e213  test    eax, eax
0x18003e215  jz      short loc_18003E267
0x18003e217  lea     r8, [rsp+58h+arg_18]; unsigned __int16 **
0x18003e21c  lea     rdx, aBiosreleasedat_0; "BIOSReleaseDate"
0x18003e223  lea     rcx, aHardwareDescri; "HARDWARE\\DESCRIPTION\\System\\BIOS"
0x18003e22a  call    ?GetHWSystemInformationFromRegistry@@YAJPEBG0PEAPEAG@Z; GetHWSystemInformationFromRegistry(ushort const *,ushort const *,ushort * *)
0x18003e22f  mov     rbx, [rsp+58h+arg_18]
0x18003e234  mov     edi, eax
0x18003e236  test    eax, eax
0x18003e238  js      short loc_18003E267
0x18003e23a  mov     rcx, rbx; unsigned __int16 *
0x18003e23d  call    ?GetBiosYear@@YAKPEAG@Z; GetBiosYear(ushort *)
0x18003e242  cmp     eax, 7EAh
0x18003e247  jnb     short loc_18003E267
0x18003e249  mov     r8, [rsp+58h+lpMem]
0x18003e24e  lea     rcx, aSkippingUpdate_4; "Skipping update on %ls %ls due to known"...
0x18003e255  mov     r9, rbx
0x18003e258  mov     rdx, r15
0x18003e25b  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003e260  mov     dword ptr [r14], 1
0x18003e267  test    rsi, rsi
0x18003e26a  jz      short loc_18003E280
0x18003e26c  call    cs:__imp_GetProcessHeap
0x18003e272  mov     r8, rsi; lpMem
0x18003e275  xor     edx, edx; dwFlags
0x18003e277  mov     rcx, rax; hHeap
0x18003e27a  call    cs:__imp_HeapFree
0x18003e280  test    rbx, rbx
0x18003e283  jz      short loc_18003E299
0x18003e285  call    cs:__imp_GetProcessHeap
0x18003e28b  mov     r8, rbx; lpMem
0x18003e28e  xor     edx, edx; dwFlags
0x18003e290  mov     rcx, rax; hHeap
0x18003e293  call    cs:__imp_HeapFree
0x18003e299  cmp     [rsp+58h+lpMem], 0
0x18003e29f  jz      short loc_18003E2B7
0x18003e2a1  call    cs:__imp_GetProcessHeap
0x18003e2a7  mov     r8, [rsp+58h+lpMem]; lpMem
0x18003e2ac  xor     edx, edx; dwFlags
0x18003e2ae  mov     rcx, rax; hHeap
0x18003e2b1  call    cs:__imp_HeapFree
0x18003e2b7  mov     eax, edi
0x18003e2b9  add     rsp, 30h
0x18003e2bd  pop     r15
0x18003e2bf  pop     r14
0x18003e2c1  pop     rdi
0x18003e2c2  pop     rsi
0x18003e2c3  pop     rbx
0x18003e2c4  retn
```
