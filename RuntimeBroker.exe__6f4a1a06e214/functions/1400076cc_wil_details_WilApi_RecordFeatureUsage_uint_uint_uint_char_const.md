# wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x1400076cc`
- end: `0x1400076f7`
- name: `?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `43`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140005238`
- `0x14000c21c`
- `0x14000c340`
- `0x14000cbc4`

## callees

- `0x1400076cc`
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
0x1400076cc  sub     rsp, 38h
0x1400076d0  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1400076d7  test    rax, rax
0x1400076da  jz      short loc_1400076E9
0x1400076dc  xor     r9d, r9d
0x1400076df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400076e4  add     rsp, 38h
0x1400076e8  retn
0x1400076e9  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1400076f0  test    rax, rax
0x1400076f3  jz      short loc_1400076E4
0x1400076f5  jmp     short loc_1400076DC
```
