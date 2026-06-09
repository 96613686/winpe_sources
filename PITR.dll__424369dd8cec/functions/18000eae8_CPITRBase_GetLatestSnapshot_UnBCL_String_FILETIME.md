# CPITRBase::GetLatestSnapshot(UnBCL::String * *,_FILETIME *)

- ea: `0x18000eae8`
- end: `0x18000ed78`
- name: `?GetLatestSnapshot@CPITRBase@@IEAAJPEAPEAVString@UnBCL@@PEAU_FILETIME@@@Z`
- size: `656`
- prototype: `__int64 __fastcall(CPITRBase *__hidden this, struct UnBCL::String **, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x18001ce50`

## callees

- `0x180009e04`
- `0x18000eae8`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec0e`
- `WDSCORE!CurrentIP` at `0x18000eb5f`
- `WDSCORE!CurrentIP` at `0x18000ec16`
- `WDSCORE!CurrentIP` at `0x18000eb5f`
- `WDSCORE!CurrentIP` at `0x18000ec16`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000ebc5`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000ec6e`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000ebc5`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000ec6e`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000ec95`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x18000ec95`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000ecbc`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x18000ecbc`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18000ecd7`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18000ecd7`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18000eb28`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x18000eb28`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18000ecf1`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18000ed49`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18000ecf1`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18000ed49`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x18000ed12`
- `unbcl!?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ` at `0x18000ed12`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18000ece6`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18000ece6`

## string_xrefs

- `0x18000eba2`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18000ebd9`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`

## pseudocode

```c
__int64 __fastcall CPITRBase::GetLatestSnapshot(CPITRBase *this, struct UnBCL::String **a2, struct _FILETIME *a3)
{
  int v5; // esi
  DWORD v6; // edi
  __int64 v7; // rbx
  struct tagLOG_PARTIAL_MSG *v8; // rax
  struct _FILETIME v9; // rbx
  int v10; // eax
  int v11; // r14d
  DWORD LastError; // esi
  __int64 v13; // rdi
  struct tagLOG_PARTIAL_MSG *v14; // rax
  UnBCL::String *v15; // rdi
  const unsigned __int16 *v16; // rax
  _BYTE v19[16]; // [rsp+68h] [rbp-21h] BYREF
  _BYTE v20[8]; // [rsp+78h] [rbp-11h] BYREF
  UnBCL::String *v21; // [rsp+80h] [rbp-9h]
  __int64 v22; // [rsp+88h] [rbp-1h] BYREF
  __int64 v23; // [rsp+90h] [rbp+7h] BYREF
  _BYTE v24[16]; // [rsp+98h] [rbp+Fh] BYREF

  v23 = 0;
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v24);
  if ( a2 )
  {
    v5 = (*(__int64 (__fastcall **)(CPITRBase *, __int64 *))(*(_QWORD *)this + 32LL))(this, &v23);
    if ( v5 >= 0 )
    {
      v9 = 0;
      while ( 1 )
      {
        while ( 1 )
        {
          v22 = 0;
          v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 8LL))(v23, &v22);
          v11 = v10;
          if ( v10 < 0 )
            break;
          v9 = *(struct _FILETIME *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v22 + 16LL))(v22, v20);
          v15 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
          v21 = v15;
          if ( v15 )
          {
            v16 = (const unsigned __int16 *)(**(__int64 (__fastcall ***)(__int64))v22)(v22);
            UnBCL::String::String(v15, v16);
            *(_QWORD *)v15 = &UnBCL::String::`local vftable';
          }
          else
          {
            v15 = 0;
          }
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v19, v15);
          UnBCL::SmartPtr<UnBCL::String>::operator=(v24, v19);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v19);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 64LL))(v22);
        }
        if ( v10 == -2147024637 )
          break;
        LastError = GetLastError();
        v13 = CurrentIP();
        v14 = ConstructPartialMsgW(50331648, "Failed to get the next snapshot. Error: 0x%08X", v11);
        WdsSetupLogMessageW(
          v14,
          0,
          L"D",
          0,
          3289,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRBase::GetLatestSnapshot",
          v13,
          LastError,
          0,
          0);
      }
      v5 = 0;
      *a2 = (struct UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::Steal(v24);
      if ( a3 )
        *a3 = v9;
    }
    else
    {
      v6 = GetLastError();
      v7 = CurrentIP();
      v8 = ConstructPartialMsgW(
             0x2000000,
             "CPITRBase::GetLatestSnapshot: Failed to get snapshot enumerator. Error: 0x%08X",
             v5);
      WdsSetupLogMessageW(
        v8,
        0,
        L"D",
        0,
        3273,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"CPITRBase::GetLatestSnapshot",
        v7,
        v6,
        0,
        0);
    }
  }
  else
  {
    v5 = -2147024809;
  }
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v24);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000eae8  mov     [rsp-8+arg_18], rbx
0x18000eaed  push    rbp
0x18000eaee  push    rsi
0x18000eaef  push    rdi
0x18000eaf0  push    r12
0x18000eaf2  push    r13
0x18000eaf4  push    r14
0x18000eaf6  push    r15
0x18000eaf8  lea     rbp, [rsp-27h]
0x18000eafd  sub     rsp, 0B0h
0x18000eb04  mov     rax, cs:__security_cookie
0x18000eb0b  xor     rax, rsp
0x18000eb0e  mov     [rbp+57h+var_38], rax
0x18000eb12  mov     [rbp+57h+var_80], r8
0x18000eb16  mov     r12, rdx
0x18000eb19  mov     rbx, rcx
0x18000eb1c  mov     [rbp+57h+var_50], 0
0x18000eb24  lea     rcx, [rbp+57h+var_48]
0x18000eb28  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x18000eb2e  nop
0x18000eb2f  test    r12, r12
0x18000eb32  jnz     short loc_18000EB3E
0x18000eb34  mov     esi, 80070057h
0x18000eb39  jmp     loc_18000ED28
0x18000eb3e  mov     rax, [rbx]
0x18000eb41  lea     rdx, [rbp+57h+var_50]
0x18000eb45  mov     rcx, rbx
0x18000eb48  mov     rax, [rax+20h]
0x18000eb4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb51  mov     esi, eax
0x18000eb53  test    eax, eax
0x18000eb55  jns     short loc_18000EBD0
0x18000eb57  call    cs:__imp_GetLastError
0x18000eb5d  mov     edi, eax
0x18000eb5f  call    cs:__imp_CurrentIP
0x18000eb65  mov     rbx, rax
0x18000eb68  mov     r8d, esi
0x18000eb6b  lea     rdx, aCpitrbaseGetla; "CPITRBase::GetLatestSnapshot: Failed to"...
0x18000eb72  mov     ecx, 2000000h; unsigned int
0x18000eb77  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000eb7c  mov     [rsp+0E0h+var_90], 0
0x18000eb84  mov     [rsp+0E0h+var_98], 0
0x18000eb8d  mov     [rsp+0E0h+var_A0], edi
0x18000eb91  mov     [rsp+0E0h+var_A8], rbx
0x18000eb96  lea     r13, aCpitrbaseGetla_0; "CPITRBase::GetLatestSnapshot"
0x18000eb9d  mov     [rsp+0E0h+var_B0], r13
0x18000eba2  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x18000eba9  mov     [rsp+0E0h+var_B8], rcx
0x18000ebae  mov     [rsp+0E0h+var_C0], 0CC9h
0x18000ebb6  xor     r9d, r9d
0x18000ebb9  lea     r8, aD; "D"
0x18000ebc0  xor     edx, edx
0x18000ebc2  mov     rcx, rax
0x18000ebc5  call    cs:__imp_WdsSetupLogMessageW
0x18000ebcb  jmp     loc_18000ED28
0x18000ebd0  xor     ebx, ebx
0x18000ebd2  lea     r13, aCpitrbaseGetla_0; "CPITRBase::GetLatestSnapshot"
0x18000ebd9  lea     r15, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x18000ebe0  mov     [rbp+57h+var_58], 0
0x18000ebe8  mov     rcx, [rbp+57h+var_50]
0x18000ebec  mov     rax, [rcx]
0x18000ebef  lea     rdx, [rbp+57h+var_58]
0x18000ebf3  mov     rax, [rax+8]
0x18000ebf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebfc  mov     r14d, eax
0x18000ebff  test    eax, eax
0x18000ec01  jns     short loc_18000EC79
0x18000ec03  cmp     eax, 80070103h
0x18000ec08  jz      loc_18000ED0C
0x18000ec0e  call    cs:__imp_GetLastError
0x18000ec14  mov     esi, eax
0x18000ec16  call    cs:__imp_CurrentIP
0x18000ec1c  mov     rdi, rax
0x18000ec1f  mov     r8d, r14d
0x18000ec22  lea     rdx, aFailedToGetThe_1; "Failed to get the next snapshot. Error:"...
0x18000ec29  mov     ecx, 3000000h; unsigned int
0x18000ec2e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000ec33  mov     [rsp+0E0h+var_90], 0
0x18000ec3b  mov     [rsp+0E0h+var_98], 0
0x18000ec44  mov     [rsp+0E0h+var_A0], esi
0x18000ec48  mov     [rsp+0E0h+var_A8], rdi
0x18000ec4d  mov     [rsp+0E0h+var_B0], r13
0x18000ec52  mov     [rsp+0E0h+var_B8], r15
0x18000ec57  mov     [rsp+0E0h+var_C0], 0CD9h
0x18000ec5f  xor     r9d, r9d
0x18000ec62  lea     r8, aD; "D"
0x18000ec69  xor     edx, edx
0x18000ec6b  mov     rcx, rax
0x18000ec6e  call    cs:__imp_WdsSetupLogMessageW
0x18000ec74  jmp     loc_18000EBE0
0x18000ec79  mov     rcx, [rbp+57h+var_58]
0x18000ec7d  mov     rax, [rcx]
0x18000ec80  lea     rdx, [rbp+57h+var_68]
0x18000ec84  mov     rax, [rax+10h]
0x18000ec88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec8d  mov     rbx, [rax]
0x18000ec90  mov     ecx, 18h
0x18000ec95  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x18000ec9b  mov     rdi, rax
0x18000ec9e  mov     [rbp+57h+var_60], rax
0x18000eca2  test    rax, rax
0x18000eca5  jz      short loc_18000ECCE
0x18000eca7  mov     rcx, [rbp+57h+var_58]
0x18000ecab  mov     rax, [rcx]
0x18000ecae  mov     rax, [rax]
0x18000ecb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecb6  mov     rdx, rax
0x18000ecb9  mov     rcx, rdi
0x18000ecbc  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18000ecc2  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x18000ecc9  mov     [rdi], rax
0x18000eccc  jmp     short loc_18000ECD0
0x18000ecce  xor     edi, edi
0x18000ecd0  mov     rdx, rdi
0x18000ecd3  lea     rcx, [rbp+57h+var_78]
0x18000ecd7  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x18000ecdd  nop
0x18000ecde  lea     rdx, [rbp+57h+var_78]
0x18000ece2  lea     rcx, [rbp+57h+var_48]
0x18000ece6  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x18000ecec  nop
0x18000eced  lea     rcx, [rbp+57h+var_78]
0x18000ecf1  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18000ecf7  mov     rcx, [rbp+57h+var_58]
0x18000ecfb  mov     rax, [rcx]
0x18000ecfe  mov     rax, [rax+40h]
0x18000ed02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed07  jmp     loc_18000EBE0
0x18000ed0c  xor     esi, esi
0x18000ed0e  lea     rcx, [rbp+57h+var_48]
0x18000ed12  call    cs:__imp_?Steal@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::Steal(void)
0x18000ed18  mov     [r12], rax
0x18000ed1c  mov     r15, [rbp+57h+var_80]
0x18000ed20  test    r15, r15
0x18000ed23  jz      short loc_18000ED28
0x18000ed25  mov     [r15], rbx
0x18000ed28  mov     rcx, [rbp+57h+var_50]
0x18000ed2c  test    rcx, rcx
0x18000ed2f  jz      short loc_18000ED45
0x18000ed31  mov     rax, [rcx]
0x18000ed34  mov     rax, [rax+10h]
0x18000ed38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed3d  mov     [rbp+57h+var_50], 0
0x18000ed45  lea     rcx, [rbp+57h+var_48]
0x18000ed49  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x18000ed4f  mov     eax, esi
0x18000ed51  mov     rcx, [rbp+57h+var_38]
0x18000ed55  xor     rcx, rsp; StackCookie
0x18000ed58  call    __security_check_cookie
0x18000ed5d  mov     rbx, [rsp+0E0h+arg_18]
0x18000ed65  add     rsp, 0B0h
0x18000ed6c  pop     r15
0x18000ed6e  pop     r14
0x18000ed70  pop     r13
0x18000ed72  pop     r12
0x18000ed74  pop     rdi
0x18000ed75  pop     rsi
0x18000ed76  pop     rbp
0x18000ed77  retn
```
