# DbTableAccess<SharingTargetTableAdapter>::Insert(SharingTargetTableAdapter *)

- ea: `0x180017ae0`
- end: `0x180017b55`
- name: `?Insert@?$DbTableAccess@VSharingTargetTableAdapter@@@@QEAAJPEAVSharingTargetTableAdapter@@@Z`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800163ec`
- `0x180017c90`

## callees

- `0x18000be3c`
- `0x180014eb0`
- `0x180015bf8`
- `0x180017ae0`

## pseudocode

```c
__int64 __fastcall DbTableAccess<SharingTargetTableAdapter>::Insert(__int64 a1, __int64 a2)
{
  int v3; // ebx
  PVOID P[3]; // [rsp+20h] [rbp-18h] BYREF
  int v6; // [rsp+50h] [rbp+18h] BYREF
  unsigned int v7; // [rsp+58h] [rbp+20h] BYREF

  P[0] = 0;
  v7 = 0;
  v6 = 0;
  v3 = DbTableDescription<SharingTargetTableAdapter>::Serialize(a2, P, &v7, &v6);
  if ( v3 >= 0 )
    v3 = DbTable::Insert(*(DbTable **)(a1 + 8), (struct JET_SETCOLUMN *)P[0], v7, v6);
  Common::GlobalHeap::Free(P[0]);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180017ae0  mov     r11, rsp
0x180017ae3  mov     [r11+8], rbx
0x180017ae7  push    rdi
0x180017ae8  sub     rsp, 30h
0x180017aec  mov     rax, rdx
0x180017aef  mov     qword ptr [r11-18h], 0
0x180017af7  mov     rdi, rcx
0x180017afa  mov     [rsp+38h+arg_18], 0
0x180017b02  mov     rcx, rax
0x180017b05  mov     [rsp+38h+arg_10], 0
0x180017b0d  lea     r9, [r11+18h]
0x180017b11  lea     r8, [r11+20h]
0x180017b15  lea     rdx, [r11-18h]
0x180017b19  call    ?Serialize@?$DbTableDescription@VSharingTargetTableAdapter@@@@SAJPEAVSharingTargetTableAdapter@@PEAPEAUJET_SETCOLUMN@@AEAKAEAH@Z; DbTableDescription<SharingTargetTableAdapter>::Serialize(SharingTargetTableAdapter *,JET_SETCOLUMN * *,ulong &,int &)
0x180017b1e  mov     ebx, eax
0x180017b20  test    eax, eax
0x180017b22  js      short loc_180017B3E
0x180017b24  mov     r9d, [rsp+38h+arg_10]; int
0x180017b29  mov     r8d, [rsp+38h+arg_18]; unsigned int
0x180017b2e  mov     rdx, [rsp+38h+P]; struct JET_SETCOLUMN *
0x180017b33  mov     rcx, [rdi+8]; this
0x180017b37  call    ?Insert@DbTable@@QEAAJPEAUJET_SETCOLUMN@@KH@Z; DbTable::Insert(JET_SETCOLUMN *,ulong,int)
0x180017b3c  mov     ebx, eax
0x180017b3e  mov     rcx, [rsp+38h+P]; P
0x180017b43  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180017b48  mov     eax, ebx
0x180017b4a  mov     rbx, [rsp+38h+arg_0]
0x180017b4f  add     rsp, 30h
0x180017b53  pop     rdi
0x180017b54  retn
```
