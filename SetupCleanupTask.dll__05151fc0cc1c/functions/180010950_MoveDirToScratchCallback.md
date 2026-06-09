# MoveDirToScratchCallback

- ea: `0x180010950`
- end: `0x180010acb`
- name: `MoveDirToScratchCallback`
- size: `379`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update`

## callees

- `0x18000638c`
- `0x180010950`
- `0x180010c98`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010a20`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010a20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109a6`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180010a92`
- `unbcl!?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ` at `0x180010a92`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180010a39`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180010a39`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180010abb`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180010abb`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180010a72`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180010aa0`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180010a72`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180010aa0`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180010a56`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180010a56`
- `WDSCORE!CurrentIP` at `0x1800109ae`
- `WDSCORE!CurrentIP` at `0x1800109ae`
- `WDSCORE!WdsSetupLogMessageW` at `0x180010a18`
- `WDSCORE!WdsSetupLogMessageW` at `0x180010a18`

## string_xrefs

- `0x1800109f5`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanupjobs.cpp`
- `0x1800109e9`: `MoveDirToScratchCallback`
- `0x1800109be`: `MoveDirToScratchCallback: Failed to move %s to Scratch Reserve. hr = 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MoveDirToScratchCallback(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v4; // rdi
  signed int v5; // ebp
  DWORD LastError; // edi
  __int64 v7; // rbx
  struct tagLOG_PARTIAL_MSG *v8; // rax
  UnBCL::String *v10; // rax
  UnBCL::String *v11; // rbx
  void (__fastcall *v12)(__int64, __int64); // rbx
  __int64 P; // rax
  __int64 v14; // rax
  _BYTE v15[16]; // [rsp+60h] [rbp-48h] BYREF
  _BYTE v16[56]; // [rsp+70h] [rbp-38h] BYREF

  if ( !a3 )
    return 0;
  if ( !a1 )
    return 0;
  if ( !*(_QWORD *)(a1 + 40) )
    return 0;
  if ( !*a3 )
    return 0;
  v4 = a3[1];
  if ( !v4 )
    return 0;
  v5 = MoveToScratch();
  if ( v5 < 0 )
  {
    LastError = GetLastError();
    v7 = CurrentIP();
    v8 = ConstructPartialMsgW(
           50331648,
           "MoveDirToScratchCallback: Failed to move %s to Scratch Reserve. hr = 0x%08X",
           *(const char **)(a1 + 40),
           v5);
    WdsSetupLogMessageW(
      v8,
      0,
      L"D",
      0,
      750,
      L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanupjobs.cpp",
      L"MoveDirToScratchCallback",
      v7,
      LastError,
      0,
      0);
    SetLastError(v5);
    return 0;
  }
  v10 = (UnBCL::String *)UnBCL::Object::operator new(0x18u);
  v11 = v10;
  if ( v10 )
  {
    UnBCL::String::String(v10, *(const unsigned __int16 **)(a1 + 40));
    *(_QWORD *)v11 = &UnBCL::String::`local vftable';
  }
  else
  {
    v11 = 0;
  }
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v15, v11);
  v12 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 56LL);
  P = UnBCL::SmartPtr<UnBCL::String>::get_P(v15);
  v14 = UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v16, P);
  v12(v4, v14);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v15);
  return 1;
}

```

## disassembly

```asm
0x180010950  push    rbx
0x180010952  push    rbp
0x180010953  push    rsi
0x180010954  push    rdi
0x180010955  sub     rsp, 88h
0x18001095c  mov     rsi, rcx
0x18001095f  test    r8, r8
0x180010962  jz      loc_180010A26
0x180010968  test    rcx, rcx
0x18001096b  jz      loc_180010A26
0x180010971  mov     rcx, [rcx+28h]
0x180010975  test    rcx, rcx
0x180010978  jz      loc_180010A26
0x18001097e  mov     rdx, [r8]
0x180010981  test    rdx, rdx
0x180010984  jz      loc_180010A26
0x18001098a  mov     rdi, [r8+8]
0x18001098e  test    rdi, rdi
0x180010991  jz      loc_180010A26
0x180010997  call    MoveToScratch
0x18001099c  mov     ebp, eax
0x18001099e  test    eax, eax
0x1800109a0  jns     loc_180010A34
0x1800109a6  call    cs:__imp_GetLastError
0x1800109ac  mov     edi, eax
0x1800109ae  call    cs:__imp_CurrentIP
0x1800109b4  mov     rbx, rax
0x1800109b7  mov     r9d, ebp
0x1800109ba  mov     r8, [rsi+28h]
0x1800109be  lea     rdx, aMovedirtoscrat_0; "MoveDirToScratchCallback: Failed to mov"...
0x1800109c5  mov     ecx, 3000000h; unsigned int
0x1800109ca  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800109cf  mov     [rsp+0A8h+var_58], 0
0x1800109d7  mov     [rsp+0A8h+var_60], 0
0x1800109e0  mov     [rsp+0A8h+var_68], edi
0x1800109e4  mov     [rsp+0A8h+var_70], rbx
0x1800109e9  lea     rcx, aMovedirtoscrat; "MoveDirToScratchCallback"
0x1800109f0  mov     [rsp+0A8h+var_78], rcx
0x1800109f5  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupclean"...
0x1800109fc  mov     [rsp+0A8h+var_80], rcx
0x180010a01  mov     [rsp+0A8h+var_88], 2EEh
0x180010a09  xor     r9d, r9d
0x180010a0c  lea     r8, aD_0; "D"
0x180010a13  xor     edx, edx
0x180010a15  mov     rcx, rax
0x180010a18  call    cs:__imp_WdsSetupLogMessageW
0x180010a1e  mov     ecx, ebp; dwErrCode
0x180010a20  call    cs:__imp_SetLastError
0x180010a26  xor     eax, eax
0x180010a28  add     rsp, 88h
0x180010a2f  pop     rdi
0x180010a30  pop     rsi
0x180010a31  pop     rbp
0x180010a32  pop     rbx
0x180010a33  retn
0x180010a34  mov     ecx, 18h
0x180010a39  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180010a3f  mov     rbx, rax
0x180010a42  mov     [rsp+0A8h+arg_10], rax
0x180010a4a  test    rax, rax
0x180010a4d  jz      short loc_180010A68
0x180010a4f  mov     rdx, [rsi+28h]
0x180010a53  mov     rcx, rax
0x180010a56  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x180010a5c  lea     rax, ??_SString@UnBCL@@6B@; const UnBCL::String::`local vftable'
0x180010a63  mov     [rbx], rax
0x180010a66  jmp     short loc_180010A6A
0x180010a68  xor     ebx, ebx
0x180010a6a  mov     rdx, rbx
0x180010a6d  lea     rcx, [rsp+0A8h+var_48]
0x180010a72  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180010a78  nop
0x180010a79  mov     rax, [rdi]
0x180010a7c  mov     rbx, [rax+38h]
0x180010a80  lea     rax, [rsp+0A8h+var_38]
0x180010a85  mov     [rsp+0A8h+arg_10], rax
0x180010a8d  lea     rcx, [rsp+0A8h+var_48]
0x180010a92  call    cs:__imp_?get_P@?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@2@XZ; UnBCL::SmartPtr<UnBCL::String>::get_P(void)
0x180010a98  mov     rdx, rax
0x180010a9b  lea     rcx, [rsp+0A8h+var_38]
0x180010aa0  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180010aa6  nop
0x180010aa7  mov     rdx, rax
0x180010aaa  mov     rcx, rdi
0x180010aad  mov     rax, rbx
0x180010ab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ab5  nop
0x180010ab6  lea     rcx, [rsp+0A8h+var_48]
0x180010abb  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180010ac1  mov     eax, 1
0x180010ac6  jmp     loc_180010A28
```
