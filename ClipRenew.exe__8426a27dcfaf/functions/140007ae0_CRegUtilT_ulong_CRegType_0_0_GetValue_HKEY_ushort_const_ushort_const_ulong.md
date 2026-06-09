# CRegUtilT<ulong,CRegType,0,0>::GetValue(HKEY__ *,ushort const *,ushort const *,ulong *)

- ea: `0x140007ae0`
- end: `0x140007c73`
- name: `?GetValue@?$CRegUtilT@KUCRegType@@$0A@$0A@@@SAJPEAUHKEY__@@PEBG1PEAK@Z`
- size: `403`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140007dcc`

## callees

- `0x140003454`
- `0x140004780`
- `0x140007ae0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007bbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007c3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007bbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140007c3e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140007bcb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140007bcb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007c4c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140007c4c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007b6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007c5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007b6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007c5a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140007ba3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140007ba3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140007b31`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140007b31`

## pseudocode

```c
__int64 __fastcall CRegUtilT<unsigned long,CRegType,0,0>::GetValue(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  BYTE *lpData; // rsi
  int v6; // ebx
  HKEY v7; // r14
  DWORD v8; // ebx
  HANDLE ProcessHeap; // rax
  int v10; // edi
  __int64 v11; // rcx
  HANDLE v12; // rax
  HKEY hKey; // [rsp+60h] [rbp+30h] BYREF
  DWORD Type; // [rsp+68h] [rbp+38h] BYREF
  int v16; // [rsp+6Ch] [rbp+3Ch]
  DWORD cbData; // [rsp+70h] [rbp+40h] BYREF
  int v18; // [rsp+74h] [rbp+44h]

  v18 = HIDWORD(a3);
  v16 = HIDWORD(a2);
  lpData = 0;
  Type = 0;
  cbData = 0;
  hKey = 0;
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Subscriptions",
         0,
         1u,
         &hKey);
  if ( v6 )
  {
    v7 = 0;
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v6);
  }
  else
  {
    v7 = hKey;
    hKey = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v6 < 0 )
  {
LABEL_25:
    v11 = (unsigned int)v6;
LABEL_26:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v11);
  }
  else
  {
    cbData = 0;
    while ( 1 )
    {
      v6 = RegQueryValueExW(v7, L"DisableSubscription", 0, &Type, lpData, &cbData);
      if ( v6 )
      {
        if ( v6 > 0 )
          v6 = (unsigned __int16)v6 | 0x80070000;
        goto LABEL_25;
      }
      if ( lpData )
        break;
      if ( !cbData )
      {
        v6 = -2147418113;
        goto LABEL_25;
      }
      v8 = cbData;
      ProcessHeap = GetProcessHeap();
      lpData = (BYTE *)HeapAlloc(ProcessHeap, 0, v8);
      if ( !lpData )
      {
        v6 = -2147024882;
        goto LABEL_25;
      }
    }
    if ( Type != 4 )
    {
      v6 = -2147024883;
      goto LABEL_25;
    }
    if ( cbData == 4 )
    {
      v10 = 0;
      *a4 = *(_DWORD *)lpData;
    }
    else
    {
      v10 = -2147024883;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942413LL);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v10);
    v6 = v10;
    if ( v10 < 0 )
    {
      v11 = (unsigned int)v10;
      goto LABEL_26;
    }
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
  if ( lpData )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, lpData);
  }
  if ( v7 )
    RegCloseKey(v7);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140007ae0  mov     r11, rsp
0x140007ae3  mov     [r11+20h], rbx
0x140007ae7  mov     [r11+18h], r8
0x140007aeb  mov     [r11+10h], rdx
0x140007aef  mov     [r11+8], rcx
0x140007af3  push    rbp
0x140007af4  push    rsi
0x140007af5  push    rdi
0x140007af6  push    r14
0x140007af8  push    r15
0x140007afa  mov     rbp, rsp
0x140007afd  sub     rsp, 30h
0x140007b01  xor     esi, esi
0x140007b03  mov     [rbp+Type], 0
0x140007b0a  mov     r15, r9
0x140007b0d  mov     [rbp+cbData], esi
0x140007b10  lea     rax, [rbp+hKey]
0x140007b14  mov     [rbp+hKey], rsi
0x140007b18  xor     r8d, r8d; ulOptions
0x140007b1b  mov     [r11-38h], rax
0x140007b1f  lea     r9d, [rsi+1]; samDesired
0x140007b23  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140007b2a  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140007b31  call    cs:__imp_RegOpenKeyExW
0x140007b37  mov     ebx, eax
0x140007b39  mov     edi, 80070000h
0x140007b3e  test    eax, eax
0x140007b40  jnz     short loc_140007B4C
0x140007b42  mov     r14, [rbp+hKey]
0x140007b46  mov     [rbp+hKey], rsi
0x140007b4a  jmp     short loc_140007B5F
0x140007b4c  xor     r14d, r14d
0x140007b4f  test    ebx, ebx
0x140007b51  jle     short loc_140007B58
0x140007b53  movzx   ebx, bx
0x140007b56  or      ebx, edi
0x140007b58  mov     ecx, ebx
0x140007b5a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140007b5f  mov     ecx, ebx
0x140007b61  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140007b66  mov     rcx, [rbp+hKey]; hKey
0x140007b6a  test    rcx, rcx
0x140007b6d  jz      short loc_140007B79
0x140007b6f  call    cs:__imp_RegCloseKey
0x140007b75  mov     [rbp+hKey], rsi
0x140007b79  test    ebx, ebx
0x140007b7b  js      loc_140007C2B
0x140007b81  mov     [rbp+cbData], esi
0x140007b84  lea     rax, [rbp+cbData]
0x140007b88  xor     r8d, r8d; lpReserved
0x140007b8b  mov     [rsp+30h+lpcbData], rax; lpcbData
0x140007b90  lea     r9, [rbp+Type]; lpType
0x140007b94  lea     rdx, ValueName; "DisableSubscription"
0x140007b9b  mov     [rsp+30h+lpData], rsi; lpData
0x140007ba0  mov     rcx, r14; hKey
0x140007ba3  call    cs:__imp_RegQueryValueExW
0x140007ba9  mov     ebx, eax
0x140007bab  test    eax, eax
0x140007bad  jnz     short loc_140007C22
0x140007baf  test    rsi, rsi
0x140007bb2  jnz     short loc_140007BE7
0x140007bb4  mov     eax, [rbp+cbData]
0x140007bb7  test    eax, eax
0x140007bb9  jz      short loc_140007BE0
0x140007bbb  mov     ebx, eax
0x140007bbd  call    cs:__imp_GetProcessHeap
0x140007bc3  mov     r8d, ebx; dwBytes
0x140007bc6  xor     edx, edx; dwFlags
0x140007bc8  mov     rcx, rax; hHeap
0x140007bcb  call    cs:__imp_HeapAlloc
0x140007bd1  mov     rsi, rax
0x140007bd4  test    rax, rax
0x140007bd7  jnz     short loc_140007B84
0x140007bd9  mov     ebx, 8007000Eh
0x140007bde  jmp     short loc_140007C2B
0x140007be0  mov     ebx, 8000FFFFh
0x140007be5  jmp     short loc_140007C2B
0x140007be7  cmp     [rbp+Type], 4
0x140007beb  jz      short loc_140007BF4
0x140007bed  mov     ebx, 8007000Dh
0x140007bf2  jmp     short loc_140007C2B
0x140007bf4  cmp     [rbp+cbData], 4
0x140007bf8  jz      short loc_140007C0A
0x140007bfa  mov     ebx, 8007000Dh
0x140007bff  mov     ecx, ebx
0x140007c01  mov     edi, ebx
0x140007c03  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140007c08  jmp     short loc_140007C11
0x140007c0a  mov     eax, [rsi]
0x140007c0c  xor     edi, edi
0x140007c0e  mov     [r15], eax
0x140007c11  mov     ecx, edi
0x140007c13  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140007c18  mov     ebx, edi
0x140007c1a  test    edi, edi
0x140007c1c  jns     short loc_140007C32
0x140007c1e  mov     ecx, edi
0x140007c20  jmp     short loc_140007C2D
0x140007c22  test    ebx, ebx
0x140007c24  jle     short loc_140007C2B
0x140007c26  movzx   ebx, bx
0x140007c29  or      ebx, edi
0x140007c2b  mov     ecx, ebx
0x140007c2d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140007c32  mov     ecx, ebx
0x140007c34  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140007c39  test    rsi, rsi
0x140007c3c  jz      short loc_140007C52
0x140007c3e  call    cs:__imp_GetProcessHeap
0x140007c44  mov     r8, rsi; lpMem
0x140007c47  xor     edx, edx; dwFlags
0x140007c49  mov     rcx, rax; hHeap
0x140007c4c  call    cs:__imp_HeapFree
0x140007c52  test    r14, r14
0x140007c55  jz      short loc_140007C60
0x140007c57  mov     rcx, r14; hKey
0x140007c5a  call    cs:__imp_RegCloseKey
0x140007c60  mov     eax, ebx
0x140007c62  mov     rbx, [rsp+30h+arg_18]
0x140007c67  add     rsp, 30h
0x140007c6b  pop     r15
0x140007c6d  pop     r14
0x140007c6f  pop     rdi
0x140007c70  pop     rsi
0x140007c71  pop     rbp
0x140007c72  retn
```
