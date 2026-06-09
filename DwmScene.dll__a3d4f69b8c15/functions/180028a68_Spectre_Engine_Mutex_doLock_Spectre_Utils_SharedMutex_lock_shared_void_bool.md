# Spectre::Engine::Mutex::doLock<&Spectre::Utils::SharedMutex::lock_shared(void)>(bool)

- ea: `0x180028a68`
- end: `0x180028b1e`
- name: `??$doLock@$1?lock_shared@SharedMutex@Utils@Spectre@@QEAAXXZ@Mutex@Engine@Spectre@@AEAAX_N@Z`
- size: `182`
- prototype: `__int64 __fastcall(Spectre::Utils::SharedMutex *this)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800290d4`
- `0x18005bb70`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x180011f64`
- `0x180028a68`
- `0x180028cc4`
- `0x180028d60`
- `0x180029078`
- `0x1800292e8`
- `0x1800cee5c`

## string_xrefs

- `0x180028aa6`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\concurrency.cpp`
- `0x180028a94`: `Mutex::doLock() -- detected recursive lock attempt on non-recursive mutex -- throwing exception to avoid deadlock`

## pseudocode

```c
__int64 __fastcall Spectre::Engine::Mutex::doLock<&public: void Spectre::Utils::SharedMutex::lock_shared(void)>(
        Spectre::Utils::SharedMutex *this)
{
  __int64 v2; // rax
  __int64 v3; // r8
  __int64 MutexesLockedByCurrentThread; // rax
  _BYTE v6[8]; // [rsp+30h] [rbp-98h] BYREF
  Spectre::Utils::SharedMutex *v7; // [rsp+38h] [rbp-90h] BYREF
  _BYTE v8[32]; // [rsp+40h] [rbp-88h] BYREF
  _BYTE v9[32]; // [rsp+60h] [rbp-68h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+80h] [rbp-48h] BYREF

  v6[0] = 0;
  if ( Spectre::Engine::Mutex::this_thread_owns(this) )
  {
    std::string::string(
      v9,
      "Mutex::doLock() -- detected recursive lock attempt on non-recursive mutex -- throwing exception to avoid deadlock");
    v2 = std::string::string(
           v8,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\concurrency.cpp");
    Spectre::Engine::EngineAccessDeniedException::EngineAccessDeniedException(pExceptionObject, v2, v3, v9);
    throw (Spectre::Engine::EngineAccessDeniedException *)pExceptionObject;
  }
  Spectre::Utils::SharedMutex::lock_shared(this);
  MutexesLockedByCurrentThread = Spectre::Engine::Mutex::GetMutexesLockedByCurrentThread();
  v7 = this;
  return std::vector<std::pair<Spectre::Engine::Mutex const *,bool>>::emplace_back<Spectre::Engine::Mutex *,bool &>(
           MutexesLockedByCurrentThread,
           &v7,
           v6);
}

```

## disassembly

```asm
0x180028a68  push    rbx
0x180028a6a  sub     rsp, 0C0h
0x180028a71  mov     rax, cs:__security_cookie
0x180028a78  xor     rax, rsp
0x180028a7b  mov     [rsp+0C8h+var_10], rax
0x180028a83  mov     rbx, rcx
0x180028a86  mov     [rsp+0C8h+var_98], 0
0x180028a8b  call    ?this_thread_owns@Mutex@Engine@Spectre@@QEBA_NXZ; Spectre::Engine::Mutex::this_thread_owns(void)
0x180028a90  test    al, al
0x180028a92  jz      short loc_180028AE1
0x180028a94  lea     rdx, aMutexDolockDet; "Mutex::doLock() -- detected recursive l"...
0x180028a9b  lea     rcx, [rsp+0C8h+var_68]
0x180028aa0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180028aa5  nop
0x180028aa6  lea     rdx, aOnecoreuapWind_51; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180028aad  lea     rcx, [rsp+0C8h+var_88]
0x180028ab2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180028ab7  lea     r9, [rsp+0C8h+var_68]
0x180028abc  mov     rdx, rax
0x180028abf  lea     rcx, [rsp+0C8h+pExceptionObject]
0x180028ac7  call    ??0EngineAccessDeniedException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineAccessDeniedException::EngineAccessDeniedException(std::string,int,std::string const &,bool)
0x180028acc  lea     rdx, _TI5?AUEngineAccessDeniedException@Engine@Spectre@@; pThrowInfo
0x180028ad3  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x180028adb  call    _CxxThrowException_0
0x180028ae1  mov     rcx, rbx; this
0x180028ae4  call    ?lock_shared@SharedMutex@Utils@Spectre@@QEAAXXZ; Spectre::Utils::SharedMutex::lock_shared(void)
0x180028ae9  call    ?GetMutexesLockedByCurrentThread@Mutex@Engine@Spectre@@CAAEAV?$vector@U?$pair@PEBVMutex@Engine@Spectre@@_N@std@@V?$allocator@U?$pair@PEBVMutex@Engine@Spectre@@_N@std@@@2@@std@@XZ; Spectre::Engine::Mutex::GetMutexesLockedByCurrentThread(void)
0x180028aee  mov     [rsp+0C8h+var_90], rbx
0x180028af3  lea     r8, [rsp+0C8h+var_98]
0x180028af8  lea     rdx, [rsp+0C8h+var_90]
0x180028afd  mov     rcx, rax
0x180028b00  call    ??$emplace_back@PEAVMutex@Engine@Spectre@@AEA_N@?$vector@U?$pair@PEBVMutex@Engine@Spectre@@_N@std@@V?$allocator@U?$pair@PEBVMutex@Engine@Spectre@@_N@std@@@2@@std@@QEAAAEAU?$pair@PEBVMutex@Engine@Spectre@@_N@1@$$QEAPEAVMutex@Engine@Spectre@@AEA_N@Z; std::vector<std::pair<Spectre::Engine::Mutex const *,bool>>::emplace_back<Spectre::Engine::Mutex *,bool &>(Spectre::Engine::Mutex * &&,bool &)
0x180028b05  mov     rcx, [rsp+0C8h+var_10]
0x180028b0d  xor     rcx, rsp; StackCookie
0x180028b10  call    __security_check_cookie
0x180028b15  add     rsp, 0C0h
0x180028b1c  pop     rbx
0x180028b1d  retn
```
