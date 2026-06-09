# VidSynicPortCreateGuestEntry

- ea: `0x1400974dc`
- end: `0x1400979ee`
- name: `VidSynicPortCreateGuestEntry`
- size: `1298`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x140035708`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x140008990`
- `0x14000a010`
- `0x140021c60`
- `0x1400248f4`
- `0x140030990`
- `0x1400309d0`
- `0x1400386a0`
- `0x1400974dc`
- `0x140098b5c`
- `0x140098cf8`
- `0x140098d34`
- `0x140098dd4`
- `0x1400f1ea0`
- `0x1400f2a00`

## import_xrefs

- `ntoskrnl!MmGetPhysicalAddress` at `0x1400977c3`
- `ntoskrnl!MmGetPhysicalAddress` at `0x1400977c3`
- `ntoskrnl!ExAllocatePool2` at `0x140097627`
- `ntoskrnl!ExAllocatePool2` at `0x140097781`
- `ntoskrnl!ExAllocatePool2` at `0x140097627`
- `ntoskrnl!ExAllocatePool2` at `0x140097781`
- `winhvr!WinHvGetPortProperty` at `0x14009773a`
- `winhvr!WinHvGetPortProperty` at `0x14009773a`
- `winhvr!WinHvDisconnectPort` at `0x140097952`
- `winhvr!WinHvDisconnectPort` at `0x140097952`
- `winhvr!WinHvConnectPort` at `0x14009789a`
- `winhvr!WinHvConnectPort` at `0x14009789a`
- `winhvr!WinHvDeletePort` at `0x140097979`
- `winhvr!WinHvDeletePort` at `0x140097979`
- `winhvr!WinHvCreatePort` at `0x1400976db`
- `winhvr!WinHvCreatePort` at `0x1400976db`
- `winhvr!WinHvAllocatePortId` at `0x140097808`
- `winhvr!WinHvAllocatePortId` at `0x140097808`

## string_xrefs

- `0x140097595`: `VidSynicPortCreateGuestEntry`
- `0x140097648`: `VidSynicPortCreateGuestEntry`
- `0x1400976fa`: `VidSynicPortCreateGuestEntry`
- `0x140097759`: `VidSynicPortCreateGuestEntry`
- `0x1400977a3`: `VidSynicPortCreateGuestEntry`
- `0x140097827`: `VidSynicPortCreateGuestEntry`
- `0x1400978b9`: `VidSynicPortCreateGuestEntry`
- `0x1400978f4`: `VidSynicPortCreateGuestEntry`
- `0x1400979bf`: `VidSynicPortCreateGuestEntry`

## pseudocode

```c
__int64 __fastcall VidSynicPortCreateGuestEntry(
        __int64 a1,
        unsigned __int8 a2,
        char a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        __int64 a7,
        __int64 *a8)
{
  unsigned int v10; // r14d
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  int PortProperty; // edi
  __int64 Pool2; // rax
  __int64 v16; // rbx
  char v17; // r15
  __int64 v18; // rdx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  __int64 v21; // rcx
  bool v22; // r14
  PHYSICAL_ADDRESS PhysicalAddress; // rax
  void *v24; // rax
  char v25; // r12
  __int64 v26; // rax
  int v28; // [rsp+30h] [rbp-D0h]
  int v29; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v30; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v31; // [rsp+48h] [rbp-B8h] BYREF
  PHYSICAL_ADDRESS v32; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v33; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v34; // [rsp+68h] [rbp-98h]
  __int64 *v35; // [rsp+70h] [rbp-90h]
  __int128 v36; // [rsp+78h] [rbp-88h] BYREF
  char v37[32]; // [rsp+90h] [rbp-70h] BYREF
  char v38[16]; // [rsp+B0h] [rbp-50h] BYREF
  char v39[16]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v40; // [rsp+D0h] [rbp-30h]
  __int64 v41; // [rsp+D8h] [rbp-28h]
  unsigned int *v42; // [rsp+E0h] [rbp-20h]
  __int64 v43; // [rsp+E8h] [rbp-18h]

  v35 = a8;
  v36 = 0;
  v10 = a2;
  HviGetHypervisorFeatures(&v36);
  v12 = *(_DWORD *)a7;
  v34 = 0;
  v32.QuadPart = 0;
  v31 = -1;
  v29 = 0xFFFFFF;
  v33 = 0;
  v13 = v12 - 1;
  if ( v13 && v13 != 2 )
  {
    if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
    {
      tlgCreate1Sz_char(v38, "VidSynicPortCreateGuestEntry");
      tlgCreate1Sz_char(v39, "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c");
      LODWORD(v31) = 625;
      v40 = &v31;
      v30 = *(_DWORD *)a7;
      v41 = 4;
      v42 = &v30;
      v43 = 4;
      tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_14004945E, 0, 0, 6, v37);
    }
    PortProperty = -1073741637;
    goto LABEL_49;
  }
  Pool2 = ExAllocatePool2(65, 136, 1917084758);
  v16 = Pool2;
  if ( !Pool2 )
  {
    VidTraceErrorInternal0("VidSynicPortCreateGuestEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 640);
    PortProperty = -1073741801;
LABEL_49:
    VidTraceErrorStatusPartitionInternal0(
      (unsigned int)"VidSynicPortCreateGuestEntry",
      (unsigned int)"onecore\\vm\\vid\\sys\\driver\\vidsynicport.c",
      844,
      PortProperty,
      a1 + 656);
    return (unsigned int)PortProperty;
  }
  v17 = 1;
  v18 = v10;
  *(_DWORD *)Pool2 = *(_DWORD *)a7;
  *(_BYTE *)(Pool2 + 40) = 1;
  *(_DWORD *)(Pool2 + 4) = a6;
  v19 = *(_DWORD *)a7;
  v33 = 0;
  LODWORD(v33) = v19;
  v30 = v10 | 0x80000000;
  v34 = 0;
  v20 = v19 - 1;
  if ( v20 )
  {
    if ( v20 == 2 )
    {
      *(_QWORD *)(Pool2 + 120) = Pool2 + 112;
      *(_QWORD *)(Pool2 + 112) = Pool2 + 112;
      *((_QWORD *)&v33 + 1) = *(_QWORD *)(a7 + 8);
    }
  }
  else
  {
    *((_QWORD *)&v33 + 1) = __PAIR64__(a5, a4);
  }
  LODWORD(v18) = v10 | 0x80000000;
  PortProperty = WinHvCreatePort(*(_QWORD *)(a1 + 648), v18, a6, -1, &v33, a3, 0);
  if ( PortProperty < 0 )
  {
    VidTraceErrorInternal0("VidSynicPortCreateGuestEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 683);
LABEL_45:
    if ( *(_DWORD *)v16 == 3 )
      VidSynicPortpUnmapMonitorPage(v16);
    VidSynicPortpEntryFree(v21, v16);
    goto LABEL_48;
  }
  v22 = (v36 & 0x100000000000LL) != 0;
  if ( *(_DWORD *)a7 == 3 )
  {
    if ( (v36 & 0x100000000000LL) != 0 )
    {
      PortProperty = WinHvGetPortProperty(*(_QWORD *)(a1 + 648), *(unsigned int *)(v16 + 4), 2, &v32);
      if ( PortProperty < 0 )
      {
        VidTraceErrorInternal0("VidSynicPortCreateGuestEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 703);
        goto LABEL_45;
      }
      PhysicalAddress = v32;
    }
    else
    {
      v24 = (void *)ExAllocatePool2(65, 4096, 1917084758);
      *(_QWORD *)(v16 + 104) = v24;
      if ( !v24 )
      {
        VidTraceErrorInternal0("VidSynicPortCreateGuestEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 725);
        PortProperty = -1073741801;
        goto LABEL_45;
      }
      *(_BYTE *)(v16 + 128) = 1;
      PhysicalAddress = MmGetPhysicalAddress(v24);
    }
    *(PHYSICAL_ADDRESS *)(a7 + 8) = PhysicalAddress;
  }
  v25 = 0;
  VidLockAcquireExclusive(a1 + 3328);
  PortProperty = VidHandleTableAllocateEntry(a1 + 3296, v16, &v31);
  if ( PortProperty >= 0 )
  {
    PortProperty = WinHvAllocatePortId(v16, &v29);
    if ( PortProperty < 0 )
    {
      VidTraceErrorInternal0("VidSynicPortCreateGuestEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 752);
      goto LABEL_38;
    }
    *(_DWORD *)(v16 + 8) = v29;
    v36 = 0;
    HviGetHypervisorFeatures(&v36);
    if ( (v36 & 0x100000000LL) != 0 && !v22 )
      *(_DWORD *)(v16 + 8) = *(_DWORD *)(v16 + 8) & 0x3FFFFFFF | 0x40000000;
    LOBYTE(v28) = 0;
    PortProperty = WinHvConnectPort(
                     -1,
                     v30,
                     *(unsigned int *)(v16 + 8),
                     *(_QWORD *)(a1 + 648),
                     *(_DWORD *)(v16 + 4),
                     a7,
                     v28);
    if ( PortProperty < 0 )
    {
      VidTraceErrorInternal0("VidSynicPortCreateGuestEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 778);
      goto LABEL_38;
    }
    if ( *(_DWORD *)a7 == 3 )
    {
      if ( v22 )
      {
        PortProperty = ((__int64 (__fastcall *)(_QWORD, _QWORD))VidSynicPortpMapMonitorPage)(
                         v16,
                         (PHYSICAL_ADDRESS)v32.QuadPart);
        if ( PortProperty < 0 )
        {
          v25 = 1;
          VidTraceErrorInternal0("VidSynicPortCreateGuestEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 793);
          goto LABEL_38;
        }
      }
      VidSynicPortpInitializeMonitorPage(v16);
    }
    v26 = v31;
    v17 = 0;
    v16 = 0;
    v29 |= 0xFFFFFFu;
    v31 = -1;
    PortProperty = 0;
    *v35 = v26;
  }
LABEL_38:
  if ( v31 != -1 )
    VidHandleTableFreeEntry(a1 + 3296);
  if ( v25 )
    WinHvDisconnectPort(-1, *(unsigned int *)(v16 + 8));
  VidLockRelease(a1 + 3328);
  if ( v17 )
    WinHvDeletePort(*(_QWORD *)(a1 + 648), *(unsigned int *)(v16 + 4));
  if ( v16 )
    goto LABEL_45;
LABEL_48:
  if ( PortProperty < 0 )
    goto LABEL_49;
  return (unsigned int)PortProperty;
}

```

## disassembly

```asm
0x1400974dc  push    rbp
0x1400974de  push    rbx
0x1400974df  push    rsi
0x1400974e0  push    rdi
0x1400974e1  push    r12
0x1400974e3  push    r13
0x1400974e5  push    r14
0x1400974e7  push    r15
0x1400974e9  lea     rbp, [rsp-8]
0x1400974ee  sub     rsp, 108h
0x1400974f5  mov     rax, cs:__security_cookie
0x1400974fc  xor     rax, rsp
0x1400974ff  mov     [rbp+40h+var_50], rax
0x140097503  mov     rax, [rbp+40h+arg_38]
0x14009750a  mov     r13, rcx
0x14009750d  mov     rsi, [rbp+40h+arg_30]
0x140097514  lea     rcx, [rsp+140h+var_C8]
0x140097519  xorps   xmm0, xmm0
0x14009751c  mov     [rsp+140h+var_D0], rax
0x140097521  movups  [rsp+140h+var_C8], xmm0
0x140097526  mov     edi, r9d
0x140097529  movzx   r14d, dl
0x14009752d  mov     r12b, r8b
0x140097530  call    HviGetHypervisorFeatures
0x140097535  mov     ecx, [rsi]
0x140097537  xor     eax, eax
0x140097539  xor     r15d, r15d
0x14009753c  mov     [rsp+140h+var_D8], rax
0x140097541  mov     [rsp+140h+var_F0], r15
0x140097546  xorps   xmm1, xmm1
0x140097549  mov     [rsp+140h+var_F8], 0FFFFFFFFFFFFFFFFh
0x140097552  mov     [rsp+140h+var_100], 0FFFFFFh
0x14009755a  movups  [rsp+140h+var_E8], xmm1
0x14009755f  sub     ecx, 1
0x140097562  jz      loc_140097619
0x140097568  cmp     ecx, 2
0x14009756b  jz      loc_140097619
0x140097571  mov     eax, cs:dword_140065110
0x140097577  cmp     eax, 2
0x14009757a  jbe     loc_14009760F
0x140097580  mov     edx, 100h
0x140097585  lea     rcx, dword_140065110
0x14009758c  call    _tlgKeywordOn
0x140097591  test    al, al
0x140097593  jz      short loc_14009760F
0x140097595  lea     rdx, aVidsynicportcr_0; "VidSynicPortCreateGuestEntry"
0x14009759c  lea     rcx, [rbp+40h+var_90]
0x1400975a0  call    _tlgCreate1Sz_char
0x1400975a5  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x1400975ac  lea     rcx, [rbp+40h+var_80]
0x1400975b0  call    _tlgCreate1Sz_char
0x1400975b5  lea     rax, [rsp+140h+var_F8]
0x1400975ba  mov     dword ptr [rsp+140h+var_F8], 271h
0x1400975c2  mov     [rbp+40h+var_70], rax
0x1400975c6  lea     rdx, unk_14004945E
0x1400975cd  mov     eax, [rsi]
0x1400975cf  lea     rcx, dword_140065110
0x1400975d6  mov     [rsp+140h+var_FC], eax
0x1400975da  xor     r9d, r9d
0x1400975dd  lea     rax, [rsp+140h+var_FC]
0x1400975e2  mov     [rbp+40h+var_68], 4
0x1400975ea  mov     [rbp+40h+var_60], rax
0x1400975ee  xor     r8d, r8d
0x1400975f1  lea     rax, [rbp+40h+var_B0]
0x1400975f5  mov     [rbp+40h+var_58], 4
0x1400975fd  mov     [rsp+140h+var_118], rax
0x140097602  mov     dword ptr [rsp+140h+var_120], 6
0x14009760a  call    _tlgWriteTransfer_EtwWriteTransfer
0x14009760f  mov     edi, 0C00000BBh
0x140097614  jmp     loc_1400979A3
0x140097619  mov     edx, 88h
0x14009761e  mov     r8d, 72446456h
0x140097624  lea     ecx, [rdx-47h]
0x140097627  call    cs:__imp_ExAllocatePool2
0x14009762e  nop     dword ptr [rax+rax+00h]
0x140097633  mov     rbx, rax
0x140097636  test    rax, rax
0x140097639  jnz     short loc_14009765E
0x14009763b  mov     r8d, 280h
0x140097641  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x140097648  lea     rcx, aVidsynicportcr_0; "VidSynicPortCreateGuestEntry"
0x14009764f  call    VidTraceErrorInternal0
0x140097654  mov     edi, 0C0000017h
0x140097659  jmp     loc_1400979A3
0x14009765e  mov     eax, [rsi]
0x140097660  mov     r15b, 1
0x140097663  mov     r8d, [rbp+40h+arg_28]
0x140097667  mov     edx, r14d
0x14009766a  mov     [rbx], eax
0x14009766c  bts     edx, 1Fh
0x140097670  mov     [rbx+28h], r15b
0x140097674  xor     eax, eax
0x140097676  mov     [rbx+4], r8d
0x14009767a  xorps   xmm0, xmm0
0x14009767d  mov     ecx, [rsi]
0x14009767f  movups  [rsp+140h+var_E8], xmm0
0x140097684  mov     dword ptr [rsp+140h+var_E8], ecx
0x140097688  mov     [rsp+140h+var_FC], edx
0x14009768c  mov     [rsp+140h+var_D8], rax
0x140097691  sub     ecx, 1
0x140097694  jz      short loc_1400976B1
0x140097696  cmp     ecx, 2
0x140097699  jnz     short loc_1400976BC
0x14009769b  lea     rax, [rbx+70h]
0x14009769f  mov     [rax+8], rax
0x1400976a3  mov     [rax], rax
0x1400976a6  mov     rax, [rsi+8]
0x1400976aa  mov     qword ptr [rsp+140h+var_E8+8], rax
0x1400976af  jmp     short loc_1400976BC
0x1400976b1  mov     eax, [rbp+40h+arg_20]
0x1400976b4  mov     dword ptr [rsp+140h+var_E8+0Ch], eax
0x1400976b8  mov     dword ptr [rsp+140h+var_E8+8], edi
0x1400976bc  mov     rcx, [r13+288h]
0x1400976c3  lea     rax, [rsp+140h+var_E8]
0x1400976c8  mov     byte ptr [rsp+140h+var_110], 0
0x1400976cd  or      r9, 0FFFFFFFFFFFFFFFFh
0x1400976d1  mov     byte ptr [rsp+140h+var_118], r12b
0x1400976d6  mov     [rsp+140h+var_120], rax
0x1400976db  call    cs:__imp_WinHvCreatePort
0x1400976e2  nop     dword ptr [rax+rax+00h]
0x1400976e7  mov     edi, eax
0x1400976e9  test    eax, eax
0x1400976eb  jns     short loc_14009770B
0x1400976ed  mov     r8d, 2ABh
0x1400976f3  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x1400976fa  lea     rcx, aVidsynicportcr_0; "VidSynicPortCreateGuestEntry"
0x140097701  call    VidTraceErrorInternal0
0x140097706  jmp     loc_14009798A
0x14009770b  mov     r14, qword ptr [rsp+140h+var_C8]
0x140097710  shr     r14, 2Ch
0x140097714  and     r14b, r15b
0x140097717  cmp     dword ptr [rsi], 3
0x14009771a  jnz     loc_1400977D3
0x140097720  test    r14b, r14b
0x140097723  jz      short loc_140097771
0x140097725  mov     edx, [rbx+4]
0x140097728  lea     r9, [rsp+140h+var_F0]
0x14009772d  mov     rcx, [r13+288h]
0x140097734  mov     r8d, 2
0x14009773a  call    cs:__imp_WinHvGetPortProperty
0x140097741  nop     dword ptr [rax+rax+00h]
0x140097746  mov     edi, eax
0x140097748  test    eax, eax
0x14009774a  jns     short loc_14009776A
0x14009774c  mov     r8d, 2BFh
0x140097752  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x140097759  lea     rcx, aVidsynicportcr_0; "VidSynicPortCreateGuestEntry"
0x140097760  call    VidTraceErrorInternal0
0x140097765  jmp     loc_14009798A
0x14009776a  mov     rax, [rsp+140h+var_F0]
0x14009776f  jmp     short loc_1400977CF
0x140097771  mov     edx, 1000h
0x140097776  mov     ecx, 41h ; 'A'
0x14009777b  mov     r8d, 72446456h
0x140097781  call    cs:__imp_ExAllocatePool2
0x140097788  nop     dword ptr [rax+rax+00h]
0x14009778d  mov     [rbx+68h], rax
0x140097791  test    rax, rax
0x140097794  jnz     short loc_1400977B9
0x140097796  mov     r8d, 2D5h
0x14009779c  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x1400977a3  lea     rcx, aVidsynicportcr_0; "VidSynicPortCreateGuestEntry"
0x1400977aa  call    VidTraceErrorInternal0
0x1400977af  mov     edi, 0C0000017h
0x1400977b4  jmp     loc_14009798A
0x1400977b9  mov     rcx, rax; BaseAddress
0x1400977bc  mov     [rbx+80h], r15b
0x1400977c3  call    cs:__imp_MmGetPhysicalAddress
0x1400977ca  nop     dword ptr [rax+rax+00h]
0x1400977cf  mov     [rsi+8], rax
0x1400977d3  lea     rcx, [r13+0D00h]
0x1400977da  xor     r12b, r12b
0x1400977dd  call    VidLockAcquireExclusive
0x1400977e2  lea     rcx, [r13+0CE0h]
0x1400977e9  mov     rdx, rbx
0x1400977ec  lea     r8, [rsp+140h+var_F8]
0x1400977f1  call    VidHandleTableAllocateEntry
0x1400977f6  mov     edi, eax
0x1400977f8  test    eax, eax
0x1400977fa  js      loc_14009792F
0x140097800  lea     rdx, [rsp+140h+var_100]
0x140097805  mov     rcx, rbx
0x140097808  call    cs:__imp_WinHvAllocatePortId
0x14009780f  nop     dword ptr [rax+rax+00h]
0x140097814  mov     edi, eax
0x140097816  test    eax, eax
0x140097818  jns     short loc_140097838
0x14009781a  mov     r8d, 2F0h
0x140097820  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x140097827  lea     rcx, aVidsynicportcr_0; "VidSynicPortCreateGuestEntry"
0x14009782e  call    VidTraceErrorInternal0
0x140097833  jmp     loc_14009792F
0x140097838  mov     eax, [rsp+140h+var_100]
0x14009783c  lea     rcx, [rsp+140h+var_C8]
0x140097841  xorps   xmm0, xmm0
0x140097844  mov     [rbx+8], eax
0x140097847  movups  [rsp+140h+var_C8], xmm0
0x14009784c  call    HviGetHypervisorFeatures
0x140097851  mov     rax, 100000000h
0x14009785b  test    qword ptr [rsp+140h+var_C8], rax
0x140097860  jz      short loc_140097876
0x140097862  test    r14b, r14b
0x140097865  jnz     short loc_140097876
0x140097867  mov     eax, [rbx+8]
0x14009786a  and     eax, 3FFFFFFFh
0x14009786f  bts     eax, 1Eh
0x140097873  mov     [rbx+8], eax
0x140097876  mov     eax, [rbx+4]
0x140097879  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14009787d  mov     r9, [r13+288h]
0x140097884  mov     r8d, [rbx+8]
0x140097888  mov     edx, [rsp+140h+var_FC]
0x14009788c  mov     byte ptr [rsp+140h+var_110], r12b
0x140097891  mov     [rsp+140h+var_118], rsi
0x140097896  mov     dword ptr [rsp+140h+var_120], eax
0x14009789a  call    cs:__imp_WinHvConnectPort
0x1400978a1  nop     dword ptr [rax+rax+00h]
0x1400978a6  mov     edi, eax
0x1400978a8  test    eax, eax
0x1400978aa  jns     short loc_1400978C7
0x1400978ac  mov     r8d, 30Ah
0x1400978b2  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x1400978b9  lea     rcx, aVidsynicportcr_0; "VidSynicPortCreateGuestEntry"
0x1400978c0  call    VidTraceErrorInternal0
0x1400978c5  jmp     short loc_14009792F
0x1400978c7  cmp     dword ptr [rsi], 3
0x1400978ca  jnz     short loc_14009790A
0x1400978cc  test    r14b, r14b
0x1400978cf  jz      short loc_140097902
0x1400978d1  mov     rdx, [rsp+140h+var_F0]
0x1400978d6  mov     rcx, rbx
0x1400978d9  call    VidSynicPortpMapMonitorPage
0x1400978de  mov     edi, eax
0x1400978e0  test    eax, eax
0x1400978e2  jns     short loc_140097902
0x1400978e4  mov     r12b, r15b
0x1400978e7  mov     r8d, 319h
0x1400978ed  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x1400978f4  lea     rcx, aVidsynicportcr_0; "VidSynicPortCreateGuestEntry"
0x1400978fb  call    VidTraceErrorInternal0
0x140097900  jmp     short loc_14009792F
0x140097902  mov     rcx, rbx
0x140097905  call    VidSynicPortpInitializeMonitorPage
0x14009790a  mov     rax, [rsp+140h+var_F8]
0x14009790f  xor     r15b, r15b
0x140097912  mov     rcx, [rsp+140h+var_D0]
0x140097917  xor     ebx, ebx
0x140097919  or      [rsp+140h+var_100], 0FFFFFFh
0x140097921  mov     [rsp+140h+var_F8], 0FFFFFFFFFFFFFFFFh
0x14009792a  xor     edi, edi
0x14009792c  mov     [rcx], rax
0x14009792f  mov     rdx, [rsp+140h+var_F8]
0x140097934  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x140097938  jz      short loc_140097946
0x14009793a  lea     rcx, [r13+0CE0h]
0x140097941  call    VidHandleTableFreeEntry
0x140097946  test    r12b, r12b
0x140097949  jz      short loc_14009795E
0x14009794b  mov     edx, [rbx+8]
0x14009794e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140097952  call    cs:__imp_WinHvDisconnectPort
0x140097959  nop     dword ptr [rax+rax+00h]
0x14009795e  lea     rcx, [r13+0D00h]
0x140097965  call    VidLockRelease
0x14009796a  test    r15b, r15b
0x14009796d  jz      short loc_140097985
0x14009796f  mov     edx, [rbx+4]
0x140097972  mov     rcx, [r13+288h]
0x140097979  call    cs:__imp_WinHvDeletePort
0x140097980  nop     dword ptr [rax+rax+00h]
0x140097985  test    rbx, rbx
0x140097988  jz      short loc_14009799F
0x14009798a  cmp     dword ptr [rbx], 3
0x14009798d  jnz     short loc_140097997
0x14009798f  mov     rcx, rbx
0x140097992  call    VidSynicPortpUnmapMonitorPage
0x140097997  mov     rdx, rbx
0x14009799a  call    VidSynicPortpEntryFree
0x14009799f  test    edi, edi
0x1400979a1  jns     short loc_1400979CB
0x1400979a3  lea     rax, [r13+290h]
0x1400979aa  mov     r9d, edi
0x1400979ad  mov     r8d, 34Ch
0x1400979b3  mov     [rsp+140h+var_120], rax
0x1400979b8  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x1400979bf  lea     rcx, aVidsynicportcr_0; "VidSynicPortCreateGuestEntry"
0x1400979c6  call    VidTraceErrorStatusPartitionInternal0
0x1400979cb  mov     eax, edi
0x1400979cd  mov     rcx, [rbp+40h+var_50]
0x1400979d1  xor     rcx, rsp; StackCookie
0x1400979d4  call    __security_check_cookie
0x1400979d9  add     rsp, 108h
0x1400979e0  pop     r15
0x1400979e2  pop     r14
0x1400979e4  pop     r13
0x1400979e6  pop     r12
0x1400979e8  pop     rdi
0x1400979e9  pop     rsi
0x1400979ea  pop     rbx
0x1400979eb  pop     rbp
  ... truncated ...
```
