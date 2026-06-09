# BfRemoveBatchedVirtualizationMapping

- ea: `0x140010898`
- end: `0x140010d5d`
- name: `BfRemoveBatchedVirtualizationMapping`
- size: `1221`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x14001d974`
- `0x140025c70`

## callees

- `0x140001348`
- `0x140003304`
- `0x14000f008`
- `0x140010898`
- `0x140011264`
- `0x14001e5c8`
- `0x140021b60`
- `0x140021d1c`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x1400109b8`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400109b8`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400109d0`
- `ntoskrnl!ExReleaseFastMutex` at `0x140010a37`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400109d0`
- `ntoskrnl!ExReleaseFastMutex` at `0x140010a37`
- `ntoskrnl!PsGetCurrentSilo` at `0x1400108d2`
- `ntoskrnl!PsGetCurrentSilo` at `0x1400108d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010bdf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010d33`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010bdf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010d33`
- `ntoskrnl!PsIsHostSilo` at `0x1400108e1`
- `ntoskrnl!PsIsHostSilo` at `0x1400108e1`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140010b80`
- `FLTMGR!FltAcquireResourceExclusive` at `0x140010b80`
- `FLTMGR!FltReleaseContext` at `0x140010d1a`
- `FLTMGR!FltReleaseContext` at `0x140010d1a`
- `FLTMGR!FltReleaseResource` at `0x140010d05`
- `FLTMGR!FltReleaseResource` at `0x140010d05`

## pseudocode

```c
__int64 __fastcall BfRemoveBatchedVirtualizationMapping(__int64 a1, unsigned int a2)
{
  _WORD *v3; // rdi
  __int64 v4; // r15
  __int64 CurrentSilo; // rax
  int v7; // edx
  int InstanceTierNode; // ebx
  int v9; // edx
  int v10; // edx
  char v11; // r13
  __int64 v12; // r12
  __int64 v13; // r10
  __int64 v14; // r12
  __int64 v15; // r14
  __int16 v16; // r8
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int16 v20; // ax
  __int64 v21; // rcx
  int v22; // edx
  int v23; // edx
  int v24; // eax
  int v25; // r9d
  char v27; // [rsp+30h] [rbp-39h]
  int v28; // [rsp+38h] [rbp-31h]
  __int64 v29; // [rsp+40h] [rbp-29h] BYREF
  PFLT_CONTEXT Context; // [rsp+48h] [rbp-21h] BYREF
  __int64 v31; // [rsp+50h] [rbp-19h]
  __int128 v32; // [rsp+58h] [rbp-11h] BYREF
  _WORD v33[2]; // [rsp+68h] [rbp-1h] BYREF
  int v34; // [rsp+6Ch] [rbp+3h]
  __int64 v35; // [rsp+70h] [rbp+7h]
  __int128 v36; // [rsp+78h] [rbp+Fh] BYREF
  PVOID P; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v38; // [rsp+E8h] [rbp+7Fh] BYREF

  v3 = 0;
  P = 0;
  v38 = 0;
  v4 = 0;
  Context = 0;
  v29 = 0;
  CurrentSilo = PsGetCurrentSilo();
  if ( (unsigned __int8)PsIsHostSilo(CurrentSilo) )
  {
    InstanceTierNode = BfpValidateBatchedMappingConfig((int *)a1, a2);
    if ( InstanceTierNode >= 0 )
    {
      ExAcquireFastMutex(&FastMutex);
      if ( byte_14000B1C0 )
      {
        ExReleaseFastMutex(&FastMutex);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v10) = 2;
          WPP_RECORDER_SF_sD(
            WPP_GLOBAL_Control->DeviceExtension,
            v10,
            6,
            181,
            (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
            209);
        }
        return (unsigned int)-1073741637;
      }
      else
      {
        v11 = 0;
        ExReleaseFastMutex(&FastMutex);
        v12 = *(unsigned int *)(a1 + 28);
        v13 = a1 + *(unsigned int *)(a1 + 24);
        v31 = v13;
        v14 = a1 + v12;
        v15 = *(unsigned int *)(v13 + 32);
        while ( 1 )
        {
          if ( --v15 < 0 )
            goto LABEL_38;
          v34 = 0;
          v32 = 0;
          v36 = 0;
          v16 = *(_WORD *)(32 * v15 + v13 + 52);
          v17 = *(unsigned int *)(32 * v15 + v13 + 40) + 32LL;
          LOWORD(v36) = *(_WORD *)(32 * v15 + v13 + 38);
          v33[0] = v16;
          *((_QWORD *)&v36 + 1) = a1 + v17;
          v18 = *(unsigned int *)(32 * v15 + v13 + 56) + 32LL;
          v33[1] = v16;
          v35 = a1 + v18;
          v19 = *(unsigned __int16 *)(32 * v15 + v13 + 36);
          v20 = *(_WORD *)(v14 + 8 * v19 + 36);
          v21 = *(unsigned int *)(v14 + 8 * v19 + 40) + 32LL;
          LOWORD(v32) = v20;
          WORD1(v32) = v20;
          *((_QWORD *)&v32 + 1) = a1 + v21;
          InstanceTierNode = BfpInitializeContainerRootId(
                               (unsigned int)&v36,
                               (unsigned int)&v32,
                               0,
                               (unsigned int)v33,
                               (__int64)&P);
          if ( InstanceTierNode < 0 )
            break;
          v3 = P;
          InstanceTierNode = BfValidateContainerRootId((unsigned __int16 *)P, *(unsigned __int16 *)P);
          if ( InstanceTierNode < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_38;
            v28 = InstanceTierNode;
            v25 = 183;
            v27 = 18;
            goto LABEL_34;
          }
          if ( **((_DWORD **)&v32 + 1) == 6029404 && *(_WORD *)(*((_QWORD *)&v32 + 1) + 4LL) == 63 )
            v3[1] = 96;
          if ( !v4 )
          {
            InstanceTierNode = BfpGetInstanceTierNode(
                                 (unsigned int)&v32,
                                 *(_QWORD *)(a1 + 8),
                                 *(_QWORD *)(a1 + 16),
                                 0,
                                 (__int64)&Context,
                                 (__int64)&v38,
                                 (__int64)&v29);
            if ( InstanceTierNode < 0 )
            {
              if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                goto LABEL_38;
              v28 = InstanceTierNode;
              v25 = 184;
              v27 = 43;
LABEL_34:
              LOBYTE(v23) = 2;
              WPP_RECORDER_SF_sDd(
                WPP_GLOBAL_Control->DeviceExtension,
                v23,
                6,
                v25,
                (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
                (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
                v27,
                v28);
              goto LABEL_38;
            }
            FltAcquireResourceExclusive((PERESOURCE)(v38 + 16));
            v4 = v29;
            v11 = 1;
          }
          if ( v3[((unsigned __int64)(unsigned __int16)v3[2] >> 1) + 2] == 92 )
          {
            v3[2] -= 2;
            *v3 -= 2;
          }
          v24 = BfpExecuteCallbackOnVirtualizationRootNode(v4, v3, BfpRemoveMapping, 0);
          InstanceTierNode = 0;
          if ( v24 != -1073741275 )
            InstanceTierNode = v24;
          if ( InstanceTierNode < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_38;
            v28 = InstanceTierNode;
            v25 = 185;
            v27 = 82;
            goto LABEL_34;
          }
          ExFreePoolWithTag(v3, 0x706D4642u);
          v13 = v31;
          v3 = 0;
          P = 0;
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v22) = 2;
          WPP_RECORDER_SF_sDd(
            WPP_GLOBAL_Control->DeviceExtension,
            v22,
            6,
            182,
            (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
            (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
            10,
            InstanceTierNode);
        }
        v3 = P;
LABEL_38:
        if ( v11 )
          FltReleaseResource((PERESOURCE)(v38 + 16));
        if ( Context )
          FltReleaseContext(Context);
        if ( v3 )
          ExFreePoolWithTag(v3, 0x706D4642u);
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        6,
        180,
        (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
        195);
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        6,
        179,
        (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
        187);
    }
    return (unsigned int)-1073741790;
  }
  return (unsigned int)InstanceTierNode;
}

```

## disassembly

```asm
0x140010898  mov     [rsp-8+arg_0], rbx
0x14001089d  push    rbp
0x14001089e  push    rsi
0x14001089f  push    rdi
0x1400108a0  push    r12
0x1400108a2  push    r13
0x1400108a4  push    r14
0x1400108a6  push    r15
0x1400108a8  lea     rbp, [rsp-27h]
0x1400108ad  sub     rsp, 90h
0x1400108b4  xor     r14d, r14d
0x1400108b7  mov     ebx, edx
0x1400108b9  mov     edi, r14d
0x1400108bc  mov     [rbp+57h+P], r14
0x1400108c0  mov     [rbp+57h+arg_18], r14
0x1400108c4  mov     r15d, r14d
0x1400108c7  mov     [rbp+57h+Context], r14
0x1400108cb  mov     rsi, rcx
0x1400108ce  mov     [rbp+57h+var_80], r14
0x1400108d2  call    cs:__imp_PsGetCurrentSilo
0x1400108d9  nop     dword ptr [rax+rax+00h]
0x1400108de  mov     rcx, rax
0x1400108e1  call    cs:__imp_PsIsHostSilo
0x1400108e8  nop     dword ptr [rax+rax+00h]
0x1400108ed  test    al, al
0x1400108ef  jnz     short loc_140010947
0x1400108f1  lea     rax, WPP_RECORDER_INITIALIZED
0x1400108f8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400108ff  jz      short loc_14001093D
0x140010901  mov     rcx, cs:WPP_GLOBAL_Control
0x140010908  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x14001090f  mov     dword ptr [rsp+0C0h+var_90], 18BBh
0x140010917  lea     r8d, [r14+6]
0x14001091b  mov     [rsp+0C0h+var_98], rax
0x140010920  mov     r9d, 0B3h
0x140010926  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x14001092d  mov     dl, 2
0x14001092f  mov     rcx, [rcx+40h]
0x140010933  mov     [rsp+0C0h+var_A0], rax
0x140010938  call    WPP_RECORDER_SF_sD
0x14001093d  mov     ebx, 0C0000022h
0x140010942  jmp     loc_140010D3F
0x140010947  mov     edx, ebx
0x140010949  mov     rcx, rsi
0x14001094c  call    BfpValidateBatchedMappingConfig
0x140010951  mov     ebx, eax
0x140010953  test    eax, eax
0x140010955  jns     short loc_1400109AE
0x140010957  lea     rax, WPP_RECORDER_INITIALIZED
0x14001095e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010965  jz      loc_140010D3F
0x14001096b  mov     rcx, cs:WPP_GLOBAL_Control
0x140010972  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140010979  mov     dword ptr [rsp+0C0h+var_90], 18C3h
0x140010981  mov     r9d, 0B4h
0x140010987  mov     [rsp+0C0h+var_98], rax
0x14001098c  mov     r8d, 6
0x140010992  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x140010999  mov     dl, 2
0x14001099b  mov     rcx, [rcx+40h]
0x14001099f  mov     [rsp+0C0h+var_A0], rax
0x1400109a4  call    WPP_RECORDER_SF_sD
0x1400109a9  jmp     loc_140010D3F
0x1400109ae  lea     r12, FastMutex
0x1400109b5  mov     rcx, r12; FastMutex
0x1400109b8  call    cs:__imp_ExAcquireFastMutex
0x1400109bf  nop     dword ptr [rax+rax+00h]
0x1400109c4  cmp     cs:byte_14000B1C0, r14b
0x1400109cb  mov     rcx, r12; FastMutex
0x1400109ce  jz      short loc_140010A34
0x1400109d0  call    cs:__imp_ExReleaseFastMutex
0x1400109d7  nop     dword ptr [rax+rax+00h]
0x1400109dc  lea     rax, WPP_RECORDER_INITIALIZED
0x1400109e3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400109ea  jz      short loc_140010A2A
0x1400109ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400109f3  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x1400109fa  mov     dword ptr [rsp+0C0h+var_90], 18D1h
0x140010a02  mov     r9d, 0B5h
0x140010a08  mov     [rsp+0C0h+var_98], rax
0x140010a0d  mov     r8d, 6
0x140010a13  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x140010a1a  mov     dl, 2
0x140010a1c  mov     rcx, [rcx+40h]
0x140010a20  mov     [rsp+0C0h+var_A0], rax
0x140010a25  call    WPP_RECORDER_SF_sD
0x140010a2a  mov     ebx, 0C00000BBh
0x140010a2f  jmp     loc_140010D3F
0x140010a34  mov     r13b, r14b
0x140010a37  call    cs:__imp_ExReleaseFastMutex
0x140010a3e  nop     dword ptr [rax+rax+00h]
0x140010a43  mov     r10d, [rsi+18h]
0x140010a47  mov     r12d, [rsi+1Ch]
0x140010a4b  add     r10, rsi
0x140010a4e  mov     [rbp+57h+var_70], r10
0x140010a52  add     r12, rsi
0x140010a55  mov     r14d, [r10+20h]
0x140010a59  dec     r14
0x140010a5c  test    r14, r14
0x140010a5f  js      loc_140010CF8
0x140010a65  xorps   xmm0, xmm0
0x140010a68  mov     [rbp+57h+var_54], 0
0x140010a6f  movups  [rbp+57h+var_68], xmm0
0x140010a73  mov     r9, r14
0x140010a76  shl     r9, 5
0x140010a7a  movups  [rbp+57h+var_48], xmm0
0x140010a7e  movzx   r8d, word ptr [r9+r10+34h]
0x140010a84  movzx   edx, word ptr [r9+r10+26h]
0x140010a8a  mov     ecx, [r9+r10+28h]
0x140010a8f  add     rcx, 20h ; ' '
0x140010a93  mov     word ptr [rbp+57h+var_48], dx
0x140010a97  add     rcx, rsi
0x140010a9a  mov     [rbp+57h+var_58], r8w
0x140010a9f  mov     qword ptr [rbp+57h+var_48+8], rcx
0x140010aa3  lea     rdx, [rbp+57h+var_68]
0x140010aa7  mov     ecx, [r9+r10+38h]
0x140010aac  add     rcx, 20h ; ' '
0x140010ab0  mov     [rbp+57h+var_56], r8w
0x140010ab5  add     rcx, rsi
0x140010ab8  xor     r8d, r8d
0x140010abb  mov     [rbp+57h+var_50], rcx
0x140010abf  movzx   ecx, word ptr [r9+r10+24h]
0x140010ac5  lea     r9, [rbp+57h+var_58]
0x140010ac9  movzx   eax, word ptr [r12+rcx*8+24h]
0x140010acf  mov     ecx, [r12+rcx*8+28h]
0x140010ad4  add     rcx, 20h ; ' '
0x140010ad8  mov     word ptr [rbp+57h+var_68], ax
0x140010adc  add     rcx, rsi
0x140010adf  mov     word ptr [rbp+57h+var_68+2], ax
0x140010ae3  mov     qword ptr [rbp+57h+var_68+8], rcx
0x140010ae7  lea     rax, [rbp+57h+P]
0x140010aeb  lea     rcx, [rbp+57h+var_48]
0x140010aef  mov     [rsp+0C0h+var_A0], rax
0x140010af4  call    BfpInitializeContainerRootId
0x140010af9  mov     ebx, eax
0x140010afb  test    eax, eax
0x140010afd  js      loc_140010CA2
0x140010b03  mov     rdi, [rbp+57h+P]
0x140010b07  mov     rcx, rdi
0x140010b0a  movzx   edx, word ptr [rdi]
0x140010b0d  call    BfValidateContainerRootId
0x140010b12  mov     ebx, eax
0x140010b14  test    eax, eax
0x140010b16  js      loc_140010C4A
0x140010b1c  mov     rax, qword ptr [rbp+57h+var_68+8]
0x140010b20  cmp     word ptr [rax], 5Ch ; '\'
0x140010b24  jnz     short loc_140010B3A
0x140010b26  cmp     word ptr [rax+2], 5Ch ; '\'
0x140010b2b  jnz     short loc_140010B3A
0x140010b2d  cmp     word ptr [rax+4], 3Fh ; '?'
0x140010b32  jnz     short loc_140010B3A
0x140010b34  mov     word ptr [rdi+2], 60h ; '`'
0x140010b3a  test    r15, r15
0x140010b3d  jnz     short loc_140010B93
0x140010b3f  mov     r8, [rsi+10h]
0x140010b43  lea     rax, [rbp+57h+var_80]
0x140010b47  mov     rdx, [rsi+8]
0x140010b4b  lea     rcx, [rbp+57h+var_68]
0x140010b4f  mov     [rsp+0C0h+var_90], rax
0x140010b54  xor     r9d, r9d
0x140010b57  lea     rax, [rbp+57h+arg_18]
0x140010b5b  mov     [rsp+0C0h+var_98], rax
0x140010b60  lea     rax, [rbp+57h+Context]
0x140010b64  mov     [rsp+0C0h+var_A0], rax
0x140010b69  call    BfpGetInstanceTierNode
0x140010b6e  mov     ebx, eax
0x140010b70  test    eax, eax
0x140010b72  js      loc_140010BFA
0x140010b78  mov     rcx, [rbp+57h+arg_18]
0x140010b7c  add     rcx, 10h; Resource
0x140010b80  call    cs:__imp_FltAcquireResourceExclusive
0x140010b87  nop     dword ptr [rax+rax+00h]
0x140010b8c  mov     r15, [rbp+57h+var_80]
0x140010b90  mov     r13b, 1
0x140010b93  movzx   ecx, word ptr [rdi+4]
0x140010b97  mov     eax, ecx
0x140010b99  shr     rax, 1
0x140010b9c  cmp     word ptr [rdi+rax*2+4], 5Ch ; '\'
0x140010ba2  jnz     short loc_140010BB4
0x140010ba4  sub     cx, 2
0x140010ba8  mov     eax, 0FFFEh
0x140010bad  mov     [rdi+4], cx
0x140010bb1  add     [rdi], ax
0x140010bb4  xor     r9d, r9d
0x140010bb7  lea     r8, BfpRemoveMapping
0x140010bbe  mov     rdx, rdi
0x140010bc1  mov     rcx, r15
0x140010bc4  call    BfpExecuteCallbackOnVirtualizationRootNode
0x140010bc9  xor     ebx, ebx
0x140010bcb  cmp     eax, 0C0000225h
0x140010bd0  cmovnz  ebx, eax
0x140010bd3  test    ebx, ebx
0x140010bd5  js      short loc_140010C22
0x140010bd7  mov     edx, 706D4642h; Tag
0x140010bdc  mov     rcx, rdi; P
0x140010bdf  call    cs:__imp_ExFreePoolWithTag
0x140010be6  nop     dword ptr [rax+rax+00h]
0x140010beb  mov     r10, [rbp+57h+var_70]
0x140010bef  xor     edi, edi
0x140010bf1  mov     [rbp+57h+P], rdi
0x140010bf5  jmp     loc_140010A59
0x140010bfa  lea     rax, WPP_RECORDER_INITIALIZED
0x140010c01  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010c08  jz      loc_140010CF8
0x140010c0e  mov     [rsp+0C0h+var_88], ebx
0x140010c12  mov     r9d, 0B8h
0x140010c18  mov     dword ptr [rsp+0C0h+var_90], 192Bh
0x140010c20  jmp     short loc_140010C70
0x140010c22  lea     rax, WPP_RECORDER_INITIALIZED
0x140010c29  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010c30  jz      loc_140010CF8
0x140010c36  mov     [rsp+0C0h+var_88], ebx
0x140010c3a  mov     r9d, 0B9h
0x140010c40  mov     dword ptr [rsp+0C0h+var_90], 1952h
0x140010c48  jmp     short loc_140010C70
0x140010c4a  lea     rax, WPP_RECORDER_INITIALIZED
0x140010c51  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010c58  jz      loc_140010CF8
0x140010c5e  mov     [rsp+0C0h+var_88], ebx
0x140010c62  mov     r9d, 0B7h
0x140010c68  mov     dword ptr [rsp+0C0h+var_90], 1912h
0x140010c70  mov     rcx, cs:WPP_GLOBAL_Control
0x140010c77  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140010c7e  mov     [rsp+0C0h+var_98], rax
0x140010c83  mov     r8d, 6
0x140010c89  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x140010c90  mov     dl, 2
0x140010c92  mov     [rsp+0C0h+var_A0], rax
0x140010c97  mov     rcx, [rcx+40h]
0x140010c9b  call    WPP_RECORDER_SF_sDd
0x140010ca0  jmp     short loc_140010CF8
0x140010ca2  lea     rax, WPP_RECORDER_INITIALIZED
0x140010ca9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010cb0  jz      short loc_140010CF4
0x140010cb2  mov     rcx, cs:WPP_GLOBAL_Control
0x140010cb9  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140010cc0  mov     [rsp+0C0h+var_88], ebx
0x140010cc4  mov     r9d, 0B6h
0x140010cca  mov     dword ptr [rsp+0C0h+var_90], 190Ah
0x140010cd2  mov     r8d, 6
0x140010cd8  mov     [rsp+0C0h+var_98], rax
0x140010cdd  mov     dl, 2
0x140010cdf  mov     rcx, [rcx+40h]
0x140010ce3  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x140010cea  mov     [rsp+0C0h+var_A0], rax
0x140010cef  call    WPP_RECORDER_SF_sDd
0x140010cf4  mov     rdi, [rbp+57h+P]
0x140010cf8  test    r13b, r13b
0x140010cfb  jz      short loc_140010D11
0x140010cfd  mov     rcx, [rbp+57h+arg_18]
0x140010d01  add     rcx, 10h; Resource
0x140010d05  call    cs:__imp_FltReleaseResource
0x140010d0c  nop     dword ptr [rax+rax+00h]
0x140010d11  mov     rcx, [rbp+57h+Context]; Context
0x140010d15  test    rcx, rcx
0x140010d18  jz      short loc_140010D26
0x140010d1a  call    cs:__imp_FltReleaseContext
0x140010d21  nop     dword ptr [rax+rax+00h]
0x140010d26  test    rdi, rdi
0x140010d29  jz      short loc_140010D3F
0x140010d2b  mov     edx, 706D4642h; Tag
0x140010d30  mov     rcx, rdi; P
0x140010d33  call    cs:__imp_ExFreePoolWithTag
0x140010d3a  nop     dword ptr [rax+rax+00h]
0x140010d3f  mov     eax, ebx
0x140010d41  mov     rbx, [rsp+0C0h+arg_0]
0x140010d49  add     rsp, 90h
0x140010d50  pop     r15
0x140010d52  pop     r14
0x140010d54  pop     r13
0x140010d56  pop     r12
0x140010d58  pop     rdi
0x140010d59  pop     rsi
0x140010d5a  pop     rbp
0x140010d5b  retn
```
