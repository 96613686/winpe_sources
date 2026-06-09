# WPP_SF_L

- ea: `0x18000be2c`
- end: `0x18000be5d`
- name: `WPP_SF_L`
- size: `49`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180001c40`
- `0x180001e70`
- `0x1800029a0`
- `0x180002b40`
- `0x180003520`
- `0x1800035d0`
- `0x180003760`
- `0x18000750c`
- `0x180007594`
- `0x180007630`

## callees

- `0x1800072e0`

## pseudocode

```c
ULONG __fastcall WPP_SF_L(__int64 a1, USHORT a2, ULONGLONG a3, int a4)
{
  int v5; // [rsp+58h] [rbp+20h] BYREF

  v5 = a4;
  return FastWppTraceMessage(1050, a2, a3, &v5, 4, 0);
}

```

## disassembly

```asm
0x18000be2c  mov     rax, rsp
0x18000be2f  mov     [rax+20h], r9d
0x18000be33  sub     rsp, 38h
0x18000be37  mov     qword ptr [rax-10h], 0
0x18000be3f  lea     r9, [rax+20h]
0x18000be43  mov     ecx, 41Ah
0x18000be48  movzx   edx, dx
0x18000be4b  mov     qword ptr [rax-18h], 4
0x18000be53  call    FastWppTraceMessage
0x18000be58  add     rsp, 38h
0x18000be5c  retn
```
