# FwpsGetPacketListSecurityInformation0

- ea: `0x1800036b0`
- end: `0x180003973`
- name: `FwpsGetPacketListSecurityInformation0`
- size: `707`
- prototype: `NTSTATUS __stdcall(NET_BUFFER_LIST *packetList, UINT32 queryFlags, FWPS_PACKET_LIST_INFORMATION0 *packetInformation)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800036b0`
- `0x180004904`
- `0x18000de60`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x180003709`
- `ntoskrnl!MmBadPointer` at `0x180003785`
- `ntoskrnl!MmBadPointer` at `0x180003835`
- `NETIO!WfpNblInfoGet` at `0x1800036f8`
- `NETIO!WfpNblInfoGet` at `0x18000376d`
- `NETIO!WfpNblInfoGet` at `0x1800036f8`
- `NETIO!WfpNblInfoGet` at `0x18000376d`

## string_xrefs

- `0x180003738`: `FwpsIPSecGetPacketListSecurityInformation`
- `0x180003918`: `FwpsIPSecGetPacketListSecurityInformation`
- `0x18000381e`: `FwpsGetPacketListSecurityInformation0`
- `0x1800038c0`: `FwpsGetPacketListSecurityInformation0`
- `0x1800038da`: `FwpsGetPacketListSecurityInformation0`

## pseudocode

```c
NTSTATUS __stdcall FwpsGetPacketListSecurityInformation0(
        NET_BUFFER_LIST *packetList,
        UINT32 queryFlags,
        FWPS_PACKET_LIST_INFORMATION0 *packetInformation)
{
  char v4; // bp
  __int64 v6; // rbx
  _QWORD *v7; // rax
  _QWORD *v8; // rcx
  _DWORD *v9; // rdx
  __int64 v10; // r8
  _QWORD *v11; // rdx
  _QWORD *v12; // rax
  bool v14; // zf
  UINT32 v15; // ecx
  UINT32 v16; // eax
  UINT32 v17; // ecx
  UINT32 v18; // r8d
  int v19; // eax
  UINT32 v20; // ecx

  v4 = queryFlags;
  if ( packetList )
  {
    if ( !packetInformation )
    {
      LODWORD(v6) = WfpReportSysErrorAsNtStatus(
                      (__int64)packetList,
                      (int)"FwpsGetPacketListSecurityInformation0",
                      -1071513572);
      return v6;
    }
    if ( (queryFlags & 3) == 3 )
    {
      LODWORD(v6) = WfpReportSysErrorAsNtStatus(
                      (__int64)packetList,
                      (int)"FwpsGetPacketListSecurityInformation0",
                      -1071513570);
      return v6;
    }
    LODWORD(v6) = 0;
    if ( (queryFlags & 4) == 0 )
      goto LABEL_22;
    v7 = (_QWORD *)WfpNblInfoGet(packetList);
    if ( v7 )
    {
      v8 = MmBadPointer;
      if ( v7 != MmBadPointer )
      {
        v9 = (_DWORD *)v7[3];
        if ( v9 )
          goto LABEL_8;
      }
    }
    v11 = (_QWORD *)WfpNblInfoGet(packetList);
    if ( !v11 || (v12 = MmBadPointer, v11 == MmBadPointer) )
    {
      v8 = MmBadPointer;
      if ( v11 != MmBadPointer )
        goto LABEL_21;
      v12 = MmBadPointer;
    }
    else
    {
      v8 = (_QWORD *)v11[1];
    }
    if ( v8 )
    {
      if ( v8 != v12 && (unsigned int)(*((_DWORD *)v8 + 1) - 1) <= 1 )
      {
        v9 = (_DWORD *)v8[42];
        if ( v9 )
        {
LABEL_8:
          if ( (v4 & 1) != 0 && (*v9 & 2) != 0 || (v4 & 2) != 0 && (*v9 & 1) != 0 )
          {
            v6 = WfpReportSysErrorAsNtStatus((__int64)v8, (int)"FwpsIPSecGetPacketListSecurityInformation", -1071513570);
            if ( v6
              && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
            {
              WPP_SF_sd(
                (__int64)WPP_GLOBAL_Control->AttachedDevice,
                0xFu,
                v10,
                "FwpsIPSecGetPacketListSecurityInformation",
                v6);
              return v6;
            }
            if ( v6 )
              return v6;
          }
          else
          {
            packetInformation->ipsecInformation.flags = 0;
            v14 = (*v9 & 1) == 0;
            packetInformation->ipsecInformation.flags = 1;
            if ( v14 )
            {
              if ( (*v9 & 0x200000) != 0 )
              {
                packetInformation->ipsecInformation.flags = 13;
              }
              else
              {
                v20 = (*v9 & 4 | 2u) >> 1;
                packetInformation->ipsecInformation.flags = v20;
                packetInformation->ipsecInformation.flags = v20 | (*v9 >> 1) & 4;
              }
            }
            else
            {
              v15 = (*v9 & 4 | 2u) >> 1;
              packetInformation->ipsecInformation.flags = v15;
              v16 = v15 | (*v9 >> 1) & 4;
              packetInformation->ipsecInformation.flags = v16;
              v17 = v16 | (*v9 >> 1) & 8;
              packetInformation->ipsecInformation.flags = v17;
              v18 = v17 | (*v9 >> 1) & 0x10;
              packetInformation->ipsecInformation.flags = v18;
              if ( (v18 & 4) == 0 || (v19 = 32, (*v9 & 0x400000) != 0) )
                v19 = 0;
              packetInformation->ipsecInformation.flags = v19 | v18;
            }
          }
          goto LABEL_22;
        }
      }
    }
LABEL_21:
    packetInformation->ipsecInformation.flags = 0;
LABEL_22:
    if ( (v4 & 8) != 0 )
    {
      if ( (packetList->Flags & 0x1000000) != 0 )
        *(_DWORD *)&packetInformation->fwpInformation |= 1u;
      LODWORD(v6) = 0;
    }
    return v6;
  }
  LODWORD(v6) = -1071513572;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
  {
    WPP_SF_sd(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0xAu,
      (__int64)packetInformation,
      "FwpsGetPacketListSecurityInformation0",
      -1071513572);
  }
  return v6;
}

```

## disassembly

```asm
0x1800036b0  mov     [rsp+arg_10], rbx
0x1800036b5  push    rbp
0x1800036b6  push    rsi
0x1800036b7  push    rdi
0x1800036b8  sub     rsp, 30h
0x1800036bc  mov     rdi, r8
0x1800036bf  mov     ebp, edx
0x1800036c1  mov     rsi, rcx
0x1800036c4  test    rcx, rcx
0x1800036c7  jz      loc_1800037F1
0x1800036cd  test    r8, r8
0x1800036d0  jz      loc_1800038B9
0x1800036d6  mov     eax, edx
0x1800036d8  and     eax, 3
0x1800036db  cmp     al, 3
0x1800036dd  jz      loc_1800038D4
0x1800036e3  mov     [rsp+48h+arg_8], r14
0x1800036e8  xor     r14d, r14d
0x1800036eb  mov     ebx, r14d
0x1800036ee  test    bpl, 4
0x1800036f2  jz      loc_1800037C3
0x1800036f8  call    cs:__imp_WfpNblInfoGet
0x1800036ff  nop     dword ptr [rax+rax+00h]
0x180003704  test    rax, rax
0x180003707  jz      short loc_18000376A
0x180003709  mov     rcx, cs:MmBadPointer
0x180003710  cmp     rax, [rcx]
0x180003713  jz      short loc_18000376A
0x180003715  mov     rdx, [rax+18h]
0x180003719  test    rdx, rdx
0x18000371c  jz      short loc_18000376A
0x18000371e  test    bpl, 1
0x180003722  jz      loc_180003850
0x180003728  mov     eax, [rdx]
0x18000372a  test    al, 2
0x18000372c  jz      loc_180003850
0x180003732  mov     r8d, 0C022001Eh
0x180003738  lea     rdx, aFwpsipsecgetpa; "FwpsIPSecGetPacketListSecurityInformati"...
0x18000373f  call    WfpReportSysErrorAsNtStatus
0x180003744  mov     rbx, rax
0x180003747  test    rax, rax
0x18000374a  jz      short loc_180003763
0x18000374c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003753  lea     rax, WPP_GLOBAL_Control
0x18000375a  cmp     rcx, rax
0x18000375d  jnz     loc_1800038FD
0x180003763  test    rbx, rbx
0x180003766  jz      short loc_1800037C3
0x180003768  jmp     short loc_1800037DC
0x18000376a  mov     rcx, rsi
0x18000376d  call    cs:__imp_WfpNblInfoGet
0x180003774  nop     dword ptr [rax+rax+00h]
0x180003779  mov     rdx, rax
0x18000377c  test    rax, rax
0x18000377f  jz      loc_180003835
0x180003785  mov     rcx, cs:MmBadPointer
0x18000378c  mov     rax, [rcx]
0x18000378f  cmp     rdx, rax
0x180003792  jz      loc_180003835
0x180003798  mov     rcx, [rdx+8]
0x18000379c  test    rcx, rcx
0x18000379f  jz      short loc_1800037C0
0x1800037a1  cmp     rcx, rax
0x1800037a4  jz      short loc_1800037C0
0x1800037a6  mov     eax, [rcx+4]
0x1800037a9  dec     eax
0x1800037ab  cmp     eax, 1
0x1800037ae  ja      short loc_1800037C0
0x1800037b0  mov     rdx, [rcx+150h]
0x1800037b7  test    rdx, rdx
0x1800037ba  jnz     loc_18000371E
0x1800037c0  mov     [rdi], r14d
0x1800037c3  test    bpl, 8
0x1800037c7  jz      short loc_1800037DC
0x1800037c9  test    dword ptr [rsi+88h], 1000000h
0x1800037d3  jz      short loc_1800037D9
0x1800037d5  or      dword ptr [rdi+4], 1
0x1800037d9  mov     rbx, r14
0x1800037dc  mov     r14, [rsp+48h+arg_8]
0x1800037e1  mov     eax, ebx
0x1800037e3  mov     rbx, [rsp+48h+arg_10]
0x1800037e8  add     rsp, 30h
0x1800037ec  pop     rdi
0x1800037ed  pop     rsi
0x1800037ee  pop     rbp
0x1800037ef  retn
0x1800037f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800037f8  lea     rax, WPP_GLOBAL_Control
0x1800037ff  mov     rbx, 0FFFFFFFFC022001Ch
0x180003806  cmp     rcx, rax
0x180003809  jz      short loc_1800037E1
0x18000380b  cmp     byte ptr [rcx+29h], 2
0x18000380f  jb      short loc_1800037E1
0x180003811  test    dword ptr [rcx+2Ch], 1000h
0x180003818  jz      short loc_1800037E1
0x18000381a  mov     rcx, [rcx+18h]
0x18000381e  lea     r9, aFwpsgetpacketl; "FwpsGetPacketListSecurityInformation0"
0x180003825  mov     edx, 0Ah
0x18000382a  mov     [rsp+48h+var_28], ebx
0x18000382e  call    WPP_SF_sd
0x180003833  jmp     short loc_1800037E1
0x180003835  mov     rax, cs:MmBadPointer
0x18000383c  mov     rcx, [rax]
0x18000383f  cmp     rdx, rcx
0x180003842  jnz     loc_1800037C0
0x180003848  mov     rax, rcx
0x18000384b  jmp     loc_18000379C
0x180003850  test    bpl, 2
0x180003854  jnz     loc_1800038EE
0x18000385a  mov     [rdi], r14d
0x18000385d  test    dword ptr [rdx], 1
0x180003863  mov     dword ptr [rdi], 1
0x180003869  mov     ecx, [rdx]
0x18000386b  jz      loc_180003948
0x180003871  and     ecx, 4
0x180003874  or      ecx, 2
0x180003877  shr     ecx, 1
0x180003879  mov     [rdi], ecx
0x18000387b  mov     eax, [rdx]
0x18000387d  shr     eax, 1
0x18000387f  and     eax, 4
0x180003882  or      eax, ecx
0x180003884  mov     [rdi], eax
0x180003886  mov     ecx, [rdx]
0x180003888  shr     ecx, 1
0x18000388a  and     ecx, 8
0x18000388d  or      ecx, eax
0x18000388f  mov     [rdi], ecx
0x180003891  mov     r8d, [rdx]
0x180003894  shr     r8d, 1
0x180003897  and     r8d, 10h
0x18000389b  or      r8d, ecx
0x18000389e  mov     [rdi], r8d
0x1800038a1  test    r8b, 4
0x1800038a5  jnz     loc_180003932
0x1800038ab  mov     eax, r14d
0x1800038ae  or      r8d, eax
0x1800038b1  mov     [rdi], r8d
0x1800038b4  jmp     loc_1800037C3
0x1800038b9  mov     r8, 0FFFFFFFFC022001Ch
0x1800038c0  lea     rdx, aFwpsgetpacketl; "FwpsGetPacketListSecurityInformation0"
0x1800038c7  call    WfpReportSysErrorAsNtStatus
0x1800038cc  mov     rbx, rax
0x1800038cf  jmp     loc_1800037E1
0x1800038d4  mov     r8d, 0C022001Eh
0x1800038da  lea     rdx, aFwpsgetpacketl; "FwpsGetPacketListSecurityInformation0"
0x1800038e1  call    WfpReportSysErrorAsNtStatus
0x1800038e6  mov     rbx, rax
0x1800038e9  jmp     loc_1800037E1
0x1800038ee  mov     eax, [rdx]
0x1800038f0  test    al, 1
0x1800038f2  jz      loc_18000385A
0x1800038f8  jmp     loc_180003732
0x1800038fd  cmp     byte ptr [rcx+29h], 2
0x180003901  jb      loc_180003763
0x180003907  test    dword ptr [rcx+2Ch], 1000h
0x18000390e  jz      loc_180003763
0x180003914  mov     rcx, [rcx+18h]
0x180003918  lea     r9, aFwpsipsecgetpa; "FwpsIPSecGetPacketListSecurityInformati"...
0x18000391f  mov     edx, 0Fh
0x180003924  mov     [rsp+48h+var_28], ebx
0x180003928  call    WPP_SF_sd
0x18000392d  jmp     loc_1800037DC
0x180003932  test    dword ptr [rdx], 400000h
0x180003938  mov     eax, 20h ; ' '
0x18000393d  jz      loc_1800038AE
0x180003943  jmp     loc_1800038AB
0x180003948  bt      ecx, 15h
0x18000394c  jnb     short loc_180003959
0x18000394e  mov     dword ptr [rdi], 0Dh
0x180003954  jmp     loc_1800037C3
0x180003959  and     ecx, 4
0x18000395c  or      ecx, 2
0x18000395f  shr     ecx, 1
0x180003961  mov     [rdi], ecx
0x180003963  mov     eax, [rdx]
0x180003965  shr     eax, 1
0x180003967  and     eax, 4
0x18000396a  or      eax, ecx
0x18000396c  mov     [rdi], eax
0x18000396e  jmp     loc_1800037C3
```
