# errorlib::scoped_error<hresult_error::tag>::receive<long>(long &&)

- ea: `0x1400076b4`
- end: `0x1400076e2`
- name: `??$receive@J@?$scoped_error@Utag@hresult_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z`
- size: `46`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140008784`
- `0x140009434`
- `0x1400098b0`
- `0x14000f54c`

## callees

- `0x140005e68`
- `0x140008728`

## pseudocode

```c
__int64 __fastcall errorlib::scoped_error<hresult_error::tag>::receive<long>(__int64 a1, __int64 a2)
{
  char v4; // [rsp+40h] [rbp+18h] BYREF

  errorlib::scoped_error<hresult_error::tag>::scoped_error<hresult_error::tag>(&v4, 2, a2);
  return errorlib::scoped_error<hresult_error::tag>::operator=(a1, &v4);
}

```

## disassembly

```asm
0x1400076b4  push    rbx
0x1400076b6  sub     rsp, 20h
0x1400076ba  mov     rbx, rcx
0x1400076bd  mov     r8, rdx
0x1400076c0  mov     edx, 2
0x1400076c5  lea     rcx, [rsp+28h+arg_10]
0x1400076ca  call    ??$?0J@?$scoped_error@Utag@hresult_error@@@errorlib@@QEAA@W4type@ErrorSource@1@$$QEAJ@Z; errorlib::scoped_error<hresult_error::tag>::scoped_error<hresult_error::tag>(errorlib::ErrorSource::type,long &&)
0x1400076cf  lea     rdx, [rsp+28h+arg_10]
0x1400076d4  mov     rcx, rbx
0x1400076d7  call    ??4?$scoped_error@Utag@hresult_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<hresult_error::tag>::operator=(errorlib::scoped_error<hresult_error::tag>)
0x1400076dc  add     rsp, 20h
0x1400076e0  pop     rbx
0x1400076e1  retn
```
