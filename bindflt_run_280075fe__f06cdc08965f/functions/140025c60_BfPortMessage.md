# BfPortMessage

- ea: `0x140025c60`
- end: `0x140026109`
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
- `0x140024384`
- `0x140025c60`

## import_xrefs

- `ntoskrnl!ExGetPreviousMode` at `0x140025c92`
- `ntoskrnl!ExGetPreviousMode` at `0x140025c92`
- `ntoskrnl!ProbeForWrite` at `0x140025e04`
- `ntoskrnl!ProbeForWrite` at `0x140025e04`
- `ntoskrnl!ProbeForRead` at `0x140025dea`
- `ntoskrnl!ProbeForRead` at `0x140025dea`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400260c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400260e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400260c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400260e0`
- `ntoskrnl!ExAllocatePool2` at `0x140025d64`
- `ntoskrnl!ExAllocatePool2` at `0x140025e39`
- `ntoskrnl!ExAllocatePool2` at `0x140025d64`
- `ntoskrnl!ExAllocatePool2` at `0x140025e39`

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
  KPROCESSOR_MODE PreviousMode; // r13
  int v11; // edx
  unsigned int v12; // ebx
  int v13; // r9d
  int v14; // edx
  int v15; // r9d
  ULONG *v16; // rax
  int v17; // edx
  ULONG v18; // eax
  ULONG v19; // ecx
  char v21; // [rsp+30h] [rbp-68h]
  char v22; // [rsp+30h] [rbp-68h]
  char v23; // [rsp+38h] [rbp-60h]
  char v24; // [rsp+40h] [rbp-58h]
  ULONG v25[4]; // [rsp+50h] [rbp-48h] BYREF
  ULONG *v26; // [rsp+60h] [rbp-38h]
  _DWORD *v27; // [rsp+68h] [rbp-30h]

  v6 = InputBufferLength;
  v25[0] = 0;
  Pool2 = 0;
  v9 = 0;
  v26 = 0;
  PreviousMode = ExGetPreviousMode();
  v11 = 12;
  if ( (unsigned int)v6 < 0xC )
  {
    v12 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_41;
    v13 = 10;
    v24 = 12;
    v23 = v6;
    v21 = -93;
    goto LABEL_4;
  }
  if ( OutputBufferLength < 0xC )
  {
    v12 = -1073741811;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v13 = 11;
      v24 = 12;
      v23 = OutputBufferLength;
      v21 = -87;
LABEL_4:
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_sDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        3,
        v13,
        (__int64)WPP_d5e84d3892ba3ffb3afa1607ae793b21_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\message.c",
        v21,
        v23,
        v24);
      goto LABEL_41;
    }
    goto LABEL_41;
  }
  Pool2 = (_DWORD *)ExAllocatePool2(256, v6, 1936541250);
  v27 = Pool2;
  if ( !Pool2 )
  {
    v12 = -1073741670;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_41;
    v15 = 12;
    v22 = -79;
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
  v16 = (ULONG *)ExAllocatePool2(256, OutputBufferLength, 1936541250);
  v9 = v16;
  v26 = v16;
  if ( !v16 )
  {
    v12 = -1073741670;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_41;
    v15 = 13;
    v22 = -49;
LABEL_11:
    LOBYTE(v14) = 2;
    WPP_RECORDER_SF_sD(
      WPP_GLOBAL_Control->DeviceExtension,
      v14,
      3,
      v15,
      (__int64)WPP_d5e84d3892ba3ffb3afa1607ae793b21_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\message.c",
      v22);
    goto LABEL_41;
  }
  v11 = Pool2[1];
  if ( v11 == (_DWORD)v6 )
  {
    v12 = 0;
    v17 = *Pool2;
    if ( *Pool2 )
    {
      switch ( v17 )
      {
        case 2:
          *v16 = 3;
          v16[1] = 12;
          v18 = BfRemoveVirtualizationMapping(Pool2 + 2, (unsigned int)(Pool2[1] - 8));
          break;
        case 4:
          *v16 = 5;
          v16[1] = 12;
          v18 = BfStoreBatchedVirtualizationMapping((__int64)(Pool2 + 2), Pool2[1] - 8);
          break;
        case 6:
          *v16 = 7;
          v16[1] = 12;
          v18 = BfRemoveBatchedVirtualizationMapping(Pool2 + 2, (unsigned int)(Pool2[1] - 8));
          break;
        case 8:
          v16[1] = BfProcessGetMappingsRequest(Pool2 + 2, OutputBufferLength, v16, v25);
          v19 = v25[0];
          *v9 = v25[0];
          *ReturnOutputBufferLength = v19;
          goto LABEL_38;
        case 10:
          *v16 = 11;
          v16[1] = 12;
          v18 = BfProcessTrackWritesRequest(Pool2 + 2, (unsigned int)(Pool2[1] - 8));
          break;
        default:
          v12 = -1073741811;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v17) = 2;
            WPP_RECORDER_SF_sDD(
              WPP_GLOBAL_Control->DeviceExtension,
              v17,
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
      *v16 = 1;
      v16[1] = 12;
      v18 = BfStoreVirtualizationMapping(Pool2 + 2, (unsigned int)(Pool2[1] - 8));
    }
    v9[2] = v18;
    *ReturnOutputBufferLength = 12;
LABEL_38:
    if ( PreviousMode )
      RtlCopyToUser(OutputBuffer, v9, OutputBufferLength);
    else
      RtlCopyVolatileMemory(OutputBuffer, v9, OutputBufferLength);
    goto LABEL_41;
  }
  v12 = -1073741811;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v13 = 14;
    v24 = Pool2[1];
    v23 = v6;
    v21 = -41;
    goto LABEL_4;
  }
LABEL_41:
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x736D4642u);
  if ( v9 )
    ExFreePoolWithTag(v9, 0x736D4642u);
  return v12;
}

```

## disassembly

```asm
0x140025c60  mov     rax, rsp
0x140025c63  mov     [rax+8], rbx
0x140025c67  mov     [rax+10h], rsi
0x140025c6b  mov     [rax+20h], r9
0x140025c6f  push    rdi
0x140025c70  push    r12
0x140025c72  push    r13
0x140025c74  push    r14
0x140025c76  push    r15
0x140025c78  sub     rsp, 70h
0x140025c7c  mov     r15d, r8d
0x140025c7f  mov     r14, rdx
0x140025c82  mov     dword ptr [rax-48h], 0
0x140025c89  xor     esi, esi
0x140025c8b  xor     edi, edi
0x140025c8d  mov     [rsp+98h+var_38], rdi
0x140025c92  call    cs:__imp_ExGetPreviousMode
0x140025c99  nop     dword ptr [rax+rax+00h]
0x140025c9e  mov     r13b, al
0x140025ca1  lea     edx, [rsi+0Ch]
0x140025ca4  cmp     r15d, edx
0x140025ca7  jnb     short loc_140025D0C
0x140025ca9  mov     ebx, 0C000000Dh
0x140025cae  lea     rcx, WPP_RECORDER_INITIALIZED
0x140025cb5  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140025cbc  jz      loc_1400260BA
0x140025cc2  lea     r9d, [rsi+0Ah]
0x140025cc6  mov     dword ptr [rsp+98h+var_58], edx
0x140025cca  mov     dword ptr [rsp+98h+var_60], r15d
0x140025ccf  mov     dword ptr [rsp+98h+var_68], 0A3h
0x140025cd7  lea     rax, aOnecoreBaseFsW_3; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140025cde  mov     [rsp+98h+var_70], rax
0x140025ce3  lea     rax, WPP_d5e84d3892ba3ffb3afa1607ae793b21_Traceguids
0x140025cea  mov     [rsp+98h+var_78], rax
0x140025cef  mov     r8d, 3
0x140025cf5  mov     dl, 2
0x140025cf7  mov     rcx, cs:WPP_GLOBAL_Control
0x140025cfe  mov     rcx, [rcx+40h]
0x140025d02  call    WPP_RECORDER_SF_sDdd
0x140025d07  jmp     loc_1400260BA
0x140025d0c  mov     r12d, dword ptr [rsp+98h+Length]
0x140025d14  cmp     r12d, edx
0x140025d17  jnb     short loc_140025D4B
0x140025d19  mov     ebx, 0C000000Dh
0x140025d1e  lea     rcx, WPP_RECORDER_INITIALIZED
0x140025d25  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140025d2c  jz      loc_1400260BA
0x140025d32  mov     r9d, 0Bh
0x140025d38  mov     dword ptr [rsp+98h+var_58], edx
0x140025d3c  mov     dword ptr [rsp+98h+var_60], r12d
0x140025d41  mov     dword ptr [rsp+98h+var_68], 0A9h
0x140025d49  jmp     short loc_140025CD7
0x140025d4b  mov     [rsp+98h+arg_10], r13b
0x140025d53  mov     rbx, r15
0x140025d56  mov     r8d, 736D4642h
0x140025d5c  mov     rdx, r15
0x140025d5f  mov     ecx, 100h
0x140025d64  call    cs:__imp_ExAllocatePool2
0x140025d6b  nop     dword ptr [rax+rax+00h]
0x140025d70  mov     rsi, rax
0x140025d73  mov     [rsp+98h+var_30], rax
0x140025d78  test    rax, rax
0x140025d7b  jnz     short loc_140025DD7
0x140025d7d  mov     ebx, 0C000009Ah
0x140025d82  lea     rcx, WPP_RECORDER_INITIALIZED
0x140025d89  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140025d90  jz      loc_1400260BA
0x140025d96  lea     r9d, [rax+0Ch]
0x140025d9a  mov     dword ptr [rsp+98h+var_68], 0B1h
0x140025da2  lea     rax, aOnecoreBaseFsW_3; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140025da9  mov     [rsp+98h+var_70], rax
0x140025dae  lea     rax, WPP_d5e84d3892ba3ffb3afa1607ae793b21_Traceguids
0x140025db5  mov     [rsp+98h+var_78], rax
0x140025dba  mov     r8d, 3
0x140025dc0  mov     dl, 2
0x140025dc2  mov     rcx, cs:WPP_GLOBAL_Control
0x140025dc9  mov     rcx, [rcx+40h]
0x140025dcd  call    WPP_RECORDER_SF_sD
0x140025dd2  jmp     loc_1400260BA
0x140025dd7  mov     edi, 1
0x140025ddc  cmp     r13b, dil
0x140025ddf  jnz     short loc_140025E10
0x140025de1  mov     r8d, edi; Alignment
0x140025de4  mov     rdx, rbx; Length
0x140025de7  mov     rcx, r14; Address
0x140025dea  call    cs:__imp_ProbeForRead
0x140025df1  nop     dword ptr [rax+rax+00h]
0x140025df6  mov     rdx, r12; Length
0x140025df9  mov     r8d, edi; Alignment
0x140025dfc  mov     rcx, [rsp+98h+Address]; Address
0x140025e04  call    cs:__imp_ProbeForWrite
0x140025e0b  nop     dword ptr [rax+rax+00h]
0x140025e10  mov     r8, rbx; Size
0x140025e13  mov     rdx, r14; Src
0x140025e16  mov     rcx, rsi; void *
0x140025e19  test    r13b, r13b
0x140025e1c  jz      short loc_140025E25
0x140025e1e  call    RtlCopyFromUser
0x140025e23  jmp     short loc_140025E2B
0x140025e25  call    RtlCopyVolatileMemory
0x140025e2a  nop
0x140025e2b  mov     r8d, 736D4642h
0x140025e31  mov     rdx, r12
0x140025e34  mov     ecx, 100h
0x140025e39  call    cs:__imp_ExAllocatePool2
0x140025e40  nop     dword ptr [rax+rax+00h]
0x140025e45  mov     rdi, rax
0x140025e48  mov     [rsp+98h+var_38], rax
0x140025e4d  test    rax, rax
0x140025e50  jnz     short loc_140025E7C
0x140025e52  mov     ebx, 0C000009Ah
0x140025e57  lea     rcx, WPP_RECORDER_INITIALIZED
0x140025e5e  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140025e65  jz      loc_1400260BA
0x140025e6b  lea     r9d, [rax+0Dh]
0x140025e6f  mov     dword ptr [rsp+98h+var_68], 0CFh
0x140025e77  jmp     loc_140025DA2
0x140025e7c  mov     edx, [rsi+4]
0x140025e7f  cmp     edx, r15d
0x140025e82  jz      short loc_140025EB9
0x140025e84  mov     ebx, 0C000000Dh
0x140025e89  lea     rcx, WPP_RECORDER_INITIALIZED
0x140025e90  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140025e97  jz      loc_1400260BA
0x140025e9d  mov     r9d, 0Eh
0x140025ea3  mov     dword ptr [rsp+98h+var_58], edx
0x140025ea7  mov     dword ptr [rsp+98h+var_60], r15d
0x140025eac  mov     dword ptr [rsp+98h+var_68], 0D7h
0x140025eb4  jmp     loc_140025CD7
0x140025eb9  xor     ebx, ebx
0x140025ebb  mov     edx, [rsi]
0x140025ebd  test    edx, edx
0x140025ebf  jz      loc_140025FFF
0x140025ec5  cmp     edx, 2
0x140025ec8  jz      loc_140025FDE
0x140025ece  cmp     edx, 4
0x140025ed1  jz      loc_140025FBD
0x140025ed7  cmp     edx, 6
0x140025eda  jz      loc_140025F9C
0x140025ee0  cmp     edx, 8
0x140025ee3  jz      loc_140025F70
0x140025ee9  cmp     edx, 0Ah
0x140025eec  jz      short loc_140025F4C
0x140025eee  mov     ebx, 0C000000Dh
0x140025ef3  lea     rcx, WPP_RECORDER_INITIALIZED
0x140025efa  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140025f01  jz      loc_1400260BA
0x140025f07  mov     r9d, 1Bh
0x140025f0d  mov     dword ptr [rsp+98h+var_60], edx
0x140025f11  mov     dword ptr [rsp+98h+var_68], 1BFh
0x140025f19  lea     rax, aOnecoreBaseFsW_3; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140025f20  mov     [rsp+98h+var_70], rax
0x140025f25  lea     rax, WPP_d5e84d3892ba3ffb3afa1607ae793b21_Traceguids
0x140025f2c  mov     [rsp+98h+var_78], rax
0x140025f31  lea     r8d, [r9-18h]
0x140025f35  mov     dl, 2
0x140025f37  mov     rcx, cs:WPP_GLOBAL_Control
0x140025f3e  mov     rcx, [rcx+40h]
0x140025f42  call    WPP_RECORDER_SF_sDD
0x140025f47  jmp     loc_1400260BA
0x140025f4c  mov     dword ptr [rax], 0Bh
0x140025f52  mov     r15d, 0Ch
0x140025f58  mov     [rax+4], r15d
0x140025f5c  mov     edx, [rsi+4]
0x140025f5f  sub     edx, 8
0x140025f62  lea     rcx, [rsi+8]
0x140025f66  call    BfProcessTrackWritesRequest
0x140025f6b  jmp     loc_14002601E
0x140025f70  lea     rcx, [rsi+8]
0x140025f74  lea     r9, [rsp+98h+var_48]
0x140025f79  mov     r8, rdi
0x140025f7c  mov     edx, r12d
0x140025f7f  call    BfProcessGetMappingsRequest
0x140025f84  mov     [rdi+4], eax
0x140025f87  mov     ecx, [rsp+98h+var_48]
0x140025f8b  mov     [rdi], ecx
0x140025f8d  mov     rax, [rsp+98h+ReturnOutputBufferLength]
0x140025f95  mov     [rax], ecx
0x140025f97  jmp     loc_14002602C
0x140025f9c  mov     dword ptr [rax], 7
0x140025fa2  mov     r15d, 0Ch
0x140025fa8  mov     [rax+4], r15d
0x140025fac  mov     edx, [rsi+4]
0x140025faf  sub     edx, 8
0x140025fb2  lea     rcx, [rsi+8]
0x140025fb6  call    BfRemoveBatchedVirtualizationMapping
0x140025fbb  jmp     short loc_14002601E
0x140025fbd  mov     dword ptr [rax], 5
0x140025fc3  mov     r15d, 0Ch
0x140025fc9  mov     [rax+4], r15d
0x140025fcd  mov     edx, [rsi+4]
0x140025fd0  sub     edx, 8
0x140025fd3  lea     rcx, [rsi+8]
0x140025fd7  call    BfStoreBatchedVirtualizationMapping
0x140025fdc  jmp     short loc_14002601E
0x140025fde  mov     dword ptr [rax], 3
0x140025fe4  mov     r15d, 0Ch
0x140025fea  mov     [rax+4], r15d
0x140025fee  mov     edx, [rsi+4]
0x140025ff1  sub     edx, 8
0x140025ff4  lea     rcx, [rsi+8]
0x140025ff8  call    BfRemoveVirtualizationMapping
0x140025ffd  jmp     short loc_14002601E
0x140025fff  mov     dword ptr [rax], 1
0x140026005  mov     r15d, 0Ch
0x14002600b  mov     [rax+4], r15d
0x14002600f  mov     edx, [rsi+4]
0x140026012  sub     edx, 8
0x140026015  lea     rcx, [rsi+8]
0x140026019  call    BfStoreVirtualizationMapping
0x14002601e  mov     [rdi+8], eax
0x140026021  mov     rax, [rsp+98h+ReturnOutputBufferLength]
0x140026029  mov     [rax], r15d
0x14002602c  mov     r8, r12; Size
0x14002602f  mov     rdx, rdi; Src
0x140026032  mov     rcx, [rsp+98h+Address]; void *
0x14002603a  test    r13b, r13b
0x14002603d  jz      short loc_140026046
0x14002603f  call    RtlCopyToUser
0x140026044  jmp     short loc_14002604B
0x140026046  call    RtlCopyVolatileMemory
0x14002604b  jmp     short loc_1400260BA
0x14002604d  mov     ebx, eax
0x14002604f  lea     rcx, WPP_RECORDER_INITIALIZED
0x140026056  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14002605d  jz      short loc_14002609F
0x14002605f  mov     r9d, 1Ch
0x140026065  mov     dword ptr [rsp+98h+var_60], eax
0x140026069  mov     dword ptr [rsp+98h+var_68], 1CAh
0x140026071  lea     rax, aOnecoreBaseFsW_3; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140026078  mov     [rsp+98h+var_70], rax
0x14002607d  lea     rax, WPP_d5e84d3892ba3ffb3afa1607ae793b21_Traceguids
0x140026084  mov     [rsp+98h+var_78], rax
0x140026089  lea     r8d, [r9-19h]
0x14002608d  mov     dl, 2
0x14002608f  mov     rcx, cs:WPP_GLOBAL_Control
0x140026096  mov     rcx, [rcx+40h]
0x14002609a  call    WPP_RECORDER_SF_sDD
0x14002609f  mov     rsi, [rsp+98h+var_30]
0x1400260a4  mov     rdi, [rsp+98h+var_38]
0x1400260a9  jmp     short loc_1400260BA
0x1400260ab  mov     ebx, 0C0000005h
0x1400260b0  mov     rsi, [rsp+98h+var_30]
0x1400260b5  mov     rdi, [rsp+98h+var_38]
0x1400260ba  test    rsi, rsi
0x1400260bd  jz      short loc_1400260D3
0x1400260bf  mov     edx, 736D4642h; Tag
0x1400260c4  mov     rcx, rsi; P
0x1400260c7  call    cs:__imp_ExFreePoolWithTag
0x1400260ce  nop     dword ptr [rax+rax+00h]
0x1400260d3  test    rdi, rdi
0x1400260d6  jz      short loc_1400260EC
0x1400260d8  mov     edx, 736D4642h; Tag
0x1400260dd  mov     rcx, rdi; P
0x1400260e0  call    cs:__imp_ExFreePoolWithTag
0x1400260e7  nop     dword ptr [rax+rax+00h]
0x1400260ec  mov     eax, ebx
0x1400260ee  lea     r11, [rsp+98h+var_28]
0x1400260f3  mov     rbx, [r11+30h]
0x1400260f7  mov     rsi, [r11+38h]
0x1400260fb  mov     rsp, r11
0x1400260fe  pop     r15
0x140026100  pop     r14
0x140026102  pop     r13
0x140026104  pop     r12
0x140026106  pop     rdi
0x140026107  retn
0x14002618d  push    rbp
0x14002618f  sub     rsp, 50h
0x140026193  mov     rbp, rdx
0x140026196  xor     eax, eax
0x140026198  cmp     [rbp+0B0h], al
0x14002619e  setnz   al
0x1400261a1  mov     [rbp+58h], eax
0x1400261a4  mov     eax, [rbp+58h]
0x1400261a7  add     rsp, 50h
0x1400261ab  pop     rbp
0x1400261ac  retn
0x1400261ae  push    rbp
0x1400261b0  sub     rsp, 50h
0x1400261b4  mov     rbp, rdx
0x1400261b7  xor     eax, eax
0x1400261b9  cmp     [rbp+0B0h], al
0x1400261bf  setnz   al
0x1400261c2  mov     [rbp+54h], eax
0x1400261c5  mov     eax, [rbp+54h]
0x1400261c8  add     rsp, 50h
0x1400261cc  pop     rbp
0x1400261cd  retn
```
