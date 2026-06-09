# Spectre::Engine::Mutex::doLock<&Spectre::Utils::SharedMutex::lock(void)>(bool)

- ea: `0x1800289ac`
- end: `0x180028a62`
- name: `??$doLock@$1?lock@SharedMutex@Utils@Spectre@@QEAAXXZ@Mutex@Engine@Spectre@@AEAAX_N@Z`
- size: `182`
- prototype: `__int64 __fastcall(Spectre::Utils::SharedMutex *this)`
- caller_count: `20`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180025bd0`
- `0x1800263f0`
- `0x180026a2c`
- `0x180028d0c`
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
- `0x1800289ac`
- `0x180028cc4`
- `0x180028d60`
- `0x180029078`
- `0x1800292e8`
- `0x1800cede8`

## string_xrefs

- `0x1800289ea`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\concurrency.cpp`
- `0x1800289d8`: `Mutex::doLock() -- detected recursive lock attempt on non-recursive mutex -- throwing exception to avoid deadlock`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Spectre::Engine::Mutex::doLock<&public: void Spectre::Utils::SharedMutex::lock(void)>(
        Spectre::Utils::SharedMutex *this)
{
  __int64 v2; // rax
  __int64 v3; // r8
  __int64 MutexesLockedByCurrentThread; // rax
  char v6[8]; // [rsp+30h] [rbp-98h] BYREF
  Spectre::Utils::SharedMutex *v7; // [rsp+38h] [rbp-90h] BYREF
  _BYTE v8[32]; // [rsp+40h] [rbp-88h] BYREF
  _BYTE v9[32]; // [rsp+60h] [rbp-68h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+80h] [rbp-48h] BYREF

  v6[0] = 1;
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
  Spectre::Utils::SharedMutex::lock(this);
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
0x1800289ac  push    rbx
0x1800289ae  sub     rsp, 0C0h
0x1800289b5  mov     rax, cs:__security_cookie
0x1800289bc  xor     rax, rsp
0x1800289bf  mov     [rsp+0C8h+var_10], rax
0x1800289c7  mov     rbx, rcx
0x1800289ca  mov     [rsp+0C8h+var_98], 1
0x1800289cf  call    ?this_thread_owns@Mutex@Engine@Spectre@@QEBA_NXZ; Spectre::Engine::Mutex::this_thread_owns(void)
0x1800289d4  test    al, al
0x1800289d6  jz      short loc_180028A25
0x1800289d8  lea     rdx, aMutexDolockDet; "Mutex::doLock() -- detected recursive l"...
0x1800289df  lea     rcx, [rsp+0C8h+var_68]
0x1800289e4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800289e9  nop
0x1800289ea  lea     rdx, aOnecoreuapWind_51; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800289f1  lea     rcx, [rsp+0C8h+var_88]
0x1800289f6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800289fb  lea     r9, [rsp+0C8h+var_68]
0x180028a00  mov     rdx, rax
0x180028a03  lea     rcx, [rsp+0C8h+pExceptionObject]
0x180028a0b  call    ??0EngineAccessDeniedException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineAccessDeniedException::EngineAccessDeniedException(std::string,int,std::string const &,bool)
0x180028a10  lea     rdx, _TI5?AUEngineAccessDeniedException@Engine@Spectre@@; pThrowInfo
0x180028a17  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x180028a1f  call    _CxxThrowException_0
0x180028a25  mov     rcx, rbx; this
0x180028a28  call    ?lock@SharedMutex@Utils@Spectre@@QEAAXXZ; Spectre::Utils::SharedMutex::lock(void)
0x180028a2d  call    ?GetMutexesLockedByCurrentThread@Mutex@Engine@Spectre@@CAAEAV?$vector@U?$pair@PEBVMutex@Engine@Spectre@@_N@std@@V?$allocator@U?$pair@PEBVMutex@Engine@Spectre@@_N@std@@@2@@std@@XZ; Spectre::Engine::Mutex::GetMutexesLockedByCurrentThread(void)
0x180028a32  mov     [rsp+0C8h+var_90], rbx
0x180028a37  lea     r8, [rsp+0C8h+var_98]
0x180028a3c  lea     rdx, [rsp+0C8h+var_90]
0x180028a41  mov     rcx, rax
0x180028a44  call    ??$emplace_back@PEAVMutex@Engine@Spectre@@AEA_N@?$vector@U?$pair@PEBVMutex@Engine@Spectre@@_N@std@@V?$allocator@U?$pair@PEBVMutex@Engine@Spectre@@_N@std@@@2@@std@@QEAAAEAU?$pair@PEBVMutex@Engine@Spectre@@_N@1@$$QEAPEAVMutex@Engine@Spectre@@AEA_N@Z; std::vector<std::pair<Spectre::Engine::Mutex const *,bool>>::emplace_back<Spectre::Engine::Mutex *,bool &>(Spectre::Engine::Mutex * &&,bool &)
0x180028a49  mov     rcx, [rsp+0C8h+var_10]
0x180028a51  xor     rcx, rsp; StackCookie
0x180028a54  call    __security_check_cookie
0x180028a59  add     rsp, 0C0h
0x180028a60  pop     rbx
0x180028a61  retn
```
