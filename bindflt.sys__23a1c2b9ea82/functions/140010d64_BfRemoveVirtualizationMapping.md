# BfRemoveVirtualizationMapping

- ea: `0x140010d64`
- end: `0x14001125d`
- name: `BfRemoveVirtualizationMapping`
- size: `1273`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x140025c70`

## callees

- `0x140001348`
- `0x140003140`
- `0x140003304`
- `0x14000f008`
- `0x140010d64`
- `0x140011264`
- `0x14001fb68`
- `0x140021b60`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140010ee5`
- `ntoskrnl!ExAcquireFastMutex` at `0x140010ee5`
- `ntoskrnl!ExReleaseFastMutex` at `0x140010efd`
- `ntoskrnl!ExReleaseFastMutex` at `0x140010f61`
- `ntoskrnl!ExReleaseFastMutex` at `0x140010efd`
- `ntoskrnl!ExReleaseFastMutex` at `0x140010f61`
- `ntoskrnl!PsGetCurrentSilo` at `0x140010d9a`
- `ntoskrnl!PsGetCurrentSilo` at `0x140010d9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011232`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011232`
- `ntoskrnl!PsIsHostSilo` at `0x140010da9`
- `ntoskrnl!PsIsHostSilo` at `0x140010da9`
- `FLTMGR!FltAcquireResourceExclusive` at `0x14001119b`
- `FLTMGR!FltAcquireResourceExclusive` at `0x14001119b`
- `FLTMGR!FltReleaseResource` at `0x140011219`
- `FLTMGR!FltReleaseResource` at `0x140011219`

## pseudocode

```c
__int64 __fastcall BfRemoveVirtualizationMapping(__int64 a1, unsigned int a2)
{
  __int64 CurrentSilo; // rax
  int v5; // edx
  int InstanceTierNode; // ebx
  int v7; // edx
  int v8; // edx
  __int64 v9; // r14
  __int16 v10; // cx
  __int16 v11; // ax
  __int64 v12; // r15
  __int64 v13; // rax
  int v14; // eax
  int v15; // edx
  _WORD *v16; // rsi
  int v17; // r9d
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // rdi
  int v21; // edx
  char v23; // [rsp+30h] [rbp-29h]
  int v24; // [rsp+38h] [rbp-21h]
  __int64 v25; // [rsp+50h] [rbp-9h] BYREF
  __int64 v26; // [rsp+58h] [rbp-1h] BYREF
  __int128 v27; // [rsp+60h] [rbp+7h] BYREF
  __int128 v28; // [rsp+70h] [rbp+17h] BYREF
  _QWORD v29[2]; // [rsp+80h] [rbp+27h] BYREF
  __int64 v30; // [rsp+D0h] [rbp+77h] BYREF
  PVOID P; // [rsp+D8h] [rbp+7Fh] BYREF

  v25 = 0;
  v26 = 0;
  v30 = 0;
  P = 0;
  CurrentSilo = PsGetCurrentSilo();
  if ( !(unsigned __int8)PsIsHostSilo(CurrentSilo) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 2;
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        6,
        186,
        (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
        151);
    }
    return (unsigned int)-1073741790;
  }
  if ( a2 < 0x28 )
  {
    InstanceTierNode = -1073741811;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 2;
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        6,
        187,
        (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
        163);
    }
    return (unsigned int)InstanceTierNode;
  }
  if ( *(_DWORD *)a1 > a2 )
  {
    InstanceTierNode = -1073741811;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 2;
      WPP_RECORDER_SF_sDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        6,
        188,
        (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
        170,
        *(_DWORD *)a1,
        a2);
    }
    return (unsigned int)InstanceTierNode;
  }
  ExAcquireFastMutex(&FastMutex);
  if ( byte_14000B1C0 )
  {
    ExReleaseFastMutex(&FastMutex);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        6,
        189,
        (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
        184);
    }
    return (unsigned int)-1073741637;
  }
  ExReleaseFastMutex(&FastMutex);
  InstanceTierNode = BfpValidateVirtualizationRoot(a1, a1 + 32, a2, &v30);
  if ( InstanceTierNode < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        3,
        190,
        (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
        198,
        InstanceTierNode);
    }
    return (unsigned int)InstanceTierNode;
  }
  v9 = v30;
  v10 = *(_WORD *)(a1 + 24);
  v28 = 0;
  v11 = *(_WORD *)(v30 + 4);
  v12 = v30 + 6;
  *((_QWORD *)&v28 + 1) = v30 + 6;
  LOWORD(v28) = v11;
  WORD1(v28) = v11;
  v27 = 0;
  if ( v10 )
  {
    v13 = *(unsigned int *)(a1 + 28);
    LOWORD(v27) = v10;
    *((_QWORD *)&v27 + 1) = a1 + v13;
    WORD1(v27) = v10;
  }
  v14 = BfpInitializeContainerRootId(
          (unsigned int)&v28,
          0,
          *(unsigned __int16 *)(v30 + 2),
          (unsigned int)&v27,
          (__int64)&P);
  v16 = P;
  InstanceTierNode = v14;
  if ( v14 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_37;
    v24 = v14;
    v17 = 191;
    v23 = -38;
    goto LABEL_23;
  }
  if ( *((_WORD *)P + ((unsigned __int64)*((unsigned __int16 *)P + 2) >> 1) + 2) == 92 )
  {
    *((_WORD *)P + 2) -= 2;
    *v16 -= 2;
  }
  v18 = *(_QWORD *)(a1 + 16);
  v19 = *(_QWORD *)(a1 + 8);
  v29[0] = 0;
  v29[1] = v12;
  LOWORD(v29[0]) = *(_WORD *)(v9 + 2);
  WORD1(v29[0]) = v29[0];
  InstanceTierNode = BfpGetInstanceTierNode((unsigned int)v29, v19, v18, 0, 0, (__int64)&v25, (__int64)&v26);
  if ( InstanceTierNode == -1073741275 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v15) = 2;
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        v15,
        8,
        192,
        (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
        1);
    }
    InstanceTierNode = -1073741811;
    goto LABEL_37;
  }
  if ( InstanceTierNode >= 0 )
  {
    v20 = v25;
    FltAcquireResourceExclusive((PERESOURCE)(v25 + 16));
    InstanceTierNode = BfpExecuteCallbackOnVirtualizationRootNode(v26, v16, BfpRemoveMapping, 0);
    if ( InstanceTierNode < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v21) = 2;
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v21,
        6,
        194,
        (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
        22,
        InstanceTierNode);
    }
    FltReleaseResource((PERESOURCE)(v20 + 16));
    goto LABEL_37;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v24 = InstanceTierNode;
    v17 = 193;
    v23 = 7;
LABEL_23:
    LOBYTE(v15) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v15,
      6,
      v17,
      (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
      v23,
      v24);
  }
LABEL_37:
  if ( v16 )
    ExFreePoolWithTag(v16, 0x706D4642u);
  return (unsigned int)InstanceTierNode;
}

```

## disassembly

```asm
0x140010d64  mov     [rsp-8+arg_0], rbx
0x140010d69  mov     [rsp-8+arg_8], rsi
0x140010d6e  push    rbp
0x140010d6f  push    rdi
0x140010d70  push    r12
0x140010d72  push    r14
0x140010d74  push    r15
0x140010d76  lea     rbp, [rsp-37h]
0x140010d7b  sub     rsp, 90h
0x140010d82  xor     r12d, r12d
0x140010d85  mov     esi, edx
0x140010d87  mov     [rbp+57h+var_60], r12
0x140010d8b  mov     rdi, rcx
0x140010d8e  mov     [rbp+57h+var_58], r12
0x140010d92  mov     [rbp+57h+arg_10], r12
0x140010d96  mov     [rbp+57h+P], r12
0x140010d9a  call    cs:__imp_PsGetCurrentSilo
0x140010da1  nop     dword ptr [rax+rax+00h]
0x140010da6  mov     rcx, rax
0x140010da9  call    cs:__imp_PsIsHostSilo
0x140010db0  nop     dword ptr [rax+rax+00h]
0x140010db5  test    al, al
0x140010db7  jnz     short loc_140010E10
0x140010db9  lea     rax, WPP_RECORDER_INITIALIZED
0x140010dc0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010dc7  jz      short loc_140010E06
0x140010dc9  mov     rcx, cs:WPP_GLOBAL_Control
0x140010dd0  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140010dd7  mov     dword ptr [rsp+0B0h+var_80], 1997h
0x140010ddf  lea     r8d, [r12+6]
0x140010de4  mov     [rsp+0B0h+var_88], rax
0x140010de9  mov     r9d, 0BAh
0x140010def  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x140010df6  mov     dl, 2
0x140010df8  mov     rcx, [rcx+40h]
0x140010dfc  mov     [rsp+0B0h+var_90], rax
0x140010e01  call    WPP_RECORDER_SF_sD
0x140010e06  mov     ebx, 0C0000022h
0x140010e0b  jmp     loc_14001123E
0x140010e10  cmp     esi, 28h ; '('
0x140010e13  jnb     short loc_140010E71
0x140010e15  mov     ebx, 0C000000Dh
0x140010e1a  lea     rax, WPP_RECORDER_INITIALIZED
0x140010e21  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010e28  jz      loc_14001123E
0x140010e2e  mov     rcx, cs:WPP_GLOBAL_Control
0x140010e35  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140010e3c  mov     dword ptr [rsp+0B0h+var_80], 19A3h
0x140010e44  mov     r9d, 0BBh
0x140010e4a  mov     [rsp+0B0h+var_88], rax
0x140010e4f  mov     r8d, 6
0x140010e55  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x140010e5c  mov     dl, 2
0x140010e5e  mov     rcx, [rcx+40h]
0x140010e62  mov     [rsp+0B0h+var_90], rax
0x140010e67  call    WPP_RECORDER_SF_sD
0x140010e6c  jmp     loc_14001123E
0x140010e71  mov     ecx, [rdi]
0x140010e73  cmp     ecx, esi
0x140010e75  jbe     short loc_140010EDB
0x140010e77  mov     ebx, 0C000000Dh
0x140010e7c  lea     rax, WPP_RECORDER_INITIALIZED
0x140010e83  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010e8a  jz      loc_14001123E
0x140010e90  mov     [rsp+0B0h+var_70], esi
0x140010e94  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140010e9b  mov     [rsp+0B0h+var_78], ecx
0x140010e9f  mov     r9d, 0BCh
0x140010ea5  mov     rcx, cs:WPP_GLOBAL_Control
0x140010eac  mov     r8d, 6
0x140010eb2  mov     dword ptr [rsp+0B0h+var_80], 19AAh
0x140010eba  mov     dl, 2
0x140010ebc  mov     [rsp+0B0h+var_88], rax
0x140010ec1  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x140010ec8  mov     [rsp+0B0h+var_90], rax
0x140010ecd  mov     rcx, [rcx+40h]
0x140010ed1  call    WPP_RECORDER_SF_sDdd
0x140010ed6  jmp     loc_14001123E
0x140010edb  lea     rbx, FastMutex
0x140010ee2  mov     rcx, rbx; FastMutex
0x140010ee5  call    cs:__imp_ExAcquireFastMutex
0x140010eec  nop     dword ptr [rax+rax+00h]
0x140010ef1  cmp     cs:byte_14000B1C0, r12b
0x140010ef8  mov     rcx, rbx; FastMutex
0x140010efb  jz      short loc_140010F61
0x140010efd  call    cs:__imp_ExReleaseFastMutex
0x140010f04  nop     dword ptr [rax+rax+00h]
0x140010f09  lea     rax, WPP_RECORDER_INITIALIZED
0x140010f10  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010f17  jz      short loc_140010F57
0x140010f19  mov     rcx, cs:WPP_GLOBAL_Control
0x140010f20  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140010f27  mov     dword ptr [rsp+0B0h+var_80], 19B8h
0x140010f2f  mov     r9d, 0BDh
0x140010f35  mov     [rsp+0B0h+var_88], rax
0x140010f3a  mov     r8d, 6
0x140010f40  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x140010f47  mov     dl, 2
0x140010f49  mov     rcx, [rcx+40h]
0x140010f4d  mov     [rsp+0B0h+var_90], rax
0x140010f52  call    WPP_RECORDER_SF_sD
0x140010f57  mov     ebx, 0C00000BBh
0x140010f5c  jmp     loc_14001123E
0x140010f61  call    cs:__imp_ExReleaseFastMutex
0x140010f68  nop     dword ptr [rax+rax+00h]
0x140010f6d  lea     rdx, [rdi+20h]
0x140010f71  mov     r8d, esi
0x140010f74  lea     r9, [rbp+57h+arg_10]
0x140010f78  mov     rcx, rdi
0x140010f7b  call    BfpValidateVirtualizationRoot
0x140010f80  mov     ebx, eax
0x140010f82  test    eax, eax
0x140010f84  jns     short loc_140010FE1
0x140010f86  lea     rax, WPP_RECORDER_INITIALIZED
0x140010f8d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010f94  jz      loc_14001123E
0x140010f9a  mov     rcx, cs:WPP_GLOBAL_Control
0x140010fa1  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140010fa8  mov     [rsp+0B0h+var_78], ebx
0x140010fac  mov     r9d, 0BEh
0x140010fb2  mov     dword ptr [rsp+0B0h+var_80], 19C6h
0x140010fba  mov     r8d, 3
0x140010fc0  mov     [rsp+0B0h+var_88], rax
0x140010fc5  mov     dl, 2
0x140010fc7  mov     rcx, [rcx+40h]
0x140010fcb  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x140010fd2  mov     [rsp+0B0h+var_90], rax
0x140010fd7  call    WPP_RECORDER_SF_sDd
0x140010fdc  jmp     loc_14001123E
0x140010fe1  mov     r14, [rbp+57h+arg_10]
0x140010fe5  xorps   xmm0, xmm0
0x140010fe8  movzx   ecx, word ptr [rdi+18h]
0x140010fec  movups  [rbp+57h+var_40], xmm0
0x140010ff0  movzx   eax, word ptr [r14+4]
0x140010ff5  lea     r15, [r14+6]
0x140010ff9  mov     qword ptr [rbp+57h+var_40+8], r15
0x140010ffd  mov     word ptr [rbp+57h+var_40], ax
0x140011001  mov     word ptr [rbp+57h+var_40+2], ax
0x140011005  movups  [rbp+57h+var_50], xmm0
0x140011009  test    cx, cx
0x14001100c  jz      short loc_140011020
0x14001100e  mov     eax, [rdi+1Ch]
0x140011011  add     rax, rdi
0x140011014  mov     word ptr [rbp+57h+var_50], cx
0x140011018  mov     qword ptr [rbp+57h+var_50+8], rax
0x14001101c  mov     word ptr [rbp+57h+var_50+2], cx
0x140011020  movzx   r8d, word ptr [r14+2]
0x140011025  lea     rax, [rbp+57h+P]
0x140011029  lea     r9, [rbp+57h+var_50]
0x14001102d  mov     [rsp+0B0h+var_90], rax
0x140011032  xor     edx, edx
0x140011034  lea     rcx, [rbp+57h+var_40]
0x140011038  call    BfpInitializeContainerRootId
0x14001103d  mov     rsi, [rbp+57h+P]
0x140011041  mov     ebx, eax
0x140011043  test    eax, eax
0x140011045  jns     short loc_1400110A2
0x140011047  lea     rax, WPP_RECORDER_INITIALIZED
0x14001104e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140011055  jz      loc_140011225
0x14001105b  mov     [rsp+0B0h+var_78], ebx
0x14001105f  mov     r9d, 0BFh
0x140011065  mov     dword ptr [rsp+0B0h+var_80], 19DAh
0x14001106d  mov     rcx, cs:WPP_GLOBAL_Control
0x140011074  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14001107b  mov     [rsp+0B0h+var_88], rax
0x140011080  mov     r8d, 6
0x140011086  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x14001108d  mov     dl, 2
0x14001108f  mov     [rsp+0B0h+var_90], rax
0x140011094  mov     rcx, [rcx+40h]
0x140011098  call    WPP_RECORDER_SF_sDd
0x14001109d  jmp     loc_140011225
0x1400110a2  movzx   ecx, word ptr [rsi+4]
0x1400110a6  mov     eax, ecx
0x1400110a8  shr     rax, 1
0x1400110ab  cmp     word ptr [rsi+rax*2+4], 5Ch ; '\'
0x1400110b1  jnz     short loc_1400110C3
0x1400110b3  sub     cx, 2
0x1400110b7  mov     eax, 0FFFEh
0x1400110bc  mov     [rsi+4], cx
0x1400110c0  add     [rsi], ax
0x1400110c3  mov     r8, [rdi+10h]
0x1400110c7  lea     rcx, [rbp+57h+var_30]
0x1400110cb  mov     rdx, [rdi+8]
0x1400110cf  xor     r9d, r9d
0x1400110d2  mov     [rbp+57h+var_30], r12
0x1400110d6  mov     [rbp+57h+var_28], r15
0x1400110da  movzx   eax, word ptr [r14+2]
0x1400110df  mov     word ptr [rbp+57h+var_30], ax
0x1400110e3  mov     word ptr [rbp+57h+var_30+2], ax
0x1400110e7  lea     rax, [rbp+57h+var_58]
0x1400110eb  mov     [rsp+0B0h+var_80], rax
0x1400110f0  lea     rax, [rbp+57h+var_60]
0x1400110f4  mov     [rsp+0B0h+var_88], rax
0x1400110f9  mov     [rsp+0B0h+var_90], r12
0x1400110fe  call    BfpGetInstanceTierNode
0x140011103  mov     ebx, eax
0x140011105  cmp     eax, 0C0000225h
0x14001110a  jnz     short loc_140011164
0x14001110c  lea     rax, WPP_RECORDER_INITIALIZED
0x140011113  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001111a  jz      short loc_14001115A
0x14001111c  mov     rcx, cs:WPP_GLOBAL_Control
0x140011123  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14001112a  mov     dword ptr [rsp+0B0h+var_80], 1A01h
0x140011132  mov     r9d, 0C0h
0x140011138  mov     [rsp+0B0h+var_88], rax
0x14001113d  mov     r8d, 8
0x140011143  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x14001114a  mov     dl, 2
0x14001114c  mov     rcx, [rcx+40h]
0x140011150  mov     [rsp+0B0h+var_90], rax
0x140011155  call    WPP_RECORDER_SF_sD
0x14001115a  mov     ebx, 0C000000Dh
0x14001115f  jmp     loc_140011225
0x140011164  test    ebx, ebx
0x140011166  jns     short loc_140011193
0x140011168  lea     rax, WPP_RECORDER_INITIALIZED
0x14001116f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140011176  jz      loc_140011225
0x14001117c  mov     [rsp+0B0h+var_78], ebx
0x140011180  mov     r9d, 0C1h
0x140011186  mov     dword ptr [rsp+0B0h+var_80], 1A07h
0x14001118e  jmp     loc_14001106D
0x140011193  mov     rdi, [rbp+57h+var_60]
0x140011197  lea     rcx, [rdi+10h]; Resource
0x14001119b  call    cs:__imp_FltAcquireResourceExclusive
0x1400111a2  nop     dword ptr [rax+rax+00h]
0x1400111a7  mov     rcx, [rbp+57h+var_58]
0x1400111ab  lea     r8, BfpRemoveMapping
0x1400111b2  xor     r9d, r9d
0x1400111b5  mov     rdx, rsi
0x1400111b8  call    BfpExecuteCallbackOnVirtualizationRootNode
0x1400111bd  mov     ebx, eax
0x1400111bf  test    eax, eax
0x1400111c1  jns     short loc_140011215
0x1400111c3  lea     rax, WPP_RECORDER_INITIALIZED
0x1400111ca  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400111d1  jz      short loc_140011215
0x1400111d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400111da  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x1400111e1  mov     [rsp+0B0h+var_78], ebx
0x1400111e5  mov     r9d, 0C2h
0x1400111eb  mov     dword ptr [rsp+0B0h+var_80], 1A16h
0x1400111f3  mov     r8d, 6
0x1400111f9  mov     [rsp+0B0h+var_88], rax
0x1400111fe  mov     dl, 2
0x140011200  mov     rcx, [rcx+40h]
0x140011204  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x14001120b  mov     [rsp+0B0h+var_90], rax
0x140011210  call    WPP_RECORDER_SF_sDd
0x140011215  lea     rcx, [rdi+10h]; Resource
0x140011219  call    cs:__imp_FltReleaseResource
0x140011220  nop     dword ptr [rax+rax+00h]
0x140011225  test    rsi, rsi
0x140011228  jz      short loc_14001123E
0x14001122a  mov     edx, 706D4642h; Tag
0x14001122f  mov     rcx, rsi; P
0x140011232  call    cs:__imp_ExFreePoolWithTag
0x140011239  nop     dword ptr [rax+rax+00h]
0x14001123e  lea     r11, [rsp+0B0h+var_20]
0x140011246  mov     eax, ebx
0x140011248  mov     rbx, [r11+30h]
0x14001124c  mov     rsi, [r11+38h]
0x140011250  mov     rsp, r11
0x140011253  pop     r15
0x140011255  pop     r14
0x140011257  pop     r12
0x140011259  pop     rdi
0x14001125a  pop     rbp
0x14001125b  retn
```
