# ScoServer_CleanupInfo(DEVICE_EXTENSION *)

- ea: `0x14014284c`
- end: `0x1401429c1`
- name: `?ScoServer_CleanupInfo@@YAXPEAUDEVICE_EXTENSION@@@Z`
- size: `373`
- prototype: `void __fastcall(struct DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14012e3e0`

## callees

- `0x140005b4c`
- `0x14014284c`
- `0x140143078`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x140142908`
- `ntoskrnl!RtlRbRemoveNode` at `0x140142908`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401428cc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140142932`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401428cc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140142932`
- `ntoskrnl!KeReleaseSpinLock` at `0x14014291a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140142946`
- `ntoskrnl!KeReleaseSpinLock` at `0x14014291a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140142946`

## pseudocode

```c
void __fastcall ScoServer_CleanupInfo(struct DEVICE_EXTENSION *a1)
{
  char v2; // bl
  char v3; // dl
  __int16 DeviceType; // ax
  KIRQL v5; // al
  _RTL_RB_TREE *p_ScoRbTree; // rdi
  KIRQL v7; // r15
  _RTL_BALANCED_NODE *Root; // rsi
  unsigned __int64 v9; // rcx
  __int16 v10; // ax

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
      40,
      (__int64)WPP_7c6dd03ac08a37dbf42aef9cb2166acd_Traceguids,
      a1);
  v5 = KeAcquireSpinLockRaiseToDpc(&a1->AllChildPdoLock);
  p_ScoRbTree = &a1->ScoRbTree;
  while ( 1 )
  {
    v7 = v5;
    if ( (*(_BYTE *)&a1->ScoRbTree.0 & 1) != 0 )
    {
      Root = p_ScoRbTree->Root;
      if ( !p_ScoRbTree->Root )
        break;
      v9 = (unsigned __int64)p_ScoRbTree ^ (unsigned __int64)Root;
    }
    else
    {
      v9 = (unsigned __int64)p_ScoRbTree->Root;
      Root = p_ScoRbTree->Root;
    }
    if ( !v9 )
      break;
    RtlRbRemoveNode(&a1->ScoRbTree, Root);
    KeReleaseSpinLock(&a1->AllChildPdoLock, v7);
    ScoServer_SynchFreeInfo(&Root[-5].16);
    v5 = KeAcquireSpinLockRaiseToDpc(&a1->AllChildPdoLock);
  }
  KeReleaseSpinLock(&a1->AllChildPdoLock, v5);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    v2 = 0;
  v10 = WPP_GLOBAL_Control->DeviceType;
  if ( v2 || v10 )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v2,
      v10 != 0,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      4,
      41,
      (__int64)WPP_7c6dd03ac08a37dbf42aef9cb2166acd_Traceguids,
      a1);
}

```

## disassembly

```asm
0x14014284c  push    rbx
0x14014284e  push    rbp
0x14014284f  push    rsi
0x140142850  push    rdi
0x140142851  push    r12
0x140142853  push    r14
0x140142855  push    r15
0x140142857  sub     rsp, 50h
0x14014285b  mov     rbp, rcx
0x14014285e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140142865  xor     r12d, r12d
0x140142868  mov     bl, 1
0x14014286a  mov     eax, [rcx+2Ch]
0x14014286d  test    al, 8
0x14014286f  jz      short loc_140142879
0x140142871  cmp     byte ptr [rcx+29h], 5
0x140142875  mov     dl, bl
0x140142877  jnb     short loc_14014287C
0x140142879  mov     dl, r12b
0x14014287c  movzx   eax, word ptr [rcx+48h]
0x140142880  lea     r9, WPP_7c6dd03ac08a37dbf42aef9cb2166acd_Traceguids
0x140142887  test    ax, ax
0x14014288a  setnz   r8b
0x14014288e  test    dl, dl
0x140142890  jnz     short loc_140142897
0x140142892  test    ax, ax
0x140142895  jz      short loc_1401428C2
0x140142897  mov     [rsp+88h+var_48], rbp
0x14014289c  mov     [rsp+88h+var_50], r9
0x1401428a1  mov     r9, [rcx+40h]
0x1401428a5  mov     rcx, [rcx+18h]
0x1401428a9  mov     [rsp+88h+var_58], 28h ; '('
0x1401428b0  mov     [rsp+88h+var_60], 4
0x1401428b8  mov     [rsp+88h+var_68], 5
0x1401428bd  call    WPP_RECORDER_AND_TRACE_SF_q
0x1401428c2  lea     r14, [rbp+110h]
0x1401428c9  mov     rcx, r14; SpinLock
0x1401428cc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1401428d3  nop     dword ptr [rax+rax+00h]
0x1401428d8  lea     rdi, [rbp+0F0h]
0x1401428df  mov     r15b, al
0x1401428e2  test    [rdi+8], bl
0x1401428e5  jz      short loc_1401428F7
0x1401428e7  mov     rsi, [rdi]
0x1401428ea  test    rsi, rsi
0x1401428ed  jz      short loc_140142940
0x1401428ef  mov     rcx, rsi
0x1401428f2  xor     rcx, rdi
0x1401428f5  jmp     short loc_1401428FD
0x1401428f7  mov     rcx, [rdi]
0x1401428fa  mov     rsi, rcx
0x1401428fd  test    rcx, rcx
0x140142900  jz      short loc_140142940
0x140142902  mov     rdx, rsi
0x140142905  mov     rcx, rdi
0x140142908  call    cs:__imp_RtlRbRemoveNode
0x14014290f  nop     dword ptr [rax+rax+00h]
0x140142914  mov     dl, r15b; NewIrql
0x140142917  mov     rcx, r14; SpinLock
0x14014291a  call    cs:__imp_KeReleaseSpinLock
0x140142921  nop     dword ptr [rax+rax+00h]
0x140142926  lea     rcx, [rsi-68h]; P
0x14014292a  call    ?ScoServer_SynchFreeInfo@@YAXPEAU_SCO_SERVER_INFO@@@Z; ScoServer_SynchFreeInfo(_SCO_SERVER_INFO *)
0x14014292f  mov     rcx, r14; SpinLock
0x140142932  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140142939  nop     dword ptr [rax+rax+00h]
0x14014293e  jmp     short loc_1401428DF
0x140142940  mov     dl, r15b; NewIrql
0x140142943  mov     rcx, r14; SpinLock
0x140142946  call    cs:__imp_KeReleaseSpinLock
0x14014294d  nop     dword ptr [rax+rax+00h]
0x140142952  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140142959  mov     eax, [rcx+2Ch]
0x14014295c  test    al, 8
0x14014295e  jz      short loc_140142966
0x140142960  cmp     byte ptr [rcx+29h], 5
0x140142964  jnb     short loc_140142969
0x140142966  mov     bl, r12b
0x140142969  movzx   eax, word ptr [rcx+48h]
0x14014296d  test    ax, ax
0x140142970  setnz   r8b
0x140142974  test    bl, bl
0x140142976  jnz     short loc_14014297D
0x140142978  test    ax, ax
0x14014297b  jz      short loc_1401429B1
0x14014297d  mov     r9, [rcx+40h]
0x140142981  lea     rdx, WPP_7c6dd03ac08a37dbf42aef9cb2166acd_Traceguids
0x140142988  mov     rcx, [rcx+18h]
0x14014298c  mov     [rsp+88h+var_48], rbp
0x140142991  mov     [rsp+88h+var_50], rdx
0x140142996  mov     dl, bl
0x140142998  mov     [rsp+88h+var_58], 29h ; ')'
0x14014299f  mov     [rsp+88h+var_60], 4
0x1401429a7  mov     [rsp+88h+var_68], 5
0x1401429ac  call    WPP_RECORDER_AND_TRACE_SF_q
0x1401429b1  add     rsp, 50h
0x1401429b5  pop     r15
0x1401429b7  pop     r14
0x1401429b9  pop     r12
0x1401429bb  pop     rdi
0x1401429bc  pop     rsi
0x1401429bd  pop     rbp
0x1401429be  pop     rbx
0x1401429bf  retn
```
