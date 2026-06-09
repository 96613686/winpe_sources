# LineScroller::_CheckScroll(LineScrollbarBase *,int,SCROLLBARVISIBILITY)

- ea: `0x1800b7e50`
- end: `0x1800b7fae`
- name: `?_CheckScroll@LineScroller@@AEAAHPEAVLineScrollbarBase@@HW4SCROLLBARVISIBILITY@@@Z`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18007c000`

## callees

- `0x1800b7e50`

## import_xrefs

- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800b7ee6`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800b7f91`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800b7ee6`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800b7f91`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800b7f26`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800b7f26`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800b7eef`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800b7eef`
- `DUI70!?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z` at `0x1800b7ec8`
- `DUI70!?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z` at `0x1800b7ec8`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x1800b7eb9`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x1800b7f66`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x1800b7eb9`
- `DUI70!?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z` at `0x1800b7f66`
- `DUI70!?GetBoolFalse@Value@DirectUI@@SAPEAV12@XZ` at `0x1800b7f78`
- `DUI70!?GetBoolFalse@Value@DirectUI@@SAPEAV12@XZ` at `0x1800b7f78`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x1800b7e6a`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x1800b7ef8`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x1800b7e6a`
- `DUI70!?GetLayoutPos@Element@DirectUI@@QEAAHXZ` at `0x1800b7ef8`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x1800b7f2e`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x1800b7f70`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x1800b7f2e`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x1800b7f70`
- `DUI70!?LayoutPosProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800b7ed6`
- `DUI70!?LayoutPosProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800b7f5c`
- `DUI70!?IsScrollable@BaseScrollBar@DirectUI@@QEAA_NXZ` at `0x1800b7e82`
- `DUI70!?IsScrollable@BaseScrollBar@DirectUI@@QEAA_NXZ` at `0x1800b7e82`
- `DUI70!?EnabledProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800b7eaf`
- `DUI70!?EnabledProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800b7f7e`
- `DUI70!?_GetChangesUpdatePass@Element@DirectUI@@QEAAHXZ` at `0x1800b7f39`
- `DUI70!?_GetChangesUpdatePass@Element@DirectUI@@QEAAHXZ` at `0x1800b7f39`

## pseudocode

```c
__int64 __fastcall LineScroller::_CheckScroll(DirectUI::Element *a1, __int64 a2, int a3, int a4)
{
  int LayoutPos; // r14d
  bool IsScrollable; // al
  int v10; // ebx
  struct DirectUI::Value *Int; // rax
  DirectUI::Value *v12; // rbx
  int ChangesUpdatePass; // eax
  struct DirectUI::Value *Unset; // rax

  LayoutPos = DirectUI::Element::GetLayoutPos((DirectUI::Element *)a2);
  if ( !a3 )
    goto LABEL_11;
  IsScrollable = DirectUI::BaseScrollBar::IsScrollable((DirectUI::BaseScrollBar *)(a2 + 352));
  v10 = IsScrollable;
  if ( a4 == 2 )
  {
    DirectUI::Element::RemoveLocalValue(
      (DirectUI::Element *)a2,
      (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::LayoutPosProp);
    if ( v10 )
      Unset = (struct DirectUI::Value *)DirectUI::Value::GetUnset();
    else
      Unset = (struct DirectUI::Value *)DirectUI::Value::GetBoolFalse();
    DirectUI::Element::SetValue(
      (DirectUI::Element *)a2,
      (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::EnabledProp,
      1,
      Unset);
    return (LayoutPos != -3) ^ (unsigned int)(DirectUI::Element::GetLayoutPos((DirectUI::Element *)a2) == -3);
  }
  if ( a4 )
  {
LABEL_11:
    DirectUI::Element::SetLayoutPos((DirectUI::Element *)a2, -3);
    return (LayoutPos != -3) ^ (unsigned int)(DirectUI::Element::GetLayoutPos((DirectUI::Element *)a2) == -3);
  }
  if ( !IsScrollable && LayoutPos != -3 )
  {
    ChangesUpdatePass = DirectUI::Element::_GetChangesUpdatePass(a1);
    if ( ChangesUpdatePass != *((_DWORD *)a1 + 153) )
    {
      *((_DWORD *)a1 + 153) = ChangesUpdatePass;
      *((_DWORD *)a1 + 154) = 0;
    }
    if ( (int)++*((_DWORD *)a1 + 154) > 4 )
      v10 = 1;
  }
  DirectUI::Element::RemoveLocalValue(
    (DirectUI::Element *)a2,
    (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::EnabledProp);
  if ( v10 )
    Int = (struct DirectUI::Value *)DirectUI::Value::GetUnset();
  else
    Int = (struct DirectUI::Value *)DirectUI::Value::CreateInt(4294967293LL, 0);
  v12 = Int;
  if ( Int )
  {
    DirectUI::Element::SetValue(
      (DirectUI::Element *)a2,
      (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::LayoutPosProp,
      1,
      Int);
    DirectUI::Value::Release(v12);
  }
  return (LayoutPos != -3) ^ (unsigned int)(DirectUI::Element::GetLayoutPos((DirectUI::Element *)a2) == -3);
}

```

## disassembly

```asm
0x1800b7e50  push    rbx
0x1800b7e52  push    rbp
0x1800b7e53  push    rsi
0x1800b7e54  push    rdi
0x1800b7e55  push    r14
0x1800b7e57  sub     rsp, 20h
0x1800b7e5b  mov     rsi, rcx
0x1800b7e5e  mov     ebp, r9d
0x1800b7e61  mov     rcx, rdx
0x1800b7e64  mov     ebx, r8d
0x1800b7e67  mov     rdi, rdx
0x1800b7e6a  call    cs:__imp_?GetLayoutPos@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetLayoutPos(void)
0x1800b7e70  mov     r14d, eax
0x1800b7e73  test    ebx, ebx
0x1800b7e75  jz      loc_1800B7F1E
0x1800b7e7b  lea     rcx, [rdi+160h]
0x1800b7e82  call    cs:__imp_?IsScrollable@BaseScrollBar@DirectUI@@QEAA_NXZ; DirectUI::BaseScrollBar::IsScrollable(void)
0x1800b7e88  movzx   ebx, al
0x1800b7e8b  cmp     ebp, 2
0x1800b7e8e  jz      loc_1800B7F5C
0x1800b7e94  test    ebp, ebp
0x1800b7e96  jnz     loc_1800B7F1E
0x1800b7e9c  mov     ebp, 1
0x1800b7ea1  test    al, al
0x1800b7ea3  jnz     short loc_1800B7EAF
0x1800b7ea5  cmp     r14d, 0FFFFFFFDh
0x1800b7ea9  jnz     loc_1800B7F36
0x1800b7eaf  mov     rdx, cs:__imp_?EnabledProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::EnabledProp(void)
0x1800b7eb6  mov     rcx, rdi
0x1800b7eb9  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x1800b7ebf  test    ebx, ebx
0x1800b7ec1  jnz     short loc_1800B7F2E
0x1800b7ec3  xor     edx, edx
0x1800b7ec5  lea     ecx, [rbx-3]
0x1800b7ec8  call    cs:__imp_?CreateInt@Value@DirectUI@@SAPEAV12@HW4DynamicScaleValue@@@Z; DirectUI::Value::CreateInt(int,DynamicScaleValue)
0x1800b7ece  mov     rbx, rax
0x1800b7ed1  test    rax, rax
0x1800b7ed4  jz      short loc_1800B7EF5
0x1800b7ed6  mov     rdx, cs:__imp_?LayoutPosProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::LayoutPosProp(void)
0x1800b7edd  mov     r9, rax
0x1800b7ee0  mov     r8d, ebp
0x1800b7ee3  mov     rcx, rdi
0x1800b7ee6  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x1800b7eec  mov     rcx, rbx
0x1800b7eef  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800b7ef5  mov     rcx, rdi
0x1800b7ef8  call    cs:__imp_?GetLayoutPos@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetLayoutPos(void)
0x1800b7efe  xor     edx, edx
0x1800b7f00  cmp     eax, 0FFFFFFFDh
0x1800b7f03  setz    dl
0x1800b7f06  xor     ecx, ecx
0x1800b7f08  cmp     r14d, 0FFFFFFFDh
0x1800b7f0c  setnz   cl
0x1800b7f0f  xor     edx, ecx
0x1800b7f11  mov     eax, edx
0x1800b7f13  add     rsp, 20h
0x1800b7f17  pop     r14
0x1800b7f19  pop     rdi
0x1800b7f1a  pop     rsi
0x1800b7f1b  pop     rbp
0x1800b7f1c  pop     rbx
0x1800b7f1d  retn
0x1800b7f1e  mov     edx, 0FFFFFFFDh
0x1800b7f23  mov     rcx, rdi
0x1800b7f26  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x1800b7f2c  jmp     short loc_1800B7EF5
0x1800b7f2e  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x1800b7f34  jmp     short loc_1800B7ECE
0x1800b7f36  mov     rcx, rsi
0x1800b7f39  call    cs:__imp_?_GetChangesUpdatePass@Element@DirectUI@@QEAAHXZ; DirectUI::Element::_GetChangesUpdatePass(void)
0x1800b7f3f  cmp     eax, [rsi+264h]
0x1800b7f45  jnz     short loc_1800B7F9C
0x1800b7f47  add     [rsi+268h], ebp
0x1800b7f4d  cmp     dword ptr [rsi+268h], 4
0x1800b7f54  cmovg   ebx, ebp
0x1800b7f57  jmp     loc_1800B7EAF
0x1800b7f5c  mov     rdx, cs:__imp_?LayoutPosProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::LayoutPosProp(void)
0x1800b7f63  mov     rcx, rdi
0x1800b7f66  call    cs:__imp_?RemoveLocalValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZ@Z; DirectUI::Element::RemoveLocalValue(DirectUI::PropertyInfo const * (*)(void))
0x1800b7f6c  test    ebx, ebx
0x1800b7f6e  jz      short loc_1800B7F78
0x1800b7f70  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x1800b7f76  jmp     short loc_1800B7F7E
0x1800b7f78  call    cs:__imp_?GetBoolFalse@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetBoolFalse(void)
0x1800b7f7e  mov     rdx, cs:__imp_?EnabledProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::EnabledProp(void)
0x1800b7f85  mov     r9, rax
0x1800b7f88  mov     r8d, 1
0x1800b7f8e  mov     rcx, rdi
0x1800b7f91  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x1800b7f97  jmp     loc_1800B7EF5
0x1800b7f9c  mov     [rsi+264h], eax
0x1800b7fa2  mov     dword ptr [rsi+268h], 0
0x1800b7fac  jmp     short loc_1800B7F47
```
