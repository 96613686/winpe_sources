# Spectre::Engine::Lockable::VerifyReadAccess(void)

- ea: `0x180029178`
- end: `0x180029215`
- name: `?VerifyReadAccess@Lockable@Engine@Spectre@@QEBAXXZ`
- size: `157`
- prototype: `void __fastcall(Spectre::Engine::Lockable *__hidden this)`
- caller_count: `18`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002c6c4`
- `0x18003bf04`
- `0x18003e878`
- `0x18003e8d8`
- `0x18003e9fc`
- `0x18003eaac`
- `0x18003eb80`
- `0x18003ec58`
- `0x18003f60c`
- `0x18005c920`
- `0x18005ca5c`
- `0x18005cb98`
- `0x18005ccd4`
- `0x18005ce10`
- `0x18005cf4c`
- `0x180060fac`
- `0x18006b058`
- `0x18006c380`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x180011f64`
- `0x180028d60`
- `0x180029178`
- `0x180029328`

## string_xrefs

- `0x1800291c7`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\concurrency.cpp`
- `0x1800291b5`: `Lockable::VerifyReadAccess() -- SHARED OR EXCLUSIVE LOCK REQUIRED\nThe requested operation requires that the current thread holds this lockable object's mutex lock for exclusive (read/write) or shared (read-only) access.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Spectre::Engine::Lockable::VerifyReadAccess(Spectre::Engine::Lockable *this)
{
  __int64 v2; // rax
  __int64 v3; // r8
  _BYTE v4[32]; // [rsp+38h] [rbp-90h] BYREF
  _BYTE v5[32]; // [rsp+58h] [rbp-70h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+78h] [rbp-50h] BYREF

  if ( *((_DWORD *)this + 6) == 1
    && !Spectre::Engine::Mutex::this_thread_owns(this, 0)
    && !Spectre::Engine::Mutex::this_thread_owns(this, 1) )
  {
    std::string::string(
      v5,
      "Lockable::VerifyReadAccess() -- SHARED OR EXCLUSIVE LOCK REQUIRED\n"
      "The requested operation requires that the current thread holds this lockable object's mutex lock for exclusive (re"
      "ad/write) or shared (read-only) access.\n");
    v2 = std::string::string(
           v4,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\concurrency.cpp");
    Spectre::Engine::EngineAccessDeniedException::EngineAccessDeniedException(pExceptionObject, v2, v3, v5);
    throw (Spectre::Engine::EngineAccessDeniedException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x180029178  push    rbx
0x18002917a  sub     rsp, 0C0h
0x180029181  mov     rax, cs:__security_cookie
0x180029188  xor     rax, rsp
0x18002918b  mov     [rsp+0C8h+var_18], rax
0x180029193  mov     rbx, rcx
0x180029196  cmp     dword ptr [rcx+18h], 1
0x18002919a  jnz     short loc_1800291FC
0x18002919c  xor     edx, edx; bool
0x18002919e  call    ?this_thread_owns@Mutex@Engine@Spectre@@QEBA_N_N@Z; Spectre::Engine::Mutex::this_thread_owns(bool)
0x1800291a3  test    al, al
0x1800291a5  jnz     short loc_1800291FC
0x1800291a7  mov     dl, 1; bool
0x1800291a9  mov     rcx, rbx; this
0x1800291ac  call    ?this_thread_owns@Mutex@Engine@Spectre@@QEBA_N_N@Z; Spectre::Engine::Mutex::this_thread_owns(bool)
0x1800291b1  test    al, al
0x1800291b3  jnz     short loc_1800291FC
0x1800291b5  lea     rdx, aLockableVerify; "Lockable::VerifyReadAccess() -- SHARED "...
0x1800291bc  lea     rcx, [rsp+0C8h+var_70]
0x1800291c1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800291c6  nop
0x1800291c7  lea     rdx, aOnecoreuapWind_51; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800291ce  lea     rcx, [rsp+0C8h+var_90]
0x1800291d3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800291d8  lea     r9, [rsp+0C8h+var_70]
0x1800291dd  mov     rdx, rax
0x1800291e0  lea     rcx, [rsp+0C8h+pExceptionObject]
0x1800291e5  call    ??0EngineAccessDeniedException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineAccessDeniedException::EngineAccessDeniedException(std::string,int,std::string const &,bool)
0x1800291ea  lea     rdx, _TI5?AUEngineAccessDeniedException@Engine@Spectre@@; pThrowInfo
0x1800291f1  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x1800291f6  call    _CxxThrowException_0
0x1800291fc  mov     rcx, [rsp+0C8h+var_18]
0x180029204  xor     rcx, rsp; StackCookie
0x180029207  call    __security_check_cookie
0x18002920c  add     rsp, 0C0h
0x180029213  pop     rbx
0x180029214  retn
```
