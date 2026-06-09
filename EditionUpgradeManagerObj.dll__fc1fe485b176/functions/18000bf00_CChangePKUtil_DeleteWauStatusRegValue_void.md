# CChangePKUtil::DeleteWauStatusRegValue(void)

- ea: `0x18000bf00`
- end: `0x18000c0c5`
- name: `?DeleteWauStatusRegValue@CChangePKUtil@@SAJXZ`
- size: `453`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000aae0`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x18000be7c`
- `0x18000bf00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000c05d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000c05d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bf6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c019`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c08b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000bf6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c019`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c08b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bfda`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bfda`

## pseudocode

```c
__int64 __fastcall CChangePKUtil::DeleteWauStatusRegValue(__int64 a1, __int64 a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v4; // edi
  __int64 v5; // rdx
  LSTATUS v6; // eax
  __int64 v7; // rdx
  int v8; // eax
  HKEY v9; // rdi
  __int64 v10; // rcx
  LSTATUS v11; // eax
  HKEY hKey; // [rsp+50h] [rbp+20h] BYREF
  DWORD Type; // [rsp+58h] [rbp+28h] BYREF
  HKEY v15; // [rsp+60h] [rbp+30h] BYREF

  hKey = 0;
  v2 = CRegUtilT<unsigned long,CRegType,0,0>::RegOpenKeyAccess64BitView<0>(-2147483646, a2, 1, &hKey);
  v3 = v2;
  if ( !(_WORD)v2 )
  {
    v4 = 1;
    goto LABEL_7;
  }
  v4 = 0;
  if ( (unsigned __int16)v2 == 2 )
  {
LABEL_7:
    v3 = 0;
    goto LABEL_8;
  }
  if ( v2 >= 0 )
    v3 = -2147467259;
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v3);
LABEL_8:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  if ( hKey )
    RegCloseKey(hKey);
  if ( (v3 & 0x80000000) != 0 )
    goto LABEL_36;
  if ( v4 != 1 )
    goto LABEL_37;
  v15 = 0;
  Type = 0;
  LODWORD(hKey) = 0;
  v6 = CRegUtilT<unsigned long,CRegType,0,0>::RegOpenKeyAccess64BitView<0>(-2147483646, v5, 1, &v15);
  v3 = v6;
  if ( v6 < 0 )
    goto LABEL_13;
  v6 = RegQueryValueExW(v15, L"Status", 0, &Type, 0, (LPDWORD)&hKey);
  if ( v6 )
  {
    if ( v6 != 2 )
    {
      if ( v6 > 0 )
      {
        v3 = (unsigned __int16)v6 | 0x80070000;
        v6 = v3;
      }
      else
      {
        v3 = v6;
      }
LABEL_13:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v6);
      goto LABEL_21;
    }
    v4 = 0;
  }
  else
  {
    v4 = 1;
  }
LABEL_21:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  if ( v15 )
    RegCloseKey(v15);
  if ( (v3 & 0x80000000) != 0 )
    goto LABEL_36;
  if ( v4 != 1 )
    goto LABEL_37;
  hKey = 0;
  v8 = CRegUtilT<unsigned long,CRegType,0,0>::RegOpenKeyAccess64BitView<0>(-2147483646, v7, 2, &hKey);
  v9 = hKey;
  v3 = v8;
  if ( v8 < 0 )
  {
    v10 = (unsigned int)v8;
LABEL_27:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v10);
    goto LABEL_33;
  }
  v11 = RegDeleteValueW(hKey, L"Status");
  v3 = v11;
  if ( v11 )
  {
    if ( v11 > 0 )
      v3 = (unsigned __int16)v11 | 0x80070000;
    v10 = v3;
    goto LABEL_27;
  }
  v3 = 0;
LABEL_33:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  if ( v9 )
    RegCloseKey(v9);
  if ( (v3 & 0x80000000) != 0 )
LABEL_36:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v3);
LABEL_37:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  if ( (v3 & 0x80000000) != 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v3);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  return v3;
}

```

## disassembly

```asm
0x18000bf00  mov     [rsp-18h+arg_18], rbx
0x18000bf05  push    rbp
0x18000bf06  push    rdi
0x18000bf07  push    r12
0x18000bf09  mov     rbp, rsp
0x18000bf0c  sub     rsp, 30h
0x18000bf10  mov     r12, 0FFFFFFFF80000002h
0x18000bf17  mov     [rbp+hKey], 0
0x18000bf1f  mov     rcx, r12
0x18000bf22  lea     r9, [rbp+hKey]
0x18000bf26  mov     r8d, 1
0x18000bf2c  call    ??$RegOpenKeyAccess64BitView@$0A@@?$CRegUtilT@KUCRegType@@$0A@$0A@@@CAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; CRegUtilT<ulong,CRegType,0,0>::RegOpenKeyAccess64BitView<0>(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x18000bf31  mov     ebx, eax
0x18000bf33  movzx   eax, ax
0x18000bf36  test    eax, eax
0x18000bf38  jz      short loc_18000BF54
0x18000bf3a  xor     edi, edi
0x18000bf3c  cmp     eax, 2
0x18000bf3f  jz      short loc_18000BF59
0x18000bf41  test    ebx, ebx
0x18000bf43  mov     eax, 80004005h
0x18000bf48  cmovns  ebx, eax
0x18000bf4b  mov     ecx, ebx
0x18000bf4d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000bf52  jmp     short loc_18000BF5B
0x18000bf54  mov     edi, 1
0x18000bf59  xor     ebx, ebx
0x18000bf5b  mov     ecx, ebx
0x18000bf5d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000bf62  mov     rcx, [rbp+hKey]; hKey
0x18000bf66  test    rcx, rcx
0x18000bf69  jz      short loc_18000BF71
0x18000bf6b  call    cs:__imp_RegCloseKey
0x18000bf71  test    ebx, ebx
0x18000bf73  js      loc_18000C095
0x18000bf79  cmp     edi, 1
0x18000bf7c  jnz     loc_18000C09C
0x18000bf82  lea     r9, [rbp+arg_10]
0x18000bf86  mov     [rbp+arg_10], 0
0x18000bf8e  mov     r8d, edi
0x18000bf91  mov     [rbp+Type], 0
0x18000bf98  mov     rcx, r12
0x18000bf9b  mov     dword ptr [rbp+hKey], 0
0x18000bfa2  call    ??$RegOpenKeyAccess64BitView@$0A@@?$CRegUtilT@KUCRegType@@$0A@$0A@@@CAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; CRegUtilT<ulong,CRegType,0,0>::RegOpenKeyAccess64BitView<0>(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x18000bfa7  mov     ebx, eax
0x18000bfa9  test    eax, eax
0x18000bfab  jns     short loc_18000BFB6
0x18000bfad  mov     ecx, eax
0x18000bfaf  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000bfb4  jmp     short loc_18000C007
0x18000bfb6  mov     rcx, [rbp+arg_10]; hKey
0x18000bfba  lea     rax, [rbp+hKey]
0x18000bfbe  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000bfc3  lea     r9, [rbp+Type]; lpType
0x18000bfc7  xor     r8d, r8d; lpReserved
0x18000bfca  mov     [rsp+30h+lpData], 0; lpData
0x18000bfd3  lea     rdx, ValueName; "Status"
0x18000bfda  call    cs:__imp_RegQueryValueExW
0x18000bfe0  test    eax, eax
0x18000bfe2  jz      short loc_18000C002
0x18000bfe4  cmp     eax, 2
0x18000bfe7  jz      short loc_18000BFFE
0x18000bfe9  test    eax, eax
0x18000bfeb  jg      short loc_18000BFF1
0x18000bfed  mov     ebx, eax
0x18000bfef  jmp     short loc_18000BFAD
0x18000bff1  movzx   ebx, ax
0x18000bff4  or      ebx, 80070000h
0x18000bffa  mov     eax, ebx
0x18000bffc  jmp     short loc_18000BFAD
0x18000bffe  xor     edi, edi
0x18000c000  jmp     short loc_18000C007
0x18000c002  mov     edi, 1
0x18000c007  mov     ecx, ebx
0x18000c009  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c00e  cmp     [rbp+arg_10], 0
0x18000c013  jz      short loc_18000C01F
0x18000c015  mov     rcx, [rbp+arg_10]; hKey
0x18000c019  call    cs:__imp_RegCloseKey
0x18000c01f  test    ebx, ebx
0x18000c021  js      short loc_18000C095
0x18000c023  cmp     edi, 1
0x18000c026  jnz     short loc_18000C09C
0x18000c028  lea     r9, [rbp+hKey]
0x18000c02c  mov     [rbp+hKey], 0
0x18000c034  lea     r8d, [rdi+1]
0x18000c038  mov     rcx, r12
0x18000c03b  call    ??$RegOpenKeyAccess64BitView@$0A@@?$CRegUtilT@KUCRegType@@$0A@$0A@@@CAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; CRegUtilT<ulong,CRegType,0,0>::RegOpenKeyAccess64BitView<0>(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x18000c040  mov     rdi, [rbp+hKey]
0x18000c044  mov     ebx, eax
0x18000c046  test    eax, eax
0x18000c048  jns     short loc_18000C053
0x18000c04a  mov     ecx, eax
0x18000c04c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000c051  jmp     short loc_18000C07C
0x18000c053  lea     rdx, ValueName; "Status"
0x18000c05a  mov     rcx, rdi; hKey
0x18000c05d  call    cs:__imp_RegDeleteValueW
0x18000c063  mov     ebx, eax
0x18000c065  test    eax, eax
0x18000c067  jz      short loc_18000C07A
0x18000c069  test    eax, eax
0x18000c06b  jle     short loc_18000C076
0x18000c06d  movzx   ebx, bx
0x18000c070  or      ebx, 80070000h
0x18000c076  mov     ecx, ebx
0x18000c078  jmp     short loc_18000C04C
0x18000c07a  xor     ebx, ebx
0x18000c07c  mov     ecx, ebx
0x18000c07e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c083  test    rdi, rdi
0x18000c086  jz      short loc_18000C091
0x18000c088  mov     rcx, rdi; hKey
0x18000c08b  call    cs:__imp_RegCloseKey
0x18000c091  test    ebx, ebx
0x18000c093  jns     short loc_18000C09C
0x18000c095  mov     ecx, ebx
0x18000c097  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000c09c  mov     ecx, ebx
0x18000c09e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c0a3  test    ebx, ebx
0x18000c0a5  jns     short loc_18000C0AE
0x18000c0a7  mov     ecx, ebx
0x18000c0a9  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000c0ae  mov     ecx, ebx
0x18000c0b0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c0b5  mov     eax, ebx
0x18000c0b7  mov     rbx, [rsp+30h+arg_18]
0x18000c0bc  add     rsp, 30h
0x18000c0c0  pop     r12
0x18000c0c2  pop     rdi
0x18000c0c3  pop     rbp
0x18000c0c4  retn
```
