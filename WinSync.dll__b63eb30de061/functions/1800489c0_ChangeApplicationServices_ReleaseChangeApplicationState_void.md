# ChangeApplicationServices::ReleaseChangeApplicationState(void)

- ea: `0x1800489c0`
- end: `0x180048b02`
- name: `?ReleaseChangeApplicationState@ChangeApplicationServices@@AEAAXXZ`
- size: `322`
- prototype: `void __fastcall(ChangeApplicationServices *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180047900`
- `0x180047a60`

## callees

- `0x18001a038`
- `0x18001a274`
- `0x180047c90`
- `0x1800489c0`
- `0x180094010`

## string_xrefs

- `0x1800489f0`: `ChangeApplicationServices::ReleaseChangeApplicationState`
- `0x180048adf`: `ChangeApplicationServices::ReleaseChangeApplicationState`

## pseudocode

```c
void __fastcall ChangeApplicationServices::ReleaseChangeApplicationState(ChangeApplicationServices *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      48,
      WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      "ChangeApplicationServices::ReleaseChangeApplicationState");
  }
  HashTable<SyncId,SharedRefPtr<ChangeUnitChangeApplicationStatus>,DefaultHashTableContext>::FreeHashTable((char *)this + 176);
  SharedRefPtr<IForgottenKnowledge>::Recycle((char *)this + 80);
  SharedRefPtr<IForgottenKnowledge>::Recycle((char *)this + 88);
  SharedRefPtr<IForgottenKnowledge>::Recycle((char *)this + 96);
  SharedRefPtr<IForgottenKnowledge>::Recycle((char *)this + 104);
  v2 = *((_QWORD *)this + 17);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  *((_QWORD *)this + 17) = 0;
  v3 = *((_QWORD *)this + 18);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  *((_QWORD *)this + 18) = 0;
  v4 = *((_QWORD *)this + 19);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  *((_QWORD *)this + 19) = 0;
  SharedRefPtr<IForgottenKnowledge>::Recycle((char *)this + 160);
  SharedRefPtr<IForgottenKnowledge>::Recycle((char *)this + 168);
  *((_DWORD *)this + 56) = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      49,
      WPP_4a2131fcd8013ce1363c263eed970622_Traceguids,
      "ChangeApplicationServices::ReleaseChangeApplicationState");
  }
}

```

## disassembly

```asm
0x1800489c0  mov     [rsp+arg_0], rbx
0x1800489c5  push    rsi
0x1800489c6  sub     rsp, 20h
0x1800489ca  mov     rbx, rcx
0x1800489cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800489d4  lea     rsi, WPP_GLOBAL_Control
0x1800489db  cmp     rcx, rsi
0x1800489de  jz      short loc_180048A08
0x1800489e0  test    byte ptr [rcx+1Ch], 80h
0x1800489e4  jz      short loc_180048A08
0x1800489e6  cmp     byte ptr [rcx+19h], 5
0x1800489ea  jb      short loc_180048A08
0x1800489ec  mov     rcx, [rcx+10h]
0x1800489f0  lea     r9, aChangeapplicat_10; "ChangeApplicationServices::ReleaseChang"...
0x1800489f7  mov     edx, 30h ; '0'
0x1800489fc  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x180048a03  call    WPP_SF_s
0x180048a08  lea     rcx, [rbx+0B0h]
0x180048a0f  call    ?FreeHashTable@?$HashTable@VSyncId@@V?$SharedRefPtr@VChangeUnitChangeApplicationStatus@@@@VDefaultHashTableContext@@@@AEAAXXZ; HashTable<SyncId,SharedRefPtr<ChangeUnitChangeApplicationStatus>,DefaultHashTableContext>::FreeHashTable(void)
0x180048a14  lea     rcx, [rbx+50h]
0x180048a18  call    ?Recycle@?$SharedRefPtr@UIForgottenKnowledge@@@@QEAAXXZ; SharedRefPtr<IForgottenKnowledge>::Recycle(void)
0x180048a1d  lea     rcx, [rbx+58h]
0x180048a21  call    ?Recycle@?$SharedRefPtr@UIForgottenKnowledge@@@@QEAAXXZ; SharedRefPtr<IForgottenKnowledge>::Recycle(void)
0x180048a26  lea     rcx, [rbx+60h]
0x180048a2a  call    ?Recycle@?$SharedRefPtr@UIForgottenKnowledge@@@@QEAAXXZ; SharedRefPtr<IForgottenKnowledge>::Recycle(void)
0x180048a2f  lea     rcx, [rbx+68h]
0x180048a33  call    ?Recycle@?$SharedRefPtr@UIForgottenKnowledge@@@@QEAAXXZ; SharedRefPtr<IForgottenKnowledge>::Recycle(void)
0x180048a38  mov     rcx, [rbx+88h]
0x180048a3f  test    rcx, rcx
0x180048a42  jz      short loc_180048A50
0x180048a44  mov     rax, [rcx]
0x180048a47  mov     rax, [rax+10h]
0x180048a4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a50  mov     qword ptr [rbx+88h], 0
0x180048a5b  mov     rcx, [rbx+90h]
0x180048a62  test    rcx, rcx
0x180048a65  jz      short loc_180048A73
0x180048a67  mov     rax, [rcx]
0x180048a6a  mov     rax, [rax+10h]
0x180048a6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a73  mov     qword ptr [rbx+90h], 0
0x180048a7e  mov     rcx, [rbx+98h]
0x180048a85  test    rcx, rcx
0x180048a88  jz      short loc_180048A96
0x180048a8a  mov     rax, [rcx]
0x180048a8d  mov     rax, [rax+10h]
0x180048a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a96  lea     rcx, [rbx+0A0h]
0x180048a9d  mov     qword ptr [rbx+98h], 0
0x180048aa8  call    ?Recycle@?$SharedRefPtr@UIForgottenKnowledge@@@@QEAAXXZ; SharedRefPtr<IForgottenKnowledge>::Recycle(void)
0x180048aad  lea     rcx, [rbx+0A8h]
0x180048ab4  call    ?Recycle@?$SharedRefPtr@UIForgottenKnowledge@@@@QEAAXXZ; SharedRefPtr<IForgottenKnowledge>::Recycle(void)
0x180048ab9  mov     dword ptr [rbx+0E0h], 0
0x180048ac3  mov     rcx, cs:WPP_GLOBAL_Control
0x180048aca  cmp     rcx, rsi
0x180048acd  jz      short loc_180048AF7
0x180048acf  test    byte ptr [rcx+1Ch], 80h
0x180048ad3  jz      short loc_180048AF7
0x180048ad5  cmp     byte ptr [rcx+19h], 5
0x180048ad9  jb      short loc_180048AF7
0x180048adb  mov     rcx, [rcx+10h]
0x180048adf  lea     r9, aChangeapplicat_10; "ChangeApplicationServices::ReleaseChang"...
0x180048ae6  mov     edx, 31h ; '1'
0x180048aeb  lea     r8, WPP_4a2131fcd8013ce1363c263eed970622_Traceguids
0x180048af2  call    WPP_SF_s
0x180048af7  mov     rbx, [rsp+28h+arg_0]
0x180048afc  add     rsp, 20h
0x180048b00  pop     rsi
0x180048b01  retn
```
