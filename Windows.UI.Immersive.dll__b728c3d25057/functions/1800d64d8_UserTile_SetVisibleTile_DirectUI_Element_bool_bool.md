# UserTile::_SetVisibleTile(DirectUI::Element *,bool,bool)

- ea: `0x1800d64d8`
- end: `0x1800d672f`
- name: `?_SetVisibleTile@UserTile@@AEAAXPEAVElement@DirectUI@@_N1@Z`
- size: `599`
- prototype: `void __fastcall(UserTile *__hidden this, struct DirectUI::Element *, bool, bool)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800ccba0`
- `0x1800d6038`
- `0x1800d6770`

## callees

- `0x180037a1c`
- `0x1800610ec`
- `0x1800d58cc`
- `0x1800d6414`
- `0x1800d64d8`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800d6599`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800d6599`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x1800d6573`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x1800d657f`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x1800d6573`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x1800d657f`
- `DUI70!?CustomProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800d6510`
- `DUI70!?CustomProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800d6543`
- `DUI70!?GetType@Value@DirectUI@@QEBAHXZ` at `0x1800d6538`
- `DUI70!?GetType@Value@DirectUI@@QEBAHXZ` at `0x1800d6565`
- `DUI70!?GetType@Value@DirectUI@@QEBAHXZ` at `0x1800d6538`
- `DUI70!?GetType@Value@DirectUI@@QEBAHXZ` at `0x1800d6565`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800d663f`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800d66ab`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800d66b5`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800d663f`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800d66ab`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x1800d66b5`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800d66c5`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800d6710`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800d66c5`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x1800d6710`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800d65af`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800d65b8`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800d65af`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800d65b8`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800d6521`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800d6554`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800d6521`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800d6554`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x1800d661b`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x1800d661b`

## pseudocode

```c
void __fastcall UserTile::_SetVisibleTile(UserTile *this, struct DirectUI::Element *a2, char a3, char a4)
{
  DirectUI::Element *v4; // rbp
  DirectUI::Value *Value; // rax
  DirectUI::Value *v9; // r14
  int v10; // ebx
  DirectUI::Value *v11; // rax
  DirectUI::Value *v12; // r15
  const WCHAR *String; // rbx
  const WCHAR *v14; // rax
  int v15; // eax
  __int64 v16; // r9
  struct DirectUI::IClassInfo *v17; // rbx
  __int64 v18; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-58h]
  __int64 v20; // [rsp+80h] [rbp+8h] BYREF

  v4 = (DirectUI::Element *)*((_QWORD *)this + 40);
  if ( !a4 )
  {
    if ( v4 )
    {
      Value = DirectUI::Element::GetValue(
                *((DirectUI::Element **)this + 40),
                (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::CustomProp,
                1,
                0);
      v9 = Value;
      if ( Value )
      {
        v10 = 0;
        if ( DirectUI::Value::GetType(Value) == 5 )
        {
          v11 = DirectUI::Element::GetValue(
                  a2,
                  (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::CustomProp,
                  1,
                  0);
          v12 = v11;
          if ( v11 )
          {
            if ( DirectUI::Value::GetType(v11) == 5 )
            {
              String = DirectUI::Value::GetString(v12);
              v14 = DirectUI::Value::GetString(v9);
              v15 = CompareStringOrdinal(v14, -1, String, -1, 1);
              v10 = 0;
              if ( v15 == 2 )
                v10 = -2147467259;
            }
            DirectUI::Value::Release(v12);
          }
        }
        DirectUI::Value::Release(v9);
        if ( v10 < 0 )
          goto LABEL_27;
      }
    }
  }
  if ( a3 )
  {
    if ( !*((_BYTE *)this + 328) )
    {
      UserTile::_SetBehaviorHelper(this, this, L"AnimationTrap");
      UserTile::_SetBehaviorHelper(this, *((struct DirectUI::Element **)this + 40), L"ImplicitAnimation");
      *((_BYTE *)this + 328) = 1;
    }
    UserTile::_SetBehaviorHelper(this, a2, L"ImplicitAnimation");
  }
  if ( (int)DirectUI::Element::Add(this, a2) < 0 )
  {
LABEL_27:
    DirectUI::Element::Destroy(a2, 1);
  }
  else
  {
    *((_QWORD *)this + 40) = a2;
    if ( a3 )
    {
      if ( v4 )
      {
        DirectUI::Element::SetVisible(a2, 0);
        v20 = 0;
        if ( (int)DirectUI::DuiPVLTrigger::EnsureObject((DirectUI::DuiPVLTrigger *)&v20) >= 0 )
        {
          LOBYTE(v16) = 1;
          LOBYTE(bIgnoreCase) = 1;
          (*(void (__fastcall **)(__int64, DirectUI::Element *, struct DirectUI::Element *, __int64, BOOL, char, _BYTE, _QWORD))(*(_QWORD *)v20 + 176LL))(
            v20,
            v4,
            a2,
            v16,
            bIgnoreCase,
            1,
            0,
            0);
        }
        DirectUI::DuiPVLTrigger::~DuiPVLTrigger((DirectUI::DuiPVLTrigger *)&v20);
      }
      else
      {
        DirectUI::Element::SetVisible(a2, 1);
      }
    }
    else
    {
      DirectUI::Element::SetVisible(a2, 1);
      if ( v4 )
        DirectUI::Element::Destroy(v4, 1);
    }
    v17 = LowResourceVideo::Class;
    if ( (struct DirectUI::IClassInfo *)(*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)a2 + 280LL))(a2) == v17 )
    {
      v18 = element_cast<LowResourceVideo>(a2);
      if ( v18 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v18 + 216) + 24LL))(*(_QWORD *)(v18 + 216));
    }
  }
}

```

## disassembly

```asm
0x1800d64d8  mov     [rsp+arg_8], rbx
0x1800d64dd  mov     [rsp+arg_10], rbp
0x1800d64e2  push    rsi
0x1800d64e3  push    rdi
0x1800d64e4  push    r12
0x1800d64e6  push    r14
0x1800d64e8  push    r15
0x1800d64ea  sub     rsp, 50h
0x1800d64ee  mov     rbp, [rcx+140h]
0x1800d64f5  mov     r12b, r8b
0x1800d64f8  mov     rdi, rdx
0x1800d64fb  mov     rsi, rcx
0x1800d64fe  test    r9b, r9b
0x1800d6501  jnz     loc_1800D65C6
0x1800d6507  test    rbp, rbp
0x1800d650a  jz      loc_1800D65C6
0x1800d6510  mov     rdx, cs:__imp_?CustomProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::CustomProp(void)
0x1800d6517  xor     r9d, r9d
0x1800d651a  mov     rcx, rbp
0x1800d651d  lea     r8d, [r9+1]
0x1800d6521  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x1800d6527  mov     r14, rax
0x1800d652a  test    rax, rax
0x1800d652d  jz      loc_1800D65C6
0x1800d6533  mov     rcx, rax
0x1800d6536  xor     ebx, ebx
0x1800d6538  call    cs:__imp_?GetType@Value@DirectUI@@QEBAHXZ; DirectUI::Value::GetType(void)
0x1800d653e  cmp     eax, 5
0x1800d6541  jnz     short loc_1800D65B5
0x1800d6543  mov     rdx, cs:__imp_?CustomProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::CustomProp(void)
0x1800d654a  lea     r8d, [rbx+1]
0x1800d654e  xor     r9d, r9d
0x1800d6551  mov     rcx, rdi
0x1800d6554  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x1800d655a  mov     r15, rax
0x1800d655d  test    rax, rax
0x1800d6560  jz      short loc_1800D65B5
0x1800d6562  mov     rcx, rax
0x1800d6565  call    cs:__imp_?GetType@Value@DirectUI@@QEBAHXZ; DirectUI::Value::GetType(void)
0x1800d656b  cmp     eax, 5
0x1800d656e  jnz     short loc_1800D65AC
0x1800d6570  mov     rcx, r15
0x1800d6573  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x1800d6579  mov     rcx, r14
0x1800d657c  mov     rbx, rax
0x1800d657f  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x1800d6585  or      edx, 0FFFFFFFFh; cchCount1
0x1800d6588  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x1800d6590  mov     r9d, edx; cchCount2
0x1800d6593  mov     r8, rbx; lpString2
0x1800d6596  mov     rcx, rax; lpString1
0x1800d6599  call    cs:__imp_CompareStringOrdinal
0x1800d659f  xor     ebx, ebx
0x1800d65a1  mov     ecx, 80004005h
0x1800d65a6  cmp     eax, 2
0x1800d65a9  cmovz   ebx, ecx
0x1800d65ac  mov     rcx, r15
0x1800d65af  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800d65b5  mov     rcx, r14
0x1800d65b8  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800d65be  test    ebx, ebx
0x1800d65c0  js      loc_1800D670B
0x1800d65c6  test    r12b, r12b
0x1800d65c9  jz      short loc_1800D6615
0x1800d65cb  cmp     byte ptr [rsi+148h], 0
0x1800d65d2  jnz     short loc_1800D6603
0x1800d65d4  lea     r8, aAnimationtrap; "AnimationTrap"
0x1800d65db  mov     rdx, rsi; struct DirectUI::Element *
0x1800d65de  mov     rcx, rsi; this
0x1800d65e1  call    ?_SetBehaviorHelper@UserTile@@AEAAXPEAVElement@DirectUI@@PEBG@Z; UserTile::_SetBehaviorHelper(DirectUI::Element *,ushort const *)
0x1800d65e6  mov     rdx, [rsi+140h]; struct DirectUI::Element *
0x1800d65ed  lea     r8, aImplicitanimat; "ImplicitAnimation"
0x1800d65f4  mov     rcx, rsi; this
0x1800d65f7  call    ?_SetBehaviorHelper@UserTile@@AEAAXPEAVElement@DirectUI@@PEBG@Z; UserTile::_SetBehaviorHelper(DirectUI::Element *,ushort const *)
0x1800d65fc  mov     byte ptr [rsi+148h], 1
0x1800d6603  lea     r8, aImplicitanimat; "ImplicitAnimation"
0x1800d660a  mov     rdx, rdi; struct DirectUI::Element *
0x1800d660d  mov     rcx, rsi; this
0x1800d6610  call    ?_SetBehaviorHelper@UserTile@@AEAAXPEAVElement@DirectUI@@PEBG@Z; UserTile::_SetBehaviorHelper(DirectUI::Element *,ushort const *)
0x1800d6615  mov     rdx, rdi
0x1800d6618  mov     rcx, rsi
0x1800d661b  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x1800d6621  test    eax, eax
0x1800d6623  js      loc_1800D670B
0x1800d6629  mov     [rsi+140h], rdi
0x1800d6630  mov     rcx, rdi
0x1800d6633  test    r12b, r12b
0x1800d6636  jz      short loc_1800D66B3
0x1800d6638  test    rbp, rbp
0x1800d663b  jz      short loc_1800D66A9
0x1800d663d  xor     edx, edx
0x1800d663f  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x1800d6645  lea     rcx, [rsp+78h+arg_0]; this
0x1800d664d  mov     [rsp+78h+arg_0], 0
0x1800d6659  call    ?EnsureObject@DuiPVLTrigger@DirectUI@@IEAAJXZ; DirectUI::DuiPVLTrigger::EnsureObject(void)
0x1800d665e  test    eax, eax
0x1800d6660  js      short loc_1800D669A
0x1800d6662  mov     rcx, [rsp+78h+arg_0]
0x1800d666a  mov     r9b, 1
0x1800d666d  mov     [rsp+78h+var_40], 0
0x1800d6676  mov     r8, rdi
0x1800d6679  mov     [rsp+78h+var_48], 0
0x1800d667e  mov     rdx, rbp
0x1800d6681  mov     [rsp+78h+var_50], 1
0x1800d6686  mov     rax, [rcx]
0x1800d6689  mov     byte ptr [rsp+78h+bIgnoreCase], 1
0x1800d668e  mov     rax, [rax+0B0h]
0x1800d6695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d669a  lea     rcx, [rsp+78h+arg_0]; this
0x1800d66a2  call    ??1DuiPVLTrigger@DirectUI@@QEAA@XZ; DirectUI::DuiPVLTrigger::~DuiPVLTrigger(void)
0x1800d66a7  jmp     short loc_1800D66CB
0x1800d66a9  mov     dl, 1
0x1800d66ab  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x1800d66b1  jmp     short loc_1800D66CB
0x1800d66b3  mov     dl, 1
0x1800d66b5  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x1800d66bb  test    rbp, rbp
0x1800d66be  jz      short loc_1800D66CB
0x1800d66c0  mov     dl, 1
0x1800d66c2  mov     rcx, rbp
0x1800d66c5  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x1800d66cb  mov     rax, [rdi]
0x1800d66ce  mov     rcx, rdi
0x1800d66d1  mov     rbx, cs:?Class@LowResourceVideo@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * LowResourceVideo::Class
0x1800d66d8  mov     rax, [rax+118h]
0x1800d66df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d66e4  cmp     rax, rbx
0x1800d66e7  jnz     short loc_1800D6716
0x1800d66e9  mov     rcx, rdi
0x1800d66ec  call    ??$element_cast@VLowResourceVideo@@@@YAPEAVLowResourceVideo@@PEAVElement@DirectUI@@@Z; element_cast<LowResourceVideo>(DirectUI::Element *)
0x1800d66f1  test    rax, rax
0x1800d66f4  jz      short loc_1800D6716
0x1800d66f6  mov     rcx, [rax+0D8h]
0x1800d66fd  mov     rax, [rcx]
0x1800d6700  mov     rax, [rax+18h]
0x1800d6704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6709  jmp     short loc_1800D6716
0x1800d670b  mov     dl, 1
0x1800d670d  mov     rcx, rdi
0x1800d6710  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x1800d6716  lea     r11, [rsp+78h+var_28]
0x1800d671b  mov     rbx, [r11+38h]
0x1800d671f  mov     rbp, [r11+40h]
0x1800d6723  mov     rsp, r11
0x1800d6726  pop     r15
0x1800d6728  pop     r14
0x1800d672a  pop     r12
0x1800d672c  pop     rdi
0x1800d672d  pop     rsi
0x1800d672e  retn
```
