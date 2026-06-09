# wil::details::in1diag3::Log_HrIfNullMsg<SERVICE_STATUS_HANDLE__ *,0>(void *,uint,char const *,long,SERVICE_STATUS_HANDLE__ *,char const *,...)

- ea: `0x18000d490`
- end: `0x18000d4e4`
- name: `??$Log_HrIfNullMsg@PEAUSERVICE_STATUS_HANDLE__@@$0A@@in1diag3@details@wil@@YAPEAUSERVICE_STATUS_HANDLE__@@PEAXIPEBDJPEAU3@1ZZ`
- size: `84`
- prototype: `__int64(int, int, int, int, __int64, __int64, ...)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000e9e8`

## callees

- `0x180007acc`
- `0x18000d490`

## pseudocode

```c
__int64 wil::details::in1diag3::Log_HrIfNullMsg<SERVICE_STATUS_HANDLE__ *,0>(
        int a1,
        int a2,
        int a3,
        int a4,
        __int64 a5,
        __int64 a6,
        ...)
{
  int v7; // [rsp+20h] [rbp-48h]
  wil::details *v8; // [rsp+30h] [rbp-38h]
  __int64 retaddr; // [rsp+68h] [rbp+0h]
  va_list va; // [rsp+A0h] [rbp+38h] BYREF

  va_start(va, a6);
  if ( !a5 )
  {
    LODWORD(v8) = a4;
    wil::details::ReportFailure_HrMsg<2>(a1, a2, a3, retaddr, v7, retaddr, v8, a6, (__int64)va);
  }
  return a5;
}

```

## disassembly

```asm
0x18000d490  mov     r11, rsp
0x18000d493  sub     rsp, 68h
0x18000d497  mov     eax, r9d
0x18000d49a  cmp     [rsp+68h+arg_20], 0
0x18000d4a3  jnz     short loc_18000D4D7
0x18000d4a5  mov     qword ptr [r11-18h], 0
0x18000d4ad  lea     r11, [r11+38h]
0x18000d4b1  mov     r10, [rsp+68h+arg_28]
0x18000d4b9  mov     r9, [rsp+68h]; int
0x18000d4be  mov     [rsp+68h+var_28], r11; __int64
0x18000d4c3  mov     [rsp+68h+var_30], r10; __int64
0x18000d4c8  mov     dword ptr [rsp+68h+var_38], eax; wil::details *
0x18000d4cc  mov     [rsp+68h+var_40], r9; __int64
0x18000d4d1  call    ??$ReportFailure_HrMsg@$01@details@wil@@YAXPEAXIPEBD110J1PEAD@Z; wil::details::ReportFailure_HrMsg<2>(void *,uint,char const *,char const *,char const *,void *,long,char const *,char *)
0x18000d4d6  nop
0x18000d4d7  mov     rax, [rsp+68h+arg_20]
0x18000d4df  add     rsp, 68h
0x18000d4e3  retn
```
