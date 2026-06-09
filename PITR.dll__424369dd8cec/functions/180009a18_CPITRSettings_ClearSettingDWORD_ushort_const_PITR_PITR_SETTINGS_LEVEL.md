# CPITRSettings::ClearSettingDWORD(ushort const *,PITR::PITR_SETTINGS_LEVEL)

- ea: `0x180009a18`
- end: `0x180009b26`
- name: `?ClearSettingDWORD@CPITRSettings@@IEAAJPEBGW4PITR_SETTINGS_LEVEL@PITR@@@Z`
- size: `270`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, int)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180009980`
- `0x1800099a0`
- `0x1800099c0`
- `0x1800099e0`
- `0x180009a00`
- `0x180009b30`

## callees

- `0x180009a18`
- `0x18000f50c`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180009acd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180009acd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009abb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009ade`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009abb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009ade`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ae8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ae8`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180009aa7`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180009aa7`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180009a66`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180009a66`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180009a3d`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180009a3d`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180009a83`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180009b09`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180009a83`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180009b09`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180009a77`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180009a77`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180009a9e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180009a9e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180009a8e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180009a8e`

## pseudocode

```c
__int64 __fastcall CPITRSettings::ClearSettingDWORD(__int64 a1, const unsigned __int16 *a2, int a3)
{
  __int64 v6; // rcx
  unsigned int v7; // ebx
  __int64 SettingValueName; // rax
  UnBCL::String *v9; // rax
  const WCHAR *CString; // rax
  HKEY v11; // rcx
  LSTATUS v12; // edi
  signed int LastError; // eax
  _BYTE v15[16]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v16[16]; // [rsp+30h] [rbp-38h] BYREF

  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v16);
  if ( a3 <= 1 )
  {
    v7 = -2147024846;
    goto LABEL_13;
  }
  SettingValueName = CPITRSettings::GetSettingValueName(v6, a2, a3);
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v15, SettingValueName);
  UnBCL::SmartPtr<UnBCL::String>::operator=(v16, v15);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v15);
  if ( !UnBCL::SmartPtr<UnBCL::String>::get_P(v16) )
  {
    v7 = -2147024809;
    goto LABEL_13;
  }
  v9 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v16);
  CString = UnBCL::String::get_CString(v9);
  v11 = *(HKEY *)(a1 + 32);
  if ( !v11 )
  {
    SetLastError(0x57u);
LABEL_10:
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_13;
  }
  v7 = 0;
  if ( CString )
    v12 = RegDeleteValueW(v11, CString);
  else
    v12 = 87;
  SetLastError(v12);
  if ( v12 )
    goto LABEL_10;
LABEL_13:
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v16);
  return v7;
}

```

## disassembly

```asm
0x180009a18  push    rbx
0x180009a1a  push    rsi
0x180009a1b  push    rdi
0x180009a1c  sub     rsp, 50h
0x180009a20  mov     rax, cs:__security_cookie
0x180009a27  xor     rax, rsp
0x180009a2a  mov     [rsp+68h+var_28], rax
0x180009a2f  mov     ebx, r8d
0x180009a32  mov     rsi, rdx
0x180009a35  mov     rdi, rcx
0x180009a38  lea     rcx, [rsp+68h+var_38]
0x180009a3d  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x180009a43  nop
0x180009a44  cmp     ebx, 1
0x180009a47  jg      short loc_180009A53
0x180009a49  mov     ebx, 80070032h
0x180009a4e  jmp     loc_180009B04
0x180009a53  mov     r8d, ebx
0x180009a56  mov     rdx, rsi
0x180009a59  call    ?GetSettingValueName@CPITRSettings@@IEAAPEAVString@UnBCL@@PEBGW4PITR_SETTINGS_LEVEL@PITR@@@Z; CPITRSettings::GetSettingValueName(ushort const *,PITR::PITR_SETTINGS_LEVEL)
0x180009a5e  mov     rdx, rax
0x180009a61  lea     rcx, [rsp+68h+var_48]
0x180009a66  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180009a6c  nop
0x180009a6d  lea     rdx, [rsp+68h+var_48]
0x180009a72  lea     rcx, [rsp+68h+var_38]
0x180009a77  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180009a7d  nop
0x180009a7e  lea     rcx, [rsp+68h+var_48]
0x180009a83  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180009a89  lea     rcx, [rsp+68h+var_38]
0x180009a8e  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180009a94  test    rax, rax
0x180009a97  jz      short loc_180009AFF
0x180009a99  lea     rcx, [rsp+68h+var_38]
0x180009a9e  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180009aa4  mov     rcx, rax
0x180009aa7  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180009aad  mov     rcx, [rdi+20h]; hKey
0x180009ab1  test    rcx, rcx
0x180009ab4  jnz     short loc_180009AC3
0x180009ab6  mov     ecx, 57h ; 'W'; dwErrCode
0x180009abb  call    cs:__imp_SetLastError
0x180009ac1  jmp     short loc_180009AE8
0x180009ac3  xor     ebx, ebx
0x180009ac5  test    rax, rax
0x180009ac8  jz      short loc_180009AD7
0x180009aca  mov     rdx, rax; lpValueName
0x180009acd  call    cs:__imp_RegDeleteValueW
0x180009ad3  mov     edi, eax
0x180009ad5  jmp     short loc_180009ADC
0x180009ad7  mov     edi, 57h ; 'W'
0x180009adc  mov     ecx, edi; dwErrCode
0x180009ade  call    cs:__imp_SetLastError
0x180009ae4  test    edi, edi
0x180009ae6  jz      short loc_180009B04
0x180009ae8  call    cs:__imp_GetLastError
0x180009aee  mov     ebx, eax
0x180009af0  test    eax, eax
0x180009af2  jle     short loc_180009B04
0x180009af4  movzx   ebx, ax
0x180009af7  or      ebx, 80070000h
0x180009afd  jmp     short loc_180009B04
0x180009aff  mov     ebx, 80070057h
0x180009b04  lea     rcx, [rsp+68h+var_38]
0x180009b09  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180009b0f  mov     eax, ebx
0x180009b11  mov     rcx, [rsp+68h+var_28]
0x180009b16  xor     rcx, rsp; StackCookie
0x180009b19  call    __security_check_cookie
0x180009b1e  add     rsp, 50h
0x180009b22  pop     rdi
0x180009b23  pop     rsi
0x180009b24  pop     rbx
0x180009b25  retn
```
