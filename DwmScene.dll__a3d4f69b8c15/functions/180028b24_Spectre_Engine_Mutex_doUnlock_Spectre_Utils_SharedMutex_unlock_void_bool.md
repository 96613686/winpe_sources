# Spectre::Engine::Mutex::doUnlock<&Spectre::Utils::SharedMutex::unlock(void)>(bool)

- ea: `0x180028b24`
- end: `0x180028bed`
- name: `??$doUnlock@$1?unlock@SharedMutex@Utils@Spectre@@QEAAXXZ@Mutex@Engine@Spectre@@AEAAX_N@Z`
- size: `201`
- prototype: `__int64 __fastcall(Spectre::Utils::SharedMutex *this)`
- caller_count: `21`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800120ec`
- `0x180024ff8`
- `0x180025bd0`
- `0x1800263f0`
- `0x180026ab0`
- `0x180031554`
- `0x180094440`
- `0x1800944dc`
- `0x180094d34`
- `0x180094e14`
- `0x180094f74`
- `0x180095024`
- `0x1800950b4`
- `0x1800951f8`
- `0x180095280`
- `0x180095338`
- `0x180095410`
- `0x180096494`
- `0x180096c80`
- `0x180097504`
- `0x1800975e4`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x180011f64`
- `0x180028b24`
- `0x180028d60`
- `0x180028edc`
- `0x180029078`
- `0x1800292ac`
- `0x1800292e8`
- `0x1800ceeb8`

## string_xrefs

- `0x180028b61`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\concurrency.cpp`
- `0x180028b4f`: `Mutex::doUnlock() -- detected attempt to unlock a mutex that is not owned by this thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Spectre::Engine::Mutex::doUnlock<&public: void Spectre::Utils::SharedMutex::unlock(void)>(
        Spectre::Utils::SharedMutex *this)
{
  __int64 v2; // rax
  __int64 v3; // r8
  __int64 MutexesLockedByCurrentThread; // rbx
  __int64 v5; // r8
  _QWORD *ThisMutex; // rax
  _BYTE v7[8]; // [rsp+30h] [rbp-98h] BYREF
  _BYTE v8[8]; // [rsp+38h] [rbp-90h] BYREF
  _BYTE v9[32]; // [rsp+40h] [rbp-88h] BYREF
  _BYTE v10[32]; // [rsp+60h] [rbp-68h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+80h] [rbp-48h] BYREF

  if ( !Spectre::Engine::Mutex::this_thread_owns(this) )
  {
    std::string::string(v10, "Mutex::doUnlock() -- detected attempt to unlock a mutex that is not owned by this thread");
    v2 = std::string::string(
           v9,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\concurrency.cpp");
    Spectre::Engine::EngineAccessDeniedException::EngineAccessDeniedException(pExceptionObject, v2, v3, v10);
    throw (Spectre::Engine::EngineAccessDeniedException *)pExceptionObject;
  }
  MutexesLockedByCurrentThread = Spectre::Engine::Mutex::GetMutexesLockedByCurrentThread();
  LOBYTE(v5) = 1;
  ThisMutex = (_QWORD *)Spectre::Engine::Mutex::FindThisMutex(this, v7, v5);
  std::vector<std::pair<Spectre::Engine::Mutex const *,bool>>::erase(MutexesLockedByCurrentThread, v8, *ThisMutex);
  Spectre::Utils::SharedMutex::unlock(this);
}

```

## disassembly

```asm
0x180028b24  mov     [rsp+arg_8], rbx
0x180028b29  push    rdi
0x180028b2a  sub     rsp, 0C0h
0x180028b31  mov     rax, cs:__security_cookie
0x180028b38  xor     rax, rsp
0x180028b3b  mov     [rsp+0C8h+var_10], rax
0x180028b43  mov     rdi, rcx
0x180028b46  call    ?this_thread_owns@Mutex@Engine@Spectre@@QEBA_NXZ; Spectre::Engine::Mutex::this_thread_owns(void)
0x180028b4b  test    al, al
0x180028b4d  jnz     short loc_180028B9C
0x180028b4f  lea     rdx, aMutexDounlockD; "Mutex::doUnlock() -- detected attempt t"...
0x180028b56  lea     rcx, [rsp+0C8h+var_68]
0x180028b5b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180028b60  nop
0x180028b61  lea     rdx, aOnecoreuapWind_51; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180028b68  lea     rcx, [rsp+0C8h+var_88]
0x180028b6d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180028b72  lea     r9, [rsp+0C8h+var_68]
0x180028b77  mov     rdx, rax
0x180028b7a  lea     rcx, [rsp+0C8h+pExceptionObject]
0x180028b82  call    ??0EngineAccessDeniedException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineAccessDeniedException::EngineAccessDeniedException(std::string,int,std::string const &,bool)
0x180028b87  lea     rdx, _TI5?AUEngineAccessDeniedException@Engine@Spectre@@; pThrowInfo
0x180028b8e  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x180028b96  call    _CxxThrowException_0
0x180028b9c  call    ?GetMutexesLockedByCurrentThread@Mutex@Engine@Spectre@@CAAEAV?$vector@U?$pair@PEBVMutex@Engine@Spectre@@_N@std@@V?$allocator@U?$pair@PEBVMutex@Engine@Spectre@@_N@std@@@2@@std@@XZ; Spectre::Engine::Mutex::GetMutexesLockedByCurrentThread(void)
0x180028ba1  mov     rbx, rax
0x180028ba4  mov     r8b, 1
0x180028ba7  lea     rdx, [rsp+0C8h+var_98]
0x180028bac  mov     rcx, rdi
0x180028baf  call    ?FindThisMutex@Mutex@Engine@Spectre@@AEBA?AV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@U?$pair@PEBVMutex@Engine@Spectre@@_N@std@@@std@@@std@@@std@@_N@Z; Spectre::Engine::Mutex::FindThisMutex(bool)
0x180028bb4  mov     r8, [rax]
0x180028bb7  lea     rdx, [rsp+0C8h+var_90]
0x180028bbc  mov     rcx, rbx
0x180028bbf  call    ?erase@?$vector@U?$pair@PEBVMutex@Engine@Spectre@@_N@std@@V?$allocator@U?$pair@PEBVMutex@Engine@Spectre@@_N@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U?$pair@PEBVMutex@Engine@Spectre@@_N@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@U?$pair@PEBVMutex@Engine@Spectre@@_N@std@@@std@@@std@@@2@@Z; std::vector<std::pair<Spectre::Engine::Mutex const *,bool>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::pair<Spectre::Engine::Mutex const *,bool>>>>)
0x180028bc4  mov     rcx, rdi; this
0x180028bc7  call    ?unlock@SharedMutex@Utils@Spectre@@QEAAXXZ; Spectre::Utils::SharedMutex::unlock(void)
0x180028bcc  mov     rcx, [rsp+0C8h+var_10]
0x180028bd4  xor     rcx, rsp; StackCookie
0x180028bd7  call    __security_check_cookie
0x180028bdc  mov     rbx, [rsp+0C8h+arg_8]
0x180028be4  add     rsp, 0C0h
0x180028beb  pop     rdi
0x180028bec  retn
```
