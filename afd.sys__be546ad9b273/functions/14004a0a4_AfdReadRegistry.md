# AfdReadRegistry

- ea: `0x14004a0a4`
- end: `0x14004a5ce`
- name: `AfdReadRegistry`
- size: `1322`
- prototype: `int __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14004ac54`

## callees

- `0x14004a0a4`
- `0x14004a5d4`
- `0x14004a6dc`
- `0x140072840`
- `0x140072c80`
- `0x1400937a0`
- `0x140093814`

## import_xrefs

- `ntoskrnl!IoOpenDriverRegistryKey` at `0x14004a0fd`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x14004a0fd`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x14004a3f3`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x14004a3f3`
- `ntoskrnl!ZwClose` at `0x14004a5a8`
- `ntoskrnl!ZwClose` at `0x14004a5a8`
- `ntoskrnl!MmIsThisAnNtAsSystem` at `0x14004a3ff`
- `ntoskrnl!MmIsThisAnNtAsSystem` at `0x14004a3ff`
- `ntoskrnl!RtlGetVersion` at `0x14004a18b`
- `ntoskrnl!RtlGetVersion` at `0x14004a18b`

## string_xrefs

- `0x14004a317`: `DisableRawSecurity`

## pseudocode

```c
int __fastcall AfdReadRegistry(__int64 a1)
{
  __int64 (__fastcall *v2)(_QWORD); // rax
  unsigned int SingleParameter; // eax
  char v4; // cl
  unsigned int v5; // eax
  BOOL v6; // eax
  __int64 v7; // rdi
  __int64 v8; // rbx
  int v9; // eax
  _DWORD *v10; // rcx
  unsigned int v11; // r9d
  unsigned int v12; // r8d
  unsigned int v13; // r9d
  unsigned int v14; // eax
  __int64 v16; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v17; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE VersionInformation[284]; // [rsp+50h] [rbp-B0h] BYREF

  memset(VersionInformation, 0, sizeof(VersionInformation));
  LODWORD(v2) = IoOpenDriverRegistryKey(a1, 0, 1);
  if ( !(_DWORD)v2 )
  {
    SingleParameter = AfdReadSingleParameter(0);
    v4 = 64;
    if ( SingleParameter <= 0x40 )
    {
      v4 = SingleParameter;
      if ( SingleParameter < 2 )
        v4 = 2;
    }
    AfdIrpStackSize = v4;
    AfdTdiStackSize = v4 - 1;
    v5 = AfdReadSingleParameter(0);
    if ( v5 > 0x10 )
      LOBYTE(v5) = 2;
    AfdPriorityBoost = v5;
    memset(&VersionInformation[4], 0, 0x118u);
    *(_DWORD *)VersionInformation = 284;
    v6 = RtlGetVersion((PRTL_OSVERSIONINFOW)VersionInformation) < 0 || VersionInformation[282] == 1;
    v7 = 0;
    AfdDoNotHoldNICBuffers = v6;
    v8 = 0;
    do
    {
      v9 = AfdReadSingleParameter(0);
      v10 = *(&AfdConfigInfo + v8 + 1);
      v8 += 2;
      ++v7;
      *v10 = v9;
    }
    while ( v7 != 17 );
    if ( !AfdSendWindowSize )
      AfdSendWindowSize = 1;
    if ( !AfdReceiveWindowSize )
      AfdReceiveWindowSize = 1;
    v11 = AfdSmallBufferSize;
    if ( (unsigned int)AfdSmallBufferSize < 0x58 )
    {
      if ( (BYTE10(xmmword_1400875E0) & 0x10) != 0 )
        WPP_SF_SlP();
      v11 = 88;
      LODWORD(AfdSmallBufferSize) = 88;
    }
    v12 = AfdMediumBufferSize;
    if ( (unsigned int)AfdMediumBufferSize < v11 )
    {
      if ( (BYTE10(xmmword_1400875E0) & 0x10) != 0 )
        WPP_SF_Sll(1300, 15, AfdMediumBufferSize, (unsigned int)L"MediumBufferSize", AfdMediumBufferSize, v11);
      v12 = AfdSmallBufferSize;
      LODWORD(AfdMediumBufferSize) = AfdSmallBufferSize;
    }
    v13 = AfdLargeBufferSize;
    if ( (unsigned int)AfdLargeBufferSize < v12 )
    {
      if ( (BYTE10(xmmword_1400875E0) & 0x10) != 0 )
        WPP_SF_Sll(1300, 16, v12, (unsigned int)L"LargeBufferSize", AfdLargeBufferSize, v12);
      v13 = AfdMediumBufferSize;
      LODWORD(AfdLargeBufferSize) = AfdMediumBufferSize;
    }
    if ( (unsigned int)AfdHugeBufferSize < v13 )
    {
      if ( (BYTE10(xmmword_1400875E0) & 0x10) != 0 )
        WPP_SF_Sll(1300, 17, AfdHugeBufferSize, (unsigned int)L"HugeBufferSize", AfdHugeBufferSize, v13);
      LODWORD(AfdHugeBufferSize) = AfdLargeBufferSize;
    }
    AfdIgnorePushBitOnReceives = (unsigned int)AfdReadSingleParameter(0) != 0;
    AfdDisableRawSecurity = (unsigned int)AfdReadSingleParameter(0) != 0;
    AfdDisableDirectSuperAccept = (unsigned int)AfdReadSingleParameter(0) != 0;
    AfdDisableChainedReceive = (unsigned int)AfdReadSingleParameter(0) != 0;
    AfdUseTdiSendAndDisconnect = (unsigned int)AfdReadSingleParameter(0) != 0;
    if ( (unsigned int)AfdReadSingleParameter(0) )
    {
      v17 = WNF_AFD_IGNORE_ORDERLY_RELEASE_CHANGE;
      v16 = 0;
      ExSubscribeWnfStateChange(&v16, &v17, 1);
    }
    if ( MmIsThisAnNtAsSystem() )
      AfdMaxActiveTransmitFileCount = AfdReadSingleParameter(0);
    if ( AfdDefaultTransmitWorker != 16 && AfdDefaultTransmitWorker != 32 )
    {
      if ( (BYTE2(xmmword_1400875E0) & 0x10) != 0 )
        WPP_SF_Sll(1044, 18, AfdDefaultTransmitWorker, (unsigned int)L"TransmitWorker", AfdDefaultTransmitWorker, 16);
      AfdDefaultTransmitWorker = 16;
    }
    v14 = AfdReadSingleParameter(0);
    if ( v14 != AfdBufferAlignment )
    {
      if ( v14 - 16 > 0xFF0 || ((v14 - 1) & v14) != 0 )
      {
        if ( (BYTE10(xmmword_1400875E0) & 0x10) != 0 )
          WPP_SF_Sll(1300, 19, v14, (unsigned int)L"BufferAlignment", v14, AfdBufferAlignment);
      }
      else
      {
        LODWORD(AfdAlignmentTableSize) = v14 >> 4;
        AfdBufferAlignment = v14;
      }
    }
    AfdTdiWellKnownProviderValidationLevel = AfdReadTdiValidationLevel(
                                               0,
                                               L"AfdTdiWellKnownProviderValidationLevel",
                                               (unsigned int)AfdTdiWellKnownProviderValidationLevel);
    AfdTdiUnknownProviderValidationLevel = AfdReadTdiValidationLevel(
                                             0,
                                             L"AfdTdiUnknownProviderValidationLevel",
                                             (unsigned int)AfdTdiUnknownProviderValidationLevel);
    AfdAllowTdiFilters = (unsigned int)AfdReadSingleParameter(0) != 0;
    if ( (unsigned int)AfdReadSingleParameter(0) )
    {
      AfdParametersNotifyHandle = 0;
      v2 = AfdReadVolatileParameters;
      qword_140087E90 = (__int64)AfdReadVolatileParameters;
      AfdVolatileConfig = 1;
      qword_140087E98 = 0;
      *(_QWORD *)AfdParametersNotifyWorker = 0;
    }
    else
    {
      AfdVolatileConfig = 0;
      LODWORD(v2) = ZwClose(0);
    }
  }
  return (int)v2;
}

```

## disassembly

```asm
0x14004a0a4  push    rbp
0x14004a0a6  push    rbx
0x14004a0a7  push    rdi
0x14004a0a8  push    r12
0x14004a0aa  lea     rbp, [rsp-88h]
0x14004a0b2  sub     rsp, 188h
0x14004a0b9  mov     rax, cs:__security_cookie
0x14004a0c0  xor     rax, rsp
0x14004a0c3  mov     [rbp+0A0h+var_30], rax
0x14004a0c7  mov     rbx, rcx
0x14004a0ca  mov     [rsp+1A0h+Handle], 0
0x14004a0d3  mov     edi, 11Ch
0x14004a0d8  lea     rcx, [rsp+1A0h+VersionInformation]; void *
0x14004a0dd  mov     r8d, edi; Size
0x14004a0e0  xor     edx, edx; Val
0x14004a0e2  call    memset
0x14004a0e7  xor     r9d, r9d
0x14004a0ea  lea     rax, [rsp+1A0h+Handle]
0x14004a0ef  xor     edx, edx
0x14004a0f1  mov     [rsp+1A0h+var_180], rax
0x14004a0f6  mov     rcx, rbx
0x14004a0f9  lea     r8d, [r9+1]
0x14004a0fd  call    cs:__imp_IoOpenDriverRegistryKey
0x14004a104  nop     dword ptr [rax+rax+00h]
0x14004a109  test    eax, eax
0x14004a10b  jnz     loc_14004A5B4
0x14004a111  movsx   r8d, cs:AfdIrpStackSize
0x14004a119  lea     rdx, aIrpstacksize; "IrpStackSize"
0x14004a120  mov     rcx, [rsp+1A0h+Handle]; KeyHandle
0x14004a125  call    AfdReadSingleParameter
0x14004a12a  mov     ebx, 2
0x14004a12f  lea     ecx, [rbx+3Eh]
0x14004a132  cmp     eax, ecx
0x14004a134  ja      short loc_14004A13D
0x14004a136  cmp     eax, ebx
0x14004a138  mov     ecx, eax
0x14004a13a  cmovb   ecx, ebx
0x14004a13d  movsx   r8d, cs:AfdPriorityBoost
0x14004a145  lea     rdx, aPriorityboost; "PriorityBoost"
0x14004a14c  mov     cs:AfdIrpStackSize, cl
0x14004a152  dec     cl
0x14004a154  mov     cs:AfdTdiStackSize, cl
0x14004a15a  mov     rcx, [rsp+1A0h+Handle]; KeyHandle
0x14004a15f  call    AfdReadSingleParameter
0x14004a164  cmp     eax, 10h
0x14004a167  lea     rcx, [rsp+1A0h+VersionInformation.dwMajorVersion]; void *
0x14004a16c  mov     r8d, 118h; Size
0x14004a172  cmova   eax, ebx
0x14004a175  xor     edx, edx; Val
0x14004a177  mov     cs:AfdPriorityBoost, al
0x14004a17d  call    memset
0x14004a182  lea     rcx, [rsp+1A0h+VersionInformation]; lpVersionInformation
0x14004a187  mov     [rsp+1A0h+VersionInformation.dwOSVersionInfoSize], edi
0x14004a18b  call    cs:__imp_RtlGetVersion
0x14004a192  nop     dword ptr [rax+rax+00h]
0x14004a197  test    eax, eax
0x14004a199  js      short loc_14004A1A5
0x14004a19b  cmp     [rbp+0A0h+var_36], 1
0x14004a19f  jz      short loc_14004A1A5
0x14004a1a1  xor     eax, eax
0x14004a1a3  jmp     short loc_14004A1AA
0x14004a1a5  mov     eax, 1
0x14004a1aa  xor     edi, edi
0x14004a1ac  mov     cs:AfdDoNotHoldNICBuffers, eax
0x14004a1b2  xor     ebx, ebx
0x14004a1b4  lea     r12, AfdConfigInfo
0x14004a1bb  mov     r8, [rbx+r12+8]
0x14004a1c0  mov     rdx, [rbx+r12]
0x14004a1c4  mov     rcx, [rsp+1A0h+Handle]; KeyHandle
0x14004a1c9  mov     r8d, [r8]
0x14004a1cc  call    AfdReadSingleParameter
0x14004a1d1  mov     rcx, [rbx+r12+8]
0x14004a1d6  lea     rbx, [rbx+10h]
0x14004a1da  inc     rdi
0x14004a1dd  mov     [rcx], eax
0x14004a1df  cmp     rdi, 11h
0x14004a1e3  jnz     short loc_14004A1BB
0x14004a1e5  cmp     cs:AfdSendWindowSize, 0
0x14004a1ec  jnz     short loc_14004A1F8
0x14004a1ee  mov     cs:AfdSendWindowSize, 1
0x14004a1f8  cmp     cs:AfdReceiveWindowSize, 0
0x14004a1ff  jnz     short loc_14004A20B
0x14004a201  mov     cs:AfdReceiveWindowSize, 1
0x14004a20b  mov     r9d, cs:AfdSmallBufferSize
0x14004a212  cmp     r9d, 58h ; 'X'
0x14004a216  jnb     short loc_14004A233
0x14004a218  test    byte ptr cs:xmmword_1400875E0+0Ah, 10h
0x14004a21f  jz      short loc_14004A226
0x14004a221  call    WPP_SF_SlP
0x14004a226  mov     r9d, 58h ; 'X'
0x14004a22c  mov     cs:AfdSmallBufferSize, r9d
0x14004a233  mov     r8d, cs:AfdMediumBufferSize
0x14004a23a  mov     ebx, 514h
0x14004a23f  cmp     r8d, r9d
0x14004a242  jnb     short loc_14004A278
0x14004a244  test    byte ptr cs:xmmword_1400875E0+0Ah, 10h
0x14004a24b  jz      short loc_14004A26A
0x14004a24d  mov     dword ptr [rsp+1A0h+var_178], r9d
0x14004a252  mov     edx, 0Fh
0x14004a257  lea     r9, aMediumbuffersi; "MediumBufferSize"
0x14004a25e  mov     dword ptr [rsp+1A0h+var_180], r8d
0x14004a263  mov     ecx, ebx
0x14004a265  call    WPP_SF_Sll
0x14004a26a  mov     r8d, cs:AfdSmallBufferSize
0x14004a271  mov     cs:AfdMediumBufferSize, r8d
0x14004a278  mov     r9d, cs:AfdLargeBufferSize
0x14004a27f  cmp     r9d, r8d
0x14004a282  jnb     short loc_14004A2B8
0x14004a284  test    byte ptr cs:xmmword_1400875E0+0Ah, 10h
0x14004a28b  jz      short loc_14004A2AA
0x14004a28d  mov     dword ptr [rsp+1A0h+var_178], r8d
0x14004a292  mov     edx, 10h
0x14004a297  mov     dword ptr [rsp+1A0h+var_180], r9d
0x14004a29c  mov     ecx, ebx
0x14004a29e  lea     r9, aLargebuffersiz; "LargeBufferSize"
0x14004a2a5  call    WPP_SF_Sll
0x14004a2aa  mov     r9d, cs:AfdMediumBufferSize
0x14004a2b1  mov     cs:AfdLargeBufferSize, r9d
0x14004a2b8  mov     r8d, cs:AfdHugeBufferSize
0x14004a2bf  cmp     r8d, r9d
0x14004a2c2  jnb     short loc_14004A2F6
0x14004a2c4  test    byte ptr cs:xmmword_1400875E0+0Ah, 10h
0x14004a2cb  jz      short loc_14004A2EA
0x14004a2cd  mov     dword ptr [rsp+1A0h+var_178], r9d
0x14004a2d2  mov     edx, 11h
0x14004a2d7  lea     r9, aHugebuffersize; "HugeBufferSize"
0x14004a2de  mov     dword ptr [rsp+1A0h+var_180], r8d
0x14004a2e3  mov     ecx, ebx
0x14004a2e5  call    WPP_SF_Sll
0x14004a2ea  mov     eax, cs:AfdLargeBufferSize
0x14004a2f0  mov     cs:AfdHugeBufferSize, eax
0x14004a2f6  movzx   r8d, cs:AfdIgnorePushBitOnReceives
0x14004a2fe  lea     rdx, aIgnorepushbito; "IgnorePushBitOnReceives"
0x14004a305  mov     rcx, [rsp+1A0h+Handle]; KeyHandle
0x14004a30a  call    AfdReadSingleParameter
0x14004a30f  movzx   r8d, cs:AfdDisableRawSecurity
0x14004a317  lea     rdx, aDisablerawsecu; "DisableRawSecurity"
0x14004a31e  mov     rcx, [rsp+1A0h+Handle]; KeyHandle
0x14004a323  test    eax, eax
0x14004a325  setnz   cs:AfdIgnorePushBitOnReceives
0x14004a32c  call    AfdReadSingleParameter
0x14004a331  movzx   r8d, cs:AfdDisableDirectSuperAccept
0x14004a339  lea     rdx, aDisabledirecta; "DisableDirectAcceptEx"
0x14004a340  mov     rcx, [rsp+1A0h+Handle]; KeyHandle
0x14004a345  test    eax, eax
0x14004a347  setnz   cs:AfdDisableRawSecurity
0x14004a34e  call    AfdReadSingleParameter
0x14004a353  movzx   r8d, cs:AfdDisableChainedReceive
0x14004a35b  lea     rdx, aDisablechained; "DisableChainedReceive"
0x14004a362  mov     rcx, [rsp+1A0h+Handle]; KeyHandle
0x14004a367  test    eax, eax
0x14004a369  setnz   cs:AfdDisableDirectSuperAccept
0x14004a370  call    AfdReadSingleParameter
0x14004a375  movzx   r8d, cs:AfdUseTdiSendAndDisconnect
0x14004a37d  lea     rdx, aUsetdisendandd; "UseTdiSendAndDisconnect"
0x14004a384  mov     rcx, [rsp+1A0h+Handle]; KeyHandle
0x14004a389  test    eax, eax
0x14004a38b  setnz   cs:AfdDisableChainedReceive
0x14004a392  call    AfdReadSingleParameter
0x14004a397  mov     rcx, [rsp+1A0h+Handle]; KeyHandle
0x14004a39c  lea     rdx, aIgnoreorderlyr; "IgnoreOrderlyRelease"
0x14004a3a3  test    eax, eax
0x14004a3a5  setnz   cs:AfdUseTdiSendAndDisconnect
0x14004a3ac  xor     r8d, r8d
0x14004a3af  call    AfdReadSingleParameter
0x14004a3b4  test    eax, eax
0x14004a3b6  jz      short loc_14004A3FF
0x14004a3b8  mov     rax, cs:WNF_AFD_IGNORE_ORDERLY_RELEASE_CHANGE
0x14004a3bf  lea     rdx, [rsp+1A0h+var_160]
0x14004a3c4  xor     r9d, r9d
0x14004a3c7  mov     [rsp+1A0h+var_160], rax
0x14004a3cc  lea     rax, AfdIgnoreOrderlyReleaseCallback
0x14004a3d3  mov     [rsp+1A0h+var_178], 0
0x14004a3dc  lea     rcx, [rsp+1A0h+var_168]
0x14004a3e1  mov     [rsp+1A0h+var_168], 0
0x14004a3ea  mov     [rsp+1A0h+var_180], rax
0x14004a3ef  lea     r8d, [r9+1]
0x14004a3f3  call    cs:__imp_ExSubscribeWnfStateChange
0x14004a3fa  nop     dword ptr [rax+rax+00h]
0x14004a3ff  call    cs:__imp_MmIsThisAnNtAsSystem
0x14004a406  nop     dword ptr [rax+rax+00h]
0x14004a40b  test    al, al
0x14004a40d  jz      short loc_14004A42D
0x14004a40f  mov     r8d, cs:AfdMaxActiveTransmitFileCount
0x14004a416  lea     rdx, aMaxactivetrans; "MaxActiveTransmitFileCount"
0x14004a41d  mov     rcx, [rsp+1A0h+Handle]; KeyHandle
0x14004a422  call    AfdReadSingleParameter
0x14004a427  mov     cs:AfdMaxActiveTransmitFileCount, eax
0x14004a42d  mov     r8d, cs:AfdDefaultTransmitWorker
0x14004a434  cmp     r8d, 10h
0x14004a438  jz      short loc_14004A476
0x14004a43a  cmp     r8d, 20h ; ' '
0x14004a43e  jz      short loc_14004A476
0x14004a440  test    byte ptr cs:xmmword_1400875E0+2, 10h
0x14004a447  jz      short loc_14004A46C
0x14004a449  mov     edx, 12h
0x14004a44e  mov     dword ptr [rsp+1A0h+var_178], 10h
0x14004a456  mov     ecx, 414h
0x14004a45b  mov     dword ptr [rsp+1A0h+var_180], r8d
0x14004a460  lea     r9, aTransmitworker; "TransmitWorker"
0x14004a467  call    WPP_SF_Sll
0x14004a46c  mov     cs:AfdDefaultTransmitWorker, 10h
0x14004a476  mov     r8d, cs:AfdBufferAlignment
0x14004a47d  lea     rdx, aBufferalignmen; "BufferAlignment"
0x14004a484  mov     rcx, [rsp+1A0h+Handle]; KeyHandle
0x14004a489  call    AfdReadSingleParameter
0x14004a48e  mov     r9d, cs:AfdBufferAlignment
0x14004a495  mov     r8d, eax
0x14004a498  cmp     eax, r9d
0x14004a49b  jz      short loc_14004A4E8
0x14004a49d  lea     ecx, [rax-10h]
0x14004a4a0  cmp     ecx, 0FF0h
0x14004a4a6  ja      short loc_14004A4C2
0x14004a4a8  lea     ecx, [rax-1]
0x14004a4ab  test    eax, ecx
0x14004a4ad  jnz     short loc_14004A4C2
0x14004a4af  shr     r8d, 4
0x14004a4b3  mov     cs:AfdAlignmentTableSize, r8d
0x14004a4ba  mov     cs:AfdBufferAlignment, eax
0x14004a4c0  jmp     short loc_14004A4E8
0x14004a4c2  test    byte ptr cs:xmmword_1400875E0+0Ah, 10h
0x14004a4c9  jz      short loc_14004A4E8
0x14004a4cb  mov     dword ptr [rsp+1A0h+var_178], r9d
0x14004a4d0  mov     edx, 13h
0x14004a4d5  lea     r9, aBufferalignmen; "BufferAlignment"
0x14004a4dc  mov     dword ptr [rsp+1A0h+var_180], r8d
0x14004a4e1  mov     ecx, ebx
0x14004a4e3  call    WPP_SF_Sll
0x14004a4e8  mov     r8d, cs:AfdTdiWellKnownProviderValidationLevel
0x14004a4ef  lea     rdx, aAfdtdiwellknow; "AfdTdiWellKnownProviderValidationLevel"
0x14004a4f6  mov     rcx, [rsp+1A0h+Handle]
0x14004a4fb  call    AfdReadTdiValidationLevel
0x14004a500  mov     r8d, cs:AfdTdiUnknownProviderValidationLevel
0x14004a507  lea     rdx, aAfdtdiunknownp; "AfdTdiUnknownProviderValidationLevel"
0x14004a50e  mov     rcx, [rsp+1A0h+Handle]
0x14004a513  mov     cs:AfdTdiWellKnownProviderValidationLevel, eax
0x14004a519  call    AfdReadTdiValidationLevel
0x14004a51e  movzx   r8d, cs:AfdAllowTdiFilters
0x14004a526  lea     rdx, aAfdallowtdifil; "AfdAllowTdiFilters"
0x14004a52d  mov     rcx, [rsp+1A0h+Handle]; KeyHandle
0x14004a532  mov     cs:AfdTdiUnknownProviderValidationLevel, eax
0x14004a538  call    AfdReadSingleParameter
0x14004a53d  movzx   r8d, cs:AfdVolatileConfig
0x14004a545  lea     rdx, aVolatileparame; "VolatileParameters"
0x14004a54c  mov     rcx, [rsp+1A0h+Handle]; KeyHandle
0x14004a551  test    eax, eax
0x14004a553  setnz   cs:AfdAllowTdiFilters
0x14004a55a  call    AfdReadSingleParameter
0x14004a55f  test    eax, eax
0x14004a561  jz      short loc_14004A59C
0x14004a563  mov     rax, [rsp+1A0h+Handle]
0x14004a568  mov     cs:AfdParametersNotifyHandle, rax
0x14004a56f  lea     rax, AfdReadVolatileParameters
0x14004a576  mov     cs:qword_140087E90, rax
0x14004a57d  mov     cs:AfdVolatileConfig, 1
0x14004a584  mov     cs:qword_140087E98, 0
0x14004a58f  mov     cs:AfdParametersNotifyWorker, 0
0x14004a59a  jmp     short loc_14004A5B4
0x14004a59c  mov     rcx, [rsp+1A0h+Handle]; Handle
0x14004a5a1  mov     cs:AfdVolatileConfig, 0
0x14004a5a8  call    cs:__imp_ZwClose
0x14004a5af  nop     dword ptr [rax+rax+00h]
0x14004a5b4  mov     rcx, [rbp+0A0h+var_30]
0x14004a5b8  xor     rcx, rsp; StackCookie
0x14004a5bb  call    __security_check_cookie
0x14004a5c0  add     rsp, 188h
0x14004a5c7  pop     r12
0x14004a5c9  pop     rdi
0x14004a5ca  pop     rbx
0x14004a5cb  pop     rbp
0x14004a5cc  retn
```
