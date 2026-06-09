# SmartComPtr<ABI::Windows::Devices::Printers::IPdlPassthroughTarget>::~SmartComPtr<ABI::Windows::Devices::Printers::IPdlPassthroughTarget>(void)

- ea: `0x180004350`
- end: `0x18000437b`
- name: `??1?$SmartComPtr@UIPdlPassthroughTarget@Printers@Devices@Windows@ABI@@@@QEAA@XZ`
- size: `43`
- prototype: ``
- caller_count: `30`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800bf530`
- `0x1800bf550`
- `0x1800bf590`
- `0x1800bf610`
- `0x1800bf630`
- `0x1800bf670`
- `0x1800bf690`
- `0x1800bf6b0`
- `0x1800bf6d0`
- `0x1800bf6f0`
- `0x1800bf710`
- `0x1800bf750`
- `0x1800bf770`
- `0x1800bf7b0`
- `0x1800bf7d0`
- `0x1800bf850`
- `0x1800bf890`
- `0x1800bf8d0`
- `0x1800bf8f0`
- `0x1800bf930`
- `0x1800bf9d0`
- `0x1800bf9f0`
- `0x1800bfa10`
- `0x1800bfb70`
- `0x1800c00c0`
- `0x1800c00e0`
- `0x1800c0100`
- `0x1800c01b0`
- `0x1800c0210`
- `0x1800c02e0`

## callees

- `0x180004350`
- `0x1800bf3b0`

## pseudocode

```c
__int64 __fastcall SmartComPtr<ABI::Windows::Devices::Printers::IPdlPassthroughTarget>::~SmartComPtr<ABI::Windows::Devices::Printers::IPdlPassthroughTarget>(
        __int64 *a1)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *a1;
  if ( v2 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x180004350  push    rbx
0x180004352  sub     rsp, 20h
0x180004356  mov     rbx, rcx
0x180004359  mov     rcx, [rcx]
0x18000435c  test    rcx, rcx
0x18000435f  jz      short loc_18000436E
0x180004361  mov     rax, [rcx]
0x180004364  mov     rax, [rax+10h]
0x180004368  call    cs:__guard_dispatch_icall_fptr
0x18000436e  mov     qword ptr [rbx], 0
0x180004375  add     rsp, 20h
0x180004379  pop     rbx
0x18000437a  retn
```
