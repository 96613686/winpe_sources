# _BrandContentWorker(DirectUI::Element *,DirectUI::PropertyInfo const *)

- ea: `0x18000f47c`
- end: `0x18000f52e`
- name: `?_BrandContentWorker@@YAXPEAVElement@DirectUI@@PEBUPropertyInfo@2@@Z`
- size: `178`
- prototype: `void __fastcall(struct DirectUI::Element *, const struct DirectUI::PropertyInfo *)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000f3d0`

## callees

- `0x18000f47c`

## import_xrefs

- `SHLWAPI!StrChrW` at `0x18000f4c4`
- `SHLWAPI!StrChrW` at `0x18000f4c4`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000f514`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000f514`
- `WINBRAND!BrandingFormatString` at `0x18000f4d2`
- `WINBRAND!BrandingFormatString` at `0x18000f4d2`
- `DUI70!?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z` at `0x18000f4e5`
- `DUI70!?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z` at `0x18000f4e5`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18000f494`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18000f494`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z` at `0x18000f502`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z` at `0x18000f502`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000f50b`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000f50b`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000f527`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18000f4ae`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18000f4ae`
- `DUI70!?GetType@Value@DirectUI@@QEBAHXZ` at `0x18000f4a0`
- `DUI70!?GetType@Value@DirectUI@@QEBAHXZ` at `0x18000f4a0`

## pseudocode

```c
void __fastcall _BrandContentWorker(struct DirectUI::Element *a1, const struct DirectUI::PropertyInfo *a2)
{
  DirectUI::Value *Value; // rsi
  const WCHAR *String; // rax
  const WCHAR *v6; // rbx
  const unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // rbx
  struct DirectUI::Value *v9; // rax
  DirectUI::Value *v10; // rdi

  Value = DirectUI::Element::GetValue(a1, a2, 2, 0);
  if ( DirectUI::Value::GetType(Value) == 5 )
  {
    String = DirectUI::Value::GetString(Value);
    v6 = String;
    if ( String )
    {
      if ( StrChrW(String, 0x25u) )
      {
        v7 = (const unsigned __int16 *)BrandingFormatString(v6);
        v8 = (unsigned __int16 *)v7;
        if ( v7 )
        {
          v9 = DirectUI::Value::CreateString(v7, 0);
          v10 = v9;
          if ( v9 )
          {
            DirectUI::Element::SetValue(a1, a2, 1, v9);
            DirectUI::Value::Release(v10);
          }
          GlobalFree(v8);
        }
      }
    }
  }
  DirectUI::Value::Release(Value);
}

```

## disassembly

```asm
0x18000f47c  push    rbx
0x18000f47e  push    rbp
0x18000f47f  push    rsi
0x18000f480  push    rdi
0x18000f481  push    r14
0x18000f483  sub     rsp, 20h
0x18000f487  xor     r9d, r9d
0x18000f48a  mov     rbp, rdx
0x18000f48d  mov     r14, rcx
0x18000f490  lea     r8d, [r9+2]
0x18000f494  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18000f49a  mov     rcx, rax
0x18000f49d  mov     rsi, rax
0x18000f4a0  call    cs:__imp_?GetType@Value@DirectUI@@QEBAHXZ; DirectUI::Value::GetType(void)
0x18000f4a6  cmp     eax, 5
0x18000f4a9  jnz     short loc_18000F51A
0x18000f4ab  mov     rcx, rsi
0x18000f4ae  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x18000f4b4  mov     rbx, rax
0x18000f4b7  test    rax, rax
0x18000f4ba  jz      short loc_18000F51A
0x18000f4bc  mov     edx, 25h ; '%'; wMatch
0x18000f4c1  mov     rcx, rax; pszStart
0x18000f4c4  call    cs:__imp_StrChrW
0x18000f4ca  test    rax, rax
0x18000f4cd  jz      short loc_18000F51A
0x18000f4cf  mov     rcx, rbx
0x18000f4d2  call    cs:__imp_BrandingFormatString
0x18000f4d8  mov     rbx, rax
0x18000f4db  test    rax, rax
0x18000f4de  jz      short loc_18000F51A
0x18000f4e0  xor     edx, edx
0x18000f4e2  mov     rcx, rax
0x18000f4e5  call    cs:__imp_?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z; DirectUI::Value::CreateString(ushort const *,HINSTANCE__ *)
0x18000f4eb  mov     rdi, rax
0x18000f4ee  test    rax, rax
0x18000f4f1  jz      short loc_18000F511
0x18000f4f3  mov     r9, rax
0x18000f4f6  mov     r8d, 1
0x18000f4fc  mov     rdx, rbp
0x18000f4ff  mov     rcx, r14
0x18000f502  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const *,int,DirectUI::Value *)
0x18000f508  mov     rcx, rdi
0x18000f50b  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18000f511  mov     rcx, rbx; hMem
0x18000f514  call    cs:__imp_GlobalFree
0x18000f51a  mov     rcx, rsi
0x18000f51d  add     rsp, 20h
0x18000f521  pop     r14
0x18000f523  pop     rdi
0x18000f524  pop     rsi
0x18000f525  pop     rbp
0x18000f526  pop     rbx
0x18000f527  jmp     cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
```
