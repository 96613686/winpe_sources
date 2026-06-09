# ClientPicker::SetFilter(CLIENTFILTER,ARPFrame *)

- ea: `0x18000e3d4`
- end: `0x18000e4b2`
- name: `?SetFilter@ClientPicker@@QEAAJW4CLIENTFILTER@@PEAVARPFrame@@@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000e4c0`

## callees

- `0x180008ac0`
- `0x180009ba0`
- `0x18000b9dc`
- `0x18000e3d4`
- `0x18000fcb8`
- `0x18000fdc4`

## import_xrefs

- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18000e405`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18000e405`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000e45c`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000e45c`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18000e411`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18000e411`

## pseudocode

```c
__int64 __fastcall ClientPicker::SetFilter(UINT_PTR a1, int a2, __int64 a3)
{
  int v5; // edi
  DirectUI::Value *Value; // rsi
  const unsigned __int16 *String; // rax
  ClientBlock *v8; // rcx
  int *v9; // rdx
  int v10; // ecx
  _DWORD *v11; // rdx
  const unsigned __int16 *v13; // [rsp+20h] [rbp-38h] BYREF
  ClientBlock *v14; // [rsp+28h] [rbp-30h]

  *(_DWORD *)(a1 + 204) = a2;
  *(_WORD *)(a1 + 208) = 256;
  v5 = -2147467259;
  Value = DirectUI::Element::GetValue(
            (DirectUI::Element *)a1,
            (const struct DirectUI::PropertyInfo *)&off_1800772F8,
            2,
            0);
  String = DirectUI::Value::GetString(Value);
  if ( String )
  {
    v13 = String;
    v14 = 0;
    TraverseTree<ClientBlock>(a3, FindClientBlockCB, &v13);
    v8 = v14;
    *(_QWORD *)(a1 + 248) = v14;
    if ( v8 )
      v5 = ClientBlock::InitializeClientPicker(v8, (struct DirectUI::Element **)a1);
  }
  DirectUI::Value::Release(Value);
  if ( v5 >= 0 )
  {
    v9 = *(int **)(a1 + 224);
    v10 = *v9;
    if ( (*v9 & 0xFFFFFFF) != 0 )
    {
      v11 = v9 + 2;
      if ( (v10 & 0x10000000) != 0 )
        v11 = *(_DWORD **)v11;
      _SetStaticTextAndAccName(
        *(struct DirectUI::Element **)(a1 + 232),
        *(const unsigned __int16 **)(*(_QWORD *)v11 + 8LL));
    }
    ClientPicker::CalculateWidth((ClientPicker *)a1);
    ClientPicker::_SyncUIActive(a1);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000e3d4  push    rbx
0x18000e3d6  push    rbp
0x18000e3d7  push    rsi
0x18000e3d8  push    rdi
0x18000e3d9  sub     rsp, 38h
0x18000e3dd  xor     r9d, r9d
0x18000e3e0  mov     [rcx+0CCh], edx
0x18000e3e6  mov     rbp, r8
0x18000e3e9  mov     word ptr [rcx+0D0h], 100h
0x18000e3f2  lea     rdx, off_1800772F8; "ClientType"
0x18000e3f9  mov     rbx, rcx
0x18000e3fc  mov     edi, 80004005h
0x18000e401  lea     r8d, [r9+2]
0x18000e405  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18000e40b  mov     rcx, rax
0x18000e40e  mov     rsi, rax
0x18000e411  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x18000e417  test    rax, rax
0x18000e41a  jz      short loc_18000E459
0x18000e41c  lea     r8, [rsp+58h+var_38]
0x18000e421  mov     [rsp+58h+var_38], rax
0x18000e426  lea     rdx, ?FindClientBlockCB@@YAJPEAVClientBlock@@_J@Z; FindClientBlockCB(ClientBlock *,__int64)
0x18000e42d  mov     [rsp+58h+var_30], 0
0x18000e436  mov     rcx, rbp
0x18000e439  call    ??$TraverseTree@VClientBlock@@@@YAJPEAVElement@DirectUI@@P6AJPEAVClientBlock@@_J@Z2@Z; TraverseTree<ClientBlock>(DirectUI::Element *,long (*)(ClientBlock *,__int64),__int64)
0x18000e43e  mov     rcx, [rsp+58h+var_30]; this
0x18000e443  mov     [rbx+0F8h], rcx
0x18000e44a  test    rcx, rcx
0x18000e44d  jz      short loc_18000E459
0x18000e44f  mov     rdx, rbx; struct ClientPicker *
0x18000e452  call    ?InitializeClientPicker@ClientBlock@@QEAAJPEAVClientPicker@@@Z; ClientBlock::InitializeClientPicker(ClientPicker *)
0x18000e457  mov     edi, eax
0x18000e459  mov     rcx, rsi
0x18000e45c  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18000e462  test    edi, edi
0x18000e464  js      short loc_18000E4A7
0x18000e466  mov     rdx, [rbx+0E0h]
0x18000e46d  mov     ecx, [rdx]
0x18000e46f  test    ecx, 0FFFFFFFh
0x18000e475  jz      short loc_18000E497
0x18000e477  add     rdx, 8
0x18000e47b  bt      ecx, 1Ch
0x18000e47f  jnb     short loc_18000E484
0x18000e481  mov     rdx, [rdx]
0x18000e484  mov     rdx, [rdx]
0x18000e487  mov     rcx, [rbx+0E8h]; struct DirectUI::Element *
0x18000e48e  mov     rdx, [rdx+8]; unsigned __int16 *
0x18000e492  call    ?_SetStaticTextAndAccName@@YAXPEAVElement@DirectUI@@PEBG@Z; _SetStaticTextAndAccName(DirectUI::Element *,ushort const *)
0x18000e497  mov     rcx, rbx; this
0x18000e49a  call    ?CalculateWidth@ClientPicker@@QEAAXXZ; ClientPicker::CalculateWidth(void)
0x18000e49f  mov     rcx, rbx; uIDEvent
0x18000e4a2  call    ?_SyncUIActive@ClientPicker@@AEAAXXZ; ClientPicker::_SyncUIActive(void)
0x18000e4a7  mov     eax, edi
0x18000e4a9  add     rsp, 38h
0x18000e4ad  pop     rdi
0x18000e4ae  pop     rsi
0x18000e4af  pop     rbp
0x18000e4b0  pop     rbx
0x18000e4b1  retn
```
