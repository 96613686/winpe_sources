# Spectre::Engine::Mutex::doUnlock<&Spectre::Utils::SharedMutex::unlock_shared(void)>(bool)

- ea: `0x180028bf4`
- end: `0x180028cbd`
- name: `??$doUnlock@$1?unlock_shared@SharedMutex@Utils@Spectre@@QEAAXXZ@Mutex@Engine@Spectre@@AEAAX_N@Z`
- size: `201`
- prototype: `__int64 __fastcall(Spectre::Utils::SharedMutex *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180028e3c`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x180011f64`
- `0x180028bf4`
- `0x180028d60`
- `0x180028edc`
- `0x180029078`
- `0x1800292ac`
- `0x1800292e8`
- `0x1800ceef4`

## string_xrefs

- `0x180028c31`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\concurrency.cpp`
- `0x180028c1f`: `Mutex::doUnlock() -- detected attempt to unlock a mutex that is not owned by this thread`

## pseudocode

```c
void __fastcall Spectre::Engine::Mutex::doUnlock<&public: void Spectre::Utils::SharedMutex::unlock_shared(void)>(
        Spectre::Utils::SharedMutex *this)
{
  __int64 v2; // rax
  __int64 v3; // r8
  __int64 MutexesLockedByCurrentThread; // rbx
  _QWORD *ThisMutex; // rax
  _BYTE v6[8]; // [rsp+30h] [rbp-98h] BYREF
  _BYTE v7[8]; // [rsp+38h] [rbp-90h] BYREF
  _BYTE v8[32]; // [rsp+40h] [rbp-88h] BYREF
  _BYTE v9[32]; // [rsp+60h] [rbp-68h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+80h] [rbp-48h] BYREF

  if ( !Spectre::Engine::Mutex::this_thread_owns(this) )
  {
    std::string::string(v9, "Mutex::doUnlock() -- detected attempt to unlock a mutex that is not owned by this thread");
    v2 = std::string::string(
           v8,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\concurrency.cpp");
    Spectre::Engine::EngineAccessDeniedException::EngineAccessDeniedException(pExceptionObject, v2, v3, v9);
    throw (Spectre::Engine::EngineAccessDeniedException *)pExceptionObject;
  }
  MutexesLockedByCurrentThread = Spectre::Engine::Mutex::GetMutexesLockedByCurrentThread();
  ThisMutex = (_QWORD *)Spectre::Engine::Mutex::FindThisMutex(this, v6, 0);
  std::vector<std::pair<Spectre::Engine::Mutex const *,bool>>::erase(MutexesLockedByCurrentThread, v7, *ThisMutex);
  Spectre::Utils::SharedMutex::unlock_shared(this);
}

```

## disassembly

```asm
0x180028bf4  mov     [rsp+arg_8], rbx
0x180028bf9  push    rdi
0x180028bfa  sub     rsp, 0C0h
0x180028c01  mov     rax, cs:__security_cookie
0x180028c08  xor     rax, rsp
0x180028c0b  mov     [rsp+0C8h+var_10], rax
0x180028c13  mov     rdi, rcx
0x180028c16  call    ?this_thread_owns@Mutex@Engine@Spectre@@QEBA_NXZ; Spectre::Engine::Mutex::this_thread_owns(void)
0x180028c1b  test    al, al
0x180028c1d  jnz     short loc_180028C6C
0x180028c1f  lea     rdx, aMutexDounlockD; "Mutex::doUnlock() -- detected attempt t"...
0x180028c26  lea     rcx, [rsp+0C8h+var_68]
0x180028c2b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180028c30  nop
0x180028c31  lea     rdx, aOnecoreuapWind_51; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180028c38  lea     rcx, [rsp+0C8h+var_88]
0x180028c3d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180028c42  lea     r9, [rsp+0C8h+var_68]
0x180028c47  mov     rdx, rax
0x180028c4a  lea     rcx, [rsp+0C8h+pExceptionObject]
0x180028c52  call    ??0EngineAccessDeniedException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineAccessDeniedException::EngineAccessDeniedException(std::string,int,std::string const &,bool)
0x180028c57  lea     rdx, _TI5?AUEngineAccessDeniedException@Engine@Spectre@@; pThrowInfo
0x180028c5e  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x180028c66  call    _CxxThrowException_0
0x180028c6c  call    ?GetMutexesLockedByCurrentThread@Mutex@Engine@Spectre@@CAAEAV?$vector@U?$pair@PEBVMutex@Engine@Spectre@@_N@std@@V?$allocator@U?$pair@PEBVMutex@Engine@Spectre@@_N@std@@@2@@std@@XZ; Spectre::Engine::Mutex::GetMutexesLockedByCurrentThread(void)
0x180028c71  mov     rbx, rax
0x180028c74  xor     r8d, r8d
0x180028c77  lea     rdx, [rsp+0C8h+var_98]
0x180028c7c  mov     rcx, rdi
0x180028c7f  call    ?FindThisMutex@Mutex@Engine@Spectre@@AEBA?AV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@U?$pair@PEBVMutex@Engine@Spectre@@_N@std@@@std@@@std@@@std@@_N@Z; Spectre::Engine::Mutex::FindThisMutex(bool)
0x180028c84  mov     r8, [rax]
0x180028c87  lea     rdx, [rsp+0C8h+var_90]
0x180028c8c  mov     rcx, rbx
0x180028c8f  call    ?erase@?$vector@U?$pair@PEBVMutex@Engine@Spectre@@_N@std@@V?$allocator@U?$pair@PEBVMutex@Engine@Spectre@@_N@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U?$pair@PEBVMutex@Engine@Spectre@@_N@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@U?$pair@PEBVMutex@Engine@Spectre@@_N@std@@@std@@@std@@@2@@Z; std::vector<std::pair<Spectre::Engine::Mutex const *,bool>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::pair<Spectre::Engine::Mutex const *,bool>>>>)
0x180028c94  mov     rcx, rdi; this
0x180028c97  call    ?unlock_shared@SharedMutex@Utils@Spectre@@QEAAXXZ; Spectre::Utils::SharedMutex::unlock_shared(void)
0x180028c9c  mov     rcx, [rsp+0C8h+var_10]
0x180028ca4  xor     rcx, rsp; StackCookie
0x180028ca7  call    __security_check_cookie
0x180028cac  mov     rbx, [rsp+0C8h+arg_8]
0x180028cb4  add     rsp, 0C0h
0x180028cbb  pop     rdi
0x180028cbc  retn
```
