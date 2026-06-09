# DUI_SetElementBitmap(DirectUI::Element *,HBITMAP__ *,uchar,uint,ImageRtlMode,bool)

- ea: `0x1800d0858`
- end: `0x1800d08f0`
- name: `?DUI_SetElementBitmap@@YAJPEAVElement@DirectUI@@PEAUHBITMAP__@@EIW4ImageRtlMode@@_N@Z`
- size: `152`
- prototype: `int __high(struct DirectUI::Element *, HBITMAP, unsigned __int8, unsigned int, enum ImageRtlMode, bool)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18008f8d0`
- `0x1800d6f28`

## callees

- `0x1800d0858`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800d08c2`
- `GDI32!DeleteObject` at `0x1800d08c2`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x1800d08d6`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x1800d08d6`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z` at `0x1800d088b`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z` at `0x1800d088b`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800d0899`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800d08cf`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800d08b7`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800d08b7`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800d08ac`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800d08ac`

## pseudocode

```c
__int64 __fastcall DUI_SetElementBitmap(DirectUI::Element *a1, HBITMAP a2, unsigned __int8 a3)
{
  struct DirectUI::Value *Graphic; // rax
  DirectUI::Value *v6; // rsi
  unsigned int v7; // ebx

  if ( a2 )
  {
    Graphic = DirectUI::Value::CreateGraphic(a2, a3, 0xFFFFFFFF, 0, 0, 0);
    v6 = Graphic;
    if ( Graphic )
    {
      v7 = DirectUI::Element::SetValue(
             a1,
             (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ContentProp,
             1,
             Graphic);
      DirectUI::Value::Release(v6);
    }
    else
    {
      DeleteObject(a2);
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)DirectUI::Element::RemoveLocalValue(
                           a1,
                           (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ContentProp);
  }
  return v7;
}

```

## disassembly

```asm
0x1800d0858  mov     [rsp+arg_0], rbx
0x1800d085d  mov     [rsp+arg_8], rsi
0x1800d0862  push    rdi
0x1800d0863  sub     rsp, 30h
0x1800d0867  mov     al, r8b
0x1800d086a  mov     rbx, rdx
0x1800d086d  mov     rdi, rcx
0x1800d0870  test    rdx, rdx
0x1800d0873  jz      short loc_1800D08CF
0x1800d0875  mov     [rsp+38h+var_10], 0
0x1800d087a  xor     r9d, r9d
0x1800d087d  or      r8d, 0FFFFFFFFh
0x1800d0881  mov     [rsp+38h+var_18], 0
0x1800d0886  mov     dl, al
0x1800d0888  mov     rcx, rbx
0x1800d088b  call    cs:__imp_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z; DirectUI::Value::CreateGraphic(HBITMAP__ *,uchar,uint,bool,bool,bool)
0x1800d0891  mov     rsi, rax
0x1800d0894  test    rax, rax
0x1800d0897  jz      short loc_1800D08BF
0x1800d0899  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x1800d08a0  mov     r9, rax
0x1800d08a3  mov     r8d, 1
0x1800d08a9  mov     rcx, rdi
0x1800d08ac  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x1800d08b2  mov     rcx, rsi
0x1800d08b5  mov     ebx, eax
0x1800d08b7  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800d08bd  jmp     short loc_1800D08DE
0x1800d08bf  mov     rcx, rbx; ho
0x1800d08c2  call    cs:__imp_DeleteObject
0x1800d08c8  mov     ebx, 8007000Eh
0x1800d08cd  jmp     short loc_1800D08DE
0x1800d08cf  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x1800d08d6  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x1800d08dc  mov     ebx, eax
0x1800d08de  mov     rsi, [rsp+38h+arg_8]
0x1800d08e3  mov     eax, ebx
0x1800d08e5  mov     rbx, [rsp+38h+arg_0]
0x1800d08ea  add     rsp, 30h
0x1800d08ee  pop     rdi
0x1800d08ef  retn
```
