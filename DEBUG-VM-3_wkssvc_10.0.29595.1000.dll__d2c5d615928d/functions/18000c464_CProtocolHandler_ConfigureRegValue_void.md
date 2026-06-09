# CProtocolHandler::ConfigureRegValue(void)

- ea: `0x18000c464`
- end: `0x18000c6be`
- name: `?ConfigureRegValue@CProtocolHandler@@AEAAKXZ`
- size: `602`
- prototype: `unsigned int __fastcall(CProtocolHandler *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000c308`

## callees

- `0x18000c464`
- `0x180022b7c`
- `0x180023534`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c4b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c4b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c6a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c6a8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c536`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c629`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c536`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c629`

## string_xrefs

- `0x18000c4ad`: `System\CurrentControlSet\Services\LanmanWorkstation\Parameters`

## pseudocode

```c
__int64 __fastcall CProtocolHandler::ConfigureRegValue(CProtocolHandler *this)
{
  unsigned int v2; // eax
  unsigned int v3; // esi
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  unsigned int v6; // eax
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF
  DWORD Type; // [rsp+70h] [rbp+30h] BYREF
  unsigned int Data; // [rsp+78h] [rbp+38h] BYREF

  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 4;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\LanmanWorkstation\\Parameters",
         0,
         0x20019u,
         &hKey);
  v3 = v2;
  if ( v2 )
  {
    v4 = WPP_witness_GLOBAL_Control;
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
    {
      v5 = 15;
LABEL_6:
      WPP_SF_d(v4[2], v5, &WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids, v2);
      goto LABEL_35;
    }
    goto LABEL_35;
  }
  cbData = 4;
  v6 = RegQueryValueExW(hKey, L"WitnessKeepAliveInSeconds", 0, &Type, (LPBYTE)&Data, &cbData);
  if ( v6 )
  {
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 16, &WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids, v6);
    }
LABEL_22:
    *((_DWORD *)this + 1) = 120;
    goto LABEL_24;
  }
  if ( Type != 4 )
  {
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_witness_GLOBAL_Control + 2),
        17,
        (unsigned int)&WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids,
        (unsigned int)L"WitnessKeepAliveInSeconds",
        Type);
    }
    goto LABEL_22;
  }
  if ( Data < 0xA )
  {
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_witness_GLOBAL_Control + 2),
        18,
        (unsigned int)&WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids,
        (unsigned int)L"WitnessKeepAliveInSeconds",
        4);
    }
    goto LABEL_22;
  }
  *((_DWORD *)this + 1) = Data;
LABEL_24:
  cbData = 4;
  v2 = RegQueryValueExW(hKey, L"WitnessFlags", 0, &Type, (LPBYTE)&Data, &cbData);
  v3 = v2;
  if ( v2 )
  {
    v4 = WPP_witness_GLOBAL_Control;
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
    {
      v5 = 19;
      goto LABEL_6;
    }
  }
  else if ( Type == 4 )
  {
    *(_DWORD *)this = Data;
  }
  else if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
         && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_witness_GLOBAL_Control + 2),
      20,
      (unsigned int)&WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids,
      (unsigned int)L"WitnessFlags",
      Type);
  }
LABEL_35:
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x18000c464  mov     [rsp-18h+arg_0], rsi
0x18000c469  push    rbp
0x18000c46a  push    rdi
0x18000c46b  push    r15
0x18000c46d  mov     rbp, rsp
0x18000c470  sub     rsp, 40h
0x18000c474  mov     r15, rcx
0x18000c477  mov     [rbp+hKey], 0
0x18000c47f  lea     rax, [rbp+hKey]
0x18000c483  mov     [rbp+Type], 0
0x18000c48a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c491  mov     [rsp+40h+phkResult], rax; phkResult
0x18000c496  mov     r9d, 20019h; samDesired
0x18000c49c  mov     [rbp+Data], 0
0x18000c4a3  xor     r8d, r8d; ulOptions
0x18000c4a6  mov     [rbp+cbData], 4
0x18000c4ad  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\La"...
0x18000c4b4  call    cs:__imp_RegOpenKeyExW
0x18000c4ba  mov     esi, eax
0x18000c4bc  test    eax, eax
0x18000c4be  jz      short loc_18000C508
0x18000c4c0  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000c4c7  lea     rdi, WPP_witness_GLOBAL_Control
0x18000c4ce  cmp     rcx, rdi
0x18000c4d1  jz      loc_18000C69F
0x18000c4d7  test    byte ptr [rcx+1Ch], 1
0x18000c4db  jz      loc_18000C69F
0x18000c4e1  cmp     byte ptr [rcx+19h], 1
0x18000c4e5  jb      loc_18000C69F
0x18000c4eb  mov     edx, 0Fh
0x18000c4f0  mov     rcx, [rcx+10h]
0x18000c4f4  lea     r8, WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids
0x18000c4fb  mov     r9d, eax
0x18000c4fe  call    WPP_SF_d
0x18000c503  jmp     loc_18000C69F
0x18000c508  mov     rcx, [rbp+hKey]; hKey
0x18000c50c  lea     rax, [rbp+cbData]
0x18000c510  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000c515  lea     rsi, aWitnesskeepali; "WitnessKeepAliveInSeconds"
0x18000c51c  lea     rax, [rbp+Data]
0x18000c520  mov     [rbp+cbData], 4
0x18000c527  lea     r9, [rbp+Type]; lpType
0x18000c52b  mov     [rsp+40h+phkResult], rax; lpData
0x18000c530  xor     r8d, r8d; lpReserved
0x18000c533  mov     rdx, rsi; lpValueName
0x18000c536  call    cs:__imp_RegQueryValueExW
0x18000c53c  lea     rdi, WPP_witness_GLOBAL_Control
0x18000c543  test    eax, eax
0x18000c545  jz      short loc_18000C585
0x18000c547  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000c54e  cmp     rcx, rdi
0x18000c551  jz      loc_18000C5F0
0x18000c557  test    byte ptr [rcx+1Ch], 1
0x18000c55b  jz      loc_18000C5F0
0x18000c561  cmp     byte ptr [rcx+19h], 1
0x18000c565  jb      loc_18000C5F0
0x18000c56b  mov     rcx, [rcx+10h]
0x18000c56f  lea     r8, WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids
0x18000c576  mov     edx, 10h
0x18000c57b  mov     r9d, eax
0x18000c57e  call    WPP_SF_d
0x18000c583  jmp     short loc_18000C5F0
0x18000c585  mov     eax, [rbp+Type]
0x18000c588  cmp     eax, 4
0x18000c58b  jz      short loc_18000C5B0
0x18000c58d  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000c594  cmp     rcx, rdi
0x18000c597  jz      short loc_18000C5F0
0x18000c599  test    byte ptr [rcx+1Ch], 1
0x18000c59d  jz      short loc_18000C5F0
0x18000c59f  cmp     byte ptr [rcx+19h], 1
0x18000c5a3  jb      short loc_18000C5F0
0x18000c5a5  mov     edx, 11h
0x18000c5aa  mov     dword ptr [rsp+40h+phkResult], eax
0x18000c5ae  jmp     short loc_18000C5DD
0x18000c5b0  mov     eax, [rbp+Data]
0x18000c5b3  cmp     eax, 0Ah
0x18000c5b6  jnb     short loc_18000C5FA
0x18000c5b8  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000c5bf  cmp     rcx, rdi
0x18000c5c2  jz      short loc_18000C5F0
0x18000c5c4  test    byte ptr [rcx+1Ch], 1
0x18000c5c8  jz      short loc_18000C5F0
0x18000c5ca  cmp     byte ptr [rcx+19h], 1
0x18000c5ce  jb      short loc_18000C5F0
0x18000c5d0  mov     edx, 12h
0x18000c5d5  mov     dword ptr [rsp+40h+phkResult], 4
0x18000c5dd  mov     rcx, [rcx+10h]
0x18000c5e1  lea     r8, WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids
0x18000c5e8  mov     r9, rsi
0x18000c5eb  call    WPP_SF_Sd
0x18000c5f0  mov     dword ptr [r15+4], 78h ; 'x'
0x18000c5f8  jmp     short loc_18000C5FE
0x18000c5fa  mov     [r15+4], eax
0x18000c5fe  mov     rcx, [rbp+hKey]; hKey
0x18000c602  lea     rax, [rbp+cbData]
0x18000c606  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000c60b  lea     r9, [rbp+Type]; lpType
0x18000c60f  lea     rax, [rbp+Data]
0x18000c613  mov     [rbp+cbData], 4
0x18000c61a  xor     r8d, r8d; lpReserved
0x18000c61d  mov     [rsp+40h+phkResult], rax; lpData
0x18000c622  lea     rdx, aWitnessflags; "WitnessFlags"
0x18000c629  call    cs:__imp_RegQueryValueExW
0x18000c62f  mov     esi, eax
0x18000c631  test    eax, eax
0x18000c633  jz      short loc_18000C657
0x18000c635  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000c63c  cmp     rcx, rdi
0x18000c63f  jz      short loc_18000C69F
0x18000c641  test    byte ptr [rcx+1Ch], 1
0x18000c645  jz      short loc_18000C69F
0x18000c647  cmp     byte ptr [rcx+19h], 1
0x18000c64b  jb      short loc_18000C69F
0x18000c64d  mov     edx, 13h
0x18000c652  jmp     loc_18000C4F0
0x18000c657  mov     eax, [rbp+Type]
0x18000c65a  cmp     eax, 4
0x18000c65d  jz      short loc_18000C699
0x18000c65f  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000c666  cmp     rcx, rdi
0x18000c669  jz      short loc_18000C69F
0x18000c66b  test    byte ptr [rcx+1Ch], 1
0x18000c66f  jz      short loc_18000C69F
0x18000c671  cmp     byte ptr [rcx+19h], 1
0x18000c675  jb      short loc_18000C69F
0x18000c677  mov     rcx, [rcx+10h]
0x18000c67b  lea     r9, aWitnessflags; "WitnessFlags"
0x18000c682  mov     edx, 14h
0x18000c687  mov     dword ptr [rsp+40h+phkResult], eax
0x18000c68b  lea     r8, WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids
0x18000c692  call    WPP_SF_Sd
0x18000c697  jmp     short loc_18000C69F
0x18000c699  mov     eax, [rbp+Data]
0x18000c69c  mov     [r15], eax
0x18000c69f  mov     rcx, [rbp+hKey]; hKey
0x18000c6a3  test    rcx, rcx
0x18000c6a6  jz      short loc_18000C6AE
0x18000c6a8  call    cs:__imp_RegCloseKey
0x18000c6ae  mov     eax, esi
0x18000c6b0  mov     rsi, [rsp+40h+arg_0]
0x18000c6b5  add     rsp, 40h
0x18000c6b9  pop     r15
0x18000c6bb  pop     rdi
0x18000c6bc  pop     rbp
0x18000c6bd  retn
```
