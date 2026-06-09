# BthCleanupExtension(DEVICE_EXTENSION *)

- ea: `0x14001cc04`
- end: `0x14001cccb`
- name: `?BthCleanupExtension@@YAXPEAUDEVICE_EXTENSION@@@Z`
- size: `199`
- prototype: `void __fastcall(struct DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14001c5fc`

## callees

- `0x140005b4c`
- `0x14001cc04`

## import_xrefs

- `ntoskrnl!ExDeleteLookasideListEx` at `0x14001cc69`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14001cc69`
- `ntoskrnl!ZwClose` at `0x14001ccad`
- `ntoskrnl!ZwClose` at `0x14001ccad`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14001cc8a`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14001cc8a`

## pseudocode

```c
void __fastcall BthCleanupExtension(struct DEVICE_EXTENSION *a1)
{
  bool v2; // dl
  void *HContainerIdHashAlg; // rcx
  void *LinkKeysHandle; // rcx

  v2 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_q(
    WPP_GLOBAL_Control->AttachedDevice,
    v2,
    1,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    6,
    76,
    (__int64)WPP_70f807cd943530ae8ba584e42371a91c_Traceguids,
    a1);
  if ( a1->IsBipLookasideListInitialized )
  {
    ExDeleteLookasideListEx(&a1->BipLookasideList);
    a1->IsBipLookasideListInitialized = 0;
  }
  HContainerIdHashAlg = a1->HContainerIdHashAlg;
  if ( HContainerIdHashAlg )
  {
    BCryptCloseAlgorithmProvider(HContainerIdHashAlg, 0);
    a1->HContainerIdHashAlg = 0;
  }
  LinkKeysHandle = a1->LinkKeysHandle;
  if ( LinkKeysHandle )
  {
    ZwClose(LinkKeysHandle);
    a1->LinkKeysHandle = 0;
  }
}

```

## disassembly

```asm
0x14001cc04  push    rbx
0x14001cc06  sub     rsp, 50h
0x14001cc0a  mov     rbx, rcx
0x14001cc0d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001cc14  mov     eax, [rcx+2Ch]
0x14001cc17  test    al, 20h
0x14001cc19  jz      short loc_14001CC25
0x14001cc1b  cmp     byte ptr [rcx+29h], 4
0x14001cc1f  jb      short loc_14001CC25
0x14001cc21  mov     dl, 1
0x14001cc23  jmp     short loc_14001CC27
0x14001cc25  xor     dl, dl
0x14001cc27  mov     r9, [rcx+40h]
0x14001cc2b  lea     rax, WPP_70f807cd943530ae8ba584e42371a91c_Traceguids
0x14001cc32  mov     rcx, [rcx+18h]
0x14001cc36  mov     r8b, 1
0x14001cc39  mov     [rsp+58h+var_18], rbx
0x14001cc3e  mov     [rsp+58h+var_20], rax
0x14001cc43  mov     [rsp+58h+var_28], 4Ch ; 'L'
0x14001cc4a  mov     [rsp+58h+var_30], 6
0x14001cc52  mov     [rsp+58h+var_38], 4
0x14001cc57  call    WPP_RECORDER_AND_TRACE_SF_q
0x14001cc5c  cmp     byte ptr [rbx+0D0h], 0
0x14001cc63  jz      short loc_14001CC7C
0x14001cc65  lea     rcx, [rbx+70h]; Lookaside
0x14001cc69  call    cs:__imp_ExDeleteLookasideListEx
0x14001cc70  nop     dword ptr [rax+rax+00h]
0x14001cc75  mov     byte ptr [rbx+0D0h], 0
0x14001cc7c  mov     rcx, [rbx+1E0h]; hAlgorithm
0x14001cc83  test    rcx, rcx
0x14001cc86  jz      short loc_14001CCA1
0x14001cc88  xor     edx, edx; dwFlags
0x14001cc8a  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14001cc91  nop     dword ptr [rax+rax+00h]
0x14001cc96  mov     qword ptr [rbx+1E0h], 0
0x14001cca1  mov     rcx, [rbx+0D8h]; Handle
0x14001cca8  test    rcx, rcx
0x14001ccab  jz      short loc_14001CCC4
0x14001ccad  call    cs:__imp_ZwClose
0x14001ccb4  nop     dword ptr [rax+rax+00h]
0x14001ccb9  mov     qword ptr [rbx+0D8h], 0
0x14001ccc4  add     rsp, 50h
0x14001ccc8  pop     rbx
0x14001ccc9  retn
```
