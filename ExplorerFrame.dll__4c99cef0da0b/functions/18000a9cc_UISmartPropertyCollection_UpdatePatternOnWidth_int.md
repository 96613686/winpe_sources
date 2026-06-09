# UISmartPropertyCollection::_UpdatePatternOnWidth(int)

- ea: `0x18000a9cc`
- end: `0x18000ab10`
- name: `?_UpdatePatternOnWidth@UISmartPropertyCollection@@AEAAXH@Z`
- size: `324`
- prototype: `void __fastcall(UISmartPropertyCollection *__hidden this, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000af60`

## callees

- `0x1800099cc`
- `0x18000a9cc`
- `0x18000e480`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000aa62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000aaf7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000aa62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000aaf7`
- `DUI70!?HasChildren@Element@DirectUI@@QEAA_NXZ` at `0x18000a9e3`
- `DUI70!?HasChildren@Element@DirectUI@@QEAA_NXZ` at `0x18000a9e3`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x18000aacb`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x18000aacb`
- `DUI70!?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z` at `0x18000aaaa`
- `DUI70!?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z` at `0x18000aaaa`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000aad4`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000aaeb`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000aad4`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000aaeb`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18000aa57`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18000aa57`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18000aa46`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18000aa46`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall UISmartPropertyCollection::_UpdatePatternOnWidth(UISmartPropertyCollection *this, int a2)
{
  int *v4; // r14
  struct DirectUI::Value *Value; // rbx
  const unsigned __int16 *String; // rdi
  struct DirectUI::Value *v7; // rax
  DirectUI::Value *v8; // rdi
  LPVOID pv[5]; // [rsp+30h] [rbp-28h] BYREF
  int v10; // [rsp+70h] [rbp+18h] BYREF
  int v11; // [rsp+78h] [rbp+20h] BYREF

  if ( DirectUI::Element::HasChildren(this) )
  {
    v4 = (int *)((char *)this + 212);
    if ( a2 < *((_DWORD *)this + 52) || *v4 != -1 && a2 > *v4 )
    {
      pv[0] = 0;
      v10 = 0;
      v11 = 0;
      Value = DirectUI::Element::GetValue(this, UISmartPropertyCollection::WidthPatternMapProp, 2, 0);
      pv[1] = Value;
      String = DirectUI::Value::GetString(Value);
      CoTaskMemFree(0);
      if ( UISmartPropertyCollection::_GetWidthPatternForSize(this, a2, String, (unsigned __int16 **)pv, &v10, &v11) >= 0 )
      {
        *((_DWORD *)this + 52) = v10;
        *v4 = v11;
        v7 = DirectUI::Value::CreateString((const unsigned __int16 *)pv[0], 0);
        v8 = v7;
        if ( v7 )
        {
          DirectUI::Element::SetValue(this, UISmartPropertyCollection::PropWidthPatternProp, 1, v7);
          DirectUI::Value::Release(v8);
        }
        UISmartPropertyCollection::_UpdateUIProperties(this);
      }
      if ( Value )
        DirectUI::Value::Release(Value);
      CoTaskMemFree(pv[0]);
    }
  }
}

```

## disassembly

```asm
0x18000a9cc  mov     [rsp+arg_0], rbx
0x18000a9d1  mov     [rsp+arg_8], rbp
0x18000a9d6  push    rsi
0x18000a9d7  push    rdi
0x18000a9d8  push    r14
0x18000a9da  sub     rsp, 40h
0x18000a9de  mov     ebp, edx
0x18000a9e0  mov     rsi, rcx
0x18000a9e3  call    cs:__imp_?HasChildren@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::HasChildren(void)
0x18000a9e9  test    al, al
0x18000a9eb  jz      loc_18000AAFD
0x18000a9f1  lea     r14, [rsi+0D4h]
0x18000a9f8  cmp     ebp, [rsi+0D0h]
0x18000a9fe  jl      short loc_18000AA13
0x18000aa00  cmp     dword ptr [r14], 0FFFFFFFFh
0x18000aa04  jz      loc_18000AAFD
0x18000aa0a  cmp     ebp, [r14]
0x18000aa0d  jle     loc_18000AAFD
0x18000aa13  mov     [rsp+58h+pv], 0
0x18000aa1c  mov     [rsp+58h+arg_10], 0
0x18000aa24  mov     [rsp+58h+arg_18], 0
0x18000aa2c  mov     [rsp+58h+var_20], 0
0x18000aa35  xor     r9d, r9d
0x18000aa38  lea     r8d, [r9+2]
0x18000aa3c  lea     rdx, ?WidthPatternMapProp@UISmartPropertyCollection@@SAPEBUPropertyInfo@DirectUI@@XZ; UISmartPropertyCollection::WidthPatternMapProp(void)
0x18000aa43  mov     rcx, rsi
0x18000aa46  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x18000aa4c  mov     rbx, rax
0x18000aa4f  mov     [rsp+58h+var_20], rax
0x18000aa54  mov     rcx, rax
0x18000aa57  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x18000aa5d  mov     rdi, rax
0x18000aa60  xor     ecx, ecx; pv
0x18000aa62  call    cs:__imp_CoTaskMemFree
0x18000aa68  lea     rax, [rsp+58h+arg_18]
0x18000aa6d  mov     [rsp+58h+var_30], rax; int *
0x18000aa72  lea     rax, [rsp+58h+arg_10]
0x18000aa77  mov     [rsp+58h+var_38], rax; int *
0x18000aa7c  lea     r9, [rsp+58h+pv]; unsigned __int16 **
0x18000aa81  mov     r8, rdi; unsigned __int16 *
0x18000aa84  mov     edx, ebp; int
0x18000aa86  mov     rcx, rsi; this
0x18000aa89  call    ?_GetWidthPatternForSize@UISmartPropertyCollection@@AEAAJHPEBGPEAPEAGPEAH2@Z; UISmartPropertyCollection::_GetWidthPatternForSize(int,ushort const *,ushort * *,int *,int *)
0x18000aa8e  test    eax, eax
0x18000aa90  js      short loc_18000AAE3
0x18000aa92  mov     eax, [rsp+58h+arg_10]
0x18000aa96  mov     [rsi+0D0h], eax
0x18000aa9c  mov     eax, [rsp+58h+arg_18]
0x18000aaa0  mov     [r14], eax
0x18000aaa3  xor     edx, edx
0x18000aaa5  mov     rcx, [rsp+58h+pv]
0x18000aaaa  call    cs:__imp_?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z; DirectUI::Value::CreateString(ushort const *,HINSTANCE__ *)
0x18000aab0  mov     rdi, rax
0x18000aab3  test    rax, rax
0x18000aab6  jz      short loc_18000AADA
0x18000aab8  mov     r9, rax
0x18000aabb  mov     r8d, 1
0x18000aac1  lea     rdx, ?PropWidthPatternProp@UISmartPropertyCollection@@SAPEBUPropertyInfo@DirectUI@@XZ; UISmartPropertyCollection::PropWidthPatternProp(void)
0x18000aac8  mov     rcx, rsi
0x18000aacb  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x18000aad1  mov     rcx, rdi
0x18000aad4  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18000aada  mov     rcx, rsi; this
0x18000aadd  call    ?_UpdateUIProperties@UISmartPropertyCollection@@AEAAXXZ; UISmartPropertyCollection::_UpdateUIProperties(void)
0x18000aae2  nop
0x18000aae3  test    rbx, rbx
0x18000aae6  jz      short loc_18000AAF2
0x18000aae8  mov     rcx, rbx
0x18000aaeb  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18000aaf1  nop
0x18000aaf2  mov     rcx, [rsp+58h+pv]; pv
0x18000aaf7  call    cs:__imp_CoTaskMemFree
0x18000aafd  mov     rbx, [rsp+58h+arg_0]
0x18000ab02  mov     rbp, [rsp+58h+arg_8]
0x18000ab07  add     rsp, 40h
0x18000ab0b  pop     r14
0x18000ab0d  pop     rdi
0x18000ab0e  pop     rsi
0x18000ab0f  retn
```
