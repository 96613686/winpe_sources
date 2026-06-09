# wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000b0d0`
- end: `0x18000b0f9`
- name: `?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `41`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180009bac`
- `0x180009d90`
- `0x18000a768`
- `0x18000b100`

## callees

- `0x18000b0d0`
- `0x180018010`

## pseudocode

```c
void __fastcall wil::details::WilApi_RecordFeatureUsage(wil::details *this, __int64 a2, __int64 a3)
{
  void (__fastcall *v3)(wil::details *, __int64, __int64, _QWORD); // rax

  v3 = (void (__fastcall *)(wil::details *, __int64, __int64, _QWORD))g_wil_details_internalRecordFeatureUsage;
  if ( g_wil_details_internalRecordFeatureUsage
    || (v3 = (void (__fastcall *)(wil::details *, __int64, __int64, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
  {
    v3(this, a2, a3, 0);
  }
}

```

## disassembly

```asm
0x18000b0d0  sub     rsp, 38h
0x18000b0d4  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000b0db  test    rax, rax
0x18000b0de  jnz     short loc_18000B0EC
0x18000b0e0  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000b0e7  test    rax, rax
0x18000b0ea  jz      short loc_18000B0F4
0x18000b0ec  xor     r9d, r9d
0x18000b0ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0f4  add     rsp, 38h
0x18000b0f8  retn
```
