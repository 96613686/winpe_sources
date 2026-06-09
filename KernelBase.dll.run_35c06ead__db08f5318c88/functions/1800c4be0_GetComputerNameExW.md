# GetComputerNameExW

- ea: `0x1800c4be0`
- end: `0x1800c5124`
- name: `GetComputerNameExW`
- size: `1348`
- prototype: `BOOL __stdcall(COMPUTER_NAME_FORMAT NameType, LPWSTR lpBuffer, LPDWORD nSize)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800c4ac0`
- `0x1800c4be0`
- `0x18012905c`

## callees

- `0x1800134a0`
- `0x1800c495c`
- `0x1800c4be0`
- `0x1800c512c`
- `0x1800c51d0`
- `0x1800c5490`
- `0x180188eb9`

## import_xrefs

- `ntdll!wcslen` at `0x1800c4f96`
- `ntdll!wcslen` at `0x1800c4f96`
- `ntdll!RtlEnterCriticalSection` at `0x1800c4ecc`
- `ntdll!RtlEnterCriticalSection` at `0x1800c4ecc`
- `ntdll!RtlLeaveCriticalSection` at `0x1800c4fb0`
- `ntdll!RtlLeaveCriticalSection` at `0x1800c4fb0`
- `ntdll!RtlSetLastWin32Error` at `0x1800c4e32`
- `ntdll!RtlSetLastWin32Error` at `0x180193a46`
- `ntdll!RtlSetLastWin32Error` at `0x1800c4e32`
- `ntdll!RtlSetLastWin32Error` at `0x180193a46`
- `ntdll!RtlAllocateHeap` at `0x1800c4f69`
- `ntdll!RtlAllocateHeap` at `0x1800c4f69`

## string_xrefs

- `0x1800c4d4f`: `\Registry\Machine\System\CurrentControlSet\Control\ComputerName\ActiveComputerName`
- `0x1800c4d46`: `ComputerName`
- `0x180193a5c`: `ComputerName`
- `0x1800c4d02`: `\Registry\Machine\System\CurrentControlSet\Services\Tcpip\Parameters`
- `0x1800c4d09`: `DnscacheTcpipParameters`
- `0x1800c4cdc`: `\Registry\Machine\Software\Policies\Microsoft\System\DNSClient`
- `0x1800c4ef0`: `\Registry\Machine\System\Setup`
- `0x1800c4f27`: `\Registry\Machine\System\Setup`
- `0x1800c4fcd`: `\Registry\Machine\System\CurrentControlSet\Services\CCG`
- `0x180193a65`: `\Registry\Machine\System\CurrentControlSet\Control\ComputerName\ComputerName`

## pseudocode

```c
BOOL __stdcall GetComputerNameExW(COMPUTER_NAME_FORMAT NameType, LPWSTR lpBuffer, LPDWORD nSize)
{
  __int64 v3; // r14
  DWORD EnvironmentVariableW; // r15d
  int v7; // r15d
  BOOL v8; // edi
  int NameFromReg; // eax
  int VolatileNameInReg; // edx
  const wchar_t *v11; // r8
  int v13; // eax
  COMPUTER_NAME_FORMAT v14; // ecx
  COMPUTER_NAME_FORMAT v15; // ecx
  DWORD v16; // ecx
  DWORD v17; // r8d
  ULONG v18; // ecx
  __int64 v19; // rcx
  int v20; // eax
  wchar_t *Heap; // rax
  const wchar_t *v22; // r14
  int v23; // eax
  COMPUTER_NAME_FORMAT v24; // ecx
  int v25; // [rsp+30h] [rbp-10h] BYREF
  _DWORD v26[3]; // [rsp+34h] [rbp-Ch] BYREF
  DWORD nSizea; // [rsp+80h] [rbp+40h] BYREF
  DWORD v28; // [rsp+98h] [rbp+58h] BYREF

  v3 = NameType;
  nSizea = 0;
  v28 = 0;
  v25 = 0;
  if ( NameType >= ComputerNameMax )
  {
    v19 = 3221225485LL;
    goto LABEL_54;
  }
  if ( !nSize || !lpBuffer && *nSize )
  {
    v18 = 87;
LABEL_44:
    RtlSetLastWin32Error(v18);
    return 0;
  }
  if ( (unsigned int)NameType <= ComputerNameDnsFullyQualified )
  {
    EnvironmentVariableW = GetEnvironmentVariableW(ClusterNameVars[NameType], lpBuffer, *nSize);
    if ( EnvironmentVariableW )
    {
      if ( *nSize < EnvironmentVariableW )
      {
        v8 = 0;
        RtlSetLastWin32Error(0xEAu);
      }
      else
      {
        v8 = 1;
      }
      *nSize = EnvironmentVariableW;
      return v8;
    }
  }
  if ( !dword_18039D4A4 || (unsigned int)v3 > 2 )
  {
LABEL_7:
    if ( (v3 & 0xFFFFFFFB) == 0 && qword_1803A2E60 )
    {
      if ( *nSize >= dword_1803A2E68 + 1 )
      {
        *nSize = dword_1803A2E68;
        v8 = 1;
        memcpy_0(lpBuffer, qword_1803A2E60, 2LL * (*nSize + 1));
        return v8;
      }
      *nSize = dword_1803A2E68 + 1;
LABEL_79:
      v18 = 234;
      goto LABEL_44;
    }
    v7 = 0;
    if ( lpBuffer && *nSize )
      *lpBuffer = 0;
    v8 = 1;
    if ( (_DWORD)v3 )
    {
      switch ( (_DWORD)v3 )
      {
        case 1:
          goto LABEL_67;
        case 2:
LABEL_18:
          NameFromReg = BasepGetNameFromReg(
                          0,
                          (unsigned int)L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\System\\DNSClient",
                          (unsigned int)L"PrimaryDnsSuffix",
                          (_DWORD)lpBuffer,
                          (__int64)nSize);
          VolatileNameInReg = NameFromReg;
          if ( NameFromReg >= 0 )
            goto LABEL_26;
          if ( NameFromReg == -2147483643 )
            goto LABEL_22;
          v11 = L"Domain";
          goto LABEL_21;
        case 3:
LABEL_30:
          v14 = ComputerNamePhysicalDnsHostname;
          if ( lpBuffer )
          {
            nSizea = *nSize;
            if ( (_DWORD)v3 != 7 )
              v14 = ComputerNameDnsHostname;
            if ( GetComputerNameExW(v14, lpBuffer, &nSizea) )
            {
              ++nSizea;
              v15 = ComputerNamePhysicalDnsDomain;
              lpBuffer[nSizea - 1] = 46;
              v28 = *nSize - nSizea;
              if ( (_DWORD)v3 != 7 )
                v15 = ComputerNameDnsDomain;
              if ( GetComputerNameExW(v15, &lpBuffer[nSizea], &v28) )
              {
                v16 = v28;
                VolatileNameInReg = 0;
                if ( v28 )
                {
                  if ( v28 == 1 && lpBuffer[nSizea] == 46 )
                  {
                    v16 = 0;
                    lpBuffer[nSizea] = 0;
                    v28 = 0;
                  }
                }
                else
                {
                  lpBuffer[--nSizea] = 0;
                  v16 = v28;
                }
                v17 = v16 + nSizea;
                goto LABEL_40;
              }
              if ( NtCurrentTeb()->LastErrorValue == 234 )
              {
                VolatileNameInReg = -2147483643;
                v7 = 0;
                v17 = v28 + nSizea;
                goto LABEL_41;
              }
LABEL_69:
              v17 = 0;
              VolatileNameInReg = -1073741823;
LABEL_40:
              v7 = 1;
LABEL_41:
              *nSize = v17;
LABEL_22:
              if ( VolatileNameInReg < 0 )
              {
                if ( v7 )
                  return 0;
                goto LABEL_53;
              }
LABEL_26:
              if ( dword_18039D4A0 && (v3 & 0xFFFFFFFB) == 0 )
              {
                RtlEnterCriticalSection(&stru_1803A2E70);
                v26[0] = 4;
                if ( (int)BasepGetValueFromReg(0, L"\\Registry\\Machine\\System\\Setup", L"OOBEInProgress", &v25, v26) >= 0
                  && v25
                  || (v26[0] = 4,
                      (int)BasepGetValueFromReg(
                             0,
                             L"\\Registry\\Machine\\System\\Setup",
                             L"SystemSetupInProgress",
                             &v25,
                             v26) >= 0)
                  && v25 )
                {
                  v20 = 0;
                  dword_18039D4A0 = 0;
                }
                else
                {
                  v20 = dword_18039D4A0;
                }
                if ( v20 && !qword_1803A2E60 )
                {
                  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2LL * (*nSize + 1));
                  v22 = Heap;
                  if ( Heap )
                  {
                    memcpy_0(Heap, lpBuffer, 2LL * *nSize);
                    v22[*nSize] = 0;
                    dword_1803A2E68 = wcslen(v22);
                    qword_1803A2E60 = (PVOID)v22;
                  }
                  else
                  {
                    dword_18039D4A0 = 0;
                  }
                }
                RtlLeaveCriticalSection(&stru_1803A2E70);
              }
              return v8;
            }
            if ( NtCurrentTeb()->LastErrorValue != 234 )
              goto LABEL_69;
            v28 = 0;
          }
          else
          {
            v28 = 0;
            nSizea = 0;
            if ( (_DWORD)v3 != 7 )
              v14 = ComputerNameDnsHostname;
            GetComputerNameExW(v14, 0, &nSizea);
            if ( NtCurrentTeb()->LastErrorValue != 234 )
              return 0;
          }
          v24 = ComputerNamePhysicalDnsDomain;
          if ( (_DWORD)v3 != 7 )
            v24 = ComputerNameDnsDomain;
          GetComputerNameExW(v24, 0, &v28);
          if ( NtCurrentTeb()->LastErrorValue != 234 )
            return 0;
          VolatileNameInReg = -2147483643;
          *nSize = v28 + nSizea;
LABEL_53:
          v19 = (unsigned int)VolatileNameInReg;
LABEL_54:
          BaseSetLastNTError(v19);
          return 0;
      }
      if ( (_DWORD)v3 != 4 )
      {
        if ( (_DWORD)v3 != 5 )
        {
          if ( (_DWORD)v3 == 6 )
            goto LABEL_18;
          if ( (_DWORD)v3 != 7 )
          {
            VolatileNameInReg = -1073741811;
            goto LABEL_53;
          }
          goto LABEL_30;
        }
LABEL_67:
        v11 = L"Hostname";
LABEL_21:
        VolatileNameInReg = BasepGetNameFromReg(
                              (unsigned int)L"DnscacheTcpipParameters",
                              (unsigned int)L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Tcpip\\Parameters",
                              (_DWORD)v11,
                              (_DWORD)lpBuffer,
                              (__int64)nSize);
        goto LABEL_22;
      }
    }
    v13 = BasepGetNameFromReg(
            0,
            (unsigned int)L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\ComputerName\\ActiveComputerName",
            (unsigned int)L"ComputerName",
            (_DWORD)lpBuffer,
            (__int64)nSize);
    VolatileNameInReg = v13;
    if ( v13 >= 0 )
      goto LABEL_26;
    if ( v13 != -2147483643 )
    {
      VolatileNameInReg = BasepGetNameFromReg(
                            0,
                            (unsigned int)L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\ComputerName\\ComputerName",
                            (unsigned int)L"ComputerName",
                            (_DWORD)lpBuffer,
                            (__int64)nSize);
      if ( VolatileNameInReg >= 0 )
      {
        VolatileNameInReg = BaseCreateVolatileNameInReg(lpBuffer);
        if ( (int)(VolatileNameInReg + 0x80000000) < 0 || VolatileNameInReg == -1073741790 )
          goto LABEL_26;
        dword_18039D4A0 = 0;
      }
    }
    goto LABEL_53;
  }
  v23 = BasepGetNameFromReg(
          0,
          (unsigned int)L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\CCG",
          (unsigned int)EDJRegistryValues[v3],
          (_DWORD)lpBuffer,
          (__int64)nSize);
  if ( v23 < 0 )
  {
    if ( v23 == -2147483643 )
      goto LABEL_79;
    dword_18039D4A4 = 0;
    goto LABEL_7;
  }
  return 1;
}

```

## disassembly

```asm
0x1800c4be0  mov     [rsp-38h+arg_8], rbx
0x1800c4be5  push    rbp
0x1800c4be6  push    rsi
0x1800c4be7  push    rdi
0x1800c4be8  push    r12
0x1800c4bea  push    r13
0x1800c4bec  push    r14
0x1800c4bee  push    r15
0x1800c4bf0  mov     rbp, rsp
0x1800c4bf3  sub     rsp, 40h
0x1800c4bf7  xor     r12d, r12d
0x1800c4bfa  movsxd  r14, ecx
0x1800c4bfd  mov     [rbp+nSize], r12d
0x1800c4c01  mov     rbx, r8
0x1800c4c04  mov     [rbp+arg_18], r12d
0x1800c4c08  mov     rsi, rdx
0x1800c4c0b  mov     [rbp+var_10], r12d
0x1800c4c0f  cmp     r14d, 8
0x1800c4c13  jge     loc_1800C5052
0x1800c4c19  test    rbx, rbx
0x1800c4c1c  jz      loc_1800C4E2D
0x1800c4c22  test    rdx, rdx
0x1800c4c25  jz      loc_1800C4E24
0x1800c4c2b  lea     rax, __ImageBase
0x1800c4c32  mov     rdi, r14
0x1800c4c35  cmp     r14d, 3
0x1800c4c39  ja      short loc_1800C4C5D
0x1800c4c3b  mov     r8d, [r8]; nSize
0x1800c4c3e  mov     rcx, ds:rva ClusterNameVars[rax+r14*8]; lpName
0x1800c4c46  call    GetEnvironmentVariableW
0x1800c4c4b  mov     r15d, eax
0x1800c4c4e  test    eax, eax
0x1800c4c50  jnz     loc_1800C505C
0x1800c4c56  lea     rax, __ImageBase
0x1800c4c5d  cmp     cs:dword_18039D4A4, r12d
0x1800c4c64  mov     r13d, 80000005h
0x1800c4c6a  jnz     loc_1800C4FBB
0x1800c4c70  test    r14d, 0FFFFFFFBh
0x1800c4c77  jz      loc_1800C4E3D
0x1800c4c7d  mov     r15d, r12d
0x1800c4c80  test    rsi, rsi
0x1800c4c83  jz      short loc_1800C4C8E
0x1800c4c85  cmp     [rbx], r12d
0x1800c4c88  jbe     short loc_1800C4C8E
0x1800c4c8a  mov     [rsi], r12w
0x1800c4c8e  mov     ecx, r14d
0x1800c4c91  mov     edi, 1
0x1800c4c96  test    r14d, r14d
0x1800c4c99  jz      loc_1800C4D3E
0x1800c4c9f  sub     ecx, edi
0x1800c4ca1  jz      loc_1800C4FF5
0x1800c4ca7  sub     ecx, edi
0x1800c4ca9  jz      short loc_1800C4CCB
0x1800c4cab  sub     ecx, edi
0x1800c4cad  jz      loc_1800C4D87
0x1800c4cb3  sub     ecx, edi
0x1800c4cb5  jz      loc_1800C4D3E
0x1800c4cbb  sub     ecx, edi
0x1800c4cbd  jz      loc_1800C4FF5
0x1800c4cc3  sub     ecx, edi
0x1800c4cc5  jnz     loc_1800C4D7F
0x1800c4ccb  mov     r9, rsi
0x1800c4cce  mov     [rsp+40h+var_20], rbx
0x1800c4cd3  lea     r8, aPrimarydnssuff; "PrimaryDnsSuffix"
0x1800c4cda  xor     ecx, ecx
0x1800c4cdc  lea     rdx, aRegistryMachin_6; "\\Registry\\Machine\\Software\\Policies"...
0x1800c4ce3  call    BasepGetNameFromReg
0x1800c4ce8  mov     edx, eax
0x1800c4cea  test    eax, eax
0x1800c4cec  jns     short loc_1800C4D65
0x1800c4cee  cmp     eax, r13d
0x1800c4cf1  jz      short loc_1800C4D17
0x1800c4cf3  lea     r8, aDomain; "Domain"
0x1800c4cfa  mov     r9, rsi
0x1800c4cfd  mov     [rsp+40h+var_20], rbx
0x1800c4d02  lea     rdx, aRegistryMachin_38; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800c4d09  lea     rcx, aDnscachetcpipp; "DnscacheTcpipParameters"
0x1800c4d10  call    BasepGetNameFromReg
0x1800c4d15  mov     edx, eax
0x1800c4d17  test    edx, edx
0x1800c4d19  jns     short loc_1800C4D65
0x1800c4d1b  test    r15d, r15d
0x1800c4d1e  jz      loc_1800C4EB9
0x1800c4d24  xor     eax, eax
0x1800c4d26  mov     rbx, [rsp+40h+arg_8]
0x1800c4d2e  add     rsp, 40h
0x1800c4d32  pop     r15
0x1800c4d34  pop     r14
0x1800c4d36  pop     r13
0x1800c4d38  pop     r12
0x1800c4d3a  pop     rdi
0x1800c4d3b  pop     rsi
0x1800c4d3c  pop     rbp
0x1800c4d3d  retn
0x1800c4d3e  mov     r9, rsi
0x1800c4d41  mov     [rsp+40h+var_20], rbx
0x1800c4d46  lea     r8, aComputername_1; "ComputerName"
0x1800c4d4d  xor     ecx, ecx
0x1800c4d4f  lea     rdx, aRegistryMachin_33; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800c4d56  call    BasepGetNameFromReg
0x1800c4d5b  mov     edx, eax
0x1800c4d5d  test    eax, eax
0x1800c4d5f  js      loc_1800C4EB0
0x1800c4d65  cmp     cs:dword_18039D4A0, r12d
0x1800c4d6c  jz      short loc_1800C4D7B
0x1800c4d6e  test    r14d, 0FFFFFFFBh
0x1800c4d75  jz      loc_1800C4EC5
0x1800c4d7b  mov     eax, edi
0x1800c4d7d  jmp     short loc_1800C4D26
0x1800c4d7f  cmp     ecx, edi
0x1800c4d81  jnz     loc_1800C508C
0x1800c4d87  lea     r8, [rbp+nSize]; nSize
0x1800c4d8b  mov     ecx, 5
0x1800c4d90  test    rsi, rsi
0x1800c4d93  jz      loc_1800C4E82
0x1800c4d99  mov     eax, [rbx]
0x1800c4d9b  cmp     r14d, 7
0x1800c4d9f  mov     rdx, rsi; lpBuffer
0x1800c4da2  mov     [rbp+nSize], eax
0x1800c4da5  cmovnz  ecx, edi; NameType
0x1800c4da8  call    GetComputerNameExW
0x1800c4dad  test    eax, eax
0x1800c4daf  jz      loc_1800C5001
0x1800c4db5  mov     eax, [rbp+nSize]
0x1800c4db8  lea     r8, [rbp+arg_18]; nSize
0x1800c4dbc  add     eax, edi
0x1800c4dbe  mov     r15d, 2Eh ; '.'
0x1800c4dc4  mov     [rbp+nSize], eax
0x1800c4dc7  dec     eax
0x1800c4dc9  lea     ecx, [r15-28h]
0x1800c4dcd  mov     [rsi+rax*2], r15w
0x1800c4dd2  mov     eax, [rbx]
0x1800c4dd4  sub     eax, [rbp+nSize]
0x1800c4dd7  mov     [rbp+arg_18], eax
0x1800c4dda  cmp     r14d, 7
0x1800c4dde  mov     eax, [rbp+nSize]
0x1800c4de1  lea     rdx, [rsi+rax*2]; lpBuffer
0x1800c4de5  lea     eax, [rcx-4]
0x1800c4de8  cmovnz  ecx, eax; NameType
0x1800c4deb  call    GetComputerNameExW
0x1800c4df0  test    eax, eax
0x1800c4df2  jz      loc_1800C5021
0x1800c4df8  mov     ecx, [rbp+arg_18]
0x1800c4dfb  mov     edx, r12d
0x1800c4dfe  test    ecx, ecx
0x1800c4e00  jz      loc_1800C50D7
0x1800c4e06  cmp     ecx, edi
0x1800c4e08  jz      loc_1800C50EC
0x1800c4e0e  mov     r8d, [rbp+nSize]
0x1800c4e12  lea     r8d, [rcx+r8]
0x1800c4e16  mov     r15d, edi
0x1800c4e19  mov     rax, rbx
0x1800c4e1c  mov     [rbx], r8d
0x1800c4e1f  jmp     loc_1800C4D17
0x1800c4e24  cmp     [r8], r12d
0x1800c4e27  jbe     loc_1800C4C2B
0x1800c4e2d  mov     ecx, 57h ; 'W'; LastError
0x1800c4e32  call    cs:__imp_RtlSetLastWin32Error
0x1800c4e38  jmp     loc_1800C4D24
0x1800c4e3d  mov     rax, cs:qword_1803A2E60
0x1800c4e44  test    rax, rax
0x1800c4e47  jz      loc_1800C4C7D
0x1800c4e4d  mov     ecx, cs:dword_1803A2E68
0x1800c4e53  lea     eax, [rcx+1]
0x1800c4e56  cmp     [rbx], eax
0x1800c4e58  jb      loc_1800C5080
0x1800c4e5e  mov     [rbx], ecx
0x1800c4e60  mov     edi, 1
0x1800c4e65  mov     rdx, cs:qword_1803A2E60; Src
0x1800c4e6c  mov     rcx, rsi; void *
0x1800c4e6f  mov     r8d, [rbx]
0x1800c4e72  add     r8d, edi
0x1800c4e75  add     r8, r8; Size
0x1800c4e78  call    memcpy_0
0x1800c4e7d  jmp     loc_1800C4D7B
0x1800c4e82  cmp     r14d, 7
0x1800c4e86  mov     [rbp+arg_18], r12d
0x1800c4e8a  mov     [rbp+nSize], r12d
0x1800c4e8e  cmovnz  ecx, edi; NameType
0x1800c4e91  xor     edx, edx; lpBuffer
0x1800c4e93  call    GetComputerNameExW
0x1800c4e98  mov     eax, gs:68h
0x1800c4ea0  cmp     eax, 0EAh
0x1800c4ea5  jnz     loc_1800C4D24
0x1800c4eab  jmp     loc_1800C509A
0x1800c4eb0  cmp     eax, r13d
0x1800c4eb3  jnz     loc_180193A54
0x1800c4eb9  mov     ecx, edx
0x1800c4ebb  call    BaseSetLastNTError
0x1800c4ec0  jmp     loc_1800C4D24
0x1800c4ec5  lea     rcx, stru_1803A2E70; CriticalSection
0x1800c4ecc  call    cs:__imp_RtlEnterCriticalSection
0x1800c4ed2  lea     rax, [rbp+var_C]
0x1800c4ed6  mov     r14d, 4
0x1800c4edc  lea     r9, [rbp+var_10]
0x1800c4ee0  mov     [rsp+40h+var_20], rax
0x1800c4ee5  lea     r8, aOobeinprogress; "OOBEInProgress"
0x1800c4eec  mov     [rbp+var_C], r14d
0x1800c4ef0  lea     rdx, aRegistryMachin_8; "\\Registry\\Machine\\System\\Setup"
0x1800c4ef7  xor     ecx, ecx
0x1800c4ef9  call    BasepGetValueFromReg
0x1800c4efe  test    eax, eax
0x1800c4f00  js      short loc_1800C4F0D
0x1800c4f02  mov     eax, [rbp+var_10]
0x1800c4f05  test    eax, eax
0x1800c4f07  jnz     loc_1800C5116
0x1800c4f0d  lea     rax, [rbp+var_C]
0x1800c4f11  mov     [rbp+var_C], r14d
0x1800c4f15  lea     r9, [rbp+var_10]
0x1800c4f19  mov     [rsp+40h+var_20], rax
0x1800c4f1e  lea     r8, aSystemsetupinp; "SystemSetupInProgress"
0x1800c4f25  xor     ecx, ecx
0x1800c4f27  lea     rdx, aRegistryMachin_8; "\\Registry\\Machine\\System\\Setup"
0x1800c4f2e  call    BasepGetValueFromReg
0x1800c4f33  test    eax, eax
0x1800c4f35  jns     loc_1800C510B
0x1800c4f3b  mov     eax, cs:dword_18039D4A0
0x1800c4f41  test    eax, eax
0x1800c4f43  jz      short loc_1800C4FA9
0x1800c4f45  mov     rax, cs:qword_1803A2E60
0x1800c4f4c  test    rax, rax
0x1800c4f4f  jnz     short loc_1800C4FA9
0x1800c4f51  mov     r8d, [rbx]
0x1800c4f54  xor     edx, edx; Flags
0x1800c4f56  mov     rcx, gs:60h
0x1800c4f5f  add     r8d, edi
0x1800c4f62  add     r8, r8; Size
0x1800c4f65  mov     rcx, [rcx+30h]; HeapHandle
0x1800c4f69  call    cs:__imp_RtlAllocateHeap
0x1800c4f6f  mov     r14, rax
0x1800c4f72  test    rax, rax
0x1800c4f75  jz      loc_1800C5046
0x1800c4f7b  mov     r8d, [rbx]
0x1800c4f7e  mov     rdx, rsi; Src
0x1800c4f81  add     r8, r8; Size
0x1800c4f84  mov     rcx, rax; void *
0x1800c4f87  call    memcpy_0
0x1800c4f8c  mov     edx, [rbx]
0x1800c4f8e  mov     rcx, r14; String
0x1800c4f91  mov     [r14+rdx*2], r12w
0x1800c4f96  call    cs:__imp_wcslen
0x1800c4f9c  mov     cs:dword_1803A2E68, eax
0x1800c4fa2  mov     cs:qword_1803A2E60, r14
0x1800c4fa9  lea     rcx, stru_1803A2E70; CriticalSection
0x1800c4fb0  call    cs:__imp_RtlLeaveCriticalSection
0x1800c4fb6  jmp     loc_1800C4D7B
0x1800c4fbb  cmp     r14d, 2
0x1800c4fbf  ja      loc_1800C4C70
0x1800c4fc5  mov     r8, ds:rva EDJRegistryValues[rax+rdi*8]
0x1800c4fcd  lea     rdx, aRegistryMachin_13; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800c4fd4  mov     r9, rsi
0x1800c4fd7  mov     [rsp+40h+var_20], rbx
0x1800c4fdc  xor     ecx, ecx
0x1800c4fde  call    BasepGetNameFromReg
0x1800c4fe3  test    eax, eax
0x1800c4fe5  js      loc_1800C506F
0x1800c4feb  mov     eax, 1
0x1800c4ff0  jmp     loc_1800C4D26
0x1800c4ff5  lea     r8, aHostname; "Hostname"
0x1800c4ffc  jmp     loc_1800C4CFA
0x1800c5001  mov     eax, gs:68h
0x1800c5009  cmp     eax, 0EAh
0x1800c500e  jz      loc_1800C5096
0x1800c5014  mov     r8d, r12d
0x1800c5017  mov     edx, 0C0000001h
0x1800c501c  jmp     loc_1800C4E16
0x1800c5021  mov     eax, gs:68h
0x1800c5029  cmp     eax, 0EAh
0x1800c502e  jnz     short loc_1800C5014
0x1800c5030  mov     ecx, [rbp+nSize]
0x1800c5033  mov     edx, r13d
0x1800c5036  mov     r8d, [rbp+arg_18]
0x1800c503a  mov     r15d, r12d
0x1800c503d  lea     r8d, [r8+rcx]
0x1800c5041  jmp     loc_1800C4E19
0x1800c5046  mov     cs:dword_18039D4A0, r12d
0x1800c504d  jmp     loc_1800C4FA9
0x1800c5052  mov     ecx, 0C000000Dh
0x1800c5057  jmp     loc_1800C4EBB
0x1800c505c  cmp     [rbx], r15d
0x1800c505f  jb      loc_180193A3E
0x1800c5065  mov     edi, 1
0x1800c506a  jmp     loc_180193A4C
0x1800c506f  cmp     eax, r13d
0x1800c5072  jz      short loc_1800C5082
0x1800c5074  mov     cs:dword_18039D4A4, r12d
0x1800c507b  jmp     loc_1800C4C70
0x1800c5080  mov     [rbx], eax
0x1800c5082  mov     ecx, 0EAh
0x1800c5087  jmp     loc_1800C4E32
0x1800c508c  mov     edx, 0C000000Dh
0x1800c5091  jmp     loc_1800C4EB9
0x1800c5096  mov     [rbp+arg_18], r12d
0x1800c509a  mov     ecx, 6
0x1800c509f  lea     r8, [rbp+arg_18]; nSize
0x1800c50a3  cmp     r14d, 7
0x1800c50a7  lea     eax, [rcx-4]
0x1800c50aa  cmovnz  ecx, eax; NameType
0x1800c50ad  xor     edx, edx; lpBuffer
0x1800c50af  call    GetComputerNameExW
  ... truncated ...
```
