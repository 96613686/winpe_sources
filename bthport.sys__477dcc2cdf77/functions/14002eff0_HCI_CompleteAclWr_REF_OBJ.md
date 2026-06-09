# HCI_CompleteAclWr(_REF_OBJ *)

- ea: `0x14002eff0`
- end: `0x14002f158`
- name: `?HCI_CompleteAclWr@@YAXPEAU_REF_OBJ@@@Z`
- size: `360`
- prototype: `void __fastcall(struct _REF_OBJ *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140005608`
- `0x14000764c`
- `0x14002eff0`
- `0x140161d7c`
- `0x140165580`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002f0c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f0d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f0c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f0d8`

## string_xrefs

- `0x14002f082`: `onecore\drivers\wdm\bluetooth\drivers\bthport\src\hciaclwrite.cpp`
- `0x14002f09f`: `onecore\drivers\wdm\bluetooth\drivers\bthport\src\hciaclwrite.cpp`

## pseudocode

```c
void __fastcall HCI_CompleteAclWr(struct _REF_OBJ *a1)
{
  int v1; // r8d
  struct _REF_OBJ *v2; // rbx
  char v3; // di
  char v4; // dl
  __int16 DeviceType; // ax
  __int64 v6; // rcx
  __int64 v7; // rsi
  void *v8; // rcx
  void (__fastcall *v9)(__int64); // rax
  int v10; // edx
  int v11; // r8d
  __int16 v12; // ax

  v1 = (int)a1;
  v2 = a1 - 3;
  v3 = 1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || (v4 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    v4 = 0;
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  if ( v4 || DeviceType )
  {
    LOBYTE(v1) = DeviceType != 0;
    WPP_RECORDER_AND_TRACE_SF_qi(
      WPP_GLOBAL_Control->AttachedDevice,
      v4,
      v1,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      2,
      35,
      (__int64)WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids,
      *(_QWORD *)&v2->Count,
      a1);
  }
  v6 = *(_QWORD *)&v2[4].Count;
  v7 = *(_QWORD *)&v2->Count;
  if ( v6 )
  {
    RefObj_ReleaseEx(
      v6 + 8,
      HCI_QueueAclWrBip,
      792,
      "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hciaclwrite.cpp");
    RefObj_ReleaseEx(
      *(_QWORD *)&v2[4].Count + 8LL,
      HCI_WriteAclData,
      793,
      "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\hciaclwrite.cpp");
  }
  v8 = *(void **)&v2[1].Count;
  if ( v8 )
    ExFreePoolWithTag(v8, 0);
  ExFreePoolWithTag(v2, 0);
  v9 = *(void (__fastcall **)(__int64))(v7 + 104);
  *(_QWORD *)(v7 + 152) = 0;
  v9(v7);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    v3 = 0;
  v12 = WPP_GLOBAL_Control->DeviceType;
  if ( v3 || v12 )
  {
    LOBYTE(v10) = v3;
    LOBYTE(v11) = v12 != 0;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v10,
      v11,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      2,
      36,
      (__int64)WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids);
  }
}

```

## disassembly

```asm
0x14002eff0  push    rbx
0x14002eff2  push    rbp
0x14002eff3  push    rsi
0x14002eff4  push    rdi
0x14002eff5  push    r15
0x14002eff7  sub     rsp, 50h
0x14002effb  mov     r8, rcx
0x14002effe  lea     rbx, [rcx-48h]
0x14002f002  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f009  xor     ebp, ebp
0x14002f00b  mov     dil, 1
0x14002f00e  mov     eax, [rcx+2Ch]
0x14002f011  test    al, 2
0x14002f013  jz      short loc_14002F01E
0x14002f015  cmp     byte ptr [rcx+29h], 5
0x14002f019  mov     dl, dil
0x14002f01c  jnb     short loc_14002F021
0x14002f01e  mov     dl, bpl
0x14002f021  movzx   eax, word ptr [rcx+48h]
0x14002f025  lea     r15, WPP_26f9bb70120c32f961cc3ff802b9d219_Traceguids
0x14002f02c  test    ax, ax
0x14002f02f  setnz   r10b
0x14002f033  test    dl, dl
0x14002f035  jnz     short loc_14002F03C
0x14002f037  test    ax, ax
0x14002f03a  jz      short loc_14002F072
0x14002f03c  mov     rax, [rbx]
0x14002f03f  mov     r9, [rcx+40h]
0x14002f043  mov     rcx, [rcx+18h]
0x14002f047  mov     [rsp+78h+var_30], r8
0x14002f04c  mov     r8b, r10b
0x14002f04f  mov     [rsp+78h+var_38], rax
0x14002f054  mov     [rsp+78h+var_40], r15
0x14002f059  mov     [rsp+78h+var_48], 23h ; '#'
0x14002f060  mov     [rsp+78h+var_50], 2
0x14002f068  mov     [rsp+78h+var_58], 5
0x14002f06d  call    WPP_RECORDER_AND_TRACE_SF_qi
0x14002f072  mov     rcx, [rbx+60h]
0x14002f076  mov     rsi, [rbx]
0x14002f079  test    rcx, rcx
0x14002f07c  jz      short loc_14002F0BC
0x14002f07e  add     rcx, 8
0x14002f082  lea     r9, aOnecoreDrivers_32; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14002f089  mov     r8d, 318h
0x14002f08f  lea     rdx, ?HCI_QueueAclWrBip@@YAJPEAUHCI_INTERFACE@@PEAU_HCI_CONNECTION@@PEAU_BIP@@@Z; HCI_QueueAclWrBip(HCI_INTERFACE *,_HCI_CONNECTION *,_BIP *)
0x14002f096  call    RefObj_ReleaseEx
0x14002f09b  mov     rcx, [rbx+60h]
0x14002f09f  lea     r9, aOnecoreDrivers_32; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14002f0a6  add     rcx, 8
0x14002f0aa  lea     rdx, ?HCI_WriteAclData@@YAJPEAUHCI_INTERFACE@@PEAU_BIP@@PEAU_HCI_CONNECTION_INFO@@@Z; HCI_WriteAclData(HCI_INTERFACE *,_BIP *,_HCI_CONNECTION_INFO *)
0x14002f0b1  mov     r8d, 319h
0x14002f0b7  call    RefObj_ReleaseEx
0x14002f0bc  mov     rcx, [rbx+18h]; P
0x14002f0c0  test    rcx, rcx
0x14002f0c3  jz      short loc_14002F0D3
0x14002f0c5  xor     edx, edx; Tag
0x14002f0c7  call    cs:__imp_ExFreePoolWithTag
0x14002f0ce  nop     dword ptr [rax+rax+00h]
0x14002f0d3  xor     edx, edx; Tag
0x14002f0d5  mov     rcx, rbx; P
0x14002f0d8  call    cs:__imp_ExFreePoolWithTag
0x14002f0df  nop     dword ptr [rax+rax+00h]
0x14002f0e4  mov     rax, [rsi+68h]
0x14002f0e8  mov     rcx, rsi
0x14002f0eb  mov     [rsi+98h], rbp
0x14002f0f2  call    _guard_dispatch_icall
0x14002f0f7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f0fe  mov     eax, [rcx+2Ch]
0x14002f101  test    al, 2
0x14002f103  jz      short loc_14002F10B
0x14002f105  cmp     byte ptr [rcx+29h], 5
0x14002f109  jnb     short loc_14002F10E
0x14002f10b  mov     dil, bpl
0x14002f10e  movzx   eax, word ptr [rcx+48h]
0x14002f112  test    ax, ax
0x14002f115  setnz   r8b
0x14002f119  test    dil, dil
0x14002f11c  jnz     short loc_14002F123
0x14002f11e  test    ax, ax
0x14002f121  jz      short loc_14002F14C
0x14002f123  mov     r9, [rcx+40h]
0x14002f127  mov     dl, dil
0x14002f12a  mov     rcx, [rcx+18h]
0x14002f12e  mov     [rsp+78h+var_40], r15
0x14002f133  mov     [rsp+78h+var_48], 24h ; '$'
0x14002f13a  mov     [rsp+78h+var_50], 2
0x14002f142  mov     [rsp+78h+var_58], 5
0x14002f147  call    WPP_RECORDER_AND_TRACE_SF_
0x14002f14c  add     rsp, 50h
0x14002f150  pop     r15
0x14002f152  pop     rdi
0x14002f153  pop     rsi
0x14002f154  pop     rbp
0x14002f155  pop     rbx
0x14002f156  retn
```
