# Spectre::Engine::Lockable::GetExclusiveLockIfNecessary(void)

- ea: `0x180028f78`
- end: `0x18002906f`
- name: `?GetExclusiveLockIfNecessary@Lockable@Engine@Spectre@@QEAA?AV?$unique_lock@VMutex@Engine@Spectre@@@std@@XZ`
- size: `247`
- prototype: `__int64 __fastcall(Spectre::Engine::Mutex *this)`
- caller_count: `58`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800119a0`
- `0x180012744`
- `0x1800137d0`
- `0x180013a60`
- `0x180013b20`
- `0x180013fd0`
- `0x18001522c`
- `0x180015300`
- `0x180015460`
- `0x18001557c`
- `0x1800156a0`
- `0x180015a30`
- `0x180015ba0`
- `0x180015d40`
- `0x180015dc0`
- `0x180015ec0`
- `0x180016d58`
- `0x180016e44`
- `0x180016f30`
- `0x180018df0`
- `0x180019380`
- `0x1800199a0`
- `0x180019f88`
- `0x18001c060`
- `0x180023ff8`
- `0x180024244`
- `0x1800258e8`
- `0x1800261bc`
- `0x1800264d8`
- `0x1800316f0`
- `0x180031820`
- `0x180031efc`
- `0x1800324f0`
- `0x180032e10`
- `0x180033c10`
- `0x1800343b4`
- `0x180034434`
- `0x1800345ec`
- `0x180035c90`
- `0x180039748`
- `0x180040ab4`
- `0x180044534`
- `0x180044640`
- `0x180049d74`
- `0x180049e40`
- `0x180049f0c`
- `0x180049fd8`
- `0x18004a0a4`
- `0x18005355c`
- `0x180059af8`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x180011f64`
- `0x1800120ec`
- `0x180018830`
- `0x180028f40`
- `0x180028f78`
- `0x180029328`
- `0x1800681a8`

## string_xrefs

- `0x180028fc7`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\concurrency.cpp`
- `0x180028fb5`: `Attempt to get exclusive lock failed due to mutex already being locked in shared mode`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Spectre::Engine::Lockable::GetExclusiveLockIfNecessary(Spectre::Engine::Mutex *this, __int64 a2)
{
  int v4; // eax
  int v5; // r8d
  __int64 ExclusiveLock; // rax
  _BYTE v8[16]; // [rsp+38h] [rbp-A0h] BYREF
  __int64 v9; // [rsp+48h] [rbp-90h]
  _BYTE v10[32]; // [rsp+50h] [rbp-88h] BYREF
  _BYTE v11[32]; // [rsp+70h] [rbp-68h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+90h] [rbp-48h] BYREF

  v9 = a2;
  if ( Spectre::Engine::Mutex::this_thread_owns(this, 0) )
  {
    std::string::string(v11, "Attempt to get exclusive lock failed due to mutex already being locked in shared mode");
    v4 = std::string::string(
           v10,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\concurrency.cpp");
    Spectre::Engine::EngineException::EngineException((unsigned int)pExceptionObject, v4, v5, (unsigned int)v11, 0);
    throw (Spectre::Engine::EngineException *)pExceptionObject;
  }
  *(_QWORD *)a2 = 0;
  *(_BYTE *)(a2 + 8) = 0;
  if ( !Spectre::Engine::Mutex::this_thread_owns(this, 1) )
  {
    ExclusiveLock = Spectre::Engine::Lockable::GetExclusiveLock(this, v8);
    std::unique_lock<Spectre::Engine::Mutex>::operator=(a2, ExclusiveLock);
    std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(v8);
  }
  return a2;
}

```

## disassembly

```asm
0x180028f78  mov     [rsp+arg_10], rbx
0x180028f7d  push    rdi
0x180028f7e  sub     rsp, 0D0h
0x180028f85  mov     rax, cs:__security_cookie
0x180028f8c  xor     rax, rsp
0x180028f8f  mov     [rsp+0D8h+var_10], rax
0x180028f97  mov     rbx, rdx
0x180028f9a  mov     rdi, rcx
0x180028f9d  mov     [rsp+0D8h+var_90], rdx
0x180028fa2  mov     [rsp+0D8h+var_A8], 0
0x180028faa  xor     edx, edx; bool
0x180028fac  call    ?this_thread_owns@Mutex@Engine@Spectre@@QEBA_N_N@Z; Spectre::Engine::Mutex::this_thread_owns(bool)
0x180028fb1  test    al, al
0x180028fb3  jz      short loc_180029007
0x180028fb5  lea     rdx, aAttemptToGetEx; "Attempt to get exclusive lock failed du"...
0x180028fbc  lea     rcx, [rsp+0D8h+var_68]
0x180028fc1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180028fc6  nop
0x180028fc7  lea     rdx, aOnecoreuapWind_51; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180028fce  lea     rcx, [rsp+0D8h+var_88]
0x180028fd3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180028fd8  mov     [rsp+0D8h+var_B8], 0
0x180028fdd  lea     r9, [rsp+0D8h+var_68]
0x180028fe2  mov     rdx, rax
0x180028fe5  lea     rcx, [rsp+0D8h+pExceptionObject]
0x180028fed  call    ??0EngineException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineException::EngineException(std::string,int,std::string const &,bool)
0x180028ff2  lea     rdx, _TI4?AUEngineException@Engine@Spectre@@; pThrowInfo
0x180028ff9  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x180029001  call    _CxxThrowException_0
0x180029007  mov     qword ptr [rbx], 0
0x18002900e  mov     byte ptr [rbx+8], 0
0x180029012  mov     [rsp+0D8h+var_A8], 1
0x18002901a  mov     dl, 1; bool
0x18002901c  mov     rcx, rdi; this
0x18002901f  call    ?this_thread_owns@Mutex@Engine@Spectre@@QEBA_N_N@Z; Spectre::Engine::Mutex::this_thread_owns(bool)
0x180029024  test    al, al
0x180029026  jnz     short loc_18002904A
0x180029028  lea     rdx, [rsp+0D8h+var_A0]
0x18002902d  mov     rcx, rdi
0x180029030  call    ?GetExclusiveLock@Lockable@Engine@Spectre@@QEAA?AV?$unique_lock@VMutex@Engine@Spectre@@@std@@XZ; Spectre::Engine::Lockable::GetExclusiveLock(void)
0x180029035  mov     rdx, rax
0x180029038  mov     rcx, rbx
0x18002903b  call    ??4?$unique_lock@VMutex@Engine@Spectre@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_lock<Spectre::Engine::Mutex>::operator=(std::unique_lock<Spectre::Engine::Mutex> &&)
0x180029040  lea     rcx, [rsp+0D8h+var_A0]
0x180029045  call    ??1?$unique_lock@VMutex@Engine@Spectre@@@std@@QEAA@XZ; std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(void)
0x18002904a  mov     rax, rbx
0x18002904d  mov     rcx, [rsp+0D8h+var_10]
0x180029055  xor     rcx, rsp; StackCookie
0x180029058  call    __security_check_cookie
0x18002905d  mov     rbx, [rsp+0D8h+arg_10]
0x180029065  add     rsp, 0D0h
0x18002906c  pop     rdi
0x18002906d  retn
```
