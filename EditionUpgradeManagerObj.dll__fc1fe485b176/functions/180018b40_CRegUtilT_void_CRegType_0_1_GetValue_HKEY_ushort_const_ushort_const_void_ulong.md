# CRegUtilT<void *,CRegType,0,1>::GetValue(HKEY__ *,ushort const *,ushort const *,void * *,ulong *)

- ea: `0x180018b40`
- end: `0x180018cba`
- name: `?GetValue@?$CRegUtilT@PEAXUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG1PEAPEAXPEAK@Z`
- size: `378`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, BYTE **, DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021f60`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x180018b40`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018c99`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018c99`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018c24`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018c24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018c16`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018c8b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018c16`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018c8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018bc8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018ca7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018bc8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018ca7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018b8c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018b8c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018bfc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018bfc`

## pseudocode

```c
__int64 __fastcall CRegUtilT<void *,CRegType,0,1>::GetValue(__int64 a1, __int64 a2, __int64 a3, BYTE **a4, DWORD *a5)
{
  BYTE *lpData; // rdi
  int v7; // ebx
  HKEY v8; // rsi
  DWORD v9; // ebx
  HANDLE ProcessHeap; // rax
  HANDLE v11; // rax
  HKEY hKey; // [rsp+60h] [rbp+30h] BYREF
  DWORD Type; // [rsp+68h] [rbp+38h] BYREF
  int v15; // [rsp+6Ch] [rbp+3Ch]
  DWORD cbData; // [rsp+70h] [rbp+40h] BYREF
  int v17; // [rsp+74h] [rbp+44h]

  v17 = HIDWORD(a3);
  v15 = HIDWORD(a2);
  lpData = 0;
  Type = 0;
  cbData = 0;
  hKey = 0;
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\", 0, 1u, &hKey);
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
LABEL_22:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
  }
  else
  {
    cbData = 0;
    while ( 1 )
    {
      v7 = RegQueryValueExW(v8, L"DigitalProductId4", 0, &Type, lpData, &cbData);
      if ( v7 )
      {
        if ( v7 > 0 )
          v7 = (unsigned __int16)v7 | 0x80070000;
        goto LABEL_22;
      }
      if ( lpData )
        break;
      if ( !cbData )
      {
        v7 = -2147418113;
        goto LABEL_22;
      }
      v9 = cbData;
      ProcessHeap = GetProcessHeap();
      lpData = (BYTE *)HeapAlloc(ProcessHeap, 0, v9);
      if ( !lpData )
      {
        v7 = -2147024882;
        goto LABEL_22;
      }
    }
    if ( Type != 3 )
    {
      v7 = -2147024883;
      goto LABEL_22;
    }
    *a4 = lpData;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v7 = 0;
    lpData = 0;
    if ( a5 )
      *a5 = cbData;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  if ( lpData )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, lpData);
  }
  if ( v8 )
    RegCloseKey(v8);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180018b40  mov     r11, rsp
0x180018b43  mov     [r11+18h], r8
0x180018b47  mov     [r11+10h], rdx
0x180018b4b  mov     [r11+8], rcx
0x180018b4f  push    rbp
0x180018b50  push    rbx
0x180018b51  push    rsi
0x180018b52  push    rdi
0x180018b53  push    r14
0x180018b55  mov     rbp, rsp
0x180018b58  sub     rsp, 30h
0x180018b5c  xor     edi, edi
0x180018b5e  mov     [rbp+Type], 0
0x180018b65  mov     r14, r9
0x180018b68  mov     [rbp+cbData], edi
0x180018b6b  lea     rax, [rbp+hKey]
0x180018b6f  mov     [rbp+hKey], rdi
0x180018b73  xor     r8d, r8d; ulOptions
0x180018b76  mov     [r11-38h], rax
0x180018b7a  lea     r9d, [rdi+1]; samDesired
0x180018b7e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180018b85  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x180018b8c  call    cs:__imp_RegOpenKeyExW
0x180018b92  mov     ebx, eax
0x180018b94  test    eax, eax
0x180018b96  jnz     short loc_180018BA2
0x180018b98  mov     rsi, [rbp+hKey]
0x180018b9c  mov     [rbp+hKey], rdi
0x180018ba0  jmp     short loc_180018BB8
0x180018ba2  xor     esi, esi
0x180018ba4  test    ebx, ebx
0x180018ba6  jle     short loc_180018BB1
0x180018ba8  movzx   ebx, bx
0x180018bab  or      ebx, 80070000h
0x180018bb1  mov     ecx, ebx
0x180018bb3  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180018bb8  mov     ecx, ebx
0x180018bba  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180018bbf  mov     rcx, [rbp+hKey]; hKey
0x180018bc3  test    rcx, rcx
0x180018bc6  jz      short loc_180018BD2
0x180018bc8  call    cs:__imp_RegCloseKey
0x180018bce  mov     [rbp+hKey], rdi
0x180018bd2  test    ebx, ebx
0x180018bd4  js      loc_180018C78
0x180018bda  mov     [rbp+cbData], edi
0x180018bdd  lea     rax, [rbp+cbData]
0x180018be1  xor     r8d, r8d; lpReserved
0x180018be4  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180018be9  lea     r9, [rbp+Type]; lpType
0x180018bed  lea     rdx, aDigitalproduct; "DigitalProductId4"
0x180018bf4  mov     [rsp+30h+lpData], rdi; lpData
0x180018bf9  mov     rcx, rsi; hKey
0x180018bfc  call    cs:__imp_RegQueryValueExW
0x180018c02  mov     ebx, eax
0x180018c04  test    eax, eax
0x180018c06  jnz     short loc_180018C6B
0x180018c08  test    rdi, rdi
0x180018c0b  jnz     short loc_180018C40
0x180018c0d  mov     eax, [rbp+cbData]
0x180018c10  test    eax, eax
0x180018c12  jz      short loc_180018C39
0x180018c14  mov     ebx, eax
0x180018c16  call    cs:__imp_GetProcessHeap
0x180018c1c  mov     r8d, ebx; dwBytes
0x180018c1f  xor     edx, edx; dwFlags
0x180018c21  mov     rcx, rax; hHeap
0x180018c24  call    cs:__imp_HeapAlloc
0x180018c2a  mov     rdi, rax
0x180018c2d  test    rax, rax
0x180018c30  jnz     short loc_180018BDD
0x180018c32  mov     ebx, 8007000Eh
0x180018c37  jmp     short loc_180018C78
0x180018c39  mov     ebx, 8000FFFFh
0x180018c3e  jmp     short loc_180018C78
0x180018c40  cmp     [rbp+Type], 3
0x180018c44  jz      short loc_180018C4D
0x180018c46  mov     ebx, 8007000Dh
0x180018c4b  jmp     short loc_180018C78
0x180018c4d  mov     [r14], rdi
0x180018c50  xor     ecx, ecx
0x180018c52  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180018c57  mov     rcx, [rbp+arg_20]
0x180018c5b  xor     ebx, ebx
0x180018c5d  xor     edi, edi
0x180018c5f  test    rcx, rcx
0x180018c62  jz      short loc_180018C7F
0x180018c64  mov     eax, [rbp+cbData]
0x180018c67  mov     [rcx], eax
0x180018c69  jmp     short loc_180018C7F
0x180018c6b  test    ebx, ebx
0x180018c6d  jle     short loc_180018C78
0x180018c6f  movzx   ebx, bx
0x180018c72  or      ebx, 80070000h
0x180018c78  mov     ecx, ebx
0x180018c7a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180018c7f  mov     ecx, ebx
0x180018c81  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180018c86  test    rdi, rdi
0x180018c89  jz      short loc_180018C9F
0x180018c8b  call    cs:__imp_GetProcessHeap
0x180018c91  mov     r8, rdi; lpMem
0x180018c94  xor     edx, edx; dwFlags
0x180018c96  mov     rcx, rax; hHeap
0x180018c99  call    cs:__imp_HeapFree
0x180018c9f  test    rsi, rsi
0x180018ca2  jz      short loc_180018CAD
0x180018ca4  mov     rcx, rsi; hKey
0x180018ca7  call    cs:__imp_RegCloseKey
0x180018cad  mov     eax, ebx
0x180018caf  add     rsp, 30h
0x180018cb3  pop     r14
0x180018cb5  pop     rdi
0x180018cb6  pop     rsi
0x180018cb7  pop     rbx
0x180018cb8  pop     rbp
0x180018cb9  retn
```
