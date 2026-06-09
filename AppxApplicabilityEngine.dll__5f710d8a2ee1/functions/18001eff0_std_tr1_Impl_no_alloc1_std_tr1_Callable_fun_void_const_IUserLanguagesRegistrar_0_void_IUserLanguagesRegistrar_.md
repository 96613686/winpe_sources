# std::tr1::_Impl_no_alloc1<std::tr1::_Callable_fun<void (*const)(IUserLanguagesRegistrar *),0>,void,IUserLanguagesRegistrar *>::_Copy(void *)

- ea: `0x18001eff0`
- end: `0x18001f065`
- name: `?_Copy@?$_Impl_no_alloc1@U?$_Callable_fun@Q6AXPEAVIUserLanguagesRegistrar@@@Z$0A@@tr1@std@@XPEAVIUserLanguagesRegistrar@@@tr1@std@@UEAAPEAV?$_Impl_base1@XPEAVIUserLanguagesRegistrar@@@23@PEAX@Z`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180011a64`
- `0x180013294`
- `0x18001eff0`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18001f026`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18001f026`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall std::tr1::_Impl_no_alloc1<std::tr1::_Callable_fun<void (*const)(IUserLanguagesRegistrar *),0>,void,IUserLanguagesRegistrar *>::_Copy(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD pExceptionObject[4]; // [rsp+28h] [rbp-20h] BYREF
  const char *v5; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 )
  {
    a2 = operator new(0x10u);
    if ( !a2 )
    {
      v5 = 0;
      exception::exception((exception *)pExceptionObject, &v5);
      pExceptionObject[0] = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)pExceptionObject;
    }
  }
  *a2 = &std::tr1::_Impl_no_alloc1<std::tr1::_Callable_fun<void (*const)(IUserLanguagesRegistrar *),0>,void,IUserLanguagesRegistrar *>::`vftable';
  a2[1] = *(_QWORD *)(a1 + 8);
  return a2;
}

```

## disassembly

```asm
0x18001eff0  push    rbx
0x18001eff2  sub     rsp, 40h
0x18001eff6  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x18001efff  mov     rbx, rcx
0x18001f002  test    rdx, rdx
0x18001f005  jnz     short loc_18001F04A
0x18001f007  lea     ecx, [rdx+10h]; Size
0x18001f00a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f00f  mov     rdx, rax
0x18001f012  test    rax, rax
0x18001f015  jnz     short loc_18001F04A
0x18001f017  mov     [rsp+48h+arg_8], rax
0x18001f01c  lea     rdx, [rsp+48h+arg_8]
0x18001f021  lea     rcx, [rsp+48h+pExceptionObject]
0x18001f026  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x18001f02c  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18001f033  mov     [rsp+48h+pExceptionObject], rax
0x18001f038  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001f03f  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001f044  call    _CxxThrowException_0
0x18001f04a  lea     rax, ??_7?$_Impl_no_alloc1@U?$_Callable_fun@Q6AXPEAVIUserLanguagesRegistrar@@@Z$0A@@tr1@std@@XPEAVIUserLanguagesRegistrar@@@tr1@std@@6B@; const std::tr1::_Impl_no_alloc1<std::tr1::_Callable_fun<void (*const)(IUserLanguagesRegistrar *),0>,void,IUserLanguagesRegistrar *>::`vftable'
0x18001f051  mov     [rdx], rax
0x18001f054  mov     rax, [rbx+8]
0x18001f058  mov     [rdx+8], rax
0x18001f05c  mov     rax, rdx
0x18001f05f  add     rsp, 40h
0x18001f063  pop     rbx
0x18001f064  retn
```
