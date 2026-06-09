# CEnumSyncChangeUnitWrappers::Remove(CSyncChangeUnitWrapper *)

- ea: `0x1800715e0`
- end: `0x1800716ef`
- name: `?Remove@CEnumSyncChangeUnitWrappers@@QEAAJPEAVCSyncChangeUnitWrapper@@@Z`
- size: `271`
- prototype: `__int64 __fastcall(CEnumSyncChangeUnitWrappers *__hidden this, struct CSyncChangeUnitWrapper *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180021918`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x180065ef8`
- `0x1800715e0`

## string_xrefs

- `0x180071612`: `CEnumSyncChangeUnitWrappers::Remove`
- `0x1800716c8`: `CEnumSyncChangeUnitWrappers::Remove`

## pseudocode

```c
__int64 __fastcall CEnumSyncChangeUnitWrappers::Remove(
        CEnumSyncChangeUnitWrappers *this,
        struct CSyncChangeUnitWrapper *a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rsi
  struct CSyncChangeUnitWrapper **v8; // rdx
  int v9; // eax
  __int64 i; // rdx
  unsigned int v11; // eax

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      54,
      WPP_3a5a3682dc74351209583b3dc1c94fc4_Traceguids,
      "CEnumSyncChangeUnitWrappers::Remove");
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = -2147467261;
  if ( a2 )
  {
    v6 = *((_QWORD *)this + 3);
    if ( v6 && *(struct CSyncChangeUnitWrapper **)v6 == a2 )
    {
      v6 = *(_QWORD *)(v6 + 8);
      *((_QWORD *)this + 3) = v6;
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (v7 = *((_QWORD *)this + 4), v5 = -2147217379, !v6)
      || a2 != *(struct CSyncChangeUnitWrapper **)v6
      && ((v8 = *(struct CSyncChangeUnitWrapper ***)(v6 + 16)) == 0 || *v8 != a2)
      || (v9 = CollectionManager<CSyncChangeUnitWrapper>::RemoveElement(v7),
          v4 = (PVOID *)WPP_GLOBAL_Control,
          v5 = v9,
          v9 < 0) )
    {
      for ( i = *(_QWORD *)(v7 + 16); i; i = *(_QWORD *)(i + 8) )
      {
        if ( a2 == *(struct CSyncChangeUnitWrapper **)i )
        {
          v11 = CollectionManager<CSyncChangeUnitWrapper>::RemoveElement(v7);
          v4 = (PVOID *)WPP_GLOBAL_Control;
          v5 = v11;
          break;
        }
      }
    }
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v4[2],
      55,
      (unsigned int)WPP_3a5a3682dc74351209583b3dc1c94fc4_Traceguids,
      (unsigned int)"CEnumSyncChangeUnitWrappers::Remove",
      v5);
  return v5;
}

```

## disassembly

```asm
0x1800715e0  push    rbx
0x1800715e2  push    rbp
0x1800715e3  push    rsi
0x1800715e4  push    rdi
0x1800715e5  sub     rsp, 38h
0x1800715e9  mov     rdi, rdx
0x1800715ec  mov     rsi, rcx
0x1800715ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800715f6  lea     rbp, WPP_GLOBAL_Control
0x1800715fd  cmp     rcx, rbp
0x180071600  jz      short loc_180071631
0x180071602  test    byte ptr [rcx+1Ch], 8
0x180071606  jz      short loc_180071631
0x180071608  cmp     byte ptr [rcx+19h], 5
0x18007160c  jb      short loc_180071631
0x18007160e  mov     rcx, [rcx+10h]
0x180071612  lea     r9, aCenumsyncchang_3; "CEnumSyncChangeUnitWrappers::Remove"
0x180071619  mov     edx, 36h ; '6'
0x18007161e  lea     r8, WPP_3a5a3682dc74351209583b3dc1c94fc4_Traceguids
0x180071625  call    WPP_SF_s
0x18007162a  mov     rcx, cs:WPP_GLOBAL_Control
0x180071631  mov     ebx, 80004003h
0x180071636  test    rdi, rdi
0x180071639  jz      short loc_1800716B3
0x18007163b  mov     rdx, [rsi+18h]
0x18007163f  test    rdx, rdx
0x180071642  jz      short loc_180071658
0x180071644  cmp     [rdx], rdi
0x180071647  jnz     short loc_180071658
0x180071649  mov     rdx, [rdx+8]
0x18007164d  mov     [rsi+18h], rdx
0x180071651  mov     rcx, cs:WPP_GLOBAL_Control
0x180071658  mov     rsi, [rsi+20h]
0x18007165c  mov     ebx, 8004101Dh
0x180071661  test    rdx, rdx
0x180071664  jz      short loc_18007168E
0x180071666  cmp     rdi, [rdx]
0x180071669  jz      short loc_180071679
0x18007166b  mov     rdx, [rdx+10h]
0x18007166f  test    rdx, rdx
0x180071672  jz      short loc_18007168E
0x180071674  cmp     [rdx], rdi
0x180071677  jnz     short loc_18007168E
0x180071679  mov     rcx, rsi
0x18007167c  call    ?RemoveElement@?$CollectionManager@VCSyncChangeUnitWrapper@@@@QEAAJPEAU?$CollectionElement@VCSyncChangeUnitWrapper@@@@@Z; CollectionManager<CSyncChangeUnitWrapper>::RemoveElement(CollectionElement<CSyncChangeUnitWrapper> *)
0x180071681  mov     rcx, cs:WPP_GLOBAL_Control
0x180071688  mov     ebx, eax
0x18007168a  test    eax, eax
0x18007168c  jns     short loc_1800716B3
0x18007168e  mov     rdx, [rsi+10h]
0x180071692  test    rdx, rdx
0x180071695  jz      short loc_1800716B3
0x180071697  cmp     rdi, [rdx]
0x18007169a  jz      short loc_1800716A2
0x18007169c  mov     rdx, [rdx+8]
0x1800716a0  jmp     short loc_180071692
0x1800716a2  mov     rcx, rsi
0x1800716a5  call    ?RemoveElement@?$CollectionManager@VCSyncChangeUnitWrapper@@@@QEAAJPEAU?$CollectionElement@VCSyncChangeUnitWrapper@@@@@Z; CollectionManager<CSyncChangeUnitWrapper>::RemoveElement(CollectionElement<CSyncChangeUnitWrapper> *)
0x1800716aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800716b1  mov     ebx, eax
0x1800716b3  cmp     rcx, rbp
0x1800716b6  jz      short loc_1800716E4
0x1800716b8  test    byte ptr [rcx+1Ch], 8
0x1800716bc  jz      short loc_1800716E4
0x1800716be  cmp     byte ptr [rcx+19h], 5
0x1800716c2  jb      short loc_1800716E4
0x1800716c4  mov     rcx, [rcx+10h]
0x1800716c8  lea     r9, aCenumsyncchang_3; "CEnumSyncChangeUnitWrappers::Remove"
0x1800716cf  mov     edx, 37h ; '7'
0x1800716d4  mov     [rsp+58h+var_38], ebx
0x1800716d8  lea     r8, WPP_3a5a3682dc74351209583b3dc1c94fc4_Traceguids
0x1800716df  call    WPP_SF_sD
0x1800716e4  mov     eax, ebx
0x1800716e6  add     rsp, 38h
0x1800716ea  pop     rdi
0x1800716eb  pop     rsi
0x1800716ec  pop     rbp
0x1800716ed  pop     rbx
0x1800716ee  retn
```
