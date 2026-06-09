# Smb2AddShare

- ea: `0x140062f50`
- end: `0x140063751`
- name: `Smb2AddShare`
- size: `2049`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140059540`

## callees

- `0x14000c450`
- `0x1400280ac`
- `0x140028708`
- `0x140029014`
- `0x140038680`
- `0x140038980`
- `0x140062f50`
- `0x140065ed0`
- `0x140076fd0`

## import_xrefs

- `ntoskrnl!PcwCreateInstance` at `0x140063628`
- `ntoskrnl!PcwCreateInstance` at `0x140063628`
- `ntoskrnl!ExAllocatePool2` at `0x140063001`
- `ntoskrnl!ExAllocatePool2` at `0x140063118`
- `ntoskrnl!ExAllocatePool2` at `0x14006323e`
- `ntoskrnl!ExAllocatePool2` at `0x1400632ab`
- `ntoskrnl!ExAllocatePool2` at `0x140063001`
- `ntoskrnl!ExAllocatePool2` at `0x140063118`
- `ntoskrnl!ExAllocatePool2` at `0x14006323e`
- `ntoskrnl!ExAllocatePool2` at `0x1400632ab`
- `ntoskrnl!ExDeleteResourceLite` at `0x140063084`
- `ntoskrnl!ExDeleteResourceLite` at `0x140063097`
- `ntoskrnl!ExDeleteResourceLite` at `0x140063084`
- `ntoskrnl!ExDeleteResourceLite` at `0x140063097`
- `ntoskrnl!ExReleaseResourceLite` at `0x140063565`
- `ntoskrnl!ExReleaseResourceLite` at `0x140063565`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400634fd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400634fd`
- `ntoskrnl!ExInitializeResourceLite` at `0x14006316b`
- `ntoskrnl!ExInitializeResourceLite` at `0x140063181`
- `ntoskrnl!ExInitializeResourceLite` at `0x14006316b`
- `ntoskrnl!ExInitializeResourceLite` at `0x140063181`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063041`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063062`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400630a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400630bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063041`
- `ntoskrnl!ExFreePoolWithTag` at `0x140063062`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400630a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400630bc`
- `ntoskrnl!EtwActivityIdControl` at `0x140063496`
- `ntoskrnl!EtwActivityIdControl` at `0x140063496`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400631ff`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400631ff`
- `ntoskrnl!RtlHashUnicodeString` at `0x140063474`
- `ntoskrnl!RtlHashUnicodeString` at `0x140063474`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140062fe2`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140063292`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400632ce`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140063402`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140062fe2`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140063292`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400632ce`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140063402`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140063641`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140063641`
- `srvnet!SrvLibGetBinary` at `0x1400635d3`
- `srvnet!SrvLibGetBinary` at `0x1400635d3`
- `ksecdd!BCryptGenRandom` at `0x1400634b3`
- `ksecdd!BCryptGenRandom` at `0x1400634b3`

## string_xrefs

- `0x1400635cc`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanServer\Parameters`

## pseudocode

```c
__int64 __fastcall Smb2AddShare(__int64 a1)
{
  NTSTATUS ShareQoSFlowID; // ebx
  int v3; // r14d
  _QWORD *Instance; // rbp
  __int16 *v5; // r15
  unsigned __int16 *v6; // r13
  _WORD *v7; // r12
  int v8; // ebx
  ULONG v9; // eax
  __int64 Pool2; // rax
  PVOID *v11; // rdi
  PVOID v12; // rcx
  PVOID v13; // rcx
  _QWORD *v15; // rax
  __int64 v16; // rax
  struct _EX_RUNDOWN_REF *v17; // rcx
  bool v18; // zf
  void *v19; // rax
  __int16 v20; // ax
  void *v21; // rcx
  ULONG v22; // eax
  __int64 v23; // rax
  ULONG v24; // eax
  __int16 v25; // cx
  __int64 i; // rcx
  __int16 v27; // ax
  __int64 v28; // rax
  char *v29; // rbx
  char *v30; // rbx
  __int16 v31; // ax
  char *v32; // rbx
  __int16 v33; // ax
  void *v34; // rbx
  ULONG v35; // eax
  char v36; // si
  __int64 v37; // r8
  _QWORD *v38; // rdx
  const void *v39; // rax
  ULONG TimeIncrement; // eax
  int v41; // r8d
  struct _PCW_DATA Data; // [rsp+70h] [rbp-48h] BYREF
  ULONG HashValue; // [rsp+C0h] [rbp+8h] BYREF
  int v44; // [rsp+C8h] [rbp+10h] BYREF

  HashValue = 0;
  if ( (*(_DWORD *)(a1 + 128) & 0x21000) == 0x21000 )
    return (unsigned int)-1073741811;
  v3 = (unsigned __int8)*(_DWORD *)(a1 + 124);
  if ( v3 == 2 )
    return (unsigned int)-1073741637;
  Instance = (_QWORD *)Srv2GetInstance(*(unsigned int *)(a1 + 152));
  if ( !Instance )
    return (unsigned int)-1073741811;
  v5 = (__int16 *)(a1 + 24);
  v6 = (unsigned __int16 *)(a1 + 56);
  v7 = (_WORD *)(a1 + 8);
  v8 = *(unsigned __int16 *)(a1 + 8)
     + *(unsigned __int16 *)(a1 + 56)
     + *(unsigned __int16 *)(a1 + 72)
     + *(unsigned __int16 *)(a1 + 24);
  v9 = RtlLengthSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a1 + 184));
  Pool2 = ExAllocatePool2(256, v9 + v8 + 454, 1748128588);
  v11 = (PVOID *)Pool2;
  if ( !Pool2 )
    goto LABEL_7;
  *(_QWORD *)(Pool2 + 408) = Instance;
  v15 = (_QWORD *)(Pool2 + 336);
  v15[1] = v15;
  *v15 = v15;
  v11[27] = v11 + 26;
  v11[26] = v11 + 26;
  v16 = ExAllocatePool2(64, 656, 1748128588);
  *v11 = (PVOID)v16;
  if ( !v16 )
    goto LABEL_7;
  *(_QWORD *)v16 = 1;
  *(_WORD *)(v16 + 16) = 656;
  *(_DWORD *)(v16 + 8) = 12;
  *(_DWORD *)(v16 + 12) = 220;
  *(_QWORD *)(v16 + 48) = 0;
  *(_QWORD *)(v16 + 56) = v16;
  *(_QWORD *)(v16 + 64) = Instance;
  *(_DWORD *)(v16 + 72) = 0;
  *((_QWORD *)*v11 + 11) = v11;
  ExInitializeResourceLite((PERESOURCE)((char *)*v11 + 96));
  ExInitializeResourceLite((PERESOURCE)((char *)*v11 + 200));
  v17 = (struct _EX_RUNDOWN_REF *)((char *)*v11 + 304);
  *((_BYTE *)v11 + 278) = (*(_DWORD *)(a1 + 124) & 0x100000) != 0;
  *((_DWORD *)v11 + 89) = *(_DWORD *)a1;
  *((_DWORD *)v11 + 73) = *(_DWORD *)(a1 + 128) & 0x30;
  *((_DWORD *)v11 + 72) = *(_DWORD *)(a1 + 128) & 0xFFFFFFCF;
  *((_DWORD *)v11 + 92) = *(_DWORD *)(a1 + 148);
  *((_DWORD *)v11 + 74) = *(_DWORD *)(a1 + 140);
  *((_DWORD *)v11 + 75) = *(_DWORD *)(a1 + 144);
  *((_DWORD *)v11 + 76) = 1;
  *((_BYTE *)v11 + 281) = 0;
  ExInitializeRundownProtection(v17);
  v18 = ((_DWORD)v11[46] & 0xE000000) == 0;
  Smb2BypassCSVFileOpenRundownInitialized = 1;
  if ( !v18 )
    Smb2IsRkfInstalled = 1;
  if ( *(_WORD *)(a1 + 200) )
  {
    v19 = (void *)ExAllocatePool2(258, *(unsigned __int16 *)(a1 + 200), 1748128588);
    v11[24] = v19;
    if ( !v19 )
      goto LABEL_7;
    memmove(v19, *(const void **)(a1 + 208), *(unsigned __int16 *)(a1 + 200));
    v20 = *(_WORD *)(a1 + 200);
    *((_WORD *)v11 + 93) = v20;
    *((_WORD *)v11 + 92) = v20;
  }
  v21 = *(void **)(a1 + 192);
  if ( v21 )
  {
    v22 = RtlLengthSecurityDescriptor(v21);
    v23 = ExAllocatePool2(258, v22, 1748128588);
    v11[33] = (PVOID)v23;
    if ( v23 )
    {
      v24 = RtlLengthSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a1 + 192));
      memmove(v11[33], *(const void **)(a1 + 192), v24);
      goto LABEL_26;
    }
LABEL_7:
    ShareQoSFlowID = -1073741670;
    goto LABEL_8;
  }
LABEL_26:
  *((_DWORD *)v11 + 68) = 1;
  v11[14] = v11 + 55;
  v25 = *v7 + *v5 + 6;
  *((_WORD *)v11 + 53) = v25;
  *((_WORD *)v11 + 52) = v25;
  for ( i = 0; i != 2; ++i )
    *((_WORD *)v11[14] + i) = 92;
  v27 = *v5;
  *((_WORD *)v11 + 45) = *v5;
  *((_WORD *)v11 + 44) = v27;
  v11[12] = (char *)v11 + 444;
  memmove((char *)v11 + 444, *(const void **)(a1 + 32), (unsigned __int16)*v5);
  v28 = (unsigned __int16)*v5;
  *(_WORD *)((char *)v11 + v28 + 444) = 92;
  v29 = (char *)v11 + v28 + 446;
  LOWORD(v28) = *v7;
  *((_WORD *)v11 + 37) = *v7;
  *((_WORD *)v11 + 36) = v28;
  v11[10] = v29;
  memmove(v29, *(const void **)(a1 + 16), (unsigned __int16)*v7);
  v30 = &v29[(unsigned __int16)*v7];
  v31 = *v6;
  *((_WORD *)v11 + 61) = *v6;
  *((_WORD *)v11 + 60) = v31;
  v11[16] = v30;
  memmove(v30, *(const void **)(a1 + 64), *v6);
  v32 = &v30[*v6];
  v33 = *(_WORD *)(a1 + 72);
  *((_WORD *)v11 + 77) = v33;
  *((_WORD *)v11 + 76) = v33;
  v11[20] = v32;
  memmove(v32, *(const void **)(a1 + 80), *(unsigned __int16 *)(a1 + 72));
  v34 = (void *)((unsigned __int64)&v32[*(unsigned __int16 *)(a1 + 72) + 7] & 0xFFFFFFFFFFFFFFF8uLL);
  v11[32] = v34;
  v35 = RtlLengthSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a1 + 184));
  memmove(v34, *(const void **)(a1 + 184), v35);
  *((_DWORD *)v11 + 34) = 0;
  v11[18] = 0;
  if ( v3 == 3 )
  {
    *((_DWORD *)v11 + 71) = 1;
  }
  else
  {
    if ( v3 != 1 )
    {
      *((_DWORD *)v11 + 71) = 0;
      goto LABEL_34;
    }
    *((_DWORD *)v11 + 71) = 127;
  }
  *((_DWORD *)v11 + 73) = 48;
LABEL_34:
  RtlHashUnicodeString((PCUNICODE_STRING)(v11 + 9), 1u, 0, &HashValue);
  *((_DWORD *)v11 + 51) = HashValue;
  EtwActivityIdControl(3u, (LPGUID)(v11 + 1));
  BCryptGenRandom(0, (PUCHAR)v11 + 384, 8u, 2u);
  *((_DWORD *)v11 + 104) = *(_DWORD *)(a1 + 216);
  *(_OWORD *)(v11 + 5) = *(_OWORD *)(a1 + 220);
  ShareQoSFlowID = Smb2GenerateShareQoSFlowID(v11);
  if ( ShareQoSFlowID >= 0 )
  {
    v36 = 0;
    ExAcquireResourceExclusiveLite((PERESOURCE)(Instance[20] + 2064LL), 1u);
    if ( Smb2NoShare )
    {
      Smb2NoShare = 0;
      v36 = 1;
    }
    v37 = Instance[20] + 16 * ((HashValue & 0x7F) + 1LL);
    v38 = *(_QWORD **)(v37 + 8);
    if ( *v38 != v37 )
      __fastfail(3u);
    v11[28] = (PVOID)v37;
    v11[29] = v38;
    *v38 = v11 + 28;
    *(_QWORD *)(v37 + 8) = v11 + 28;
    ExReleaseResourceLite((PERESOURCE)(Instance[20] + 2064LL));
    Smb2DfsIsShareInDfs(v11, (char *)v11 + 276, (char *)v11 + 277);
    if ( *((_BYTE *)v11 + 276) )
      *((_DWORD *)v11 + 72) |= 1u;
    if ( *((_BYTE *)v11 + 277) )
      *((_DWORD *)v11 + 72) |= 2u;
    if ( v36 )
    {
      v44 = 16;
      SrvLibGetBinary(
        L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
        L"Guid",
        &Smb2Guid,
        &v44);
    }
    memset((char *)*v11 + 312, 0, 0x158u);
    v39 = (char *)*v11 + 312;
    Data.Size = 344;
    Data.Data = v39;
    ShareQoSFlowID = PcwCreateInstance(
                       (PPCW_INSTANCE *)v11 + 50,
                       Srv2ShareCounters,
                       (PCUNICODE_STRING)(v11 + 13),
                       1u,
                       &Data);
    v11[53] = 0;
    TimeIncrement = KeQueryTimeIncrement();
    v11[54] = (PVOID)(0x861C46800uLL / TimeIncrement);
    if ( ShareQoSFlowID >= 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qZZZ(
          WPP_GLOBAL_Control->AttachedDevice,
          0x861C46800uLL % TimeIncrement,
          v41,
          (_DWORD)v11,
          (__int64)v5,
          (__int64)v7,
          (__int64)v6);
      }
      if ( (byte_14004C339 & 0x20) != 0 )
        McTemplateK0hzr0hzr2hzr4qqqqq_EtwWriteTransfer(
          *((_WORD *)v11 + 76) >> 1,
          (unsigned int)&SMB2_EVENT_SHARE_ADD,
          v41,
          *((_WORD *)v11 + 36) >> 1,
          (__int64)v11[10],
          *((_WORD *)v11 + 44) >> 1,
          (__int64)v11[12],
          *((_WORD *)v11 + 76) >> 1,
          (__int64)v11[20],
          *((_DWORD *)v11 + 73),
          *((_DWORD *)v11 + 92),
          *((_DWORD *)v11 + 72),
          *((_DWORD *)v11 + 75),
          *((_DWORD *)v11 + 74));
      if ( ((_DWORD)v11[46] & 0x5000000) != 0 )
        _InterlockedIncrement(&Smb2ScaleOutSharesCount);
      return (unsigned int)ShareQoSFlowID;
    }
  }
LABEL_8:
  Srv2DereferenceInstance(Instance);
  if ( v11 )
  {
    v12 = v11[24];
    if ( v12 )
    {
      ExFreePoolWithTag(v12, 0);
      v11[24] = 0;
    }
    v13 = v11[33];
    if ( v13 )
    {
      ExFreePoolWithTag(v13, 0);
      v11[33] = 0;
    }
    if ( *v11 )
    {
      ExDeleteResourceLite((PERESOURCE)((char *)*v11 + 200));
      ExDeleteResourceLite((PERESOURCE)((char *)*v11 + 96));
      ExFreePoolWithTag(*v11, 0);
      *v11 = 0;
    }
    ExFreePoolWithTag(v11, 0);
  }
  return (unsigned int)ShareQoSFlowID;
}

```

## disassembly

```asm
0x140062f50  mov     rax, rsp
0x140062f53  mov     [rax+18h], rbx
0x140062f57  push    rbp
0x140062f58  push    rsi
0x140062f59  push    rdi
0x140062f5a  push    r12
0x140062f5c  push    r13
0x140062f5e  push    r14
0x140062f60  push    r15
0x140062f62  sub     rsp, 80h
0x140062f69  xor     ebx, ebx
0x140062f6b  mov     rsi, rcx
0x140062f6e  mov     [rax+8], ebx
0x140062f71  mov     eax, [rcx+80h]
0x140062f77  mov     ecx, 21000h
0x140062f7c  and     eax, ecx
0x140062f7e  cmp     eax, ecx
0x140062f80  jnz     short loc_140062F8C
0x140062f82  mov     ebx, 0C000000Dh
0x140062f87  jmp     loc_1400630C8
0x140062f8c  mov     r14d, [rsi+7Ch]
0x140062f90  movzx   r14d, r14b
0x140062f94  cmp     r14d, 2
0x140062f98  jnz     short loc_140062FA4
0x140062f9a  mov     ebx, 0C00000BBh
0x140062f9f  jmp     loc_1400630C8
0x140062fa4  mov     ecx, [rsi+98h]
0x140062faa  call    Srv2GetInstance
0x140062faf  mov     rbp, rax
0x140062fb2  test    rax, rax
0x140062fb5  jz      short loc_140062F82
0x140062fb7  movzx   eax, word ptr [rsi+48h]
0x140062fbb  lea     r15, [rsi+18h]
0x140062fbf  movzx   ebx, word ptr [r15]
0x140062fc3  lea     r13, [rsi+38h]
0x140062fc7  mov     rcx, [rsi+0B8h]; SecurityDescriptor
0x140062fce  lea     r12, [rsi+8]
0x140062fd2  add     ebx, eax
0x140062fd4  movzx   eax, word ptr [r13+0]
0x140062fd9  add     ebx, eax
0x140062fdb  movzx   eax, word ptr [r12]
0x140062fe0  add     ebx, eax
0x140062fe2  call    cs:__imp_RtlLengthSecurityDescriptor
0x140062fe9  nop     dword ptr [rax+rax+00h]
0x140062fee  lea     edx, [rbx+1C6h]
0x140062ff4  mov     ecx, 100h
0x140062ff9  add     edx, eax
0x140062ffb  mov     r8d, 6832534Ch
0x140063001  call    cs:__imp_ExAllocatePool2
0x140063008  nop     dword ptr [rax+rax+00h]
0x14006300d  xor     ebx, ebx
0x14006300f  mov     rdi, rax
0x140063012  test    rax, rax
0x140063015  jnz     loc_1400630E6
0x14006301b  mov     ebx, 0C000009Ah
0x140063020  mov     rcx, rbp; Context
0x140063023  call    Srv2DereferenceInstance
0x140063028  xor     ebp, ebp
0x14006302a  test    rdi, rdi
0x14006302d  jz      loc_1400630C8
0x140063033  mov     rcx, [rdi+0C0h]; P
0x14006303a  test    rcx, rcx
0x14006303d  jz      short loc_140063054
0x14006303f  xor     edx, edx; Tag
0x140063041  call    cs:__imp_ExFreePoolWithTag
0x140063048  nop     dword ptr [rax+rax+00h]
0x14006304d  mov     [rdi+0C0h], rbp
0x140063054  mov     rcx, [rdi+108h]; P
0x14006305b  test    rcx, rcx
0x14006305e  jz      short loc_140063075
0x140063060  xor     edx, edx; Tag
0x140063062  call    cs:__imp_ExFreePoolWithTag
0x140063069  nop     dword ptr [rax+rax+00h]
0x14006306e  mov     [rdi+108h], rbp
0x140063075  mov     rcx, [rdi]
0x140063078  test    rcx, rcx
0x14006307b  jz      short loc_1400630B7
0x14006307d  add     rcx, 0C8h; Resource
0x140063084  call    cs:__imp_ExDeleteResourceLite
0x14006308b  nop     dword ptr [rax+rax+00h]
0x140063090  mov     rcx, [rdi]
0x140063093  add     rcx, 60h ; '`'; Resource
0x140063097  call    cs:__imp_ExDeleteResourceLite
0x14006309e  nop     dword ptr [rax+rax+00h]
0x1400630a3  mov     rcx, [rdi]; P
0x1400630a6  xor     edx, edx; Tag
0x1400630a8  call    cs:__imp_ExFreePoolWithTag
0x1400630af  nop     dword ptr [rax+rax+00h]
0x1400630b4  mov     [rdi], rbp
0x1400630b7  xor     edx, edx; Tag
0x1400630b9  mov     rcx, rdi; P
0x1400630bc  call    cs:__imp_ExFreePoolWithTag
0x1400630c3  nop     dword ptr [rax+rax+00h]
0x1400630c8  mov     eax, ebx
0x1400630ca  mov     rbx, [rsp+0B8h+arg_10]
0x1400630d2  add     rsp, 80h
0x1400630d9  pop     r15
0x1400630db  pop     r14
0x1400630dd  pop     r13
0x1400630df  pop     r12
0x1400630e1  pop     rdi
0x1400630e2  pop     rsi
0x1400630e3  pop     rbp
0x1400630e4  retn
0x1400630e6  mov     [rax+198h], rbp
0x1400630ed  mov     edx, 290h
0x1400630f2  add     rax, 150h
0x1400630f8  mov     ecx, 40h ; '@'
0x1400630fd  mov     r8d, 6832534Ch
0x140063103  mov     [rax+8], rax
0x140063107  mov     [rax], rax
0x14006310a  lea     rax, [rdi+0D0h]
0x140063111  mov     [rax+8], rax
0x140063115  mov     [rax], rax
0x140063118  call    cs:__imp_ExAllocatePool2
0x14006311f  nop     dword ptr [rax+rax+00h]
0x140063124  mov     [rdi], rax
0x140063127  test    rax, rax
0x14006312a  jz      loc_14006301B
0x140063130  mov     qword ptr [rax], 1
0x140063137  mov     ecx, 290h
0x14006313c  mov     [rax+10h], cx
0x140063140  mov     dword ptr [rax+8], 0Ch
0x140063147  mov     dword ptr [rax+0Ch], 0DCh
0x14006314e  mov     [rax+30h], rbx
0x140063152  mov     [rax+38h], rax
0x140063156  mov     [rax+40h], rbp
0x14006315a  mov     [rax+48h], ebx
0x14006315d  mov     rax, [rdi]
0x140063160  mov     [rax+58h], rdi
0x140063164  mov     rcx, [rdi]
0x140063167  add     rcx, 60h ; '`'; Resource
0x14006316b  call    cs:__imp_ExInitializeResourceLite
0x140063172  nop     dword ptr [rax+rax+00h]
0x140063177  mov     rcx, [rdi]
0x14006317a  add     rcx, 0C8h; Resource
0x140063181  call    cs:__imp_ExInitializeResourceLite
0x140063188  nop     dword ptr [rax+rax+00h]
0x14006318d  mov     eax, [rsi+7Ch]
0x140063190  mov     rcx, [rdi]
0x140063193  shr     eax, 14h
0x140063196  add     rcx, 130h; RunRef
0x14006319d  and     al, 1
0x14006319f  mov     [rdi+116h], al
0x1400631a5  mov     eax, [rsi]
0x1400631a7  mov     [rdi+164h], eax
0x1400631ad  mov     eax, [rsi+80h]
0x1400631b3  and     eax, 30h
0x1400631b6  mov     [rdi+124h], eax
0x1400631bc  mov     eax, [rsi+80h]
0x1400631c2  and     eax, 0FFFFFFCFh
0x1400631c5  mov     [rdi+120h], eax
0x1400631cb  mov     eax, [rsi+94h]
0x1400631d1  mov     [rdi+170h], eax
0x1400631d7  mov     eax, [rsi+8Ch]
0x1400631dd  mov     [rdi+128h], eax
0x1400631e3  mov     eax, [rsi+90h]
0x1400631e9  mov     [rdi+12Ch], eax
0x1400631ef  mov     dword ptr [rdi+130h], 1
0x1400631f9  mov     [rdi+119h], bl
0x1400631ff  call    cs:__imp_ExInitializeRundownProtection
0x140063206  nop     dword ptr [rax+rax+00h]
0x14006320b  test    dword ptr [rdi+170h], 0E000000h
0x140063215  mov     cs:Smb2BypassCSVFileOpenRundownInitialized, 1
0x14006321c  jz      short loc_140063225
0x14006321e  mov     cs:Smb2IsRkfInstalled, 1
0x140063225  movzx   eax, word ptr [rsi+0C8h]
0x14006322c  test    ax, ax
0x14006322f  jz      short loc_140063286
0x140063231  mov     edx, eax
0x140063233  mov     ecx, 102h
0x140063238  mov     r8d, 6832534Ch
0x14006323e  call    cs:__imp_ExAllocatePool2
0x140063245  nop     dword ptr [rax+rax+00h]
0x14006324a  mov     [rdi+0C0h], rax
0x140063251  test    rax, rax
0x140063254  jz      loc_14006301B
0x14006325a  movzx   r8d, word ptr [rsi+0C8h]; Size
0x140063262  mov     rcx, rax; void *
0x140063265  mov     rdx, [rsi+0D0h]; Src
0x14006326c  call    memmove
0x140063271  movzx   eax, word ptr [rsi+0C8h]
0x140063278  mov     [rdi+0BAh], ax
0x14006327f  mov     [rdi+0B8h], ax
0x140063286  mov     rcx, [rsi+0C0h]; SecurityDescriptor
0x14006328d  test    rcx, rcx
0x140063290  jz      short loc_1400632F0
0x140063292  call    cs:__imp_RtlLengthSecurityDescriptor
0x140063299  nop     dword ptr [rax+rax+00h]
0x14006329e  mov     edx, eax
0x1400632a0  mov     ecx, 102h
0x1400632a5  mov     r8d, 6832534Ch
0x1400632ab  call    cs:__imp_ExAllocatePool2
0x1400632b2  nop     dword ptr [rax+rax+00h]
0x1400632b7  mov     [rdi+108h], rax
0x1400632be  test    rax, rax
0x1400632c1  jz      loc_14006301B
0x1400632c7  mov     rcx, [rsi+0C0h]; SecurityDescriptor
0x1400632ce  call    cs:__imp_RtlLengthSecurityDescriptor
0x1400632d5  nop     dword ptr [rax+rax+00h]
0x1400632da  mov     rdx, [rsi+0C0h]; Src
0x1400632e1  mov     rcx, [rdi+108h]; void *
0x1400632e8  mov     r8d, eax; Size
0x1400632eb  call    memmove
0x1400632f0  mov     dword ptr [rdi+110h], 1
0x1400632fa  lea     rbx, [rdi+1B8h]
0x140063301  mov     [rdi+70h], rbx
0x140063305  movzx   ecx, word ptr [r15]
0x140063309  add     cx, 6
0x14006330d  add     cx, [r12]
0x140063312  mov     [rdi+6Ah], cx
0x140063316  mov     [rdi+68h], cx
0x14006331a  xor     ecx, ecx
0x14006331c  mov     rax, [rdi+70h]
0x140063320  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x140063326  inc     rcx
0x140063329  cmp     rcx, 2
0x14006332d  jnz     short loc_14006331C
0x14006332f  movzx   eax, word ptr [r15]
0x140063333  add     rbx, 4
0x140063337  mov     [rdi+5Ah], ax
0x14006333b  mov     rcx, rbx; void *
0x14006333e  mov     [rdi+58h], ax
0x140063342  mov     [rdi+60h], rbx
0x140063346  movzx   r8d, word ptr [r15]; Size
0x14006334a  mov     rdx, [rsi+20h]; Src
0x14006334e  call    memmove
0x140063353  movzx   eax, word ptr [r15]
0x140063357  mov     word ptr [rax+rbx], 5Ch ; '\'
0x14006335d  add     rbx, 2
0x140063361  add     rbx, rax
0x140063364  movzx   eax, word ptr [r12]
0x140063369  mov     [rdi+4Ah], ax
0x14006336d  mov     rcx, rbx; void *
0x140063370  mov     [rdi+48h], ax
0x140063374  mov     [rdi+50h], rbx
0x140063378  movzx   r8d, word ptr [r12]; Size
0x14006337d  mov     rdx, [rsi+10h]; Src
0x140063381  call    memmove
0x140063386  movzx   eax, word ptr [r12]
0x14006338b  add     rbx, rax
0x14006338e  movzx   eax, word ptr [r13+0]
0x140063393  mov     [rdi+7Ah], ax
0x140063397  mov     rcx, rbx; void *
0x14006339a  mov     [rdi+78h], ax
0x14006339e  mov     [rdi+80h], rbx
0x1400633a5  movzx   r8d, word ptr [r13+0]; Size
0x1400633aa  mov     rdx, [rsi+40h]; Src
0x1400633ae  call    memmove
0x1400633b3  movzx   eax, word ptr [r13+0]
0x1400633b8  add     rbx, rax
0x1400633bb  movzx   eax, word ptr [rsi+48h]
0x1400633bf  mov     [rdi+9Ah], ax
0x1400633c6  mov     rcx, rbx; void *
0x1400633c9  mov     [rdi+98h], ax
0x1400633d0  mov     [rdi+0A0h], rbx
0x1400633d7  movzx   r8d, word ptr [rsi+48h]; Size
0x1400633dc  mov     rdx, [rsi+50h]; Src
0x1400633e0  call    memmove
0x1400633e5  movzx   eax, word ptr [rsi+48h]
0x1400633e9  add     rax, 7
0x1400633ed  add     rbx, rax
0x1400633f0  and     rbx, 0FFFFFFFFFFFFFFF8h
0x1400633f4  mov     [rdi+100h], rbx
0x1400633fb  mov     rcx, [rsi+0B8h]; SecurityDescriptor
0x140063402  call    cs:__imp_RtlLengthSecurityDescriptor
0x140063409  nop     dword ptr [rax+rax+00h]
0x14006340e  mov     rdx, [rsi+0B8h]; Src
0x140063415  mov     rcx, rbx; void *
0x140063418  mov     r8d, eax; Size
0x14006341b  call    memmove
0x140063420  xor     ecx, ecx
0x140063422  mov     [rdi+88h], ecx
0x140063428  mov     [rdi+90h], rcx
0x14006342f  cmp     r14d, 3
0x140063433  jnz     short loc_140063441
0x140063435  mov     dword ptr [rdi+11Ch], 1
0x14006343f  jmp     short loc_140063451
0x140063441  cmp     r14d, 1
0x140063445  jnz     short loc_14006345D
0x140063447  mov     dword ptr [rdi+11Ch], 7Fh
0x140063451  mov     dword ptr [rdi+124h], 30h ; '0'
0x14006345b  jmp     short loc_140063463
0x14006345d  mov     [rdi+11Ch], ecx
0x140063463  lea     r9, [rsp+0B8h+HashValue]; HashValue
0x14006346b  xor     r8d, r8d; HashAlgorithm
0x14006346e  mov     dl, 1; CaseInSensitive
0x140063470  lea     rcx, [rdi+48h]; String
0x140063474  call    cs:__imp_RtlHashUnicodeString
0x14006347b  nop     dword ptr [rax+rax+00h]
0x140063480  mov     eax, [rsp+0B8h+HashValue]
0x140063487  lea     rdx, [rdi+8]; ActivityId
0x14006348b  mov     ecx, 3; ControlCode
0x140063490  mov     [rdi+0CCh], eax
0x140063496  call    cs:__imp_EtwActivityIdControl
0x14006349d  nop     dword ptr [rax+rax+00h]
0x1400634a2  xor     ecx, ecx; hAlgorithm
0x1400634a4  lea     rdx, [rdi+180h]; pbBuffer
0x1400634ab  lea     r9d, [rcx+2]; dwFlags
0x1400634af  lea     r8d, [rcx+8]; cbBuffer
  ... truncated ...
```
