# DumpCleanupJobs(UnBCL::ArrayList<ISetupCleanupJob *> *)

- ea: `0x180014da8`
- end: `0x180014f4b`
- name: `?DumpCleanupJobs@@YAXPEAV?$ArrayList@PEAVISetupCleanupJob@@@UnBCL@@@Z`
- size: `419`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x180006838`

## callees

- `0x18000272c`
- `0x180003c68`
- `0x18000638c`
- `0x180014da8`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e1f`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x180014f0b`
- `unbcl!??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z` at `0x180014f0b`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180014e35`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180014e4e`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180014e35`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180014e4e`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180014e57`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180014e57`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180014eeb`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180014eeb`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180014ecb`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180014ecb`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180014e18`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180014e18`
- `WDSCORE!CurrentIP` at `0x180014e27`
- `WDSCORE!CurrentIP` at `0x180014e27`
- `WDSCORE!WdsSetupLogMessageW` at `0x180014ebf`
- `WDSCORE!WdsSetupLogMessageW` at `0x180014ebf`

## string_xrefs

- `0x180014e9c`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskutil.cpp`

## pseudocode

```c
__int64 __fastcall DumpCleanupJobs(__int64 a1)
{
  int v2; // edi
  __int64 (__fastcall ***v3)(_QWORD); // rcx
  __int64 result; // rax
  __int64 v5; // rcx
  _QWORD *v6; // rax
  __int64 v7; // rax
  DWORD LastError; // esi
  __int64 v9; // rbp
  const wchar_t *CString; // rax
  UnBCL::String *P; // rax
  struct tagLOG_PARTIAL_MSG *v12; // rax
  UnBCL::ArgumentNullException *v13; // rax
  UnBCL::Exception *v14; // rbx
  _BYTE v15[40]; // [rsp+60h] [rbp-28h] BYREF
  UnBCL::Exception *pExceptionObject; // [rsp+90h] [rbp+8h] BYREF
  UnBCL::ArgumentNullException *v17; // [rsp+98h] [rbp+10h]

  if ( !a1 )
  {
    v13 = (UnBCL::ArgumentNullException *)UnBCL::Object::operator new(0x38u);
    v14 = v13;
    v17 = v13;
    if ( v13 )
    {
      UnBCL::ArgumentNullException::ArgumentNullException(v13, L"CleanupJobs");
      *(_QWORD *)v14 = &UnBCL::ArgumentNullException::`local vftable';
    }
    else
    {
      v14 = 0;
    }
    pExceptionObject = AddStackTraceToException<SetupCleanupTaskException>(
                         v14,
                         "void __cdecl DumpCleanupJobs(class UnBCL::ArrayList<class ISetupCleanupJob *> *)");
    throw (UnBCL::ArgumentNullException **)&pExceptionObject;
  }
  v2 = 0;
  while ( 1 )
  {
    v3 = (__int64 (__fastcall ***)(_QWORD))(a1 + *(int *)(*(_QWORD *)(a1 + 8) + 12LL) + 8LL);
    result = (**v3)(v3);
    if ( v2 >= (int)result )
      break;
    v5 = a1 + *(int *)(*(_QWORD *)(a1 + 8) + 16LL) + 8LL;
    v6 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v5 + 24LL))(v5, (unsigned int)v2);
    v7 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 32LL))(*v6);
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v15, v7);
    LastError = GetLastError();
    v9 = CurrentIP();
    if ( UnBCL::SmartPtr<UnBCL::String>::get_P(v15) )
    {
      P = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::get_P(v15);
      CString = UnBCL::String::get_CString(P);
    }
    else
    {
      CString = L"(NULL)";
    }
    v12 = ConstructPartialMsgW(0x4000000, "  %d. %s", ++v2, (const char *)CString);
    WdsSetupLogMessageW(
      v12,
      0,
      L"D",
      0,
      117,
      L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskutil.cpp",
      L"DumpCleanupJobs",
      v9,
      LastError,
      0,
      0);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v15);
  }
  return result;
}

```

## disassembly

```asm
0x180014da8  mov     [rsp+arg_10], rbx
0x180014dad  push    rbp
0x180014dae  push    rsi
0x180014daf  push    rdi
0x180014db0  sub     rsp, 70h
0x180014db4  mov     rbx, rcx
0x180014db7  test    rcx, rcx
0x180014dba  jz      loc_180014EE6
0x180014dc0  xor     edi, edi
0x180014dc2  mov     rax, [rbx+8]
0x180014dc6  movsxd  rcx, dword ptr [rax+0Ch]
0x180014dca  add     rcx, 8
0x180014dce  add     rcx, rbx
0x180014dd1  mov     rax, [rcx]
0x180014dd4  mov     rax, [rax]
0x180014dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ddc  cmp     edi, eax
0x180014dde  jge     loc_180014ED6
0x180014de4  mov     rax, [rbx+8]
0x180014de8  movsxd  rcx, dword ptr [rax+10h]
0x180014dec  add     rcx, 8
0x180014df0  add     rcx, rbx
0x180014df3  mov     rax, [rcx]
0x180014df6  mov     edx, edi
0x180014df8  mov     rax, [rax+18h]
0x180014dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e01  mov     rcx, [rax]
0x180014e04  mov     rax, [rcx]
0x180014e07  mov     rax, [rax+20h]
0x180014e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e10  mov     rdx, rax
0x180014e13  lea     rcx, [rsp+88h+var_28]
0x180014e18  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180014e1e  nop
0x180014e1f  call    cs:__imp_GetLastError
0x180014e25  mov     esi, eax
0x180014e27  call    cs:__imp_CurrentIP
0x180014e2d  mov     rbp, rax
0x180014e30  lea     rcx, [rsp+88h+var_28]
0x180014e35  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180014e3b  test    rax, rax
0x180014e3e  jnz     short loc_180014E49
0x180014e40  lea     rax, aNull; "(NULL)"
0x180014e47  jmp     short loc_180014E5D
0x180014e49  lea     rcx, [rsp+88h+var_28]
0x180014e4e  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180014e54  mov     rcx, rax
0x180014e57  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180014e5d  inc     edi
0x180014e5f  mov     r9, rax
0x180014e62  mov     r8d, edi
0x180014e65  lea     rdx, aDS; "  %d. %s"
0x180014e6c  mov     ecx, 4000000h; unsigned int
0x180014e71  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180014e76  mov     [rsp+88h+var_38], 0
0x180014e7e  mov     [rsp+88h+var_40], 0
0x180014e87  mov     [rsp+88h+var_48], esi
0x180014e8b  mov     [rsp+88h+var_50], rbp
0x180014e90  lea     rcx, aDumpcleanupjob; "DumpCleanupJobs"
0x180014e97  mov     [rsp+88h+var_58], rcx
0x180014e9c  lea     rcx, aBaseNtsetupSet_1; "base\\ntsetup\\setup\\tools\\setupclean"...
0x180014ea3  mov     [rsp+88h+var_60], rcx
0x180014ea8  mov     [rsp+88h+var_68], 75h ; 'u'
0x180014eb0  xor     r9d, r9d
0x180014eb3  lea     r8, aD_0; "D"
0x180014eba  xor     edx, edx
0x180014ebc  mov     rcx, rax
0x180014ebf  call    cs:__imp_WdsSetupLogMessageW
0x180014ec5  nop
0x180014ec6  lea     rcx, [rsp+88h+var_28]
0x180014ecb  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180014ed1  jmp     loc_180014DC2
0x180014ed6  mov     rbx, [rsp+88h+arg_10]
0x180014ede  add     rsp, 70h
0x180014ee2  pop     rdi
0x180014ee3  pop     rsi
0x180014ee4  pop     rbp
0x180014ee5  retn
0x180014ee6  mov     ecx, 38h ; '8'
0x180014eeb  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180014ef1  mov     rbx, rax
0x180014ef4  mov     [rsp+88h+arg_8], rax
0x180014efc  test    rax, rax
0x180014eff  jz      short loc_180014F1D
0x180014f01  lea     rdx, aCleanupjobs; "CleanupJobs"
0x180014f08  mov     rcx, rax
0x180014f0b  call    cs:__imp_??0ArgumentNullException@UnBCL@@QEAA@PEBG@Z; UnBCL::ArgumentNullException::ArgumentNullException(ushort const *)
0x180014f11  lea     rax, ??_SArgumentNullException@UnBCL@@6B@; const UnBCL::ArgumentNullException::`local vftable'
0x180014f18  mov     [rbx], rax
0x180014f1b  jmp     short loc_180014F1F
0x180014f1d  xor     ebx, ebx
0x180014f1f  lea     rdx, aVoidCdeclDumpc; "void __cdecl DumpCleanupJobs(class UnBC"...
0x180014f26  mov     rcx, rbx
0x180014f29  call    ??$AddStackTraceToException@VSetupCleanupTaskException@@@@YAPEAVSetupCleanupTaskException@@PEAV0@PEBD@Z; AddStackTraceToException<SetupCleanupTaskException>(SetupCleanupTaskException *,char const *)
0x180014f2e  mov     [rsp+88h+pExceptionObject], rax
0x180014f36  lea     rdx, _TI6PEAVArgumentNullException@UnBCL@@; pThrowInfo
0x180014f3d  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180014f45  call    _CxxThrowException_0
```
