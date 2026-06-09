# SaferpSetSingleIdentificationHash

- ea: `0x18004666c`
- end: `0x180046b49`
- name: `SaferpSetSingleIdentificationHash`
- size: `1245`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180045f64`
- `0x180046348`

## callees

- `0x18000db68`
- `0x18004666c`
- `0x180047164`
- `0x180065090`

## import_xrefs

- `ntdll!NtClose` at `0x180046b07`
- `ntdll!NtClose` at `0x180046b17`
- `ntdll!NtClose` at `0x180046b07`
- `ntdll!NtClose` at `0x180046b17`
- `ntdll!NtSetValueKey` at `0x1800468ca`
- `ntdll!NtSetValueKey` at `0x180046905`
- `ntdll!NtSetValueKey` at `0x18004693a`
- `ntdll!NtSetValueKey` at `0x18004697a`
- `ntdll!NtSetValueKey` at `0x1800469bc`
- `ntdll!NtSetValueKey` at `0x1800469fe`
- `ntdll!NtSetValueKey` at `0x180046a3d`
- `ntdll!NtSetValueKey` at `0x180046a7c`
- `ntdll!NtSetValueKey` at `0x180046ac6`
- `ntdll!NtSetValueKey` at `0x1800468ca`
- `ntdll!NtSetValueKey` at `0x180046905`
- `ntdll!NtSetValueKey` at `0x18004693a`
- `ntdll!NtSetValueKey` at `0x18004697a`
- `ntdll!NtSetValueKey` at `0x1800469bc`
- `ntdll!NtSetValueKey` at `0x1800469fe`
- `ntdll!NtSetValueKey` at `0x180046a3d`
- `ntdll!NtSetValueKey` at `0x180046a7c`
- `ntdll!NtSetValueKey` at `0x180046ac6`
- `ntdll!RtlAppendUnicodeToString` at `0x18004683f`
- `ntdll!RtlAppendUnicodeToString` at `0x18004683f`
- `ntdll!NtDeleteKey` at `0x180046ae8`
- `ntdll!NtDeleteKey` at `0x180046ae8`
- `ntdll!RtlInitUnicodeString` at `0x180046715`
- `ntdll!RtlInitUnicodeString` at `0x180046727`
- `ntdll!RtlInitUnicodeString` at `0x180046715`
- `ntdll!RtlInitUnicodeString` at `0x180046727`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004689d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004689d`

## pseudocode

```c
__int64 __fastcall SaferpSetSingleIdentificationHash(char a1, __int64 a2, _QWORD *a3)
{
  bool v3; // zf
  int appended; // ebx
  _QWORD *v8; // rsi
  ULONG v9; // ecx
  ACCESS_MASK v10; // r15d
  __int64 v11; // rax
  int v12; // eax
  HANDLE v13; // rcx
  HANDLE v14; // rcx
  HANDLE v15; // rcx
  HANDLE v16; // rcx
  HANDLE v17; // rcx
  NTSTATUS v18; // eax
  HANDLE KeyHandle; // [rsp+30h] [rbp-D0h] BYREF
  int v21; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING Data; // [rsp+70h] [rbp-90h] BYREF
  WCHAR v27[264]; // [rsp+80h] [rbp-80h] BYREF

  v3 = *(_DWORD *)(a2 + 16) == 2;
  KeyHandle = 0;
  Destination = 0;
  Data = 0;
  Handle = 0;
  DestinationString = 0;
  v21 = 0;
  SystemTimeAsFileTime = 0;
  if ( !v3 || *((_DWORD *)a3 + 1) != 1144 && *((_DWORD *)a3 + 1) != 1216 )
    return (unsigned int)-1073741811;
  v8 = 0;
  if ( *((_DWORD *)a3 + 1) != 1144 )
    v8 = a3;
  RtlInitUnicodeString(&DestinationString, (PCWSTR)a3 + 16);
  RtlInitUnicodeString(&Data, (PCWSTR)a3 + 272);
  if ( DestinationString.Length >= 0x200u
    || Data.Length >= 0x200u
    || *((_DWORD *)a3 + 281) != 32771
    || *((_DWORD *)a3 + 264) != 16
    || v8 && (*((_DWORD *)v8 + 303) != 32780 || *((_DWORD *)v8 + 286) != 32) )
  {
    appended = -1073741811;
    goto LABEL_43;
  }
  v9 = *(_DWORD *)(a2 + 20);
  *(_QWORD *)&Destination.Length = 34078720;
  Destination.Buffer = v27;
  appended = CodeAuthzpFormatIdentityKeyPath(v9, L"Hashes", (GUID *)a2, &Destination);
  if ( appended < 0 )
    goto LABEL_43;
  v10 = 131103;
  appended = CodeAuthzpOpenPolicyRootKey(*(_DWORD *)(a2 + 24), g_hKeyCustomRoot, v27, 0x2001Fu, a1, &KeyHandle);
  if ( appended < 0 )
    goto LABEL_43;
  if ( !v8 )
  {
    if ( !a1 && *(_DWORD *)(a2 + 168) )
    {
      v11 = *(_QWORD *)(a2 + 40) - *(_QWORD *)((char *)a3 + 1060);
      if ( !v11 )
        v11 = *(_QWORD *)(a2 + 48) - *(_QWORD *)((char *)a3 + 1068);
      if ( !v11 )
        goto LABEL_28;
    }
    v10 = 196633;
  }
  appended = RtlAppendUnicodeToString(&Destination, L"\\SHA256");
  if ( appended < 0 )
    goto LABEL_43;
  v12 = CodeAuthzpOpenPolicyRootKey(*(_DWORD *)(a2 + 24), g_hKeyCustomRoot, v27, v10, v8 != 0, &Handle);
  appended = v12;
  if ( v12 < 0 )
  {
    if ( v8 || v12 != -1073741772 )
      goto LABEL_43;
    Handle = 0;
  }
LABEL_28:
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  appended = NtSetValueKey(KeyHandle, (PUNICODE_STRING)&stru_180069460, 0, 0xBu, &SystemTimeAsFileTime, 8u);
  if ( appended < 0 )
    goto LABEL_43;
  appended = NtSetValueKey(
               KeyHandle,
               (PUNICODE_STRING)&stru_180069450,
               0,
               1u,
               DestinationString.Buffer,
               DestinationString.MaximumLength);
  if ( appended < 0 )
    goto LABEL_43;
  appended = NtSetValueKey(KeyHandle, (PUNICODE_STRING)&stru_180069440, 0, 1u, Data.Buffer, Data.MaximumLength);
  if ( appended < 0 )
    goto LABEL_43;
  v21 = *((_DWORD *)a3 + 284);
  appended = NtSetValueKey(KeyHandle, (PUNICODE_STRING)&stru_180069430, 0, 4u, &v21, 4u);
  if ( appended < 0 )
    goto LABEL_43;
  v13 = KeyHandle;
  *(_DWORD *)(a2 + 176) = v21;
  appended = NtSetValueKey(v13, (PUNICODE_STRING)&stru_180069420, 0, 0xBu, a3 + 141, 8u);
  if ( appended < 0 )
    goto LABEL_43;
  v14 = KeyHandle;
  *(_QWORD *)(a2 + 32) = a3[141];
  appended = NtSetValueKey(v14, (PUNICODE_STRING)&stru_180069410, 0, 3u, (char *)a3 + 1060, *((_DWORD *)a3 + 264));
  if ( appended < 0 )
    goto LABEL_43;
  v15 = KeyHandle;
  *(_DWORD *)(a2 + 168) = 1;
  *(_OWORD *)(a2 + 40) = *(_OWORD *)((char *)a3 + 1060);
  appended = NtSetValueKey(v15, (PUNICODE_STRING)&stru_180069400, 0, 4u, (char *)a3 + 1124, 4u);
  if ( appended < 0 )
    goto LABEL_43;
  v16 = Handle;
  if ( v8 )
  {
    appended = NtSetValueKey(Handle, (PUNICODE_STRING)&stru_180069410, 0, 3u, (char *)v8 + 1148, *((_DWORD *)v8 + 286));
    if ( appended < 0 )
      goto LABEL_43;
    v17 = Handle;
    *(_DWORD *)(a2 + 172) = 1;
    *(_OWORD *)(a2 + 104) = *(_OWORD *)((char *)v8 + 1148);
    *(_OWORD *)(a2 + 120) = *(_OWORD *)((char *)v8 + 1164);
    v18 = NtSetValueKey(v17, (PUNICODE_STRING)&stru_180069400, 0, 4u, (char *)v8 + 1212, 4u);
  }
  else
  {
    if ( !Handle )
    {
LABEL_41:
      appended = 0;
      goto LABEL_43;
    }
    *(_DWORD *)(a2 + 172) = 0;
    *(_OWORD *)(a2 + 104) = 0;
    *(_OWORD *)(a2 + 120) = 0;
    v18 = NtDeleteKey(v16);
  }
  appended = v18;
  if ( v18 >= 0 )
    goto LABEL_41;
LABEL_43:
  if ( Handle )
    NtClose(Handle);
  if ( KeyHandle )
    NtClose(KeyHandle);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18004666c  mov     [rsp-8+arg_0], rbx
0x180046671  push    rbp
0x180046672  push    rsi
0x180046673  push    rdi
0x180046674  push    r12
0x180046676  push    r13
0x180046678  push    r14
0x18004667a  push    r15
0x18004667c  lea     rbp, [rsp-1A0h]
0x180046684  sub     rsp, 2A0h
0x18004668b  mov     rax, cs:__security_cookie
0x180046692  xor     rax, rsp
0x180046695  mov     [rbp+1D0h+var_40], rax
0x18004669c  cmp     dword ptr [rdx+10h], 2
0x1800466a0  xorps   xmm0, xmm0
0x1800466a3  xorps   xmm1, xmm1
0x1800466a6  mov     [rsp+2D0h+KeyHandle], 0
0x1800466af  movups  xmmword ptr [rsp+2D0h+Destination.Length], xmm0
0x1800466b4  mov     r14, r8
0x1800466b7  mov     rdi, rdx
0x1800466ba  movups  xmmword ptr [rsp+2D0h+var_260.Length], xmm1
0x1800466bf  mov     r12b, cl
0x1800466c2  mov     [rsp+2D0h+Handle], 0
0x1800466cb  movups  xmmword ptr [rsp+2D0h+DestinationString.Length], xmm0
0x1800466d0  mov     [rsp+2D0h+var_298], 0
0x1800466d8  mov     qword ptr [rsp+2D0h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800466e1  jz      short loc_1800466ED
0x1800466e3  mov     ebx, 0C000000Dh
0x1800466e8  jmp     loc_180046B1D
0x1800466ed  mov     eax, 478h
0x1800466f2  cmp     [r8+4], eax
0x1800466f6  jz      short loc_180046702
0x1800466f8  cmp     dword ptr [r8+4], 4C0h
0x180046700  jnz     short loc_1800466E3
0x180046702  xor     esi, esi
0x180046704  lea     rdx, [r8+20h]; SourceString
0x180046708  cmp     [r8+4], eax
0x18004670c  lea     rcx, [rsp+2D0h+DestinationString]; DestinationString
0x180046711  cmovnz  rsi, r14
0x180046715  call    cs:__imp_RtlInitUnicodeString
0x18004671b  lea     rdx, [r14+220h]; SourceString
0x180046722  lea     rcx, [rsp+2D0h+var_260]; DestinationString
0x180046727  call    cs:__imp_RtlInitUnicodeString
0x18004672d  mov     eax, 200h
0x180046732  cmp     [rsp+2D0h+DestinationString.Length], ax
0x180046737  jnb     loc_180046AF8
0x18004673d  cmp     [rsp+2D0h+var_260.Length], ax
0x180046742  jnb     loc_180046AF8
0x180046748  lea     r13, [r14+464h]
0x18004674f  cmp     dword ptr [r13+0], 8003h
0x180046757  jnz     loc_180046AF8
0x18004675d  cmp     dword ptr [r14+420h], 10h
0x180046765  jnz     loc_180046AF8
0x18004676b  test    rsi, rsi
0x18004676e  jz      short loc_18004678D
0x180046770  cmp     dword ptr [rsi+4BCh], 800Ch
0x18004677a  jnz     loc_180046AF8
0x180046780  cmp     dword ptr [rsi+478h], 20h ; ' '
0x180046787  jnz     loc_180046AF8
0x18004678d  mov     ecx, [rdi+14h]; Value
0x180046790  lea     r9, [rsp+2D0h+Destination]; Destination
0x180046795  xorps   xmm0, xmm0
0x180046798  lea     rdx, aHashes; "Hashes"
0x18004679f  movups  xmmword ptr [rsp+2D0h+Destination.Length], xmm0
0x1800467a4  mov     eax, 208h
0x1800467a9  mov     r8, rdi; Guid
0x1800467ac  mov     [rsp+2D0h+Destination.MaximumLength], ax
0x1800467b1  lea     rax, [rbp+1D0h+var_250]
0x1800467b5  mov     [rsp+2D0h+Destination.Buffer], rax
0x1800467ba  call    CodeAuthzpFormatIdentityKeyPath
0x1800467bf  mov     ebx, eax
0x1800467c1  test    eax, eax
0x1800467c3  js      loc_180046AFD
0x1800467c9  mov     rdx, cs:g_hKeyCustomRoot
0x1800467d0  lea     rax, [rsp+2D0h+KeyHandle]
0x1800467d5  mov     ecx, [rdi+18h]
0x1800467d8  lea     r8, [rbp+1D0h+var_250]
0x1800467dc  mov     qword ptr [rsp+2D0h+DataSize], rax
0x1800467e1  mov     r15d, 2001Fh
0x1800467e7  mov     r9d, r15d
0x1800467ea  mov     byte ptr [rsp+2D0h+Data], r12b
0x1800467ef  call    CodeAuthzpOpenPolicyRootKey
0x1800467f4  mov     ebx, eax
0x1800467f6  test    eax, eax
0x1800467f8  js      loc_180046AFD
0x1800467fe  test    rsi, rsi
0x180046801  jnz     short loc_180046833
0x180046803  test    r12b, r12b
0x180046806  jnz     short loc_18004682D
0x180046808  cmp     [rdi+0A8h], esi
0x18004680e  jz      short loc_18004682D
0x180046810  mov     rax, [rdi+28h]
0x180046814  sub     rax, [r14+424h]
0x18004681b  jnz     short loc_180046828
0x18004681d  mov     rax, [rdi+30h]
0x180046821  sub     rax, [r14+42Ch]
0x180046828  test    rax, rax
0x18004682b  jz      short loc_180046898
0x18004682d  mov     r15d, 30019h
0x180046833  lea     rdx, aSha256; "\\SHA256"
0x18004683a  lea     rcx, [rsp+2D0h+Destination]; Destination
0x18004683f  call    cs:__imp_RtlAppendUnicodeToString
0x180046845  mov     ebx, eax
0x180046847  test    eax, eax
0x180046849  js      loc_180046AFD
0x18004684f  mov     rdx, cs:g_hKeyCustomRoot
0x180046856  lea     rcx, [rsp+2D0h+Handle]
0x18004685b  mov     qword ptr [rsp+2D0h+DataSize], rcx
0x180046860  lea     r8, [rbp+1D0h+var_250]
0x180046864  mov     ecx, [rdi+18h]
0x180046867  test    rsi, rsi
0x18004686a  mov     r9d, r15d
0x18004686d  setnz   al
0x180046870  mov     byte ptr [rsp+2D0h+Data], al
0x180046874  call    CodeAuthzpOpenPolicyRootKey
0x180046879  mov     ebx, eax
0x18004687b  test    eax, eax
0x18004687d  jns     short loc_180046898
0x18004687f  test    rsi, rsi
0x180046882  jnz     loc_180046AFD
0x180046888  cmp     eax, 0C0000034h
0x18004688d  jnz     loc_180046AFD
0x180046893  mov     [rsp+2D0h+Handle], rsi
0x180046898  lea     rcx, [rsp+2D0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18004689d  call    cs:__imp_GetSystemTimeAsFileTime
0x1800468a3  mov     rcx, [rsp+2D0h+KeyHandle]; KeyHandle
0x1800468a8  lea     rax, [rsp+2D0h+SystemTimeAsFileTime]
0x1800468ad  mov     [rsp+2D0h+DataSize], 8; DataSize
0x1800468b5  lea     rdx, stru_180069460; ValueName
0x1800468bc  mov     r9d, 0Bh; Type
0x1800468c2  mov     [rsp+2D0h+Data], rax; Data
0x1800468c7  xor     r8d, r8d; TitleIndex
0x1800468ca  call    cs:__imp_NtSetValueKey
0x1800468d0  mov     ebx, eax
0x1800468d2  test    eax, eax
0x1800468d4  js      loc_180046AFD
0x1800468da  movzx   eax, [rsp+2D0h+DestinationString.MaximumLength]
0x1800468df  lea     rdx, stru_180069450; ValueName
0x1800468e6  mov     rcx, [rsp+2D0h+KeyHandle]; KeyHandle
0x1800468eb  mov     r15d, 1
0x1800468f1  mov     [rsp+2D0h+DataSize], eax; DataSize
0x1800468f5  mov     r9d, r15d; Type
0x1800468f8  mov     rax, [rsp+2D0h+DestinationString.Buffer]
0x1800468fd  xor     r8d, r8d; TitleIndex
0x180046900  mov     [rsp+2D0h+Data], rax; Data
0x180046905  call    cs:__imp_NtSetValueKey
0x18004690b  mov     ebx, eax
0x18004690d  test    eax, eax
0x18004690f  js      loc_180046AFD
0x180046915  movzx   eax, [rsp+2D0h+var_260.MaximumLength]
0x18004691a  lea     rdx, stru_180069440; ValueName
0x180046921  mov     rcx, [rsp+2D0h+KeyHandle]; KeyHandle
0x180046926  mov     r9d, r15d; Type
0x180046929  mov     [rsp+2D0h+DataSize], eax; DataSize
0x18004692d  xor     r8d, r8d; TitleIndex
0x180046930  mov     rax, [rsp+2D0h+var_260.Buffer]
0x180046935  mov     [rsp+2D0h+Data], rax; Data
0x18004693a  call    cs:__imp_NtSetValueKey
0x180046940  mov     ebx, eax
0x180046942  test    eax, eax
0x180046944  js      loc_180046AFD
0x18004694a  mov     eax, [r14+470h]
0x180046951  lea     r12d, [r15+3]
0x180046955  mov     rcx, [rsp+2D0h+KeyHandle]; KeyHandle
0x18004695a  lea     rdx, stru_180069430; ValueName
0x180046961  mov     [rsp+2D0h+var_298], eax
0x180046965  mov     r9d, r12d; Type
0x180046968  lea     rax, [rsp+2D0h+var_298]
0x18004696d  mov     [rsp+2D0h+DataSize], r12d; DataSize
0x180046972  xor     r8d, r8d; TitleIndex
0x180046975  mov     [rsp+2D0h+Data], rax; Data
0x18004697a  call    cs:__imp_NtSetValueKey
0x180046980  mov     ebx, eax
0x180046982  test    eax, eax
0x180046984  js      loc_180046AFD
0x18004698a  mov     eax, [rsp+2D0h+var_298]
0x18004698e  lea     r15, [r14+468h]
0x180046995  mov     rcx, [rsp+2D0h+KeyHandle]; KeyHandle
0x18004699a  lea     r9d, [r12+7]; Type
0x18004699f  mov     [rsp+2D0h+DataSize], 8; DataSize
0x1800469a7  lea     rdx, stru_180069420; ValueName
0x1800469ae  xor     r8d, r8d; TitleIndex
0x1800469b1  mov     [rsp+2D0h+Data], r15; Data
0x1800469b6  mov     [rdi+0B0h], eax
0x1800469bc  call    cs:__imp_NtSetValueKey
0x1800469c2  mov     ebx, eax
0x1800469c4  test    eax, eax
0x1800469c6  js      loc_180046AFD
0x1800469cc  mov     rax, [r15]
0x1800469cf  lea     r9d, [r12-1]; Type
0x1800469d4  mov     rcx, [rsp+2D0h+KeyHandle]; KeyHandle
0x1800469d9  lea     r15, [r14+424h]
0x1800469e0  mov     [rdi+20h], rax
0x1800469e4  lea     rdx, stru_180069410; ValueName
0x1800469eb  mov     eax, [r14+420h]
0x1800469f2  xor     r8d, r8d; TitleIndex
0x1800469f5  mov     [rsp+2D0h+DataSize], eax; DataSize
0x1800469f9  mov     [rsp+2D0h+Data], r15; Data
0x1800469fe  call    cs:__imp_NtSetValueKey
0x180046a04  mov     ebx, eax
0x180046a06  test    eax, eax
0x180046a08  js      loc_180046AFD
0x180046a0e  mov     rcx, [rsp+2D0h+KeyHandle]; KeyHandle
0x180046a13  lea     rdx, stru_180069400; ValueName
0x180046a1a  mov     dword ptr [rdi+0A8h], 1
0x180046a24  mov     r9d, r12d; Type
0x180046a27  movups  xmm0, xmmword ptr [r15]
0x180046a2b  mov     [rsp+2D0h+DataSize], r12d; DataSize
0x180046a30  xor     r8d, r8d; TitleIndex
0x180046a33  mov     [rsp+2D0h+Data], r13; Data
0x180046a38  movdqu  xmmword ptr [rdi+28h], xmm0
0x180046a3d  call    cs:__imp_NtSetValueKey
0x180046a43  mov     ebx, eax
0x180046a45  test    eax, eax
0x180046a47  js      loc_180046AFD
0x180046a4d  mov     rcx, [rsp+2D0h+Handle]; KeyHandle
0x180046a52  test    rsi, rsi
0x180046a55  jz      short loc_180046ACE
0x180046a57  mov     eax, [rsi+478h]
0x180046a5d  lea     r14, [rsi+47Ch]
0x180046a64  mov     [rsp+2D0h+DataSize], eax; DataSize
0x180046a68  lea     r9d, [r12-1]; Type
0x180046a6d  xor     r8d, r8d; TitleIndex
0x180046a70  mov     [rsp+2D0h+Data], r14; Data
0x180046a75  lea     rdx, stru_180069410; ValueName
0x180046a7c  call    cs:__imp_NtSetValueKey
0x180046a82  mov     ebx, eax
0x180046a84  test    eax, eax
0x180046a86  js      short loc_180046AFD
0x180046a88  mov     rcx, [rsp+2D0h+Handle]; KeyHandle
0x180046a8d  lea     rax, [rsi+4BCh]
0x180046a94  mov     dword ptr [rdi+0ACh], 1
0x180046a9e  lea     rdx, stru_180069400; ValueName
0x180046aa5  movups  xmm0, xmmword ptr [r14]
0x180046aa9  mov     [rsp+2D0h+DataSize], r12d; DataSize
0x180046aae  mov     r9d, r12d; Type
0x180046ab1  xor     r8d, r8d; TitleIndex
0x180046ab4  mov     [rsp+2D0h+Data], rax; Data
0x180046ab9  movups  xmmword ptr [rdi+68h], xmm0
0x180046abd  movups  xmm1, xmmword ptr [r14+10h]
0x180046ac2  movups  xmmword ptr [rdi+78h], xmm1
0x180046ac6  call    cs:__imp_NtSetValueKey
0x180046acc  jmp     short loc_180046AEE
0x180046ace  test    rcx, rcx
0x180046ad1  jz      short loc_180046AF4
0x180046ad3  xorps   xmm0, xmm0
0x180046ad6  mov     dword ptr [rdi+0ACh], 0
0x180046ae0  movups  xmmword ptr [rdi+68h], xmm0
0x180046ae4  movups  xmmword ptr [rdi+78h], xmm0
0x180046ae8  call    cs:__imp_NtDeleteKey
0x180046aee  mov     ebx, eax
0x180046af0  test    eax, eax
0x180046af2  js      short loc_180046AFD
0x180046af4  xor     ebx, ebx
0x180046af6  jmp     short loc_180046AFD
0x180046af8  mov     ebx, 0C000000Dh
0x180046afd  mov     rcx, [rsp+2D0h+Handle]; Handle
0x180046b02  test    rcx, rcx
0x180046b05  jz      short loc_180046B0D
0x180046b07  call    cs:__imp_NtClose
0x180046b0d  mov     rcx, [rsp+2D0h+KeyHandle]; Handle
0x180046b12  test    rcx, rcx
0x180046b15  jz      short loc_180046B1D
0x180046b17  call    cs:__imp_NtClose
0x180046b1d  mov     eax, ebx
0x180046b1f  mov     rcx, [rbp+1D0h+var_40]
0x180046b26  xor     rcx, rsp; StackCookie
0x180046b29  call    __security_check_cookie
0x180046b2e  mov     rbx, [rsp+2D0h+arg_0]
0x180046b36  add     rsp, 2A0h
0x180046b3d  pop     r15
0x180046b3f  pop     r14
0x180046b41  pop     r13
0x180046b43  pop     r12
0x180046b45  pop     rdi
0x180046b46  pop     rsi
0x180046b47  pop     rbp
0x180046b48  retn
```
