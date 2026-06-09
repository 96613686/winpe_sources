# CRegUtilT<ushort *,CRegType2,0,1>::GetValue(HKEY__ *,ushort const *,ushort const *,ushort * *,ulong *)

- ea: `0x1400107c8`
- end: `0x140010a0d`
- name: `?GetValue@?$CRegUtilT@PEAGUCRegType2@@$0A@$00@@SAJPEAUHKEY__@@PEBG1PEAPEAGPEAK@Z`
- size: `581`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140007494`

## callees

- `0x1400076c8`
- `0x14000c844`
- `0x1400107c8`
- `0x1400135b8`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x14001089d`
- `ADVAPI32!RegQueryValueExW` at `0x14001089d`
- `ADVAPI32!RegOpenKeyExW` at `0x140010822`
- `ADVAPI32!RegOpenKeyExW` at `0x140010822`
- `ADVAPI32!RegCloseKey` at `0x140010866`
- `ADVAPI32!RegCloseKey` at `0x1400109e6`
- `ADVAPI32!RegCloseKey` at `0x140010866`
- `ADVAPI32!RegCloseKey` at `0x1400109e6`
- `KERNEL32!HeapFree` at `0x140010985`
- `KERNEL32!HeapFree` at `0x1400109d2`
- `KERNEL32!HeapFree` at `0x140010985`
- `KERNEL32!HeapFree` at `0x1400109d2`
- `KERNEL32!HeapAlloc` at `0x1400108d5`
- `KERNEL32!HeapAlloc` at `0x1400108d5`
- `KERNEL32!GetProcessHeap` at `0x1400108c1`
- `KERNEL32!GetProcessHeap` at `0x140010970`
- `KERNEL32!GetProcessHeap` at `0x1400109be`
- `KERNEL32!GetProcessHeap` at `0x1400108c1`
- `KERNEL32!GetProcessHeap` at `0x140010970`
- `KERNEL32!GetProcessHeap` at `0x1400109be`

## string_xrefs

- `0x14001088e`: `RollbackOnline`

## pseudocode

```c
__int64 __fastcall CRegUtilT<unsigned short *,CRegType2,0,1>::GetValue(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        __int64 a5)
{
  HKEY v6; // r15
  BYTE *lpData; // r14
  int v8; // edi
  DWORD v9; // ebx
  HANDLE ProcessHeap; // rax
  __int64 v11; // rbx
  int v12; // esi
  int v13; // eax
  HANDLE v14; // rax
  __int64 v15; // rcx
  HANDLE v16; // rax
  HKEY hKey; // [rsp+70h] [rbp+40h] BYREF
  DWORD Type; // [rsp+78h] [rbp+48h] BYREF
  int v20; // [rsp+7Ch] [rbp+4Ch]
  DWORD cbData; // [rsp+80h] [rbp+50h] BYREF
  int v22; // [rsp+84h] [rbp+54h]

  v22 = HIDWORD(a3);
  v20 = HIDWORD(a2);
  Type = 0;
  cbData = 0;
  hKey = 0;
  v6 = 0;
  lpData = 0;
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\RunOnce", 0, 1u, &hKey);
  if ( v8 )
  {
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v8);
  }
  else
  {
    v6 = hKey;
    v8 = 0;
    hKey = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v8 < 0 )
  {
LABEL_30:
    v15 = (unsigned int)v8;
LABEL_31:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v15);
  }
  else
  {
    while ( 1 )
    {
      v8 = RegQueryValueExW(v6, L"RollbackOnline", 0, &Type, lpData, &cbData);
      if ( v8 )
      {
        if ( v8 > 0 )
          v8 = (unsigned __int16)v8 | 0x80070000;
        goto LABEL_30;
      }
      if ( lpData )
        break;
      if ( !cbData )
      {
        v8 = -2147418113;
        goto LABEL_30;
      }
      v9 = cbData;
      ProcessHeap = GetProcessHeap();
      lpData = (BYTE *)HeapAlloc(ProcessHeap, 0, v9);
      if ( !lpData )
      {
        lpData = 0;
        v8 = -2147024882;
        goto LABEL_30;
      }
    }
    if ( Type != 2 )
    {
      v8 = -2147024883;
      goto LABEL_30;
    }
    v11 = 0;
    a5 = 0;
    if ( !cbData || (cbData & 1) != 0 || *(_WORD *)&lpData[2 * (cbData >> 1) - 2] )
    {
      v12 = -2147024883;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942413LL);
    }
    else
    {
      v13 = CMiscHelpersT<CEmptyType>::ExpandFileName((LPCWSTR)lpData);
      v12 = v13;
      if ( v13 >= 0 )
      {
        *a4 = a5;
      }
      else
      {
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v13);
        v11 = a5;
      }
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
    if ( v11 )
    {
      v14 = GetProcessHeap();
      HeapFree(v14, 0, (LPVOID)(v11 - 4));
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    }
    v8 = v12;
    if ( v12 < 0 )
    {
      v15 = (unsigned int)v12;
      goto LABEL_31;
    }
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
  if ( lpData )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, lpData);
  }
  if ( v6 )
    RegCloseKey(v6);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400107c8  mov     r11, rsp
0x1400107cb  mov     [r11+20h], rbx
0x1400107cf  mov     [r11+18h], r8
0x1400107d3  mov     [r11+10h], rdx
0x1400107d7  mov     [r11+8], rcx
0x1400107db  push    rbp
0x1400107dc  push    rsi
0x1400107dd  push    rdi
0x1400107de  push    r12
0x1400107e0  push    r13
0x1400107e2  push    r14
0x1400107e4  push    r15
0x1400107e6  mov     rbp, rsp
0x1400107e9  sub     rsp, 30h
0x1400107ed  xor     r13d, r13d
0x1400107f0  lea     rax, [rbp+hKey]
0x1400107f4  mov     r12, r9
0x1400107f7  mov     [rbp+Type], r13d
0x1400107fb  xor     r8d, r8d; ulOptions
0x1400107fe  mov     [rbp+cbData], r13d
0x140010802  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140010809  mov     [rbp+hKey], r13
0x14001080d  lea     r9d, [r13+1]; samDesired
0x140010811  mov     [r11-48h], rax
0x140010815  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001081c  mov     r15d, r13d
0x14001081f  mov     r14d, r13d
0x140010822  call    cs:__imp_RegOpenKeyExW
0x140010829  nop     dword ptr [rax+rax+00h]
0x14001082e  mov     edi, eax
0x140010830  mov     esi, 80070000h
0x140010835  test    eax, eax
0x140010837  jnz     short loc_140010846
0x140010839  mov     r15, [rbp+hKey]
0x14001083d  mov     edi, r13d
0x140010840  mov     [rbp+hKey], r13
0x140010844  jmp     short loc_140010856
0x140010846  test    edi, edi
0x140010848  jle     short loc_14001084F
0x14001084a  movzx   edi, di
0x14001084d  or      edi, esi
0x14001084f  mov     ecx, edi
0x140010851  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140010856  mov     ecx, edi
0x140010858  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001085d  mov     rcx, [rbp+hKey]; hKey
0x140010861  test    rcx, rcx
0x140010864  jz      short loc_140010876
0x140010866  call    cs:__imp_RegCloseKey
0x14001086d  nop     dword ptr [rax+rax+00h]
0x140010872  mov     [rbp+hKey], r13
0x140010876  test    edi, edi
0x140010878  js      loc_1400109AB
0x14001087e  lea     rax, [rbp+cbData]
0x140010882  xor     r8d, r8d; lpReserved
0x140010885  mov     [rsp+30h+lpcbData], rax; lpcbData
0x14001088a  lea     r9, [rbp+Type]; lpType
0x14001088e  lea     rdx, ValueName; "RollbackOnline"
0x140010895  mov     [rsp+30h+lpData], r14; lpData
0x14001089a  mov     rcx, r15; hKey
0x14001089d  call    cs:__imp_RegQueryValueExW
0x1400108a4  nop     dword ptr [rax+rax+00h]
0x1400108a9  mov     edi, eax
0x1400108ab  test    eax, eax
0x1400108ad  jnz     loc_1400109A2
0x1400108b3  test    r14, r14
0x1400108b6  jnz     short loc_140010900
0x1400108b8  mov     eax, [rbp+cbData]
0x1400108bb  test    eax, eax
0x1400108bd  jz      short loc_1400108F6
0x1400108bf  mov     ebx, eax
0x1400108c1  call    cs:__imp_GetProcessHeap
0x1400108c8  nop     dword ptr [rax+rax+00h]
0x1400108cd  mov     r8d, ebx; dwBytes
0x1400108d0  xor     edx, edx; dwFlags
0x1400108d2  mov     rcx, rax; hHeap
0x1400108d5  call    cs:__imp_HeapAlloc
0x1400108dc  nop     dword ptr [rax+rax+00h]
0x1400108e1  mov     r14, rax
0x1400108e4  test    rax, rax
0x1400108e7  jnz     short loc_14001087E
0x1400108e9  mov     r14, r13
0x1400108ec  mov     edi, 8007000Eh
0x1400108f1  jmp     loc_1400109AB
0x1400108f6  mov     edi, 8000FFFFh
0x1400108fb  jmp     loc_1400109AB
0x140010900  cmp     [rbp+Type], 2
0x140010904  jz      short loc_140010910
0x140010906  mov     edi, 8007000Dh
0x14001090b  jmp     loc_1400109AB
0x140010910  mov     eax, [rbp+cbData]
0x140010913  mov     rbx, r13
0x140010916  mov     [rbp+arg_20], rbx
0x14001091a  test    eax, eax
0x14001091c  jnz     short loc_14001092E
0x14001091e  mov     edi, 8007000Dh
0x140010923  mov     ecx, edi
0x140010925  mov     esi, edi
0x140010927  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14001092c  jmp     short loc_140010964
0x14001092e  test    al, 1
0x140010930  jnz     short loc_14001091E
0x140010932  shr     eax, 1
0x140010934  dec     eax
0x140010936  cmp     [r14+rax*2], r13w
0x14001093b  jnz     short loc_14001091E
0x14001093d  lea     rdx, [rbp+arg_20]
0x140010941  mov     rcx, r14; lpSrc
0x140010944  call    ?ExpandFileName@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z; CMiscHelpersT<CEmptyType>::ExpandFileName(ushort const *,ushort * *)
0x140010949  mov     esi, eax
0x14001094b  test    eax, eax
0x14001094d  jns     short loc_14001095C
0x14001094f  mov     ecx, eax
0x140010951  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140010956  mov     rbx, [rbp+arg_20]
0x14001095a  jmp     short loc_140010964
0x14001095c  mov     rax, [rbp+arg_20]
0x140010960  mov     [r12], rax
0x140010964  mov     ecx, esi
0x140010966  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14001096b  test    rbx, rbx
0x14001096e  jz      short loc_140010998
0x140010970  call    cs:__imp_GetProcessHeap
0x140010977  nop     dword ptr [rax+rax+00h]
0x14001097c  lea     r8, [rbx-4]; lpMem
0x140010980  xor     edx, edx; dwFlags
0x140010982  mov     rcx, rax; hHeap
0x140010985  call    cs:__imp_HeapFree
0x14001098c  nop     dword ptr [rax+rax+00h]
0x140010991  xor     ecx, ecx
0x140010993  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140010998  mov     edi, esi
0x14001099a  test    esi, esi
0x14001099c  jns     short loc_1400109B2
0x14001099e  mov     ecx, esi
0x1400109a0  jmp     short loc_1400109AD
0x1400109a2  test    edi, edi
0x1400109a4  jle     short loc_1400109AB
0x1400109a6  movzx   edi, di
0x1400109a9  or      edi, esi
0x1400109ab  mov     ecx, edi
0x1400109ad  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1400109b2  mov     ecx, edi
0x1400109b4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1400109b9  test    r14, r14
0x1400109bc  jz      short loc_1400109DE
0x1400109be  call    cs:__imp_GetProcessHeap
0x1400109c5  nop     dword ptr [rax+rax+00h]
0x1400109ca  mov     r8, r14; lpMem
0x1400109cd  xor     edx, edx; dwFlags
0x1400109cf  mov     rcx, rax; hHeap
0x1400109d2  call    cs:__imp_HeapFree
0x1400109d9  nop     dword ptr [rax+rax+00h]
0x1400109de  test    r15, r15
0x1400109e1  jz      short loc_1400109F2
0x1400109e3  mov     rcx, r15; hKey
0x1400109e6  call    cs:__imp_RegCloseKey
0x1400109ed  nop     dword ptr [rax+rax+00h]
0x1400109f2  mov     rbx, [rsp+30h+arg_18]
0x1400109fa  mov     eax, edi
0x1400109fc  add     rsp, 30h
0x140010a00  pop     r15
0x140010a02  pop     r14
0x140010a04  pop     r13
0x140010a06  pop     r12
0x140010a08  pop     rdi
0x140010a09  pop     rsi
0x140010a0a  pop     rbp
0x140010a0b  retn
```
