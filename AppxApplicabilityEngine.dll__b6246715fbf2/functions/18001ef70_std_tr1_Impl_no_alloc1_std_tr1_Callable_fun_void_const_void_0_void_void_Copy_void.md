# std::tr1::_Impl_no_alloc1<std::tr1::_Callable_fun<void * (*const)(void *),0>,void *,void *>::_Copy(void *)

- ea: `0x18001ef70`
- end: `0x18001efe5`
- name: `?_Copy@?$_Impl_no_alloc1@U?$_Callable_fun@Q6APEAXPEAX@Z$0A@@tr1@std@@PEAXPEAX@tr1@std@@UEAAPEAV?$_Impl_base1@PEAXPEAX@23@PEAX@Z`
- size: `117`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180011a64`
- `0x180013294`
- `0x18001ef70`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18001efa6`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18001efa6`

## pseudocode

```c
_QWORD *__fastcall std::tr1::_Impl_no_alloc1<std::tr1::_Callable_fun<void * (*const)(void *),0>,void *,void *>::_Copy(
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
  *a2 = &std::tr1::_Impl_no_alloc1<std::tr1::_Callable_fun<void * (*const)(void *),0>,void *,void *>::`vftable';
  a2[1] = *(_QWORD *)(a1 + 8);
  return a2;
}

```

## disassembly

```asm
0x18001ef70  push    rbx
0x18001ef72  sub     rsp, 40h
0x18001ef76  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x18001ef7f  mov     rbx, rcx
0x18001ef82  test    rdx, rdx
0x18001ef85  jnz     short loc_18001EFCA
0x18001ef87  lea     ecx, [rdx+10h]; Size
0x18001ef8a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ef8f  mov     rdx, rax
0x18001ef92  test    rax, rax
0x18001ef95  jnz     short loc_18001EFCA
0x18001ef97  mov     [rsp+48h+arg_8], rax
0x18001ef9c  lea     rdx, [rsp+48h+arg_8]
0x18001efa1  lea     rcx, [rsp+48h+pExceptionObject]
0x18001efa6  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x18001efac  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18001efb3  mov     [rsp+48h+pExceptionObject], rax
0x18001efb8  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001efbf  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001efc4  call    _CxxThrowException_0
0x18001efca  lea     rax, ??_7?$_Impl_no_alloc1@U?$_Callable_fun@Q6APEAXPEAX@Z$0A@@tr1@std@@PEAXPEAX@tr1@std@@6B@; const std::tr1::_Impl_no_alloc1<std::tr1::_Callable_fun<void * (*const)(void *),0>,void *,void *>::`vftable'
0x18001efd1  mov     [rdx], rax
0x18001efd4  mov     rax, [rbx+8]
0x18001efd8  mov     [rdx+8], rax
0x18001efdc  mov     rax, rdx
0x18001efdf  add     rsp, 40h
0x18001efe3  pop     rbx
0x18001efe4  retn
```
