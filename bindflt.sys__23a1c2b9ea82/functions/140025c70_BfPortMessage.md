# BfPortMessage

- ea: `0x140025c70`
- end: `0x140026119`
- name: `BfPortMessage`
- size: `1193`
- prototype: `NTSTATUS __stdcall(PVOID PortCookie, PVOID InputBuffer, ULONG InputBufferLength, PVOID OutputBuffer, ULONG OutputBufferLength, PULONG ReturnOutputBufferLength)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting`

## callees

- `0x140002740`
- `0x140003140`
- `0x140003304`
- `0x1400034c8`
- `0x140004bc0`
- `0x14000f608`
- `0x14000ff58`
- `0x140010384`
- `0x140010898`
- `0x140010d64`
- `0x14001d974`
- `0x140024294`
- `0x140025c70`

## import_xrefs

- `ntoskrnl!ExGetPreviousMode` at `0x140025ca2`
- `ntoskrnl!ExGetPreviousMode` at `0x140025ca2`
- `ntoskrnl!ProbeForWrite` at `0x140025e14`
- `ntoskrnl!ProbeForWrite` at `0x140025e14`
- `ntoskrnl!ProbeForRead` at `0x140025dfa`
- `ntoskrnl!ProbeForRead` at `0x140025dfa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400260d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400260f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400260d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400260f0`
- `ntoskrnl!ExAllocatePool2` at `0x140025d74`
- `ntoskrnl!ExAllocatePool2` at `0x140025e49`
- `ntoskrnl!ExAllocatePool2` at `0x140025d74`
- `ntoskrnl!ExAllocatePool2` at `0x140025e49`

## pseudocode

```c
__int64 __fastcall BfPortMessage(
        PVOID PortCookie,
        PVOID InputBuffer,
        ULONG InputBufferLength,
        PVOID OutputBuffer,
        ULONG OutputBufferLength,
        PULONG ReturnOutputBufferLength)
{
  SIZE_T v6; // r15
  _DWORD *Pool2; // rsi
  ULONG *v9; // rdi
  __int64 v10; // r9
  KPROCESSOR_MODE PreviousMode; // r13
  int v12; // edx
  unsigned int v13; // ebx
  int v14; // r9d
  int v15; // edx
  int v16; // r9d
  __int64 v17; // r9
  ULONG *v18; // rax
  int v19; // edx
  ULONG v20; // eax
  ULONG v21; // ecx
  char v23; // [rsp+30h] [rbp-68h]
  char v24; // [rsp+30h] [rbp-68h]
  char v25; // [rsp+38h] [rbp-60h]
  char v26; // [rsp+40h] [rbp-58h]
  ULONG v27[4]; // [rsp+50h] [rbp-48h] BYREF
  ULONG *v28; // [rsp+60h] [rbp-38h]
  _DWORD *v29; // [rsp+68h] [rbp-30h]

  v6 = InputBufferLength;
  v27[0] = 0;
  Pool2 = 0;
  v9 = 0;
  v28 = 0;
  PreviousMode = ExGetPreviousMode();
  v12 = 12;
  if ( (unsigned int)v6 < 0xC )
  {
    v13 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_41;
    v14 = 10;
    v26 = 12;
    v25 = v6;
    v23 = -93;
    goto LABEL_4;
  }
  if ( OutputBufferLength < 0xC )
  {
    v13 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v14 = 11;
      v26 = 12;
      v25 = OutputBufferLength;
      v23 = -87;
LABEL_4:
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_sDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        3,
        v14,
        (__int64)WPP_d5e84d3892ba3ffb3afa1607ae793b21_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\message.c",
        v23,
        v25,
        v26);
      goto LABEL_41;
    }
    goto LABEL_41;
  }
  Pool2 = (_DWORD *)ExAllocatePool2(256, v6, 1936541250, v10);
  v29 = Pool2;
  if ( !Pool2 )
  {
    v13 = -1073741670;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_41;
    v16 = 12;
    v24 = -79;
    goto LABEL_11;
  }
  if ( PreviousMode == 1 )
  {
    ProbeForRead(InputBuffer, v6, 1u);
    ProbeForWrite(OutputBuffer, OutputBufferLength, 1u);
  }
  if ( PreviousMode )
    RtlCopyFromUser(Pool2, InputBuffer, v6);
  else
    RtlCopyVolatileMemory(Pool2, InputBuffer, v6);
  v18 = (ULONG *)ExAllocatePool2(256, OutputBufferLength, 1936541250, v17);
  v9 = v18;
  v28 = v18;
  if ( !v18 )
  {
    v13 = -1073741670;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_41;
    v16 = 13;
    v24 = -49;
LABEL_11:
    LOBYTE(v15) = 2;
    WPP_RECORDER_SF_sD(
      WPP_GLOBAL_Control->DeviceExtension,
      v15,
      3,
      v16,
      (__int64)WPP_d5e84d3892ba3ffb3afa1607ae793b21_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\message.c",
      v24);
    goto LABEL_41;
  }
  v12 = Pool2[1];
  if ( v12 == (_DWORD)v6 )
  {
    v13 = 0;
    v19 = *Pool2;
    if ( *Pool2 )
    {
      switch ( v19 )
      {
        case 2:
          *v18 = 3;
          v18[1] = 12;
          v20 = BfRemoveVirtualizationMapping(Pool2 + 2, (unsigned int)(Pool2[1] - 8));
          break;
        case 4:
          *v18 = 5;
          v18[1] = 12;
          v20 = BfStoreBatchedVirtualizationMapping((__int64)(Pool2 + 2), Pool2[1] - 8);
          break;
        case 6:
          *v18 = 7;
          v18[1] = 12;
          v20 = BfRemoveBatchedVirtualizationMapping(Pool2 + 2, (unsigned int)(Pool2[1] - 8));
          break;
        case 8:
          v18[1] = BfProcessGetMappingsRequest(Pool2 + 2, OutputBufferLength, v18, v27);
          v21 = v27[0];
          *v9 = v27[0];
          *ReturnOutputBufferLength = v21;
          goto LABEL_38;
        case 10:
          *v18 = 11;
          v18[1] = 12;
          v20 = BfProcessTrackWritesRequest(Pool2 + 2, (unsigned int)(Pool2[1] - 8));
          break;
        default:
          v13 = -1073741811;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v19) = 2;
            WPP_RECORDER_SF_sDD(
              WPP_GLOBAL_Control->DeviceExtension,
              v19,
              3,
              27,
              (__int64)WPP_d5e84d3892ba3ffb3afa1607ae793b21_Traceguids,
              (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\message.c",
              191,
              *Pool2);
          }
          goto LABEL_41;
      }
    }
    else
    {
      *v18 = 1;
      v18[1] = 12;
      v20 = BfStoreVirtualizationMapping((__int64)(Pool2 + 2), Pool2[1] - 8);
    }
    v9[2] = v20;
    *ReturnOutputBufferLength = 12;
LABEL_38:
    if ( PreviousMode )
      RtlCopyToUser(OutputBuffer, v9, OutputBufferLength);
    else
      RtlCopyVolatileMemory(OutputBuffer, v9, OutputBufferLength);
    goto LABEL_41;
  }
  v13 = -1073741811;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v14 = 14;
    v26 = Pool2[1];
    v25 = v6;
    v23 = -41;
    goto LABEL_4;
  }
LABEL_41:
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x736D4642u);
  if ( v9 )
    ExFreePoolWithTag(v9, 0x736D4642u);
  return v13;
}

```

## disassembly

```asm
0x140025c70  mov     rax, rsp
0x140025c73  mov     [rax+8], rbx
0x140025c77  mov     [rax+10h], rsi
0x140025c7b  mov     [rax+20h], r9
0x140025c7f  push    rdi
0x140025c80  push    r12
0x140025c82  push    r13
0x140025c84  push    r14
0x140025c86  push    r15
0x140025c88  sub     rsp, 70h
0x140025c8c  mov     r15d, r8d
0x140025c8f  mov     r14, rdx
0x140025c92  mov     dword ptr [rax-48h], 0
0x140025c99  xor     esi, esi
0x140025c9b  xor     edi, edi
0x140025c9d  mov     [rsp+98h+var_38], rdi
0x140025ca2  call    cs:__imp_ExGetPreviousMode
0x140025ca9  nop     dword ptr [rax+rax+00h]
0x140025cae  mov     r13b, al
0x140025cb1  lea     edx, [rsi+0Ch]
0x140025cb4  cmp     r15d, edx
0x140025cb7  jnb     short loc_140025D1C
0x140025cb9  mov     ebx, 0C000000Dh
0x140025cbe  lea     rcx, WPP_RECORDER_INITIALIZED
0x140025cc5  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140025ccc  jz      loc_1400260CA
0x140025cd2  lea     r9d, [rsi+0Ah]
0x140025cd6  mov     dword ptr [rsp+98h+var_58], edx
0x140025cda  mov     dword ptr [rsp+98h+var_60], r15d
0x140025cdf  mov     dword ptr [rsp+98h+var_68], 0A3h
0x140025ce7  lea     rax, aOnecoreBaseFsW_3; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140025cee  mov     [rsp+98h+var_70], rax
0x140025cf3  lea     rax, WPP_d5e84d3892ba3ffb3afa1607ae793b21_Traceguids
0x140025cfa  mov     [rsp+98h+var_78], rax
0x140025cff  mov     r8d, 3
0x140025d05  mov     dl, 2
0x140025d07  mov     rcx, cs:WPP_GLOBAL_Control
0x140025d0e  mov     rcx, [rcx+40h]
0x140025d12  call    WPP_RECORDER_SF_sDdd
0x140025d17  jmp     loc_1400260CA
0x140025d1c  mov     r12d, dword ptr [rsp+98h+Length]
0x140025d24  cmp     r12d, edx
0x140025d27  jnb     short loc_140025D5B
0x140025d29  mov     ebx, 0C000000Dh
0x140025d2e  lea     rcx, WPP_RECORDER_INITIALIZED
0x140025d35  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140025d3c  jz      loc_1400260CA
0x140025d42  mov     r9d, 0Bh
0x140025d48  mov     dword ptr [rsp+98h+var_58], edx
0x140025d4c  mov     dword ptr [rsp+98h+var_60], r12d
0x140025d51  mov     dword ptr [rsp+98h+var_68], 0A9h
0x140025d59  jmp     short loc_140025CE7
0x140025d5b  mov     [rsp+98h+arg_10], r13b
0x140025d63  mov     rbx, r15
0x140025d66  mov     r8d, 736D4642h
0x140025d6c  mov     rdx, r15
0x140025d6f  mov     ecx, 100h
0x140025d74  call    cs:__imp_ExAllocatePool2
0x140025d7b  nop     dword ptr [rax+rax+00h]
0x140025d80  mov     rsi, rax
0x140025d83  mov     [rsp+98h+var_30], rax
0x140025d88  test    rax, rax
0x140025d8b  jnz     short loc_140025DE7
0x140025d8d  mov     ebx, 0C000009Ah
0x140025d92  lea     rcx, WPP_RECORDER_INITIALIZED
0x140025d99  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140025da0  jz      loc_1400260CA
0x140025da6  lea     r9d, [rax+0Ch]
0x140025daa  mov     dword ptr [rsp+98h+var_68], 0B1h
0x140025db2  lea     rax, aOnecoreBaseFsW_3; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140025db9  mov     [rsp+98h+var_70], rax
0x140025dbe  lea     rax, WPP_d5e84d3892ba3ffb3afa1607ae793b21_Traceguids
0x140025dc5  mov     [rsp+98h+var_78], rax
0x140025dca  mov     r8d, 3
0x140025dd0  mov     dl, 2
0x140025dd2  mov     rcx, cs:WPP_GLOBAL_Control
0x140025dd9  mov     rcx, [rcx+40h]
0x140025ddd  call    WPP_RECORDER_SF_sD
0x140025de2  jmp     loc_1400260CA
0x140025de7  mov     edi, 1
0x140025dec  cmp     r13b, dil
0x140025def  jnz     short loc_140025E20
0x140025df1  mov     r8d, edi; Alignment
0x140025df4  mov     rdx, rbx; Length
0x140025df7  mov     rcx, r14; Address
0x140025dfa  call    cs:__imp_ProbeForRead
0x140025e01  nop     dword ptr [rax+rax+00h]
0x140025e06  mov     rdx, r12; Length
0x140025e09  mov     r8d, edi; Alignment
0x140025e0c  mov     rcx, [rsp+98h+Address]; Address
0x140025e14  call    cs:__imp_ProbeForWrite
0x140025e1b  nop     dword ptr [rax+rax+00h]
0x140025e20  mov     r8, rbx; Size
0x140025e23  mov     rdx, r14; Src
0x140025e26  mov     rcx, rsi; void *
0x140025e29  test    r13b, r13b
0x140025e2c  jz      short loc_140025E35
0x140025e2e  call    RtlCopyFromUser
0x140025e33  jmp     short loc_140025E3B
0x140025e35  call    RtlCopyVolatileMemory
0x140025e3a  nop
0x140025e3b  mov     r8d, 736D4642h
0x140025e41  mov     rdx, r12
0x140025e44  mov     ecx, 100h
0x140025e49  call    cs:__imp_ExAllocatePool2
0x140025e50  nop     dword ptr [rax+rax+00h]
0x140025e55  mov     rdi, rax
0x140025e58  mov     [rsp+98h+var_38], rax
0x140025e5d  test    rax, rax
0x140025e60  jnz     short loc_140025E8C
0x140025e62  mov     ebx, 0C000009Ah
0x140025e67  lea     rcx, WPP_RECORDER_INITIALIZED
0x140025e6e  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140025e75  jz      loc_1400260CA
0x140025e7b  lea     r9d, [rax+0Dh]
0x140025e7f  mov     dword ptr [rsp+98h+var_68], 0CFh
0x140025e87  jmp     loc_140025DB2
0x140025e8c  mov     edx, [rsi+4]
0x140025e8f  cmp     edx, r15d
0x140025e92  jz      short loc_140025EC9
0x140025e94  mov     ebx, 0C000000Dh
0x140025e99  lea     rcx, WPP_RECORDER_INITIALIZED
0x140025ea0  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140025ea7  jz      loc_1400260CA
0x140025ead  mov     r9d, 0Eh
0x140025eb3  mov     dword ptr [rsp+98h+var_58], edx
0x140025eb7  mov     dword ptr [rsp+98h+var_60], r15d
0x140025ebc  mov     dword ptr [rsp+98h+var_68], 0D7h
0x140025ec4  jmp     loc_140025CE7
0x140025ec9  xor     ebx, ebx
0x140025ecb  mov     edx, [rsi]
0x140025ecd  test    edx, edx
0x140025ecf  jz      loc_14002600F
0x140025ed5  cmp     edx, 2
0x140025ed8  jz      loc_140025FEE
0x140025ede  cmp     edx, 4
0x140025ee1  jz      loc_140025FCD
0x140025ee7  cmp     edx, 6
0x140025eea  jz      loc_140025FAC
0x140025ef0  cmp     edx, 8
0x140025ef3  jz      loc_140025F80
0x140025ef9  cmp     edx, 0Ah
0x140025efc  jz      short loc_140025F5C
0x140025efe  mov     ebx, 0C000000Dh
0x140025f03  lea     rcx, WPP_RECORDER_INITIALIZED
0x140025f0a  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140025f11  jz      loc_1400260CA
0x140025f17  mov     r9d, 1Bh
0x140025f1d  mov     dword ptr [rsp+98h+var_60], edx
0x140025f21  mov     dword ptr [rsp+98h+var_68], 1BFh
0x140025f29  lea     rax, aOnecoreBaseFsW_3; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140025f30  mov     [rsp+98h+var_70], rax
0x140025f35  lea     rax, WPP_d5e84d3892ba3ffb3afa1607ae793b21_Traceguids
0x140025f3c  mov     [rsp+98h+var_78], rax
0x140025f41  lea     r8d, [r9-18h]
0x140025f45  mov     dl, 2
0x140025f47  mov     rcx, cs:WPP_GLOBAL_Control
0x140025f4e  mov     rcx, [rcx+40h]
0x140025f52  call    WPP_RECORDER_SF_sDD
0x140025f57  jmp     loc_1400260CA
0x140025f5c  mov     dword ptr [rax], 0Bh
0x140025f62  mov     r15d, 0Ch
0x140025f68  mov     [rax+4], r15d
0x140025f6c  mov     edx, [rsi+4]
0x140025f6f  sub     edx, 8
0x140025f72  lea     rcx, [rsi+8]
0x140025f76  call    BfProcessTrackWritesRequest
0x140025f7b  jmp     loc_14002602E
0x140025f80  lea     rcx, [rsi+8]
0x140025f84  lea     r9, [rsp+98h+var_48]
0x140025f89  mov     r8, rdi
0x140025f8c  mov     edx, r12d
0x140025f8f  call    BfProcessGetMappingsRequest
0x140025f94  mov     [rdi+4], eax
0x140025f97  mov     ecx, [rsp+98h+var_48]
0x140025f9b  mov     [rdi], ecx
0x140025f9d  mov     rax, [rsp+98h+ReturnOutputBufferLength]
0x140025fa5  mov     [rax], ecx
0x140025fa7  jmp     loc_14002603C
0x140025fac  mov     dword ptr [rax], 7
0x140025fb2  mov     r15d, 0Ch
0x140025fb8  mov     [rax+4], r15d
0x140025fbc  mov     edx, [rsi+4]
0x140025fbf  sub     edx, 8
0x140025fc2  lea     rcx, [rsi+8]
0x140025fc6  call    BfRemoveBatchedVirtualizationMapping
0x140025fcb  jmp     short loc_14002602E
0x140025fcd  mov     dword ptr [rax], 5
0x140025fd3  mov     r15d, 0Ch
0x140025fd9  mov     [rax+4], r15d
0x140025fdd  mov     edx, [rsi+4]
0x140025fe0  sub     edx, 8
0x140025fe3  lea     rcx, [rsi+8]
0x140025fe7  call    BfStoreBatchedVirtualizationMapping
0x140025fec  jmp     short loc_14002602E
0x140025fee  mov     dword ptr [rax], 3
0x140025ff4  mov     r15d, 0Ch
0x140025ffa  mov     [rax+4], r15d
0x140025ffe  mov     edx, [rsi+4]
0x140026001  sub     edx, 8
0x140026004  lea     rcx, [rsi+8]
0x140026008  call    BfRemoveVirtualizationMapping
0x14002600d  jmp     short loc_14002602E
0x14002600f  mov     dword ptr [rax], 1
0x140026015  mov     r15d, 0Ch
0x14002601b  mov     [rax+4], r15d
0x14002601f  mov     edx, [rsi+4]
0x140026022  sub     edx, 8
0x140026025  lea     rcx, [rsi+8]
0x140026029  call    BfStoreVirtualizationMapping
0x14002602e  mov     [rdi+8], eax
0x140026031  mov     rax, [rsp+98h+ReturnOutputBufferLength]
0x140026039  mov     [rax], r15d
0x14002603c  mov     r8, r12; Size
0x14002603f  mov     rdx, rdi; Src
0x140026042  mov     rcx, [rsp+98h+Address]; void *
0x14002604a  test    r13b, r13b
0x14002604d  jz      short loc_140026056
0x14002604f  call    RtlCopyToUser
0x140026054  jmp     short loc_14002605B
0x140026056  call    RtlCopyVolatileMemory
0x14002605b  jmp     short loc_1400260CA
0x14002605d  mov     ebx, eax
0x14002605f  lea     rcx, WPP_RECORDER_INITIALIZED
0x140026066  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002606d  jz      short loc_1400260AF
0x14002606f  mov     r9d, 1Ch
0x140026075  mov     dword ptr [rsp+98h+var_60], eax
0x140026079  mov     dword ptr [rsp+98h+var_68], 1CAh
0x140026081  lea     rax, aOnecoreBaseFsW_3; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140026088  mov     [rsp+98h+var_70], rax
0x14002608d  lea     rax, WPP_d5e84d3892ba3ffb3afa1607ae793b21_Traceguids
0x140026094  mov     [rsp+98h+var_78], rax
0x140026099  lea     r8d, [r9-19h]
0x14002609d  mov     dl, 2
0x14002609f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400260a6  mov     rcx, [rcx+40h]
0x1400260aa  call    WPP_RECORDER_SF_sDD
0x1400260af  mov     rsi, [rsp+98h+var_30]
0x1400260b4  mov     rdi, [rsp+98h+var_38]
0x1400260b9  jmp     short loc_1400260CA
0x1400260bb  mov     ebx, 0C0000005h
0x1400260c0  mov     rsi, [rsp+98h+var_30]
0x1400260c5  mov     rdi, [rsp+98h+var_38]
0x1400260ca  test    rsi, rsi
0x1400260cd  jz      short loc_1400260E3
0x1400260cf  mov     edx, 736D4642h; Tag
0x1400260d4  mov     rcx, rsi; P
0x1400260d7  call    cs:__imp_ExFreePoolWithTag
0x1400260de  nop     dword ptr [rax+rax+00h]
0x1400260e3  test    rdi, rdi
0x1400260e6  jz      short loc_1400260FC
0x1400260e8  mov     edx, 736D4642h; Tag
0x1400260ed  mov     rcx, rdi; P
0x1400260f0  call    cs:__imp_ExFreePoolWithTag
0x1400260f7  nop     dword ptr [rax+rax+00h]
0x1400260fc  mov     eax, ebx
0x1400260fe  lea     r11, [rsp+98h+var_28]
0x140026103  mov     rbx, [r11+30h]
0x140026107  mov     rsi, [r11+38h]
0x14002610b  mov     rsp, r11
0x14002610e  pop     r15
0x140026110  pop     r14
0x140026112  pop     r13
0x140026114  pop     r12
0x140026116  pop     rdi
0x140026117  retn
0x14002619d  push    rbp
0x14002619f  sub     rsp, 50h
0x1400261a3  mov     rbp, rdx
0x1400261a6  xor     eax, eax
0x1400261a8  cmp     [rbp+0B0h], al
0x1400261ae  setnz   al
0x1400261b1  mov     [rbp+58h], eax
0x1400261b4  mov     eax, [rbp+58h]
0x1400261b7  add     rsp, 50h
0x1400261bb  pop     rbp
0x1400261bc  retn
0x1400261be  push    rbp
0x1400261c0  sub     rsp, 50h
0x1400261c4  mov     rbp, rdx
0x1400261c7  xor     eax, eax
0x1400261c9  cmp     [rbp+0B0h], al
0x1400261cf  setnz   al
0x1400261d2  mov     [rbp+54h], eax
0x1400261d5  mov     eax, [rbp+54h]
0x1400261d8  add     rsp, 50h
0x1400261dc  pop     rbp
0x1400261dd  retn
```
