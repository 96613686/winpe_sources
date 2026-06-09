# MocompInterlaced_Daytona

- ea: `0x180039c10`
- end: `0x180039c3e`
- name: `MocompInterlaced_Daytona`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180025424`

## pseudocode

```c
void __fastcall MocompInterlaced_Daytona(
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
0x180039c10  sub     rsp, 48h
0x180039c14  mov     eax, dword ptr [rsp+48h+arg_30]
0x180039c1b  mov     [rsp+48h+var_10], 0; char
0x180039c20  mov     dword ptr [rsp+48h+var_18], eax; char
0x180039c24  mov     eax, [rsp+48h+arg_28]
0x180039c28  mov     [rsp+48h+var_20], eax; int
0x180039c2c  mov     eax, [rsp+48h+arg_20]
0x180039c30  mov     [rsp+48h+var_28], eax; int
0x180039c34  call    ?MocompInterlacedCommon_Daytona@@YAXPEAEKPEBEKJJJE@Z; MocompInterlacedCommon_Daytona(uchar *,ulong,uchar const *,ulong,long,long,long,uchar)
0x180039c39  add     rsp, 48h
0x180039c3d  retn
```
