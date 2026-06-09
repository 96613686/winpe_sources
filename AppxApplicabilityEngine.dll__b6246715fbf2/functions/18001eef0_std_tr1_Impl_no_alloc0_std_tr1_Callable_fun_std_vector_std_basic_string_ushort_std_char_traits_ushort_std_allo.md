# std::tr1::_Impl_no_alloc0<std::tr1::_Callable_fun<std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> (*const)(void),0>,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>::_Copy(void *)

- ea: `0x18001eef0`
- end: `0x18001ef65`
- name: `?_Copy@?$_Impl_no_alloc0@U?$_Callable_fun@Q6A?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ$0A@@tr1@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@3@@tr1@std@@UEAAPEAV?$_Impl_base0@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@23@PEAX@Z`
- size: `117`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180011a64`
- `0x180013294`
- `0x18001eef0`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18001ef26`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18001ef26`

## pseudocode

```c
_QWORD *__fastcall std::tr1::_Impl_no_alloc0<std::tr1::_Callable_fun<std::vector<std::wstring> (*const)(void),0>,std::vector<std::wstring>>::_Copy(
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
  *a2 = &std::tr1::_Impl_no_alloc0<std::tr1::_Callable_fun<std::vector<std::wstring> (*const)(void),0>,std::vector<std::wstring>>::`vftable';
  a2[1] = *(_QWORD *)(a1 + 8);
  return a2;
}

```

## disassembly

```asm
0x18001eef0  push    rbx
0x18001eef2  sub     rsp, 40h
0x18001eef6  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x18001eeff  mov     rbx, rcx
0x18001ef02  test    rdx, rdx
0x18001ef05  jnz     short loc_18001EF4A
0x18001ef07  lea     ecx, [rdx+10h]; Size
0x18001ef0a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ef0f  mov     rdx, rax
0x18001ef12  test    rax, rax
0x18001ef15  jnz     short loc_18001EF4A
0x18001ef17  mov     [rsp+48h+arg_8], rax
0x18001ef1c  lea     rdx, [rsp+48h+arg_8]
0x18001ef21  lea     rcx, [rsp+48h+pExceptionObject]
0x18001ef26  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x18001ef2c  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18001ef33  mov     [rsp+48h+pExceptionObject], rax
0x18001ef38  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001ef3f  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001ef44  call    _CxxThrowException_0
0x18001ef4a  lea     rax, ??_7?$_Impl_no_alloc0@U?$_Callable_fun@Q6A?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ$0A@@tr1@std@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@3@@tr1@std@@6B@; const std::tr1::_Impl_no_alloc0<std::tr1::_Callable_fun<std::vector<std::wstring> (*const)(void),0>,std::vector<std::wstring>>::`vftable'
0x18001ef51  mov     [rdx], rax
0x18001ef54  mov     rax, [rbx+8]
0x18001ef58  mov     [rdx+8], rax
0x18001ef5c  mov     rax, rdx
0x18001ef5f  add     rsp, 40h
0x18001ef63  pop     rbx
0x18001ef64  retn
```
