# AfdCreate

- ea: `0x1400218d4`
- end: `0x1400220d2`
- name: `AfdCreate`
- size: `2046`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140020500`

## callees

- `0x14000f390`
- `0x140014ed0`
- `0x1400153d0`
- `0x140015430`
- `0x1400218d4`
- `0x140026e80`
- `0x140028950`
- `0x14002e43c`
- `0x14003b920`
- `0x140048860`
- `0x14005a988`
- `0x14006b014`
- `0x140072920`
- `0x140072c80`
- `0x140093008`
- `0x1400931d0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140021f5e`
- `ntoskrnl!KeInitializeEvent` at `0x140021f5e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140021fea`
- `ntoskrnl!KeWaitForSingleObject` at `0x140021fea`
- `ntoskrnl!RtlInitString` at `0x140021a35`
- `ntoskrnl!RtlInitString` at `0x140021d8f`
- `ntoskrnl!RtlInitString` at `0x140021df3`
- `ntoskrnl!RtlInitString` at `0x140021a35`
- `ntoskrnl!RtlInitString` at `0x140021d8f`
- `ntoskrnl!RtlInitString` at `0x140021df3`
- `ntoskrnl!RtlEqualString` at `0x140021a4c`
- `ntoskrnl!RtlEqualString` at `0x140021da6`
- `ntoskrnl!RtlEqualString` at `0x140021e0a`
- `ntoskrnl!RtlEqualString` at `0x140021a4c`
- `ntoskrnl!RtlEqualString` at `0x140021da6`
- `ntoskrnl!RtlEqualString` at `0x140021e0a`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x140022012`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x140022012`
- `ntoskrnl!IofCompleteRequest` at `0x140021ecf`
- `ntoskrnl!IofCompleteRequest` at `0x140021ecf`
- `NDIS!NdisAllocateRWLock` at `0x140021cad`
- `NDIS!NdisAllocateRWLock` at `0x140021cad`

## string_xrefs

- `0x140021a22`: `AfdOpenPacketXX`
- `0x140021d84`: `AfdSwOpenPacket`
- `0x140021de8`: `AfdRioRDOpenPacket`

## pseudocode

```c
__int64 __fastcall AfdCreate(PIRP Irp, __int64 a2)
{
  struct _IRP *MasterIrp; // rdi
  int v3; // r12d
  unsigned __int16 v6; // r13
  __int64 result; // rax
  __int64 v8; // rbx
  int v9; // eax
  int v10; // edx
  unsigned int v11; // r8d
  __int64 v12; // rsi
  unsigned int v13; // edx
  unsigned int v14; // ecx
  int v15; // r10d
  int v16; // r9d
  int v17; // r8d
  int v18; // edx
  int v19; // edx
  unsigned int v20; // r9d
  unsigned int v21; // r8d
  unsigned int v22; // ecx
  unsigned int v23; // ebx
  PNDIS_RW_LOCK_EX RWLock; // rax
  int v25; // edx
  unsigned int v26; // r14d
  int v27; // [rsp+28h] [rbp-91h]
  _STRING DestinationString; // [rsp+40h] [rbp-79h] BYREF
  __int128 v29; // [rsp+50h] [rbp-69h]
  STRING String2; // [rsp+60h] [rbp-59h] BYREF
  struct _KEVENT Event; // [rsp+70h] [rbp-49h] BYREF
  _OWORD v32[8]; // [rsp+90h] [rbp-29h] BYREF
  unsigned int Buffer; // [rsp+120h] [rbp+67h] BYREF
  __int64 v34; // [rsp+130h] [rbp+77h] BYREF
  __int64 v35; // [rsp+138h] [rbp+7Fh] BYREF

  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  v3 = -1;
  v34 = 0;
  Buffer = 0;
  v6 = 0;
  if ( MasterIrp )
  {
    String2.Length = *((unsigned __int8 *)&MasterIrp->Size + 3);
    *(&String2.MaximumLength + 2) = 0;
    DestinationString = 0;
    *(_DWORD *)&String2.MaximumLength = (unsigned __int16)(String2.Length + 1);
    String2.Buffer = (PCHAR)&MasterIrp->MdlAddress;
    RtlInitString(&DestinationString, "AfdOpenPacketXX");
    if ( RtlEqualString(&DestinationString, &String2, 0) )
    {
      v11 = *(&MasterIrp->Size + 2);
      if ( v11 < 0x1C
        || (v12 = *((unsigned __int8 *)&MasterIrp->Size + 3),
            v13 = *(_DWORD *)((char *)&MasterIrp->AssociatedIrp.SystemBuffer + v12 + 5),
            v14 = v13 + 2,
            v13 + 2 > 0xFFFF)
        || v14 < v13
        || (v15 = 2 * (v14 >> 1), v15 + 24 < 26)
        || (int)v11 < v15 + 24 )
      {
        v23 = -1073741819;
        AFDETW_TRACECREATE(0, 1000, 0, 0, 0, 0, -1073741819);
        return v23;
      }
      if ( (*(_DWORD *)((_BYTE *)&MasterIrp->MdlAddress + v12 + 1) & 0xEEEEEEEE) == 0
        && v15 == v14
        && ((*((_BYTE *)&MasterIrp->MdlAddress + v12 + 3) & 0x11) == 0
         || (*((_BYTE *)&MasterIrp->MdlAddress + v12 + 2) & 0x10) != 0) )
      {
        if ( v13 )
        {
          v16 = *(_DWORD *)((char *)&MasterIrp->AssociatedIrp.MasterIrp + v12 + 1);
          v17 = *(ULONG *)((char *)&MasterIrp->Flags + v12 + 5);
          v18 = *(ULONG *)((char *)&MasterIrp->Flags + v12 + 1);
          Event.Header.WaitListHead.Flink = (struct _LIST_ENTRY *)((char *)&MasterIrp->ThreadListEntry.Flink + v12 + 1);
          LOWORD(Event.Header.Lock) = *(_WORD *)((char *)&MasterIrp->AssociatedIrp.SystemBuffer + v12 + 5);
          v27 = *(_DWORD *)((char *)&MasterIrp->MdlAddress + v12 + 5);
          *(_WORD *)&Event.Header.Size = v14;
          Event.Header.SignalState = 0;
          result = AfdAllocateEndpoint((int)&v34, v18, v17, v16, (PCUNICODE_STRING)&Event, v27);
          Buffer = result;
          if ( (int)result < 0 )
            return result;
          v19 = 1002;
          goto LABEL_42;
        }
        v20 = *(ULONG *)((char *)&MasterIrp->Flags + v12 + 1);
        v35 = 0;
        if ( v20 > 0x22
          || (v21 = *(_DWORD *)((char *)&MasterIrp->AssociatedIrp.MasterIrp + v12 + 1), v21 > 0xFFFF)
          || (v22 = *(ULONG *)((char *)&MasterIrp->Flags + v12 + 5), v22 > 0xFFFF) )
        {
          AFDETW_TRACECREATE(
            0,
            1003,
            0,
            v20,
            *(ULONG *)((char *)&MasterIrp->Flags + v12 + 5),
            *(_DWORD *)((char *)&MasterIrp->AssociatedIrp.MasterIrp + v12 + 1),
            -1073741811);
          return 3221225485LL;
        }
        if ( (*((_BYTE *)&MasterIrp->MdlAddress + v12 + 1) & 0x11) == 0x10 )
        {
          AFDETW_TRACECREATE(0, 1004, 0, v20, v22, v21, -1073741811);
          return 3221225485LL;
        }
        if ( (*((_BYTE *)&MasterIrp->MdlAddress + v12 + 4) & 1) != 0
          || !(unsigned __int8)AfdCheckTDIFilter(
                                 *(unsigned __int16 *)((char *)&MasterIrp->Flags + v12 + 5),
                                 *(unsigned __int16 *)((char *)&MasterIrp->Flags + v12 + 1),
                                 v21,
                                 0,
                                 (__int64)&v35) )
        {
          result = AfdAllocateEndpoint(
                     (int)&v34,
                     *(ULONG *)((char *)&MasterIrp->Flags + v12 + 1),
                     *(ULONG *)((char *)&MasterIrp->Flags + v12 + 5),
                     *(_DWORD *)((char *)&MasterIrp->AssociatedIrp.MasterIrp + v12 + 1),
                     0,
                     *(_DWORD *)((char *)&MasterIrp->MdlAddress + v12 + 5));
          Buffer = result;
          if ( (int)result < 0 )
            return result;
          v19 = 1006;
LABEL_42:
          v8 = v34;
          AFDETW_TRACECREATE(
            0,
            v19,
            v34,
            *(ULONG *)((char *)&MasterIrp->Flags + v12 + 1),
            *(ULONG *)((char *)&MasterIrp->Flags + v12 + 5),
            *(_DWORD *)((char *)&MasterIrp->AssociatedIrp.MasterIrp + v12 + 1),
            0);
          v6 = *(_WORD *)((char *)&MasterIrp->AssociatedIrp.MasterIrp + v12 + 1);
          v3 = *(ULONG *)((char *)&MasterIrp->Flags + v12 + 1);
          *(_DWORD *)(v8 + 4) = *(_DWORD *)((char *)&MasterIrp->MdlAddress + v12 + 1);
          if ( (*((_BYTE *)&MasterIrp->MdlAddress + v12 + 1) & 1) != 0 )
          {
            *(_WORD *)v8 = -20527;
            *(_QWORD *)(v8 + 104) = v8 + 96;
            *(_QWORD *)(v8 + 96) = v8 + 96;
            *(_QWORD *)(v8 + 120) = v8 + 112;
            *(_QWORD *)(v8 + 112) = v8 + 112;
            *(_QWORD *)(v8 + 136) = v8 + 128;
            *(_QWORD *)(v8 + 128) = v8 + 128;
            *(_DWORD *)(v8 + 152) = AfdReceiveWindowSize;
            *(_DWORD *)(v8 + 160) = AfdSendWindowSize;
            RWLock = NdisAllocateRWLock(0);
            *(_QWORD *)(v8 + 168) = RWLock;
            if ( !RWLock )
            {
              v9 = -1073741670;
              v10 = 1020;
              Buffer = -1073741670;
LABEL_45:
              AFDETW_TRACECREATE(1, v10, v8, 0, 0, 0, v9);
LABEL_46:
              *(_BYTE *)(v8 + 2) = 6;
              AfdDereferenceEndpoint(v8);
              AfdDereferenceEndpoint(v8);
              return Buffer;
            }
          }
          goto LABEL_5;
        }
        v23 = -2147483620;
        Irp->IoStatus.Information = -2147483620;
        AFDETW_TRACECREATE(
          0,
          1005,
          0,
          *(ULONG *)((char *)&MasterIrp->Flags + v12 + 1),
          *(ULONG *)((char *)&MasterIrp->Flags + v12 + 5),
          *(_DWORD *)((char *)&MasterIrp->AssociatedIrp.MasterIrp + v12 + 1),
          -2147483620);
        return v23;
      }
      v25 = 1001;
    }
    else
    {
      RtlInitString(&DestinationString, "AfdSwOpenPacket");
      if ( RtlEqualString(&DestinationString, &String2, 0) )
      {
        AFDETW_TRACECREATE(0, 1007, 0, 0, 0, 0, 0);
        result = AfdSanCreateHelper(Irp);
        goto LABEL_3;
      }
      RtlInitString(&DestinationString, "AfdRioRDOpenPacket");
      if ( RtlEqualString(&DestinationString, &String2, 0) )
      {
        AFDETW_TRACECREATE(0, 1019, 0, 0, 0, 0, 0);
        result = AfdRioCreateRegistrationDomain(&v34);
        goto LABEL_3;
      }
      if ( (xmmword_1400875E0 & 4) != 0 )
        WPP_SF_(1026, 10, WPP_26e5460b40443885e905c13711d903ac_Traceguids);
      v25 = 1008;
    }
    AFDETW_TRACECREATE(0, v25, 0, 0, 0, 0, -1073741811);
    return 3221225485LL;
  }
  result = AfdAllocateEndpoint((int)&v34, -1, 0, 0, 0, 0);
LABEL_3:
  Buffer = result;
  if ( (int)result < 0 )
    return result;
  v8 = v34;
LABEL_5:
  if ( *(_WORD *)v8 == 2813
    || (*(_BYTE *)(v8 + 5) & 1) != 0
    && (*(_DWORD *)(v8 + 8) & 0x100) == 0
    && (!*(_BYTE *)(*(_QWORD *)(v8 + 272) + 24LL) || (*(_DWORD *)(v8 + 16) & 0x10000) == 0) )
  {
    *(_BYTE *)(v8 + 3) = AfdPerformSecurityCheck((__int64)Irp, a2, (int *)&Buffer);
  }
  *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL) = v8;
  *(_QWORD *)(*(_QWORD *)(a2 + 48) + 48LL) = -1;
  if ( v3 == 34 || v3 == 1 )
    *(_DWORD *)(*(_QWORD *)(a2 + 48) + 80LL) |= 0x80u;
  if ( (xmmword_1400875E0 & 4) != 0 )
    WPP_SF_qq(1026, 11, WPP_26e5460b40443885e905c13711d903ac_Traceguids, *(_QWORD *)(a2 + 48), v8);
  if ( (*(_DWORD *)(v8 + 8) & 0x100) != 0 )
  {
    v34 = 0;
    v9 = AfdCaptureCreatorSD(a2, &v34);
    Buffer = v9;
    if ( v9 >= 0 )
    {
      Irp->Tail.Overlay.DriverContext[2] = 0;
      Buffer = AfdTLCreateEndpoint(
                 v8,
                 v3,
                 v6,
                 *(_QWORD *)(v8 + 272),
                 Irp,
                 *(_QWORD *)(v8 + 48),
                 (__int64)KeGetCurrentThread(),
                 v34);
      if ( Buffer == 259 )
      {
        if ( !(unsigned __int8)AfdTLPendRequest(Irp, 0, 0) )
        {
          AfdCompleteTLEndpCreate(v8, Irp);
          IofCompleteRequest(Irp, AfdPriorityBoost);
        }
      }
      else
      {
        AfdCompleteTLEndpCreate(v8, Irp);
      }
      return Buffer;
    }
    v10 = 1009;
    goto LABEL_45;
  }
  if ( (*(_DWORD *)(v8 + 8) & 0x200) != 0 )
  {
    memset(v32, 0, 0x50u);
    v34 = 0;
    DestinationString = 0;
    v29 = 0;
    memset(&Event, 0, sizeof(Event));
    Buffer = AfdCaptureCreatorSD(a2, &v34);
    v26 = Buffer;
    if ( (Buffer & 0x80000000) != 0 )
    {
LABEL_65:
      AFDETW_TRACECREATE(1, 1010, v8, 0, 0, 0, v26);
      goto LABEL_46;
    }
    if ( !v34 )
    {
      v26 = -1073741811;
      Buffer = -1073741811;
      goto LABEL_65;
    }
    *(_QWORD *)&DestinationString.Length = &Event;
    KeInitializeEvent(&Event, SynchronizationEvent, 0);
    WORD4(v32[1]) = v3;
    *(_QWORD *)&v32[0] = AfdSynchronousTlCreateRequestComplete;
    *((_QWORD *)&v32[0] + 1) = &DestinationString;
    WORD5(v32[1]) = *(_WORD *)(*(_QWORD *)(v8 + 512) + 28LL);
    WORD6(v32[1]) = v6;
    *((_QWORD *)&v32[2] + 1) = *(_QWORD *)(v8 + 48);
    *(_QWORD *)&v32[3] = KeGetCurrentThread();
    *((_QWORD *)&v32[3] + 1) = v34;
    Buffer = (*(__int64 (__fastcall **)(_QWORD, _OWORD *))(*(_QWORD *)(*(_QWORD *)(v8 + 512) + 40LL) + 16LL))(
               *(_QWORD *)(*(_QWORD *)(v8 + 512) + 32LL),
               v32);
    if ( Buffer == 259 )
    {
      KeWaitForSingleObject(*(PVOID *)&DestinationString.Length, Executive, 0, 0, 0);
      Buffer = (unsigned int)DestinationString.Buffer;
      v32[4] = v29;
    }
    ObDereferenceSecurityDescriptor(v34, 1);
    v9 = Buffer;
    if ( (Buffer & 0x80000000) != 0 )
    {
      v10 = 1011;
      goto LABEL_45;
    }
    *(_OWORD *)(v8 + 496) = v32[4];
  }
  AFDETW_TRACECREATE(1, 1012, v8, 0, 0, 0, 0);
  AfdDereferenceEndpoint(v8);
  return 0;
}

```

## disassembly

```asm
0x1400218d4  mov     [rsp-8+arg_8], rbx
0x1400218d9  push    rbp
0x1400218da  push    rsi
0x1400218db  push    rdi
0x1400218dc  push    r12
0x1400218de  push    r13
0x1400218e0  push    r14
0x1400218e2  push    r15
0x1400218e4  lea     rbp, [rsp-27h]
0x1400218e9  sub     rsp, 0E0h
0x1400218f0  mov     rdi, [rcx+18h]
0x1400218f4  xor     esi, esi
0x1400218f6  or      r12d, 0FFFFFFFFh
0x1400218fa  mov     [rbp+57h+arg_10], rsi
0x1400218fe  mov     [rbp+57h+arg_0], esi
0x140021901  mov     r15, rdx
0x140021904  mov     r14, rcx
0x140021907  mov     r13d, esi
0x14002190a  lea     edx, [rsi+1]
0x14002190d  test    rdi, rdi
0x140021910  jnz     loc_140021A09
0x140021916  mov     dword ptr [rsp+110h+var_E8], esi; int
0x14002191a  lea     rcx, [rbp+57h+arg_10]; int
0x14002191e  xor     r9d, r9d; int
0x140021921  mov     [rsp+110h+Timeout], rsi; String2
0x140021926  xor     r8d, r8d; int
0x140021929  or      edx, 0FFFFFFFFh; int
0x14002192c  call    AfdAllocateEndpoint
0x140021931  mov     [rbp+57h+arg_0], eax
0x140021934  test    eax, eax
0x140021936  js      loc_1400220B6
0x14002193c  mov     rbx, [rbp+57h+arg_10]
0x140021940  mov     edi, 1
0x140021945  mov     eax, 0AFDh
0x14002194a  cmp     [rbx], ax
0x14002194d  jz      short loc_140021975
0x14002194f  test    [rbx+5], dil
0x140021953  jz      short loc_140021987
0x140021955  mov     eax, [rbx+8]
0x140021958  bt      eax, 8
0x14002195c  jb      short loc_140021987
0x14002195e  mov     rax, [rbx+110h]
0x140021965  mov     cl, [rax+18h]
0x140021968  test    cl, cl
0x14002196a  jz      short loc_140021975
0x14002196c  test    dword ptr [rbx+10h], 10000h
0x140021973  jnz     short loc_140021987
0x140021975  lea     r8, [rbp+57h+arg_0]
0x140021979  mov     rdx, r15
0x14002197c  mov     rcx, r14
0x14002197f  call    AfdPerformSecurityCheck
0x140021984  mov     [rbx+3], al
0x140021987  mov     rax, [r15+30h]
0x14002198b  mov     [rax+18h], rbx
0x14002198f  mov     rax, [r15+30h]
0x140021993  mov     qword ptr [rax+30h], 0FFFFFFFFFFFFFFFFh
0x14002199b  cmp     r12d, 22h ; '"'
0x14002199f  jz      short loc_1400219A6
0x1400219a1  cmp     r12d, edi
0x1400219a4  jnz     short loc_1400219AF
0x1400219a6  mov     rax, [r15+30h]
0x1400219aa  bts     dword ptr [rax+50h], 7
0x1400219af  test    byte ptr cs:xmmword_1400875E0, 4
0x1400219b6  jz      short loc_1400219D7
0x1400219b8  mov     r9, [r15+30h]
0x1400219bc  lea     r8, WPP_26e5460b40443885e905c13711d903ac_Traceguids
0x1400219c3  mov     edx, 0Bh
0x1400219c8  mov     [rsp+110h+Timeout], rbx
0x1400219cd  mov     ecx, 402h
0x1400219d2  call    WPP_SF_qq
0x1400219d7  mov     eax, [rbx+8]
0x1400219da  bt      eax, 8
0x1400219de  jnb     loc_140021EE0
0x1400219e4  lea     rdx, [rbp+57h+arg_10]
0x1400219e8  mov     [rbp+57h+arg_10], rsi
0x1400219ec  mov     rcx, r15
0x1400219ef  call    AfdCaptureCreatorSD
0x1400219f4  mov     [rbp+57h+arg_0], eax
0x1400219f7  test    eax, eax
0x1400219f9  jns     loc_140021E4A
0x1400219ff  mov     edx, 3F1h
0x140021a04  jmp     loc_140021CD8
0x140021a09  movzx   ecx, byte ptr [rdi+5]
0x140021a0d  xorps   xmm0, xmm0
0x140021a10  mov     [rbp+57h+String2.Length], cx
0x140021a14  mov     dword ptr [rbp+57h+String2+4], esi
0x140021a17  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140021a1b  lea     eax, [rdx+rcx]
0x140021a1e  mov     [rbp+57h+String2.MaximumLength], ax
0x140021a22  lea     rdx, aAfdopenpacketx; "AfdOpenPacketXX"
0x140021a29  lea     rax, [rdi+8]
0x140021a2d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140021a31  mov     [rbp+57h+String2.Buffer], rax
0x140021a35  call    cs:__imp_RtlInitString
0x140021a3c  nop     dword ptr [rax+rax+00h]
0x140021a41  xor     r8d, r8d; CaseInSensitive
0x140021a44  lea     rdx, [rbp+57h+String2]; String2
0x140021a48  lea     rcx, [rbp+57h+DestinationString]; String1
0x140021a4c  call    cs:__imp_RtlEqualString
0x140021a53  nop     dword ptr [rax+rax+00h]
0x140021a58  test    al, al
0x140021a5a  jz      loc_140021D84
0x140021a60  movzx   r8d, word ptr [rdi+6]
0x140021a65  cmp     r8d, 1Ch
0x140021a69  jb      loc_140021D5A
0x140021a6f  movzx   esi, byte ptr [rdi+5]
0x140021a73  mov     r11d, 0FFFFh
0x140021a79  mov     edx, [rsi+rdi+1Dh]
0x140021a7d  lea     ecx, [rdx+2]
0x140021a80  cmp     ecx, r11d
0x140021a83  ja      loc_140021D58
0x140021a89  cmp     ecx, edx
0x140021a8b  jb      loc_140021D58
0x140021a91  mov     eax, ecx
0x140021a93  shr     eax, 1
0x140021a95  lea     r10d, [rax+rax]
0x140021a99  lea     r9d, [r10+18h]
0x140021a9d  cmp     r9d, 1Ah
0x140021aa1  jl      loc_140021D58
0x140021aa7  cmp     r8d, r9d
0x140021aaa  jl      loc_140021D58
0x140021ab0  test    dword ptr [rsi+rdi+9], 0EEEEEEEEh
0x140021ab8  jnz     loc_140021D39
0x140021abe  cmp     r10d, ecx
0x140021ac1  jnz     loc_140021D39
0x140021ac7  test    byte ptr [rsi+rdi+0Bh], 11h
0x140021acc  jz      short loc_140021AD9
0x140021ace  test    byte ptr [rsi+rdi+0Ah], 10h
0x140021ad3  jz      loc_140021D39
0x140021ad9  xor     ebx, ebx
0x140021adb  test    edx, edx
0x140021add  jz      short loc_140021B37
0x140021adf  mov     r9d, [rsi+rdi+19h]; int
0x140021ae4  lea     rax, [rdi+21h]
0x140021ae8  mov     r8d, [rsi+rdi+15h]; int
0x140021aed  add     rax, rsi
0x140021af0  mov     edx, [rsi+rdi+11h]; int
0x140021af4  mov     [rbp+57h+Event.Header.WaitListHead.Flink], rax
0x140021af8  movzx   eax, word ptr [rsi+rdi+1Dh]
0x140021afd  mov     word ptr [rbp+57h+Event.Header], ax
0x140021b01  mov     eax, [rsi+rdi+0Dh]
0x140021b05  mov     dword ptr [rsp+110h+var_E8], eax; int
0x140021b09  lea     rax, [rbp+57h+Event]
0x140021b0d  mov     word ptr [rbp+57h+Event.Header+2], cx
0x140021b11  lea     rcx, [rbp+57h+arg_10]; int
0x140021b15  mov     [rsp+110h+Timeout], rax; String2
0x140021b1a  mov     [rbp+57h+Event.Header.SignalState], ebx
0x140021b1d  call    AfdAllocateEndpoint
0x140021b22  mov     [rbp+57h+arg_0], eax
0x140021b25  test    eax, eax
0x140021b27  js      loc_1400220B6
0x140021b2d  mov     edx, 3EAh
0x140021b32  jmp     loc_140021C1F
0x140021b37  mov     r9d, [rsi+rdi+11h]
0x140021b3c  mov     [rbp+57h+arg_18], rbx
0x140021b40  cmp     r9d, 0FFFFFFFFh
0x140021b44  jz      loc_140021D14
0x140021b4a  cmp     r9d, 23h ; '#'
0x140021b4e  jnb     loc_140021D14
0x140021b54  mov     r8d, [rsi+rdi+19h]
0x140021b59  cmp     r8d, r11d
0x140021b5c  ja      loc_140021D14
0x140021b62  mov     ecx, [rsi+rdi+15h]
0x140021b66  cmp     ecx, r11d
0x140021b69  ja      loc_140021D14
0x140021b6f  mov     al, [rsi+rdi+9]
0x140021b73  and     al, 11h
0x140021b75  cmp     al, 10h
0x140021b77  jnz     short loc_140021B97
0x140021b79  mov     r14d, 0C000000Dh
0x140021b7f  mov     edx, 3ECh
0x140021b84  mov     dword ptr [rsp+110h+var_E0], r14d
0x140021b89  mov     dword ptr [rsp+110h+var_E8], r8d
0x140021b8e  mov     dword ptr [rsp+110h+Timeout], ecx
0x140021b92  jmp     loc_1400220A9
0x140021b97  test    byte ptr [rsi+rdi+0Ch], 1
0x140021b9c  jnz     short loc_140021BEB
0x140021b9e  movzx   edx, word ptr [rsi+rdi+11h]
0x140021ba3  lea     rax, [rbp+57h+arg_18]
0x140021ba7  movzx   ecx, word ptr [rsi+rdi+15h]
0x140021bac  xor     r9d, r9d
0x140021baf  mov     [rsp+110h+Timeout], rax
0x140021bb4  call    AfdCheckTDIFilter
0x140021bb9  test    al, al
0x140021bbb  jz      short loc_140021BEB
0x140021bbd  mov     rbx, 0FFFFFFFF8000001Ch
0x140021bc4  mov     edx, 3EDh
0x140021bc9  mov     [r14+38h], rbx
0x140021bcd  mov     ecx, [rsi+rdi+19h]
0x140021bd1  mov     r9d, [rsi+rdi+11h]
0x140021bd6  mov     dword ptr [rsp+110h+var_E0], ebx
0x140021bda  mov     dword ptr [rsp+110h+var_E8], ecx
0x140021bde  mov     ecx, [rsi+rdi+15h]
0x140021be2  mov     dword ptr [rsp+110h+Timeout], ecx
0x140021be6  jmp     loc_140021D73
0x140021beb  mov     eax, [rsi+rdi+0Dh]
0x140021bef  lea     rcx, [rbp+57h+arg_10]; int
0x140021bf3  mov     r9d, [rsi+rdi+19h]; int
0x140021bf8  mov     r8d, [rsi+rdi+15h]; int
0x140021bfd  mov     edx, [rsi+rdi+11h]; int
0x140021c01  mov     dword ptr [rsp+110h+var_E8], eax; int
0x140021c05  mov     [rsp+110h+Timeout], rbx; String2
0x140021c0a  call    AfdAllocateEndpoint
0x140021c0f  mov     [rbp+57h+arg_0], eax
0x140021c12  test    eax, eax
0x140021c14  js      loc_1400220B6
0x140021c1a  mov     edx, 3EEh
0x140021c1f  mov     eax, [rsi+rdi+19h]
0x140021c23  xor     ecx, ecx
0x140021c25  mov     r9d, [rsi+rdi+11h]
0x140021c2a  mov     dword ptr [rsp+110h+var_E0], ebx
0x140021c2e  mov     rbx, [rbp+57h+arg_10]
0x140021c32  mov     dword ptr [rsp+110h+var_E8], eax
0x140021c36  mov     r8, rbx
0x140021c39  mov     eax, [rsi+rdi+15h]
0x140021c3d  mov     dword ptr [rsp+110h+Timeout], eax
0x140021c41  call    AFDETW_TRACECREATE
0x140021c46  mov     eax, [rsi+rdi+9]
0x140021c4a  movzx   r13d, word ptr [rsi+rdi+19h]
0x140021c50  mov     r12d, [rsi+rdi+11h]
0x140021c55  mov     [rbx+4], eax
0x140021c58  mov     al, [rsi+rdi+9]
0x140021c5c  mov     edi, 1
0x140021c61  test    dil, al
0x140021c64  jz      loc_140021D0D
0x140021c6a  mov     word ptr [rbx], 0AFD1h
0x140021c6f  lea     rax, [rbx+60h]
0x140021c73  mov     [rax+8], rax
0x140021c77  xor     ecx, ecx; NdisHandle
0x140021c79  mov     [rax], rax
0x140021c7c  lea     rax, [rbx+70h]
0x140021c80  mov     [rax+8], rax
0x140021c84  mov     [rax], rax
0x140021c87  lea     rax, [rbx+80h]
0x140021c8e  mov     [rax+8], rax
0x140021c92  mov     [rax], rax
0x140021c95  mov     eax, cs:AfdReceiveWindowSize
0x140021c9b  mov     [rbx+98h], eax
0x140021ca1  mov     eax, cs:AfdSendWindowSize
0x140021ca7  mov     [rbx+0A0h], eax
0x140021cad  call    cs:__imp_NdisAllocateRWLock
0x140021cb4  nop     dword ptr [rax+rax+00h]
0x140021cb9  xor     esi, esi
0x140021cbb  mov     [rbx+0A8h], rax
0x140021cc2  test    rax, rax
0x140021cc5  jnz     loc_140021945
0x140021ccb  mov     eax, 0C000009Ah
0x140021cd0  mov     edx, 3FCh
0x140021cd5  mov     [rbp+57h+arg_0], eax
0x140021cd8  mov     dword ptr [rsp+110h+var_E0], eax
0x140021cdc  mov     dword ptr [rsp+110h+var_E8], esi
0x140021ce0  mov     r8, rbx
0x140021ce3  xor     r9d, r9d
0x140021ce6  mov     dword ptr [rsp+110h+Timeout], esi
0x140021cea  mov     ecx, edi
0x140021cec  call    AFDETW_TRACECREATE
0x140021cf1  mov     rcx, rbx
0x140021cf4  mov     byte ptr [rbx+2], 6
0x140021cf8  call    AfdDereferenceEndpoint
0x140021cfd  mov     rcx, rbx
0x140021d00  call    AfdDereferenceEndpoint
0x140021d05  mov     eax, [rbp+57h+arg_0]
0x140021d08  jmp     loc_1400220B6
0x140021d0d  xor     esi, esi
0x140021d0f  jmp     loc_140021945
0x140021d14  mov     eax, [rsi+rdi+19h]
0x140021d18  mov     r14d, 0C000000Dh
0x140021d1e  mov     dword ptr [rsp+110h+var_E0], r14d
0x140021d23  mov     edx, 3EBh
0x140021d28  mov     dword ptr [rsp+110h+var_E8], eax
0x140021d2c  mov     eax, [rsi+rdi+15h]
0x140021d30  mov     dword ptr [rsp+110h+Timeout], eax
0x140021d34  jmp     loc_1400220A9
0x140021d39  xor     ebx, ebx
0x140021d3b  mov     r14d, 0C000000Dh
0x140021d41  mov     dword ptr [rsp+110h+var_E0], r14d
0x140021d46  mov     edx, 3E9h
0x140021d4b  mov     dword ptr [rsp+110h+var_E8], ebx
0x140021d4f  mov     dword ptr [rsp+110h+Timeout], ebx
0x140021d53  jmp     loc_1400220A6
0x140021d58  xor     esi, esi
0x140021d5a  mov     ebx, 0C0000005h
0x140021d5f  xor     r9d, r9d
0x140021d62  mov     dword ptr [rsp+110h+var_E0], ebx
0x140021d66  mov     edx, 3E8h
0x140021d6b  mov     dword ptr [rsp+110h+var_E8], esi
0x140021d6f  mov     dword ptr [rsp+110h+Timeout], esi
0x140021d73  xor     r8d, r8d
0x140021d76  xor     ecx, ecx
0x140021d78  call    AFDETW_TRACECREATE
0x140021d7d  mov     eax, ebx
0x140021d7f  jmp     loc_1400220B6
0x140021d84  lea     rdx, aAfdswopenpacke; "AfdSwOpenPacket"
0x140021d8b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140021d8f  call    cs:__imp_RtlInitString
0x140021d96  nop     dword ptr [rax+rax+00h]
0x140021d9b  xor     r8d, r8d; CaseInSensitive
0x140021d9e  lea     rdx, [rbp+57h+String2]; String2
0x140021da2  lea     rcx, [rbp+57h+DestinationString]; String1
0x140021da6  call    cs:__imp_RtlEqualString
  ... truncated ...
```
