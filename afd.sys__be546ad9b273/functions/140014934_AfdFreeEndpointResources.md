# AfdFreeEndpointResources

- ea: `0x140014934`
- end: `0x140014dae`
- name: `AfdFreeEndpointResources`
- size: `1146`
- prototype: `NTSTATUS __fastcall(__int64)`
- caller_count: `4`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000f390`
- `0x140014880`
- `0x1400148c0`
- `0x140014db4`

## callees

- `0x14000f390`
- `0x14000f980`
- `0x140012610`
- `0x140013030`
- `0x140014934`
- `0x1400156e0`
- `0x140015ae0`
- `0x1400329e4`
- `0x1400338b8`
- `0x14003f274`
- `0x140047c1c`
- `0x140049a00`
- `0x14004e2f8`
- `0x140059a18`
- `0x14006a5bc`
- `0x140072920`
- `0x1400930cc`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14007617b`
- `ntoskrnl!KeInitializeEvent` at `0x14007617b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400761cc`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400761cc`
- `ntoskrnl!PsReturnPoolQuota` at `0x140014a06`
- `ntoskrnl!PsReturnPoolQuota` at `0x140014a06`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x140014cb0`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x140014cb0`
- `ntoskrnl!ZwClose` at `0x140014b8e`
- `ntoskrnl!ZwClose` at `0x140014bb8`
- `ntoskrnl!ZwClose` at `0x140014b8e`
- `ntoskrnl!ZwClose` at `0x140014bb8`
- `ntoskrnl!ObfDereferenceObject` at `0x140014a16`
- `ntoskrnl!ObfDereferenceObject` at `0x140014d4f`
- `ntoskrnl!ObfDereferenceObject` at `0x14007607e`
- `ntoskrnl!ObfDereferenceObject` at `0x1400760aa`
- `ntoskrnl!ObfDereferenceObject` at `0x140014a16`
- `ntoskrnl!ObfDereferenceObject` at `0x140014d4f`
- `ntoskrnl!ObfDereferenceObject` at `0x14007607e`
- `ntoskrnl!ObfDereferenceObject` at `0x1400760aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014a85`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014c0b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400760d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007611e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014a85`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014c0b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400760d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007611e`
- `NDIS!NdisFreeRWLock` at `0x140014b21`
- `NDIS!NdisFreeRWLock` at `0x140014b21`

## pseudocode

```c
NTSTATUS __fastcall AfdFreeEndpointResources(__int64 a1)
{
  void *v2; // rcx
  __int64 v3; // rcx
  char *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  NTSTATUS result; // eax
  void *v8; // rcx
  struct _NDIS_RW_LOCK_EX *v9; // rcx
  _QWORD **v10; // rdi
  _QWORD *v11; // rcx
  _QWORD *v12; // rax
  void *v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  void *v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int128 v20; // [rsp+30h] [rbp-50h] BYREF
  struct _KEVENT Event; // [rsp+40h] [rbp-40h] BYREF
  PVOID Object; // [rsp+58h] [rbp-28h] BYREF
  __int128 v23; // [rsp+60h] [rbp-20h]
  __int64 v24; // [rsp+70h] [rbp-10h]

  if ( (*(_WORD *)a1 & 0xAFD4) == 0xAFD4 )
    AfdFreeQueuedConnections(a1);
  v2 = *(void **)(a1 + 80);
  if ( v2 )
  {
    AfdRioCleanupRioState(v2);
    *(_QWORD *)(a1 + 80) = 0;
  }
  if ( *(_WORD *)a1 == 0xFA09 )
    AfdRioCleanupRegistrationDomain(a1);
  if ( *(_DWORD *)(a1 + 464) )
    AfdDereferenceGroup();
  if ( *(_WORD *)a1 == 0xAFD1 )
  {
    v10 = (_QWORD **)(a1 + 128);
    if ( *(_QWORD *)(a1 + 128) )
    {
      while ( 1 )
      {
        v11 = *v10;
        if ( *v10 == v10 )
          break;
        if ( (_QWORD **)v11[1] != v10 || (v12 = (_QWORD *)*v11, *(_QWORD **)(*v11 + 8LL) != v11) )
          __fastfail(3u);
        *v10 = v12;
        v12[1] = v10;
        AfdReturnBuffer(v11, *(PEPROCESS *)(a1 + 48));
      }
    }
  }
  if ( (*(_DWORD *)(a1 + 8) & 0x100) != 0 || !*(_QWORD *)(a1 + 24) )
  {
    v3 = *(_QWORD *)(a1 + 40);
    if ( v3 )
      ObDereferenceSecurityDescriptor(v3, 1);
    *(_QWORD *)(a1 + 40) = 0;
  }
  else
  {
    if ( *(_QWORD *)(a1 + 256) )
    {
      if ( ((*(_WORD *)a1 + 20528) & 0xFFF9) == 0 )
      {
        AfdTdiClearVcEventHandlers(a1, 0);
        if ( (*(_DWORD *)(a1 + 8) & 0x400000) != 0 )
        {
          LOBYTE(v15) = 1;
          AfdTdiClearVcEventHandlers(a1, v15);
        }
      }
    }
    ObfDereferenceObject(*(PVOID *)(a1 + 24));
    *(_QWORD *)(a1 + 24) = 0;
    *(_QWORD *)(a1 + 40) = 0;
    if ( (*(_DWORD *)(a1 + 8) & 0x400000) != 0 )
    {
      ObfDereferenceObject(*(PVOID *)(*(_QWORD *)(a1 + 280) + 8LL));
      *(_QWORD *)(*(_QWORD *)(a1 + 280) + 8LL) = 0;
      *(_QWORD *)(*(_QWORD *)(a1 + 280) + 16LL) = 0;
    }
  }
  if ( (*(_DWORD *)(a1 + 8) & 0x100) == 0 )
  {
    v13 = *(void **)(a1 + 256);
    if ( v13 )
    {
      ZwClose(v13);
      *(_QWORD *)(a1 + 256) = 0;
      if ( (*(_DWORD *)(a1 + 8) & 0x400000) != 0 )
      {
        ZwClose(**(HANDLE **)(a1 + 280));
        **(_QWORD **)(a1 + 280) = 0;
      }
    }
  }
  v4 = *(char **)(a1 + 88);
  if ( v4 )
  {
    AfdDereferenceCompartment(v4);
    *(_QWORD *)(a1 + 88) = 0;
  }
  AfdRemoveEndpointFromList(a1);
  PsReturnPoolQuota(*(PEPROCESS *)(a1 + 48), (POOL_TYPE)512, (*(_DWORD *)(a1 + 8) & 0x200) != 0 ? 528LL : 496LL);
  ObfDereferenceObject(*(PVOID *)(a1 + 48));
  *(_QWORD *)(a1 + 48) = 0;
  if ( *(_WORD *)a1 == 0xAFD2 )
  {
    v16 = *(_QWORD *)(a1 + 200);
    if ( v16 )
    {
      AfdDereferenceEndpoint(v16);
      *(_QWORD *)(a1 + 200) = 0;
      *(_QWORD *)(a1 + 240) = 0;
      *(_DWORD *)(a1 + 236) = 0;
    }
  }
  if ( *(_WORD *)a1 == 6909 )
  {
    AfdDereferenceEndpoint(*(_QWORD *)(a1 + 96));
    *(_QWORD *)(a1 + 96) = 0;
  }
  else if ( *(_WORD *)a1 == 2813 )
  {
    AfdSanCleanupHelper(a1);
  }
  v5 = *(void **)(a1 + 240);
  if ( v5 )
  {
    ExFreePoolWithTag(v5, 0x6C646641u);
    *(_QWORD *)(a1 + 240) = 0;
  }
  if ( *(_WORD *)a1 == 0xAFD1 )
  {
    v8 = *(void **)(a1 + 184);
    if ( v8 )
    {
      if ( *(_DWORD *)(a1 + 176) > (unsigned int)AfdStandardAddressLength )
        ExFreePoolWithTag(v8, 0x52646641u);
      else
        PplFreeToLookasideList(PplAddressPool, *(_QWORD *)(a1 + 184));
      *(_QWORD *)(a1 + 184) = 0;
    }
    v9 = *(struct _NDIS_RW_LOCK_EX **)(a1 + 168);
    if ( v9 )
    {
      NdisFreeRWLock(v9);
      *(_QWORD *)(a1 + 168) = 0;
    }
  }
  if ( *(_QWORD *)(a1 + 224) )
  {
    ExFreePoolWithTag(*(PVOID *)(a1 + 224), 0x58646641u);
    *(_QWORD *)(a1 + 224) = 0;
  }
  if ( ((*(_WORD *)a1 + 20528) & 0xFFF9) == 0 && (*(_DWORD *)(a1 + 8) & 0x100) == 0 )
  {
    v17 = *(void **)(a1 + 208);
    if ( v17 )
      AfdFreeConnectDataBuffers(v17);
  }
  v6 = *(void **)(a1 + 456);
  if ( v6 )
  {
    ObfDereferenceObject(v6);
    *(_QWORD *)(a1 + 456) = 0;
  }
  if ( *(_QWORD *)(a1 + 272) )
  {
    v14 = *(_QWORD *)(a1 + 272);
    if ( (*(_DWORD *)(a1 + 8) & 0x100) != 0 )
      AfdTlDereferenceTransport(v14);
    else
      AfdDereferenceTransport(v14);
    *(_QWORD *)(a1 + 272) = 0;
  }
  result = *(_DWORD *)(a1 + 8);
  if ( (result & 0x100) == 0 )
  {
    if ( (*(_DWORD *)(a1 + 8) & 0x200000) != 0 )
    {
      AfdDereferenceTransport(*(_QWORD *)(a1 + 280));
    }
    else
    {
      if ( (*(_DWORD *)(a1 + 8) & 0x400000) == 0 )
        goto LABEL_72;
      AfdDereferenceTransport(*(_QWORD *)(*(_QWORD *)(a1 + 280) + 24LL));
      *(_QWORD *)(*(_QWORD *)(a1 + 280) + 24LL) = 0;
      ExFreePoolWithTag(*(PVOID *)(a1 + 280), 0x56646641u);
    }
    *(_QWORD *)(a1 + 280) = 0;
LABEL_72:
    result = *(_DWORD *)(a1 + 8);
    if ( (result & 0x200) != 0 )
    {
      if ( *(_QWORD *)(a1 + 504) )
      {
        v24 = 0;
        Object = &Event;
        v23 = 0;
        v20 = 0;
        memset(&Event, 0, sizeof(Event));
        KeInitializeEvent(&Event, SynchronizationEvent, 0);
        v18 = *(_QWORD *)(a1 + 496);
        *(_QWORD *)&v20 = AfdSynchronousTlCloseRequestComplete;
        *((_QWORD *)&v20 + 1) = &Object;
        result = (**(__int64 (__fastcall ***)(__int64, __int128 *))(a1 + 504))(v18, &v20);
        if ( result == 259 )
          result = KeWaitForSingleObject(Object, Executive, 0, 0, 0);
      }
      v19 = *(_QWORD *)(a1 + 512);
      if ( v19 )
        result = AfdTlDereferenceTransport(v19);
    }
  }
  if ( (xmmword_1400875E0 & 8) != 0 )
    result = WPP_SF_q(1027, 12, WPP_b1ac8061ea4e33a65bcabadbb0b1b671_Traceguids, a1);
  *(_WORD *)a1 = -13571;
  return result;
}

```

## disassembly

```asm
0x140014934  push    rbp
0x140014936  push    rbx
0x140014937  push    rsi
0x140014938  push    rdi
0x140014939  push    r12
0x14001493b  push    r14
0x14001493d  push    r15
0x14001493f  mov     rbp, rsp
0x140014942  sub     rsp, 80h
0x140014949  movzx   eax, word ptr [rcx]
0x14001494c  mov     rbx, rcx
0x14001494f  mov     ecx, 0AFD4h
0x140014954  and     ax, cx
0x140014957  cmp     ax, cx
0x14001495a  jz      loc_140014C2A
0x140014960  mov     rcx, [rbx+50h]; P
0x140014964  xor     esi, esi
0x140014966  test    rcx, rcx
0x140014969  jnz     loc_140014C3A
0x14001496f  mov     eax, 0FA09h
0x140014974  cmp     [rbx], ax
0x140014977  jz      loc_140014C48
0x14001497d  mov     ecx, [rbx+1D0h]
0x140014983  test    ecx, ecx
0x140014985  jnz     loc_140014C55
0x14001498b  mov     r12d, 0AFD1h
0x140014991  cmp     [rbx], r12w
0x140014995  jz      loc_140014B39
0x14001499b  mov     eax, [rbx+8]
0x14001499e  mov     edi, 5030h
0x1400149a3  bt      eax, 8
0x1400149a7  mov     ecx, 0FFF9h
0x1400149ac  jnb     loc_140014C5F
0x1400149b2  mov     rcx, [rbx+28h]
0x1400149b6  test    rcx, rcx
0x1400149b9  jnz     loc_140014CAB
0x1400149bf  mov     [rbx+28h], rsi
0x1400149c3  mov     eax, [rbx+8]
0x1400149c6  bt      eax, 8
0x1400149ca  jnb     loc_140014B7E
0x1400149d0  mov     rcx, [rbx+58h]; P
0x1400149d4  test    rcx, rcx
0x1400149d7  jnz     loc_140014BF8
0x1400149dd  mov     rcx, rbx
0x1400149e0  call    AfdRemoveEndpointFromList
0x1400149e5  mov     eax, [rbx+8]
0x1400149e8  mov     edx, 200h; PoolType
0x1400149ed  mov     rcx, [rbx+30h]; Process
0x1400149f1  and     eax, 200h
0x1400149f6  neg     eax
0x1400149f8  sbb     r8, r8
0x1400149fb  and     r8d, 20h
0x1400149ff  add     r8, 1F0h; Amount
0x140014a06  call    cs:__imp_PsReturnPoolQuota
0x140014a0d  nop     dword ptr [rax+rax+00h]
0x140014a12  mov     rcx, [rbx+30h]; Object
0x140014a16  call    cs:__imp_ObfDereferenceObject
0x140014a1d  nop     dword ptr [rax+rax+00h]
0x140014a22  mov     eax, 0AFD2h
0x140014a27  mov     [rbx+30h], rsi
0x140014a2b  cmp     [rbx], ax
0x140014a2e  jz      loc_140014CC1
0x140014a34  movzx   eax, word ptr [rbx]
0x140014a37  mov     ecx, 1AFDh
0x140014a3c  cmp     ax, cx
0x140014a3f  jz      loc_140014CEF
0x140014a45  mov     ecx, 0AFDh
0x140014a4a  cmp     ax, cx
0x140014a4d  jz      loc_140014D01
0x140014a53  mov     rcx, [rbx+0F0h]; P
0x140014a5a  test    rcx, rcx
0x140014a5d  jnz     loc_140014C06
0x140014a63  cmp     [rbx], r12w
0x140014a67  jz      loc_140014B01
0x140014a6d  mov     rax, [rbx+0E0h]
0x140014a74  test    rax, rax
0x140014a77  jz      short loc_140014A98
0x140014a79  mov     rcx, [rbx+0E0h]; P
0x140014a80  mov     edx, 58646641h; Tag
0x140014a85  call    cs:__imp_ExFreePoolWithTag
0x140014a8c  nop     dword ptr [rax+rax+00h]
0x140014a91  mov     [rbx+0E0h], rsi
0x140014a98  add     di, [rbx]
0x140014a9b  mov     eax, 0FFF9h
0x140014aa0  test    ax, di
0x140014aa3  jnz     short loc_140014AB2
0x140014aa5  mov     eax, [rbx+8]
0x140014aa8  bt      eax, 8
0x140014aac  jnb     loc_140014D35
0x140014ab2  mov     rcx, [rbx+1C8h]; Object
0x140014ab9  test    rcx, rcx
0x140014abc  jnz     loc_140014D4F
0x140014ac2  cmp     [rbx+110h], rsi
0x140014ac9  jnz     loc_140014BD3
0x140014acf  mov     eax, [rbx+8]
0x140014ad2  bt      eax, 8
0x140014ad6  jnb     loc_140014D71
0x140014adc  test    byte ptr cs:xmmword_1400875E0, 8
0x140014ae3  jnz     loc_140014D90
0x140014ae9  mov     word ptr [rbx], 0CAFDh
0x140014aee  add     rsp, 80h
0x140014af5  pop     r15
0x140014af7  pop     r14
0x140014af9  pop     r12
0x140014afb  pop     rdi
0x140014afc  pop     rsi
0x140014afd  pop     rbx
0x140014afe  pop     rbp
0x140014aff  retn
0x140014b01  mov     rcx, [rbx+0B8h]; P
0x140014b08  test    rcx, rcx
0x140014b0b  jnz     loc_140014D0E
0x140014b11  mov     rcx, [rbx+0A8h]; Lock
0x140014b18  test    rcx, rcx
0x140014b1b  jz      loc_140014A6D
0x140014b21  call    cs:__imp_NdisFreeRWLock
0x140014b28  nop     dword ptr [rax+rax+00h]
0x140014b2d  mov     [rbx+0A8h], rsi
0x140014b34  jmp     loc_140014A6D
0x140014b39  lea     rdi, [rbx+80h]
0x140014b40  cmp     [rdi], rsi
0x140014b43  jz      loc_14001499B
0x140014b49  mov     rcx, [rdi]; Entry
0x140014b4c  cmp     rcx, rdi
0x140014b4f  jz      loc_14001499B
0x140014b55  cmp     [rcx+8], rdi
0x140014b59  jnz     loc_140014C23
0x140014b5f  mov     rax, [rcx]
0x140014b62  cmp     [rax+8], rcx
0x140014b66  jnz     loc_140014C23
0x140014b6c  mov     [rdi], rax
0x140014b6f  mov     [rax+8], rdi
0x140014b73  mov     rdx, [rbx+30h]; Process
0x140014b77  call    AfdReturnBuffer
0x140014b7c  jmp     short loc_140014B49
0x140014b7e  mov     rcx, [rbx+100h]; Handle
0x140014b85  test    rcx, rcx
0x140014b88  jz      loc_1400149D0
0x140014b8e  call    cs:__imp_ZwClose
0x140014b95  nop     dword ptr [rax+rax+00h]
0x140014b9a  mov     [rbx+100h], rsi
0x140014ba1  mov     eax, [rbx+8]
0x140014ba4  bt      eax, 16h
0x140014ba8  jnb     loc_1400149D0
0x140014bae  mov     rcx, [rbx+118h]
0x140014bb5  mov     rcx, [rcx]; Handle
0x140014bb8  call    cs:__imp_ZwClose
0x140014bbf  nop     dword ptr [rax+rax+00h]
0x140014bc4  mov     rax, [rbx+118h]
0x140014bcb  mov     [rax], rsi
0x140014bce  jmp     loc_1400149D0
0x140014bd3  mov     eax, [rbx+8]
0x140014bd6  bt      eax, 8
0x140014bda  mov     rcx, [rbx+110h]
0x140014be1  jnb     loc_140014D67
0x140014be7  call    AfdTlDereferenceTransport
0x140014bec  mov     [rbx+110h], rsi
0x140014bf3  jmp     loc_140014ACF
0x140014bf8  call    AfdDereferenceCompartment
0x140014bfd  mov     [rbx+58h], rsi
0x140014c01  jmp     loc_1400149DD
0x140014c06  mov     edx, 6C646641h; Tag
0x140014c0b  call    cs:__imp_ExFreePoolWithTag
0x140014c12  nop     dword ptr [rax+rax+00h]
0x140014c17  mov     [rbx+0F0h], rsi
0x140014c1e  jmp     loc_140014A63
0x140014c23  mov     ecx, 3
0x140014c28  int     29h; Win8: RtlFailFast(ecx)
0x140014c2a  mov     rcx, rbx
0x140014c2d  call    AfdFreeQueuedConnections
0x140014c32  mov     eax, [rbx+8]
0x140014c35  jmp     loc_140014960
0x140014c3a  call    AfdRioCleanupRioState
0x140014c3f  mov     [rbx+50h], rsi
0x140014c43  jmp     loc_14001496F
0x140014c48  mov     rcx, rbx
0x140014c4b  call    AfdRioCleanupRegistrationDomain
0x140014c50  jmp     loc_14001497D
0x140014c55  call    AfdDereferenceGroup
0x140014c5a  jmp     loc_14001498B
0x140014c5f  cmp     [rbx+18h], rsi
0x140014c63  jz      loc_1400149B2
0x140014c69  cmp     [rbx+100h], rsi
0x140014c70  jz      loc_14007607A
0x140014c76  mov     eax, edi
0x140014c78  add     ax, [rbx]
0x140014c7b  test    cx, ax
0x140014c7e  jnz     loc_14007607A
0x140014c84  xor     edx, edx
0x140014c86  mov     rcx, rbx
0x140014c89  call    AfdTdiClearVcEventHandlers
0x140014c8e  mov     eax, [rbx+8]
0x140014c91  bt      eax, 16h
0x140014c95  jnb     loc_14007607A
0x140014c9b  mov     dl, 1
0x140014c9d  mov     rcx, rbx
0x140014ca0  call    AfdTdiClearVcEventHandlers
0x140014ca5  nop
0x140014ca6  jmp     loc_14007607A
0x140014cab  mov     edx, 1
0x140014cb0  call    cs:__imp_ObDereferenceSecurityDescriptor
0x140014cb7  nop     dword ptr [rax+rax+00h]
0x140014cbc  jmp     loc_1400149BF
0x140014cc1  mov     rcx, [rbx+0C8h]
0x140014cc8  test    rcx, rcx
0x140014ccb  jz      loc_140014A34
0x140014cd1  call    AfdDereferenceEndpoint
0x140014cd6  mov     [rbx+0C8h], rsi
0x140014cdd  mov     [rbx+0F0h], rsi
0x140014ce4  mov     [rbx+0ECh], esi
0x140014cea  jmp     loc_140014A34
0x140014cef  mov     rcx, [rbx+60h]
0x140014cf3  call    AfdDereferenceEndpoint
0x140014cf8  mov     [rbx+60h], rsi
0x140014cfc  jmp     loc_140014A53
0x140014d01  mov     rcx, rbx
0x140014d04  call    AfdSanCleanupHelper
0x140014d09  jmp     loc_140014A53
0x140014d0e  mov     eax, cs:AfdStandardAddressLength
0x140014d14  cmp     [rbx+0B0h], eax
0x140014d1a  ja      loc_1400760D1
0x140014d20  mov     rdx, rcx
0x140014d23  mov     rcx, cs:PplAddressPool
0x140014d2a  call    PplFreeToLookasideList
0x140014d2f  nop
0x140014d30  jmp     loc_1400760E2
0x140014d35  mov     rcx, [rbx+0D0h]; P
0x140014d3c  test    rcx, rcx
0x140014d3f  jz      loc_140014AB2
0x140014d45  call    AfdFreeConnectDataBuffers
0x140014d4a  jmp     loc_140014AB2
0x140014d4f  call    cs:__imp_ObfDereferenceObject
0x140014d56  nop     dword ptr [rax+rax+00h]
0x140014d5b  mov     [rbx+1C8h], rsi
0x140014d62  jmp     loc_140014AC2
0x140014d67  call    AfdDereferenceTransport
0x140014d6c  jmp     loc_140014BEC
0x140014d71  mov     eax, [rbx+8]
0x140014d74  bt      eax, 15h
0x140014d78  jnb     loc_1400760EE
0x140014d7e  mov     rcx, [rbx+118h]
0x140014d85  call    AfdDereferenceTransport
0x140014d8a  nop
0x140014d8b  jmp     loc_14007612A
0x140014d90  mov     edx, 0Ch
0x140014d95  lea     r8, WPP_b1ac8061ea4e33a65bcabadbb0b1b671_Traceguids
0x140014d9c  mov     ecx, 403h
0x140014da1  mov     r9, rbx
0x140014da4  call    WPP_SF_q
0x140014da9  jmp     loc_140014AE9
0x14007607a  mov     rcx, [rbx+18h]; Object
0x14007607e  call    cs:__imp_ObfDereferenceObject
0x140076085  nop     dword ptr [rax+rax+00h]
0x14007608a  mov     [rbx+18h], rsi
0x14007608e  mov     [rbx+28h], rsi
0x140076092  mov     eax, [rbx+8]
0x140076095  bt      eax, 16h
0x140076099  jnb     loc_1400149C3
0x14007609f  mov     rcx, [rbx+118h]
0x1400760a6  mov     rcx, [rcx+8]; Object
0x1400760aa  call    cs:__imp_ObfDereferenceObject
0x1400760b1  nop     dword ptr [rax+rax+00h]
0x1400760b6  mov     rax, [rbx+118h]
0x1400760bd  mov     [rax+8], rsi
0x1400760c1  mov     rax, [rbx+118h]
0x1400760c8  mov     [rax+10h], rsi
0x1400760cc  jmp     loc_1400149C3
0x1400760d1  mov     edx, 52646641h; Tag
0x1400760d6  call    cs:__imp_ExFreePoolWithTag
0x1400760dd  nop     dword ptr [rax+rax+00h]
0x1400760e2  mov     [rbx+0B8h], rsi
0x1400760e9  jmp     loc_140014B11
0x1400760ee  mov     eax, [rbx+8]
0x1400760f1  bt      eax, 16h
0x1400760f5  jnb     short loc_140076131
0x1400760f7  mov     rcx, [rbx+118h]
0x1400760fe  mov     rcx, [rcx+18h]
0x140076102  call    AfdDereferenceTransport
0x140076107  mov     rax, [rbx+118h]
0x14007610e  mov     edx, 56646641h; Tag
0x140076113  mov     [rax+18h], rsi
0x140076117  mov     rcx, [rbx+118h]; P
0x14007611e  call    cs:__imp_ExFreePoolWithTag
0x140076125  nop     dword ptr [rax+rax+00h]
0x14007612a  mov     [rbx+118h], rsi
0x140076131  mov     eax, [rbx+8]
0x140076134  bt      eax, 9
0x140076138  jnb     loc_140014ADC
0x14007613e  cmp     [rbx+1F8h], rsi
0x140076145  jz      loc_1400761D8
0x14007614b  xor     eax, eax
0x14007614d  mov     [rbp+var_10], rsi
0x140076151  xorps   xmm0, xmm0
0x140076154  mov     [rbp+Event.Header.WaitListHead.Blink], rax
0x140076158  xor     r8d, r8d; State
0x14007615b  lea     rax, [rbp+Event]
0x14007615f  xorps   xmm1, xmm1
0x140076162  mov     [rbp+Object], rax
0x140076166  lea     rcx, [rbp+Event]; Event
0x14007616a  movdqu  [rbp+var_20], xmm0
  ... truncated ...
```
