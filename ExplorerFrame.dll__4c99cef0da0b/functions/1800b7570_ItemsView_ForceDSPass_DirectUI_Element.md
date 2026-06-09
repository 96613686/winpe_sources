# ItemsView_ForceDSPass(DirectUI::Element *)

- ea: `0x1800b7570`
- end: `0x1800b7650`
- name: `?ItemsView_ForceDSPass@@YAXPEAVElement@DirectUI@@@Z`
- size: `224`
- prototype: `void __fastcall(struct DirectUI::Element *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800b7520`

## callees

- `0x180016790`
- `0x1800b7570`

## import_xrefs

- `USER32!GetDC` at `0x1800b75dc`
- `USER32!GetDC` at `0x1800b75dc`
- `USER32!ReleaseDC` at `0x1800b7625`
- `USER32!ReleaseDC` at `0x1800b7625`
- `DUI70!?LastDSConstProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800b7599`
- `DUI70!?NeedsDSUpdate@Element@DirectUI@@QEAA_NXZ` at `0x1800b7582`
- `DUI70!?NeedsDSUpdate@Element@DirectUI@@QEAA_NXZ` at `0x1800b7582`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x1800b7593`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x1800b7593`
- `DUI70!?GetType@Value@DirectUI@@QEBAHXZ` at `0x1800b75c3`
- `DUI70!?GetType@Value@DirectUI@@QEBAHXZ` at `0x1800b75c3`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800b75ad`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800b75ad`
- `DUI70!??0DCSurface@DirectUI@@QEAA@PEAUHDC__@@@Z` at `0x1800b75f2`
- `DUI70!??0DCSurface@DirectUI@@QEAA@PEAUHDC__@@@Z` at `0x1800b75f2`
- `DUI70!??1DCSurface@DirectUI@@UEAA@XZ` at `0x1800b7630`
- `DUI70!??1DCSurface@DirectUI@@UEAA@XZ` at `0x1800b7630`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x1800b761a`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x1800b761a`
- `DUI70!?GetSize@Value@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x1800b75d1`
- `DUI70!?GetSize@Value@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x1800b75d1`
- `DUI70!?MarkNeedsDSUpdate@Element@DirectUI@@QEAAXXZ` at `0x1800b75fb`
- `DUI70!?MarkNeedsDSUpdate@Element@DirectUI@@QEAAXXZ` at `0x1800b75fb`

## pseudocode

```c
void __fastcall ItemsView_ForceDSPass(struct DirectUI::Element *a1)
{
  DirectUI::Element *Parent; // rdi
  DirectUI::Value *Value; // rax
  DirectUI::Value *v4; // rbx
  const struct tagSIZE *Size; // rsi
  HDC DC; // rax
  HDC v7; // rbx
  _BYTE v8[24]; // [rsp+30h] [rbp-18h] BYREF
  DirectUI::Value *v9; // [rsp+58h] [rbp+10h] BYREF
  char v10; // [rsp+60h] [rbp+18h] BYREF

  if ( DirectUI::Element::NeedsDSUpdate(a1) )
  {
    Parent = DirectUI::Element::GetParent(a1);
    Value = DirectUI::Element::GetValue(
              Parent,
              (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::LastDSConstProp,
              1,
              0);
    v9 = Value;
    v4 = Value;
    if ( Value && DirectUI::Value::GetType(Value) == 7 )
    {
      Size = DirectUI::Value::GetSize(v4);
      DC = GetDC(0);
      v7 = DC;
      if ( DC )
      {
        DirectUI::DCSurface::DCSurface((DirectUI::DCSurface *)v8, DC);
        DirectUI::Element::MarkNeedsDSUpdate(Parent);
        DirectUI::Element::_UpdateDesiredSize(
          Parent,
          (unsigned int)&v10,
          Size->cx,
          (struct DirectUI::Surface *)(unsigned int)Size->cy);
        ReleaseDC(0, v7);
        DirectUI::DCSurface::~DCSurface((DirectUI::DCSurface *)v8);
      }
    }
    CValuePtr::~CValuePtr((CValuePtr *)&v9);
  }
}

```

## disassembly

```asm
0x1800b7570  mov     [rsp+arg_0], rbx
0x1800b7575  mov     [rsp+arg_18], rsi
0x1800b757a  push    rdi
0x1800b757b  sub     rsp, 40h
0x1800b757f  mov     rbx, rcx
0x1800b7582  call    cs:__imp_?NeedsDSUpdate@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::NeedsDSUpdate(void)
0x1800b7588  test    al, al
0x1800b758a  jz      loc_1800B7640
0x1800b7590  mov     rcx, rbx
0x1800b7593  call    cs:__imp_?GetParent@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetParent(void)
0x1800b7599  mov     rdx, cs:__imp_?LastDSConstProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::LastDSConstProp(void)
0x1800b75a0  xor     r9d, r9d
0x1800b75a3  mov     rcx, rax
0x1800b75a6  mov     rdi, rax
0x1800b75a9  lea     r8d, [r9+1]
0x1800b75ad  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x1800b75b3  mov     [rsp+48h+arg_8], rax
0x1800b75b8  mov     rbx, rax
0x1800b75bb  test    rax, rax
0x1800b75be  jz      short loc_1800B7636
0x1800b75c0  mov     rcx, rax
0x1800b75c3  call    cs:__imp_?GetType@Value@DirectUI@@QEBAHXZ; DirectUI::Value::GetType(void)
0x1800b75c9  cmp     eax, 7
0x1800b75cc  jnz     short loc_1800B7636
0x1800b75ce  mov     rcx, rbx
0x1800b75d1  call    cs:__imp_?GetSize@Value@DirectUI@@QEAAPEBUtagSIZE@@XZ; DirectUI::Value::GetSize(void)
0x1800b75d7  xor     ecx, ecx; hWnd
0x1800b75d9  mov     rsi, rax
0x1800b75dc  call    cs:__imp_GetDC
0x1800b75e2  mov     rbx, rax
0x1800b75e5  test    rax, rax
0x1800b75e8  jz      short loc_1800B7636
0x1800b75ea  mov     rdx, rax
0x1800b75ed  lea     rcx, [rsp+48h+var_18]
0x1800b75f2  call    cs:__imp_??0DCSurface@DirectUI@@QEAA@PEAUHDC__@@@Z; DirectUI::DCSurface::DCSurface(HDC__ *)
0x1800b75f8  mov     rcx, rdi
0x1800b75fb  call    cs:__imp_?MarkNeedsDSUpdate@Element@DirectUI@@QEAAXXZ; DirectUI::Element::MarkNeedsDSUpdate(void)
0x1800b7601  mov     r9d, [rsi+4]
0x1800b7605  lea     rax, [rsp+48h+var_18]
0x1800b760a  mov     r8d, [rsi]
0x1800b760d  lea     rdx, [rsp+48h+arg_10]
0x1800b7612  mov     rcx, rdi
0x1800b7615  mov     [rsp+48h+var_28], rax
0x1800b761a  call    cs:__imp_?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z; DirectUI::Element::_UpdateDesiredSize(int,int,DirectUI::Surface *)
0x1800b7620  mov     rdx, rbx; hDC
0x1800b7623  xor     ecx, ecx; hWnd
0x1800b7625  call    cs:__imp_ReleaseDC
0x1800b762b  lea     rcx, [rsp+48h+var_18]
0x1800b7630  call    cs:__imp_??1DCSurface@DirectUI@@UEAA@XZ; DirectUI::DCSurface::~DCSurface(void)
0x1800b7636  lea     rcx, [rsp+48h+arg_8]; this
0x1800b763b  call    ??1CValuePtr@@QEAA@XZ; CValuePtr::~CValuePtr(void)
0x1800b7640  mov     rbx, [rsp+48h+arg_0]
0x1800b7645  mov     rsi, [rsp+48h+arg_18]
0x1800b764a  add     rsp, 40h
0x1800b764e  pop     rdi
0x1800b764f  retn
```
