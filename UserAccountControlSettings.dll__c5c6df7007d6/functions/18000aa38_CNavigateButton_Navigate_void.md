# CNavigateButton::_Navigate(void)

- ea: `0x18000aa38`
- end: `0x18000ab3a`
- name: `?_Navigate@CNavigateButton@@AEAAXXZ`
- size: `258`
- prototype: `void __fastcall(struct IUnknown **this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000a4a0`

## callees

- `0x18000a278`
- `0x18000aa38`

## import_xrefs

- `SHLWAPI!__imp_StrCmpICW` at `0x18000aaef`
- `SHLWAPI!__imp_StrCmpICW` at `0x18000aaef`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18000aa72`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18000aaa6`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18000aada`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18000aa72`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18000aaa6`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18000aada`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18000aa64`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18000aa98`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18000aacc`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18000aa64`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18000aa98`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18000aacc`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18000aa5b`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18000aa8f`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18000aac3`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18000aa5b`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18000aa8f`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18000aac3`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000ab13`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000ab1c`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000ab13`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000ab1c`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000ab33`

## pseudocode

```c
void __fastcall CNavigateButton::_Navigate(struct IUnknown **this)
{
  unsigned __int8 v2; // bl
  DirectUI::Value *Value; // r14
  const unsigned __int16 *String; // rsi
  DirectUI::Value *v5; // r15
  const unsigned __int16 *v6; // rbp
  DirectUI::Value *v7; // r12
  const WCHAR *v8; // rax

  v2 = 1;
  Value = DirectUI::Element::GetValue(
            (DirectUI::Element *)this,
            (const struct DirectUI::PropertyInfo *)&off_1800150C8,
            1,
            0);
  if ( Value == (DirectUI::Value *)DirectUI::Value::GetUnset() )
    String = 0;
  else
    String = DirectUI::Value::GetString(Value);
  v5 = DirectUI::Element::GetValue(
         (DirectUI::Element *)this,
         (const struct DirectUI::PropertyInfo *)&off_1800150F8,
         1,
         0);
  if ( v5 == (DirectUI::Value *)DirectUI::Value::GetUnset() )
    v6 = 0;
  else
    v6 = DirectUI::Value::GetString(v5);
  v7 = DirectUI::Element::GetValue(
         (DirectUI::Element *)this,
         (const struct DirectUI::PropertyInfo *)&off_180015128,
         1,
         0);
  if ( v7 == (DirectUI::Value *)DirectUI::Value::GetUnset()
    || (v8 = DirectUI::Value::GetString(v7)) == 0
    || StrCmpICW(v8, L"true") )
  {
    v2 = 0;
  }
  CNavigateButton::Navigate(String, v6, this[27], v2);
  DirectUI::Value::Release(Value);
  DirectUI::Value::Release(v5);
  DirectUI::Value::Release(v7);
}

```

## disassembly

```asm
0x18000aa38  push    rbx
0x18000aa3a  push    rbp
0x18000aa3b  push    rsi
0x18000aa3c  push    rdi
0x18000aa3d  push    r12
0x18000aa3f  push    r14
0x18000aa41  push    r15
0x18000aa43  sub     rsp, 20h
0x18000aa47  xor     r9d, r9d
0x18000aa4a  lea     rdx, off_1800150C8; "navigationtargetroot"
0x18000aa51  mov     rdi, rcx
0x18000aa54  lea     ebx, [r9+1]
0x18000aa58  mov     r8d, ebx
0x18000aa5b  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18000aa61  mov     r14, rax
0x18000aa64  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x18000aa6a  cmp     r14, rax
0x18000aa6d  jz      short loc_18000AA7D
0x18000aa6f  mov     rcx, r14
0x18000aa72  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x18000aa78  mov     rsi, rax
0x18000aa7b  jmp     short loc_18000AA7F
0x18000aa7d  xor     esi, esi
0x18000aa7f  xor     r9d, r9d
0x18000aa82  lea     rdx, off_1800150F8; "navigationtargetrelative"
0x18000aa89  mov     r8d, ebx
0x18000aa8c  mov     rcx, rdi
0x18000aa8f  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18000aa95  mov     r15, rax
0x18000aa98  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x18000aa9e  cmp     r15, rax
0x18000aaa1  jz      short loc_18000AAB1
0x18000aaa3  mov     rcx, r15
0x18000aaa6  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x18000aaac  mov     rbp, rax
0x18000aaaf  jmp     short loc_18000AAB3
0x18000aab1  xor     ebp, ebp
0x18000aab3  xor     r9d, r9d
0x18000aab6  lea     rdx, off_180015128; "nobackstack"
0x18000aabd  mov     r8d, ebx
0x18000aac0  mov     rcx, rdi
0x18000aac3  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18000aac9  mov     r12, rax
0x18000aacc  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x18000aad2  cmp     r12, rax
0x18000aad5  jz      short loc_18000AAF9
0x18000aad7  mov     rcx, r12
0x18000aada  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x18000aae0  test    rax, rax
0x18000aae3  jz      short loc_18000AAF9
0x18000aae5  lea     rdx, pszStr2; "true"
0x18000aaec  mov     rcx, rax; pszStr1
0x18000aaef  call    cs:__imp_StrCmpICW
0x18000aaf5  test    eax, eax
0x18000aaf7  jz      short loc_18000AAFB
0x18000aaf9  xor     bl, bl
0x18000aafb  mov     r8, [rdi+0D8h]; struct IUnknown *
0x18000ab02  mov     r9b, bl; bool
0x18000ab05  mov     rdx, rbp; unsigned __int16 *
0x18000ab08  mov     rcx, rsi; unsigned __int16 *
0x18000ab0b  call    ?Navigate@CNavigateButton@@SAXPEBG0PEAUIUnknown@@_N@Z; CNavigateButton::Navigate(ushort const *,ushort const *,IUnknown *,bool)
0x18000ab10  mov     rcx, r14
0x18000ab13  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18000ab19  mov     rcx, r15
0x18000ab1c  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18000ab22  mov     rcx, r12
0x18000ab25  add     rsp, 20h
0x18000ab29  pop     r15
0x18000ab2b  pop     r14
0x18000ab2d  pop     r12
0x18000ab2f  pop     rdi
0x18000ab30  pop     rsi
0x18000ab31  pop     rbp
0x18000ab32  pop     rbx
0x18000ab33  jmp     cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
```
