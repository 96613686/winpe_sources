# CRegUtilT<ushort *,CRegType,0,1>::GetValue(HKEY__ *,ushort const *,ushort const *,ushort * *,ulong *)

- ea: `0x1800188f8`
- end: `0x180018b38`
- name: `?GetValue@?$CRegUtilT@PEAGUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG1PEAPEAGPEAK@Z`
- size: `576`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *, HKEY hKey)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180022088`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x18000b448`
- `0x18000b68c`
- `0x1800188f8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018ac9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018b0a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018ac9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018b0a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800189f4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800189f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800189e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018aba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018afc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800189e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018aba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018afc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018993`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018b18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018993`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018b18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018952`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018952`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800189c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800189c8`

## pseudocode

```c
__int64 __fastcall CRegUtilT<unsigned short *,CRegType,0,1>::GetValue(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        HKEY hKey)
{
  BYTE *lpData; // r14
  int v7; // ebx
  HKEY v8; // r15
  DWORD v9; // ebx
  HANDLE ProcessHeap; // rax
  __int64 v11; // rsi
  int v12; // edi
  int v13; // ecx
  int StringCch; // eax
  int v15; // eax
  __int64 v16; // rax
  HANDLE v17; // rax
  int v18; // ecx
  HANDLE v19; // rax
  __int64 v21; // [rsp+30h] [rbp-10h] BYREF
  __int64 v22; // [rsp+80h] [rbp+40h] BYREF
  DWORD Type; // [rsp+88h] [rbp+48h] BYREF
  int v24; // [rsp+8Ch] [rbp+4Ch]
  DWORD cbData; // [rsp+90h] [rbp+50h] BYREF
  int v26; // [rsp+94h] [rbp+54h]

  v26 = HIDWORD(a3);
  v24 = HIDWORD(a2);
  v22 = a1;
  Type = 0;
  cbData = 0;
  hKey = 0;
  lpData = 0;
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\ProductOptions", 0, 1u, &hKey);
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
    v7 = 0;
    hKey = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v7 >= 0 )
  {
    cbData = 0;
    while ( 1 )
    {
      v7 = RegQueryValueExW(v8, L"OSProductPfn", 0, &Type, lpData, &cbData);
      if ( v7 )
      {
        if ( v7 > 0 )
          v7 = (unsigned __int16)v7 | 0x80070000;
        goto LABEL_37;
      }
      if ( lpData )
        break;
      if ( !cbData )
      {
        v7 = -2147418113;
        goto LABEL_37;
      }
      v9 = cbData;
      ProcessHeap = GetProcessHeap();
      lpData = (BYTE *)HeapAlloc(ProcessHeap, 0, v9);
      if ( !lpData )
      {
        lpData = 0;
        v7 = -2147024882;
        goto LABEL_37;
      }
    }
    if ( Type != 1 )
    {
      v7 = -2147024883;
      goto LABEL_37;
    }
    v11 = 0;
    v21 = 0;
    if ( !cbData || (cbData & 1) != 0 || *(_WORD *)&lpData[2 * (cbData >> 1) - 2] )
    {
      v12 = -2147024883;
      v13 = -2147024883;
    }
    else
    {
      LODWORD(v22) = 0;
      StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(lpData, &v22);
      v12 = StringCch;
      if ( StringCch >= 0 )
      {
        v15 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(lpData, v22, &v21);
        v12 = v15;
        if ( v15 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v15);
        v11 = v21;
      }
      else
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(StringCch);
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
      if ( v12 >= 0 )
      {
        v16 = v11;
        v11 = 0;
        *a4 = v16;
LABEL_31:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
        if ( v11 )
        {
          v17 = GetProcessHeap();
          HeapFree(v17, 0, (LPVOID)(v11 - 4));
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        }
        v7 = v12;
        if ( v12 < 0 )
        {
          v18 = v12;
          goto LABEL_38;
        }
        goto LABEL_39;
      }
      v13 = v12;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v13);
    goto LABEL_31;
  }
LABEL_37:
  v18 = v7;
LABEL_38:
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v18);
LABEL_39:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v7);
  if ( lpData )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, lpData);
  }
  if ( v8 )
    RegCloseKey(v8);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800188f8  mov     r11, rsp
0x1800188fb  mov     [r11+20h], rbx
0x1800188ff  mov     [r11+18h], r8
0x180018903  mov     [r11+10h], rdx
0x180018907  mov     [r11+8], rcx
0x18001890b  push    rbp
0x18001890c  push    rsi
0x18001890d  push    rdi
0x18001890e  push    r12
0x180018910  push    r13
0x180018912  push    r14
0x180018914  push    r15
0x180018916  mov     rbp, rsp
0x180018919  sub     rsp, 40h
0x18001891d  xor     r13d, r13d
0x180018920  lea     rax, [rbp+hKey]
0x180018924  mov     r12, r9
0x180018927  mov     [rbp+Type], r13d
0x18001892b  xor     r8d, r8d; ulOptions
0x18001892e  mov     [rbp+cbData], r13d
0x180018932  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Pro"...
0x180018939  mov     [rbp+hKey], r13
0x18001893d  lea     edi, [r13+1]
0x180018941  mov     [r11-58h], rax
0x180018945  mov     r9d, edi; samDesired
0x180018948  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001894f  mov     r14d, r13d
0x180018952  call    cs:__imp_RegOpenKeyExW
0x180018958  mov     ebx, eax
0x18001895a  mov     esi, 80070000h
0x18001895f  test    eax, eax
0x180018961  jnz     short loc_180018970
0x180018963  mov     r15, [rbp+hKey]
0x180018967  mov     ebx, r13d
0x18001896a  mov     [rbp+hKey], r13
0x18001896e  jmp     short loc_180018983
0x180018970  mov     r15, r13
0x180018973  test    ebx, ebx
0x180018975  jle     short loc_18001897C
0x180018977  movzx   ebx, bx
0x18001897a  or      ebx, esi
0x18001897c  mov     ecx, ebx
0x18001897e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180018983  mov     ecx, ebx
0x180018985  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001898a  mov     rcx, [rbp+hKey]; hKey
0x18001898e  test    rcx, rcx
0x180018991  jz      short loc_18001899D
0x180018993  call    cs:__imp_RegCloseKey
0x180018999  mov     [rbp+hKey], r13
0x18001899d  test    ebx, ebx
0x18001899f  js      loc_180018AE9
0x1800189a5  mov     [rbp+cbData], r13d
0x1800189a9  lea     rax, [rbp+cbData]
0x1800189ad  xor     r8d, r8d; lpReserved
0x1800189b0  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800189b5  lea     r9, [rbp+Type]; lpType
0x1800189b9  lea     rdx, aOsproductpfn; "OSProductPfn"
0x1800189c0  mov     [rsp+40h+lpData], r14; lpData
0x1800189c5  mov     rcx, r15; hKey
0x1800189c8  call    cs:__imp_RegQueryValueExW
0x1800189ce  mov     ebx, eax
0x1800189d0  test    eax, eax
0x1800189d2  jnz     loc_180018AE0
0x1800189d8  test    r14, r14
0x1800189db  jnz     short loc_180018A19
0x1800189dd  mov     eax, [rbp+cbData]
0x1800189e0  test    eax, eax
0x1800189e2  jz      short loc_180018A0F
0x1800189e4  mov     ebx, eax
0x1800189e6  call    cs:__imp_GetProcessHeap
0x1800189ec  mov     r8d, ebx; dwBytes
0x1800189ef  xor     edx, edx; dwFlags
0x1800189f1  mov     rcx, rax; hHeap
0x1800189f4  call    cs:__imp_HeapAlloc
0x1800189fa  mov     r14, rax
0x1800189fd  test    rax, rax
0x180018a00  jnz     short loc_1800189A9
0x180018a02  mov     r14, r13
0x180018a05  mov     ebx, 8007000Eh
0x180018a0a  jmp     loc_180018AE9
0x180018a0f  mov     ebx, 8000FFFFh
0x180018a14  jmp     loc_180018AE9
0x180018a19  cmp     [rbp+Type], edi
0x180018a1c  jz      short loc_180018A28
0x180018a1e  mov     ebx, 8007000Dh
0x180018a23  jmp     loc_180018AE9
0x180018a28  mov     eax, [rbp+cbData]
0x180018a2b  mov     rsi, r13
0x180018a2e  mov     [rbp+var_10], r13
0x180018a32  test    eax, eax
0x180018a34  jnz     short loc_180018A46
0x180018a36  mov     ebx, 8007000Dh
0x180018a3b  mov     edi, ebx
0x180018a3d  mov     ecx, ebx
0x180018a3f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180018a44  jmp     short loc_180018AAE
0x180018a46  test    dil, al
0x180018a49  jnz     short loc_180018A36
0x180018a4b  shr     eax, 1
0x180018a4d  sub     eax, edi
0x180018a4f  cmp     [r14+rax*2], r13w
0x180018a54  jnz     short loc_180018A36
0x180018a56  lea     rdx, [rbp+arg_0]
0x180018a5a  mov     dword ptr [rbp+arg_0], r13d
0x180018a5e  mov     rcx, r14
0x180018a61  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x180018a66  mov     edi, eax
0x180018a68  test    eax, eax
0x180018a6a  jns     short loc_180018A75
0x180018a6c  mov     ecx, eax
0x180018a6e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180018a73  jmp     short loc_180018A95
0x180018a75  mov     edx, dword ptr [rbp+arg_0]
0x180018a78  lea     r8, [rbp+var_10]
0x180018a7c  mov     rcx, r14; Src
0x180018a7f  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x180018a84  mov     edi, eax
0x180018a86  test    eax, eax
0x180018a88  jns     short loc_180018A91
0x180018a8a  mov     ecx, eax
0x180018a8c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180018a91  mov     rsi, [rbp+var_10]
0x180018a95  mov     ecx, edi
0x180018a97  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180018a9c  test    edi, edi
0x180018a9e  jns     short loc_180018AA4
0x180018aa0  mov     ecx, edi
0x180018aa2  jmp     short loc_180018A3F
0x180018aa4  mov     rax, rsi
0x180018aa7  mov     rsi, r13
0x180018aaa  mov     [r12], rax
0x180018aae  mov     ecx, edi
0x180018ab0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180018ab5  test    rsi, rsi
0x180018ab8  jz      short loc_180018AD6
0x180018aba  call    cs:__imp_GetProcessHeap
0x180018ac0  lea     r8, [rsi-4]; lpMem
0x180018ac4  xor     edx, edx; dwFlags
0x180018ac6  mov     rcx, rax; hHeap
0x180018ac9  call    cs:__imp_HeapFree
0x180018acf  xor     ecx, ecx
0x180018ad1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180018ad6  mov     ebx, edi
0x180018ad8  test    edi, edi
0x180018ada  jns     short loc_180018AF0
0x180018adc  mov     ecx, edi
0x180018ade  jmp     short loc_180018AEB
0x180018ae0  test    ebx, ebx
0x180018ae2  jle     short loc_180018AE9
0x180018ae4  movzx   ebx, bx
0x180018ae7  or      ebx, esi
0x180018ae9  mov     ecx, ebx
0x180018aeb  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180018af0  mov     ecx, ebx
0x180018af2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180018af7  test    r14, r14
0x180018afa  jz      short loc_180018B10
0x180018afc  call    cs:__imp_GetProcessHeap
0x180018b02  mov     r8, r14; lpMem
0x180018b05  xor     edx, edx; dwFlags
0x180018b07  mov     rcx, rax; hHeap
0x180018b0a  call    cs:__imp_HeapFree
0x180018b10  test    r15, r15
0x180018b13  jz      short loc_180018B1E
0x180018b15  mov     rcx, r15; hKey
0x180018b18  call    cs:__imp_RegCloseKey
0x180018b1e  mov     eax, ebx
0x180018b20  mov     rbx, [rsp+40h+arg_18]
0x180018b28  add     rsp, 40h
0x180018b2c  pop     r15
0x180018b2e  pop     r14
0x180018b30  pop     r13
0x180018b32  pop     r12
0x180018b34  pop     rdi
0x180018b35  pop     rsi
0x180018b36  pop     rbp
0x180018b37  retn
```
