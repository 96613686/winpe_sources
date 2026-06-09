# DbTableAccess<SharingToken>::Update(SharingToken *,SharingToken *)

- ea: `0x180017ba8`
- end: `0x180017c8a`
- name: `?Update@?$DbTableAccess@VSharingToken@@@@QEAAJPEAVSharingToken@@0@Z`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180017c90`

## callees

- `0x18000be3c`
- `0x180015468`
- `0x18001577c`
- `0x180015934`
- `0x180015998`
- `0x180017ba8`

## pseudocode

```c
__int64 __fastcall DbTableAccess<SharingToken>::Update(__int64 a1, __int64 a2, __int64 a3)
{
  int SCBasedOnPK; // ebx
  __int64 v7; // rcx
  int v8; // eax
  PVOID v9; // rdi
  unsigned int csetcolumn; // [rsp+40h] [rbp-20h] BYREF
  unsigned int v12; // [rsp+44h] [rbp-1Ch] BYREF
  PVOID P; // [rsp+48h] [rbp-18h] BYREF
  struct _jetSeekCriteria *v14[2]; // [rsp+50h] [rbp-10h] BYREF
  int v15; // [rsp+98h] [rbp+38h] BYREF

  P = 0;
  v14[0] = 0;
  csetcolumn = 0;
  v12 = 0;
  v15 = 0;
  SCBasedOnPK = DbTableDescription<SharingToken>::GetSCBasedOnPK(a2, v14, &v12);
  if ( SCBasedOnPK >= 0 )
  {
    v7 = a3;
    if ( a2 == a3 )
      v7 = a2;
    v8 = DbTableDescription<SharingToken>::Serialize(v7, &P, &csetcolumn, &v15);
    v9 = P;
    SCBasedOnPK = v8;
    if ( v8 >= 0 )
      SCBasedOnPK = DbTable::Update(*(JET_SESID **)(a1 + 8), v14[0], v12, (struct JET_SETCOLUMN *)P, csetcolumn, v15, 0);
    if ( v9 )
      Common::GlobalHeap::Free(v9);
  }
  if ( v14[0] )
    DbTableDescription<SharingToken>::ReleaseSC(v14, v12);
  return (unsigned int)SCBasedOnPK;
}

```

## disassembly

```asm
0x180017ba8  mov     [rsp-18h+arg_0], rbx
0x180017bad  mov     [rsp-18h+arg_8], rsi
0x180017bb2  push    rbp
0x180017bb3  push    rdi
0x180017bb4  push    r15
0x180017bb6  mov     rbp, rsp
0x180017bb9  sub     rsp, 60h
0x180017bbd  mov     rdi, rdx
0x180017bc0  mov     [rbp+P], 0
0x180017bc8  mov     rsi, r8
0x180017bcb  mov     [rbp+var_10], 0
0x180017bd3  mov     r15, rcx
0x180017bd6  mov     [rbp+var_20], 0
0x180017bdd  mov     rcx, rdi
0x180017be0  mov     [rbp+var_1C], 0
0x180017be7  lea     r8, [rbp+var_1C]
0x180017beb  mov     [rbp+arg_18], 0
0x180017bf2  lea     rdx, [rbp+var_10]
0x180017bf6  call    ?GetSCBasedOnPK@?$DbTableDescription@VSharingToken@@@@SAJPEAVSharingToken@@PEAPEAU_jetSeekCriteria@@AEAK@Z; DbTableDescription<SharingToken>::GetSCBasedOnPK(SharingToken *,_jetSeekCriteria * *,ulong &)
0x180017bfb  mov     ebx, eax
0x180017bfd  test    eax, eax
0x180017bff  js      short loc_180017C60
0x180017c01  lea     r9, [rbp+arg_18]
0x180017c05  mov     rcx, rsi
0x180017c08  lea     r8, [rbp+var_20]
0x180017c0c  lea     rdx, [rbp+P]
0x180017c10  cmp     rdi, rsi
0x180017c13  jnz     short loc_180017C18
0x180017c15  mov     rcx, rdi
0x180017c18  call    ?Serialize@?$DbTableDescription@VSharingToken@@@@SAJPEAVSharingToken@@PEAPEAUJET_SETCOLUMN@@AEAKAEAH@Z; DbTableDescription<SharingToken>::Serialize(SharingToken *,JET_SETCOLUMN * *,ulong &,int &)
0x180017c1d  mov     rdi, [rbp+P]
0x180017c21  mov     ebx, eax
0x180017c23  test    eax, eax
0x180017c25  js      short loc_180017C53
0x180017c27  mov     eax, [rbp+arg_18]
0x180017c2a  mov     r9, rdi; struct JET_SETCOLUMN *
0x180017c2d  mov     r8d, [rbp+var_1C]; unsigned int
0x180017c31  mov     rdx, [rbp+var_10]; struct _jetSeekCriteria *
0x180017c35  mov     rcx, [r15+8]; this
0x180017c39  mov     [rsp+60h+var_30], 0; int
0x180017c41  mov     [rsp+60h+var_38], eax; int
0x180017c45  mov     eax, [rbp+var_20]
0x180017c48  mov     [rsp+60h+csetcolumn], eax; csetcolumn
0x180017c4c  call    ?Update@DbTable@@QEAAJPEAU_jetSeekCriteria@@KPEAUJET_SETCOLUMN@@HHH@Z; DbTable::Update(_jetSeekCriteria *,ulong,JET_SETCOLUMN *,int,int,int)
0x180017c51  mov     ebx, eax
0x180017c53  test    rdi, rdi
0x180017c56  jz      short loc_180017C60
0x180017c58  mov     rcx, rdi; P
0x180017c5b  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180017c60  cmp     [rbp+var_10], 0
0x180017c65  jz      short loc_180017C73
0x180017c67  mov     edx, [rbp+var_1C]
0x180017c6a  lea     rcx, [rbp+var_10]
0x180017c6e  call    ?ReleaseSC@?$DbTableDescription@VSharingToken@@@@SAXPEAPEAU_jetSeekCriteria@@K@Z; DbTableDescription<SharingToken>::ReleaseSC(_jetSeekCriteria * *,ulong)
0x180017c73  lea     r11, [rsp+60h+var_s0]
0x180017c78  mov     eax, ebx
0x180017c7a  mov     rbx, [r11+20h]
0x180017c7e  mov     rsi, [r11+28h]
0x180017c82  mov     rsp, r11
0x180017c85  pop     r15
0x180017c87  pop     rdi
0x180017c88  pop     rbp
0x180017c89  retn
```
