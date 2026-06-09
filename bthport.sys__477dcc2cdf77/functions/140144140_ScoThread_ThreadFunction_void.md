# ScoThread_ThreadFunction(void *)

- ea: `0x140144140`
- end: `0x14014449d`
- name: `?ScoThread_ThreadFunction@@YAXPEAX@Z`
- size: `861`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140005608`
- `0x140005690`
- `0x140005b4c`
- `0x140141b6c`
- `0x140144140`
- `0x140144bf0`
- `0x140165540`
- `0x140165940`

## import_xrefs

- `ntoskrnl!KeWaitForMultipleObjects` at `0x140144272`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140144272`
- `ntoskrnl!PsTerminateSystemThread` at `0x140144419`
- `ntoskrnl!PsTerminateSystemThread` at `0x140144419`
- `ntoskrnl!KeSetPriorityThread` at `0x1401441ea`
- `ntoskrnl!KeSetPriorityThread` at `0x1401441ea`
- `ntoskrnl!KeClearEvent` at `0x1401442f1`
- `ntoskrnl!KeClearEvent` at `0x14014439a`
- `ntoskrnl!KeClearEvent` at `0x1401442f1`
- `ntoskrnl!KeClearEvent` at `0x14014439a`
- `ntoskrnl!KeSetEvent` at `0x14014423f`
- `ntoskrnl!KeSetEvent` at `0x14014423f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140144314`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140144314`
- `ntoskrnl!KeReleaseSpinLock` at `0x140144374`
- `ntoskrnl!KeReleaseSpinLock` at `0x140144374`

## pseudocode

```c
void __fastcall ScoThread_ThreadFunction(char *StartContext)
{
  char v2; // bl
  char v3; // dl
  __int16 DeviceType; // ax
  __int64 i; // rdx
  NTSTATUS v6; // eax
  int v7; // r8d
  NTSTATUS v8; // edx
  int v9; // edx
  KIRQL v10; // r8
  _LIST_ENTRY **v11; // rdx
  _LIST_ENTRY *v12; // rcx
  _LIST_ENTRY *Flink; // rax
  _LIST_ENTRY *Blink; // rax
  enum _BTH_SCO_CTRL_CODE v15; // r8d
  unsigned int v16; // r9d
  int v17; // edx
  int v18; // r8d
  __int16 v19; // ax
  struct _LIST_ENTRY v20; // [rsp+50h] [rbp-B0h] BYREF
  PVOID Object[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v22; // [rsp+70h] [rbp-90h]
  struct _KWAIT_BLOCK WaitBlockArray[3]; // [rsp+80h] [rbp-80h] BYREF

  *(_OWORD *)Object = 0;
  v22 = 0;
  v2 = 1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || (v3 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    v3 = 0;
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  if ( v3 || DeviceType )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v3,
      DeviceType != 0,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      4,
      21,
      (__int64)WPP_156ad3417adc34dfbe002b9340b9b992_Traceguids,
      (char)StartContext);
  KeSetPriorityThread(KeGetCurrentThread(), *((_DWORD *)StartContext + 8));
  memset(WaitBlockArray, 0, sizeof(WaitBlockArray));
  *(_OWORD *)Object = 0;
  v22 = 0;
  for ( i = 0; i != 3; ++i )
    Object[i] = &StartContext[16 * i + 80 + 8 * i];
  StartContext[48] = 1;
  KeSetEvent((PRKEVENT)(StartContext + 56), 0, 0);
  while ( 1 )
  {
    v6 = KeWaitForMultipleObjects(3u, Object, WaitAny, Executive, 0, 0, 0, WaitBlockArray);
    v8 = v6;
    if ( !v6 )
      break;
    v9 = v6 - 1;
    if ( v6 == 1 )
    {
      KeClearEvent((PRKEVENT)(StartContext + 104));
      ScoMp_ControlScoCxn(
        *((struct _SCO_INTERFACE **)StartContext - 94),
        (struct _SCO_CONNECTION *)(StartContext - 784),
        v15,
        v16);
    }
    else if ( v6 == 2 )
    {
      v20 = 0;
      KeClearEvent((PRKEVENT)(StartContext + 128));
      v20.Blink = &v20;
      v20.Flink = &v20;
      v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)StartContext);
      v11 = (_LIST_ENTRY **)(StartContext + 16);
      while ( 1 )
      {
        v12 = *v11;
        if ( *v11 == (_LIST_ENTRY *)v11 )
          break;
        if ( (_LIST_ENTRY **)v12->Blink != v11
          || (Flink = v12->Flink, v12->Flink->Blink != v12)
          || (*v11 = Flink, Flink->Blink = (_LIST_ENTRY *)v11, Blink = v20.Blink, v20.Blink->Flink != &v20) )
        {
          __fastfail(3u);
        }
        v12->Blink = v20.Blink;
        v12->Flink = &v20;
        Blink->Flink = v12;
        v20.Blink = v12;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)StartContext, v10);
      ScoCxn_CompleteTransferRequests((struct _SCO_CONNECTION *)(StartContext - 784), &v20);
    }
    else
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || (LOBYTE(v9) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        LOBYTE(v9) = 0;
      LOBYTE(v7) = 1;
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        v7,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        4,
        23,
        (__int64)WPP_156ad3417adc34dfbe002b9340b9b992_Traceguids,
        v6);
    }
  }
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || (LOBYTE(v8) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
    LOBYTE(v8) = 0;
  LOBYTE(v7) = 1;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    v8,
    v7,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    4,
    22,
    (__int64)WPP_156ad3417adc34dfbe002b9340b9b992_Traceguids);
  ScoCxn_CompleteTransferRequests(
    (struct _SCO_CONNECTION *)(StartContext - 784),
    (struct _LIST_ENTRY *)StartContext + 1);
  PsTerminateSystemThread(0);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    v2 = 0;
  v19 = WPP_GLOBAL_Control->DeviceType;
  if ( v2 || v19 )
  {
    LOBYTE(v17) = v2;
    LOBYTE(v18) = v19 != 0;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v17,
      v18,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      4,
      24,
      (__int64)WPP_156ad3417adc34dfbe002b9340b9b992_Traceguids);
  }
}

```

## disassembly

```asm
0x140144140  mov     [rsp-8+arg_8], rbx
0x140144145  mov     [rsp-8+arg_10], rsi
0x14014414a  push    rbp
0x14014414b  push    rdi
0x14014414c  push    r13
0x14014414e  lea     rbp, [rsp-20h]
0x140144153  sub     rsp, 120h
0x14014415a  mov     rax, cs:__security_cookie
0x140144161  xor     rax, rsp
0x140144164  mov     [rbp+30h+var_20], rax
0x140144168  xorps   xmm0, xmm0
0x14014416b  xor     eax, eax
0x14014416d  movups  xmmword ptr [rsp+130h+Object], xmm0
0x140144172  mov     [rsp+130h+var_C0], rax
0x140144177  mov     rdi, rcx
0x14014417a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140144181  xor     esi, esi
0x140144183  mov     eax, [rcx+2Ch]
0x140144186  lea     ebx, [rsi+1]
0x140144189  test    al, 8
0x14014418b  jz      short loc_140144195
0x14014418d  cmp     byte ptr [rcx+29h], 5
0x140144191  mov     dl, bl
0x140144193  jnb     short loc_140144198
0x140144195  mov     dl, sil
0x140144198  movzx   eax, word ptr [rcx+48h]
0x14014419c  lea     r13, WPP_156ad3417adc34dfbe002b9340b9b992_Traceguids
0x1401441a3  test    ax, ax
0x1401441a6  setnz   r8b
0x1401441aa  test    dl, dl
0x1401441ac  jnz     short loc_1401441B3
0x1401441ae  test    ax, ax
0x1401441b1  jz      short loc_1401441DE
0x1401441b3  mov     r9, [rcx+40h]
0x1401441b7  mov     rcx, [rcx+18h]
0x1401441bb  mov     [rsp+130h+var_F0], rdi
0x1401441c0  mov     [rsp+130h+WaitBlockArray], r13
0x1401441c5  mov     word ptr [rsp+130h+Timeout], 15h
0x1401441cc  mov     dword ptr [rsp+130h+Alertable], 4
0x1401441d4  mov     [rsp+130h+WaitMode], 5
0x1401441d9  call    WPP_RECORDER_AND_TRACE_SF_q
0x1401441de  mov     rcx, gs:188h; Thread
0x1401441e7  mov     edx, [rdi+20h]; Priority
0x1401441ea  call    cs:__imp_KeSetPriorityThread
0x1401441f1  nop     dword ptr [rax+rax+00h]
0x1401441f6  xor     edx, edx; Val
0x1401441f8  lea     rcx, [rbp+30h+var_B0]; void *
0x1401441fc  mov     r8d, 90h; Size
0x140144202  call    memset
0x140144207  xorps   xmm0, xmm0
0x14014420a  xor     eax, eax
0x14014420c  movups  xmmword ptr [rsp+130h+Object], xmm0
0x140144211  mov     [rsp+130h+var_C0], rax
0x140144216  mov     rdx, rsi
0x140144219  lea     rcx, [rdx+5]
0x14014421d  lea     rcx, [rdx+rcx*2]
0x140144221  lea     rcx, [rdi+rcx*8]
0x140144225  mov     [rsp+rdx*8+130h+Object], rcx
0x14014422a  add     rdx, rbx
0x14014422d  cmp     rdx, 3
0x140144231  jnz     short loc_140144219
0x140144233  lea     rcx, [rdi+38h]; Event
0x140144237  mov     [rdi+30h], bl
0x14014423a  xor     r8d, r8d; Wait
0x14014423d  xor     edx, edx; Increment
0x14014423f  call    cs:__imp_KeSetEvent
0x140144246  nop     dword ptr [rax+rax+00h]
0x14014424b  xor     r9d, r9d; WaitReason
0x14014424e  lea     rax, [rbp+30h+var_B0]
0x140144252  mov     [rsp+130h+WaitBlockArray], rax; WaitBlockArray
0x140144257  lea     rdx, [rsp+130h+Object]; Object
0x14014425c  mov     [rsp+130h+Timeout], rsi; Timeout
0x140144261  mov     r8d, ebx; WaitType
0x140144264  mov     [rsp+130h+Alertable], sil; Alertable
0x140144269  lea     ecx, [r9+3]; Count
0x14014426d  mov     [rsp+130h+WaitMode], sil; WaitMode
0x140144272  call    cs:__imp_KeWaitForMultipleObjects
0x140144279  nop     dword ptr [rax+rax+00h]
0x14014427e  mov     edx, eax
0x140144280  test    eax, eax
0x140144282  jz      loc_1401443C5
0x140144288  sub     edx, ebx
0x14014428a  jz      loc_140144396
0x140144290  cmp     edx, ebx
0x140144292  jz      short loc_1401442E2
0x140144294  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14014429b  mov     ecx, [r10+2Ch]
0x14014429f  test    cl, 8
0x1401442a2  jz      short loc_1401442AD
0x1401442a4  cmp     byte ptr [r10+29h], 2
0x1401442a9  mov     dl, bl
0x1401442ab  jnb     short loc_1401442B0
0x1401442ad  mov     dl, sil
0x1401442b0  mov     r9, [r10+40h]
0x1401442b4  mov     r8b, bl
0x1401442b7  mov     rcx, [r10+18h]
0x1401442bb  mov     dword ptr [rsp+130h+var_F0], eax
0x1401442bf  mov     [rsp+130h+WaitBlockArray], r13
0x1401442c4  mov     word ptr [rsp+130h+Timeout], 17h
0x1401442cb  mov     dword ptr [rsp+130h+Alertable], 4
0x1401442d3  mov     [rsp+130h+WaitMode], 2
0x1401442d8  call    WPP_RECORDER_AND_TRACE_SF_d
0x1401442dd  jmp     loc_14014424B
0x1401442e2  xorps   xmm0, xmm0
0x1401442e5  lea     rcx, [rdi+80h]; Event
0x1401442ec  movups  xmmword ptr [rsp+130h+var_E0.Flink], xmm0
0x1401442f1  call    cs:__imp_KeClearEvent
0x1401442f8  nop     dword ptr [rax+rax+00h]
0x1401442fd  lea     rax, [rsp+130h+var_E0]
0x140144302  mov     rcx, rdi; SpinLock
0x140144305  mov     [rsp+130h+var_E0.Blink], rax
0x14014430a  lea     rax, [rsp+130h+var_E0]
0x14014430f  mov     [rsp+130h+var_E0.Flink], rax
0x140144314  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14014431b  nop     dword ptr [rax+rax+00h]
0x140144320  mov     r8b, al
0x140144323  lea     rdx, [rdi+10h]
0x140144327  mov     rcx, [rdx]
0x14014432a  cmp     rcx, rdx
0x14014432d  jz      short loc_14014436E
0x14014432f  cmp     [rcx+8], rdx
0x140144333  jnz     loc_1401443BE
0x140144339  mov     rax, [rcx]
0x14014433c  cmp     [rax+8], rcx
0x140144340  jnz     short loc_1401443BE
0x140144342  mov     [rdx], rax
0x140144345  lea     r9, [rsp+130h+var_E0]
0x14014434a  mov     [rax+8], rdx
0x14014434e  mov     rax, [rsp+130h+var_E0.Blink]
0x140144353  cmp     [rax], r9
0x140144356  jnz     short loc_1401443BE
0x140144358  mov     [rcx+8], rax
0x14014435c  lea     r9, [rsp+130h+var_E0]
0x140144361  mov     [rcx], r9
0x140144364  mov     [rax], rcx
0x140144367  mov     [rsp+130h+var_E0.Blink], rcx
0x14014436c  jmp     short loc_140144327
0x14014436e  mov     dl, r8b; NewIrql
0x140144371  mov     rcx, rdi; SpinLock
0x140144374  call    cs:__imp_KeReleaseSpinLock
0x14014437b  nop     dword ptr [rax+rax+00h]
0x140144380  lea     rcx, [rdi-310h]; struct _SCO_CONNECTION *
0x140144387  lea     rdx, [rsp+130h+var_E0]; struct _LIST_ENTRY *
0x14014438c  call    ?ScoCxn_CompleteTransferRequests@@YAXPEAU_SCO_CONNECTION@@PEAU_LIST_ENTRY@@@Z; ScoCxn_CompleteTransferRequests(_SCO_CONNECTION *,_LIST_ENTRY *)
0x140144391  jmp     loc_14014424B
0x140144396  lea     rcx, [rdi+68h]; Event
0x14014439a  call    cs:__imp_KeClearEvent
0x1401443a1  nop     dword ptr [rax+rax+00h]
0x1401443a6  mov     rcx, [rdi-2F0h]; struct _SCO_INTERFACE *
0x1401443ad  lea     rdx, [rdi-310h]; struct _SCO_CONNECTION *
0x1401443b4  call    ?ScoMp_ControlScoCxn@@YAJPEAU_SCO_INTERFACE@@PEAU_SCO_CONNECTION@@W4_BTH_SCO_CTRL_CODE@@K@Z; ScoMp_ControlScoCxn(_SCO_INTERFACE *,_SCO_CONNECTION *,_BTH_SCO_CTRL_CODE,ulong)
0x1401443b9  jmp     loc_14014424B
0x1401443be  mov     ecx, 3
0x1401443c3  int     29h; Win8: RtlFailFast(ecx)
0x1401443c5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401443cc  mov     eax, [rcx+2Ch]
0x1401443cf  test    al, 8
0x1401443d1  jz      short loc_1401443DB
0x1401443d3  cmp     byte ptr [rcx+29h], 4
0x1401443d7  mov     dl, bl
0x1401443d9  jnb     short loc_1401443DE
0x1401443db  mov     dl, sil
0x1401443de  mov     r9, [rcx+40h]
0x1401443e2  mov     r8b, bl
0x1401443e5  mov     rcx, [rcx+18h]
0x1401443e9  mov     [rsp+130h+WaitBlockArray], r13
0x1401443ee  mov     word ptr [rsp+130h+Timeout], 16h
0x1401443f5  mov     dword ptr [rsp+130h+Alertable], 4
0x1401443fd  mov     [rsp+130h+WaitMode], 4
0x140144402  call    WPP_RECORDER_AND_TRACE_SF_
0x140144407  lea     rdx, [rdi+10h]; struct _LIST_ENTRY *
0x14014440b  lea     rcx, [rdi-310h]; struct _SCO_CONNECTION *
0x140144412  call    ?ScoCxn_CompleteTransferRequests@@YAXPEAU_SCO_CONNECTION@@PEAU_LIST_ENTRY@@@Z; ScoCxn_CompleteTransferRequests(_SCO_CONNECTION *,_LIST_ENTRY *)
0x140144417  xor     ecx, ecx; ExitStatus
0x140144419  call    cs:__imp_PsTerminateSystemThread
0x140144420  nop     dword ptr [rax+rax+00h]
0x140144425  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14014442c  mov     eax, [rcx+2Ch]
0x14014442f  test    al, 8
0x140144431  jz      short loc_140144439
0x140144433  cmp     byte ptr [rcx+29h], 5
0x140144437  jnb     short loc_14014443C
0x140144439  mov     bl, sil
0x14014443c  movzx   eax, word ptr [rcx+48h]
0x140144440  test    ax, ax
0x140144443  setnz   r8b
0x140144447  test    bl, bl
0x140144449  jnz     short loc_140144450
0x14014444b  test    ax, ax
0x14014444e  jz      short loc_140144478
0x140144450  mov     r9, [rcx+40h]
0x140144454  mov     dl, bl
0x140144456  mov     rcx, [rcx+18h]
0x14014445a  mov     [rsp+130h+WaitBlockArray], r13
0x14014445f  mov     word ptr [rsp+130h+Timeout], 18h
0x140144466  mov     dword ptr [rsp+130h+Alertable], 4
0x14014446e  mov     [rsp+130h+WaitMode], 5
0x140144473  call    WPP_RECORDER_AND_TRACE_SF_
0x140144478  mov     rcx, [rbp+30h+var_20]
0x14014447c  xor     rcx, rsp; StackCookie
0x14014447f  call    __security_check_cookie
0x140144484  lea     r11, [rsp+130h+var_10]
0x14014448c  mov     rbx, [r11+28h]
0x140144490  mov     rsi, [r11+30h]
0x140144494  mov     rsp, r11
0x140144497  pop     r13
0x140144499  pop     rdi
0x14014449a  pop     rbp
0x14014449b  retn
```
