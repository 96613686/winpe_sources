# CheckAndUpdateWMI(void)

- ea: `0x140004e24`
- end: `0x140004f19`
- name: `?CheckAndUpdateWMI@@YAJXZ`
- size: `245`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140005ad0`

## callees

- `0x140003320`
- `0x140004e24`
- `0x140005560`
- `0x140005810`
- `0x140014ad0`

## import_xrefs

- `wbemcomn!??0WString@@QEAA@XZ` at `0x140004e43`
- `wbemcomn!??0WString@@QEAA@XZ` at `0x140004e43`
- `wbemcomn!?DeleteString@WString@@AEAAXPEAG@Z` at `0x140004efa`
- `wbemcomn!?DeleteString@WString@@AEAAXPEAG@Z` at `0x140004efa`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x140004e66`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetSystemDefaultUILanguage` at `0x140004e66`

## pseudocode

```c
__int64 CheckAndUpdateWMI(void)
{
  LANGID SystemDefaultUILanguage; // bx
  int NamespaceName; // ebx
  unsigned __int16 *v3; // [rsp+20h] [rbp-40h] BYREF
  struct IWbemServices *v4; // [rsp+28h] [rbp-38h] BYREF
  unsigned __int16 v5[8]; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int16 v6[8]; // [rsp+40h] [rbp-20h] BYREF

  WString::WString((WString *)&v3);
  if ( (int)GetNamespaceName(0, (struct WString *)&v3) >= 0 )
    CWMIBroker::GetNamespace((const struct WString *)&v3, &v4);
  SystemDefaultUILanguage = GetSystemDefaultUILanguage();
  if ( SystemDefaultUILanguage != 1033 )
  {
    StringCchPrintfW(v5, 8u, L"%03x");
    if ( (int)GetNamespaceName(v5, (struct WString *)&v3) >= 0 )
      CWMIBroker::GetNamespace((const struct WString *)&v3, &v4);
  }
  StringCchPrintfW(v6, 8u, L"%03x", SystemDefaultUILanguage & 0x3FF);
  NamespaceName = GetNamespaceName(v6, (struct WString *)&v3);
  if ( NamespaceName >= 0 )
    NamespaceName = CWMIBroker::GetNamespace((const struct WString *)&v3, &v4);
  WString::DeleteString((WString *)&v3, v3);
  return (unsigned int)NamespaceName;
}

```

## disassembly

```asm
0x140004e24  mov     [rsp-8+arg_0], rbx
0x140004e29  push    rbp
0x140004e2a  mov     rbp, rsp
0x140004e2d  sub     rsp, 60h
0x140004e31  mov     rax, cs:__security_cookie
0x140004e38  xor     rax, rsp
0x140004e3b  mov     [rbp+var_10], rax
0x140004e3f  lea     rcx, [rbp+var_40]
0x140004e43  call    cs:__imp_??0WString@@QEAA@XZ; WString::WString(void)
0x140004e49  nop
0x140004e4a  lea     rdx, [rbp+var_40]; struct WString *
0x140004e4e  xor     ecx, ecx; unsigned __int16 *
0x140004e50  call    ?GetNamespaceName@@YAJPEAGAEAVWString@@@Z; GetNamespaceName(ushort *,WString &)
0x140004e55  test    eax, eax
0x140004e57  js      short loc_140004E66
0x140004e59  lea     rdx, [rbp+var_38]; struct IWbemServices **
0x140004e5d  lea     rcx, [rbp+var_40]; struct WString *
0x140004e61  call    ?GetNamespace@CWMIBroker@@SAJAEBVWString@@PEAPEAUIWbemServices@@@Z; CWMIBroker::GetNamespace(WString const &,IWbemServices * *)
0x140004e66  call    cs:__imp_GetSystemDefaultUILanguage
0x140004e6c  movzx   ebx, ax
0x140004e6f  mov     eax, 409h
0x140004e74  cmp     ax, bx
0x140004e77  jz      short loc_140004EB1
0x140004e79  mov     r9d, 9
0x140004e7f  lea     r8, a03x; "%03x"
0x140004e86  lea     edx, [r9-1]; unsigned __int64
0x140004e8a  lea     rcx, [rbp+var_30]; unsigned __int16 *
0x140004e8e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140004e93  lea     rdx, [rbp+var_40]; struct WString *
0x140004e97  lea     rcx, [rbp+var_30]; unsigned __int16 *
0x140004e9b  call    ?GetNamespaceName@@YAJPEAGAEAVWString@@@Z; GetNamespaceName(ushort *,WString &)
0x140004ea0  test    eax, eax
0x140004ea2  js      short loc_140004EB1
0x140004ea4  lea     rdx, [rbp+var_38]; struct IWbemServices **
0x140004ea8  lea     rcx, [rbp+var_40]; struct WString *
0x140004eac  call    ?GetNamespace@CWMIBroker@@SAJAEBVWString@@PEAPEAUIWbemServices@@@Z; CWMIBroker::GetNamespace(WString const &,IWbemServices * *)
0x140004eb1  mov     r9d, ebx
0x140004eb4  and     r9d, 3FFh
0x140004ebb  lea     r8, a03x; "%03x"
0x140004ec2  mov     edx, 8; unsigned __int64
0x140004ec7  lea     rcx, [rbp+var_20]; unsigned __int16 *
0x140004ecb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140004ed0  lea     rdx, [rbp+var_40]; struct WString *
0x140004ed4  lea     rcx, [rbp+var_20]; unsigned __int16 *
0x140004ed8  call    ?GetNamespaceName@@YAJPEAGAEAVWString@@@Z; GetNamespaceName(ushort *,WString &)
0x140004edd  mov     ebx, eax
0x140004edf  test    eax, eax
0x140004ee1  js      short loc_140004EF2
0x140004ee3  lea     rdx, [rbp+var_38]; struct IWbemServices **
0x140004ee7  lea     rcx, [rbp+var_40]; struct WString *
0x140004eeb  call    ?GetNamespace@CWMIBroker@@SAJAEBVWString@@PEAPEAUIWbemServices@@@Z; CWMIBroker::GetNamespace(WString const &,IWbemServices * *)
0x140004ef0  mov     ebx, eax
0x140004ef2  mov     rdx, [rbp+var_40]
0x140004ef6  lea     rcx, [rbp+var_40]
0x140004efa  call    cs:__imp_?DeleteString@WString@@AEAAXPEAG@Z; WString::DeleteString(ushort *)
0x140004f00  mov     eax, ebx
0x140004f02  mov     rcx, [rbp+var_10]
0x140004f06  xor     rcx, rsp; StackCookie
0x140004f09  call    __security_check_cookie
0x140004f0e  mov     rbx, [rsp+60h+arg_0]
0x140004f13  add     rsp, 60h
0x140004f17  pop     rbp
0x140004f18  retn
```
