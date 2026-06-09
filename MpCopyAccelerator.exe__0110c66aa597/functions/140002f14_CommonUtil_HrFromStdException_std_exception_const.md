# CommonUtil::HrFromStdException(std::exception const &)

- ea: `0x140002f14`
- end: `0x140002f31`
- name: `?HrFromStdException@CommonUtil@@YAJAEBVexception@std@@@Z`
- size: `29`
- prototype: `void __fastcall __noreturn(CommonUtil *__hidden this, const struct std::exception *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400259e8`
- `0x140026216`
- `0x14002627c`

## callees

- `0x140002f14`
- `0x140007c1c`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void __fastcall __noreturn CommonUtil::HrFromStdException(CommonUtil *this, const struct std::exception *a2)
{
  __int64 *v2; // rbp
  int v3; // eax
  int v4; // ecx
  __int64 *v5; // rdx
  __int64 v6; // [rsp+0h] [rbp-58h] BYREF
  const CommonUtil::CHResultException *v7; // [rsp+20h] [rbp-38h] BYREF
  const std::bad_alloc *v8; // [rsp+28h] [rbp-30h] BYREF
  const std::out_of_range *v9; // [rsp+30h] [rbp-28h] BYREF
  const std::invalid_argument *v10; // [rsp+38h] [rbp-20h] BYREF
  const std::exception *v11; // [rsp+40h] [rbp-18h] BYREF

  try
  {
    throw;
  }
  catch ( const CommonUtil::CHResultException *v7 )
  {
    v5 = &v6;
    v2 = v5;
    v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5[4] + 16LL))(v5[4]);
    v4 = -2147418113;
    if ( v3 >= 0 )
      v3 = v4;
    *((_DWORD *)v2 + 26) = v3;
    return;
  }
  catch ( const std::bad_alloc *v8 )
  {
    return;
  }
  catch ( const std::out_of_range *v9 )
  {
    return;
  }
  catch ( const std::invalid_argument *v10 )
  {
    return;
  }
  catch ( const std::exception *v11 )
  {
    return;
  }
}

```

## disassembly

```asm
0x140002f14  sub     rsp, 58h
0x140002f18  xor     edx, edx; pThrowInfo
0x140002f1a  xor     ecx, ecx; pExceptionObject
0x140002f1c  call    _CxxThrowException
0x140002f22  mov     eax, [rsp+arg_60]
0x140002f26  add     rsp, 58h
0x140002f2a  retn
0x140002f2b  jmp     short loc_140002F22
0x140002f2d  jmp     short loc_140002F22
0x140002f2f  jmp     short loc_140002F22
```
