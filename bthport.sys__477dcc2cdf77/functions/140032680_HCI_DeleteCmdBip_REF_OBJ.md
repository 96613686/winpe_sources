# HCI_DeleteCmdBip(_REF_OBJ *)

- ea: `0x140032680`
- end: `0x14003274c`
- name: `?HCI_DeleteCmdBip@@YAXPEAU_REF_OBJ@@@Z`
- size: `204`
- prototype: `void __fastcall(struct _REF_OBJ *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140005b4c`
- `0x140032680`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x140032701`
- `ntoskrnl!IoFreeWorkItem` at `0x140032701`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003272f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003272f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032719`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032719`

## pseudocode

```c
void __fastcall HCI_DeleteCmdBip(struct _REF_OBJ *a1)
{
  PIO_WORKITEM *p_DebugInfo; // rbx
  struct _REF_OBJ_DEBUG_INFO *DebugInfo; // rdi
  char v3; // dl
  __int16 DeviceType; // ax

  p_DebugInfo = &a1[-9].DebugInfo;
  DebugInfo = a1[-9].DebugInfo;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (v3 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    v3 = 0;
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  if ( v3 || DeviceType )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v3,
      DeviceType != 0,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      2,
      10,
      (__int64)WPP_871f840aa82a303a522ab977de612843_Traceguids,
      DebugInfo);
  IoFreeWorkItem(p_DebugInfo[17]);
  p_DebugInfo[17] = 0;
  ExFreePoolWithTag(p_DebugInfo, 0);
  ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(*(_QWORD *)DebugInfo + 112LL), DebugInfo);
}

```

## disassembly

```asm
0x140032680  mov     [rsp+arg_0], rbx
0x140032685  mov     [rsp+arg_8], rsi
0x14003268a  push    rdi
0x14003268b  sub     rsp, 50h
0x14003268f  lea     rbx, [rcx-0C8h]
0x140032696  mov     rdi, [rbx]
0x140032699  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400326a0  xor     esi, esi
0x1400326a2  mov     eax, [rcx+2Ch]
0x1400326a5  test    al, 2
0x1400326a7  jz      short loc_1400326B1
0x1400326a9  cmp     byte ptr [rcx+29h], 5
0x1400326ad  mov     dl, 1
0x1400326af  jnb     short loc_1400326B4
0x1400326b1  mov     dl, sil
0x1400326b4  movzx   eax, word ptr [rcx+48h]
0x1400326b8  test    ax, ax
0x1400326bb  setnz   r8b
0x1400326bf  test    dl, dl
0x1400326c1  jnz     short loc_1400326C8
0x1400326c3  test    ax, ax
0x1400326c6  jz      short loc_1400326FA
0x1400326c8  mov     r9, [rcx+40h]
0x1400326cc  lea     rax, WPP_871f840aa82a303a522ab977de612843_Traceguids
0x1400326d3  mov     rcx, [rcx+18h]
0x1400326d7  mov     [rsp+58h+var_18], rdi
0x1400326dc  mov     [rsp+58h+var_20], rax
0x1400326e1  mov     [rsp+58h+var_28], 0Ah
0x1400326e8  mov     [rsp+58h+var_30], 2
0x1400326f0  mov     [rsp+58h+var_38], 5
0x1400326f5  call    WPP_RECORDER_AND_TRACE_SF_q
0x1400326fa  mov     rcx, [rbx+88h]; IoWorkItem
0x140032701  call    cs:__imp_IoFreeWorkItem
0x140032708  nop     dword ptr [rax+rax+00h]
0x14003270d  xor     edx, edx; Tag
0x14003270f  mov     [rbx+88h], rsi
0x140032716  mov     rcx, rbx; P
0x140032719  call    cs:__imp_ExFreePoolWithTag
0x140032720  nop     dword ptr [rax+rax+00h]
0x140032725  mov     rcx, [rdi]
0x140032728  mov     rdx, rdi; Entry
0x14003272b  add     rcx, 70h ; 'p'; Lookaside
0x14003272f  call    cs:__imp_ExFreeToLookasideListEx
0x140032736  nop     dword ptr [rax+rax+00h]
0x14003273b  mov     rbx, [rsp+58h+arg_0]
0x140032740  mov     rsi, [rsp+58h+arg_8]
0x140032745  add     rsp, 50h
0x140032749  pop     rdi
0x14003274a  retn
```
