# wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x14000b564`
- end: `0x14000b58d`
- name: `?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `41`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000462c`
- `0x140009eb8`
- `0x14000a0d0`
- `0x14000b594`

## callees

- `0x14000b564`
- `0x140010010`

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
0x14000b564  sub     rsp, 38h
0x14000b568  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x14000b56f  test    rax, rax
0x14000b572  jnz     short loc_14000B580
0x14000b574  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x14000b57b  test    rax, rax
0x14000b57e  jz      short loc_14000B588
0x14000b580  xor     r9d, r9d
0x14000b583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b588  add     rsp, 38h
0x14000b58c  retn
```
