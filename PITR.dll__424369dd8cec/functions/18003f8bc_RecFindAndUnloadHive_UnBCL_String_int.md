# RecFindAndUnloadHive(UnBCL::String *,int)

- ea: `0x18003f8bc`
- end: `0x18003fc02`
- name: `?RecFindAndUnloadHive@@YAJPEAVString@UnBCL@@H@Z`
- size: `838`
- prototype: `__int64 __fastcall(struct UnBCL::String *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18003fec0`

## callees

- `0x180009e04`
- `0x1800371c0`
- `0x18003e988`
- `0x18003ec48`
- `0x18003ee94`
- `0x18003f8bc`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f929`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f941`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f959`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f9fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fad6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fae7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fb42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fb5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f929`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f941`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f959`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f9fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fad6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fae7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fb42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fb5a`
- `WDSCORE!CurrentIP` at `0x18003f961`
- `WDSCORE!CurrentIP` at `0x18003fa06`
- `WDSCORE!CurrentIP` at `0x18003fade`
- `WDSCORE!CurrentIP` at `0x18003f961`
- `WDSCORE!CurrentIP` at `0x18003fa06`
- `WDSCORE!CurrentIP` at `0x18003fade`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003f9d3`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003fa95`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003fb3c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003f9d3`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003fa95`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003fb3c`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18003f8df`
- `unbcl!?get_Length@String@UnBCL@@QEBAHXZ` at `0x18003f8df`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18003f910`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18003f96d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18003fa23`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18003fa2f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18003faaf`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18003f910`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18003f96d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18003fa23`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18003fa2f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18003faaf`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18003fb76`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18003fbb9`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18003fb76`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18003fbb9`

## string_xrefs

- `0x18003f979`: `Conversion to NT path failed for %s. Error: 0x%08X`
- `0x18003fa3b`: `Attempting to find and unload hive %s (%s)`

## pseudocode

```c
__int64 __fastcall RecFindAndUnloadHive(struct UnBCL::String *a1)
{
  struct UnBCL::String **v2; // rbx
  const unsigned __int16 *CString; // rax
  signed int LastError; // eax
  bool v5; // sf
  signed int v6; // eax
  unsigned int v7; // esi
  DWORD v8; // edi
  __int64 v9; // rbx
  const char *v10; // rax
  struct tagLOG_PARTIAL_MSG *v11; // rax
  void (__fastcall ***v12)(_QWORD, __int64); // rcx
  DWORD v14; // esi
  __int64 v15; // rdi
  UnBCL::String *v16; // rax
  const char *v17; // rbx
  const char *v18; // rax
  struct tagLOG_PARTIAL_MSG *v19; // rax
  UnBCL::String *v20; // rax
  const unsigned __int16 *v21; // rax
  bool v22; // r9
  HKEY v23; // rdx
  const unsigned __int16 *v24; // r8
  DWORD v25; // edi
  __int64 v26; // rbx
  DWORD v27; // eax
  struct tagLOG_PARTIAL_MSG *v28; // rax
  signed int v29; // eax
  bool v30; // sf
  signed int v31; // eax
  unsigned int v32; // ebx
  bool v33; // [rsp+20h] [rbp-59h]
  void **v34; // [rsp+60h] [rbp-19h] BYREF
  void (__fastcall ***v35)(_QWORD, __int64); // [rsp+68h] [rbp-11h]
  _QWORD v36[2]; // [rsp+70h] [rbp-9h] BYREF
  _BYTE v37[20]; // [rsp+80h] [rbp+7h] BYREF
  int v38; // [rsp+94h] [rbp+1Bh]

  if ( !a1 || (int)UnBCL::String::get_Length(a1) < 2 )
    return 2147942487LL;
  v35 = 0;
  v34 = &RAII::CAutoDelete<UnBCL::String *>::`vftable';
  v2 = (struct UnBCL::String **)RAII::CAutoCleanupBase<IVssEnumObject *>::operator&(&v34);
  CString = UnBCL::String::get_CString(a1);
  if ( !HiveListEnumerator::ConvertWin32PathToNt(CString, v2) )
  {
    LastError = GetLastError();
    v5 = LastError < 0;
    if ( LastError > 0 )
      v5 = 1;
    if ( v5 )
    {
      v6 = GetLastError();
      v7 = v6;
      if ( v6 > 0 )
        v7 = (unsigned __int16)v6 | 0x80070000;
    }
    else
    {
      v7 = -2147467259;
    }
    v8 = GetLastError();
    v9 = CurrentIP();
    v10 = (const char *)UnBCL::String::get_CString(a1);
    v11 = ConstructPartialMsgW(50331648, "Conversion to NT path failed for %s. Error: 0x%08X", v10, v7);
    WdsSetupLogMessageW(
      v11,
      0,
      L"D",
      0,
      685,
      L"base\\diagnosis\\srt\\srinfra\\recutil\\reg.cpp",
      L"RecFindAndUnloadHive",
      v9,
      v8,
      0,
      0);
    v34 = &RAII::CAutoDelete<UnBCL::String *>::`vftable';
    v12 = v35;
    if ( !v35 )
      return v7;
    goto LABEL_11;
  }
  v14 = GetLastError();
  v15 = CurrentIP();
  v16 = (UnBCL::String *)((__int64 (__fastcall *)(void ***))v34[3])(&v34);
  v17 = (const char *)UnBCL::String::get_CString(v16);
  v18 = (const char *)UnBCL::String::get_CString(a1);
  v19 = ConstructPartialMsgW(0x4000000, "Attempting to find and unload hive %s (%s)", v18, v17);
  WdsSetupLogMessageW(
    v19,
    0,
    L"D",
    0,
    691,
    L"base\\diagnosis\\srt\\srinfra\\recutil\\reg.cpp",
    L"RecFindAndUnloadHive",
    v15,
    v14,
    0,
    0);
  v20 = (UnBCL::String *)((__int64 (__fastcall *)(void ***))v34[3])(&v34);
  v21 = UnBCL::String::get_CString(v20);
  SingleHiveUnloader::SingleHiveUnloader((SingleHiveUnloader *)v36, v21, 0, v22, v33);
  if ( !RegValueEnumAction::Enumerate((struct RegValueEnumAction *)v36, v23, v24) )
  {
    v25 = GetLastError();
    v26 = CurrentIP();
    v27 = GetLastError();
    v28 = ConstructPartialMsgW(50331648, "Enumeration of hive list failed. GLE: %u", v27);
    WdsSetupLogMessageW(
      v28,
      0,
      L"D",
      0,
      696,
      L"base\\diagnosis\\srt\\srinfra\\recutil\\reg.cpp",
      L"RecFindAndUnloadHive",
      v26,
      v25,
      0,
      0);
    v29 = GetLastError();
    v30 = v29 < 0;
    if ( v29 > 0 )
      v30 = 1;
    if ( v30 )
    {
      v31 = GetLastError();
      v7 = v31;
      if ( v31 > 0 )
        v7 = (unsigned __int16)v31 | 0x80070000;
    }
    else
    {
      v7 = -2147467259;
    }
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v37);
    v36[0] = &RegValueEnumAction::`vftable';
    v34 = &RAII::CAutoDelete<UnBCL::String *>::`vftable';
    v12 = v35;
    if ( !v35 )
      return v7;
LABEL_11:
    (**v35)(v12, 1);
    return v7;
  }
  v32 = v38;
  if ( v38 > 0 )
    v32 = (unsigned __int16)v38 | 0x80070000;
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v37);
  v36[0] = &RegValueEnumAction::`vftable';
  v34 = &RAII::CAutoDelete<UnBCL::String *>::`vftable';
  if ( v35 )
    (**v35)(v35, 1);
  return v32;
}

```

## disassembly

```asm
0x18003f8bc  push    rbp
0x18003f8be  push    rbx
0x18003f8bf  push    rsi
0x18003f8c0  push    rdi
0x18003f8c1  push    r13
0x18003f8c3  push    r14
0x18003f8c5  push    r15
0x18003f8c7  lea     rbp, [rsp-27h]
0x18003f8cc  sub     rsp, 0A0h
0x18003f8d3  mov     r14, rcx
0x18003f8d6  test    rcx, rcx
0x18003f8d9  jz      loc_18003FBEB
0x18003f8df  call    cs:__imp_?get_Length@String@UnBCL@@QEBAHXZ; UnBCL::String::get_Length(void)
0x18003f8e5  cmp     eax, 2
0x18003f8e8  jl      loc_18003FBEB
0x18003f8ee  mov     [rbp+57h+var_68], 0
0x18003f8f6  lea     r13, ??_7?$CAutoDelete@PEAVString@UnBCL@@@RAII@@6B@; const RAII::CAutoDelete<UnBCL::String *>::`vftable'
0x18003f8fd  mov     [rbp+57h+var_70], r13
0x18003f901  lea     rcx, [rbp+57h+var_70]
0x18003f905  call    ??I?$CAutoCleanupBase@PEAUIVssEnumObject@@@RAII@@UEBAPEBQEAUIVssEnumObject@@XZ; RAII::CAutoCleanupBase<IVssEnumObject *>::operator&(void)
0x18003f90a  mov     rbx, rax
0x18003f90d  mov     rcx, r14
0x18003f910  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18003f916  mov     rdx, rbx; struct UnBCL::String **
0x18003f919  mov     rcx, rax; unsigned __int16 *
0x18003f91c  call    ?ConvertWin32PathToNt@HiveListEnumerator@@SA_NPEBGPEAPEAVString@UnBCL@@@Z; HiveListEnumerator::ConvertWin32PathToNt(ushort const *,UnBCL::String * *)
0x18003f921  test    al, al
0x18003f923  jnz     loc_18003F9FE
0x18003f929  call    cs:__imp_GetLastError
0x18003f92f  mov     edi, 80070000h
0x18003f934  test    eax, eax
0x18003f936  jle     short loc_18003F93F
0x18003f938  movzx   eax, ax
0x18003f93b  or      eax, edi
0x18003f93d  test    eax, eax
0x18003f93f  jns     short loc_18003F954
0x18003f941  call    cs:__imp_GetLastError
0x18003f947  mov     esi, eax
0x18003f949  test    eax, eax
0x18003f94b  jle     short loc_18003F959
0x18003f94d  movzx   esi, ax
0x18003f950  or      esi, edi
0x18003f952  jmp     short loc_18003F959
0x18003f954  mov     esi, 80004005h
0x18003f959  call    cs:__imp_GetLastError
0x18003f95f  mov     edi, eax
0x18003f961  call    cs:__imp_CurrentIP
0x18003f967  mov     rbx, rax
0x18003f96a  mov     rcx, r14
0x18003f96d  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18003f973  mov     r8, rax
0x18003f976  mov     r9d, esi
0x18003f979  lea     rdx, aConversionToNt; "Conversion to NT path failed for %s. Er"...
0x18003f980  mov     ecx, 3000000h; unsigned int
0x18003f985  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18003f98a  mov     [rsp+0D0h+var_80], 0
0x18003f992  mov     [rsp+0D0h+var_88], 0
0x18003f99b  mov     [rsp+0D0h+var_90], edi
0x18003f99f  mov     [rsp+0D0h+var_98], rbx
0x18003f9a4  lea     r14, aRecfindandunlo; "RecFindAndUnloadHive"
0x18003f9ab  mov     [rsp+0D0h+var_A0], r14
0x18003f9b0  lea     r15, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\srinfra\\recutil"...
0x18003f9b7  mov     [rsp+0D0h+var_A8], r15
0x18003f9bc  mov     dword ptr [rsp+0D0h+var_B0], 2ADh
0x18003f9c4  xor     r9d, r9d
0x18003f9c7  lea     r8, aD; "D"
0x18003f9ce  xor     edx, edx
0x18003f9d0  mov     rcx, rax
0x18003f9d3  call    cs:__imp_WdsSetupLogMessageW
0x18003f9d9  nop
0x18003f9da  mov     [rbp+57h+var_70], r13
0x18003f9de  mov     rcx, [rbp+57h+var_68]
0x18003f9e2  test    rcx, rcx
0x18003f9e5  jz      short loc_18003F9F7
0x18003f9e7  mov     rax, [rcx]
0x18003f9ea  mov     rax, [rax]
0x18003f9ed  mov     edx, 1
0x18003f9f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f9f7  mov     eax, esi
0x18003f9f9  jmp     loc_18003FBF0
0x18003f9fe  call    cs:__imp_GetLastError
0x18003fa04  mov     esi, eax
0x18003fa06  call    cs:__imp_CurrentIP
0x18003fa0c  mov     rdi, rax
0x18003fa0f  mov     rcx, [rbp+57h+var_70]
0x18003fa13  mov     rax, [rcx+18h]
0x18003fa17  lea     rcx, [rbp+57h+var_70]
0x18003fa1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fa20  mov     rcx, rax
0x18003fa23  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18003fa29  mov     rbx, rax
0x18003fa2c  mov     rcx, r14
0x18003fa2f  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18003fa35  mov     r9, rbx
0x18003fa38  mov     r8, rax
0x18003fa3b  lea     rdx, aAttemptingToFi; "Attempting to find and unload hive %s ("...
0x18003fa42  mov     ecx, 4000000h; unsigned int
0x18003fa47  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18003fa4c  mov     [rsp+0D0h+var_80], 0
0x18003fa54  mov     [rsp+0D0h+var_88], 0
0x18003fa5d  mov     [rsp+0D0h+var_90], esi
0x18003fa61  mov     [rsp+0D0h+var_98], rdi
0x18003fa66  lea     r14, aRecfindandunlo; "RecFindAndUnloadHive"
0x18003fa6d  mov     [rsp+0D0h+var_A0], r14
0x18003fa72  lea     r15, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\srinfra\\recutil"...
0x18003fa79  mov     [rsp+0D0h+var_A8], r15
0x18003fa7e  mov     dword ptr [rsp+0D0h+var_B0], 2B3h; bool
0x18003fa86  xor     r9d, r9d
0x18003fa89  lea     r8, aD; "D"
0x18003fa90  xor     edx, edx
0x18003fa92  mov     rcx, rax
0x18003fa95  call    cs:__imp_WdsSetupLogMessageW
0x18003fa9b  mov     rax, [rbp+57h+var_70]
0x18003fa9f  lea     rcx, [rbp+57h+var_70]
0x18003faa3  mov     rax, [rax+18h]
0x18003faa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003faac  mov     rcx, rax
0x18003faaf  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18003fab5  mov     rdx, rax; unsigned __int16 *
0x18003fab8  xor     r8d, r8d; bool
0x18003fabb  lea     rcx, [rbp+57h+var_60]; this
0x18003fabf  call    ??0SingleHiveUnloader@@QEAA@PEBG_N11@Z; SingleHiveUnloader::SingleHiveUnloader(ushort const *,bool,bool,bool)
0x18003fac4  nop
0x18003fac5  lea     rcx, [rbp+57h+var_60]; struct RegValueEnumAction *
0x18003fac9  call    ?Enumerate@RegValueEnumAction@@SA_NAEAV1@PEAUHKEY__@@PEBG@Z; RegValueEnumAction::Enumerate(RegValueEnumAction &,HKEY__ *,ushort const *)
0x18003face  test    al, al
0x18003fad0  jnz     loc_18003FBA3
0x18003fad6  call    cs:__imp_GetLastError
0x18003fadc  mov     edi, eax
0x18003fade  call    cs:__imp_CurrentIP
0x18003fae4  mov     rbx, rax
0x18003fae7  call    cs:__imp_GetLastError
0x18003faed  mov     r8d, eax
0x18003faf0  lea     rdx, aEnumerationOfH; "Enumeration of hive list failed. GLE: %"...
0x18003faf7  mov     ecx, 3000000h; unsigned int
0x18003fafc  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18003fb01  mov     [rsp+0D0h+var_80], 0
0x18003fb09  mov     [rsp+0D0h+var_88], 0
0x18003fb12  mov     [rsp+0D0h+var_90], edi
0x18003fb16  mov     [rsp+0D0h+var_98], rbx
0x18003fb1b  mov     [rsp+0D0h+var_A0], r14
0x18003fb20  mov     [rsp+0D0h+var_A8], r15
0x18003fb25  mov     dword ptr [rsp+0D0h+var_B0], 2B8h
0x18003fb2d  xor     r9d, r9d
0x18003fb30  lea     r8, aD; "D"
0x18003fb37  xor     edx, edx
0x18003fb39  mov     rcx, rax
0x18003fb3c  call    cs:__imp_WdsSetupLogMessageW
0x18003fb42  call    cs:__imp_GetLastError
0x18003fb48  mov     edi, 80070000h
0x18003fb4d  test    eax, eax
0x18003fb4f  jle     short loc_18003FB58
0x18003fb51  movzx   eax, ax
0x18003fb54  or      eax, edi
0x18003fb56  test    eax, eax
0x18003fb58  jns     short loc_18003FB6D
0x18003fb5a  call    cs:__imp_GetLastError
0x18003fb60  mov     esi, eax
0x18003fb62  test    eax, eax
0x18003fb64  jle     short loc_18003FB72
0x18003fb66  movzx   esi, ax
0x18003fb69  or      esi, edi
0x18003fb6b  jmp     short loc_18003FB72
0x18003fb6d  mov     esi, 80004005h
0x18003fb72  lea     rcx, [rbp+57h+var_50]
0x18003fb76  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18003fb7c  lea     rax, ??_7RegValueEnumAction@@6B@; const RegValueEnumAction::`vftable'
0x18003fb83  mov     [rbp+57h+var_60], rax
0x18003fb87  mov     [rbp+57h+var_70], r13
0x18003fb8b  mov     rcx, [rbp+57h+var_68]
0x18003fb8f  test    rcx, rcx
0x18003fb92  jz      loc_18003F9F7
0x18003fb98  mov     rdx, [rcx]
0x18003fb9b  mov     rax, [rdx]
0x18003fb9e  jmp     loc_18003F9ED
0x18003fba3  mov     ebx, [rbp+57h+var_3C]
0x18003fba6  test    ebx, ebx
0x18003fba8  jz      short loc_18003FBB5
0x18003fbaa  jle     short loc_18003FBB5
0x18003fbac  movzx   ebx, bx
0x18003fbaf  or      ebx, 80070000h
0x18003fbb5  lea     rcx, [rbp+57h+var_50]
0x18003fbb9  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18003fbbf  lea     rax, ??_7RegValueEnumAction@@6B@; const RegValueEnumAction::`vftable'
0x18003fbc6  mov     [rbp+57h+var_60], rax
0x18003fbca  mov     [rbp+57h+var_70], r13
0x18003fbce  mov     rcx, [rbp+57h+var_68]
0x18003fbd2  test    rcx, rcx
0x18003fbd5  jz      short loc_18003FBE7
0x18003fbd7  mov     rdx, [rcx]
0x18003fbda  mov     rax, [rdx]
0x18003fbdd  mov     edx, 1
0x18003fbe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fbe7  mov     eax, ebx
0x18003fbe9  jmp     short loc_18003FBF0
0x18003fbeb  mov     eax, 80070057h
0x18003fbf0  add     rsp, 0A0h
0x18003fbf7  pop     r15
0x18003fbf9  pop     r14
0x18003fbfb  pop     r13
0x18003fbfd  pop     rdi
0x18003fbfe  pop     rsi
0x18003fbff  pop     rbx
0x18003fc00  pop     rbp
0x18003fc01  retn
```
