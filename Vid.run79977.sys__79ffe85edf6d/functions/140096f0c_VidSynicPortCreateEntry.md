# VidSynicPortCreateEntry

- ea: `0x140096f0c`
- end: `0x1400974d5`
- name: `VidSynicPortCreateEntry`
- size: `1481`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, HANDLE Handle, __int64)`
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
- `0x140096f0c`
- `0x140098b5c`
- `0x140098cf8`
- `0x140098d34`
- `0x140098dd4`
- `0x1400f1ea0`
- `0x1400f2a00`

## import_xrefs

- `ntoskrnl!ExEventObjectType` at `0x1400970d4`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x1400970ff`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x1400970ff`
- `ntoskrnl!MmGetPhysicalAddress` at `0x140097201`
- `ntoskrnl!MmGetPhysicalAddress` at `0x140097201`
- `ntoskrnl!ExAllocatePool2` at `0x14009706e`
- `ntoskrnl!ExAllocatePool2` at `0x1400971bf`
- `ntoskrnl!ExAllocatePool2` at `0x14009706e`
- `ntoskrnl!ExAllocatePool2` at `0x1400971bf`
- `winhvr!WinHvSetPortProperty` at `0x14009737c`
- `winhvr!WinHvSetPortProperty` at `0x14009737c`
- `winhvr!WinHvGetPortProperty` at `0x1400972b9`
- `winhvr!WinHvGetPortProperty` at `0x1400972b9`
- `winhvr!WinHvConnectPort` at `0x1400973db`
- `winhvr!WinHvConnectPort` at `0x1400973db`
- `winhvr!WinHvDeletePort` at `0x140097438`
- `winhvr!WinHvDeletePort` at `0x140097438`
- `winhvr!WinHvCreatePort` at `0x140097269`
- `winhvr!WinHvCreatePort` at `0x140097269`
- `winhvr!WinHvAllocatePortId` at `0x14009713c`
- `winhvr!WinHvAllocatePortId` at `0x14009713c`

## string_xrefs

- `0x140096fd8`: `VidSynicPortCreateEntry`
- `0x14009708f`: `VidSynicPortCreateEntry`
- `0x14009711c`: `VidSynicPortCreateEntry`
- `0x14009715b`: `VidSynicPortCreateEntry`
- `0x1400971e1`: `VidSynicPortCreateEntry`
- `0x140097288`: `VidSynicPortCreateEntry`
- `0x1400972d8`: `VidSynicPortCreateEntry`
- `0x140097309`: `VidSynicPortCreateEntry`
- `0x14009739b`: `VidSynicPortCreateEntry`
- `0x1400973fe`: `VidSynicPortCreateEntry`
- `0x140097474`: `VidSynicPortCreateEntry`

## pseudocode

```c
__int64 __fastcall VidSynicPortCreateEntry(
        __int64 a1,
        __int64 a2,
        unsigned __int8 a3,
        char a4,
        unsigned int a5,
        unsigned int *a6,
        HANDLE Handle,
        __int64 a8)
{
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  int PortId; // edi
  __int64 Pool2; // rsi
  char v14; // r15
  __int64 v15; // rcx
  unsigned int *v16; // r12
  unsigned int v17; // ecx
  bool v18; // bl
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  void *v22; // rax
  __int64 v23; // r8
  __int64 v24; // r13
  __int64 v25; // rbx
  unsigned int v26; // ebx
  __int64 v27; // rdx
  _QWORD *v29; // rcx
  __int64 v30; // rax
  int Object; // [rsp+28h] [rbp-D8h]
  int HandleInformation; // [rsp+30h] [rbp-D0h]
  int HandleInformationa; // [rsp+30h] [rbp-D0h]
  unsigned int v36; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v37; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v38; // [rsp+50h] [rbp-B0h]
  __int128 v39; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+68h] [rbp-98h]
  __int64 v41; // [rsp+70h] [rbp-90h] BYREF
  __int64 v42; // [rsp+78h] [rbp-88h]
  __int128 v43; // [rsp+80h] [rbp-80h] BYREF
  char v44[32]; // [rsp+90h] [rbp-70h] BYREF
  char v45[16]; // [rsp+B0h] [rbp-50h] BYREF
  char v46[16]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v47; // [rsp+D0h] [rbp-30h]
  __int64 v48; // [rsp+D8h] [rbp-28h]
  unsigned int *v49; // [rsp+E0h] [rbp-20h]
  __int64 v50; // [rsp+E8h] [rbp-18h]

  v38 = a1;
  v42 = a8;
  v43 = 0;
  HviGetHypervisorFeatures(&v43);
  v9 = *a6;
  v41 = 0;
  v40 = 0;
  v37 = -1;
  v39 = 0;
  v10 = v9 - 1;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      if ( v11 - 1 >= 2 )
      {
        if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
        {
          tlgCreate1Sz_char(v45, "VidSynicPortCreateEntry");
          tlgCreate1Sz_char(v46, "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c");
          LODWORD(v37) = 282;
          v47 = &v37;
          v36 = *a6;
          v48 = 4;
          v49 = &v36;
          v50 = 4;
          tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, &unk_1400494AD, 0, 0, 6, v44);
        }
        PortId = -1073741637;
        goto LABEL_58;
      }
    }
  }
  Pool2 = ExAllocatePool2(65, 136, 1917084758);
  if ( !Pool2 )
  {
    VidTraceErrorInternal0("VidSynicPortCreateEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 297);
    PortId = -1073741801;
LABEL_58:
    VidTraceErrorStatusPartitionInternal0(
      (unsigned int)"VidSynicPortCreateEntry",
      (unsigned int)"onecore\\vm\\vid\\sys\\driver\\vidsynicport.c",
      544,
      PortId,
      v38 + 656);
    return (unsigned int)PortId;
  }
  *(_DWORD *)Pool2 = *a6;
  if ( *a6 == 2 )
  {
    *(_QWORD *)(Pool2 + 64) = -1;
  }
  else if ( *a6 == 3 )
  {
    *(_QWORD *)(Pool2 + 120) = Pool2 + 112;
    *(_QWORD *)(Pool2 + 112) = Pool2 + 112;
  }
  v14 = 1;
  if ( *a6 == 3
    || ObReferenceObjectByHandleWithTag(
         Handle,
         2u,
         (POBJECT_TYPE)ExEventObjectType,
         1,
         0x72446456u,
         (PVOID *)(Pool2 + 16),
         0) >= 0 )
  {
    v16 = (unsigned int *)(Pool2 + 4);
    PortId = WinHvAllocatePortId(Pool2, Pool2 + 4);
    if ( PortId < 0 )
    {
      VidTraceErrorInternal0("VidSynicPortCreateEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 344);
      goto LABEL_54;
    }
    v17 = *a6;
    v18 = (v43 & 0x100000000000LL) != 0;
    v40 = 0;
    v39 = 0;
    LODWORD(v39) = v17;
    v19 = v17 - 1;
    if ( v19 )
    {
      v20 = v19 - 1;
      if ( v20 )
      {
        v21 = v20 - 1;
        if ( !v21 )
        {
          if ( (v43 & 0x100000000000LL) == 0 )
          {
            v22 = (void *)ExAllocatePool2(65, 4096, 1917084758);
            *(_QWORD *)(Pool2 + 104) = v22;
            if ( !v22 )
            {
              VidTraceErrorInternal0("VidSynicPortCreateEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 391);
              PortId = -1073741801;
              goto LABEL_54;
            }
            *(_BYTE *)(Pool2 + 128) = 1;
            *((PHYSICAL_ADDRESS *)&v39 + 1) = MmGetPhysicalAddress(v22);
          }
LABEL_30:
          v23 = *v16;
          LOBYTE(HandleInformation) = a4;
          LOBYTE(Object) = 0;
          v36 = a3 | 0x80000000;
          PortId = WinHvCreatePort(-1, v36, v23, *(_QWORD *)(v38 + 648), &v39, Object, HandleInformation);
          if ( PortId < 0 )
          {
            VidTraceErrorInternal0("VidSynicPortCreateEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 415);
            goto LABEL_54;
          }
          if ( *a6 == 3 )
          {
            if ( v18 )
            {
              PortId = WinHvGetPortProperty(-1, *v16, 2, &v41);
              if ( PortId < 0 )
              {
                VidTraceErrorInternal0("VidSynicPortCreateEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 436);
                goto LABEL_52;
              }
              PortId = VidSynicPortpMapMonitorPage(Pool2, v41);
              if ( PortId < 0 )
              {
                VidTraceErrorInternal0("VidSynicPortCreateEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 443);
                goto LABEL_52;
              }
            }
            VidSynicPortpInitializeMonitorPage(Pool2);
          }
          else if ( *a6 != 4 )
          {
            PortId = WinHvSetPortProperty(-1, *v16, 3, 1);
            if ( PortId < 0 )
            {
              VidTraceErrorInternal0("VidSynicPortCreateEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 465);
              goto LABEL_52;
            }
          }
          v24 = v38 + 3328;
          VidLockAcquireExclusive(v38 + 3328);
          v25 = v38 + 3296;
          *(_QWORD *)&v43 = v38 + 3296;
          PortId = VidHandleTableAllocateEntry(v38 + 3296, Pool2, &v37);
          if ( PortId >= 0 )
          {
            if ( *a6 == 4 )
              v26 = *v16;
            else
              v26 = a5;
            LOBYTE(HandleInformationa) = a4;
            PortId = WinHvConnectPort(*(_QWORD *)(v38 + 648), v36, v26, -1, *v16, a6, HandleInformationa);
            if ( PortId >= 0 )
            {
              v29 = (_QWORD *)v42;
              v27 = -1;
              v30 = v37;
              v14 = 0;
              *(_DWORD *)(Pool2 + 8) = v26;
              Pool2 = 0;
              v25 = v43;
              PortId = 0;
              *v29 = v30;
LABEL_49:
              if ( v27 != -1 )
                VidHandleTableFreeEntry(v25);
              VidLockRelease(v24);
              if ( !v14 )
              {
LABEL_53:
                if ( !Pool2 )
                  goto LABEL_57;
                goto LABEL_54;
              }
LABEL_52:
              WinHvDeletePort(-1, *(unsigned int *)(Pool2 + 4));
              goto LABEL_53;
            }
            VidTraceErrorInternal0("VidSynicPortCreateEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 505);
            v25 = v43;
          }
          v27 = v37;
          goto LABEL_49;
        }
        if ( v21 != 1 )
          goto LABEL_30;
      }
      else
      {
        LODWORD(v40) = 0x10000;
      }
    }
    DWORD2(v39) = *(_DWORD *)(a2 + 16);
    HIDWORD(v39) = -1;
    goto LABEL_30;
  }
  VidTraceErrorInternal0("VidSynicPortCreateEntry", "onecore\\vm\\vid\\sys\\driver\\vidsynicport.c", 332);
  PortId = -1073741811;
LABEL_54:
  if ( *(_DWORD *)Pool2 == 3 )
    VidSynicPortpUnmapMonitorPage(Pool2);
  VidSynicPortpEntryFree(v15, Pool2);
LABEL_57:
  if ( PortId < 0 )
    goto LABEL_58;
  return (unsigned int)PortId;
}

```

## disassembly

```asm
0x140096f0c  push    rbp
0x140096f0e  push    rbx
0x140096f0f  push    rsi
0x140096f10  push    rdi
0x140096f11  push    r12
0x140096f13  push    r13
0x140096f15  push    r14
0x140096f17  push    r15
0x140096f19  lea     rbp, [rsp-8]
0x140096f1e  sub     rsp, 108h
0x140096f25  mov     rax, cs:__security_cookie
0x140096f2c  xor     rax, rsp
0x140096f2f  mov     [rbp+40h+var_50], rax
0x140096f33  mov     rax, [rbp+40h+arg_38]
0x140096f3a  xorps   xmm0, xmm0
0x140096f3d  mov     r14, [rbp+40h+arg_28]
0x140096f41  mov     r13, rdx
0x140096f44  mov     rbx, [rbp+40h+Handle]
0x140096f4b  mov     [rsp+140h+var_F0], rcx
0x140096f50  lea     rcx, [rbp+40h+var_C0]
0x140096f54  mov     [rsp+140h+var_C8], rax
0x140096f59  movups  [rbp+40h+var_C0], xmm0
0x140096f5d  mov     [rsp+140h+var_100], r9b
0x140096f62  mov     [rsp+140h+var_FF], r8b
0x140096f67  call    HviGetHypervisorFeatures
0x140096f6c  mov     ecx, [r14]
0x140096f6f  xor     eax, eax
0x140096f71  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140096f75  mov     [rsp+140h+var_D0], 0
0x140096f7e  mov     [rsp+140h+var_D8], rax
0x140096f83  xorps   xmm1, xmm1
0x140096f86  mov     [rsp+140h+var_F8], rdi
0x140096f8b  movups  [rsp+140h+var_E8], xmm1
0x140096f90  sub     ecx, 1
0x140096f93  jz      loc_14009705D
0x140096f99  sub     ecx, 1
0x140096f9c  jz      loc_14009705D
0x140096fa2  sub     ecx, 1
0x140096fa5  jz      loc_14009705D
0x140096fab  cmp     ecx, 1
0x140096fae  jz      loc_14009705D
0x140096fb4  mov     eax, cs:dword_140065110
0x140096fba  cmp     eax, 2
0x140096fbd  jbe     loc_140097053
0x140096fc3  mov     edx, 100h
0x140096fc8  lea     rcx, dword_140065110
0x140096fcf  call    _tlgKeywordOn
0x140096fd4  test    al, al
0x140096fd6  jz      short loc_140097053
0x140096fd8  lea     rdx, aVidsynicportcr; "VidSynicPortCreateEntry"
0x140096fdf  lea     rcx, [rbp+40h+var_90]
0x140096fe3  call    _tlgCreate1Sz_char
0x140096fe8  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x140096fef  lea     rcx, [rbp+40h+var_80]
0x140096ff3  call    _tlgCreate1Sz_char
0x140096ff8  lea     rax, [rsp+140h+var_F8]
0x140096ffd  mov     dword ptr [rsp+140h+var_F8], 11Ah
0x140097005  mov     [rbp+40h+var_70], rax
0x140097009  lea     rdx, unk_1400494AD
0x140097010  mov     eax, [r14]
0x140097013  lea     rcx, dword_140065110
0x14009701a  mov     [rsp+140h+var_FC], eax
0x14009701e  xor     r9d, r9d
0x140097021  lea     rax, [rsp+140h+var_FC]
0x140097026  mov     [rbp+40h+var_68], 4
0x14009702e  mov     [rbp+40h+var_60], rax
0x140097032  xor     r8d, r8d
0x140097035  lea     rax, [rbp+40h+var_B0]
0x140097039  mov     [rbp+40h+var_58], 4
0x140097041  mov     [rsp+140h+Object], rax
0x140097046  mov     [rsp+140h+Tag], 6
0x14009704e  call    _tlgWriteTransfer_EtwWriteTransfer
0x140097053  mov     edi, 0C00000BBh
0x140097058  jmp     loc_140097462
0x14009705d  mov     edx, 88h
0x140097062  mov     r12d, 72446456h
0x140097068  mov     r8d, r12d
0x14009706b  lea     ecx, [rdx-47h]
0x14009706e  call    cs:__imp_ExAllocatePool2
0x140097075  nop     dword ptr [rax+rax+00h]
0x14009707a  mov     rsi, rax
0x14009707d  test    rax, rax
0x140097080  jnz     short loc_1400970A5
0x140097082  mov     r8d, 129h
0x140097088  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x14009708f  lea     rcx, aVidsynicportcr; "VidSynicPortCreateEntry"
0x140097096  call    VidTraceErrorInternal0
0x14009709b  mov     edi, 0C0000017h
0x1400970a0  jmp     loc_140097462
0x1400970a5  mov     eax, [r14]
0x1400970a8  mov     [rsi], eax
0x1400970aa  mov     ecx, [r14]
0x1400970ad  sub     ecx, 2
0x1400970b0  jz      short loc_1400970C4
0x1400970b2  cmp     ecx, 1
0x1400970b5  jnz     short loc_1400970C8
0x1400970b7  lea     rax, [rsi+70h]
0x1400970bb  mov     [rax+8], rax
0x1400970bf  mov     [rax], rax
0x1400970c2  jmp     short loc_1400970C8
0x1400970c4  mov     [rsi+40h], rdi
0x1400970c8  cmp     dword ptr [r14], 3
0x1400970cc  mov     r15d, 1
0x1400970d2  jz      short loc_140097132
0x1400970d4  mov     r8, cs:ExEventObjectType
0x1400970db  lea     rax, [rsi+10h]
0x1400970df  mov     qword ptr [rsp+140h+HandleInformation], 0; HandleInformation
0x1400970e8  lea     edx, [r15+1]; DesiredAccess
0x1400970ec  mov     [rsp+140h+Object], rax; Object
0x1400970f1  mov     r9b, r15b; AccessMode
0x1400970f4  mov     rcx, rbx; Handle
0x1400970f7  mov     [rsp+140h+Tag], r12d; Tag
0x1400970fc  mov     r8, [r8]; ObjectType
0x1400970ff  call    cs:__imp_ObReferenceObjectByHandleWithTag
0x140097106  nop     dword ptr [rax+rax+00h]
0x14009710b  test    eax, eax
0x14009710d  jns     short loc_140097132
0x14009710f  mov     r8d, 14Ch
0x140097115  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x14009711c  lea     rcx, aVidsynicportcr; "VidSynicPortCreateEntry"
0x140097123  call    VidTraceErrorInternal0
0x140097128  mov     edi, 0C000000Dh
0x14009712d  jmp     loc_140097449
0x140097132  lea     r12, [rsi+4]
0x140097136  mov     rcx, rsi
0x140097139  mov     rdx, r12
0x14009713c  call    cs:__imp_WinHvAllocatePortId
0x140097143  nop     dword ptr [rax+rax+00h]
0x140097148  mov     edi, eax
0x14009714a  test    eax, eax
0x14009714c  jns     short loc_14009716C
0x14009714e  mov     r8d, 158h
0x140097154  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x14009715b  lea     rcx, aVidsynicportcr; "VidSynicPortCreateEntry"
0x140097162  call    VidTraceErrorInternal0
0x140097167  jmp     loc_140097449
0x14009716c  mov     ecx, [r14]
0x14009716f  xor     eax, eax
0x140097171  mov     rbx, qword ptr [rbp+40h+var_C0]
0x140097175  xorps   xmm0, xmm0
0x140097178  shr     rbx, 2Ch
0x14009717c  and     bl, r15b
0x14009717f  mov     [rsp+140h+var_D8], rax
0x140097184  movups  [rsp+140h+var_E8], xmm0
0x140097189  mov     dword ptr [rsp+140h+var_E8], ecx
0x14009718d  sub     ecx, r15d
0x140097190  jz      loc_14009721C
0x140097196  sub     ecx, r15d
0x140097199  jz      short loc_140097214
0x14009719b  sub     ecx, r15d
0x14009719e  jz      short loc_1400971AB
0x1400971a0  cmp     ecx, r15d
0x1400971a3  jnz     loc_14009722C
0x1400971a9  jmp     short loc_14009721C
0x1400971ab  test    bl, bl
0x1400971ad  jnz     short loc_14009722C
0x1400971af  mov     edx, 1000h
0x1400971b4  mov     ecx, 41h ; 'A'
0x1400971b9  mov     r8d, 72446456h
0x1400971bf  call    cs:__imp_ExAllocatePool2
0x1400971c6  nop     dword ptr [rax+rax+00h]
0x1400971cb  mov     [rsi+68h], rax
0x1400971cf  test    rax, rax
0x1400971d2  jnz     short loc_1400971F7
0x1400971d4  mov     r8d, 187h
0x1400971da  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x1400971e1  lea     rcx, aVidsynicportcr; "VidSynicPortCreateEntry"
0x1400971e8  call    VidTraceErrorInternal0
0x1400971ed  mov     edi, 0C0000017h
0x1400971f2  jmp     loc_140097449
0x1400971f7  mov     rcx, rax; BaseAddress
0x1400971fa  mov     [rsi+80h], r15b
0x140097201  call    cs:__imp_MmGetPhysicalAddress
0x140097208  nop     dword ptr [rax+rax+00h]
0x14009720d  mov     qword ptr [rsp+140h+var_E8+8], rax
0x140097212  jmp     short loc_14009722C
0x140097214  mov     dword ptr [rsp+140h+var_D8], 10000h
0x14009721c  mov     eax, [r13+10h]
0x140097220  mov     dword ptr [rsp+140h+var_E8+8], eax
0x140097224  mov     dword ptr [rsp+140h+var_E8+0Ch], 0FFFFFFFFh
0x14009722c  mov     cl, [rsp+140h+var_100]
0x140097230  or      r13, 0FFFFFFFFFFFFFFFFh
0x140097234  movzx   eax, [rsp+140h+var_FF]
0x140097239  mov     r8d, [r12]
0x14009723d  bts     eax, 1Fh
0x140097241  mov     byte ptr [rsp+140h+HandleInformation], cl
0x140097245  mov     edx, eax
0x140097247  lea     rcx, [rsp+140h+var_E8]
0x14009724c  mov     byte ptr [rsp+140h+Object], 0
0x140097251  mov     qword ptr [rsp+140h+Tag], rcx
0x140097256  mov     rcx, [rsp+140h+var_F0]
0x14009725b  mov     [rsp+140h+var_FC], eax
0x14009725f  mov     r9, [rcx+288h]
0x140097266  mov     rcx, r13
0x140097269  call    cs:__imp_WinHvCreatePort
0x140097270  nop     dword ptr [rax+rax+00h]
0x140097275  mov     edi, eax
0x140097277  test    eax, eax
0x140097279  jns     short loc_140097299
0x14009727b  mov     r8d, 19Fh
0x140097281  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x140097288  lea     rcx, aVidsynicportcr; "VidSynicPortCreateEntry"
0x14009728f  call    VidTraceErrorInternal0
0x140097294  jmp     loc_140097449
0x140097299  mov     eax, [r14]
0x14009729c  cmp     eax, 3
0x14009729f  jnz     loc_140097367
0x1400972a5  test    bl, bl
0x1400972a7  jz      short loc_14009731A
0x1400972a9  mov     edx, [r12]
0x1400972ad  lea     r9, [rsp+140h+var_D0]
0x1400972b2  lea     r8d, [rax-1]
0x1400972b6  mov     rcx, r13
0x1400972b9  call    cs:__imp_WinHvGetPortProperty
0x1400972c0  nop     dword ptr [rax+rax+00h]
0x1400972c5  mov     edi, eax
0x1400972c7  test    eax, eax
0x1400972c9  jns     short loc_1400972E9
0x1400972cb  mov     r8d, 1B4h
0x1400972d1  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x1400972d8  lea     rcx, aVidsynicportcr; "VidSynicPortCreateEntry"
0x1400972df  call    VidTraceErrorInternal0
0x1400972e4  jmp     loc_140097432
0x1400972e9  mov     rdx, [rsp+140h+var_D0]
0x1400972ee  mov     rcx, rsi
0x1400972f1  call    VidSynicPortpMapMonitorPage
0x1400972f6  mov     edi, eax
0x1400972f8  test    eax, eax
0x1400972fa  jns     short loc_14009731A
0x1400972fc  mov     r8d, 1BBh
0x140097302  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x140097309  lea     rcx, aVidsynicportcr; "VidSynicPortCreateEntry"
0x140097310  call    VidTraceErrorInternal0
0x140097315  jmp     loc_140097432
0x14009731a  mov     rcx, rsi
0x14009731d  call    VidSynicPortpInitializeMonitorPage
0x140097322  mov     rbx, [rsp+140h+var_F0]
0x140097327  lea     r13, [rbx+0D00h]
0x14009732e  mov     rcx, r13
0x140097331  call    VidLockAcquireExclusive
0x140097336  add     rbx, 0CE0h
0x14009733d  lea     r8, [rsp+140h+var_F8]
0x140097342  mov     rcx, rbx
0x140097345  mov     qword ptr [rbp+40h+var_C0], rbx
0x140097349  mov     rdx, rsi
0x14009734c  call    VidHandleTableAllocateEntry
0x140097351  mov     edi, eax
0x140097353  test    eax, eax
0x140097355  js      loc_14009740E
0x14009735b  cmp     dword ptr [r14], 4
0x14009735f  jnz     short loc_1400973AC
0x140097361  mov     ebx, [r12]
0x140097365  jmp     short loc_1400973AF
0x140097367  cmp     eax, 4
0x14009736a  jz      short loc_140097322
0x14009736c  mov     edx, [r12]
0x140097370  mov     r9, r15
0x140097373  mov     r8d, 3
0x140097379  mov     rcx, r13
0x14009737c  call    cs:__imp_WinHvSetPortProperty
0x140097383  nop     dword ptr [rax+rax+00h]
0x140097388  mov     edi, eax
0x14009738a  test    eax, eax
0x14009738c  jns     short loc_140097322
0x14009738e  mov     r8d, 1D1h
0x140097394  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x14009739b  lea     rcx, aVidsynicportcr; "VidSynicPortCreateEntry"
0x1400973a2  call    VidTraceErrorInternal0
0x1400973a7  jmp     loc_140097432
0x1400973ac  mov     ebx, [rbp+40h+arg_20]
0x1400973af  mov     al, [rsp+140h+var_100]
0x1400973b3  or      r9, 0FFFFFFFFFFFFFFFFh
0x1400973b7  mov     rcx, [rsp+140h+var_F0]
0x1400973bc  mov     r8d, ebx
0x1400973bf  mov     edx, [rsp+140h+var_FC]
0x1400973c3  mov     byte ptr [rsp+140h+HandleInformation], al
0x1400973c7  mov     eax, [r12]
0x1400973cb  mov     rcx, [rcx+288h]
0x1400973d2  mov     [rsp+140h+Object], r14
0x1400973d7  mov     [rsp+140h+Tag], eax
0x1400973db  call    cs:__imp_WinHvConnectPort
0x1400973e2  nop     dword ptr [rax+rax+00h]
0x1400973e7  mov     edi, eax
0x1400973e9  test    eax, eax
0x1400973eb  jns     loc_1400974B1
0x1400973f1  mov     r8d, 1F9h
0x1400973f7  lea     rdx, aOnecoreVmVidSy_1; "onecore\\vm\\vid\\sys\\driver\\vidsynic"...
0x1400973fe  lea     rcx, aVidsynicportcr; "VidSynicPortCreateEntry"
0x140097405  call    VidTraceErrorInternal0
0x14009740a  mov     rbx, qword ptr [rbp+40h+var_C0]
0x14009740e  mov     rdx, [rsp+140h+var_F8]
0x140097413  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x140097417  jz      short loc_140097421
0x140097419  mov     rcx, rbx
0x14009741c  call    VidHandleTableFreeEntry
0x140097421  mov     rcx, r13
0x140097424  call    VidLockRelease
0x140097429  test    r15b, r15b
0x14009742c  jz      short loc_140097444
0x14009742e  or      r13, 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
