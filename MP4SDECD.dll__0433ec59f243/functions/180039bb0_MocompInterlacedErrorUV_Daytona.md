# MocompInterlacedErrorUV_Daytona

- ea: `0x180039bb0`
- end: `0x180039bfc`
- name: `MocompInterlacedErrorUV_Daytona`
- size: `76`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned __int8 *, unsigned int, int, int, char)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180039a94`

## pseudocode

```c
void __fastcall MocompInterlacedErrorUV_Daytona(
        unsigned __int8 *a1,
        unsigned int a2,
        const union Buffer *a3,
        char a4,
        unsigned __int8 *a5,
        unsigned int a6,
        unsigned int a7,
        char a8,
        char a9)
{
  MocompInterlacedErrorUVCommonRndCtrl_Daytona(a1, a2, a3, a4, a5, a6, a7, a8, a9, 0);
}

```

## disassembly

```asm
0x180039bb0  sub     rsp, 58h
0x180039bb4  mov     eax, dword ptr [rsp+58h+arg_40]
0x180039bbb  mov     [rsp+58h+var_10], 0; char
0x180039bc0  mov     dword ptr [rsp+58h+var_18], eax; char
0x180039bc4  mov     eax, dword ptr [rsp+58h+arg_38]
0x180039bcb  mov     [rsp+58h+var_20], eax; int
0x180039bcf  mov     eax, [rsp+58h+arg_30]
0x180039bd6  mov     [rsp+58h+var_28], eax; int
0x180039bda  mov     eax, [rsp+58h+arg_28]
0x180039be1  mov     [rsp+58h+var_30], eax; unsigned int
0x180039be5  mov     rax, [rsp+58h+arg_20]
0x180039bed  mov     [rsp+58h+var_38], rax; unsigned __int8 *
0x180039bf2  call    ?MocompInterlacedErrorUVCommonRndCtrl_Daytona@@YAXPEAEKPEBTBuffer@@_NPEBEKJJJE@Z; MocompInterlacedErrorUVCommonRndCtrl_Daytona(uchar *,ulong,Buffer const *,bool,uchar const *,ulong,long,long,long,uchar)
0x180039bf7  add     rsp, 58h
0x180039bfb  retn
```
