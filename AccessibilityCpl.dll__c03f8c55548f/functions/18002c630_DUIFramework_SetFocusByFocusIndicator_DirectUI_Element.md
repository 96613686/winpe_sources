# DUIFramework_SetFocusByFocusIndicator(DirectUI::Element *)

- ea: `0x18002c630`
- end: `0x18002c710`
- name: `?DUIFramework_SetFocusByFocusIndicator@@YAJPEAVElement@DirectUI@@@Z`
- size: `224`
- prototype: `__int64 __fastcall(struct DirectUI::Element *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18002bcf0`

## callees

- `0x18002c630`
- `0x18002e010`

## import_xrefs

- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18002c674`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18002c674`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18002c68c`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18002c68c`
- `DUI70!StrToID` at `0x18002c648`
- `DUI70!StrToID` at `0x18002c648`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18002c654`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18002c698`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18002c654`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18002c698`
- `DUI70!?Init@NavReference@DirectUI@@QEAAXPEAVElement@2@PEAUtagRECT@@@Z` at `0x18002c6c0`
- `DUI70!?Init@NavReference@DirectUI@@QEAAXPEAVElement@2@PEAUtagRECT@@@Z` at `0x18002c6c0`
- `DUI70!?GetAtom@Value@DirectUI@@QEAAGXZ` at `0x18002c680`
- `DUI70!?GetAtom@Value@DirectUI@@QEAAGXZ` at `0x18002c680`

## pseudocode

```c
__int64 __fastcall DUIFramework_SetFocusByFocusIndicator(struct DirectUI::Element *a1)
{
  unsigned int v2; // ebp
  unsigned __int16 v3; // ax
  DirectUI::Element *Descendent; // rax
  DirectUI::Value *Value; // rdi
  unsigned __int16 Atom; // bx
  struct DirectUI::Element *v7; // rbx
  __int64 v8; // rax
  __int128 v10; // [rsp+30h] [rbp-48h] BYREF
  __int64 v11; // [rsp+40h] [rbp-38h]

  v2 = -2147467259;
  v3 = StrToID(L"FocusIndicator");
  Descendent = DirectUI::Element::FindDescendent(a1, v3);
  if ( Descendent )
  {
    Value = DirectUI::Element::GetValue(Descendent, (const struct DirectUI::PropertyInfo *)&off_180040690, 2, 0);
    Atom = DirectUI::Value::GetAtom(Value);
    DirectUI::Value::Release(Value);
    v7 = DirectUI::Element::FindDescendent(a1, Atom);
    if ( v7 )
    {
      v11 = 0;
      v10 = 0;
      DirectUI::NavReference::Init((DirectUI::NavReference *)&v10, v7, 0);
      v8 = (*(__int64 (__fastcall **)(struct DirectUI::Element *, _QWORD, __int64, __int128 *, int))(*(_QWORD *)v7 + 152LL))(
             v7,
             0,
             3,
             &v10,
             3);
      if ( v8 )
        v7 = (struct DirectUI::Element *)v8;
      (*(void (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)v7 + 168LL))(v7);
      return 0;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18002c630  push    rbx
0x18002c632  push    rbp
0x18002c633  push    rsi
0x18002c634  push    rdi
0x18002c635  sub     rsp, 58h
0x18002c639  mov     rsi, rcx
0x18002c63c  mov     ebp, 80004005h
0x18002c641  lea     rcx, aFocusindicator; "FocusIndicator"
0x18002c648  call    cs:__imp_StrToID
0x18002c64e  movzx   edx, ax
0x18002c651  mov     rcx, rsi
0x18002c654  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18002c65a  test    rax, rax
0x18002c65d  jz      loc_18002C705
0x18002c663  xor     r9d, r9d
0x18002c666  lea     rdx, off_180040690; "firsttabtarget"
0x18002c66d  mov     rcx, rax
0x18002c670  lea     r8d, [r9+2]
0x18002c674  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18002c67a  mov     rcx, rax
0x18002c67d  mov     rdi, rax
0x18002c680  call    cs:__imp_?GetAtom@Value@DirectUI@@QEAAGXZ; DirectUI::Value::GetAtom(void)
0x18002c686  mov     rcx, rdi
0x18002c689  movzx   ebx, ax
0x18002c68c  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18002c692  movzx   edx, bx
0x18002c695  mov     rcx, rsi
0x18002c698  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18002c69e  mov     rbx, rax
0x18002c6a1  test    rax, rax
0x18002c6a4  jz      short loc_18002C705
0x18002c6a6  xorps   xmm0, xmm0
0x18002c6a9  lea     rcx, [rsp+78h+var_48]
0x18002c6ae  xor     eax, eax
0x18002c6b0  xor     r8d, r8d
0x18002c6b3  mov     rdx, rbx
0x18002c6b6  mov     [rsp+78h+var_38], rax
0x18002c6bb  movups  [rsp+78h+var_48], xmm0
0x18002c6c0  call    cs:__imp_?Init@NavReference@DirectUI@@QEAAXPEAVElement@2@PEAUtagRECT@@@Z; DirectUI::NavReference::Init(DirectUI::Element *,tagRECT *)
0x18002c6c6  mov     rax, [rbx]
0x18002c6c9  lea     r9, [rsp+78h+var_48]
0x18002c6ce  mov     r8d, 3
0x18002c6d4  xor     edx, edx
0x18002c6d6  mov     rcx, rbx
0x18002c6d9  mov     [rsp+78h+var_58], r8d
0x18002c6de  mov     rax, [rax+98h]
0x18002c6e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c6ea  test    rax, rax
0x18002c6ed  cmovnz  rbx, rax
0x18002c6f1  mov     rcx, rbx
0x18002c6f4  mov     rax, [rbx]
0x18002c6f7  mov     rax, [rax+0A8h]
0x18002c6fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c703  xor     ebp, ebp
0x18002c705  mov     eax, ebp
0x18002c707  add     rsp, 58h
0x18002c70b  pop     rdi
0x18002c70c  pop     rsi
0x18002c70d  pop     rbp
0x18002c70e  pop     rbx
0x18002c70f  retn
```
