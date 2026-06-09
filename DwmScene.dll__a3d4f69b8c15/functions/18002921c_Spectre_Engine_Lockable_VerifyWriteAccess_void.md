# Spectre::Engine::Lockable::VerifyWriteAccess(void)

- ea: `0x18002921c`
- end: `0x1800292a5`
- name: `?VerifyWriteAccess@Lockable@Engine@Spectre@@QEBAXXZ`
- size: `137`
- prototype: `void __fastcall(Spectre::Engine::Lockable *__hidden this)`
- caller_count: `47`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800126b0`
- `0x180016a30`
- `0x180025b4c`
- `0x180025ba0`
- `0x180025f80`
- `0x180026100`
- `0x18002a9b0`
- `0x18002c80c`
- `0x180031820`
- `0x180032720`
- `0x180033c10`
- `0x180033dd0`
- `0x18003bf44`
- `0x18003dffc`
- `0x18003e32c`
- `0x18003e640`
- `0x18003e950`
- `0x18003eec8`
- `0x18003f428`
- `0x18003fbe4`
- `0x18003feb4`
- `0x1800416f0`
- `0x180048040`
- `0x180055880`
- `0x1800575e4`
- `0x1800578d0`
- `0x18005ad30`
- `0x18005b2fc`
- `0x18005d440`
- `0x18006b058`
- `0x18006c380`
- `0x18006c758`
- `0x18007b480`
- `0x18007d6d4`
- `0x18007f87c`
- `0x18008c630`
- `0x1800b3a44`
- `0x1800b3bf0`
- `0x1800b3d9c`
- `0x1800b3f48`
- `0x1800b40f4`
- `0x1800b6324`
- `0x1800b7370`
- `0x1800b73b0`
- `0x1800b9950`
- `0x1800bfb68`
- `0x1800c7dd0`

## callees

- `0x18000ca90`
- `0x18000dfa2`
- `0x180011f64`
- `0x180028d60`
- `0x18002921c`
- `0x180029328`

## string_xrefs

- `0x180029258`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\concurrency.cpp`
- `0x180029246`: `Lockable::VerifyWriteAccess() -- EXCLUSIVE LOCK REQUIRED\nThe requested operation requires that the current thread holds this lockable object's mutex lock exclusive (read/write) access.\nTo acquire exclusive lock from C++, call Lockable::GetExclusiveLock() and hold the lock via: auto lock(object->GetExclusiveLock()) { ... }\nTo acquire exclusive lock from C#, call Lockable.GetExclusiveLock() and hold the lock via: using (object.GetExclusiveLock()) { ... }\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Spectre::Engine::Lockable::VerifyWriteAccess(Spectre::Engine::Lockable *this)
{
  __int64 v1; // rax
  __int64 v2; // r8
  _BYTE v3[32]; // [rsp+38h] [rbp-90h] BYREF
  _BYTE v4[32]; // [rsp+58h] [rbp-70h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+78h] [rbp-50h] BYREF

  if ( *((_DWORD *)this + 6) == 1 && !Spectre::Engine::Mutex::this_thread_owns(this, 1) )
  {
    std::string::string(
      v4,
      "Lockable::VerifyWriteAccess() -- EXCLUSIVE LOCK REQUIRED\n"
      "The requested operation requires that the current thread holds this lockable object's mutex lock exclusive (read/w"
      "rite) access.\n"
      "To acquire exclusive lock from C++, call Lockable::GetExclusiveLock() and hold the lock via: auto lock(object->Get"
      "ExclusiveLock()) { ... }\n"
      "To acquire exclusive lock from C#, call Lockable.GetExclusiveLock() and hold the lock via: using (object.GetExclus"
      "iveLock()) { ... }\n");
    v1 = std::string::string(
           v3,
           "onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\concurrency.cpp");
    Spectre::Engine::EngineAccessDeniedException::EngineAccessDeniedException(pExceptionObject, v1, v2, v4);
    throw (Spectre::Engine::EngineAccessDeniedException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x18002921c  sub     rsp, 0C8h
0x180029223  mov     rax, cs:__security_cookie
0x18002922a  xor     rax, rsp
0x18002922d  mov     [rsp+0C8h+var_18], rax
0x180029235  cmp     dword ptr [rcx+18h], 1
0x180029239  jnz     short loc_18002928D
0x18002923b  mov     dl, 1; bool
0x18002923d  call    ?this_thread_owns@Mutex@Engine@Spectre@@QEBA_N_N@Z; Spectre::Engine::Mutex::this_thread_owns(bool)
0x180029242  test    al, al
0x180029244  jnz     short loc_18002928D
0x180029246  lea     rdx, aLockableVerify_0; "Lockable::VerifyWriteAccess() -- EXCLUS"...
0x18002924d  lea     rcx, [rsp+0C8h+var_70]
0x180029252  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180029257  nop
0x180029258  lea     rdx, aOnecoreuapWind_51; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18002925f  lea     rcx, [rsp+0C8h+var_90]
0x180029264  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180029269  lea     r9, [rsp+0C8h+var_70]
0x18002926e  mov     rdx, rax
0x180029271  lea     rcx, [rsp+0C8h+pExceptionObject]
0x180029276  call    ??0EngineAccessDeniedException@Engine@Spectre@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HAEBV34@_N@Z; Spectre::Engine::EngineAccessDeniedException::EngineAccessDeniedException(std::string,int,std::string const &,bool)
0x18002927b  lea     rdx, _TI5?AUEngineAccessDeniedException@Engine@Spectre@@; pThrowInfo
0x180029282  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x180029287  call    _CxxThrowException_0
0x18002928d  mov     rcx, [rsp+0C8h+var_18]
0x180029295  xor     rcx, rsp; StackCookie
0x180029298  call    __security_check_cookie
0x18002929d  add     rsp, 0C8h
0x1800292a4  retn
```
