# CRegUtilT<ulong,CRegType,0,0>::CreateOrOpenKey(HKEY__ *,ushort const *)

- ea: `0x140006924`
- end: `0x140006a64`
- name: `?CreateOrOpenKey@?$CRegUtilT@KUCRegType@@$0A@$0A@@@SAJPEAUHKEY__@@PEBG@Z`
- size: `320`
- prototype: `__int64 __fastcall(HKEY hKey, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140007dcc`

## callees

- `0x140003454`
- `0x140004780`
- `0x140006924`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400069f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006a3c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400069f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140006a3c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400069ac`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400069ac`

## pseudocode

```c
__int64 __fastcall CRegUtilT<unsigned long,CRegType,0,0>::CreateOrOpenKey(HKEY hKey, __int64 a2)
{
  int v3; // eax
  HKEY v4; // rbx
  unsigned int v5; // edi
  HKEY hKeya; // [rsp+80h] [rbp+8h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp+10h] BYREF
  int v9; // [rsp+8Ch] [rbp+14h]

  v9 = HIDWORD(a2);
  dwDisposition = 0;
  if ( hKey == HKEY_CURRENT_USER )
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  hKeya = 0;
  v3 = RegCreateKeyExW(
         hKey,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\MfaRequiredInClipRenew",
         0,
         0,
         0,
         0x20019u,
         0,
         &hKeya,
         &dwDisposition);
  if ( v3 )
  {
    v4 = 0;
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
    v5 = v3;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v3);
  }
  else
  {
    v4 = hKeya;
    v5 = 0;
    hKeya = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( hKeya )
    RegCloseKey(hKeya);
  if ( (v5 & 0x80000000) != 0 )
    goto LABEL_11;
  if ( dwDisposition == 1 )
  {
    v5 = 0;
  }
  else
  {
    if ( dwDisposition != 2 )
    {
      v5 = -2147418113;
LABEL_11:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
      goto LABEL_17;
    }
    v5 = 1;
  }
LABEL_17:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( v4 )
    RegCloseKey(v4);
  if ( (v5 & 0x80000000) != 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  return v5;
}

```

## disassembly

```asm
0x140006924  mov     rax, rsp
0x140006927  mov     [rax+18h], rbx
0x14000692b  mov     [rax+10h], rdx
0x14000692f  push    rdi
0x140006930  sub     rsp, 70h
0x140006934  mov     dword ptr [rax+10h], 0
0x14000693b  mov     rbx, rcx
0x14000693e  cmp     rcx, 0FFFFFFFF80000001h
0x140006945  jnz     short loc_14000694E
0x140006947  xor     ecx, ecx
0x140006949  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000694e  xor     eax, eax
0x140006950  mov     [rsp+78h+hKey], 0
0x14000695c  mov     [rsp+78h+var_18], rax
0x140006961  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140006968  lea     rax, [rsp+78h+dwDisposition]
0x140006970  xorps   xmm0, xmm0
0x140006973  mov     [rsp+78h+lpdwDisposition], rax; lpdwDisposition
0x140006978  xor     r9d, r9d; lpClass
0x14000697b  lea     rax, [rsp+78h+hKey]
0x140006983  xor     r8d, r8d; Reserved
0x140006986  mov     [rsp+78h+phkResult], rax; phkResult
0x14000698b  mov     rcx, rbx; hKey
0x14000698e  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140006997  mov     [rsp+78h+samDesired], 20019h; samDesired
0x14000699f  mov     [rsp+78h+dwOptions], 0; dwOptions
0x1400069a7  movups  [rsp+78h+var_28], xmm0
0x1400069ac  call    cs:__imp_RegCreateKeyExW
0x1400069b2  test    eax, eax
0x1400069b4  jz      short loc_1400069CF
0x1400069b6  xor     ebx, ebx
0x1400069b8  test    eax, eax
0x1400069ba  jle     short loc_1400069C4
0x1400069bc  movzx   eax, ax
0x1400069bf  or      eax, 80070000h
0x1400069c4  mov     ecx, eax
0x1400069c6  mov     edi, eax
0x1400069c8  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1400069cd  jmp     short loc_1400069E5
0x1400069cf  mov     rbx, [rsp+78h+hKey]
0x1400069d7  xor     edi, edi
0x1400069d9  mov     [rsp+78h+hKey], 0
0x1400069e5  mov     ecx, edi
0x1400069e7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1400069ec  mov     rcx, [rsp+78h+hKey]; hKey
0x1400069f4  test    rcx, rcx
0x1400069f7  jz      short loc_1400069FF
0x1400069f9  call    cs:__imp_RegCloseKey
0x1400069ff  test    edi, edi
0x140006a01  jns     short loc_140006A0C
0x140006a03  mov     ecx, edi
0x140006a05  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140006a0a  jmp     short loc_140006A2D
0x140006a0c  mov     eax, [rsp+78h+dwDisposition]
0x140006a13  sub     eax, 1
0x140006a16  jz      short loc_140006A2B
0x140006a18  cmp     eax, 1
0x140006a1b  jz      short loc_140006A24
0x140006a1d  mov     edi, 8000FFFFh
0x140006a22  jmp     short loc_140006A03
0x140006a24  mov     edi, 1
0x140006a29  jmp     short loc_140006A2D
0x140006a2b  xor     edi, edi
0x140006a2d  mov     ecx, edi
0x140006a2f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140006a34  test    rbx, rbx
0x140006a37  jz      short loc_140006A42
0x140006a39  mov     rcx, rbx; hKey
0x140006a3c  call    cs:__imp_RegCloseKey
0x140006a42  test    edi, edi
0x140006a44  jns     short loc_140006A4D
0x140006a46  mov     ecx, edi
0x140006a48  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140006a4d  mov     ecx, edi
0x140006a4f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x140006a54  mov     rbx, [rsp+78h+arg_10]
0x140006a5c  mov     eax, edi
0x140006a5e  add     rsp, 70h
0x140006a62  pop     rdi
0x140006a63  retn
```
