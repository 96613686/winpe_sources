# HiveListEnumerator::UnloadHiveByNtPath(ushort const *,ushort const *,bool)

- ea: `0x180040488`
- end: `0x1800406b9`
- name: `?UnloadHiveByNtPath@HiveListEnumerator@@KA_NPEBG0_N@Z`
- size: `561`
- prototype: `bool __fastcall(wchar_t *String1, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, registry_config, installer_update`

## callers

- `0x18003f480`

## callees

- `0x180009e04`
- `0x180040488`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800404da`
- `msvcrt!_wcsnicmp` at `0x1800404da`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180040610`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180040610`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800405dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004061e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800405dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004061e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004056b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040624`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004056b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040624`
- `WDSCORE!CurrentIP` at `0x180040573`
- `WDSCORE!CurrentIP` at `0x18004062c`
- `WDSCORE!CurrentIP` at `0x180040573`
- `WDSCORE!CurrentIP` at `0x18004062c`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800405d2`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004068e`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800405d2`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004068e`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800404ed`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800404ed`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18004050e`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18004050e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180040604`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180040604`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18004052b`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18004052b`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1800404b1`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x1800404b1`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180040548`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800405e9`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18004069c`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180040548`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800405e9`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18004069c`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18004053c`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18004053c`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800405fb`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800405fb`

## string_xrefs

- `0x1800405a3`: `HiveListEnumerator::UnloadHiveByNtPath`
- `0x18004065f`: `HiveListEnumerator::UnloadHiveByNtPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall HiveListEnumerator::UnloadHiveByNtPath(wchar_t *String1, const unsigned __int16 *a2)
{
  char v3; // r14
  HKEY v4; // r12
  const UNICODE_STRING *v5; // rdi
  char v6; // bp
  const wchar_t *Buffer; // rdx
  size_t v8; // rsi
  UnBCL::String *v9; // rax
  UnBCL::String *v10; // rbx
  DWORD v11; // edi
  __int64 v12; // rbx
  struct tagLOG_PARTIAL_MSG *v13; // rax
  UnBCL::String *v15; // rax
  const WCHAR *CString; // rax
  LSTATUS KeyW; // eax
  LSTATUS v18; // esi
  DWORD LastError; // edi
  __int64 v20; // rbx
  struct tagLOG_PARTIAL_MSG *v21; // rax
  _BYTE v22[16]; // [rsp+60h] [rbp-68h] BYREF
  _BYTE v23[88]; // [rsp+70h] [rbp-58h] BYREF

  v3 = 0;
  v4 = 0;
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v22);
  v5 = (const UNICODE_STRING *)&qword_180057030;
  v6 = 1;
  do
  {
    Buffer = v5->Buffer;
    v8 = -1;
    do
      ++v8;
    while ( Buffer[v8] );
    if ( !_wcsnicmp(String1, Buffer, v8) )
    {
      v3 = 1;
      v4 = *(HKEY *)&v5->Length;
      v9 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
      v10 = v9;
      if ( v9 )
      {
        UnBCL::String::String(v9, &String1[v8 + 1]);
        *(_QWORD *)v10 = &UnBCL::String::`local vftable';
      }
      else
      {
        v10 = 0;
      }
      UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v23, v10);
      UnBCL::SmartPtr<UnBCL::String>::operator=(v22, v23);
      UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v23);
    }
    ++v5;
  }
  while ( v5 != &stru_180057050 );
  if ( v3 )
  {
    v15 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v22);
    CString = UnBCL::String::get_CString(v15);
    KeyW = RegUnLoadKeyW(v4, CString);
    v18 = KeyW;
    if ( KeyW )
    {
      SetLastError(KeyW);
      LastError = GetLastError();
      v20 = CurrentIP();
      v21 = ConstructPartialMsgW(0x2000000, "Failed to unload hive %s. Error %d", (const char *)String1, v18);
      WdsSetupLogMessageW(
        v21,
        0,
        L"D",
        0,
        296,
        L"base\\diagnosis\\srt\\srinfra\\recutil\\reg.cpp",
        L"HiveListEnumerator::UnloadHiveByNtPath",
        v20,
        LastError,
        0,
        0);
      v6 = 0;
    }
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v22);
    return v6;
  }
  else
  {
    v11 = GetLastError();
    v12 = CurrentIP();
    v13 = ConstructPartialMsgW(0x2000000, "Unsupported root key for hive %s", (const char *)String1);
    WdsSetupLogMessageW(
      v13,
      0,
      L"D",
      0,
      287,
      L"base\\diagnosis\\srt\\srinfra\\recutil\\reg.cpp",
      L"HiveListEnumerator::UnloadHiveByNtPath",
      v12,
      v11,
      0,
      0);
    SetLastError(0x57u);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v22);
    return 0;
  }
}

```

## disassembly

```asm
0x180040488  mov     [rsp+arg_8], rdx
0x18004048d  push    rbx
0x18004048e  push    rbp
0x18004048f  push    rsi
0x180040490  push    rdi
0x180040491  push    r12
0x180040493  push    r13
0x180040495  push    r14
0x180040497  push    r15
0x180040499  sub     rsp, 88h
0x1800404a0  mov     r15, rcx
0x1800404a3  xor     r13d, r13d
0x1800404a6  mov     r14b, r13b
0x1800404a9  mov     r12d, r13d
0x1800404ac  lea     rcx, [rsp+0C8h+var_68]
0x1800404b1  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x1800404b7  nop
0x1800404b8  lea     rdi, qword_180057030
0x1800404bf  mov     bpl, 1
0x1800404c2  mov     rdx, [rdi+8]; String2
0x1800404c6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800404ca  inc     rsi
0x1800404cd  cmp     [rdx+rsi*2], r13w
0x1800404d2  jnz     short loc_1800404CA
0x1800404d4  mov     r8, rsi; MaxCount
0x1800404d7  mov     rcx, r15; String1
0x1800404da  call    cs:__imp__wcsnicmp
0x1800404e0  test    eax, eax
0x1800404e2  jnz     short loc_18004054E
0x1800404e4  mov     r14b, bpl
0x1800404e7  mov     r12, [rdi]
0x1800404ea  lea     ecx, [rax+18h]
0x1800404ed  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800404f3  mov     rbx, rax
0x1800404f6  mov     [rsp+0C8h+arg_8], rax
0x1800404fe  test    rax, rax
0x180040501  jz      short loc_180040520
0x180040503  lea     rdx, [r15+2]
0x180040507  lea     rdx, [rdx+rsi*2]
0x18004050b  mov     rcx, rax
0x18004050e  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180040514  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x18004051b  mov     [rbx], rax
0x18004051e  jmp     short loc_180040523
0x180040520  mov     rbx, r13
0x180040523  mov     rdx, rbx
0x180040526  lea     rcx, [rsp+0C8h+var_58]
0x18004052b  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180040531  nop
0x180040532  lea     rdx, [rsp+0C8h+var_58]
0x180040537  lea     rcx, [rsp+0C8h+var_68]
0x18004053c  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180040542  nop
0x180040543  lea     rcx, [rsp+0C8h+var_58]
0x180040548  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18004054e  add     rdi, 10h
0x180040552  lea     rax, stru_180057050
0x180040559  cmp     rdi, rax
0x18004055c  jnz     loc_1800404C2
0x180040562  test    r14b, r14b
0x180040565  jnz     loc_1800405F6
0x18004056b  call    cs:__imp_GetLastError
0x180040571  mov     edi, eax
0x180040573  call    cs:__imp_CurrentIP
0x180040579  mov     rbx, rax
0x18004057c  mov     r8, r15
0x18004057f  lea     rdx, aUnsupportedRoo; "Unsupported root key for hive %s"
0x180040586  mov     ecx, 2000000h; unsigned int
0x18004058b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180040590  mov     [rsp+0C8h+var_78], r13d
0x180040595  mov     [rsp+0C8h+var_80], r13
0x18004059a  mov     [rsp+0C8h+var_88], edi
0x18004059e  mov     [rsp+0C8h+var_90], rbx
0x1800405a3  lea     rcx, aHivelistenumer_0; "HiveListEnumerator::UnloadHiveByNtPath"
0x1800405aa  mov     [rsp+0C8h+var_98], rcx
0x1800405af  lea     rcx, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\srinfra\\recutil"...
0x1800405b6  mov     [rsp+0C8h+var_A0], rcx
0x1800405bb  mov     [rsp+0C8h+var_A8], 11Fh
0x1800405c3  xor     r9d, r9d
0x1800405c6  lea     r8, aD; "D"
0x1800405cd  xor     edx, edx
0x1800405cf  mov     rcx, rax
0x1800405d2  call    cs:__imp_WdsSetupLogMessageW
0x1800405d8  mov     ecx, 57h ; 'W'; dwErrCode
0x1800405dd  call    cs:__imp_SetLastError
0x1800405e3  nop
0x1800405e4  lea     rcx, [rsp+0C8h+var_68]
0x1800405e9  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800405ef  xor     al, al
0x1800405f1  jmp     loc_1800406A5
0x1800405f6  lea     rcx, [rsp+0C8h+var_68]
0x1800405fb  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180040601  mov     rcx, rax
0x180040604  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18004060a  mov     rdx, rax; lpSubKey
0x18004060d  mov     rcx, r12; hKey
0x180040610  call    cs:__imp_RegUnLoadKeyW
0x180040616  mov     esi, eax
0x180040618  test    eax, eax
0x18004061a  jz      short loc_180040697
0x18004061c  mov     ecx, eax; dwErrCode
0x18004061e  call    cs:__imp_SetLastError
0x180040624  call    cs:__imp_GetLastError
0x18004062a  mov     edi, eax
0x18004062c  call    cs:__imp_CurrentIP
0x180040632  mov     rbx, rax
0x180040635  mov     r9d, esi
0x180040638  mov     r8, r15
0x18004063b  lea     rdx, aFailedToUnload; "Failed to unload hive %s. Error %d"
0x180040642  mov     ecx, 2000000h; unsigned int
0x180040647  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18004064c  mov     [rsp+0C8h+var_78], r13d
0x180040651  mov     [rsp+0C8h+var_80], r13
0x180040656  mov     [rsp+0C8h+var_88], edi
0x18004065a  mov     [rsp+0C8h+var_90], rbx
0x18004065f  lea     rcx, aHivelistenumer_0; "HiveListEnumerator::UnloadHiveByNtPath"
0x180040666  mov     [rsp+0C8h+var_98], rcx
0x18004066b  lea     rcx, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\srinfra\\recutil"...
0x180040672  mov     [rsp+0C8h+var_A0], rcx
0x180040677  mov     [rsp+0C8h+var_A8], 128h
0x18004067f  xor     r9d, r9d
0x180040682  lea     r8, aD; "D"
0x180040689  xor     edx, edx
0x18004068b  mov     rcx, rax
0x18004068e  call    cs:__imp_WdsSetupLogMessageW
0x180040694  mov     bpl, r13b
0x180040697  lea     rcx, [rsp+0C8h+var_68]
0x18004069c  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800406a2  mov     al, bpl
0x1800406a5  add     rsp, 88h
0x1800406ac  pop     r15
0x1800406ae  pop     r14
0x1800406b0  pop     r13
0x1800406b2  pop     r12
0x1800406b4  pop     rdi
0x1800406b5  pop     rsi
0x1800406b6  pop     rbp
0x1800406b7  pop     rbx
0x1800406b8  retn
```
