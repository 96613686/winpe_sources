# ATL::CComPtr<CPimcManager>::~CComPtr<CPimcManager>(void)

- ea: `0x180006258`
- end: `0x18000627c`
- name: `??1?$CComPtr@VCPimcManager@@@ATL@@QEAA@XZ`
- size: `36`
- prototype: ``
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e8e4`
- `0x18000e914`
- `0x18000e974`
- `0x18000eb02`
- `0x18000eb26`
- `0x18000eb86`
- `0x18000eb9e`
- `0x18000ed50`
- `0x18000ed78`
- `0x18000ee2c`
- `0x18000f03b`
- `0x18000f0b3`
- `0x18000f12b`
- `0x18000f163`

## callees

- `0x180006258`
- `0x18000e4a0`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<CPimcManager>::~CComPtr<CPimcManager>(__int64 *a1)
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
0x180006258  mov     [rsp+arg_0], rcx
0x18000625d  sub     rsp, 28h
0x180006261  mov     rcx, [rcx]
0x180006264  test    rcx, rcx
0x180006267  jz      short loc_180006277
0x180006269  mov     rax, [rcx]
0x18000626c  mov     rax, [rax+10h]
0x180006270  call    cs:__guard_dispatch_icall_fptr
0x180006276  nop
0x180006277  add     rsp, 28h
0x18000627b  retn
```
