# pplx::task<BingOnlineServices::CopyrightData>::get(void)

- ea: `0x18001d35c`
- end: `0x18001d41c`
- name: `?get@?$task@VCopyrightData@BingOnlineServices@@@pplx@@QEBA?AVCopyrightData@BingOnlineServices@@XZ`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180017b30`

## callees

- `0x18000d090`
- `0x18000dce0`
- `0x1800164a4`
- `0x180016c88`
- `0x18001d040`
- `0x18001d35c`

## import_xrefs

- `BingOnlineServices!??0CopyrightData@BingOnlineServices@@QEAA@AEBV01@@Z` at `0x18001d3f5`
- `BingOnlineServices!??0CopyrightData@BingOnlineServices@@QEAA@AEBV01@@Z` at `0x18001d3f5`

## string_xrefs

- `0x18001d38b`: `get() cannot be called on a default constructed task.`

## pseudocode

```c
BingOnlineServices::CopyrightData *__fastcall pplx::task<BingOnlineServices::CopyrightData>::get(
        __int64 a1,
        BingOnlineServices::CopyrightData *a2)
{
  void **pExceptionObject; // [rsp+40h] [rbp-48h] BYREF
  __int128 v6; // [rsp+48h] [rbp-40h]
  _BYTE v7[32]; // [rsp+58h] [rbp-30h] BYREF

  if ( !*(_QWORD *)a1 )
  {
    pplx::invalid_operation::invalid_operation(
      (pplx::invalid_operation *)&pExceptionObject,
      "get() cannot be called on a default constructed task.");
    throw (pplx::invalid_operation *)&pExceptionObject;
  }
  if ( (unsigned int)pplx::details::_Task_impl_base::_Wait() == 2 )
  {
    pExceptionObject = &Json::Exception::`vftable';
    v6 = 0;
    std::string::string(v7);
    throw (pplx::task_canceled *)&pExceptionObject;
  }
  BingOnlineServices::CopyrightData::CopyrightData(
    a2,
    (const struct BingOnlineServices::CopyrightData *)(*(_QWORD *)a1 + 192LL));
  return a2;
}

```

## disassembly

```asm
0x18001d35c  mov     [rsp+arg_10], rbx
0x18001d361  push    rdi
0x18001d362  sub     rsp, 80h
0x18001d369  mov     rax, cs:__security_cookie
0x18001d370  xor     rax, rsp
0x18001d373  mov     [rsp+88h+var_10], rax
0x18001d378  mov     rdi, rcx
0x18001d37b  mov     [rsp+88h+var_58], rdx
0x18001d380  mov     rcx, [rcx]
0x18001d383  mov     rbx, rdx
0x18001d386  test    rcx, rcx
0x18001d389  jnz     short loc_18001D3AE
0x18001d38b  lea     rdx, aGetCannotBeCal; "get() cannot be called on a default con"...
0x18001d392  lea     rcx, [rsp+88h+pExceptionObject]; this
0x18001d397  call    ??0invalid_operation@pplx@@QEAA@PEBD@Z; pplx::invalid_operation::invalid_operation(char const *)
0x18001d39c  lea     rdx, _TI2?AVinvalid_operation@pplx@@; pThrowInfo
0x18001d3a3  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18001d3a8  call    _CxxThrowException_0
0x18001d3ae  call    ?_Wait@_Task_impl_base@details@pplx@@QEAA?AW4task_group_status@3@XZ; pplx::details::_Task_impl_base::_Wait(void)
0x18001d3b3  cmp     eax, 2
0x18001d3b6  jnz     short loc_18001D3E8
0x18001d3b8  xorps   xmm0, xmm0
0x18001d3bb  lea     rax, ??_7Exception@Json@@6B@; const Json::Exception::`vftable'
0x18001d3c2  lea     rcx, [rsp+88h+var_30]
0x18001d3c7  mov     [rsp+88h+pExceptionObject], rax
0x18001d3cc  movups  [rsp+88h+var_40], xmm0
0x18001d3d1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18001d3d6  lea     rdx, _TI2?AVtask_canceled@pplx@@; pThrowInfo
0x18001d3dd  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18001d3e2  call    _CxxThrowException_0
0x18001d3e8  mov     rdx, [rdi]
0x18001d3eb  mov     rcx, rbx
0x18001d3ee  add     rdx, 0C0h
0x18001d3f5  call    cs:__imp_??0CopyrightData@BingOnlineServices@@QEAA@AEBV01@@Z; BingOnlineServices::CopyrightData::CopyrightData(BingOnlineServices::CopyrightData const &)
0x18001d3fb  mov     rax, rbx
0x18001d3fe  mov     rcx, [rsp+88h+var_10]
0x18001d403  xor     rcx, rsp; StackCookie
0x18001d406  call    __security_check_cookie
0x18001d40b  mov     rbx, [rsp+88h+arg_10]
0x18001d413  add     rsp, 80h
0x18001d41a  pop     rdi
0x18001d41b  retn
```
