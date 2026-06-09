# HCI_AclWriteSegmentComplete(_BIP *)

- ea: `0x14002e440`
- end: `0x14002e673`
- name: `?HCI_AclWriteSegmentComplete@@YAXPEAU_BIP@@@Z`
- size: `563`
- prototype: `void __fastcall(PVOID Entry)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140005ce8`
- `0x14000764c`
- `0x14002e440`
- `0x1400302bc`
- `0x14015ce04`
- `0x14015ce38`
- `0x140161d7c`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002e659`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002e659`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002e622`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002e622`

## string_xrefs

- `0x14002e63a`: `onecore\drivers\wdm\bluetooth\drivers\bthport\src\hciaclwrite.cpp`

## pseudocode

```c
void __fastcall HCI_AclWriteSegmentComplete(unsigned int *Entry)
{
  __int64 v1; // rbp
  int v3; // esi
  __int64 v4; // rdi
  struct HCI_INTERFACE *v5; // r14
  __int64 v6; // r15
  bool v7; // dl
  struct _HCI_CONNECTION *v8; // rdx
  __int64 v9; // rdx
  bool v10; // r10

  v1 = *((_QWORD *)Entry + 19);
  v3 = Entry[3];
  v4 = *(_QWORD *)(v1 + 8);
  v5 = *(struct HCI_INTERFACE **)(v1 + 16);
  v6 = *(_QWORD *)(v4 + 152);
  if ( v3 >= 0 )
  {
    v9 = Entry[8];
    if ( (_DWORD)v9 == Entry[12] )
    {
      if ( (unsigned int)v9 <= 4 )
        MicrosoftTelemetryAssertTriggeredArgsMsgKM(
          "bthport.sys",
          v9,
          0,
          "Each segment is expected to have the data packet header.");
      else
        *(_DWORD *)(v4 + 32) += v9 - 4;
      LOBYTE(v9) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      WPP_RECORDER_AND_TRACE_SF_qi(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        1,
        v5->IfrLog,
        4,
        2,
        34,
        (__int64)WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids,
        v4,
        (char)Entry);
    }
    else
    {
      v3 = -1073741762;
      v10 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      LOBYTE(v9) = v10;
      WPP_RECORDER_AND_TRACE_SF_qiD(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        1,
        v5->IfrLog,
        2,
        2,
        33,
        (__int64)WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids,
        v4,
        (char)Entry,
        Entry[8]);
      MicrosoftTelemetryAssertTriggeredArgsMsgKM(
        "bthport.sys",
        Entry[8],
        Entry[12],
        "Transport design does not allow for partial but successful transfer.");
    }
  }
  else
  {
    v7 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    WPP_RECORDER_AND_TRACE_SF_qiD(
      WPP_GLOBAL_Control->AttachedDevice,
      v7,
      1,
      v5->IfrLog,
      2,
      2,
      32,
      (__int64)WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids,
      v4,
      (char)Entry,
      v3);
    if ( *(_BYTE *)(v1 + 105) )
    {
      v8 = *(struct _HCI_CONNECTION **)(v6 + 96);
      if ( v8 )
        HCI_ReclaimAclWriteCreditsFromConnection(v5, v8, 1u);
      else
        MicrosoftTelemetryAssertTriggeredMsgKM("Segment should have been sent to transport only after referencing connection.");
    }
  }
  if ( *(int *)(v4 + 12) >= 0 && v3 < 0 )
    *(_DWORD *)(v4 + 12) = v3;
  ExFreeToNPagedLookasideList(&v5->WritePacketLookasideList, *((PVOID *)Entry + 5));
  *((_QWORD *)Entry + 5) = 0;
  RefObj_ReleaseEx(v6 + 72, v6, 774, "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hciaclwrite.cpp");
  ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(*(_QWORD *)Entry + 112LL), Entry);
}

```

## disassembly

```asm
0x14002e440  push    rbx
0x14002e442  push    rbp
0x14002e443  push    rsi
0x14002e444  push    rdi
0x14002e445  push    r14
0x14002e447  push    r15
0x14002e449  sub     rsp, 68h
0x14002e44d  mov     rbp, [rcx+98h]
0x14002e454  mov     rbx, rcx
0x14002e457  mov     esi, [rcx+0Ch]
0x14002e45a  mov     rdi, [rbp+8]
0x14002e45e  mov     r14, [rbp+10h]
0x14002e462  mov     r15, [rdi+98h]
0x14002e469  test    esi, esi
0x14002e46b  jns     loc_14002E503
0x14002e471  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002e478  mov     eax, [rcx+2Ch]
0x14002e47b  test    al, 2
0x14002e47d  jz      short loc_14002E489
0x14002e47f  cmp     byte ptr [rcx+29h], 2
0x14002e483  jb      short loc_14002E489
0x14002e485  mov     dl, 1
0x14002e487  jmp     short loc_14002E48B
0x14002e489  xor     dl, dl
0x14002e48b  mov     r9, [r14+10B0h]
0x14002e492  lea     rax, WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids
0x14002e499  mov     rcx, [rcx+18h]
0x14002e49d  mov     r8b, 1
0x14002e4a0  mov     [rsp+98h+var_48], esi
0x14002e4a4  mov     [rsp+98h+var_50], rbx
0x14002e4a9  mov     [rsp+98h+var_58], rdi
0x14002e4ae  mov     [rsp+98h+var_60], rax
0x14002e4b3  mov     [rsp+98h+var_68], 20h ; ' '
0x14002e4ba  mov     [rsp+98h+var_70], 2
0x14002e4c2  mov     [rsp+98h+var_78], 2
0x14002e4c7  call    WPP_RECORDER_AND_TRACE_SF_qiD
0x14002e4cc  cmp     byte ptr [rbp+69h], 0
0x14002e4d0  jz      loc_14002E60A
0x14002e4d6  mov     rdx, [r15+60h]; struct _HCI_CONNECTION *
0x14002e4da  test    rdx, rdx
0x14002e4dd  jz      short loc_14002E4F2
0x14002e4df  mov     r8d, 1; unsigned __int16
0x14002e4e5  mov     rcx, r14; struct HCI_INTERFACE *
0x14002e4e8  call    ?HCI_ReclaimAclWriteCreditsFromConnection@@YAXPEAUHCI_INTERFACE@@PEAU_HCI_CONNECTION@@G@Z; HCI_ReclaimAclWriteCreditsFromConnection(HCI_INTERFACE *,_HCI_CONNECTION *,ushort)
0x14002e4ed  jmp     loc_14002E60A
0x14002e4f2  lea     rcx, aSegmentShouldH; __annotation("Debug", "TelemetryAssert", "false", "Segment should have been sent to transport only after referencing connection.")
0x14002e4f9  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14002e4fe  jmp     loc_14002E60A
0x14002e503  mov     edx, [rcx+20h]
0x14002e506  cmp     edx, [rcx+30h]
0x14002e509  jz      loc_14002E590
0x14002e50f  mov     esi, 0C000003Eh
0x14002e514  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002e51b  mov     eax, [rcx+2Ch]
0x14002e51e  test    al, 2
0x14002e520  jz      short loc_14002E52D
0x14002e522  cmp     byte ptr [rcx+29h], 2
0x14002e526  jb      short loc_14002E52D
0x14002e528  mov     r10b, 1
0x14002e52b  jmp     short loc_14002E530
0x14002e52d  xor     r10b, r10b
0x14002e530  mov     r9, [r14+10B0h]
0x14002e537  lea     rax, WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids
0x14002e53e  mov     rcx, [rcx+18h]
0x14002e542  mov     r8b, 1
0x14002e545  mov     [rsp+98h+var_48], edx
0x14002e549  mov     dl, r10b
0x14002e54c  mov     [rsp+98h+var_50], rbx
0x14002e551  mov     [rsp+98h+var_58], rdi
0x14002e556  mov     [rsp+98h+var_60], rax
0x14002e55b  mov     [rsp+98h+var_68], 21h ; '!'
0x14002e562  mov     [rsp+98h+var_70], 2
0x14002e56a  mov     [rsp+98h+var_78], 2
0x14002e56f  call    WPP_RECORDER_AND_TRACE_SF_qiD
0x14002e574  mov     r8d, [rbx+30h]; __annotation("Debug", "TelemetryAssert", "false", "Transport design does not allow for partial but successful transfer.")
0x14002e578  lea     r9, aTransportDesig; "Transport design does not allow for par"...
0x14002e57f  mov     edx, [rbx+20h]
0x14002e582  lea     rcx, aBthportSys; "bthport.sys"
0x14002e589  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x14002e58e  jmp     short loc_14002E60A
0x14002e590  cmp     edx, 4
0x14002e593  jbe     short loc_14002E59D
0x14002e595  lea     eax, [rdx-4]
0x14002e598  add     [rdi+20h], eax
0x14002e59b  jmp     short loc_14002E5B3
0x14002e59d  lea     r9, aEachSegmentIsE; __annotation("Debug", "TelemetryAssert", "false", "Each segment is expected to have the data packet header.")
0x14002e5a4  xor     r8d, r8d
0x14002e5a7  lea     rcx, aBthportSys; "bthport.sys"
0x14002e5ae  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x14002e5b3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002e5ba  mov     eax, [rcx+2Ch]
0x14002e5bd  test    al, 2
0x14002e5bf  jz      short loc_14002E5CB
0x14002e5c1  cmp     byte ptr [rcx+29h], 4
0x14002e5c5  jb      short loc_14002E5CB
0x14002e5c7  mov     dl, 1
0x14002e5c9  jmp     short loc_14002E5CD
0x14002e5cb  xor     dl, dl
0x14002e5cd  mov     r9, [r14+10B0h]
0x14002e5d4  lea     rax, WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids
0x14002e5db  mov     rcx, [rcx+18h]
0x14002e5df  mov     r8b, 1
0x14002e5e2  mov     [rsp+98h+var_50], rbx
0x14002e5e7  mov     [rsp+98h+var_58], rdi
0x14002e5ec  mov     [rsp+98h+var_60], rax
0x14002e5f1  mov     [rsp+98h+var_68], 22h ; '"'
0x14002e5f8  mov     [rsp+98h+var_70], 2
0x14002e600  mov     [rsp+98h+var_78], 4
0x14002e605  call    WPP_RECORDER_AND_TRACE_SF_qi
0x14002e60a  cmp     dword ptr [rdi+0Ch], 0
0x14002e60e  jl      short loc_14002E617
0x14002e610  test    esi, esi
0x14002e612  jns     short loc_14002E617
0x14002e614  mov     [rdi+0Ch], esi
0x14002e617  mov     rdx, [rbx+28h]; Entry
0x14002e61b  lea     rcx, [r14+0A00h]; Lookaside
0x14002e622  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002e629  nop     dword ptr [rax+rax+00h]
0x14002e62e  lea     rcx, [r15+48h]
0x14002e632  mov     qword ptr [rbx+28h], 0
0x14002e63a  lea     r9, aOnecoreDrivers_32; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14002e641  mov     r8d, 306h
0x14002e647  mov     rdx, r15
0x14002e64a  call    RefObj_ReleaseEx
0x14002e64f  mov     rcx, [rbx]
0x14002e652  mov     rdx, rbx; Entry
0x14002e655  add     rcx, 70h ; 'p'; Lookaside
0x14002e659  call    cs:__imp_ExFreeToLookasideListEx
0x14002e660  nop     dword ptr [rax+rax+00h]
0x14002e665  add     rsp, 68h
0x14002e669  pop     r15
0x14002e66b  pop     r14
0x14002e66d  pop     rdi
0x14002e66e  pop     rsi
0x14002e66f  pop     rbp
0x14002e670  pop     rbx
0x14002e671  retn
```
