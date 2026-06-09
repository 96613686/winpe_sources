# HCI_FindExecutingCmd(HCI_INTERFACE *,_HCI_EVENT *)

- ea: `0x140033e90`
- end: `0x14003422b`
- name: `?HCI_FindExecutingCmd@@YAPEAU_BIP@@PEAUHCI_INTERFACE@@PEAT_HCI_EVENT@@@Z`
- size: `923`
- prototype: `struct _BIP *(struct HCI_INTERFACE *, union _HCI_EVENT *)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14006b0fc`
- `0x14006b1dc`
- `0x1401c248c`

## callees

- `0x140032d14`
- `0x140033e90`
- `0x140035fc8`
- `0x140041f28`
- `0x140077a20`
- `0x140161a44`
- `0x140161d7c`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140034132`
- `ntoskrnl!RtlCompareMemory` at `0x140034132`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140033ee7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140033ee7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003418a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003418a`

## string_xrefs

- `0x140034070`: `onecore\drivers\wdm\bluetooth\drivers\bthport\src\hcicommand.cpp`
- `0x1400341a4`: `onecore\drivers\wdm\bluetooth\drivers\bthport\src\hcicommand.cpp`
- `0x1400341e0`: `onecore\drivers\wdm\bluetooth\drivers\bthport\src\hcicommand.cpp`

## pseudocode

```c
_LIST_ENTRY *__fastcall HCI_FindExecutingCmd(struct HCI_INTERFACE *a1, union _HCI_EVENT *a2)
{
  int Event_Code; // r15d
  unsigned __int8 v5; // al
  _LIST_ENTRY *v6; // rsi
  struct _HCI_CONNECTION *v7; // r13
  _LIST_ENTRY *Flink; // r14
  _LIST_ENTRY **p_Blink; // r12
  char v10; // bl
  __int64 v11; // rbp
  __int16 v12; // cx
  char *v13; // rsi
  __int16 v15; // ax
  bool v16; // zf
  unsigned __int8 v17; // al
  bool v18; // zf
  unsigned __int16 Command_Opcode; // ax
  char v20; // al
  __int64 v21; // rsi
  unsigned __int8 v22; // al
  unsigned __int64 *p_Random_Number; // r10
  struct _HCI_CONNECTION *ConnectionFromBdAddrEx2; // rax
  char v25; // dl
  unsigned int v26; // ecx
  unsigned __int16 Connection_Handle; // ax
  _LIST_ENTRY *v28; // rax
  _LIST_ENTRY *Blink; // rcx
  unsigned __int64 *SpinLock; // [rsp+40h] [rbp-58h]
  KIRQL NewIrql; // [rsp+A8h] [rbp+10h]
  _LIST_ENTRY *p_CmdSentList; // [rsp+B0h] [rbp+18h]

  Event_Code = a2->HciEvent.Event_Code;
  if ( (_BYTE)Event_Code == 62 )
  {
    v5 = a2->Event_Generic.Event_Parameter[0];
    if ( (v5 == 1 || v5 == 10) && a2->Event_Generic.Event_Parameter[4] == 1 )
      return 0;
  }
  v6 = 0;
  v7 = 0;
  SpinLock = &a1->HciLock;
  NewIrql = KeAcquireSpinLockRaiseToDpc(&a1->HciLock);
  Flink = a1->CmdSentList.Flink;
  p_CmdSentList = &a1->CmdSentList;
  if ( Flink == &a1->CmdSentList )
    goto LABEL_72;
  while ( 1 )
  {
    p_Blink = &Flink[-12].Blink;
    v10 = 0;
    v11 = 3LL * LODWORD(Flink[-1].Blink);
    v12 = *((_WORD *)&g_HciCommandTable + 12 * LODWORD(Flink[-1].Blink));
    if ( v12 == -1024 && (_BYTE)Event_Code == 0xFF )
    {
      if ( HCI_CheckVendorPattern((struct _HCI_COMMAND_BIP_CONTEXT *)&Flink[-12].Blink, a2) )
        goto LABEL_37;
      v13 = &byte_140167C10[8 * v11];
      goto LABEL_28;
    }
    v13 = &byte_140167C10[24 * LODWORD(Flink[-1].Blink)];
    if ( *v13 == 90 )
    {
      v16 = (unsigned int)Feature_56240707__private_IsEnabledDeviceUsageNoInline() == 0;
      v15 = *((_WORD *)&g_HciCommandTable + 4 * v11);
      if ( v16 )
      {
        if ( v15 != 1043 )
        {
          if ( v15 != 8217 )
            goto LABEL_28;
          if ( a2->HciEvent.Event_Code != 8 )
          {
            v16 = a2->HciEvent.Event_Code == 48;
            goto LABEL_26;
          }
          goto LABEL_27;
        }
        v16 = a2->HciEvent.Event_Code == 8;
      }
      else
      {
        if ( v15 == 1043 )
        {
          v17 = a2->HciEvent.Event_Code;
          v18 = a2->HciEvent.Event_Code == 8;
        }
        else
        {
          if ( v15 != 8217 )
            goto LABEL_28;
          v17 = a2->HciEvent.Event_Code;
          if ( a2->HciEvent.Event_Code == 8 )
            goto LABEL_27;
          v18 = v17 == 48;
        }
        if ( v18 )
        {
LABEL_27:
          v10 = 1;
LABEL_28:
          if ( v10 )
            goto LABEL_37;
          goto LABEL_34;
        }
        v16 = v17 == 89;
      }
LABEL_26:
      if ( !v16 )
        goto LABEL_28;
      goto LABEL_27;
    }
    if ( (_BYTE)Event_Code == 15 )
    {
      Command_Opcode = a2->Event_CommandStatus.Command_Opcode;
      if ( (Command_Opcode == 8205 || Command_Opcode == 8259) && v12 == Command_Opcode )
        goto LABEL_37;
    }
LABEL_34:
    if ( *v13 != (_BYTE)Event_Code )
      goto LABEL_70;
    v20 = *((_BYTE *)&g_HciCommandTable + 8 * v11 + 17);
    if ( v20 )
    {
      if ( v20 != a2->Event_Generic.Event_Parameter[0] )
        goto LABEL_70;
    }
LABEL_37:
    v21 = *((unsigned __int8 *)&g_HciCommandTable + 8 * v11 + 18);
    if ( !v10 || *((_BYTE *)&g_HciCommandTable + 8 * v11 + 19) )
    {
      p_Random_Number = (unsigned __int64 *)(&a2->HciEvent.Event_Code
                                           + *((unsigned __int8 *)&g_HciCommandTable + 8 * v11 + 19));
    }
    else
    {
      v22 = a2->HciEvent.Event_Code;
      if ( a2->HciEvent.Event_Code == 8 || v22 == 48 || v22 == 89 )
        p_Random_Number = &a2->cc_LE_Rand.Random_Number;
      else
        p_Random_Number = 0;
    }
    if ( (*((_BYTE *)&g_HciCommandTable + 8 * v11 + 20) & 0x10) != 0 )
    {
      ConnectionFromBdAddrEx2 = HCI_GetConnectionFromBdAddrEx2(
                                  a1,
                                  (struct _BDADDR *)p_Random_Number,
                                  1389,
                                  "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hcicommand.cpp",
                                  (void *)0x44494E46,
                                  0,
                                  HciPhyTypeBR);
      v7 = ConnectionFromBdAddrEx2;
      if ( !ConnectionFromBdAddrEx2 )
        goto LABEL_70;
      p_Random_Number = (unsigned __int64 *)&ConnectionFromBdAddrEx2->Info.ConnectionHandle;
    }
    if ( (_BYTE)Event_Code != 15 )
    {
      v25 = *((_BYTE *)&g_HciCommandTable + 8 * v11 + 20);
      if ( (v25 & 1) != 0 )
      {
        v26 = 6;
      }
      else if ( (v25 & 2) != 0 )
      {
        v26 = 2;
      }
      else
      {
        v26 = v25 < 0;
      }
      if ( (_BYTE)Event_Code == 62 )
      {
        if ( a2->Event_Generic.Event_Parameter[0] == 1
          && !a2->Event_UserConfirmationRequest.Numeric_Value
          && !a2->Event_LEConnectionComplete.Peer_Address.NAP )
        {
          goto LABEL_65;
        }
      }
      else if ( (_BYTE)Event_Code == 14
             && a2->Event_ConnectionComplete.Connection_Handle == 2065
             && *((_WORD *)&g_HciCommandTable + 4 * v11) == 2065
             && !a2->Event_ConnectionRequest.BD_ADDR.NAP )
      {
        goto LABEL_65;
      }
      if ( v26 && RtlCompareMemory((char *)p_Blink + v21 + 244, p_Random_Number, v26) != v26 )
        goto LABEL_70;
    }
LABEL_65:
    if ( Event_Code == 14 )
    {
      Connection_Handle = a2->Event_ConnectionComplete.Connection_Handle;
    }
    else
    {
      if ( Event_Code != 15 )
        break;
      Connection_Handle = a2->Event_CommandStatus.Command_Opcode;
    }
    if ( *((_WORD *)p_Blink + 122) == Connection_Handle )
      break;
LABEL_70:
    Flink = Flink->Flink;
    if ( Flink == p_CmdSentList )
    {
      v6 = 0;
      goto LABEL_72;
    }
  }
  v28 = Flink->Flink;
  if ( Flink->Flink->Blink != Flink || (Blink = Flink->Blink, Blink->Flink != Flink) )
    __fastfail(3u);
  Blink->Flink = v28;
  v28->Blink = Blink;
  Flink->Blink = Flink;
  Flink->Flink = Flink;
  v6 = *p_Blink;
  RefObj_AddRefEx(
    p_Blink + 25,
    HCI_FindExecutingCmd,
    1484,
    "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hcicommand.cpp");
  HCI_StartIdleTimer(a1, 1u);
LABEL_72:
  KeReleaseSpinLock(SpinLock, NewIrql);
  if ( v7 )
    RefObj_ReleaseEx(
      &v7->RefObj,
      1145654854,
      1502,
      "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hcicommand.cpp");
  return v6;
}

```

## disassembly

```asm
0x140033e90  mov     [rsp+arg_0], rcx
0x140033e95  push    rbx
0x140033e96  push    rbp
0x140033e97  push    rsi
0x140033e98  push    rdi
0x140033e99  push    r12
0x140033e9b  push    r13
0x140033e9d  push    r14
0x140033e9f  push    r15
0x140033ea1  sub     rsp, 58h
0x140033ea5  movzx   r15d, byte ptr [rdx]
0x140033ea9  mov     rbx, rcx
0x140033eac  mov     rdi, rdx
0x140033eaf  mov     cl, 1
0x140033eb1  cmp     r15b, 3Eh ; '>'
0x140033eb5  jnz     short loc_140033ECB
0x140033eb7  mov     al, [rdx+2]
0x140033eba  cmp     al, cl
0x140033ebc  jnz     loc_140033F6A
0x140033ec2  cmp     [rdx+6], cl
0x140033ec5  jz      loc_140033F77
0x140033ecb  lea     rax, [rbx+7B0h]
0x140033ed2  xor     esi, esi
0x140033ed4  mov     rcx, rax; SpinLock
0x140033ed7  mov     [rsp+98h+arg_18], rsi
0x140033edf  xor     r13d, r13d
0x140033ee2  mov     [rsp+98h+SpinLock], rax
0x140033ee7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140033eee  nop     dword ptr [rax+rax+00h]
0x140033ef3  mov     [rsp+98h+NewIrql], al
0x140033efa  lea     rax, [rbx+970h]
0x140033f01  mov     r14, [rax]
0x140033f04  mov     [rsp+98h+arg_10], rax
0x140033f0c  cmp     r14, rax
0x140033f0f  jz      loc_14003417E
0x140033f15  lea     r12, [r14-0B8h]
0x140033f1c  xor     bl, bl
0x140033f1e  mov     eax, [r12+0B0h]
0x140033f26  lea     r8, ?g_HciCommandTable@@3QBU_HCI_COMMAND_ENTRY@@B; _HCI_COMMAND_ENTRY const near * const g_HciCommandTable
0x140033f2d  lea     rbp, [rax+rax*2]
0x140033f31  mov     eax, 0FC00h
0x140033f36  movzx   ecx, word ptr [r8+rbp*8]
0x140033f3b  cmp     cx, ax
0x140033f3e  jnz     short loc_140033F7E
0x140033f40  cmp     r15b, 0FFh
0x140033f44  jnz     short loc_140033F7E
0x140033f46  mov     rdx, rdi; union _HCI_EVENT *
0x140033f49  mov     rcx, r12; struct _HCI_COMMAND_BIP_CONTEXT *
0x140033f4c  call    ?HCI_CheckVendorPattern@@YAEPEAU_HCI_COMMAND_BIP_CONTEXT@@PEAT_HCI_EVENT@@@Z; HCI_CheckVendorPattern(_HCI_COMMAND_BIP_CONTEXT *,_HCI_EVENT *)
0x140033f51  lea     r8, ?g_HciCommandTable@@3QBU_HCI_COMMAND_ENTRY@@B; _HCI_COMMAND_ENTRY const near * const g_HciCommandTable
0x140033f58  test    al, al
0x140033f5a  jnz     loc_14003402C
0x140033f60  lea     rsi, [r8+10h]
0x140033f64  lea     rsi, [rsi+rbp*8]
0x140033f68  jmp     short loc_140033FE8
0x140033f6a  cmp     al, 0Ah
0x140033f6c  jnz     loc_140033ECB
0x140033f72  jmp     loc_140033EC2
0x140033f77  xor     eax, eax
0x140033f79  jmp     loc_1400341B9
0x140033f7e  lea     rsi, [r8+10h]
0x140033f82  lea     rsi, [rsi+rbp*8]
0x140033f86  cmp     byte ptr [rsi], 5Ah ; 'Z'
0x140033f89  jnz     short loc_140033FEE
0x140033f8b  call    Feature_56240707__private_IsEnabledDeviceUsageNoInline
0x140033f90  lea     r8, ?g_HciCommandTable@@3QBU_HCI_COMMAND_ENTRY@@B; _HCI_COMMAND_ENTRY const near * const g_HciCommandTable
0x140033f97  test    eax, eax
0x140033f99  movzx   eax, word ptr [r8+rbp*8]
0x140033f9e  mov     ecx, 413h
0x140033fa3  jnz     short loc_140033FC3
0x140033fa5  cmp     ax, cx
0x140033fa8  jz      short loc_140033FBE
0x140033faa  mov     ecx, 2019h
0x140033faf  cmp     ax, cx
0x140033fb2  jnz     short loc_140033FE8
0x140033fb4  mov     al, [rdi]
0x140033fb6  cmp     al, 8
0x140033fb8  jz      short loc_140033FE6
0x140033fba  cmp     al, 30h ; '0'
0x140033fbc  jmp     short loc_140033FE4
0x140033fbe  cmp     byte ptr [rdi], 8
0x140033fc1  jmp     short loc_140033FE4
0x140033fc3  cmp     ax, cx
0x140033fc6  jz      short loc_140033FDC
0x140033fc8  mov     ecx, 2019h
0x140033fcd  cmp     ax, cx
0x140033fd0  jnz     short loc_140033FE8
0x140033fd2  mov     al, [rdi]
0x140033fd4  cmp     al, 8
0x140033fd6  jz      short loc_140033FE6
0x140033fd8  cmp     al, 30h ; '0'
0x140033fda  jmp     short loc_140033FE0
0x140033fdc  mov     al, [rdi]
0x140033fde  cmp     al, 8
0x140033fe0  jz      short loc_140033FE6
0x140033fe2  cmp     al, 59h ; 'Y'
0x140033fe4  jnz     short loc_140033FE8
0x140033fe6  mov     bl, 1
0x140033fe8  test    bl, bl
0x140033fea  jnz     short loc_14003402C
0x140033fec  jmp     short loc_140034011
0x140033fee  cmp     r15b, 0Fh
0x140033ff2  jnz     short loc_140034011
0x140033ff4  movzx   eax, word ptr [rdi+4]
0x140033ff8  mov     edx, 200Dh
0x140033ffd  cmp     ax, dx
0x140034000  jz      short loc_14003400C
0x140034002  mov     edx, 2043h
0x140034007  cmp     ax, dx
0x14003400a  jnz     short loc_140034011
0x14003400c  cmp     cx, ax
0x14003400f  jz      short loc_14003402C
0x140034011  cmp     [rsi], r15b
0x140034014  jnz     loc_140034165
0x14003401a  mov     al, [r8+rbp*8+11h]
0x14003401f  test    al, al
0x140034021  jz      short loc_14003402C
0x140034023  cmp     al, [rdi+2]
0x140034026  jnz     loc_140034165
0x14003402c  movzx   esi, byte ptr [r8+rbp*8+12h]
0x140034032  test    bl, bl
0x140034034  jz      short loc_140034057
0x140034036  cmp     byte ptr [r8+rbp*8+13h], 0
0x14003403c  jnz     short loc_140034057
0x14003403e  mov     al, [rdi]
0x140034040  cmp     al, 8
0x140034042  jz      short loc_140034051
0x140034044  cmp     al, 30h ; '0'
0x140034046  jz      short loc_140034051
0x140034048  cmp     al, 59h ; 'Y'
0x14003404a  jz      short loc_140034051
0x14003404c  xor     r10d, r10d
0x14003404f  jmp     short loc_140034060
0x140034051  lea     r10, [rdi+3]
0x140034055  jmp     short loc_140034060
0x140034057  movzx   r10d, byte ptr [r8+rbp*8+13h]
0x14003405d  add     r10, rdi
0x140034060  test    byte ptr [r8+rbp*8+14h], 10h
0x140034066  jz      short loc_1400340B2
0x140034068  mov     rcx, [rsp+98h+arg_0]; struct HCI_INTERFACE *
0x140034070  lea     r9, aOnecoreDrivers_61; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140034077  mov     [rsp+98h+var_68], 0; enum _HCI_PHY_TYPE
0x14003407c  mov     r8d, 56Dh; int
0x140034082  mov     [rsp+98h+var_70], 0; char
0x140034087  mov     rdx, r10; struct _BDADDR *
0x14003408a  mov     [rsp+98h+var_78], 44494E46h; void *
0x140034093  call    ?HCI_GetConnectionFromBdAddrEx2@@YAPEAU_HCI_CONNECTION@@PEAUHCI_INTERFACE@@PEAU_BDADDR@@JPEADPEAXEW4_HCI_PHY_TYPE@@@Z; HCI_GetConnectionFromBdAddrEx2(HCI_INTERFACE *,_BDADDR *,long,char *,void *,uchar,_HCI_PHY_TYPE)
0x140034098  mov     r13, rax
0x14003409b  test    rax, rax
0x14003409e  jz      loc_140034165
0x1400340a4  lea     r10, [rax+80h]
0x1400340ab  lea     r8, ?g_HciCommandTable@@3QBU_HCI_COMMAND_ENTRY@@B; _HCI_COMMAND_ENTRY const near * const g_HciCommandTable
0x1400340b2  cmp     r15b, 0Fh
0x1400340b6  jz      loc_140034143
0x1400340bc  mov     dl, [r8+rbp*8+14h]
0x1400340c1  test    dl, 1
0x1400340c4  jz      short loc_1400340CD
0x1400340c6  mov     ecx, 6
0x1400340cb  jmp     short loc_1400340E0
0x1400340cd  test    dl, 2
0x1400340d0  jz      short loc_1400340D9
0x1400340d2  mov     ecx, 2
0x1400340d7  jmp     short loc_1400340E0
0x1400340d9  xor     ecx, ecx
0x1400340db  test    dl, dl
0x1400340dd  sets    cl
0x1400340e0  cmp     r15b, 3Eh ; '>'
0x1400340e4  jnz     short loc_1400340FC
0x1400340e6  cmp     byte ptr [rdi+2], 1
0x1400340ea  jnz     short loc_14003411C
0x1400340ec  cmp     dword ptr [rdi+8], 0
0x1400340f0  jnz     short loc_14003411C
0x1400340f2  xor     eax, eax
0x1400340f4  cmp     ax, [rdi+0Ch]
0x1400340f8  jnz     short loc_14003411C
0x1400340fa  jmp     short loc_140034143
0x1400340fc  cmp     r15b, 0Eh
0x140034100  jnz     short loc_14003411C
0x140034102  mov     eax, 811h
0x140034107  cmp     ax, [rdi+3]
0x14003410b  jnz     short loc_14003411C
0x14003410d  cmp     ax, [r8+rbp*8]
0x140034112  jnz     short loc_14003411C
0x140034114  xor     eax, eax
0x140034116  cmp     ax, [rdi+6]
0x14003411a  jz      short loc_140034143
0x14003411c  test    ecx, ecx
0x14003411e  jz      short loc_140034143
0x140034120  mov     ebx, ecx
0x140034122  mov     rdx, r10; Source2
0x140034125  lea     rcx, [rsi+0F4h]
0x14003412c  mov     r8d, ebx; Length
0x14003412f  add     rcx, r12; Source1
0x140034132  call    cs:__imp_RtlCompareMemory
0x140034139  nop     dword ptr [rax+rax+00h]
0x14003413e  cmp     rax, rbx
0x140034141  jnz     short loc_140034165
0x140034143  mov     ecx, r15d
0x140034146  sub     ecx, 0Eh
0x140034149  jz      short loc_140034156
0x14003414b  cmp     ecx, 1
0x14003414e  jnz     short loc_1400341CB
0x140034150  movzx   eax, word ptr [rdi+4]
0x140034154  jmp     short loc_14003415A
0x140034156  movzx   eax, word ptr [rdi+3]
0x14003415a  cmp     [r12+0F4h], ax
0x140034163  jz      short loc_1400341CB
0x140034165  mov     r14, [r14]
0x140034168  cmp     r14, [rsp+98h+arg_10]
0x140034170  jnz     loc_140033F15
0x140034176  mov     rsi, [rsp+98h+arg_18]
0x14003417e  mov     dl, [rsp+98h+NewIrql]; NewIrql
0x140034185  mov     rcx, [rsp+98h+SpinLock]; SpinLock
0x14003418a  call    cs:__imp_KeReleaseSpinLock
0x140034191  nop     dword ptr [rax+rax+00h]
0x140034196  test    r13, r13
0x140034199  jz      short loc_1400341B6
0x14003419b  lea     rcx, [r13+8]
0x14003419f  mov     edx, 44494E46h
0x1400341a4  lea     r9, aOnecoreDrivers_61; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400341ab  mov     r8d, 5DEh
0x1400341b1  call    RefObj_ReleaseEx
0x1400341b6  mov     rax, rsi
0x1400341b9  add     rsp, 58h
0x1400341bd  pop     r15
0x1400341bf  pop     r14
0x1400341c1  pop     r13
0x1400341c3  pop     r12
0x1400341c5  pop     rdi
0x1400341c6  pop     rsi
0x1400341c7  pop     rbp
0x1400341c8  pop     rbx
0x1400341c9  retn
0x1400341cb  mov     rax, [r14]
0x1400341ce  cmp     [rax+8], r14
0x1400341d2  jnz     short loc_140034224
0x1400341d4  mov     rcx, [r14+8]
0x1400341d8  cmp     [rcx], r14
0x1400341db  jnz     short loc_140034224
0x1400341dd  mov     [rcx], rax
0x1400341e0  lea     r9, aOnecoreDrivers_61; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400341e7  mov     [rax+8], rcx
0x1400341eb  lea     rdx, ?HCI_FindExecutingCmd@@YAPEAU_BIP@@PEAUHCI_INTERFACE@@PEAT_HCI_EVENT@@@Z; HCI_FindExecutingCmd(HCI_INTERFACE *,_HCI_EVENT *)
0x1400341f2  mov     [r14+8], r14
0x1400341f6  lea     rcx, [r12+0C8h]
0x1400341fe  mov     [r14], r14
0x140034201  mov     r8d, 5CCh
0x140034207  mov     rsi, [r12]
0x14003420b  call    RefObj_AddRefEx
0x140034210  mov     rcx, [rsp+98h+arg_0]; struct HCI_INTERFACE *
0x140034218  mov     dl, 1; unsigned __int8
0x14003421a  call    ?HCI_StartIdleTimer@@YAXPEAUHCI_INTERFACE@@E@Z; HCI_StartIdleTimer(HCI_INTERFACE *,uchar)
0x14003421f  jmp     loc_14003417E
0x140034224  mov     ecx, 3
0x140034229  int     29h; Win8: RtlFailFast(ecx)
```
