# std::tr1::_Impl_no_alloc1<std::tr1::_Callable_fun<long (*const)(HKEY__ *),0>,long,HKEY__ *>::_Copy(void *)

- ea: `0x180020e60`
- end: `0x180020ed5`
- name: `?_Copy@?$_Impl_no_alloc1@U?$_Callable_fun@Q6AJPEAUHKEY__@@@Z$0A@@tr1@std@@JPEAUHKEY__@@@tr1@std@@UEAAPEAV?$_Impl_base1@JPEAUHKEY__@@@23@PEAX@Z`
- size: `117`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180011a64`
- `0x180013294`
- `0x180020e60`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180020e96`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180020e96`

## pseudocode

```c
_QWORD *__fastcall std::tr1::_Impl_no_alloc1<std::tr1::_Callable_fun<long (*const)(HKEY__ *),0>,long,HKEY__ *>::_Copy(
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
  *a2 = &std::tr1::_Impl_no_alloc1<std::tr1::_Callable_fun<long (*const)(HKEY__ *),0>,long,HKEY__ *>::`vftable';
  a2[1] = *(_QWORD *)(a1 + 8);
  return a2;
}

```

## disassembly

```asm
0x180020e60  push    rbx
0x180020e62  sub     rsp, 40h
0x180020e66  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x180020e6f  mov     rbx, rcx
0x180020e72  test    rdx, rdx
0x180020e75  jnz     short loc_180020EBA
0x180020e77  lea     ecx, [rdx+10h]; Size
0x180020e7a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020e7f  mov     rdx, rax
0x180020e82  test    rax, rax
0x180020e85  jnz     short loc_180020EBA
0x180020e87  mov     [rsp+48h+arg_8], rax
0x180020e8c  lea     rdx, [rsp+48h+arg_8]
0x180020e91  lea     rcx, [rsp+48h+pExceptionObject]
0x180020e96  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x180020e9c  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180020ea3  mov     [rsp+48h+pExceptionObject], rax
0x180020ea8  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180020eaf  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180020eb4  call    _CxxThrowException_0
0x180020eba  lea     rax, ??_7?$_Impl_no_alloc1@U?$_Callable_fun@Q6AJPEAUHKEY__@@@Z$0A@@tr1@std@@JPEAUHKEY__@@@tr1@std@@6B@; const std::tr1::_Impl_no_alloc1<std::tr1::_Callable_fun<long (*const)(HKEY__ *),0>,long,HKEY__ *>::`vftable'
0x180020ec1  mov     [rdx], rax
0x180020ec4  mov     rax, [rbx+8]
0x180020ec8  mov     [rdx+8], rax
0x180020ecc  mov     rax, rdx
0x180020ecf  add     rsp, 40h
0x180020ed3  pop     rbx
0x180020ed4  retn
```
