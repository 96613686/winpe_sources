# MocompInterlacedRndCtrl_Daytona

- ea: `0x1800253f0`
- end: `0x18002541e`
- name: `MocompInterlacedRndCtrl_Daytona`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180025424`

## pseudocode

```c
void __fastcall MocompInterlacedRndCtrl_Daytona(
        unsigned __int8 *a1,
        unsigned int a2,
        const unsigned __int8 *a3,
        int a4,
        unsigned int a5)
{
  MocompInterlacedCommon_Daytona(a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x1800253f0  sub     rsp, 48h
0x1800253f4  mov     eax, dword ptr [rsp+48h+arg_30]
0x1800253fb  mov     [rsp+48h+var_10], 1; char
0x180025400  mov     dword ptr [rsp+48h+var_18], eax; char
0x180025404  mov     eax, [rsp+48h+arg_28]
0x180025408  mov     [rsp+48h+var_20], eax; int
0x18002540c  mov     eax, [rsp+48h+arg_20]
0x180025410  mov     [rsp+48h+var_28], eax; int
0x180025414  call    ?MocompInterlacedCommon_Daytona@@YAXPEAEKPEBEKJJJE@Z; MocompInterlacedCommon_Daytona(uchar *,ulong,uchar const *,ulong,long,long,long,uchar)
0x180025419  add     rsp, 48h
0x18002541d  retn
```
