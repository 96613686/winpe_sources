# CMonitorEvents::RegRead(void)

- ea: `0x18000a6d8`
- end: `0x18000aa8c`
- name: `?RegRead@CMonitorEvents@@QEAAXXZ`
- size: `948`
- prototype: `void __fastcall(CMonitorEvents *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b2b4`

## callees

- `0x18000a6d8`
- `0x18000b648`
- `0x18001323c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a71a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a71a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aa31`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aa31`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a762`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a816`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a8c3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a970`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000aa27`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a762`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a816`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a8c3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a970`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000aa27`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000a7a4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000a851`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000a8fe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000a9ab`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000a7a4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000a851`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000a8fe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000a9ab`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000a7b8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000a865`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000a912`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000a9bf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000aa45`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000a7b8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000a865`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000a912`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000a9bf`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000aa45`
- `wbemcomn!GetMemLogObject` at `0x18000a7ac`
- `wbemcomn!GetMemLogObject` at `0x18000a859`
- `wbemcomn!GetMemLogObject` at `0x18000a906`
- `wbemcomn!GetMemLogObject` at `0x18000a9b3`
- `wbemcomn!GetMemLogObject` at `0x18000aa39`
- `wbemcomn!GetMemLogObject` at `0x18000a7ac`
- `wbemcomn!GetMemLogObject` at `0x18000a859`
- `wbemcomn!GetMemLogObject` at `0x18000a906`
- `wbemcomn!GetMemLogObject` at `0x18000a9b3`
- `wbemcomn!GetMemLogObject` at `0x18000aa39`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMonitorEvents::RegRead(BYTE *this)
{
  HKEY v2; // rbx
  LSTATUS v3; // eax
  CMemoryLog *v4; // rax
  LSTATUS v5; // eax
  CMemoryLog *v6; // rax
  LSTATUS v7; // eax
  CMemoryLog *v8; // rax
  LSTATUS v9; // eax
  CMemoryLog *v10; // rax
  CMemoryLog *MemLogObject; // rax
  HKEY hKey[2]; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+38h] BYREF
  DWORD Type; // [rsp+80h] [rbp+40h] BYREF
  int Data; // [rsp+88h] [rbp+48h] BYREF

  hKey[0] = 0;
  Data = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\WBEM\\CIMOM", 0, 0x2001Fu, hKey) )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -1);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_c9be8021473137ba96341d1ad3a34b20_Traceguids);
    }
  }
  else
  {
    v2 = hKey[0];
    hKey[1] = hKey[0];
    Type = 0;
    cbData = 4;
    v3 = RegQueryValueExW(hKey[0], L"ADAPDelay", 0, &Type, this + 552, &cbData);
    if ( v3 || Type != 4 )
    {
      if ( v3 == 2 )
      {
        Data = 240;
        RegSetValueExW(hKey[0], L"ADAPDelay", 0, 4u, (const BYTE *)&Data, 4u);
      }
      else
      {
        v4 = GetMemLogObject();
        CMemoryLog::Write(v4, -1);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_c9be8021473137ba96341d1ad3a34b20_Traceguids);
        }
      }
    }
    cbData = 4;
    v5 = RegQueryValueExW(hKey[0], L"LodCtrDelay", 0, &Type, this + 556, &cbData);
    if ( v5 || Type != 4 )
    {
      if ( v5 == 2 )
      {
        Data = 60;
        RegSetValueExW(hKey[0], L"LodCtrDelay", 0, 4u, (const BYTE *)&Data, 4u);
      }
      else
      {
        v6 = GetMemLogObject();
        CMemoryLog::Write(v6, -1);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_c9be8021473137ba96341d1ad3a34b20_Traceguids);
        }
      }
    }
    cbData = 4;
    v7 = RegQueryValueExW(hKey[0], L"TimeToFullDredge", 0, &Type, this + 560, &cbData);
    if ( v7 || Type != 4 )
    {
      if ( v7 == 2 )
      {
        Data = -1;
        RegSetValueExW(hKey[0], L"TimeToFullDredge", 0, 4u, (const BYTE *)&Data, 4u);
      }
      else
      {
        v8 = GetMemLogObject();
        CMemoryLog::Write(v8, -1);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_c9be8021473137ba96341d1ad3a34b20_Traceguids);
        }
      }
    }
    cbData = 4;
    v9 = RegQueryValueExW(hKey[0], L"TimeToTerminateAdap", 0, &Type, this + 564, &cbData);
    if ( v9 || Type != 4 )
    {
      if ( v9 == 2 )
      {
        Data = 600000;
        RegSetValueExW(hKey[0], L"TimeToTerminateAdap", 0, 4u, (const BYTE *)&Data, 4u);
      }
      else
      {
        v10 = GetMemLogObject();
        CMemoryLog::Write(v10, -1);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            WPP_c9be8021473137ba96341d1ad3a34b20_Traceguids,
            L"TimeToTerminateAdap");
        }
      }
    }
    cbData = 8;
    RegQueryValueExW(hKey[0], L"LastFullDredgeTimestamp", 0, &Type, this + 568, &cbData);
    RegCloseKey(v2);
  }
}

```

## disassembly

```asm
0x18000a6d8  push    rbp
0x18000a6da  push    rbx
0x18000a6db  push    r12
0x18000a6dd  push    r13
0x18000a6df  push    r15
0x18000a6e1  mov     rbp, rsp
0x18000a6e4  sub     rsp, 40h
0x18000a6e8  mov     r13, rcx
0x18000a6eb  mov     [rbp+hKey], 0
0x18000a6f3  mov     [rbp+Data], 0
0x18000a6fa  lea     rax, [rbp+hKey]
0x18000a6fe  mov     [rsp+40h+phkResult], rax; phkResult
0x18000a703  mov     r9d, 2001Fh; samDesired
0x18000a709  xor     r8d, r8d; ulOptions
0x18000a70c  lea     rdx, SubKey; "Software\\Microsoft\\WBEM\\CIMOM"
0x18000a713  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a71a  call    cs:__imp_RegOpenKeyExW
0x18000a720  test    eax, eax
0x18000a722  jnz     loc_18000AA39
0x18000a728  mov     rbx, [rbp+hKey]
0x18000a72c  mov     [rbp+var_8], rbx
0x18000a730  mov     [rbp+Type], eax
0x18000a733  lea     r12d, [rax+4]
0x18000a737  mov     [rbp+cbData], r12d
0x18000a73b  lea     rax, [r13+228h]
0x18000a742  lea     rcx, [rbp+cbData]
0x18000a746  mov     [rsp+40h+lpcbData], rcx; lpcbData
0x18000a74b  mov     [rsp+40h+phkResult], rax; lpData
0x18000a750  lea     r9, [rbp+Type]; lpType
0x18000a754  xor     r8d, r8d; lpReserved
0x18000a757  lea     rdx, aAdapdelay; "ADAPDelay"
0x18000a75e  mov     rcx, [rbp+hKey]; hKey
0x18000a762  call    cs:__imp_RegQueryValueExW
0x18000a768  lea     r15, WPP_GLOBAL_Control
0x18000a76f  test    eax, eax
0x18000a771  jnz     short loc_18000A779
0x18000a773  cmp     [rbp+Type], r12d
0x18000a777  jz      short loc_18000A7EB
0x18000a779  cmp     eax, 2
0x18000a77c  jnz     short loc_18000A7AC
0x18000a77e  mov     [rbp+Data], 0F0h
0x18000a785  mov     dword ptr [rsp+40h+lpcbData], r12d; cbData
0x18000a78a  lea     rax, [rbp+Data]
0x18000a78e  mov     [rsp+40h+phkResult], rax; lpData
0x18000a793  mov     r9d, r12d; dwType
0x18000a796  xor     r8d, r8d; Reserved
0x18000a799  lea     rdx, aAdapdelay; "ADAPDelay"
0x18000a7a0  mov     rcx, [rbp+hKey]; hKey
0x18000a7a4  call    cs:__imp_RegSetValueExW
0x18000a7aa  jmp     short loc_18000A7EB
0x18000a7ac  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000a7b2  or      edx, 0FFFFFFFFh
0x18000a7b5  mov     rcx, rax
0x18000a7b8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000a7be  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a7c5  cmp     rcx, r15
0x18000a7c8  jz      short loc_18000A7EB
0x18000a7ca  test    byte ptr [rcx+1Ch], 1
0x18000a7ce  jz      short loc_18000A7EB
0x18000a7d0  cmp     byte ptr [rcx+19h], 2
0x18000a7d4  jb      short loc_18000A7EB
0x18000a7d6  mov     edx, 0Bh
0x18000a7db  lea     r8, WPP_c9be8021473137ba96341d1ad3a34b20_Traceguids
0x18000a7e2  mov     rcx, [rcx+10h]
0x18000a7e6  call    WPP_SF_
0x18000a7eb  mov     [rbp+cbData], r12d
0x18000a7ef  lea     rax, [r13+22Ch]
0x18000a7f6  lea     rcx, [rbp+cbData]
0x18000a7fa  mov     [rsp+40h+lpcbData], rcx; lpcbData
0x18000a7ff  mov     [rsp+40h+phkResult], rax; lpData
0x18000a804  lea     r9, [rbp+Type]; lpType
0x18000a808  xor     r8d, r8d; lpReserved
0x18000a80b  lea     rdx, aLodctrdelay; "LodCtrDelay"
0x18000a812  mov     rcx, [rbp+hKey]; hKey
0x18000a816  call    cs:__imp_RegQueryValueExW
0x18000a81c  test    eax, eax
0x18000a81e  jnz     short loc_18000A826
0x18000a820  cmp     [rbp+Type], r12d
0x18000a824  jz      short loc_18000A898
0x18000a826  cmp     eax, 2
0x18000a829  jnz     short loc_18000A859
0x18000a82b  mov     [rbp+Data], 3Ch ; '<'
0x18000a832  mov     dword ptr [rsp+40h+lpcbData], r12d; cbData
0x18000a837  lea     rax, [rbp+Data]
0x18000a83b  mov     [rsp+40h+phkResult], rax; lpData
0x18000a840  mov     r9d, r12d; dwType
0x18000a843  xor     r8d, r8d; Reserved
0x18000a846  lea     rdx, aLodctrdelay; "LodCtrDelay"
0x18000a84d  mov     rcx, [rbp+hKey]; hKey
0x18000a851  call    cs:__imp_RegSetValueExW
0x18000a857  jmp     short loc_18000A898
0x18000a859  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000a85f  or      edx, 0FFFFFFFFh
0x18000a862  mov     rcx, rax
0x18000a865  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000a86b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a872  cmp     rcx, r15
0x18000a875  jz      short loc_18000A898
0x18000a877  test    byte ptr [rcx+1Ch], 1
0x18000a87b  jz      short loc_18000A898
0x18000a87d  cmp     byte ptr [rcx+19h], 2
0x18000a881  jb      short loc_18000A898
0x18000a883  mov     edx, 0Ch
0x18000a888  lea     r8, WPP_c9be8021473137ba96341d1ad3a34b20_Traceguids
0x18000a88f  mov     rcx, [rcx+10h]
0x18000a893  call    WPP_SF_
0x18000a898  mov     [rbp+cbData], r12d
0x18000a89c  lea     rax, [r13+230h]
0x18000a8a3  lea     rcx, [rbp+cbData]
0x18000a8a7  mov     [rsp+40h+lpcbData], rcx; lpcbData
0x18000a8ac  mov     [rsp+40h+phkResult], rax; lpData
0x18000a8b1  lea     r9, [rbp+Type]; lpType
0x18000a8b5  xor     r8d, r8d; lpReserved
0x18000a8b8  lea     rdx, aTimetofulldred; "TimeToFullDredge"
0x18000a8bf  mov     rcx, [rbp+hKey]; hKey
0x18000a8c3  call    cs:__imp_RegQueryValueExW
0x18000a8c9  test    eax, eax
0x18000a8cb  jnz     short loc_18000A8D3
0x18000a8cd  cmp     [rbp+Type], r12d
0x18000a8d1  jz      short loc_18000A945
0x18000a8d3  cmp     eax, 2
0x18000a8d6  jnz     short loc_18000A906
0x18000a8d8  mov     [rbp+Data], 0FFFFFFFFh
0x18000a8df  mov     dword ptr [rsp+40h+lpcbData], r12d; cbData
0x18000a8e4  lea     rax, [rbp+Data]
0x18000a8e8  mov     [rsp+40h+phkResult], rax; lpData
0x18000a8ed  mov     r9d, r12d; dwType
0x18000a8f0  xor     r8d, r8d; Reserved
0x18000a8f3  lea     rdx, aTimetofulldred; "TimeToFullDredge"
0x18000a8fa  mov     rcx, [rbp+hKey]; hKey
0x18000a8fe  call    cs:__imp_RegSetValueExW
0x18000a904  jmp     short loc_18000A945
0x18000a906  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000a90c  or      edx, 0FFFFFFFFh
0x18000a90f  mov     rcx, rax
0x18000a912  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000a918  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a91f  cmp     rcx, r15
0x18000a922  jz      short loc_18000A945
0x18000a924  test    byte ptr [rcx+1Ch], 1
0x18000a928  jz      short loc_18000A945
0x18000a92a  cmp     byte ptr [rcx+19h], 2
0x18000a92e  jb      short loc_18000A945
0x18000a930  mov     edx, 0Dh
0x18000a935  lea     r8, WPP_c9be8021473137ba96341d1ad3a34b20_Traceguids
0x18000a93c  mov     rcx, [rcx+10h]
0x18000a940  call    WPP_SF_
0x18000a945  mov     [rbp+cbData], r12d
0x18000a949  lea     rax, [r13+234h]
0x18000a950  lea     rcx, [rbp+cbData]
0x18000a954  mov     [rsp+40h+lpcbData], rcx; lpcbData
0x18000a959  mov     [rsp+40h+phkResult], rax; lpData
0x18000a95e  lea     r9, [rbp+Type]; lpType
0x18000a962  xor     r8d, r8d; lpReserved
0x18000a965  lea     rdx, aTimetoterminat; "TimeToTerminateAdap"
0x18000a96c  mov     rcx, [rbp+hKey]; hKey
0x18000a970  call    cs:__imp_RegQueryValueExW
0x18000a976  test    eax, eax
0x18000a978  jnz     short loc_18000A980
0x18000a97a  cmp     [rbp+Type], r12d
0x18000a97e  jz      short loc_18000A9F9
0x18000a980  cmp     eax, 2
0x18000a983  jnz     short loc_18000A9B3
0x18000a985  mov     [rbp+Data], 927C0h
0x18000a98c  mov     dword ptr [rsp+40h+lpcbData], r12d; cbData
0x18000a991  lea     rax, [rbp+Data]
0x18000a995  mov     [rsp+40h+phkResult], rax; lpData
0x18000a99a  mov     r9d, r12d; dwType
0x18000a99d  xor     r8d, r8d; Reserved
0x18000a9a0  lea     rdx, aTimetoterminat; "TimeToTerminateAdap"
0x18000a9a7  mov     rcx, [rbp+hKey]; hKey
0x18000a9ab  call    cs:__imp_RegSetValueExW
0x18000a9b1  jmp     short loc_18000A9F9
0x18000a9b3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000a9b9  or      edx, 0FFFFFFFFh
0x18000a9bc  mov     rcx, rax
0x18000a9bf  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000a9c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a9cc  cmp     rcx, r15
0x18000a9cf  jz      short loc_18000A9F9
0x18000a9d1  test    byte ptr [rcx+1Ch], 1
0x18000a9d5  jz      short loc_18000A9F9
0x18000a9d7  cmp     byte ptr [rcx+19h], 2
0x18000a9db  jb      short loc_18000A9F9
0x18000a9dd  mov     edx, 0Eh
0x18000a9e2  lea     r9, aTimetoterminat; "TimeToTerminateAdap"
0x18000a9e9  lea     r8, WPP_c9be8021473137ba96341d1ad3a34b20_Traceguids
0x18000a9f0  mov     rcx, [rcx+10h]
0x18000a9f4  call    WPP_SF_S
0x18000a9f9  mov     [rbp+cbData], 8
0x18000aa00  lea     rax, [r13+238h]
0x18000aa07  lea     rcx, [rbp+cbData]
0x18000aa0b  mov     [rsp+40h+lpcbData], rcx; lpcbData
0x18000aa10  mov     [rsp+40h+phkResult], rax; lpData
0x18000aa15  lea     r9, [rbp+Type]; lpType
0x18000aa19  xor     r8d, r8d; lpReserved
0x18000aa1c  lea     rdx, aLastfulldredge; "LastFullDredgeTimestamp"
0x18000aa23  mov     rcx, [rbp+hKey]; hKey
0x18000aa27  call    cs:__imp_RegQueryValueExW
0x18000aa2d  nop
0x18000aa2e  mov     rcx, rbx; hKey
0x18000aa31  call    cs:__imp_RegCloseKey
0x18000aa37  jmp     short loc_18000AA7F
0x18000aa39  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000aa3f  or      edx, 0FFFFFFFFh
0x18000aa42  mov     rcx, rax
0x18000aa45  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000aa4b  lea     r15, WPP_GLOBAL_Control
0x18000aa52  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa59  cmp     rcx, r15
0x18000aa5c  jz      short loc_18000AA7F
0x18000aa5e  test    byte ptr [rcx+1Ch], 1
0x18000aa62  jz      short loc_18000AA7F
0x18000aa64  cmp     byte ptr [rcx+19h], 2
0x18000aa68  jb      short loc_18000AA7F
0x18000aa6a  mov     edx, 0Fh
0x18000aa6f  lea     r8, WPP_c9be8021473137ba96341d1ad3a34b20_Traceguids
0x18000aa76  mov     rcx, [rcx+10h]
0x18000aa7a  call    WPP_SF_
0x18000aa7f  add     rsp, 40h
0x18000aa83  pop     r15
0x18000aa85  pop     r13
0x18000aa87  pop     r12
0x18000aa89  pop     rbx
0x18000aa8a  pop     rbp
0x18000aa8b  retn
```
