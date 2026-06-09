# WPP_SF_Dd

- ea: `0x18000bdd0`
- end: `0x18000be23`
- name: `WPP_SF_Dd`
- size: `83`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

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
ULONG __fastcall WPP_SF_Dd(__int64 a1, USHORT a2, __int64 a3, int a4)
{
  int v5[6]; // [rsp+40h] [rbp-18h] BYREF
  int v6; // [rsp+78h] [rbp+20h] BYREF

  v6 = a4;
  v5[0] = dword_18001276C;
  return FastWppTraceMessage(1050, a2, (ULONGLONG)WPP_d1f5b049c58935796a293ebb03e09278_Traceguids, &v6, 4, v5, 4, 0);
}

```

## disassembly

```asm
0x18000bdd0  mov     r11, rsp
0x18000bdd3  mov     [r11+20h], r9d
0x18000bdd7  sub     rsp, 58h
0x18000bddb  mov     eax, cs:dword_18001276C
0x18000bde1  lea     r9, [r11+20h]
0x18000bde5  mov     ecx, 4
0x18000bdea  mov     qword ptr [r11-20h], 0
0x18000bdf2  mov     [r11-28h], rcx
0x18000bdf6  lea     r8, WPP_d1f5b049c58935796a293ebb03e09278_Traceguids
0x18000bdfd  mov     [rsp+58h+var_18], eax
0x18000be01  mov     r10d, 41Ah
0x18000be07  lea     rax, [r11-18h]
0x18000be0b  movzx   edx, dx
0x18000be0e  mov     [r11-30h], rax
0x18000be12  mov     [r11-38h], rcx
0x18000be16  mov     ecx, r10d
0x18000be19  call    FastWppTraceMessage
0x18000be1e  add     rsp, 58h
0x18000be22  retn
```
