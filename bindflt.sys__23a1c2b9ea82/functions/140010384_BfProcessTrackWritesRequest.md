# BfProcessTrackWritesRequest

- ea: `0x140010384`
- end: `0x14001088f`
- name: `BfProcessTrackWritesRequest`
- size: `1291`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140025c70`

## callees

- `0x140001348`
- `0x140003140`
- `0x140003304`
- `0x14000f008`
- `0x140010384`
- `0x140011264`
- `0x14001fb68`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x14001050f`
- `ntoskrnl!ExAcquireFastMutex` at `0x14001050f`
- `ntoskrnl!PsJobType` at `0x1400105b0`
- `ntoskrnl!ObIsKernelHandle` at `0x1400105a4`
- `ntoskrnl!ObIsKernelHandle` at `0x1400105a4`
- `ntoskrnl!ExReleaseFastMutex` at `0x140010527`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001058b`
- `ntoskrnl!ExReleaseFastMutex` at `0x140010527`
- `ntoskrnl!ExReleaseFastMutex` at `0x14001058b`
- `ntoskrnl!PsGetJobSilo` at `0x140010650`
- `ntoskrnl!PsGetJobSilo` at `0x140010650`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400105db`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400105db`
- `ntoskrnl!PsGetCurrentSilo` at `0x1400103c3`
- `ntoskrnl!PsGetCurrentSilo` at `0x1400103c3`
- `ntoskrnl!ObfDereferenceObject` at `0x14001086d`
- `ntoskrnl!ObfDereferenceObject` at `0x14001086d`
- `ntoskrnl!PsIsHostSilo` at `0x1400103d2`
- `ntoskrnl!PsIsHostSilo` at `0x1400103d2`
- `FLTMGR!FltAcquireResourceExclusive` at `0x1400107b8`
- `FLTMGR!FltAcquireResourceExclusive` at `0x1400107b8`
- `FLTMGR!FltReleaseResource` at `0x140010858`
- `FLTMGR!FltReleaseResource` at `0x140010858`

## pseudocode

```c
__int64 __fastcall BfProcessTrackWritesRequest(__int64 a1, unsigned int a2)
{
  __int64 CurrentSilo; // rax
  int v5; // edx
  NTSTATUS JobSilo; // ebx
  int v7; // edx
  void *v8; // rcx
  BOOLEAN IsKernelHandle; // al
  int v10; // edx
  int v11; // r9d
  int v12; // r8d
  _WORD *v13; // rdi
  __int64 v14; // r8
  __int64 v15; // rsi
  int v16; // edx
  char v18; // [rsp+30h] [rbp-50h]
  NTSTATUS v19; // [rsp+38h] [rbp-48h]
  __int64 v20; // [rsp+50h] [rbp-30h] BYREF
  __int64 v21; // [rsp+58h] [rbp-28h] BYREF
  __int64 v22; // [rsp+60h] [rbp-20h] BYREF
  __int128 v23; // [rsp+68h] [rbp-18h] BYREF
  PVOID Object; // [rsp+B0h] [rbp+30h] BYREF
  _WORD *v25; // [rsp+B8h] [rbp+38h] BYREF

  Object = 0;
  v21 = 0;
  v20 = 0;
  v22 = 0;
  v25 = 0;
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
        195,
        (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
        63);
    }
    JobSilo = -1073741790;
    goto LABEL_40;
  }
  if ( a2 < 0x20 )
  {
    JobSilo = -1073741811;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 2;
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        6,
        196,
        (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
        75);
    }
    goto LABEL_40;
  }
  if ( *(_DWORD *)a1 > a2 )
  {
    JobSilo = -1073741811;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 2;
      WPP_RECORDER_SF_sDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        6,
        197,
        (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
        82,
        *(_DWORD *)a1,
        a2);
    }
    goto LABEL_40;
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
        198,
        (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
        96);
    }
    JobSilo = -1073741637;
    goto LABEL_40;
  }
  ExReleaseFastMutex(&FastMutex);
  v8 = *(void **)(a1 + 16);
  if ( v8 )
  {
    IsKernelHandle = ObIsKernelHandle(v8);
    JobSilo = ObReferenceObjectByHandle(
                *(HANDLE *)(a1 + 16),
                4u,
                (POBJECT_TYPE)PsJobType,
                IsKernelHandle == 0,
                &Object,
                0);
    if ( JobSilo < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_40;
      v19 = JobSilo;
      v11 = 199;
      v18 = 118;
LABEL_19:
      v12 = 6;
      goto LABEL_20;
    }
    JobSilo = PsGetJobSilo(Object, &v21);
    if ( JobSilo < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_40;
      v19 = JobSilo;
      v11 = 200;
      v18 = 126;
      goto LABEL_19;
    }
  }
  v23 = 0;
  JobSilo = BfpValidateVirtualizationRoot(a1, a1 + 24, a2, &v25);
  if ( JobSilo < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_40;
    v19 = JobSilo;
    v11 = 201;
    v18 = -116;
    v12 = 3;
LABEL_20:
    LOBYTE(v10) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      v12,
      v11,
      (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
      v18,
      v19);
    goto LABEL_40;
  }
  v13 = v25;
  v14 = *(_QWORD *)(a1 + 8);
  *((_QWORD *)&v23 + 1) = v25 + 3;
  LOWORD(v23) = v25[1];
  WORD1(v23) = v23;
  JobSilo = BfpGetInstanceTierNode((unsigned int)&v23, 0, v14, 0, 0, (__int64)&v20, (__int64)&v22);
  if ( JobSilo == -1073741275 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        8,
        202,
        (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
        167);
    }
    JobSilo = -1073741811;
  }
  else
  {
    if ( JobSilo < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_40;
      v19 = JobSilo;
      v11 = 203;
      v18 = -83;
      goto LABEL_19;
    }
    v15 = v20;
    FltAcquireResourceExclusive((PERESOURCE)(v20 + 16));
    if ( v13[((unsigned __int64)(unsigned __int16)v13[2] >> 1) + 2] == 92 )
    {
      v13[2] -= 2;
      *v13 -= 2;
    }
    JobSilo = BfpExecuteCallbackOnVirtualizationRootNode(v22, v13, BfpSetMappingNodeForTracking, v21);
    if ( JobSilo < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v16) = 2;
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v16,
        6,
        204,
        (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
        200,
        JobSilo);
    }
    FltReleaseResource((PERESOURCE)(v15 + 16));
  }
LABEL_40:
  if ( Object )
    ObfDereferenceObject(Object);
  return (unsigned int)JobSilo;
}

```

## disassembly

```asm
0x140010384  mov     [rsp-18h+arg_0], rbx
0x140010389  push    rbp
0x14001038a  push    rsi
0x14001038b  push    rdi
0x14001038c  mov     rbp, rsp
0x14001038f  sub     rsp, 80h
0x140010396  mov     edi, edx
0x140010398  mov     [rbp+arg_10], 0
0x1400103a0  mov     rsi, rcx
0x1400103a3  mov     [rbp+var_28], 0
0x1400103ab  mov     [rbp+var_30], 0
0x1400103b3  mov     [rbp+var_20], 0
0x1400103bb  mov     [rbp+arg_18], 0
0x1400103c3  call    cs:__imp_PsGetCurrentSilo
0x1400103ca  nop     dword ptr [rax+rax+00h]
0x1400103cf  mov     rcx, rax
0x1400103d2  call    cs:__imp_PsIsHostSilo
0x1400103d9  nop     dword ptr [rax+rax+00h]
0x1400103de  test    al, al
0x1400103e0  jnz     short loc_14001043A
0x1400103e2  lea     rax, WPP_RECORDER_INITIALIZED
0x1400103e9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400103f0  jz      short loc_140010430
0x1400103f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400103f9  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140010400  mov     dword ptr [rsp+80h+var_50], 1A3Fh
0x140010408  mov     r9d, 0C3h
0x14001040e  mov     [rsp+80h+HandleInformation], rax
0x140010413  mov     r8d, 6
0x140010419  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x140010420  mov     dl, 2
0x140010422  mov     rcx, [rcx+40h]
0x140010426  mov     [rsp+80h+Object], rax
0x14001042b  call    WPP_RECORDER_SF_sD
0x140010430  mov     ebx, 0C0000022h
0x140010435  jmp     loc_140010864
0x14001043a  cmp     edi, 20h ; ' '
0x14001043d  jnb     short loc_14001049B
0x14001043f  mov     ebx, 0C000000Dh
0x140010444  lea     rax, WPP_RECORDER_INITIALIZED
0x14001044b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010452  jz      loc_140010864
0x140010458  mov     rcx, cs:WPP_GLOBAL_Control
0x14001045f  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140010466  mov     dword ptr [rsp+80h+var_50], 1A4Bh
0x14001046e  mov     r9d, 0C4h
0x140010474  mov     [rsp+80h+HandleInformation], rax
0x140010479  mov     r8d, 6
0x14001047f  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x140010486  mov     dl, 2
0x140010488  mov     rcx, [rcx+40h]
0x14001048c  mov     [rsp+80h+Object], rax
0x140010491  call    WPP_RECORDER_SF_sD
0x140010496  jmp     loc_140010864
0x14001049b  mov     ecx, [rsi]
0x14001049d  cmp     ecx, edi
0x14001049f  jbe     short loc_140010505
0x1400104a1  mov     ebx, 0C000000Dh
0x1400104a6  lea     rax, WPP_RECORDER_INITIALIZED
0x1400104ad  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400104b4  jz      loc_140010864
0x1400104ba  mov     [rsp+80h+var_40], edi
0x1400104be  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x1400104c5  mov     [rsp+80h+var_48], ecx
0x1400104c9  mov     r9d, 0C5h
0x1400104cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400104d6  mov     r8d, 6
0x1400104dc  mov     dword ptr [rsp+80h+var_50], 1A52h
0x1400104e4  mov     dl, 2
0x1400104e6  mov     [rsp+80h+HandleInformation], rax
0x1400104eb  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x1400104f2  mov     [rsp+80h+Object], rax
0x1400104f7  mov     rcx, [rcx+40h]
0x1400104fb  call    WPP_RECORDER_SF_sDdd
0x140010500  jmp     loc_140010864
0x140010505  lea     rbx, FastMutex
0x14001050c  mov     rcx, rbx; FastMutex
0x14001050f  call    cs:__imp_ExAcquireFastMutex
0x140010516  nop     dword ptr [rax+rax+00h]
0x14001051b  cmp     cs:byte_14000B1C0, 0
0x140010522  mov     rcx, rbx; FastMutex
0x140010525  jz      short loc_14001058B
0x140010527  call    cs:__imp_ExReleaseFastMutex
0x14001052e  nop     dword ptr [rax+rax+00h]
0x140010533  lea     rax, WPP_RECORDER_INITIALIZED
0x14001053a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010541  jz      short loc_140010581
0x140010543  mov     rcx, cs:WPP_GLOBAL_Control
0x14001054a  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140010551  mov     dword ptr [rsp+80h+var_50], 1A60h
0x140010559  mov     r9d, 0C6h
0x14001055f  mov     [rsp+80h+HandleInformation], rax
0x140010564  mov     r8d, 6
0x14001056a  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x140010571  mov     dl, 2
0x140010573  mov     rcx, [rcx+40h]
0x140010577  mov     [rsp+80h+Object], rax
0x14001057c  call    WPP_RECORDER_SF_sD
0x140010581  mov     ebx, 0C00000BBh
0x140010586  jmp     loc_140010864
0x14001058b  call    cs:__imp_ExReleaseFastMutex
0x140010592  nop     dword ptr [rax+rax+00h]
0x140010597  mov     rcx, [rsi+10h]; Handle
0x14001059b  test    rcx, rcx
0x14001059e  jz      loc_14001068A
0x1400105a4  call    cs:__imp_ObIsKernelHandle
0x1400105ab  nop     dword ptr [rax+rax+00h]
0x1400105b0  mov     r8, cs:PsJobType
0x1400105b7  mov     edx, 4; DesiredAccess
0x1400105bc  mov     rcx, [rsi+10h]; Handle
0x1400105c0  test    al, al
0x1400105c2  lea     rax, [rbp+arg_10]
0x1400105c6  mov     [rsp+80h+HandleInformation], 0; HandleInformation
0x1400105cf  setz    r9b; AccessMode
0x1400105d3  mov     [rsp+80h+Object], rax; Object
0x1400105d8  mov     r8, [r8]; ObjectType
0x1400105db  call    cs:__imp_ObReferenceObjectByHandle
0x1400105e2  nop     dword ptr [rax+rax+00h]
0x1400105e7  mov     ebx, eax
0x1400105e9  test    eax, eax
0x1400105eb  jns     short loc_140010648
0x1400105ed  lea     rax, WPP_RECORDER_INITIALIZED
0x1400105f4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400105fb  jz      loc_140010864
0x140010601  mov     [rsp+80h+var_48], ebx
0x140010605  mov     r9d, 0C7h
0x14001060b  mov     dword ptr [rsp+80h+var_50], 1A76h
0x140010613  mov     r8d, 6
0x140010619  mov     rcx, cs:WPP_GLOBAL_Control
0x140010620  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140010627  mov     [rsp+80h+HandleInformation], rax
0x14001062c  mov     dl, 2
0x14001062e  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x140010635  mov     [rsp+80h+Object], rax
0x14001063a  mov     rcx, [rcx+40h]
0x14001063e  call    WPP_RECORDER_SF_sDd
0x140010643  jmp     loc_140010864
0x140010648  mov     rcx, [rbp+arg_10]
0x14001064c  lea     rdx, [rbp+var_28]
0x140010650  call    cs:__imp_PsGetJobSilo
0x140010657  nop     dword ptr [rax+rax+00h]
0x14001065c  mov     ebx, eax
0x14001065e  test    eax, eax
0x140010660  jns     short loc_14001068A
0x140010662  lea     rax, WPP_RECORDER_INITIALIZED
0x140010669  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010670  jz      loc_140010864
0x140010676  mov     [rsp+80h+var_48], ebx
0x14001067a  mov     r9d, 0C8h
0x140010680  mov     dword ptr [rsp+80h+var_50], 1A7Eh
0x140010688  jmp     short loc_140010613
0x14001068a  xorps   xmm0, xmm0
0x14001068d  lea     rdx, [rsi+18h]
0x140010691  lea     r9, [rbp+arg_18]
0x140010695  mov     r8d, edi
0x140010698  mov     rcx, rsi
0x14001069b  movups  [rbp+var_18], xmm0
0x14001069f  call    BfpValidateVirtualizationRoot
0x1400106a4  mov     ebx, eax
0x1400106a6  test    eax, eax
0x1400106a8  jns     short loc_1400106DB
0x1400106aa  lea     rax, WPP_RECORDER_INITIALIZED
0x1400106b1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400106b8  jz      loc_140010864
0x1400106be  mov     [rsp+80h+var_48], ebx
0x1400106c2  mov     r9d, 0C9h
0x1400106c8  mov     dword ptr [rsp+80h+var_50], 1A8Ch
0x1400106d0  mov     r8d, 3
0x1400106d6  jmp     loc_140010619
0x1400106db  mov     rdi, [rbp+arg_18]
0x1400106df  lea     rcx, [rbp+var_18]
0x1400106e3  mov     r8, [rsi+8]
0x1400106e7  xor     r9d, r9d
0x1400106ea  xor     edx, edx
0x1400106ec  lea     rax, [rdi+6]
0x1400106f0  mov     qword ptr [rbp+var_18+8], rax
0x1400106f4  movzx   eax, word ptr [rdi+2]
0x1400106f8  mov     word ptr [rbp+var_18], ax
0x1400106fc  mov     word ptr [rbp+var_18+2], ax
0x140010700  lea     rax, [rbp+var_20]
0x140010704  mov     [rsp+80h+var_50], rax
0x140010709  lea     rax, [rbp+var_30]
0x14001070d  mov     [rsp+80h+HandleInformation], rax
0x140010712  mov     [rsp+80h+Object], 0
0x14001071b  call    BfpGetInstanceTierNode
0x140010720  mov     ebx, eax
0x140010722  cmp     eax, 0C0000225h
0x140010727  jnz     short loc_140010781
0x140010729  lea     rax, WPP_RECORDER_INITIALIZED
0x140010730  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010737  jz      short loc_140010777
0x140010739  mov     rcx, cs:WPP_GLOBAL_Control
0x140010740  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140010747  mov     dword ptr [rsp+80h+var_50], 1AA7h
0x14001074f  mov     r9d, 0CAh
0x140010755  mov     [rsp+80h+HandleInformation], rax
0x14001075a  mov     r8d, 8
0x140010760  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x140010767  mov     dl, 2
0x140010769  mov     rcx, [rcx+40h]
0x14001076d  mov     [rsp+80h+Object], rax
0x140010772  call    WPP_RECORDER_SF_sD
0x140010777  mov     ebx, 0C000000Dh
0x14001077c  jmp     loc_140010864
0x140010781  test    ebx, ebx
0x140010783  jns     short loc_1400107B0
0x140010785  lea     rax, WPP_RECORDER_INITIALIZED
0x14001078c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010793  jz      loc_140010864
0x140010799  mov     [rsp+80h+var_48], ebx
0x14001079d  mov     r9d, 0CBh
0x1400107a3  mov     dword ptr [rsp+80h+var_50], 1AADh
0x1400107ab  jmp     loc_140010613
0x1400107b0  mov     rsi, [rbp+var_30]
0x1400107b4  lea     rcx, [rsi+10h]; Resource
0x1400107b8  call    cs:__imp_FltAcquireResourceExclusive
0x1400107bf  nop     dword ptr [rax+rax+00h]
0x1400107c4  movzx   ecx, word ptr [rdi+4]
0x1400107c8  mov     eax, ecx
0x1400107ca  shr     rax, 1
0x1400107cd  cmp     word ptr [rdi+rax*2+4], 5Ch ; '\'
0x1400107d3  jnz     short loc_1400107E5
0x1400107d5  sub     cx, 2
0x1400107d9  mov     eax, 0FFFEh
0x1400107de  mov     [rdi+4], cx
0x1400107e2  add     [rdi], ax
0x1400107e5  mov     r9, [rbp+var_28]
0x1400107e9  lea     r8, BfpSetMappingNodeForTracking
0x1400107f0  mov     rcx, [rbp+var_20]
0x1400107f4  mov     rdx, rdi
0x1400107f7  call    BfpExecuteCallbackOnVirtualizationRootNode
0x1400107fc  mov     ebx, eax
0x1400107fe  test    eax, eax
0x140010800  jns     short loc_140010854
0x140010802  lea     rax, WPP_RECORDER_INITIALIZED
0x140010809  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140010810  jz      short loc_140010854
0x140010812  mov     rcx, cs:WPP_GLOBAL_Control
0x140010819  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140010820  mov     [rsp+80h+var_48], ebx
0x140010824  mov     r9d, 0CCh
0x14001082a  mov     dword ptr [rsp+80h+var_50], 1AC8h
0x140010832  mov     r8d, 6
0x140010838  mov     [rsp+80h+HandleInformation], rax
0x14001083d  mov     dl, 2
0x14001083f  mov     rcx, [rcx+40h]
0x140010843  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x14001084a  mov     [rsp+80h+Object], rax
0x14001084f  call    WPP_RECORDER_SF_sDd
0x140010854  lea     rcx, [rsi+10h]; Resource
0x140010858  call    cs:__imp_FltReleaseResource
0x14001085f  nop     dword ptr [rax+rax+00h]
0x140010864  mov     rcx, [rbp+arg_10]; Object
0x140010868  test    rcx, rcx
0x14001086b  jz      short loc_140010879
0x14001086d  call    cs:__imp_ObfDereferenceObject
0x140010874  nop     dword ptr [rax+rax+00h]
0x140010879  mov     eax, ebx
0x14001087b  mov     rbx, [rsp+80h+arg_0]
0x140010883  add     rsp, 80h
0x14001088a  pop     rdi
0x14001088b  pop     rsi
0x14001088c  pop     rbp
0x14001088d  retn
```
