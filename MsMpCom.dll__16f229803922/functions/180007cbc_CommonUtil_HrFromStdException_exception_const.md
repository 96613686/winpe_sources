# CommonUtil::HrFromStdException(exception const &)

- ea: `0x180007cbc`
- end: `0x180007cde`
- name: `?HrFromStdException@CommonUtil@@YAJAEBVexception@@@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(CommonUtil *__hidden this, const struct exception *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000999f`
- `0x180009ada`
- `0x180009bb7`

## callees

- `0x180001ccc`
- `0x180007cbc`

## pseudocode

```c
void __fastcall __noreturn CommonUtil::HrFromStdException(CommonUtil *this, const struct exception *a2)
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
  const exception *v11; // [rsp+40h] [rbp-18h] BYREF

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
  catch ( const exception *v11 )
  {
    return;
  }
}

```

## disassembly

```asm
0x180007cbc  mov     [rsp+arg_0], rcx
0x180007cc1  sub     rsp, 58h
0x180007cc5  xor     edx, edx; pThrowInfo
0x180007cc7  xor     ecx, ecx; pExceptionObject
0x180007cc9  call    _CxxThrowException_0
0x180007ccf  mov     eax, dword ptr [rsp+58h+arg_0]
0x180007cd3  add     rsp, 58h
0x180007cd7  retn
0x180007cd8  jmp     short loc_180007CCF
0x180007cda  jmp     short loc_180007CCF
0x180007cdc  jmp     short loc_180007CCF
```
