# CRegUtilT<ulong,CRegType,0,0>::GetValue(HKEY__ *,ushort const *,ushort const *,ulong *)

- ea: `0x18002872c`
- end: `0x1800288c0`
- name: `?GetValue@?$CRegUtilT@KUCRegType@@$0A@$0A@@@SAJPEAUHKEY__@@PEBG1PEAK@Z`
- size: `404`
- prototype: `__int64 __fastcall(__int64, __int64, const WCHAR *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x18002bae0`

## callees

- `0x180027008`
- `0x18002872c`
- `0x1800293a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002877c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002877c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800287b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800288a4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800287b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800288a4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800287e9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800287e9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180028811`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180028811`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028803`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028888`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028803`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028888`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028896`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028896`

## pseudocode

```c
__int64 __fastcall CRegUtilT<unsigned long,CRegType,0,0>::GetValue(__int64 a1, __int64 a2, const WCHAR *a3, _DWORD *a4)
{
  BYTE *lpData; // rsi
  int v7; // ebx
  HKEY v8; // r14
  DWORD v9; // ebx
  HANDLE ProcessHeap; // rax
  int v11; // edi
  int v12; // ecx
  HANDLE v13; // rax
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD Type; // [rsp+70h] [rbp+30h] BYREF
  int v17; // [rsp+74h] [rbp+34h]
  DWORD cbData; // [rsp+78h] [rbp+38h] BYREF
  int v19; // [rsp+7Ch] [rbp+3Ch]

  v19 = HIDWORD(a2);
  v17 = HIDWORD(a1);
  lpData = 0;
  Type = 0;
  cbData = 0;
  hKey = 0;
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup", 0, 1u, &hKey);
  if ( v7 )
  {
    v8 = 0;
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
  }
  else
  {
    v8 = hKey;
    hKey = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v7 < 0 )
  {
LABEL_25:
    v12 = v7;
LABEL_26:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v12);
  }
  else
  {
    cbData = 0;
    while ( 1 )
    {
      v7 = RegQueryValueExW(v8, a3, 0, &Type, lpData, &cbData);
      if ( v7 )
      {
        if ( v7 > 0 )
          v7 = (unsigned __int16)v7 | 0x80070000;
        goto LABEL_25;
      }
      if ( lpData )
        break;
      if ( !cbData )
      {
        v7 = -2147418113;
        goto LABEL_25;
      }
      v9 = cbData;
      ProcessHeap = GetProcessHeap();
      lpData = (BYTE *)HeapAlloc(ProcessHeap, 0, v9);
      if ( !lpData )
      {
        v7 = -2147024882;
        goto LABEL_25;
      }
    }
    if ( Type != 4 )
    {
      v7 = -2147024883;
      goto LABEL_25;
    }
    if ( cbData == 4 )
    {
      v11 = 0;
      *a4 = *(_DWORD *)lpData;
    }
    else
    {
      v11 = -2147024883;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024883);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v11);
    v7 = v11;
    if ( v11 < 0 )
    {
      v12 = v11;
      goto LABEL_26;
    }
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  if ( lpData )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, lpData);
  }
  if ( v8 )
    RegCloseKey(v8);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002872c  mov     r11, rsp
0x18002872f  mov     [r11+18h], rbx
0x180028733  mov     [r11+10h], rdx
0x180028737  mov     [r11+8], rcx
0x18002873b  push    rbp
0x18002873c  push    rsi
0x18002873d  push    rdi
0x18002873e  push    r14
0x180028740  push    r15
0x180028742  mov     rbp, rsp
0x180028745  sub     rsp, 40h
0x180028749  xor     esi, esi
0x18002874b  mov     [rbp+Type], 0
0x180028752  mov     r15, r9
0x180028755  mov     [rbp+cbData], esi
0x180028758  mov     rdi, r8
0x18002875b  mov     [rbp+hKey], rsi
0x18002875f  lea     rax, [rbp+hKey]
0x180028763  xor     r8d, r8d; ulOptions
0x180028766  lea     r9d, [rsi+1]; samDesired
0x18002876a  mov     [r11-48h], rax
0x18002876e  lea     rdx, aSystemSetup; "SYSTEM\\Setup"
0x180028775  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002877c  call    cs:__imp_RegOpenKeyExW
0x180028782  mov     ebx, eax
0x180028784  test    eax, eax
0x180028786  jnz     short loc_180028792
0x180028788  mov     r14, [rbp+hKey]
0x18002878c  mov     [rbp+hKey], rsi
0x180028790  jmp     short loc_1800287A9
0x180028792  xor     r14d, r14d
0x180028795  test    ebx, ebx
0x180028797  jle     short loc_1800287A2
0x180028799  movzx   ebx, bx
0x18002879c  or      ebx, 80070000h
0x1800287a2  mov     ecx, ebx
0x1800287a4  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800287a9  mov     ecx, ebx
0x1800287ab  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800287b0  mov     rcx, [rbp+hKey]; hKey
0x1800287b4  test    rcx, rcx
0x1800287b7  jz      short loc_1800287C3
0x1800287b9  call    cs:__imp_RegCloseKey
0x1800287bf  mov     [rbp+hKey], rsi
0x1800287c3  test    ebx, ebx
0x1800287c5  js      loc_180028875
0x1800287cb  mov     [rbp+cbData], esi
0x1800287ce  lea     rax, [rbp+cbData]
0x1800287d2  xor     r8d, r8d; lpReserved
0x1800287d5  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800287da  lea     r9, [rbp+Type]; lpType
0x1800287de  mov     rdx, rdi; lpValueName
0x1800287e1  mov     [rsp+40h+lpData], rsi; lpData
0x1800287e6  mov     rcx, r14; hKey
0x1800287e9  call    cs:__imp_RegQueryValueExW
0x1800287ef  mov     ebx, eax
0x1800287f1  test    eax, eax
0x1800287f3  jnz     short loc_180028868
0x1800287f5  test    rsi, rsi
0x1800287f8  jnz     short loc_18002882D
0x1800287fa  mov     eax, [rbp+cbData]
0x1800287fd  test    eax, eax
0x1800287ff  jz      short loc_180028826
0x180028801  mov     ebx, eax
0x180028803  call    cs:__imp_GetProcessHeap
0x180028809  mov     r8d, ebx; dwBytes
0x18002880c  xor     edx, edx; dwFlags
0x18002880e  mov     rcx, rax; hHeap
0x180028811  call    cs:__imp_HeapAlloc
0x180028817  mov     rsi, rax
0x18002881a  test    rax, rax
0x18002881d  jnz     short loc_1800287CE
0x18002881f  mov     ebx, 8007000Eh
0x180028824  jmp     short loc_180028875
0x180028826  mov     ebx, 8000FFFFh
0x18002882b  jmp     short loc_180028875
0x18002882d  cmp     [rbp+Type], 4
0x180028831  jz      short loc_18002883A
0x180028833  mov     ebx, 8007000Dh
0x180028838  jmp     short loc_180028875
0x18002883a  cmp     [rbp+cbData], 4
0x18002883e  jz      short loc_180028850
0x180028840  mov     ebx, 8007000Dh
0x180028845  mov     ecx, ebx
0x180028847  mov     edi, ebx
0x180028849  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002884e  jmp     short loc_180028857
0x180028850  mov     eax, [rsi]
0x180028852  xor     edi, edi
0x180028854  mov     [r15], eax
0x180028857  mov     ecx, edi
0x180028859  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002885e  mov     ebx, edi
0x180028860  test    edi, edi
0x180028862  jns     short loc_18002887C
0x180028864  mov     ecx, edi
0x180028866  jmp     short loc_180028877
0x180028868  test    ebx, ebx
0x18002886a  jle     short loc_180028875
0x18002886c  movzx   ebx, bx
0x18002886f  or      ebx, 80070000h
0x180028875  mov     ecx, ebx
0x180028877  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002887c  mov     ecx, ebx
0x18002887e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180028883  test    rsi, rsi
0x180028886  jz      short loc_18002889C
0x180028888  call    cs:__imp_GetProcessHeap
0x18002888e  mov     r8, rsi; lpMem
0x180028891  xor     edx, edx; dwFlags
0x180028893  mov     rcx, rax; hHeap
0x180028896  call    cs:__imp_HeapFree
0x18002889c  test    r14, r14
0x18002889f  jz      short loc_1800288AA
0x1800288a1  mov     rcx, r14; hKey
0x1800288a4  call    cs:__imp_RegCloseKey
0x1800288aa  mov     eax, ebx
0x1800288ac  mov     rbx, [rsp+40h+arg_10]
0x1800288b4  add     rsp, 40h
0x1800288b8  pop     r15
0x1800288ba  pop     r14
0x1800288bc  pop     rdi
0x1800288bd  pop     rsi
0x1800288be  pop     rbp
0x1800288bf  retn
```
