# HCI_PurgeBips(HCI_INTERFACE *)

- ea: `0x1400aeb90`
- end: `0x1400aeea8`
- name: `?HCI_PurgeBips@@YAXPEAUHCI_INTERFACE@@@Z`
- size: `792`
- prototype: `void __fastcall(struct HCI_INTERFACE *)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400e55f8`
- `0x1401b8308`
- `0x1401bc9c8`

## callees

- `0x140005690`
- `0x140005b4c`
- `0x140033804`
- `0x140046880`
- `0x1400475ec`
- `0x1400aeb90`
- `0x1400afb10`
- `0x140165580`

## import_xrefs

- `ntoskrnl!KeReadStateEvent` at `0x1400aede8`
- `ntoskrnl!KeReadStateEvent` at `0x1400aede8`
- `ntoskrnl!KeClearEvent` at `0x1400aee2e`
- `ntoskrnl!KeClearEvent` at `0x1400aee2e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400aec4b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400aec4b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400aecc4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400aecc4`

## pseudocode

```c
void __fastcall HCI_PurgeBips(struct HCI_INTERFACE *a1)
{
  char v2; // si
  bool v3; // dl
  __int16 DeviceType; // ax
  KIRQL v5; // r14
  _LIST_ENTRY *p_BipQueue; // rdx
  _LIST_ENTRY *Flink; // rcx
  _LIST_ENTRY *v8; // rax
  _LIST_ENTRY **v9; // rax
  int v10; // r8d
  _QWORD *v11; // rax
  __int64 v12; // rcx
  __int128 *v13; // rdx
  _QWORD *v14; // rbx
  bool v15; // r14
  char StateEvent; // al
  int v17; // r8d
  int v18; // edx
  __int16 v19; // ax
  int v20; // [rsp+20h] [rbp-60h]
  __int128 v21; // [rsp+60h] [rbp-20h] BYREF
  struct _LIST_ENTRY v22; // [rsp+70h] [rbp-10h] BYREF

  v21 = 0;
  v22 = 0;
  v2 = 1;
  v3 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  if ( v3 || DeviceType )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v3,
      DeviceType != 0,
      a1->IfrLog,
      5,
      2,
      35,
      (__int64)WPP_d90ccc382b3c325a5f596c542d4908f7_Traceguids,
      a1);
  *((_QWORD *)&v21 + 1) = &v21;
  *(_QWORD *)&v21 = &v21;
  v22.Blink = &v22;
  v22.Flink = &v22;
  v5 = KeAcquireSpinLockRaiseToDpc(&a1->HciLock);
  p_BipQueue = &a1->BipQueue;
  while ( 1 )
  {
    Flink = p_BipQueue->Flink;
    if ( p_BipQueue->Flink == p_BipQueue )
      break;
    if ( Flink->Blink != p_BipQueue
      || (v8 = Flink->Flink, Flink->Flink->Blink != Flink)
      || (p_BipQueue->Flink = v8,
          v8->Blink = p_BipQueue,
          v9 = (_LIST_ENTRY **)*((_QWORD *)&v21 + 1),
          **((__int128 ***)&v21 + 1) != &v21) )
    {
LABEL_25:
      __fastfail(3u);
    }
    Flink->Blink = (_LIST_ENTRY *)*((_QWORD *)&v21 + 1);
    Flink->Flink = (_LIST_ENTRY *)&v21;
    *v9 = Flink;
    *((_QWORD *)&v21 + 1) = Flink;
  }
  HCI_PurgePendedAclBipsLocked(a1, &v22, 0xFFFFu);
  KeReleaseSpinLock(&a1->HciLock, v5);
  while ( 1 )
  {
    v11 = (_QWORD *)v21;
    if ( (__int128 *)v21 == &v21 )
      break;
    if ( *(__int128 **)(v21 + 8) != &v21 )
      goto LABEL_25;
    v12 = *(_QWORD *)v21;
    if ( *(_QWORD *)(*(_QWORD *)v21 + 8LL) != (_QWORD)v21 )
      goto LABEL_25;
    *(_QWORD *)&v21 = *(_QWORD *)v21;
    v13 = &v21;
    *(_QWORD *)(v12 + 8) = &v21;
    v14 = v11 - 11;
    v11[1] = v11;
    *v11 = v11;
    *((_DWORD *)v11 - 19) = -1073741667;
    LOBYTE(v13) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    WPP_RECORDER_AND_TRACE_SF_qLd(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)v13,
      v10,
      a1->IfrLog,
      v20,
      2,
      36,
      (__int64)WPP_d90ccc382b3c325a5f596c542d4908f7_Traceguids,
      (char)v14,
      *((_DWORD *)v14 + 2),
      *((_DWORD *)v14 + 12));
    if ( *((_DWORD *)v14 + 2) == 1 )
      HCI_DoCmdCompletion(a1, (struct _BIP *)v14, 0, -1073741667, 0);
    else
      ((void (__fastcall *)(_QWORD *))v14[23])(v14);
  }
  if ( v22.Flink != &v22 )
    HCI_ProcessPendedAclBipsList(a1, &v22, 0);
  v15 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  StateEvent = KeReadStateEvent(&a1->ThreadEvents[1]);
  LOBYTE(v17) = 1;
  LOBYTE(v18) = v15;
  WPP_RECORDER_AND_TRACE_SF_d(
    WPP_GLOBAL_Control->AttachedDevice,
    v18,
    v17,
    a1->IfrLog,
    4,
    2,
    37,
    (__int64)WPP_d90ccc382b3c325a5f596c542d4908f7_Traceguids,
    StateEvent);
  KeClearEvent(&a1->ThreadEvents[1]);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    v2 = 0;
  v19 = WPP_GLOBAL_Control->DeviceType;
  if ( v2 || v19 )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v2,
      v19 != 0,
      a1->IfrLog,
      5,
      2,
      38,
      (__int64)WPP_d90ccc382b3c325a5f596c542d4908f7_Traceguids,
      a1);
}

```

## disassembly

```asm
0x1400aeb90  push    rbp
0x1400aeb92  push    rbx
0x1400aeb93  push    rsi
0x1400aeb94  push    rdi
0x1400aeb95  push    r12
0x1400aeb97  push    r14
0x1400aeb99  push    r15
0x1400aeb9b  mov     rbp, rsp
0x1400aeb9e  sub     rsp, 80h
0x1400aeba5  xorps   xmm0, xmm0
0x1400aeba8  xorps   xmm1, xmm1
0x1400aebab  movups  [rbp+var_20], xmm0
0x1400aebaf  mov     rdi, rcx
0x1400aebb2  movups  xmmword ptr [rbp+var_10.Flink], xmm1
0x1400aebb6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400aebbd  mov     esi, 1
0x1400aebc2  mov     eax, [rcx+2Ch]
0x1400aebc5  lea     r15d, [rsi+1]
0x1400aebc9  test    r15b, al
0x1400aebcc  jz      short loc_1400AEBD9
0x1400aebce  cmp     byte ptr [rcx+29h], 5
0x1400aebd2  jb      short loc_1400AEBD9
0x1400aebd4  mov     dl, sil
0x1400aebd7  jmp     short loc_1400AEBDB
0x1400aebd9  xor     dl, dl
0x1400aebdb  movzx   eax, word ptr [rcx+48h]
0x1400aebdf  lea     r12, WPP_d90ccc382b3c325a5f596c542d4908f7_Traceguids
0x1400aebe6  test    ax, ax
0x1400aebe9  setnz   r8b
0x1400aebed  test    dl, dl
0x1400aebef  jnz     short loc_1400AEBF6
0x1400aebf1  test    ax, ax
0x1400aebf4  jz      short loc_1400AEC21
0x1400aebf6  mov     r9, [rdi+10B0h]
0x1400aebfd  mov     rcx, [rcx+18h]
0x1400aec01  mov     [rsp+80h+var_40], rdi
0x1400aec06  mov     [rsp+80h+var_48], r12
0x1400aec0b  mov     [rsp+80h+var_50], 23h ; '#'
0x1400aec12  mov     [rsp+80h+var_58], r15d
0x1400aec17  mov     byte ptr [rsp+80h+var_60], 5
0x1400aec1c  call    WPP_RECORDER_AND_TRACE_SF_q
0x1400aec21  lea     rax, [rbp+var_20]
0x1400aec25  mov     qword ptr [rbp+var_20+8], rax
0x1400aec29  lea     rbx, [rdi+7B0h]
0x1400aec30  lea     rax, [rbp+var_20]
0x1400aec34  mov     rcx, rbx; SpinLock
0x1400aec37  mov     qword ptr [rbp+var_20], rax
0x1400aec3b  lea     rax, [rbp+var_10]
0x1400aec3f  mov     [rbp+var_10.Blink], rax
0x1400aec43  lea     rax, [rbp+var_10]
0x1400aec47  mov     [rbp+var_10.Flink], rax
0x1400aec4b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400aec52  nop     dword ptr [rax+rax+00h]
0x1400aec57  mov     r14b, al
0x1400aec5a  lea     rdx, [rdi+9A0h]
0x1400aec61  mov     rcx, [rdx]
0x1400aec64  cmp     rcx, rdx
0x1400aec67  jz      short loc_1400AECAC
0x1400aec69  cmp     [rcx+8], rdx
0x1400aec6d  jnz     loc_1400AEDA1
0x1400aec73  mov     rax, [rcx]
0x1400aec76  cmp     [rax+8], rcx
0x1400aec7a  jnz     loc_1400AEDA1
0x1400aec80  mov     [rdx], rax
0x1400aec83  lea     r8, [rbp+var_20]
0x1400aec87  mov     [rax+8], rdx
0x1400aec8b  mov     rax, qword ptr [rbp+var_20+8]
0x1400aec8f  cmp     [rax], r8
0x1400aec92  jnz     loc_1400AEDA1
0x1400aec98  mov     [rcx+8], rax
0x1400aec9c  lea     r8, [rbp+var_20]
0x1400aeca0  mov     [rcx], r8
0x1400aeca3  mov     [rax], rcx
0x1400aeca6  mov     qword ptr [rbp+var_20+8], rcx
0x1400aecaa  jmp     short loc_1400AEC61
0x1400aecac  mov     r8d, 0FFFFh; unsigned __int16
0x1400aecb2  lea     rdx, [rbp+var_10]; struct _LIST_ENTRY *
0x1400aecb6  mov     rcx, rdi; struct HCI_INTERFACE *
0x1400aecb9  call    ?HCI_PurgePendedAclBipsLocked@@YAXPEAUHCI_INTERFACE@@PEAU_LIST_ENTRY@@G@Z; HCI_PurgePendedAclBipsLocked(HCI_INTERFACE *,_LIST_ENTRY *,ushort)
0x1400aecbe  mov     rcx, rbx; SpinLock
0x1400aecc1  mov     dl, r14b; NewIrql
0x1400aecc4  call    cs:__imp_KeReleaseSpinLock
0x1400aeccb  nop     dword ptr [rax+rax+00h]
0x1400aecd0  mov     r14d, 0C000009Dh
0x1400aecd6  mov     rax, qword ptr [rbp+var_20]
0x1400aecda  lea     rcx, [rbp+var_20]
0x1400aecde  cmp     rax, rcx
0x1400aece1  jz      loc_1400AEDA8
0x1400aece7  lea     rcx, [rbp+var_20]
0x1400aeceb  cmp     [rax+8], rcx
0x1400aecef  jnz     loc_1400AEDA1
0x1400aecf5  mov     rcx, [rax]
0x1400aecf8  cmp     [rcx+8], rax
0x1400aecfc  jnz     loc_1400AEDA1
0x1400aed02  mov     qword ptr [rbp+var_20], rcx
0x1400aed06  lea     rdx, [rbp+var_20]
0x1400aed0a  mov     [rcx+8], rdx
0x1400aed0e  lea     rbx, [rax-58h]
0x1400aed12  mov     [rax+8], rax
0x1400aed16  mov     [rax], rax
0x1400aed19  mov     [rbx+0Ch], r14d
0x1400aed1d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400aed24  mov     eax, [rcx+2Ch]
0x1400aed27  test    r15b, al
0x1400aed2a  jz      short loc_1400AED37
0x1400aed2c  cmp     byte ptr [rcx+29h], 4
0x1400aed30  jb      short loc_1400AED37
0x1400aed32  mov     dl, sil
0x1400aed35  jmp     short loc_1400AED39
0x1400aed37  xor     dl, dl
0x1400aed39  mov     eax, [rbx+30h]
0x1400aed3c  mov     r9, [rdi+10B0h]
0x1400aed43  mov     rcx, [rcx+18h]
0x1400aed47  mov     [rsp+80h+var_30], eax
0x1400aed4b  mov     eax, [rbx+8]
0x1400aed4e  mov     [rsp+80h+var_38], eax
0x1400aed52  mov     [rsp+80h+var_40], rbx
0x1400aed57  mov     [rsp+80h+var_48], r12
0x1400aed5c  mov     [rsp+80h+var_50], 24h ; '$'
0x1400aed63  mov     [rsp+80h+var_58], r15d
0x1400aed68  call    WPP_RECORDER_AND_TRACE_SF_qLd
0x1400aed6d  cmp     [rbx+8], esi
0x1400aed70  jnz     short loc_1400AED8D
0x1400aed72  mov     r9d, r14d; int
0x1400aed75  mov     byte ptr [rsp+80h+var_60], 0; unsigned __int8
0x1400aed7a  xor     r8d, r8d; union _HCI_EVENT *
0x1400aed7d  mov     rdx, rbx; struct _BIP *
0x1400aed80  mov     rcx, rdi; struct HCI_INTERFACE *
0x1400aed83  call    ?HCI_DoCmdCompletion@@YAJPEAUHCI_INTERFACE@@PEAU_BIP@@PEAT_HCI_EVENT@@JE@Z; HCI_DoCmdCompletion(HCI_INTERFACE *,_BIP *,_HCI_EVENT *,long,uchar)
0x1400aed88  jmp     loc_1400AECD6
0x1400aed8d  mov     rax, [rbx+0B8h]
0x1400aed94  mov     rcx, rbx
0x1400aed97  call    _guard_dispatch_icall
0x1400aed9c  jmp     loc_1400AECD6
0x1400aeda1  mov     ecx, 3
0x1400aeda6  int     29h; Win8: RtlFailFast(ecx)
0x1400aeda8  lea     rax, [rbp+var_10]
0x1400aedac  cmp     [rbp+var_10.Flink], rax
0x1400aedb0  jz      short loc_1400AEDC1
0x1400aedb2  xor     r8d, r8d; unsigned __int8
0x1400aedb5  lea     rdx, [rbp+var_10]; struct _LIST_ENTRY *
0x1400aedb9  mov     rcx, rdi; struct HCI_INTERFACE *
0x1400aedbc  call    ?HCI_ProcessPendedAclBipsList@@YAXPEAUHCI_INTERFACE@@PEAU_LIST_ENTRY@@E@Z; HCI_ProcessPendedAclBipsList(HCI_INTERFACE *,_LIST_ENTRY *,uchar)
0x1400aedc1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400aedc8  mov     eax, [rcx+2Ch]
0x1400aedcb  test    r15b, al
0x1400aedce  jz      short loc_1400AEDDB
0x1400aedd0  cmp     byte ptr [rcx+29h], 4
0x1400aedd4  jb      short loc_1400AEDDB
0x1400aedd6  mov     r14b, sil
0x1400aedd9  jmp     short loc_1400AEDDE
0x1400aeddb  xor     r14b, r14b
0x1400aedde  lea     rbx, [rdi+508h]
0x1400aede5  mov     rcx, rbx; Event
0x1400aede8  call    cs:__imp_KeReadStateEvent
0x1400aedef  nop     dword ptr [rax+rax+00h]
0x1400aedf4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400aedfb  mov     r8b, sil
0x1400aedfe  mov     r9, [rdi+10B0h]
0x1400aee05  mov     dl, r14b
0x1400aee08  mov     dword ptr [rsp+80h+var_40], eax
0x1400aee0c  mov     [rsp+80h+var_48], r12
0x1400aee11  mov     rcx, [rcx+18h]
0x1400aee15  mov     [rsp+80h+var_50], 25h ; '%'
0x1400aee1c  mov     [rsp+80h+var_58], r15d
0x1400aee21  mov     byte ptr [rsp+80h+var_60], 4
0x1400aee26  call    WPP_RECORDER_AND_TRACE_SF_d
0x1400aee2b  mov     rcx, rbx; Event
0x1400aee2e  call    cs:__imp_KeClearEvent
0x1400aee35  nop     dword ptr [rax+rax+00h]
0x1400aee3a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400aee41  mov     eax, [rcx+2Ch]
0x1400aee44  test    r15b, al
0x1400aee47  jz      short loc_1400AEE4F
0x1400aee49  cmp     byte ptr [rcx+29h], 5
0x1400aee4d  jnb     short loc_1400AEE52
0x1400aee4f  xor     sil, sil
0x1400aee52  movzx   eax, word ptr [rcx+48h]
0x1400aee56  test    ax, ax
0x1400aee59  setnz   r8b
0x1400aee5d  test    sil, sil
0x1400aee60  jnz     short loc_1400AEE67
0x1400aee62  test    ax, ax
0x1400aee65  jz      short loc_1400AEE95
0x1400aee67  mov     r9, [rdi+10B0h]
0x1400aee6e  mov     dl, sil
0x1400aee71  mov     rcx, [rcx+18h]
0x1400aee75  mov     [rsp+80h+var_40], rdi
0x1400aee7a  mov     [rsp+80h+var_48], r12
0x1400aee7f  mov     [rsp+80h+var_50], 26h ; '&'
0x1400aee86  mov     [rsp+80h+var_58], r15d
0x1400aee8b  mov     byte ptr [rsp+80h+var_60], 5
0x1400aee90  call    WPP_RECORDER_AND_TRACE_SF_q
0x1400aee95  add     rsp, 80h
0x1400aee9c  pop     r15
0x1400aee9e  pop     r14
0x1400aeea0  pop     r12
0x1400aeea2  pop     rdi
0x1400aeea3  pop     rsi
0x1400aeea4  pop     rbx
0x1400aeea5  pop     rbp
0x1400aeea6  retn
```
