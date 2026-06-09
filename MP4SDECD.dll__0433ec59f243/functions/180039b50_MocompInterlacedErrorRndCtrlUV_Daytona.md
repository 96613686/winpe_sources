# MocompInterlacedErrorRndCtrlUV_Daytona

- ea: `0x180039b50`
- end: `0x180039b9c`
- name: `MocompInterlacedErrorRndCtrlUV_Daytona`
- size: `76`
- prototype: `__int64 __fastcall(int, int, int, int, unsigned __int8 *, unsigned int, int, int, char)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180039a94`

## pseudocode

```c
void __fastcall MocompInterlacedErrorRndCtrlUV_Daytona(
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
  MocompInterlacedErrorUVCommonRndCtrl_Daytona(a1, a2, a3, a4, a5, a6, a7, a8, a9, 1u);
}

```

## disassembly

```asm
0x180039b50  sub     rsp, 58h
0x180039b54  mov     eax, dword ptr [rsp+58h+arg_40]
0x180039b5b  mov     [rsp+58h+var_10], 1; char
0x180039b60  mov     dword ptr [rsp+58h+var_18], eax; char
0x180039b64  mov     eax, dword ptr [rsp+58h+arg_38]
0x180039b6b  mov     [rsp+58h+var_20], eax; int
0x180039b6f  mov     eax, [rsp+58h+arg_30]
0x180039b76  mov     [rsp+58h+var_28], eax; int
0x180039b7a  mov     eax, [rsp+58h+arg_28]
0x180039b81  mov     [rsp+58h+var_30], eax; unsigned int
0x180039b85  mov     rax, [rsp+58h+arg_20]
0x180039b8d  mov     [rsp+58h+var_38], rax; unsigned __int8 *
0x180039b92  call    ?MocompInterlacedErrorUVCommonRndCtrl_Daytona@@YAXPEAEKPEBTBuffer@@_NPEBEKJJJE@Z; MocompInterlacedErrorUVCommonRndCtrl_Daytona(uchar *,ulong,Buffer const *,bool,uchar const *,ulong,long,long,long,uchar)
0x180039b97  add     rsp, 58h
0x180039b9b  retn
```
