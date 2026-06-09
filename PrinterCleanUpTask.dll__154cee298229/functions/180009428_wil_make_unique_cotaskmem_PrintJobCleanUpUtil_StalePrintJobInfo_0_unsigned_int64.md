# wil::make_unique_cotaskmem<PrintJobCleanUpUtil::StalePrintJobInfo [0]>(unsigned __int64)

- ea: `0x180009428`
- end: `0x18000946a`
- name: `??$make_unique_cotaskmem@$$BY0A@UStalePrintJobInfo@PrintJobCleanUpUtil@@@wil@@YA?AV?$unique_ptr@$$BY0A@UStalePrintJobInfo@PrintJobCleanUpUtil@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z`
- size: `66`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000b308`

## callees

- `0x180009428`
- `0x180009470`
- `0x18000f134`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_cotaskmem<PrintJobCleanUpUtil::StalePrintJobInfo [0]>(_QWORD *a1)
{
  unsigned int v2; // r8d
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  wil::make_unique_cotaskmem_nothrow<PrintJobCleanUpUtil::StalePrintJobInfo [0]>(a1);
  if ( !*a1 )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0x1854, v2, v3);
  return a1;
}

```

## disassembly

```asm
0x180009428  mov     [rsp+arg_0], rcx
0x18000942d  push    rbx
0x18000942e  sub     rsp, 30h
0x180009432  mov     rbx, rcx
0x180009435  mov     [rsp+38h+var_18], 0
0x18000943d  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@UStalePrintJobInfo@PrintJobCleanUpUtil@@@wil@@YA?AV?$unique_ptr@$$BY0A@UStalePrintJobInfo@PrintJobCleanUpUtil@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<PrintJobCleanUpUtil::StalePrintJobInfo [0]>(unsigned __int64)
0x180009442  mov     [rsp+38h+var_18], 1
0x18000944a  mov     rcx, [rsp+38h]; this
0x18000944f  cmp     qword ptr [rbx], 0
0x180009453  jnz     short loc_180009460
0x180009455  mov     edx, 1854h; void *
0x18000945a  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180009460  mov     rax, rbx
0x180009463  add     rsp, 30h
0x180009467  pop     rbx
0x180009468  retn
```
