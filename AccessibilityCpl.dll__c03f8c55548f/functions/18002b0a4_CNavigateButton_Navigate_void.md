# CNavigateButton::_Navigate(void)

- ea: `0x18002b0a4`
- end: `0x18002b1a6`
- name: `?_Navigate@CNavigateButton@@AEAAXXZ`
- size: `258`
- prototype: `void(CNavigateButton *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18002ab60`

## callees

- `0x18002a940`
- `0x18002b0a4`

## import_xrefs

- `SHLWAPI!__imp_StrCmpICW` at `0x18002b15b`
- `SHLWAPI!__imp_StrCmpICW` at `0x18002b15b`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18002b0c7`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18002b0fb`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18002b12f`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18002b0c7`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18002b0fb`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18002b12f`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18002b0de`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18002b112`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18002b146`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18002b0de`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18002b112`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18002b146`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18002b0d0`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18002b104`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18002b138`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18002b0d0`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18002b104`
- `DUI70!?GetUnset@Value@DirectUI@@SAPEAV12@XZ` at `0x18002b138`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18002b17f`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18002b188`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18002b17f`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18002b188`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18002b19f`

## pseudocode

```c
void __fastcall CNavigateButton::_Navigate(struct IUnknown **this)
{
  bool v2; // bl
  DirectUI::Value *Value; // r14
  const unsigned __int16 *String; // rsi
  DirectUI::Value *v5; // r15
  const unsigned __int16 *v6; // rbp
  DirectUI::Value *v7; // r12
  const WCHAR *v8; // rax

  v2 = 1;
  Value = DirectUI::Element::GetValue(
            (DirectUI::Element *)this,
            (const struct DirectUI::PropertyInfo *)&off_180040600,
            1,
            0);
  if ( Value == (DirectUI::Value *)DirectUI::Value::GetUnset() )
    String = 0;
  else
    String = DirectUI::Value::GetString(Value);
  v5 = DirectUI::Element::GetValue(
         (DirectUI::Element *)this,
         (const struct DirectUI::PropertyInfo *)&off_180040630,
         1,
         0);
  if ( v5 == (DirectUI::Value *)DirectUI::Value::GetUnset() )
    v6 = 0;
  else
    v6 = DirectUI::Value::GetString(v5);
  v7 = DirectUI::Element::GetValue(
         (DirectUI::Element *)this,
         (const struct DirectUI::PropertyInfo *)&off_180040660,
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
0x18002b0a4  push    rbx
0x18002b0a6  push    rbp
0x18002b0a7  push    rsi
0x18002b0a8  push    rdi
0x18002b0a9  push    r12
0x18002b0ab  push    r14
0x18002b0ad  push    r15
0x18002b0af  sub     rsp, 20h
0x18002b0b3  xor     r9d, r9d
0x18002b0b6  lea     rdx, off_180040600; "navigationtargetroot"
0x18002b0bd  mov     rdi, rcx
0x18002b0c0  lea     ebx, [r9+1]
0x18002b0c4  mov     r8d, ebx
0x18002b0c7  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18002b0cd  mov     r14, rax
0x18002b0d0  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x18002b0d6  cmp     r14, rax
0x18002b0d9  jz      short loc_18002B0E9
0x18002b0db  mov     rcx, r14
0x18002b0de  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x18002b0e4  mov     rsi, rax
0x18002b0e7  jmp     short loc_18002B0EB
0x18002b0e9  xor     esi, esi
0x18002b0eb  xor     r9d, r9d
0x18002b0ee  lea     rdx, off_180040630; "navigationtargetrelative"
0x18002b0f5  mov     r8d, ebx
0x18002b0f8  mov     rcx, rdi
0x18002b0fb  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18002b101  mov     r15, rax
0x18002b104  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x18002b10a  cmp     r15, rax
0x18002b10d  jz      short loc_18002B11D
0x18002b10f  mov     rcx, r15
0x18002b112  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x18002b118  mov     rbp, rax
0x18002b11b  jmp     short loc_18002B11F
0x18002b11d  xor     ebp, ebp
0x18002b11f  xor     r9d, r9d
0x18002b122  lea     rdx, off_180040660; "nobackstack"
0x18002b129  mov     r8d, ebx
0x18002b12c  mov     rcx, rdi
0x18002b12f  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18002b135  mov     r12, rax
0x18002b138  call    cs:__imp_?GetUnset@Value@DirectUI@@SAPEAV12@XZ; DirectUI::Value::GetUnset(void)
0x18002b13e  cmp     r12, rax
0x18002b141  jz      short loc_18002B165
0x18002b143  mov     rcx, r12
0x18002b146  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x18002b14c  test    rax, rax
0x18002b14f  jz      short loc_18002B165
0x18002b151  lea     rdx, aTrue; "true"
0x18002b158  mov     rcx, rax; pszStr1
0x18002b15b  call    cs:__imp_StrCmpICW
0x18002b161  test    eax, eax
0x18002b163  jz      short loc_18002B167
0x18002b165  xor     bl, bl
0x18002b167  mov     r8, [rdi+0D8h]; struct IUnknown *
0x18002b16e  mov     r9b, bl; bool
0x18002b171  mov     rdx, rbp; unsigned __int16 *
0x18002b174  mov     rcx, rsi; unsigned __int16 *
0x18002b177  call    ?Navigate@CNavigateButton@@SAXPEBG0PEAUIUnknown@@_N@Z; CNavigateButton::Navigate(ushort const *,ushort const *,IUnknown *,bool)
0x18002b17c  mov     rcx, r14
0x18002b17f  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18002b185  mov     rcx, r15
0x18002b188  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18002b18e  mov     rcx, r12
0x18002b191  add     rsp, 20h
0x18002b195  pop     r15
0x18002b197  pop     r14
0x18002b199  pop     r12
0x18002b19b  pop     rdi
0x18002b19c  pop     rsi
0x18002b19d  pop     rbp
0x18002b19e  pop     rbx
0x18002b19f  jmp     cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
```
