# CommonUtil::HrFromStdException(std::exception const &)

- ea: `0x14000ebd0`
- end: `0x14000ebf2`
- name: `?HrFromStdException@CommonUtil@@YAJAEBVexception@std@@@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(CommonUtil *__hidden this, const struct std::exception *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000fbd8`
- `0x14000fc04`
- `0x14000fcad`

## callees

- `0x1400022f8`
- `0x14000ebd0`

## pseudocode

```c
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
    *((_DWORD *)v2 + 24) = v3;
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
0x14000ebd0  mov     [rsp+arg_0], rcx
0x14000ebd5  sub     rsp, 58h
0x14000ebd9  xor     edx, edx; pThrowInfo
0x14000ebdb  xor     ecx, ecx; pExceptionObject
0x14000ebdd  call    _CxxThrowException_0
0x14000ebe3  mov     eax, dword ptr [rsp+58h+arg_0]
0x14000ebe7  add     rsp, 58h
0x14000ebeb  retn
0x14000ebec  jmp     short loc_14000EBE3
0x14000ebee  jmp     short loc_14000EBE3
0x14000ebf0  jmp     short loc_14000EBE3
```
