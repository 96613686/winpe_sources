# AfdReadRegistry

- ea: `0x14004a004`
- end: `0x14004a52e`
- name: `AfdReadRegistry`
- size: `1322`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14004abb4`

## callees

- `0x14004a004`
- `0x14004a534`
- `0x14004a63c`
- `0x1400726a0`
- `0x140072b00`
- `0x1400937a0`
- `0x140093814`

## import_xrefs

- `ntoskrnl!IoOpenDriverRegistryKey` at `0x14004a05d`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x14004a05d`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x14004a353`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x14004a353`
- `ntoskrnl!ZwClose` at `0x14004a508`
- `ntoskrnl!ZwClose` at `0x14004a508`
- `ntoskrnl!MmIsThisAnNtAsSystem` at `0x14004a35f`
- `ntoskrnl!MmIsThisAnNtAsSystem` at `0x14004a35f`
- `ntoskrnl!RtlGetVersion` at `0x14004a0eb`
- `ntoskrnl!RtlGetVersion` at `0x14004a0eb`

## string_xrefs

- `0x14004a277`: `DisableRawSecurity`

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
0x14004a004  push    rbp
0x14004a006  push    rbx
0x14004a007  push    rdi
0x14004a008  push    r12
0x14004a00a  lea     rbp, [rsp-88h]
0x14004a012  sub     rsp, 188h
0x14004a019  mov     rax, cs:__security_cookie
0x14004a020  xor     rax, rsp
0x14004a023  mov     [rbp+0A0h+var_30], rax
0x14004a027  mov     rbx, rcx
0x14004a02a  mov     [rsp+1A0h+Handle], 0
0x14004a033  mov     edi, 11Ch
0x14004a038  lea     rcx, [rsp+1A0h+VersionInformation]; void *
0x14004a03d  mov     r8d, edi; Size
0x14004a040  xor     edx, edx; Val
0x14004a042  call    memset
0x14004a047  xor     r9d, r9d
0x14004a04a  lea     rax, [rsp+1A0h+Handle]
0x14004a04f  xor     edx, edx
0x14004a051  mov     [rsp+1A0h+var_180], rax
0x14004a056  mov     rcx, rbx
0x14004a059  lea     r8d, [r9+1]
0x14004a05d  call    cs:__imp_IoOpenDriverRegistryKey
0x14004a064  nop     dword ptr [rax+rax+00h]
0x14004a069  test    eax, eax
0x14004a06b  jnz     loc_14004A514
0x14004a071  movsx   r8d, cs:AfdIrpStackSize
0x14004a079  lea     rdx, aIrpstacksize; "IrpStackSize"
0x14004a080  mov     rcx, [rsp+1A0h+Handle]; KeyHandle
0x14004a085  call    AfdReadSingleParameter
0x14004a08a  mov     ebx, 2
0x14004a08f  lea     ecx, [rbx+3Eh]
0x14004a092  cmp     eax, ecx
0x14004a094  ja      short loc_14004A09D
0x14004a096  cmp     eax, ebx
0x14004a098  mov     ecx, eax
0x14004a09a  cmovb   ecx, ebx
0x14004a09d  movsx   r8d, cs:AfdPriorityBoost
0x14004a0a5  lea     rdx, aPriorityboost; "PriorityBoost"
0x14004a0ac  mov     cs:AfdIrpStackSize, cl
0x14004a0b2  dec     cl
0x14004a0b4  mov     cs:AfdTdiStackSize, cl
0x14004a0ba  mov     rcx, [rsp+1A0h+Handle]; KeyHandle
0x14004a0bf  call    AfdReadSingleParameter
0x14004a0c4  cmp     eax, 10h
0x14004a0c7  lea     rcx, [rsp+1A0h+VersionInformation.dwMajorVersion]; void *
0x14004a0cc  mov     r8d, 118h; Size
0x14004a0d2  cmova   eax, ebx
0x14004a0d5  xor     edx, edx; Val
0x14004a0d7  mov     cs:AfdPriorityBoost, al
0x14004a0dd  call    memset
0x14004a0e2  lea     rcx, [rsp+1A0h+VersionInformation]; lpVersionInformation
0x14004a0e7  mov     [rsp+1A0h+VersionInformation.dwOSVersionInfoSize], edi
0x14004a0eb  call    cs:__imp_RtlGetVersion
0x14004a0f2  nop     dword ptr [rax+rax+00h]
0x14004a0f7  test    eax, eax
0x14004a0f9  js      short loc_14004A105
0x14004a0fb  cmp     [rbp+0A0h+var_36], 1
0x14004a0ff  jz      short loc_14004A105
0x14004a101  xor     eax, eax
0x14004a103  jmp     short loc_14004A10A
0x14004a105  mov     eax, 1
0x14004a10a  xor     edi, edi
0x14004a10c  mov     cs:AfdDoNotHoldNICBuffers, eax
0x14004a112  xor     ebx, ebx
0x14004a114  lea     r12, AfdConfigInfo
0x14004a11b  mov     r8, [rbx+r12+8]
0x14004a120  mov     rdx, [rbx+r12]
0x14004a124  mov     rcx, [rsp+1A0h+Handle]; KeyHandle
0x14004a129  mov     r8d, [r8]
0x14004a12c  call    AfdReadSingleParameter
0x14004a131  mov     rcx, [rbx+r12+8]
0x14004a136  lea     rbx, [rbx+10h]
0x14004a13a  inc     rdi
0x14004a13d  mov     [rcx], eax
0x14004a13f  cmp     rdi, 11h
0x14004a143  jnz     short loc_14004A11B
0x14004a145  cmp     cs:AfdSendWindowSize, 0
0x14004a14c  jnz     short loc_14004A158
0x14004a14e  mov     cs:AfdSendWindowSize, 1
0x14004a158  cmp     cs:AfdReceiveWindowSize, 0
0x14004a15f  jnz     short loc_14004A16B
0x14004a161  mov     cs:AfdReceiveWindowSize, 1
0x14004a16b  mov     r9d, cs:AfdSmallBufferSize
0x14004a172  cmp     r9d, 58h ; 'X'
0x14004a176  jnb     short loc_14004A193
0x14004a178  test    byte ptr cs:xmmword_1400875E0+0Ah, 10h
0x14004a17f  jz      short loc_14004A186
0x14004a181  call    WPP_SF_SlP
0x14004a186  mov     r9d, 58h ; 'X'
0x14004a18c  mov     cs:AfdSmallBufferSize, r9d
0x14004a193  mov     r8d, cs:AfdMediumBufferSize
0x14004a19a  mov     ebx, 514h
0x14004a19f  cmp     r8d, r9d
0x14004a1a2  jnb     short loc_14004A1D8
0x14004a1a4  test    byte ptr cs:xmmword_1400875E0+0Ah, 10h
0x14004a1ab  jz      short loc_14004A1CA
0x14004a1ad  mov     dword ptr [rsp+1A0h+var_178], r9d
0x14004a1b2  mov     edx, 0Fh
0x14004a1b7  lea     r9, aMediumbuffersi; "MediumBufferSize"
0x14004a1be  mov     dword ptr [rsp+1A0h+var_180], r8d
0x14004a1c3  mov     ecx, ebx
0x14004a1c5  call    WPP_SF_Sll
0x14004a1ca  mov     r8d, cs:AfdSmallBufferSize
0x14004a1d1  mov     cs:AfdMediumBufferSize, r8d
0x14004a1d8  mov     r9d, cs:AfdLargeBufferSize
0x14004a1df  cmp     r9d, r8d
0x14004a1e2  jnb     short loc_14004A218
0x14004a1e4  test    byte ptr cs:xmmword_1400875E0+0Ah, 10h
0x14004a1eb  jz      short loc_14004A20A
0x14004a1ed  mov     dword ptr [rsp+1A0h+var_178], r8d
0x14004a1f2  mov     edx, 10h
0x14004a1f7  mov     dword ptr [rsp+1A0h+var_180], r9d
0x14004a1fc  mov     ecx, ebx
0x14004a1fe  lea     r9, aLargebuffersiz; "LargeBufferSize"
0x14004a205  call    WPP_SF_Sll
0x14004a20a  mov     r9d, cs:AfdMediumBufferSize
0x14004a211  mov     cs:AfdLargeBufferSize, r9d
0x14004a218  mov     r8d, cs:AfdHugeBufferSize
0x14004a21f  cmp     r8d, r9d
0x14004a222  jnb     short loc_14004A256
0x14004a224  test    byte ptr cs:xmmword_1400875E0+0Ah, 10h
0x14004a22b  jz      short loc_14004A24A
0x14004a22d  mov     dword ptr [rsp+1A0h+var_178], r9d
0x14004a232  mov     edx, 11h
0x14004a237  lea     r9, aHugebuffersize; "HugeBufferSize"
0x14004a23e  mov     dword ptr [rsp+1A0h+var_180], r8d
0x14004a243  mov     ecx, ebx
0x14004a245  call    WPP_SF_Sll
0x14004a24a  mov     eax, cs:AfdLargeBufferSize
0x14004a250  mov     cs:AfdHugeBufferSize, eax
0x14004a256  movzx   r8d, cs:AfdIgnorePushBitOnReceives
0x14004a25e  lea     rdx, aIgnorepushbito; "IgnorePushBitOnReceives"
0x14004a265  mov     rcx, [rsp+1A0h+Handle]; KeyHandle
0x14004a26a  call    AfdReadSingleParameter
0x14004a26f  movzx   r8d, cs:AfdDisableRawSecurity
0x14004a277  lea     rdx, aDisablerawsecu; "DisableRawSecurity"
0x14004a27e  mov     rcx, [rsp+1A0h+Handle]; KeyHandle
0x14004a283  test    eax, eax
0x14004a285  setnz   cs:AfdIgnorePushBitOnReceives
0x14004a28c  call    AfdReadSingleParameter
0x14004a291  movzx   r8d, cs:AfdDisableDirectSuperAccept
0x14004a299  lea     rdx, aDisabledirecta; "DisableDirectAcceptEx"
0x14004a2a0  mov     rcx, [rsp+1A0h+Handle]; KeyHandle
0x14004a2a5  test    eax, eax
0x14004a2a7  setnz   cs:AfdDisableRawSecurity
0x14004a2ae  call    AfdReadSingleParameter
0x14004a2b3  movzx   r8d, cs:AfdDisableChainedReceive
0x14004a2bb  lea     rdx, aDisablechained; "DisableChainedReceive"
0x14004a2c2  mov     rcx, [rsp+1A0h+Handle]; KeyHandle
0x14004a2c7  test    eax, eax
0x14004a2c9  setnz   cs:AfdDisableDirectSuperAccept
0x14004a2d0  call    AfdReadSingleParameter
0x14004a2d5  movzx   r8d, cs:AfdUseTdiSendAndDisconnect
0x14004a2dd  lea     rdx, aUsetdisendandd; "UseTdiSendAndDisconnect"
0x14004a2e4  mov     rcx, [rsp+1A0h+Handle]; KeyHandle
0x14004a2e9  test    eax, eax
0x14004a2eb  setnz   cs:AfdDisableChainedReceive
0x14004a2f2  call    AfdReadSingleParameter
0x14004a2f7  mov     rcx, [rsp+1A0h+Handle]; KeyHandle
0x14004a2fc  lea     rdx, aIgnoreorderlyr; "IgnoreOrderlyRelease"
0x14004a303  test    eax, eax
0x14004a305  setnz   cs:AfdUseTdiSendAndDisconnect
0x14004a30c  xor     r8d, r8d
0x14004a30f  call    AfdReadSingleParameter
0x14004a314  test    eax, eax
0x14004a316  jz      short loc_14004A35F
0x14004a318  mov     rax, cs:WNF_AFD_IGNORE_ORDERLY_RELEASE_CHANGE
0x14004a31f  lea     rdx, [rsp+1A0h+var_160]
0x14004a324  xor     r9d, r9d
0x14004a327  mov     [rsp+1A0h+var_160], rax
0x14004a32c  lea     rax, AfdIgnoreOrderlyReleaseCallback
0x14004a333  mov     [rsp+1A0h+var_178], 0
0x14004a33c  lea     rcx, [rsp+1A0h+var_168]
0x14004a341  mov     [rsp+1A0h+var_168], 0
0x14004a34a  mov     [rsp+1A0h+var_180], rax
0x14004a34f  lea     r8d, [r9+1]
0x14004a353  call    cs:__imp_ExSubscribeWnfStateChange
0x14004a35a  nop     dword ptr [rax+rax+00h]
0x14004a35f  call    cs:__imp_MmIsThisAnNtAsSystem
0x14004a366  nop     dword ptr [rax+rax+00h]
0x14004a36b  test    al, al
0x14004a36d  jz      short loc_14004A38D
0x14004a36f  mov     r8d, cs:AfdMaxActiveTransmitFileCount
0x14004a376  lea     rdx, aMaxactivetrans; "MaxActiveTransmitFileCount"
0x14004a37d  mov     rcx, [rsp+1A0h+Handle]; KeyHandle
0x14004a382  call    AfdReadSingleParameter
0x14004a387  mov     cs:AfdMaxActiveTransmitFileCount, eax
0x14004a38d  mov     r8d, cs:AfdDefaultTransmitWorker
0x14004a394  cmp     r8d, 10h
0x14004a398  jz      short loc_14004A3D6
0x14004a39a  cmp     r8d, 20h ; ' '
0x14004a39e  jz      short loc_14004A3D6
0x14004a3a0  test    byte ptr cs:xmmword_1400875E0+2, 10h
0x14004a3a7  jz      short loc_14004A3CC
0x14004a3a9  mov     edx, 12h
0x14004a3ae  mov     dword ptr [rsp+1A0h+var_178], 10h
0x14004a3b6  mov     ecx, 414h
0x14004a3bb  mov     dword ptr [rsp+1A0h+var_180], r8d
0x14004a3c0  lea     r9, aTransmitworker; "TransmitWorker"
0x14004a3c7  call    WPP_SF_Sll
0x14004a3cc  mov     cs:AfdDefaultTransmitWorker, 10h
0x14004a3d6  mov     r8d, cs:AfdBufferAlignment
0x14004a3dd  lea     rdx, aBufferalignmen; "BufferAlignment"
0x14004a3e4  mov     rcx, [rsp+1A0h+Handle]; KeyHandle
0x14004a3e9  call    AfdReadSingleParameter
0x14004a3ee  mov     r9d, cs:AfdBufferAlignment
0x14004a3f5  mov     r8d, eax
0x14004a3f8  cmp     eax, r9d
0x14004a3fb  jz      short loc_14004A448
0x14004a3fd  lea     ecx, [rax-10h]
0x14004a400  cmp     ecx, 0FF0h
0x14004a406  ja      short loc_14004A422
0x14004a408  lea     ecx, [rax-1]
0x14004a40b  test    eax, ecx
0x14004a40d  jnz     short loc_14004A422
0x14004a40f  shr     r8d, 4
0x14004a413  mov     cs:AfdAlignmentTableSize, r8d
0x14004a41a  mov     cs:AfdBufferAlignment, eax
0x14004a420  jmp     short loc_14004A448
0x14004a422  test    byte ptr cs:xmmword_1400875E0+0Ah, 10h
0x14004a429  jz      short loc_14004A448
0x14004a42b  mov     dword ptr [rsp+1A0h+var_178], r9d
0x14004a430  mov     edx, 13h
0x14004a435  lea     r9, aBufferalignmen; "BufferAlignment"
0x14004a43c  mov     dword ptr [rsp+1A0h+var_180], r8d
0x14004a441  mov     ecx, ebx
0x14004a443  call    WPP_SF_Sll
0x14004a448  mov     r8d, cs:AfdTdiWellKnownProviderValidationLevel
0x14004a44f  lea     rdx, aAfdtdiwellknow; "AfdTdiWellKnownProviderValidationLevel"
0x14004a456  mov     rcx, [rsp+1A0h+Handle]
0x14004a45b  call    AfdReadTdiValidationLevel
0x14004a460  mov     r8d, cs:AfdTdiUnknownProviderValidationLevel
0x14004a467  lea     rdx, aAfdtdiunknownp; "AfdTdiUnknownProviderValidationLevel"
0x14004a46e  mov     rcx, [rsp+1A0h+Handle]
0x14004a473  mov     cs:AfdTdiWellKnownProviderValidationLevel, eax
0x14004a479  call    AfdReadTdiValidationLevel
0x14004a47e  movzx   r8d, cs:AfdAllowTdiFilters
0x14004a486  lea     rdx, aAfdallowtdifil; "AfdAllowTdiFilters"
0x14004a48d  mov     rcx, [rsp+1A0h+Handle]; KeyHandle
0x14004a492  mov     cs:AfdTdiUnknownProviderValidationLevel, eax
0x14004a498  call    AfdReadSingleParameter
0x14004a49d  movzx   r8d, cs:AfdVolatileConfig
0x14004a4a5  lea     rdx, aVolatileparame; "VolatileParameters"
0x14004a4ac  mov     rcx, [rsp+1A0h+Handle]; KeyHandle
0x14004a4b1  test    eax, eax
0x14004a4b3  setnz   cs:AfdAllowTdiFilters
0x14004a4ba  call    AfdReadSingleParameter
0x14004a4bf  test    eax, eax
0x14004a4c1  jz      short loc_14004A4FC
0x14004a4c3  mov     rax, [rsp+1A0h+Handle]
0x14004a4c8  mov     cs:AfdParametersNotifyHandle, rax
0x14004a4cf  lea     rax, AfdReadVolatileParameters
0x14004a4d6  mov     cs:qword_140087E90, rax
0x14004a4dd  mov     cs:AfdVolatileConfig, 1
0x14004a4e4  mov     cs:qword_140087E98, 0
0x14004a4ef  mov     cs:AfdParametersNotifyWorker, 0
0x14004a4fa  jmp     short loc_14004A514
0x14004a4fc  mov     rcx, [rsp+1A0h+Handle]; Handle
0x14004a501  mov     cs:AfdVolatileConfig, 0
0x14004a508  call    cs:__imp_ZwClose
0x14004a50f  nop     dword ptr [rax+rax+00h]
0x14004a514  mov     rcx, [rbp+0A0h+var_30]
0x14004a518  xor     rcx, rsp; StackCookie
0x14004a51b  call    __security_check_cookie
0x14004a520  add     rsp, 188h
0x14004a527  pop     r12
0x14004a529  pop     rdi
0x14004a52a  pop     rbx
0x14004a52b  pop     rbp
0x14004a52c  retn
```
