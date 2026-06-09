# ATL::CComPtr<CPimcContext::CEventSink>::~CComPtr<CPimcContext::CEventSink>(void)

- ea: `0x180006234`
- end: `0x180006258`
- name: `??1?$CComPtr@VCEventSink@CPimcContext@@@ATL@@QEAA@XZ`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ed68`
- `0x18000ee1c`

## callees

- `0x180006234`
- `0x18000e4a0`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<CPimcContext::CEventSink>::~CComPtr<CPimcContext::CEventSink>(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x180006234  mov     [rsp+arg_0], rcx
0x180006239  sub     rsp, 28h
0x18000623d  mov     rcx, [rcx]
0x180006240  test    rcx, rcx
0x180006243  jz      short loc_180006253
0x180006245  mov     rax, [rcx]
0x180006248  mov     rax, [rax+10h]
0x18000624c  call    cs:__guard_dispatch_icall_fptr
0x180006252  nop
0x180006253  add     rsp, 28h
0x180006257  retn
```
